# SimpleBook Development - Current Status
Last Updated: 2024-12-16

## Active Work
- Setting up Pi-based memory system for AI collaboration continuity
- Preparing to audit all existing parsers using GitHub test files
- PDF parser troubleshooting for scanned bank statements

## Recently Completed
- [x] Fixed critical double-counting bug in deposits_parser.py and other_credits_parser.py
- [x] QFX parser functional and tested
- [x] Raspberry Pi 4 received and OS installed
- [x] SSH access to Pi established
- [x] Memory file structure created on Pi

## Known Issues
### Critical
- PDF parser fails on scanned bank statements (low quality OCR)
- Handwritten payee extraction unreliable
- Need to test all parsers against actual bank statement files

### Under Investigation
- Best PDF library for scanned documents (currently using PDF Plumber)
- Alternative OCR approaches for handwritten text

## Next Session Goals
1. Complete Pi GitHub setup and auto-sync
2. Audit all existing parsers using test files from GitHub
3. Document specific PDF parser failure cases with examples
4. Research alternative PDF processing libraries

## Blockers
- Mobile home installation disaster (4" out of level, potential frame damage)
- Physical construction work reducing available coding time

## Context for AI Sessions
- Chris is self-taught in Python (3 months experience)
- Prefers understanding logic over copying code
- Works on SimpleBook between construction jobs
- Goal: Exit construction work, transition to software development
- Memory continuity is critical - previous AI sessions lost context repeatedly
Test update: Tue 16 Dec 2025 11:56:49 AM EST
