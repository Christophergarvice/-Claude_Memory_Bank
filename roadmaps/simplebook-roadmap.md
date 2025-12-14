# SimpleBook Development Roadmap

## Phase 1: Property Management ✓
- [x] Basic property tracking
- [x] Tenant management foundation
- [x] Initial rental income tracking

## Phase 2: Accounting Core (IN PROGRESS)

### QFX Parsers (Electronic Statements)
- [x] qfx_parser.py - Core QFX parsing, date normalization
- [x] checks_parser.py - Check extraction with vendor parsing
- [x] other_debits_parser.py - Non-check debits (cards, ACH, fees)
- [x] other_credits_parser.py - Refunds, ACH credits, reversals
- [ ] deposits_parser.py - **NEEDS FIX** (overlap bug with other_credits)
- [x] combine_credits.py - Working, needs duplicate detection
- [x] combine_debits.py - Needs duplicate detection + date sorting
- [ ] parsers/__init__.py - Needs exports

### UCBI PDF Parsers (Scanned Bank Statements)
- [x] Module 1: Deposits parser
- [x] Module 2: Other credits parser
- [x] Module 3: Checks parser
- [x] Module 4: Other debits parser
- [x] Module 5: Combine all parsers

### CSV Parsers
- [ ] Credit card statement parser
- [ ] Bank CSV format parser
- [ ] Multi-bank format support

### Core Accounting
- [ ] Transaction categorization
- [ ] Vendor management
- [ ] Account reconciliation
- [ ] Monthly close process

## Phase 3: Tax Management
- [ ] Income tracking by property
- [ ] Expense categorization for taxes
- [ ] 1099 preparation
- [ ] Depreciation schedules
- [ ] Tax report generation

## Phase 4: Dashboard/UI
- [ ] Property overview dashboard
- [ ] Cash flow visualization
- [ ] Expense tracking
- [ ] Maintenance scheduling
- [ ] Tenant portal basics

## Phase 5: Web Interface
- [ ] Web-based access
- [ ] Multi-user support
- [ ] Cloud synchronization
- [ ] Mobile-responsive design

## Phase 6: Mobile App
- [ ] Native mobile apps
- [ ] Photo upload (receipts)
- [ ] Push notifications
- [ ] Offline mode

## Phase 7: Integration/Cloud
- [ ] Bank API integration
- [ ] Payment processing
- [ ] Cloud backup
- [ ] Multi-property scaling

## Current Status
- **30-40 modules built** across SimpleBook_Core, SimpleBook, EchoAuto_Memory
- **Critical bug discovered**: deposits/other_credits overlap
- **Next priority**: Fix parser bug, add duplicate detection
- **Biggest challenge**: PDF parsing, especially OCR for handwritten payees
