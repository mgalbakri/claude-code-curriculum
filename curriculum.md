# Claude Code Mastery Curriculum v2
## February 2026 Edition

**Student:** MGB
**Start Date:** February 12, 2026
**Duration:** 12 Weeks
**Goal:** From zero coding knowledge to Claude Code expert

---

## Phase I: Foundation (Weeks 1–3)

### WEEK 1: The Terminal & File System
**Subtitle:** Your gateway to Claude Code
**Objective:** Master command-line navigation, file management, and install Node.js.

**Topics:**
- What is a terminal and why developers use it
- Opening Terminal on Mac (Applications → Utilities → Terminal)
- Navigation: pwd, ls, cd, cd .., cd ~
- File management: mkdir, touch, cp, mv, rm
- Reading files: cat, less, head, tail
- Environment: echo, export, PATH
- Installing Node.js and npm
- Package managers: Homebrew (Mac)

**Activities:**
- Navigate to your home directory and explore the file structure
- Create a project folder structure for Bihar Fleet
- Create, move, copy, and delete practice files
- Install Node.js using Homebrew or nvm
- Verify installation with node --version and npm --version

**Deliverable:** A project folder structure created entirely from the terminal with Node.js installed.
**Skills:** Terminal navigation, file management, reading error messages, Node.js setup

---

### WEEK 2: Git & Version Control
**Subtitle:** Never lose your work again
**Objective:** Understand how professional developers track changes and collaborate.

**Topics:**
- What is Git and why every developer uses it
- git init, git add, git commit — the core cycle
- git log, git diff, git status — understanding your history
- Branches: git branch, git checkout, git merge
- GitHub: creating repos, pushing code, pull requests
- GitHub Personal Access Tokens for Claude Code integration

**Activities:**
- Initialize a Git repository for your vessel database project
- Practice the add → commit cycle with meaningful commit messages
- Create a branch, make changes, merge it back
- Create a GitHub account and push your first repository
- Open and merge your first pull request
- Generate a GitHub Personal Access Token

**Deliverable:** Your vessel database project published on GitHub with at least 5 meaningful commits and 1 merged PR.
**Skills:** Git fundamentals, GitHub, branching, pull requests, authentication tokens

---

### WEEK 3: Claude Code — First Contact
**Subtitle:** Your AI coding partner is online
**Objective:** Install Claude Code, run your first session, and understand the core interaction model.

**Topics:**
- Installing Claude Code (npm install -g @anthropic-ai/claude-code)
- Authentication: API key vs. Claude Pro/Max subscription
- Anatomy of a session: prompt → plan → execute → review
- Plan mode: always start here
- Reading diffs: understanding what Claude changed
- Essential commands: /help, /compact, /clear, /model, /context
- Introduction to CLAUDE.md
- Understanding context window and token usage

**Activities:**
- Install Claude Code and authenticate
- Run your first session: ask Claude to build a simple vessel data file
- Practice Plan mode: describe what you want before Claude codes
- Review a diff and understand every change
- Use /compact during a long session
- Create your first CLAUDE.md file

**Deliverable:** Claude Code installed and configured. First working script built entirely through Claude Code with a CLAUDE.md file.
**Skills:** Claude Code basics, Plan mode, diff reading, /compact, CLAUDE.md creation

#### Current Model Lineup (February 2026)

- **Claude Opus 4.6** (Feb 2026) — The most capable model. Best for agentic coding, complex tool use, and multi-step reasoning. Use when quality matters most.
- **Claude Sonnet 4.5** (Sep 2025) — Strong coding and reasoning with good speed/cost balance. Default choice for most Claude Code tasks.
- **Claude Haiku 4.5** (Oct 2025) — Fastest and most affordable. Matches prior state-of-the-art coding. Use for quick tasks and high-volume operations.

**Key takeaway:** Claude Code lets you switch models mid-session. Use Opus 4.6 for complex architecture decisions, Sonnet 4.5 for everyday coding, and Haiku 4.5 for rapid iteration.

---

## Phase II: Building (Weeks 4–8)

### WEEK 4: Your First Full Application
**Subtitle:** From idea to deployed tool
**Objective:** Build a complete, working web application from scratch using Claude Code.

**Topics:**
- What is React and Next.js (conceptual overview)
- Project scaffolding with Claude Code
- Components: building blocks of modern web apps
- Styling with Tailwind CSS
- Deployment to Vercel
- Environment variables and configuration

**Activities:**
- Ask Claude Code to scaffold a Next.js project for Bihar Fleet vessel tracking
- Build a vessel list component showing all 23 ships
- Add search and filter functionality
- Style the application with Tailwind CSS
- Deploy to Vercel for the first time
- Share the live URL with someone

**Deliverable:** A deployed vessel tracking web app on Vercel showing Bihar Fleet's 23 vessels.
**Skills:** React/Next.js basics, component thinking, Tailwind CSS, Vercel deployment

---

### WEEK 5: Databases & APIs
**Subtitle:** Where your data lives
**Objective:** Connect your application to a real database and understand data flow.

**Topics:**
- What is a database and why you need one
- Supabase: your backend-as-a-service
- SQL basics: SELECT, INSERT, UPDATE, DELETE
- Database schema design
- API routes in Next.js
- CRUD operations (Create, Read, Update, Delete)
- Row Level Security basics

**Activities:**
- Set up a Supabase project
- Design a schema for vessel tracking data
- Ask Claude Code to create API routes
- Build forms to add and edit vessel data
- Implement all CRUD operations
- Add basic data validation

**Deliverable:** Your vessel tracker connected to Supabase with full CRUD operations.
**Skills:** Database concepts, Supabase, SQL basics, API routes, CRUD operations

---

### WEEK 6: Authentication & Dashboards
**Subtitle:** Real apps need real security
**Objective:** Add user authentication and build a professional dashboard.

**Topics:**
- Authentication concepts: login, sessions, tokens
- Supabase Auth integration
- Protected routes and middleware
- Dashboard design principles
- Data visualization with charts
- Responsive design (mobile + desktop)
- The /code-review workflow

**Activities:**
- Add Supabase Auth to your vessel tracker
- Create login and signup pages
- Protect dashboard routes from unauthorized access
- Build a dashboard with vessel status overview
- Add charts showing fleet utilization
- Make the dashboard responsive
- Run /code-review on your codebase

**Deliverable:** A secure, authenticated dashboard with data visualization.
**Skills:** Authentication, dashboards, error handling, /code-review, responsive design

---

### WEEK 7: Testing & Quality
**Subtitle:** Maintaining code quality at scale
**Objective:** Understand why testing matters and how to direct Claude to write tests.

**Topics:**
- What are tests and why they matter
- Unit tests, integration tests overview
- The verification loop: instruct → code → test → verify
- Using Claude to write tests
- Reading test output
- The /code-review workflow

**Activities:**
- Ask Claude to write tests for your dashboard
- Run the tests and read the output
- Find a bug → write a test → fix the bug
- Use /code-review to audit your project
- Add test commands to CLAUDE.md

**Deliverable:** Your fleet app with a test suite that runs automatically.
**Skills:** Testing concepts, verification loops, quality assurance

---

### WEEK 8: Second Project — Domain Deep Dive
**Subtitle:** Building something only YOU could design
**Objective:** Apply everything learned to build a second, more complex application.

**Topics:**
- Project scoping: defining requirements
- Breaking complex projects into phases
- Working with external APIs
- Data visualization: charts, maps
- Progressive enhancement
- Documentation: READMEs that matter

**Activities:**
- Choose your second project (Alshams Energy fuel tracking, gold price monitor, or workout tracker)
- Write a detailed project brief
- Build in phases: data → logic → UI → polish
- Deploy to Vercel with documentation
- Self-review using /code-review

**Deliverable:** A second deployed application solving a real business problem.
**Skills:** Project scoping, phased development, external APIs, data visualization

#### Claude Developer Platform & Web Access

- **Claude Developer Platform** (https://platform.claude.com/) — Central hub for API docs, usage dashboards, and key management. Useful when building applications that integrate Claude.
- **Claude Code on the Web** (https://claude.ai/code) — Browser-based access to Claude Code. Explore how it complements the CLI workflow for quick tasks or when terminal access isn't available.

---

## Phase III: Mastery (Weeks 9–12)

### WEEK 9: Skills, Hooks & Custom Commands
**Subtitle:** Teaching Claude YOUR workflow
**Objective:** Deep dive into Claude Code's extensibility system.

**Topics:**
- Skills: SKILL.md files for project patterns
- Skill frontmatter: name, description, allowed-tools
- How skills auto-invoke based on context matching
- Custom slash commands via .claude/commands/
- Hooks: PreToolUse, PostToolUse, UserPromptSubmit, Stop, SubagentStop
- Creating hooks for formatting and linting
- Hook configuration in .claude/settings.json

**Activities:**
- Create a custom skill for your domain (maritime or energy)
- Write a hook for auto-formatting code on save
- Create a custom /deploy command
- Test skill auto-invocation
- Build a notification hook that alerts on completion

**Deliverable:** At least 2 custom skills, 1 hook, and 1 custom command.
**Skills:** Skills system, hooks, custom commands, workflow automation

---

### WEEK 10: MCP Servers & Plugins
**Subtitle:** Connecting Claude to your toolchain
**Objective:** Learn Model Context Protocol to connect Claude Code to external tools.

**Topics:**
- What is MCP and why it matters
- MCP architecture: servers, tools, resources
- Building an MCP server with Python (FastMCP)
- Tool definitions with Pydantic models
- Connecting MCP servers to Claude Code
- Available community MCP servers
- MCP in Claude.ai vs Claude Code

**Activities:**
- Review the curriculum-updater MCP server you already built
- Build a second MCP server (vessel position lookup or fuel price API)
- Connect both to Claude Code
- Use MCP tools in a real workflow
- Explore community MCP servers (GitHub, Slack, etc.)

**Deliverable:** Two working MCP servers connected to Claude Code.
**Skills:** MCP architecture, FastMCP, tool design, server integration

---

### WEEK 11: Agent Teams & Parallel Sessions
**Subtitle:** Orchestrating AI workers
**Objective:** Use Claude Code's multi-agent capabilities for complex projects.

**Topics:**
- Agent Teams: multi-agent collaboration
- How teammates communicate directly and share task lists
- Self-coordination between agents
- Headless mode for background tasks
- Parallel sessions for independent workstreams
- Orchestration patterns: fan-out, pipeline, supervisor
- Resource management and context optimization

**Activities:**
- Set up an agent team for a full-stack project
- Assign frontend and backend to separate agents
- Run parallel sessions for independent tasks
- Use headless mode for automated testing
- Build an orchestration workflow for your capstone project

**Deliverable:** A project built using agent teams with at least 3 coordinated agents.
**Skills:** Agent teams, parallel sessions, headless mode, orchestration

#### Claude Agent SDK

- Released alongside Sonnet 4.5, the **Claude Agent SDK** enables building custom agents with Claude.
- Relevant to agent teams and parallel session workflows covered this week.
- Explore how the SDK complements MCP servers for orchestrating multi-agent pipelines.
- **Reference:** https://www.anthropic.com/news/claude-sonnet-4-5

---

### WEEK 12: Capstone & Portfolio
**Subtitle:** Putting it all together
**Objective:** Build a production-quality project showcasing everything you've learned.

**Topics:**
- Capstone project planning and architecture
- Professional Git workflow: feature branches, PRs, code review
- CI/CD: automated testing and deployment
- Production readiness: error handling, logging, monitoring
- Portfolio presentation: GitHub profile, README, live demos
- CLAUDE.md mastery: comprehensive project documentation

**Activities:**
- Plan your capstone (recommended: comprehensive Bihar Fleet management system)
- Build using agent teams and MCP integrations
- Implement full Git workflow with feature branches
- Set up CI/CD pipeline
- Write professional documentation
- Deploy production version
- Create portfolio page showcasing all projects

**Deliverable:** A production-deployed capstone project with full documentation, CI/CD, and a portfolio page linking all 12 weeks of work.
**Skills:** Full-stack development, professional workflows, CI/CD, portfolio presentation

---

## Appendices

### Appendix A: Daily Practice Checklist
- [ ] Open terminal and navigate to project folder
- [ ] Pull latest changes (git pull)
- [ ] Review yesterday's work (git log, git diff)
- [ ] Start Claude Code session with clear objective
- [ ] Use Plan mode before coding
- [ ] Commit progress with meaningful messages
- [ ] Push to GitHub
- [ ] Update CLAUDE.md if needed

### Appendix B: Essential Commands Reference

**Terminal:**
pwd, ls, cd, mkdir, touch, cp, mv, rm, cat, less, head, tail, echo, grep, find

**Git:**
git init, git add, git commit, git push, git pull, git branch, git checkout, git merge, git log, git diff, git status, git stash

**Claude Code:**
/help, /compact, /clear, /model, /context, /init, /code-review, /cost

**npm:**
npm install, npm run dev, npm run build, npx

### Appendix C: CLAUDE.md Starter Template
```markdown
# CLAUDE.md

## Project Overview
[What this project does in 1-2 sentences]

## Tech Stack
[List key technologies]

## Commands
[How to install, run, test, deploy]

## Architecture
[Key files and their roles]

## Conventions
[Code style, naming, patterns to follow]
```

### Appendix D: Recommended Resources
- Anthropic Documentation: https://docs.anthropic.com
- Claude Code Docs: https://docs.anthropic.com/en/docs/claude-code
- Boris Cherny on X: https://x.com/anthropaboris
- Vercel Documentation: https://vercel.com/docs
- Supabase Documentation: https://supabase.com/docs
- MDN Web Docs: https://developer.mozilla.org

---

### Appendix E: Claude Haiku 4.5 (October 2025)

Claude Haiku 4.5 matches state-of-the-art coding capabilities from months ago while delivering unprecedented speed and cost-efficiency. Useful for rapid iteration, high-volume tasks, and cost-sensitive workflows in Claude Code.

- **Reference:** https://www.anthropic.com/news/claude-haiku-4-5

---

*Curriculum Version: 2.0 — February 2026*
*Model: Claude Opus 4.6*
*Last Updated: 2026-02-12*
