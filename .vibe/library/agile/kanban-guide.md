# Kanban Guide

This document summarizes **Kanban**, a **visual workflow management method** that helps teams **balance demands with available capacity** and **improve the handling of system-level bottlenecks**. Kanban is based on **lean principles** and focuses on **continuous improvement**.

---

## Kanban Overview
Kanban is a **lightweight, flexible approach** to managing work, with a focus on **visualizing workflow**, **limiting work in progress (WIP)**, and **improving flow**. It is not prescriptive and can be applied to any workflow, from software development to marketing and operations.

### **Core Principles**
1. **Start with what you do now**: Kanban does not require a specific setup or process changes upfront. Start with your current workflow and evolve it over time.
2. **Pursue incremental, evolutionary change**: Make small, continuous improvements to your process.
3. **Respect the current process, roles, and responsibilities**: Do not impose changes; instead, encourage collaboration and consensus.
4. **Encourage acts of leadership at all levels**: Everyone in the team is encouraged to take ownership and drive improvements.

---

## Kanban Practices
Kanban is built on **six core practices**:

### **1. Visualize the Workflow**
- **Purpose**: Create a **visual representation** of your workflow to make the work visible and understandable.
- **How**: Use a **Kanban board** with columns representing different stages of the workflow (e.g., To Do, In Progress, Done).
- **Example**:
  ```markdown
  | To Do | In Progress | Review | Done |
  |-------|-------------|--------|------|
  | Task 1 | Task 2      | Task 3 | Task 4 |
  ```

### **2. Limit Work in Progress (WIP)**
- **Purpose**: Prevent **multitasking** and **bottlenecks** by limiting the number of work items in progress at any given time.
- **How**: Set **WIP limits** for each column on the Kanban board.
- **Example**:
  - **To Do**: No limit
  - **In Progress**: Max 3 tasks
  - **Review**: Max 2 tasks
  - **Done**: No limit

### **3. Manage Flow**
- **Purpose**: Monitor, measure, and **optimize the flow of work** through the workflow.
- **How**: Use **metrics** like **cycle time** (time from start to finish) and **lead time** (time from request to delivery) to identify bottlenecks and inefficiencies.
- **Tools**:
  - **Cumulative Flow Diagram (CFD)**: Visualize the flow of work over time.
  - **Cycle Time Scatterplot**: Analyze the distribution of cycle times.

### **4. Make Process Policies Explicit**
- **Purpose**: Ensure **clarity and consistency** in how work is handled.
- **How**: Define and document **policies** for each stage of the workflow (e.g., Definition of Done, Definition of Ready).
- **Example**:
  - **Definition of Done**:
    - Code reviewed and approved.
    - Tests pass.
    - Documentation updated.

### **5. Implement Feedback Loops**
- **Purpose**: **Continuously improve** the process based on feedback.
- **How**: Hold **regular meetings** (e.g., daily standups, retrospectives) to discuss workflow, bottlenecks, and improvements.
- **Example**:
  - **Daily Standup**: What did I do yesterday? What will I do today? Are there any blockers?
  - **Retrospective**: What went well? What didn’t? How can we improve?

### **6. Improve Collaboratively, Evolve Experimentally**
- **Purpose**: Encourage **team collaboration** and **experimentation** to find better ways of working.
- **How**: Use the **Scientific Method** to test changes:
  1. **Hypothesize**: Propose a change to improve the process.
  2. **Experiment**: Implement the change on a small scale.
  3. **Evaluate**: Measure the impact of the change.
  4. **Adopt or Discard**: Keep the change if it improves the process; discard it if it doesn’t.

---

## Kanban Board
A **Kanban board** is the primary tool for visualizing and managing work in Kanban. It typically consists of:

### **Columns**
- Represent **stages of the workflow** (e.g., To Do, In Progress, Review, Done).
- Can be **customized** to match your team’s process.

### **Cards**
- Represent **work items** (e.g., tasks, user stories, bugs).
- Move across columns as they progress through the workflow.

### **Swimlanes**
- Horizontal lanes that **categorize work items** (e.g., by priority, type, or team).
- Example:
  - **Expedite**: High-priority work that jumps the queue.
  - **Standard**: Normal work items.

---

## Kanban Metrics
Use metrics to **measure and improve** the flow of work:

### **1. Cycle Time**
- **Definition**: The time it takes for a work item to move from **start to finish**.
- **Purpose**: Identify bottlenecks and inefficiencies in the workflow.
- **Example**: If the average cycle time for a task is 5 days, look for ways to reduce it.

### **2. Lead Time**
- **Definition**: The time it takes for a work item to move from **request to delivery**.
- **Purpose**: Measure the **total time** from when work is requested to when it is delivered.
- **Example**: If the lead time for a feature is 10 days, look for ways to streamline the process.

### **3. Throughput**
- **Definition**: The number of work items **completed per unit of time** (e.g., tasks per week).
- **Purpose**: Measure the **team’s productivity** and capacity.
- **Example**: If the team completes 10 tasks per week, use this to forecast future work.

### **4. Work in Progress (WIP)**
- **Definition**: The number of work items **currently in progress**.
- **Purpose**: Monitor WIP to ensure it stays within **WIP limits**.
- **Example**: If the WIP limit for "In Progress" is 3, ensure no more than 3 tasks are in this column.

### **5. Cumulative Flow Diagram (CFD)**
- **Definition**: A **visual representation** of the flow of work over time.
- **Purpose**: Identify **bottlenecks** and **trends** in the workflow.
- **Example**: If the "In Progress" column is growing over time, there may be a bottleneck in this stage.

---

## Kanban vs. Scrum
While both Kanban and Scrum are **Agile methodologies**, they have key differences:

| Feature | Kanban | Scrum |
|---------|--------|-------|
| **Workflow** | Continuous flow | Iterative (Sprints) |
| **WIP Limits** | Yes | No (but can be added) |
| **Roles** | No predefined roles | Product Owner, Scrum Master, Developers |
| **Events** | No predefined events | Sprint Planning, Daily Scrum, Sprint Review, Sprint Retrospective |
| **Artifacts** | Kanban board | Product Backlog, Sprint Backlog, Increment |
| **Flexibility** | High | Medium |
| **Best For** | Continuous delivery, maintenance work | Complex projects, rapid iterations |

---

## Getting Started with Kanban
1. **Map Your Workflow**: Visualize your current process.
2. **Set Up a Kanban Board**: Use a physical board or a digital tool (e.g., Trello, Jira, GitHub Projects).
3. **Define WIP Limits**: Set limits for each column to prevent multitasking.
4. **Start Small**: Begin with a simple board and evolve it over time.
5. **Measure and Improve**: Use metrics to identify bottlenecks and improve flow.

---

## Tools for Kanban
- **Trello**: Simple, visual Kanban boards.
- **Jira**: Advanced Kanban features for software teams.
- **GitHub Projects**: Kanban-style project management for GitHub repositories.
- **Azure DevOps**: Kanban boards for Agile teams.
- **Kanbanize**: Dedicated Kanban tool with advanced analytics.

---

## Resources
- [Kanban University](https://kanban.university)
- [Kanban Guide by Atlassian](https://www.atlassian.com/agile/kanban)
- [Lean Kanban Inc.](https://www.leankanban.com)