# Qwen Multi Subagents Ready

This repository contains a set of specialized agent profiles designed to work with Qwen Code and similar AI coding assistants. These agents implement a structured development methodology based on the "Orchestrator Pattern" to coordinate multiple specialized agents in software engineering tasks.

## 🎭 Orchestration Architecture

The system uses a master orchestration pattern where a coordinator agent (Orchestrator) manages the execution of other specialized agents. Each agent has a specific role and clearly defined limits to ensure efficient and predictable collaboration.

### Included Specialized Agents

#### 🎯 `scope-rule-architect` - Scope Architect
**When to use**: When starting a new project or major feature
- Establishes the base project structure following the "Scope Rule"
- Defines where components should be placed based on their reuse
- Sets up the technology stack (React 19, TypeScript, Vitest)

#### ⚛️ `react-architect` - React Architect
**When to use**: To create/modify React components
- Makes complex architectural decisions about state patterns
- Optimizes performance of complex applications
- Implements components following React 19 best practices

#### 🗄️ `supabase-postgres-expert` - Supabase/PostgreSQL Expert
**When to use**: To design database schemas
- Creates tables and relationships with advanced data types
- Implements row-level security policies (RLS)
- Optimizes queries and designs strategic indexes

#### 🔌 `api-integration-expert` - API Integration Expert
**When to use**: To integrate external services
- Designs resilient integration patterns with error handling
- Implements retry mechanisms and circuit breakers
- Creates rate limiting and caching strategies

#### 🧪 `tdd-green-implementer` - TDD Implementer
**When to use**: After writing failing tests
- Implements the minimum code needed to pass tests
- Strictly follows the Container/Presentational pattern
- Focuses only on making tests pass (GREEN phase of TDD)

#### 🔒 `security-gatekeeper` - Security Gatekeeper
**When to use**: Before merging code to the main branch
- Performs thorough security audits
- Verifies OWASP Top 10 compliance
- Blocks merges with critical vulnerabilities

#### ♿ `web-accessibility-auditor` - Accessibility Auditor
**When to use**: After creating UI components
- Audits WCAG 2.1 AA compliance
- Verifies keyboard navigation and screen reader compatibility
- Provides specific accessibility corrections

#### 📝 `git-commit-expert` - Git Commit Expert
**When to use**: After completing each phase
- Creates commits with Conventional Commits format
- Writes professional PR descriptions
- Suggests appropriate semantic versioning

### 🔄 Orchestrated Workflow

#### 🚀 New Project from Scratch
1. **Phase 1: Setup**
   - `scope-rule-architect` creates the base structure
   - `react-architect` creates the minimal App component
   - `git-commit-expert` makes the initial commit

2. **Phase 2: First Feature**
   - `tdd-green-implementer` writes failing tests
   - `react-architect` creates the component
   - `web-accessibility-auditor` verifies accessibility
   - `git-commit-expert` commits the feature

3. **Phase 3: Database (if needed)**
   - `supabase-postgres-expert` creates tables
   - `api-integration-expert` implements connections
   - `security-gatekeeper` validates security
   - `git-commit-expert` commits DB changes

## 📁 Repository Structure

```
.claude/
├── agents/
│   ├── api-integration-expert.md
│   ├── git-commit-expert.md
│   ├── react-architect.md
│   ├── scope-rule-architect.md
│   ├── security-gatekeeper.md
│   ├── supabase-postgres-expert.md
│   ├── tdd-green-implementer.md
│   └── web-accessibility-auditor.md
└── CLAUDE.md
.agent-state.json
```

### Key Files

- **`.claude/agents/*.md`**: Detailed profiles of each specialized agent
- **`.claude/CLAUDE.md`**: Guide for Claude Code on how to coordinate agents
- **`.agent-state.json`**: Shared memory that maintains project state

## 🎯 Benefits of This Architecture

### For Developers
- **Responsibility Division**: Each agent has a clear and limited role
- **Consistency**: Standardized patterns and practices throughout the project
- **Guaranteed Quality**: Automatic security, accessibility, and testing reviews
- **Scalability**: Architecture that grows with the project

### For Teams
- **Structured Collaboration**: Predictable and documented workflow
- **Error Reduction**: Automated checks at each phase
- **Quick Onboarding**: New members quickly understand the flow
- **Maintainability**: Code organized according to scope principles

## 🚀 Getting Started

### Prerequisites

For prerequisites and setup instructions, please refer to the detailed guide at:
[https://github.com/rankgnar/qwen-subagents-claude](https://github.com/rankgnar/qwen-subagents-claude)

### Basic Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/rankgnar/qwen_multi_subagents_ready.git
   ```
2. Examine agent profiles in `.claude/agents/`
3. Copy profiles to your Qwen Code environment
4. Follow the orchestrated workflow for your project

### Usage Example
```markdown
User: "I want to start a new task management project"

Orchestrator:
1. Reading .agent-state.json... [new project]
2. Starting PHASE 1 - SETUP
3. Invoking @scope-rule-architect for base structure...
4. Structure created ✓
5. Invoking @react-architect for minimal App.jsx...
6. App.jsx created ✓
7. Updating .agent-state.json...
8. Can you run `npm start` and confirm you see "Hello World"?
```

## 🤝 Contributions

Contributions are welcome. You can:

1. **Add new agents** for other technologies or domains
2. **Improve existing profiles** with new capabilities
3. **Refine workflows** for specific use cases
4. **Create templates** for common project types

For major changes, please open an issue first to discuss what you would like to modify.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📞 Contact

For questions or feedback, feel free to open an issue on GitHub or contact me directly through my profile.

---
*"Collaboration between specialized agents produces results superior to the sum of their individual parts."*