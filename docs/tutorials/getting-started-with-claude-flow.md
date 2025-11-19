# Getting Started with Claude Flow

## Table of Contents
1. [Introduction](#introduction)
2. [Installation](#installation)
3. [Core Concepts](#core-concepts)
4. [Quick Start](#quick-start)
5. [Common Workflows](#common-workflows)
6. [Advanced Features](#advanced-features)
7. [Best Practices](#best-practices)
8. [Troubleshooting](#troubleshooting)

## Introduction

Claude Flow is an enterprise-grade AI agent orchestration platform that enables multi-agent coordination, intelligent workflow automation, and advanced development capabilities. Version 2.7+ integrates with Claude Code SDK and provides 90+ MCP tools for maximum performance.

### Key Benefits
- **84.8% SWE-Bench solve rate** - Industry-leading code generation accuracy
- **32.3% token reduction** - Optimized resource usage
- **2.8-4.4x speed improvement** - Parallel execution and smart coordination
- **27+ neural models** - Advanced learning and pattern recognition

### What You'll Learn
This tutorial will guide you through:
- Setting up Claude Flow in your project
- Understanding swarms, agents, and coordination
- Running your first multi-agent workflow
- Leveraging advanced features like Hive Mind and ReasoningBank
- Best practices for production use

## Installation

### Prerequisites
- Node.js 18+ (recommended: latest LTS)
- npm or npx
- Git (for GitHub integration features)
- Claude Code CLI (optional, for enhanced integration)

### Quick Install

```bash
# Install and verify latest alpha version
npx claude-flow@alpha --version

# Initialize in your project
npx claude-flow@alpha init

# Or install globally
npm install -g claude-flow@alpha
```

### MCP Server Setup (Optional but Recommended)

Add Claude Flow as an MCP server to Claude Code for enhanced capabilities:

```bash
# Add Claude Flow MCP server
claude mcp add claude-flow npx claude-flow@alpha mcp start

# Optional: Add ruv-swarm for enhanced coordination
claude mcp add ruv-swarm npx ruv-swarm mcp start

# Optional: Add Flow Nexus for cloud features
claude mcp add flow-nexus npx flow-nexus@latest mcp start
```

### Verify Installation

```bash
# Check version
npx claude-flow@alpha --version

# View available commands
npx claude-flow@alpha --help

# Check system status
npx claude-flow@alpha status
```

## Core Concepts

### 1. Agents

Agents are specialized AI workers that handle specific tasks. Claude Flow provides 54+ pre-built agent types:

**Core Development Agents:**
- `coder` - Implementation specialist for writing clean code
- `reviewer` - Code review and quality assurance
- `tester` - Comprehensive testing and QA
- `planner` - Strategic planning and task orchestration
- `researcher` - Deep research and information gathering

**Specialized Agents:**
- `backend-dev` - Backend API development
- `mobile-dev` - React Native mobile development
- `ml-developer` - Machine learning model development
- `system-architect` - System architecture design
- `cicd-engineer` - CI/CD pipeline creation

**GitHub Agents:**
- `github-modes` - GitHub workflow automation
- `pr-manager` - Pull request management
- `code-review-swarm` - Multi-agent code review
- `issue-tracker` - Issue management
- `release-manager` - Release coordination

### 2. Swarms

Swarms are coordinated groups of agents working together on complex tasks. They enable:

- **Parallel Execution** - Multiple agents work simultaneously
- **Intelligent Coordination** - Agents share context and results
- **Fault Tolerance** - Self-healing workflows
- **Dynamic Scaling** - Agents spawn as needed

**Swarm Topologies:**
- **Hierarchical** - Queen-led coordination with specialized workers
- **Mesh** - Peer-to-peer distributed coordination
- **Adaptive** - Dynamic topology switching based on task requirements

### 3. SPARC Methodology

SPARC is a systematic development methodology built into Claude Flow:

- **S**pecification - Requirements analysis
- **P**seudocode - Algorithm design
- **A**rchitecture - System design
- **R**efinement - TDD implementation
- **C**ompletion - Integration and deployment

```bash
# Available SPARC modes
npx claude-flow@alpha sparc modes

# Run specific mode
npx claude-flow@alpha sparc run docs "Create API documentation"
npx claude-flow@alpha sparc run tdd "Implement user authentication"
npx claude-flow@alpha sparc run architect "Design microservices architecture"
```

### 4. Memory Systems

**ReasoningBank** - Persistent learning memory that enables:
- 46% faster task execution through pattern learning
- 88% success rate improvement
- Cross-session context retention
- Pattern recognition and optimization

```bash
# Initialize ReasoningBank
npx claude-flow@alpha agent memory init

# View memory statistics
npx claude-flow@alpha agent memory status

# List stored memories
npx claude-flow@alpha agent memory list
```

### 5. Hooks System

Hooks enable automation and integration at key lifecycle points:

**Pre-Operation Hooks:**
- Auto-assign agents by file type
- Validate commands for safety
- Prepare resources automatically
- Optimize topology by complexity

**Post-Operation Hooks:**
- Auto-format code
- Train neural patterns
- Update memory
- Analyze performance
- Track token usage

**Session Management:**
- Generate summaries
- Persist state
- Track metrics
- Restore context

```bash
# Common hook commands
npx claude-flow@alpha hooks pre-task --description "Build REST API"
npx claude-flow@alpha hooks post-edit --file "src/api.ts"
npx claude-flow@alpha hooks session-restore --session-id "swarm-123"
npx claude-flow@alpha hooks post-task --task-id "task-456"
```

## Quick Start

### Example 1: Simple Swarm for Code Review

```bash
# Deploy a code review swarm
npx claude-flow@alpha swarm "Review all TypeScript files in src/ for security vulnerabilities and performance issues"
```

This command will:
1. Initialize a swarm with appropriate topology
2. Spawn specialized agents (security analyst, performance optimizer, code reviewer)
3. Distribute work across agents
4. Coordinate results
5. Generate comprehensive report

### Example 2: TDD Workflow with SPARC

```bash
# Run complete TDD workflow for a feature
npx claude-flow@alpha sparc tdd "Implement user authentication with JWT tokens"
```

This will guide you through:
1. **Specification** - Analyze requirements
2. **Pseudocode** - Design algorithm
3. **Architecture** - Plan system structure
4. **Refinement** - Write tests, then implementation
5. **Completion** - Integration and verification

### Example 3: Hive Mind Interactive Setup

```bash
# Launch interactive setup wizard (recommended for first-time users)
npx claude-flow@alpha hive-mind wizard

# Or spawn a Hive Mind swarm directly
npx claude-flow@alpha hive-mind spawn "Build a REST API with Express, PostgreSQL, and comprehensive testing"
```

Hive Mind provides:
- Queen-led hierarchical coordination
- Persistent memory across sessions
- Consensus mechanisms
- Self-organizing workflows

### Example 4: GitHub Integration

```bash
# Analyze repository and generate improvement recommendations
npx claude-flow@alpha github analyze

# Automate PR review workflow
npx claude-flow@alpha github pr-review

# Create release workflow
npx claude-flow@alpha github release
```

## Common Workflows

### Workflow 1: Full-Stack Feature Development

```bash
# Step 1: Initialize project with Claude Flow
npx claude-flow@alpha init

# Step 2: Create specification
npx claude-flow@alpha sparc run ask "User wants to add social login (Google, GitHub) to existing authentication system"

# Step 3: Design architecture
npx claude-flow@alpha sparc run architect "Design OAuth2 integration architecture"

# Step 4: Deploy development swarm
npx claude-flow@alpha swarm "Implement social login with Google and GitHub OAuth2, including backend API, frontend UI, and comprehensive tests" --claude

# Step 5: Run tests and validation
npm test
```

### Workflow 2: Code Quality Improvement

```bash
# Initialize swarm for code analysis
npx claude-flow@alpha swarm "Analyze entire codebase for code smells, security vulnerabilities, performance bottlenecks, and technical debt. Provide prioritized recommendations."

# Apply automated fixes
npx claude-flow@alpha agent booster batch "src/**/*.ts" --fix

# Run comprehensive code review
npx claude-flow@alpha sparc run review "Full codebase review focusing on maintainability and best practices"
```

### Workflow 3: Multi-Repository Coordination

```bash
# Synchronize changes across multiple repositories
npx claude-flow@alpha github multi-repo-sync

# Deploy coordinated feature across repos
npx claude-flow@alpha swarm "Add authentication middleware to API repo, update SDK repo with new auth methods, and update documentation repo" --multi-repo
```

### Workflow 4: Performance Optimization

```bash
# Run performance analysis
npx claude-flow@alpha sparc run optimize "Identify and fix performance bottlenecks in application"

# Deploy optimization swarm
npx claude-flow@alpha swarm "Optimize database queries, implement caching strategies, and reduce bundle size. Target: 50% improvement in load time"

# Benchmark results
npx claude-flow@alpha agent booster benchmark
```

## Advanced Features

### 1. Hive Mind - Intelligent Swarm Coordination

Hive Mind is a hierarchical multi-agent system with persistent memory and consensus mechanisms.

**Key Features:**
- Queen-led coordination
- Worker specialization
- Collective decision-making
- Cross-session memory
- Self-healing workflows

**Usage:**

```bash
# Interactive wizard (recommended)
npx claude-flow@alpha hive-mind wizard

# Initialize Hive Mind system
npx claude-flow@alpha hive-mind init

# Spawn intelligent swarm
npx claude-flow@alpha hive-mind spawn "Build complete e-commerce platform with shopping cart, payments, and admin dashboard"

# View swarm status
npx claude-flow@alpha hive-mind status

# Advanced metrics
npx claude-flow@alpha hive-mind metrics
```

**Architecture:**
- **Queen Agent** - Strategic orchestration and decision-making
- **Scout Agents** - Information gathering and reconnaissance
- **Worker Agents** - Specialized task execution
- **Memory Manager** - Persistent context and learning
- **Consensus Coordinator** - Distributed decision-making

### 2. ReasoningBank - Adaptive Learning Memory

ReasoningBank provides persistent memory with pattern learning and experience replay.

**Benefits:**
- 46% faster task completion
- 88% success rate
- Pattern recognition
- Cross-session learning

**Usage:**

```bash
# Initialize ReasoningBank
npx claude-flow@alpha agent memory init

# Check memory status
npx claude-flow@alpha agent memory status

# List stored patterns
npx claude-flow@alpha agent memory list

# Use with swarm
npx claude-flow@alpha swarm "Build API" --memory
```

**How It Works:**
1. **Trajectory Tracking** - Records successful task executions
2. **Verdict Judgment** - Evaluates outcomes and patterns
3. **Memory Distillation** - Extracts reusable patterns
4. **Pattern Recognition** - Applies learned patterns to new tasks

### 3. Agent Booster - Ultra-Fast Code Editing

Agent Booster provides 352x faster code editing with zero API cost.

**Features:**
- Local WASM processing
- Batch editing (1000 files in 1 second)
- Zero API costs
- Pattern-based transformations

**Usage:**

```bash
# Edit single file
npx claude-flow@alpha agent booster edit src/api.ts

# Batch edit multiple files
npx claude-flow@alpha agent booster batch "src/**/*.ts"

# Benchmark (validate 352x speed claim)
npx claude-flow@alpha agent booster benchmark
```

**Use Cases:**
- Bulk refactoring
- Code migrations
- Style updates
- Dependency updates

### 4. OpenRouter Proxy - Cost Optimization

Save 85-98% on API costs with intelligent model routing.

**Features:**
- Automatic model selection
- Cost optimization
- Fallback handling
- Usage analytics

**Usage:**

```bash
# Start proxy server
npx claude-flow@alpha proxy start

# Check status
npx claude-flow@alpha proxy status

# Configuration guide
npx claude-flow@alpha proxy config
```

### 5. Truth Verification System

Ensure high-quality outputs with automated verification.

**Features:**
- 0.95 accuracy threshold
- Automatic rollback
- Quality scoring
- Reliability metrics

**Usage:**

```bash
# Verify code quality
npx claude-flow@alpha verify code

# View truth scores
npx claude-flow@alpha truth

# Pair programming with verification
npx claude-flow@alpha pair --start
```

### 6. Neural Training

Train custom neural patterns for your specific workflows.

**Usage:**

```bash
# Train from successful workflows
npx claude-flow@alpha training start

# View training status
npx claude-flow@alpha training status

# List trained patterns
npx claude-flow@alpha training patterns
```

### 7. Flow Nexus Cloud Platform (Optional)

Access distributed sandboxes, neural networks, and cloud orchestration.

**Setup:**

```bash
# Register account
npx flow-nexus@latest register

# Login
npx flow-nexus@latest login

# Create cloud sandbox
npx flow-nexus@latest sandbox create

# Deploy neural network
npx flow-nexus@latest neural deploy
```

**Features:**
- 70+ specialized MCP tools
- Distributed execution
- Cloud storage
- Real-time monitoring

## Best Practices

### 1. Concurrent Execution

**Always batch operations in single messages:**

```bash
# ✅ CORRECT: All operations in one command
npx claude-flow@alpha swarm "Task 1" && \
npx claude-flow@alpha swarm "Task 2" && \
npx claude-flow@alpha swarm "Task 3"

# ❌ WRONG: Sequential separate commands
npx claude-flow@alpha swarm "Task 1"
# wait...
npx claude-flow@alpha swarm "Task 2"
# wait...
```

### 2. File Organization

**Never save working files to root:**

```bash
# ✅ CORRECT: Organized subdirectories
/src        # Source code
/tests      # Test files
/docs       # Documentation
/config     # Configuration
/scripts    # Utility scripts
/examples   # Example code

# ❌ WRONG: Files in root
/temp.ts
/test.md
/notes.txt
```

### 3. Memory Usage

**Leverage ReasoningBank for better performance:**

```bash
# Initialize memory at project start
npx claude-flow@alpha agent memory init

# Use --memory flag for swarms
npx claude-flow@alpha swarm "Build feature" --memory

# Regularly review learned patterns
npx claude-flow@alpha agent memory list
```

### 4. Hooks Integration

**Enable hooks for automation:**

```bash
# Pre-task validation
npx claude-flow@alpha hooks pre-task --description "Deploy API"

# Post-edit formatting
npx claude-flow@alpha hooks post-edit --file "src/api.ts"

# Session management
npx claude-flow@alpha hooks session-restore --session-id "session-123"
```

### 5. Cost Optimization

**Use appropriate tools for the task:**

```bash
# Use Agent Booster for bulk edits (zero cost)
npx claude-flow@alpha agent booster batch "src/**/*.ts"

# Use OpenRouter proxy for API calls (85-98% savings)
npx claude-flow@alpha proxy start

# Use Haiku model for simple tasks
npx claude-flow@alpha swarm "Simple task" --model haiku
```

### 6. GitHub Integration

**Integrate early for better coordination:**

```bash
# Initialize GitHub integration at project start
npx claude-flow@alpha github init

# Automate PR workflows
npx claude-flow@alpha github pr-review

# Use issue tracking
npx claude-flow@alpha github issue-triage
```

### 7. Testing Strategy

**Always use TDD with SPARC:**

```bash
# Run TDD workflow
npx claude-flow@alpha sparc tdd "Feature description"

# Verify with tests
npm test

# Use tester agent for comprehensive coverage
npx claude-flow@alpha swarm "Create comprehensive test suite with 90% coverage"
```

### 8. Monitoring and Metrics

**Track performance and optimize:**

```bash
# View system status
npx claude-flow@alpha status

# Monitor swarm performance
npx claude-flow@alpha hive-mind metrics

# Analyze bottlenecks
npx claude-flow@alpha analysis performance
```

## Troubleshooting

### Common Issues

#### 1. Installation Issues

```bash
# Clear npm cache
npm cache clean --force

# Reinstall
npm uninstall -g claude-flow
npm install -g claude-flow@alpha

# Verify
npx claude-flow@alpha --version
```

#### 2. Permission Errors

```bash
# Fix npm permissions
sudo chown -R $USER:$GROUP ~/.npm
sudo chown -R $USER:$GROUP ~/.config

# Or use npx (no global install)
npx claude-flow@alpha <command>
```

#### 3. MCP Server Connection

```bash
# Restart MCP server
claude mcp remove claude-flow
claude mcp add claude-flow npx claude-flow@alpha mcp start

# Check server status
claude mcp list
```

#### 4. Swarm Not Responding

```bash
# Check swarm status
npx claude-flow@alpha hive-mind status

# Restart with fresh session
npx claude-flow@alpha hive-mind spawn "Task" --force-new
```

#### 5. Memory Issues

```bash
# Reset ReasoningBank
npx claude-flow@alpha agent memory init --reset

# Clear old patterns
npx claude-flow@alpha agent memory clear
```

### Getting Help

- **Documentation**: https://github.com/ruvnet/claude-flow
- **Issues**: https://github.com/ruvnet/claude-flow/issues
- **Discord**: https://discord.agentics.org
- **Hive Mind Guide**: https://github.com/ruvnet/claude-flow/tree/main/docs/hive-mind

### Debug Mode

```bash
# Enable verbose logging
npx claude-flow@alpha --verbose swarm "Task"

# View detailed metrics
npx claude-flow@alpha status --detailed

# Export logs
npx claude-flow@alpha monitoring export
```

## Next Steps

Now that you understand Claude Flow basics:

1. **Experiment with SPARC modes** - Try different development workflows
2. **Deploy your first Hive Mind swarm** - Experience intelligent coordination
3. **Integrate with GitHub** - Automate your development workflows
4. **Enable ReasoningBank** - Benefit from adaptive learning
5. **Explore Flow Nexus** - Access cloud features and advanced orchestration

### Additional Resources

- **SPARC Methodology Guide**: `/docs/sparc-methodology.md`
- **Hive Mind Deep Dive**: `/docs/hive-mind/architecture.md`
- **Agent Reference**: `/docs/agents-reference.md`
- **API Documentation**: `/docs/api/README.md`
- **Integration Examples**: `/examples/`

---

**Welcome to Claude Flow!** 🌊

You're now equipped to build intelligent, coordinated AI workflows. Start with simple swarms, then gradually explore advanced features like Hive Mind and ReasoningBank as you become comfortable with the platform.

Happy orchestrating! 🚀
