# SimpleBook Core - Master Development Plan

## Project Vision
Custom accounting and property management system for rental properties, designed to replace QuickBooks with purpose-built tools for Chris's 46-acre mobile home park and construction business.

## 7-Phase Development Roadmap

### Phase 1: Property Management Foundation
- [ ] Property/unit tracking system
- [ ] Tenant management and lease tracking
- [ ] Rent payment processing
- [ ] Late fee automation
- [ ] Maintenance request tracking
- [ ] Document storage per property/tenant

### Phase 2: Accounting Core
- [x] QFX parser (bank transactions)
- [x] Deposits parser (fixed double-counting)
- [x] Other credits parser (fixed double-counting)
- [ ] PDF parser (bank statements) - IN PROGRESS
- [ ] Check register reconciliation
- [ ] Expense categorization system
- [ ] Invoice generation
- [ ] Payment tracking

### Phase 3: Tax Management
- [ ] 1099 generation and tracking
- [ ] Schedule E automation
- [ ] Depreciation calculator
- [ ] Tax document organization
- [ ] Year-end reporting

### Phase 4: Dashboard & UI
- [ ] Financial overview dashboard
- [ ] Property performance metrics
- [ ] Cash flow visualization
- [ ] Alert system (late payments, maintenance)

### Phase 5: Web Interface
- [ ] Tenant portal
- [ ] Online rent payment
- [ ] Maintenance request submission
- [ ] Document access for tenants

### Phase 6: Mobile App
- [ ] Property inspection checklist
- [ ] Photo documentation
- [ ] Quick expense entry
- [ ] Mobile notifications

### Phase 7: Integration & Cloud
- [ ] Bank API integration
- [ ] Automated backups
- [ ] Multi-device sync
- [ ] Cloud deployment

## Core Architecture Decisions
- Python-based backend
- Modular repository structure
- Custom parsers for financial data
- Local-first with cloud sync option

## Repository Structure
- simplebook_core/ - Main application
- simplebook_parsers/ - QFX, PDF, transaction parsers
- simplebook_testing/ - Test files and validation
- Claude_Memory_Bank/ - AI collaboration continuity

## Critical Requirements
- Must handle scanned bank statements
- Must extract handwritten payee information
- Must prevent double-counting (FIXED)
- Must maintain audit trail
- Must support multiple properties
