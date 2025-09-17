# Claude Code – Module 5 Notes

## 1. Version Control with Claude Code

Every human who writes code makes mistakes. Version control is **critically important** because it allows us to:

- Go back in time and undo mistakes
- Isolate changes in branches
- Keep track of all modifications

When using Claude Code:

1. Create a **feature branch** before making any changes.
2. Commit all changes in that branch.
3. Use a **branch naming template** for consistency.
4. Optionally, use **AI naming** to differentiate human vs AI branches.

Example workflow:

```bash
git checkout -b feature/dynamic-categories
# Claude Code works in this branch
# After changes, commit with detailed messages
git commit -m "Add dynamic categories feature"
Benefits:

Isolated feature development

Easy to discard or merge branches

AI can generate detailed commit messages

Helps scale work for big projects

2. Parallel Development with Git Worktrees
Git Worktrees allow multiple branches to be checked out in separate folders, so features can be developed in parallel without conflicts.

Setting Up Worktrees
Example: Developing two features simultaneously:

Data export system → feature/data-export

Analytics dashboard → feature/analytics-dashboard

Commands:

bash
Copy code
# Create worktrees
git worktree add ../expense-tracker-export -b feature/data-export
git worktree add ../expense-tracker-analytics -b feature/analytics-dashboard

# List worktrees
git worktree list
Launch Claude Code in each worktree:

bash
Copy code
# Terminal 1 - Export feature
cd ../expense-tracker-export
claude

# Terminal 2 - Analytics feature
cd ../expense-tracker-analytics
claude
Each worktree:

Is completely independent

Allows parallel development

Avoids conflicts between features

Merging Worktree Features Back
Steps:

Stop Claude Code in each worktree

Go to main branch

Merge feature branches into an integration branch:

bash
Copy code
git checkout main
git checkout -b integration/export-analytics
git merge feature/data-export
git merge feature/analytics-dashboard
Resolve conflicts, test features, and integrate safely.

3. Claude Subagents & Tasks
Subagents are small Claude Code instances that work in parallel on specialized tasks.

Benefits:

Independent context windows

Parallel execution

Specialized focus per subagent

Example Usage
Run two subagents in parallel:

text
Copy code
Subagent 1 -> Analyze backend improvements
Subagent 2 -> Analyze frontend improvements
Multiple subagents are useful for:

Large codebases

Initial project assessment

Domain separation (frontend vs backend vs database)

4. Parallel Feature Development: Subagents + Worktrees
You can combine Git Worktrees with subagents to fully parallelize development.

Workflow Example:

Run Claude Code from parent directory:

bash
Copy code
cd /parent-directory-of-expense-tracker-ai
claude
Create worktrees for features:

bash
Copy code
git worktree add ../expense-tracker-top-expense-categories -b feature/top-expense-categories
git worktree add ../expense-tracker-top-vendors -b feature/top-vendors
Spawn subagents for each feature:

Implement the feature

Include proper testing and error handling

Write a summary in [feature-name].work.txt

Final summary:

Read all .work.txt files

Provide a comprehensive summary of features

Plan next integration steps

Example Final Summary Output
Features Successfully Implemented:

Top Expense Categories Page

Location: /app/categories/page.tsx

Shows spending amounts, percentages, transaction counts

Color-coded categories with emojis

Real-time data synchronization

Top Vendors Page

Location: /app/vendors/page.tsx

Top 10 vendors with spending info

Dynamic bar charts

Summary cards

Worktrees Created:

../expense-tracker-top-expense-categories

../expense-tracker-top-vendors

Next Steps:

Merge branches into integration

Resolve conflicts (e.g., Navigation.tsx)

Test full application

Add dashboard links to new pages

5. Module 5 Key Takeaways
Always use version control and feature branches

Git worktrees allow parallel, conflict-free development

Subagents let Claude Code work on multiple features simultaneously

Combine worktrees + subagents for fast, organized development

Keep detailed summaries for integration and testing

6. Commands & Automation Examples
Parallel Work Command
Save as .claude/commands/parallel-work.md

text
Copy code
I want to develop features in parallel for my expense tracker app using Git worktrees: $ARGUMENTS

Please help me set up the worktree environment:
1. For each feature mentioned, create a worktree at ../expense-tracker-[feature-name] with branch feature/[feature-name]
2. Set up the development environment in each worktree
3. List all worktrees to confirm they were created
4. Explain what each worktree will contain and how they're isolated
Integrate Parallel Work Command
Save as .claude/commands/integrate-parallel-work.md

text
Copy code
I have features developed in parallel worktrees that I need to integrate: $ARGUMENTS

Please help me integrate these features:
1. Create a new integration branch called "integration/parallel-features"
2. For each feature name provided, merge the branch feature/[feature-name] into the integration branch
3. Resolve any merge conflicts that arise
4. Test that all features work together
5. Run all tests to ensure nothing is broken
6. Once integration is successful, merge to main and clean up branches
Usage Example:

bash
Copy code
/integrate-parallel-work budget-tracking notifications user-settings
pgsql
Copy code



