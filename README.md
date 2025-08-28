# Agent Factory

A Claude Code sub-agent that specializes in creating new specialist sub-agents from brief descriptions. This factory generates complete, ready-to-use sub-agent configuration files with proper scoping, documentation, and research workflows.

## Overview

The Agent Factory is a **sub-agent architect & planner** that transforms user requirements into research-focused specialist sub-agents. It follows a structured framework to ensure each generated agent is properly scoped, well-documented, and optimized for token efficiency.

## Key Features

- **Automated Agent Generation**: Creates complete sub-agent configs from brief descriptions
- **Research-Only Focus**: All generated agents are scoped as researchers and planners only
- **Context Management**: Implements persistent documentation patterns to reduce token usage
- **Framework Compliance**: Ensures all agents follow Claude Code sub-agent standards
- **Documentation Integration**: Automatically creates supporting research artifacts

## How It Works

### Input
Provide a brief description of the specialist expertise needed:
```
"Use agent factory to create a Firebase expert for authentication and Firestore integration"
"Create a React Native specialist for mobile development using agent factory"
"Build a agent factory agent for Docker deployment"
```

### Output
The factory generates:
1. **Sub-agent config file**: `.claude/agents/<generated-agent-name>.md`
2. **Implementation plan**: `.claude/docs/<service>-<topic>-plan-<timestamp>.md`
3. **Context session**: `.claude/docs/context-session-<date>.md`

## Generated Agent Structure

Each generated agent includes:

### Frontmatter Configuration
- **Name**: Kebab-case naming (e.g., `firebase-expert`, `react-native-specialist`)
- **Description**: Action-oriented delegation guidance
- **Tools**: Minimal research-focused toolset
- **Model**: Optimized model selection

### System Prompt Sections
- **Research-Only Boundaries**: Clear scope limitations
- **Context Management Pattern**: File structure and workflows
- **Knowledge Areas**: Service-specific expertise domains
- **Procedure Checklist**: Step-by-step research methodology
- **Output Contract**: Standardized deliverable formats

## Agent Scoping Framework

The factory applies these design principles:

### ✅ Generated Agents Will:
- Research documentation & best practices
- Analyze repository integration points (read-only)
- Produce detailed implementation plans
- Create persistent documentation in `.claude/docs/`
- Optimize for token efficiency through context reuse

### ❌ Generated Agents Will NOT:
- Implement or execute code
- Modify runtime source files
- Make direct system changes
- Override the research-only boundary

## File Structure

Generated agents maintain this documentation pattern:

```
.claude/
├── agents/
│   └── <generated-agent-name>.md
└── docs/
    ├── context-session-[timestamp].md
    ├── [service]-[topic]-plan-[timestamp].md
    └── task/
        └── [specific-research-files].md
```

## Usage Examples

### Creating a Database Expert
```
Request: "Create a PostgreSQL expert for query optimization and schema design"

Output:
- .claude/agents/postgresql-expert.md
- .claude/docs/postgresql-optimization-plan-20250828-1430.md
- Updated context session with research findings
```

### Building an API Specialist
```
Request: "Need a REST API expert for authentication and rate limiting"

Output:
- .claude/agents/api-security-expert.md
- .claude/docs/api-auth-plan-20250828-1445.md
- Comprehensive research on auth patterns and rate limiting
```

## Quality Assurance

The factory includes built-in validation:

### Agent Prioritization Matrix
- **High Priority**: Complex, fast-changing, or central technologies
- **Medium Priority**: Stable technologies with specific integration needs
- **Low Priority**: Simple or well-documented technologies

### Implementation Checklist
- [ ] Define service scope
- [ ] List documentation sources
- [ ] Identify MCP tools/APIs
- [ ] Specify knowledge areas
- [ ] Set context workflow & files
- [ ] Enforce research-only boundary
- [ ] Test with sample research task
- [ ] Integrate into parent workflow

## Best Practices

### Token Optimization
- Reuses existing context from `.claude/docs/`
- Cites documentation versions to avoid re-fetching
- Maintains session history for incremental research

### Documentation Standards
- Consistent formatting across all generated plans
- Explicit risk and assumption documentation
- Implementation-ready guidance without actual code
- Proper linking and versioning of source materials

## Getting Started

1. **Invoke the Factory**: Describe the specialist expertise needed
2. **Review the Plan**: Start with the generated plan file in `.claude/docs/`
3. **Use the Agent**: Delegate tasks to the newly created specialist
4. **Iterate**: Refine based on usage patterns and feedback

## Technical Details

### Available Tools
- **Core**: Read, Write, Glob, Grep
- **Documentation**: WebFetch, context7 library tools
- **Multi-file Operations**: MultiEdit for complex configurations
