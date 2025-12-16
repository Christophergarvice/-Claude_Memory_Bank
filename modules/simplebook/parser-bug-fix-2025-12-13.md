# Parser Bug Fix - December 13, 2025

## Critical Bug: Credit Parser Overlap

### Discovery
Comprehensive audit of QFX parsers revealed that `deposits_parser.py` and `other_credits_parser.py` both process ALL credits (amount > 0), causing duplicate transaction counting.

### Test Results BEFORE Fix
```
Input: 2 credit transactions (1 deposit, 1 refund)
Output: 3 credit records
- Deposit counted: 1 time ✓
- Refund counted: 2 times ✗ (DUPLICATE)
```

### Root Cause
```python
# deposits_parser.py - TOO BROAD
if amount > 0:
    deposits.append(...)  # Catches EVERYTHING

# other_credits_parser.py - ALSO TOO BROAD  
if amount > 0 and not "DEPOSIT" in name:
    other_credits.append(...)  # Still catches some deposits
```

### The Fix
Make deposits_parser EXCLUSIVE - only process explicit deposit indicators:
```python
deposit_indicators = [
    "DEPOSIT",
    "MOBILE DEPOSIT", 
    "ATM DEPOSIT",
    "REGULAR DEPOSIT",
    "CHECK DEPOSIT"
]

is_deposit = any(ind in name or ind in memo for ind in deposit_indicators)
if not is_deposit:
    continue  # Let other_credits_parser handle it
```

### Test Results AFTER Fix
```
Input: 2 credit transactions (1 deposit, 1 refund)
Output: 2 credit records ✓
- Deposit: 1 time ✓
- Refund: 1 time ✓
- NO DUPLICATES ✓
```

### Action Required
Replace `deposits_parser.py` in SimpleBook_Core with fixed version before next coding session.

### Impact
- Prevents inflated accounting totals
- Eliminates duplicate transaction records
- Ensures accurate credit tracking
- Critical for reliable financial reporting
