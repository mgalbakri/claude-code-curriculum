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

#### Terminal & Environment Updates (Feb 2026)
- **Terminal rendering performance** improved significantly (v2.1.39)
- **Fatal errors** are now properly displayed instead of being swallowed (v2.1.39)
- **Process hanging** after session close fixed (v2.1.39)
- **Vim normal mode** now supports arrow key history navigation when cursor cannot move further (v2.1.20)
- **External editor shortcut** (Ctrl+G) added to the help menu (v2.1.20)
- **Customizable spinner verbs** via `spinnerVerbs` setting (v2.1.23)
- **mTLS and proxy connectivity** fixed for corporate proxies and client certificates (v2.1.23)
- **Installation change:** npm installations are deprecated — use `claude install` instead (v2.1.15)

**Exercise:**
- Run `claude install` if you previously installed via npm
- Try Ctrl+G to open an external editor from within Claude Code
- Customize your spinner verbs in settings

#### Maintaining Your Claude Code Environment
- The `~/.claude` directory stores session data, memories, and settings. It can grow to 1GB+ after a few weeks of daily use.
- There is no built-in auto-cleanup — periodically review and prune old session data.
- Key space consumers: session transcripts, tool outputs, and cached context.

#### Token Optimization: Reducing Context Noise

- **The problem:** Claude Code sends raw terminal output (passing tests, verbose logs, status bars) into the LLM context window — most of it is noise you're paying tokens for
- **Impact:** Unoptimized sessions can use 10x+ more tokens than necessary
- **Strategies:**
  1. **Keep commands focused:** Use targeted commands (`grep`, `head`, `tail`) instead of dumping entire files or logs
  2. **Filter test output:** Run specific test files/cases instead of full suites when debugging
  3. **Use `.claudeignore`:** Exclude build artifacts, node_modules, and generated files from context
  4. **Leverage subagents:** Claude Code's Task tool offloads exploration to subagents, keeping the main context clean
  5. **Community tools:** Projects like CLI proxies (e.g., rtk) can filter terminal output before it reaches context

**Exercise:** Run a Claude Code session on a project. Check token usage with `/cost`. Then repeat the same task using focused commands and `.claudeignore` — compare the token difference.

**Discussion:** [Community thread on token savings](https://www.reddit.com/r/ClaudeAI/comments/1r2tt7q/i_saved_10m_tokens_89_on_my_claude_code_sessions/)

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

#### Git Workflow Updates (Feb 2026)
- **`--from-pr` flag** added to resume sessions linked to a specific GitHub PR number (v2.1.27)
- **Debug logs** now include tool call failures and denials (v2.1.27)
- **Community tip — Token optimization:** The `rtk` (Rust Token Killer) CLI proxy can sit between Claude Code and terminal commands, filtering noise from raw command output before it reaches the LLM context (reported 89% token savings)
- **Community tip — Cleaner PR reviews:** When using `claude-code-action` in GitHub workflows, configure it to reduce comment noise and clean up old comments

**Exercise:**
- Try `claude --from-pr 42` to resume a session tied to a specific PR
- Explore token-saving strategies for long-running sessions

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

| Model | Released | Model ID | Best For |
|-------|----------|----------|----------|
| **Claude Opus 4.6** | Feb 2026 | `claude-opus-4-6` | Agentic coding, complex tool use, multi-step reasoning |
| **Claude Sonnet 4.5** | Sep 2025 | `claude-sonnet-4-5-20250929` | Everyday coding, balanced speed/capability |
| **Claude Haiku 4.5** | Oct 2025 | `claude-haiku-4-5-20251001` | Quick tasks, high-volume operations, cost-sensitive workflows |

- **Opus 4.6** leads across agentic coding, computer use, tool use, search, and finance benchmarks. Available in Claude Code since v2.1.32; fast mode enabled in v2.1.36.
- **Sonnet 4.5** sets benchmark records in coding, reasoning, and computer use. The default workhorse model. Released alongside the **Claude Agent SDK** for building custom agents programmatically.
- **Haiku 4.5** matches prior state-of-the-art coding with unprecedented speed and cost-efficiency. Used internally by Claude Code for fast subagent operations.

**Key takeaway:** Switch models mid-session with `/model` or set `ANTHROPIC_MODEL`. Use Opus 4.6 for complex architecture, Sonnet 4.5 for everyday coding, Haiku 4.5 for rapid iteration. Fast mode (`/fast`) is available for Opus 4.6.

**Exercise:** Run the same prompt with all three models and compare response time, token cost, and output quality. Identify which tasks are "Haiku-appropriate" vs those that need Sonnet or Opus.

**References:**
- [Opus 4.6](https://www.anthropic.com/news/claude-opus-4-6) | [Sonnet 4.5](https://www.anthropic.com/news/claude-sonnet-4-5) | [Haiku 4.5](https://www.anthropic.com/news/claude-haiku-4-5)
- [Agent SDK docs](https://docs.anthropic.com/en/docs/agents/agent-sdk)

#### Claude Code Feature Updates (Feb 2026)

**Task Management System:**
A new task management system with dependency tracking was added (v2.1.16). Tasks can be created, updated, and tracked with `blockedBy`/`blocks` relationships. Disable with `CLAUDE_CODE_ENABLE_TASKS=false` to use the old system temporarily.

**Auto Memory:**
Claude now automatically records and recalls memories as it works (v2.1.32). Memories persist in `~/.claude/` and are loaded into the system prompt for future sessions.

**Session Resume:**
On exit, Claude Code now shows a session resume hint so you can continue your conversation later (v2.1.31).

**Exercise:**
- Toggle `/fast` mode and compare response speed vs. quality
- Let Claude build up auto memories across a few sessions, then review what it stored in `~/.claude/`
- Use the task management system on a multi-step project to track progress

#### Community Tools: ClaudeDesk

- **ClaudeDesk v4.4.0** — An open-source Electron desktop app wrapping the Claude Code CLI. Provides multi-session terminals, split views, and agent team visualization.
- Features: full git workflow (status, staging, commits) without leaving the app, 233+ automated tests.
- Useful as a GUI alternative when you prefer a desktop interface over the raw terminal.
- **Reference:** https://github.com/anthropics/claudedesk

#### Token Usage Awareness

- **Opus 4.6 uses more tokens** than previous models due to deeper planning and longer autonomous runs. Monitor your usage with `/cost` during sessions.
- Community reports suggest token consumption can spike significantly when using Opus 4.6 for design-heavy or test-heavy workflows.
- **Tip:** Use Sonnet 4.5 or Haiku 4.5 for routine tasks, and reserve Opus 4.6 for complex architecture and multi-step reasoning where quality matters most.

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

#### Cowork: Claude Code for Desktop
- **Cowork** brings Claude Code's agentic capabilities to the Claude desktop app. Give Claude access to a folder, set a task, and let it work — it loops you in along the way.
- Useful when you want Claude Code-style workflows without opening a terminal.
- Try it at [claude.com/download](https://claude.com/download).

#### Shell & Input Fixes (Feb 2026)

- **Shell completion cache** files no longer get truncated on exit (v2.1.21)
- **Full-width (zenkaku) input** from Japanese IME now works correctly in option selection prompts (v2.1.21, v2.1.31)
- **Tab key** fixed to properly autocomplete instead of queueing slash commands (v2.1.38)

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

#### Authentication & Dashboard Updates (Feb 2026)
- **PDF page-range reading:** The Read tool now accepts a `pages` parameter for PDFs (e.g., `pages: "1-5"`). Large PDFs (>10 pages) return a lightweight reference when `@` mentioned instead of being inlined into context (v2.1.30)
- **Task management in VS Code:** Native plugin management support added, plus OAuth users can browse and resume remote Claude sessions from the Sessions dialog (v2.1.16)

**Exercise:**
- Use `@` to reference a large PDF in a Claude Code session and observe how it handles pagination
- Try resuming a remote session from VS Code's Sessions dialog

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

- **Claude Developer Platform** ([platform.claude.com](https://platform.claude.com/)) — Centralized hub for managing API keys, usage, billing, and project configuration.
  - API key management and rotation
  - Usage dashboards and token consumption tracking
  - Project and organization settings
  - Model access configuration
- **Claude Code on the Web** ([claude.ai/code](https://claude.ai/code)) — Browser-based access to Claude Code. Complements the CLI workflow for quick tasks or when terminal access isn't available.

**Exercise:** Visit the Claude Developer Platform and explore the usage dashboard. Review your API key setup and ensure your Claude Code CLI is authenticated correctly. Identify how token usage maps to the sessions you've run.

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

#### Skills, Hooks & Commands Updates (Feb 2026)
- **Custom command argument shorthand:** Use `$0`, `$1`, etc. to access individual arguments in custom commands (v2.1.19)
- **`CLAUDE_CODE_ENABLE_TASKS` env var:** Set to `false` to revert to the old task system temporarily (v2.1.19)
- **`TeammateIdle` and `TaskCompleted` hook events** added for multi-agent workflows (v2.1.33)
- **Customizable `spinnerVerbs`** setting for personalizing the activity spinner (v2.1.23)
- **Bash permission matching** fixed for commands using environment variable wrappers (v2.1.38)
- **Sandbox bypass fix:** Commands excluded from sandboxing via `sandbox.excludedCommands` or `dangerouslyDisableSandbox` no longer bypass the Bash ask permission rule when `autoAllowBashIfSandboxed` is enabled (v2.1.34)

**Exercise:**
- Create a custom command that uses `$0` and `$1` argument shorthand
- Set up a hook that responds to `TeammateIdle` or `TaskCompleted` events
- Configure `spinnerVerbs` in your settings to customize the spinner

#### Non-Interactive Mode & CI Automation

- **Structured outputs** in non-interactive (`-p`) mode are now fully supported (v2.1.22). Use `-p` with `--output-format json` to get structured responses for scripts and CI pipelines.
- **Startup performance** improved when resuming sessions with `saved_hook_context` (v2.1.29).
- **Gateway compatibility:** Users on Bedrock or Vertex can set `CLAUDE_CODE_DISABLE_EXPERIMENTAL_BETAS=1` to avoid beta header validation errors (v2.1.25, v2.1.27).

**Exercise:**
- Run `claude -p "list all files" --output-format json` and parse the structured output in a bash script
- Set up a CI step that uses Claude Code in non-interactive mode

#### Auto Memory (Feb 2026)

As of v2.1.32, Claude Code **automatically records and recalls memories** as it works. This is a significant change to how context persists across sessions.

**How it works:**
- Claude maintains a persistent memory directory at `~/.claude/projects/<project>/memory/`
- `MEMORY.md` is loaded into the system prompt each session (keep it under 200 lines)
- Separate topic files (e.g., `debugging.md`, `patterns.md`) can hold detailed notes
- Memories persist across conversations automatically

**What Claude saves:**
- Stable patterns confirmed across multiple interactions
- Key architectural decisions and important file paths
- User preferences for workflow and tools
- Solutions to recurring problems

**What Claude does NOT save:**
- Session-specific or temporary state
- Unverified conclusions from a single file read
- Anything duplicating CLAUDE.md instructions

**Exercise:** After a few sessions on a project, inspect `~/.claude/projects/` to see what Claude has remembered. Try asking Claude to "remember" a preference (e.g., "always use bun instead of npm") and verify it persists in the next session.

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

#### MCP Updates (Feb 2026)
- **Pre-configured OAuth MCP connectors** added, simplifying authentication setup for MCP servers (v2.1.30)
- **Restricted tool access:** Support added for restricting which MCP tools are available to specific contexts (v2.1.33)
- **npm deprecation:** Claude Code installation via npm is deprecated — use `claude install` or see the getting started docs (v2.1.15)
- **React Compiler** now used for UI rendering performance improvements (v2.1.15)

**Exercise:**
- Set up an OAuth-based MCP connector and test authenticated access
- Experiment with restricting MCP tool availability per-project

#### MCP Origins & Design Philosophy

- **Background:** MCP was created by Anthropic and donated as an open standard for connecting AI to external tools and services
- **Core idea:** A universal protocol so AI models can discover and use tools without bespoke integrations per service
- **Why it matters for Claude Code:** MCP is the backbone of Claude Code's plugin/server ecosystem — understanding its design philosophy helps you build better integrations
- **Key design principles:**
  - Tool discovery over hardcoded integrations
  - Server-side tool definitions with client-side execution
  - Transport-agnostic (stdio, HTTP/SSE)
  - Open standard — not locked to Anthropic

**Watch:** [Why we built and donated MCP — David Soria Parra](https://www.youtube.com/watch?v=kQRu7DdTTVA)

**Exercise:** After watching the video, write a short summary of why Anthropic chose to open-source MCP rather than keep it proprietary. How does this decision affect the Claude Code ecosystem?

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
- Allows developers to build custom agents with tool use, define agent workflows, and integrate Claude as an autonomous agent into existing applications.
- Relevant to agent teams and parallel session workflows covered this week.
- **References:** [Announcement](https://www.anthropic.com/news/claude-sonnet-4-5) | [Agent SDK docs](https://docs.anthropic.com/en/docs/agents/agent-sdk)

#### Agent Teams Updates (Feb 2026)
- **Agent teams research preview** launched — multi-agent collaboration feature requiring `CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1` (v2.1.32). Note: this is token-intensive.
- **tmux integration** fixed for agent teammate sessions to properly send and receive messages (v2.1.33)
- **`TeammateIdle` and `TaskCompleted` hook events** added for orchestrating multi-agent workflows (v2.1.33)
- **Agent teams crash fix** when settings change between renders (v2.1.34)
- **Sandbox security fix** preventing excluded commands from bypassing Bash ask permission rules (v2.1.34)

**Exercise:**
- Enable agent teams with `CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1` and try a multi-agent task
- Set up a `TeammateIdle` hook to monitor agent collaboration
- Test agent teams in a tmux session

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

### Appendix E: Real-World Workflows — Claude + Obsidian

Claude Code works exceptionally well with markdown-based knowledge systems like Obsidian. This pattern extends beyond engineering into product management, documentation, and knowledge work.

#### The Pattern
1. **Knowledge lives in `.md` files** — PRDs, specs, meeting notes, decision logs stored in an Obsidian vault
2. **Claude Code operates on the vault** — Point Claude Code at your Obsidian folder to query, summarize, update, and cross-reference documents
3. **Bidirectional workflow** — Edit in Obsidian for thinking, delegate to Claude Code for synthesis and automation

#### Use Cases
- Summarize a week's meeting notes into action items
- Cross-reference PRDs against technical specs for consistency
- Generate status reports from scattered notes
- Draft RFC documents from rough bullet points

**Discussion:** [Community thread on Claude + Obsidian workflows](https://www.reddit.com/r/ClaudeAI/comments/1r2puy0/product_managers_using_claude_obsidian_what_does/)

### Appendix F: Maintaining Your ~/.claude Directory

The `~/.claude` directory stores session data, conversation history, memories, and configuration. Without periodic cleanup, it can grow to 1GB+ within weeks of daily use.

#### What takes up space
| Directory | Contents |
|-----------|----------|
| `projects/` | Per-project session data and memory files |
| `sessions/` | Full conversation transcripts |
| `memory/` | Auto-memory files persisted across sessions |

#### Cleanup strategies
1. **Manual cleanup:** Remove old session directories older than 30 days
   ```bash
   find ~/.claude/sessions -type d -mtime +30 -exec rm -rf {} +
   ```
2. **Check your usage:** `du -sh ~/.claude/*/  | sort -rh`
3. **Preserve what matters:** Back up your `memory/` and `CLAUDE.md` files before cleaning
4. **Automate it:** Add a cleanup cron job or shell alias for periodic maintenance

**Tip:** Session data accumulates fastest — if you run many long sessions daily, check monthly.

**Discussion:** [Community thread on ~/.claude cleanup](https://www.reddit.com/r/ClaudeAI/comments/1r2snly/cleanup_script_for_claude_mine_grew_to_13gb_in_4/)

---

*Curriculum Version: 2.0 — February 2026*
*Model: Claude Opus 4.6*
*Last Updated: 2026-02-12*
