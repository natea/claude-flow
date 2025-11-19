# Claude Flow Quick Reference Guide

## Installation

```bash
# Install latest alpha
npx claude-flow@alpha --version

# Initialize project
npx claude-flow@alpha init

# Add MCP server
claude mcp add claude-flow npx claude-flow@alpha mcp start
```

## Essential Commands

### Swarm Operations
```bash
# Deploy swarm
npx claude-flow@alpha swarm "task description"

# With Claude Code
npx claude-flow@alpha swarm "task" --claude

# With memory
npx claude-flow@alpha swarm "task" --memory

# Multi-repository
npx claude-flow@alpha swarm "task" --multi-repo
```

### Hive Mind
```bash
# Interactive wizard
npx claude-flow@alpha hive-mind wizard

# Initialize
npx claude-flow@alpha hive-mind init

# Spawn intelligent swarm
npx claude-flow@alpha hive-mind spawn "objective"

# Status
npx claude-flow@alpha hive-mind status

# Metrics
npx claude-flow@alpha hive-mind metrics
```

### SPARC Modes
```bash
# List modes
npx claude-flow@alpha sparc modes

# Run specific mode
npx claude-flow@alpha sparc run <mode> "task"

# TDD workflow
npx claude-flow@alpha sparc tdd "feature"

# Documentation
npx claude-flow@alpha sparc run docs "topic"

# Architecture
npx claude-flow@alpha sparc run architect "design"

# Code review
npx claude-flow@alpha sparc run review "code"
```

### Agent Management
```bash
# Agent Booster - fast editing
npx claude-flow@alpha agent booster edit <file>
npx claude-flow@alpha agent booster batch "pattern"
npx claude-flow@alpha agent booster benchmark

# Memory (ReasoningBank)
npx claude-flow@alpha agent memory init
npx claude-flow@alpha agent memory status
npx claude-flow@alpha agent memory list
```

### GitHub Integration
```bash
# Analyze repository
npx claude-flow@alpha github analyze

# PR management
npx claude-flow@alpha github pr-review

# Issue triage
npx claude-flow@alpha github issue-triage

# Release workflow
npx claude-flow@alpha github release

# Multi-repo sync
npx claude-flow@alpha github multi-repo-sync
```

### Hooks
```bash
# Pre-task
npx claude-flow@alpha hooks pre-task --description "task"

# Post-edit
npx claude-flow@alpha hooks post-edit --file "path"

# Session management
npx claude-flow@alpha hooks session-restore --session-id "id"
npx claude-flow@alpha hooks session-end --export-metrics true

# Post-task
npx claude-flow@alpha hooks post-task --task-id "id"
```

### Monitoring & Analysis
```bash
# System status
npx claude-flow@alpha status

# Performance analysis
npx claude-flow@alpha analysis performance

# Token usage
npx claude-flow@alpha monitoring tokens

# Bottleneck detection
npx claude-flow@alpha optimization analyze
```

### Cost Optimization
```bash
# OpenRouter proxy
npx claude-flow@alpha proxy start
npx claude-flow@alpha proxy status
npx claude-flow@alpha proxy config
```

### Verification
```bash
# Truth verification
npx claude-flow@alpha verify code

# View scores
npx claude-flow@alpha truth

# Pair programming
npx claude-flow@alpha pair --start
```

### Training
```bash
# Neural training
npx claude-flow@alpha training start
npx claude-flow@alpha training status
npx claude-flow@alpha training patterns
```

## Agent Types

### Core Development
- `coder` - Code implementation
- `reviewer` - Code review
- `tester` - Testing & QA
- `planner` - Task planning
- `researcher` - Research & analysis

### Specialized
- `backend-dev` - Backend development
- `mobile-dev` - Mobile development
- `ml-developer` - ML development
- `system-architect` - Architecture design
- `cicd-engineer` - CI/CD pipelines
- `api-docs` - API documentation

### GitHub
- `github-modes` - Workflow automation
- `pr-manager` - PR management
- `code-review-swarm` - Code review
- `issue-tracker` - Issue tracking
- `release-manager` - Release management

### Swarm Coordination
- `hierarchical-coordinator` - Hierarchical swarms
- `mesh-coordinator` - Mesh networks
- `adaptive-coordinator` - Adaptive topology
- `swarm-memory-manager` - Memory management

## SPARC Modes

1. `sparc` - SPARC Orchestrator
2. `code` - Code Implementation
3. `tdd` - Test-Driven Development
4. `architect` - System Architect
5. `debug` - Debug & Troubleshoot
6. `docs` - Documentation Writer
7. `review` - Code Reviewer
8. `refactor` - Refactoring Specialist
9. `integration` - Integration Specialist
10. `devops` - DevOps Engineer
11. `security` - Security Analyst
12. `optimize` - Performance Optimizer
13. `ask` - Requirements Analyst

## Common Patterns

### Full-Stack Development
```bash
# 1. Specification
npx claude-flow@alpha sparc run ask "user requirement"

# 2. Architecture
npx claude-flow@alpha sparc run architect "design"

# 3. Implementation
npx claude-flow@alpha swarm "build feature" --claude

# 4. Testing
npm test
```

### Code Quality
```bash
# Analyze
npx claude-flow@alpha swarm "analyze codebase"

# Fix with Agent Booster
npx claude-flow@alpha agent booster batch "src/**/*.ts"

# Review
npx claude-flow@alpha sparc run review "full review"
```

### Performance Optimization
```bash
# Analyze
npx claude-flow@alpha sparc run optimize "identify bottlenecks"

# Optimize
npx claude-flow@alpha swarm "optimize performance"

# Benchmark
npx claude-flow@alpha agent booster benchmark
```

## Troubleshooting

### Clear Cache
```bash
npm cache clean --force
```

### Reset MCP
```bash
claude mcp remove claude-flow
claude mcp add claude-flow npx claude-flow@alpha mcp start
```

### Reset Memory
```bash
npx claude-flow@alpha agent memory init --reset
```

### Debug Mode
```bash
npx claude-flow@alpha --verbose <command>
```

## Resources

- **Main Tutorial**: `/docs/tutorials/getting-started-with-claude-flow.md`
- **GitHub**: https://github.com/ruvnet/claude-flow
- **Discord**: https://discord.agentics.org
- **Issues**: https://github.com/ruvnet/claude-flow/issues
