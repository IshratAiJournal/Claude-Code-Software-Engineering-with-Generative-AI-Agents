Module 02 – Build Multiple Versions of a Feature with Best-of-N Pattern

Overview:
In this module, I learned how to use the Best-of-N pattern to build multiple versions of the same feature using Claude Code, compare them, and choose the best solution.

What is Best-of-N?
- Unlike humans, AI (Claude Code) is:
  - Fast
  - Cheap
  - Egoless
- We build 3 different versions of the Data Export feature:
  1. Simple implementation
  2. Advanced export system with options
  3. Cloud-integrated export system

Version 1 – Simple CSV Export:
- Simple "Export Data" button
- Exports all expenses as a CSV file
- Columns: Date, Category, Amount, Description
- Minimal UI
- Used standard browser APIs

Process:
git checkout -b feature-data-export-v1
Implemented feature → Tested → Committed changes

Version 2 – Advanced Export with Options:
- Export modal/dialog
- Multiple formats: CSV, JSON, PDF
- Date & category filters
- Data preview table
- Custom filename field
- Export summary
- Loading indicators

Process:
git checkout -b feature-data-export-v2
Implemented advanced feature → Tested thoroughly → Committed changes

Version 3 – Cloud Integration:
- Simulated email export flow
- Google Sheets integration mockup
- Backup scheduling UI
- Export history tracking
- Shareable links and QR codes
- Integration mockups (Dropbox, OneDrive)
- Export templates (Tax Report, Monthly Summary, etc.)

Process:
git checkout -b feature-data-export-v3
Implemented cloud-integrated solution → Made UI feel like SaaS app → Committed changes

Comparing Versions:
Switched between branches to test:
git checkout feature-data-export-v1
npm run dev  # Test simple CSV export

git checkout feature-data-export-v2
npm run dev  # Test advanced modal

git checkout feature-data-export-v3
npm run dev  # Test cloud integration features

Key Learnings:
- AI helps implement multiple diverse solutions quickly and creatively
- Best-of-N lets me compare approaches without wasting time
- Understanding project architecture holistically
- Cloud integration offers modern, professional application feel
- Learned effective Git branching for version control
