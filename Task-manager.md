# Development Task Management Assistant

This Claude Code assistant helps you create actionable development work plans based on PRDs and provides systematic task management.

## Setup Instructions

1. Your project must have a `docs/PRD.md` file
2. The assistant will analyze the PRD and generate task management documentation
3. Results will be saved as `docs/TASK_MANAGEMENT.md` file

## Usage

To generate a task management plan, run this command:

```bash
claude-code "Please read and analyze the docs/PRD.md file, then create an actionable development work plan using the template below. Save the results to docs/TASK_MANAGEMENT.md file. **Important: Generate all content in Korean language for better team communication and localization.**"
```

## Task Management Prompt Template

You are a senior tech lead and project manager with 15 years of experience. Based on the feature specifications and constraints in the docs/PRD.md file, please establish an actionable development work plan.

### 📋 Analysis Phase

**Step 1: PRD-Based Feature Analysis**
First, read the docs/PRD.md file and identify key features, then organize them in the following table format:

| Feature Name | Purpose | User Value | Technical Complexity | Notes |
|--------------|---------|------------|---------------------|-------|
| [Feature1] | [Purpose] | [Value] | High/Medium/Low | [Special Notes] |

**Step 2: Task Breakdown**
Break down each feature from the PRD into tasks that can be completed within 2-5 days, using the template below:

```
🔹 Task ID: T-001
📝 Task Name: [Clear and specific title]
📄 Description: [Detailed requirements that developers can immediately start working on]
✅ Completion Criteria:
- [ ] Condition 1
- [ ] Condition 2  
- [ ] Condition 3
⏱️ Estimated Effort: [X days or X hours]
🎯 Responsibility Area: [Frontend/Backend/DB/DevOps/Full-stack]
🏷️ Tags: [UI, API, Database, Integration, etc.]
```

**Step 3: Priority Matrix**
Evaluate each task on the following criteria (1-5 points) and determine priority:

**Evaluation Criteria:**
- Business Impact (1-5 points)
- User Impact (1-5 points)
- Technical Risk (1-5 points, higher = more risky)
- Dependency Importance (1-5 points, how much other tasks depend on this task)

**Priority Classification:**
- 🔴 P0 (Critical): Total 16-20 points, core to project success
- 🟡 P1 (High): Total 12-15 points, major feature components
- 🟢 P2 (Medium): Total 8-11 points, user experience improvements
- 🔵 P3 (Low): Total 4-7 points, additional features and optimizations

**Step 4: Dependency Relationship Mapping**
Express dependencies between tasks using the following symbols:

```
T-001 → T-002 (Hard): T-002 can start after T-001 completion
T-003 ⤏ T-004 (Soft): T-004 is more efficient when T-003 is completed
T-005 || T-006 (Parallel): Can proceed simultaneously
```

**Step 5: Execution Roadmap**
Build a schedule that must be completed within 3 months. Establish a phased execution plan considering dependencies:

```
📅 Phase 1: Foundation Building (Week 1-X)
🎯 Goal: Core infrastructure and basic feature implementation
📋 Tasks: [P0 tasks with no dependencies - foundational work]
🚩 Key Milestones: [Important completion points]

📅 Phase 2: Core Features (Week X-X)
🎯 Goal: Main business logic implementation
📋 Tasks: [Core user features]
🚩 Key Milestones: [Demo-ready feature completion]

📅 Phase 3: Integration & Completion (Week X-X)
🎯 Goal: Feature integration and user experience completion
📋 Tasks: [Integration, testing, UX improvements]
🚩 Key Milestones: [Beta release preparation]

📅 Phase 4: Optimization & Launch (Week X)
🎯 Goal: Performance optimization and production readiness
📋 Tasks: [Optimization, security, monitoring]
🚩 Key Milestones: [Official launch]
```

**Step 6: Risk Management**
Identify potential risks and response measures:

```
⚠️ Technical Risks:
- Risk: [Specific risk situation]
- Impact: [Impact on project]
- Response: [Specific response measures]
- Alternative: [Plan B]

⚠️ Schedule Risks:
- Risk: [Tasks with high delay probability]
- Impact: [Impact on overall schedule]
- Response: [Schedule risk mitigation measures]
- Alternative: [Scope adjustment options]
```

### 📊 Final Deliverables

**Task Summary Table:**
| Priority | Task ID | Task Name | Effort | Dependencies | Responsibility Area |
|----------|---------|-----------|--------|--------------|-------------------|
| P0 | T-001 | [...] | 3 days | None | Backend |

**Critical Path:**
```
Start → T-001 → T-003 → T-007 → T-012 → Complete
(Total Duration: X days, Buffer: Y days)
```

**Team Work Distribution:**
- Frontend Team: [Task list and schedule]
- Backend Team: [Task list and schedule]
- DevOps Team: [Task list and schedule]

---

## Claude Code Execution Instructions

1. **Read PRD File:**
   - Read the `docs/PRD.md` file to understand project information
   - Analyze core features, tech stack, timeline, etc.

2. **Perform Systematic Analysis:**
   - Proceed through steps 1-6 sequentially
   - Break down PRD feature specifications into actionable tasks
   - Establish execution plan considering dependencies and priorities

3. **Generate Deliverables:**
   - Save as `docs/TASK_MANAGEMENT.md` file
   - **Write all content in Korean for better localization**
   - Provide actionable and specific work plans

4. **Additional Considerations:**
   - Utilize tech stack specified in PRD
   - Adjust to scope completable within 3-month timeline
   - Consider team composition (1-2 full-stack developers) for work distribution

## Additional Prompt Examples

### Basic Task Management Generation
```bash
claude-code "Analyze docs/PRD.md to generate a task management plan and save it as docs/TASK_MANAGEMENT.md. Please write all content in Korean."
```

### Feature-Specific Task Analysis
```bash
claude-code "Analyze only authentication-related features from docs/PRD.md and generate a detailed task plan. Generate the output in Korean language."
```

### Sprint Planning Generation
```bash
claude-code "Generate a 2-week sprint plan based on TASK_MANAGEMENT.md. Please provide the output in Korean."
```

### Progress Update
```bash
claude-code "Check currently completed tasks and reprioritize remaining work. Write the update in Korean language."
```

### Risk Assessment Update
```bash
claude-code "Review identified risks in TASK_MANAGEMENT.md and update mitigation strategies based on current project status. Generate the report in Korean."
```

### Critical Path Analysis
```bash
claude-code "Analyze the critical path in our task management plan and identify potential bottlenecks. Please provide the analysis in Korean language."
```

---

## Usage Tips

1. **Regular Updates**: Update task status weekly to adjust plans accordingly
2. **Dependency Management**: Prioritize monitoring tasks on the critical path
3. **Risk Response**: Regularly check identified risk factors and implement response measures
4. **Team Communication**: Share work distribution tables with team members for clear role assignment
5. **Milestone Tracking**: Use key milestones to measure progress and adjust scope if needed
6. **Buffer Management**: Maintain time buffers for high-risk tasks to prevent schedule delays

## Integration with Other Tools

This task management assistant works best when integrated with:
- **PRD Generator**: Use the previously created PRD generation assistant to create `docs/PRD.md`
- **Project Management Tools**: Export task lists to tools like Jira, Asana, or Linear
- **Development Workflow**: Align task IDs with Git branches and pull requests
- **Team Standups**: Use priority classifications for daily standup discussions

## Advanced Features

### Custom Task Templates
```bash
claude-code "Create custom task templates for [specific technology/framework] based on our PRD requirements. Please generate the templates in Korean language."
```

### Resource Allocation
```bash
claude-code "Analyze task complexity and suggest optimal resource allocation across team members. Provide the analysis in Korean."
```

### Timeline Optimization
```bash
claude-code "Optimize the current timeline by identifying parallel execution opportunities and reducing dependencies. Generate the optimization report in Korean language."
```

---

## Final Output Language Specification

**Important Note**: While this prompt template is provided in English for international accessibility, all generated task management documents, analysis reports, and deliverables should be created in **Korean language** to ensure:

- Better team communication within Korean development teams
- Consistent localization with PRD documents
- Improved readability for Korean-speaking stakeholders
- Seamless integration with local project management practices

Make sure to include the language specification in every Claude Code command to ensure consistent Korean output.