Module 01 – Getting Started with Claude Code & Building Your First Application

Overview:
In this module, I learned how to get started with Claude Code and build my first application – an Expense Tracker.

Prerequisites:
- Basic understanding of command line/terminal
- Node.js installed
- Git installed and configured
- Claude Code installed and working

Steps I Followed:

1. Installation:
- Signed up for Claude Code subscription or API key
- Installed via npm:
  npm install -g @anthropic-ai/claude-code
- Verified installation:
  claude --version

2. First Launch:
- Created project directory:
  mkdir expense-tracker-ai
  cd expense-tracker-ai
- Launched Claude Code:
  claude

3. Interface Overview:
Key parts:
- Prompt input
- Tool permission requests
- Real-time file editing
- Todo updates
- Slash commands: /init, /permissions, /clear, /help

First Big Prompt:
I asked Claude to build a modern NextJS Expense Tracking Application with:
- Add expenses (date, category, amount, description)
- Organized list of expenses
- Filter by date/category
- Dashboard with spending summaries

Claude created:
- Project structure with NextJS + TypeScript + Tailwind CSS
- React components
- State management
- Basic validation
- Professional layout

Testing the App:
- Ran development server:
  npm run dev
- Opened in browser: http://localhost:3000
- Tested adding/viewing expenses.

Takeaway:
This module taught me how to:
- Think in vision-level prompts
- Build a full application using Claude Code
- Understand AI as labor rather than just a tool
- Save tons of development time 🚀
