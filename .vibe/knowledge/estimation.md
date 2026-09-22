# Estimation

This document outlines **estimation techniques** for project management. Estimation helps teams **plan, prioritize, and allocate resources** effectively by providing a **realistic assessment** of the effort required to complete work items.

---

## Why Estimate?
Estimation serves several key purposes:
1. **Planning**: Helps create realistic timelines and milestones.
2. **Prioritization**: Enables informed decisions about what to work on next.
3. **Resource Allocation**: Ensures the right resources are assigned to tasks.
4. **Risk Management**: Identifies potential delays or bottlenecks early.
5. **Stakeholder Communication**: Provides transparency to stakeholders about effort and timelines.

---

## Estimation Techniques
Different techniques can be used depending on the **stage of the project** and the **level of detail available**.

### **1. T-Shirt Sizing**
**Best for**: High-level estimation (e.g., Epics, Features).
**Description**: Assign sizes like `XS`, `S`, `M`, `L`, `XL` to work items based on relative effort.

| Size | Description | Example |
|------|-------------|---------|
| XS   | Very small effort (hours) | Fix a typo in documentation |
| S    | Small effort (1-2 days) | Add a minor UI tweak |
| M    | Medium effort (3-5 days) | Implement a new API endpoint |
| L    | Large effort (1-2 weeks) | Redesign a major feature |
| XL   | Very large effort (2+ weeks) | Build a new module from scratch |

**Pros**: Quick, easy to understand, and useful for prioritization.
**Cons**: Lack of precision; not suitable for detailed planning.

---

### **2. Story Points**
**Best for**: Agile teams estimating **Stories** or **Tasks**.
**Description**: Assign a numerical value (e.g., 1, 2, 3, 5, 8, 13) to represent the **relative effort** required to complete a work item. The scale is based on the **Fibonacci sequence** to reflect uncertainty.

| Points | Description | Example |
|--------|-------------|---------|
| 1      | Very simple, minimal effort | Update a configuration file |
| 2      | Simple, low effort | Add a new field to a form |
| 3      | Moderate effort | Implement a new UI component |
| 5      | Complex effort | Integrate with a third-party API |
| 8      | High effort | Redesign a database schema |
| 13     | Very high effort | Build a new feature from scratch |

**Pros**: Encourages team collaboration and accounts for uncertainty.
**Cons**: Requires calibration across the team; not directly tied to time.

---

### **3. Time-Based Estimation**
**Best for**: Detailed planning (e.g., Tasks, Bugs).
**Description**: Estimate the **actual time** (e.g., hours, days) required to complete a work item.

**Example**:
```markdown
**Task**: Implement Tooltip Component
- **Estimate**: 8 hours
- **Breakdown**:
  - Design: 2 hours
  - Development: 4 hours
  - Testing: 2 hours
```

**Pros**: Directly tied to timelines; easy to understand.
**Cons**: Can be inaccurate due to unknowns or dependencies.

---

### **4. Planning Poker**
**Best for**: Team-based estimation (e.g., Sprint Planning).
**Description**: A collaborative technique where team members **individually estimate** the effort for a work item using cards (e.g., Fibonacci sequence). After revealing estimates, the team discusses discrepancies and re-estimates until consensus is reached.

**Steps**:
1. Present the work item (e.g., Story, Task).
2. Team members **individually** select an estimate card.
3. All estimates are revealed simultaneously.
4. Discuss discrepancies and re-estimate if needed.
5. Repeat until consensus is reached.

**Pros**: Encourages discussion and alignment; reduces bias.
**Cons**: Time-consuming; requires team participation.

---

### **5. Analogous Estimation**
**Best for**: Estimating work items similar to **previously completed work**.
**Description**: Compare the new work item to a **similar, completed work item** and use its actual effort as the estimate.

**Example**:
```markdown
**Task**: Implement User Authentication
- **Analogous Task**: Implement Admin Authentication (completed in 5 days)
- **Estimate**: 5 days
```

**Pros**: Quick and data-driven.
**Cons**: Requires historical data; may not account for differences.

---

### **6. Parametric Estimation**
**Best for**: Estimating work based on **quantitative data** (e.g., lines of code, number of API endpoints).
**Description**: Use **statistical relationships** between historical data and work item attributes to estimate effort.

**Example**:
```markdown
**Task**: Develop a New API
- **Historical Data**: 10 hours per API endpoint
- **Number of Endpoints**: 5
- **Estimate**: 10 hours * 5 = 50 hours
```

**Pros**: Data-driven and scalable.
**Cons**: Requires historical data; may not account for complexity.

---

## Factors Affecting Estimation
Consider the following factors when estimating:

### **1. Complexity**
- How technically complex is the work item?
- Are there unknowns or risks?

### **2. Dependencies**
- Are there dependencies on other teams, systems, or work items?
- Are dependencies likely to cause delays?

### **3. Team Experience**
- How familiar is the team with the technology or domain?
- Are there skill gaps that need to be addressed?

### **4. Clarity of Requirements**
- Are the requirements clear and well-defined?
- Are there ambiguities or open questions?

### **5. External Constraints**
- Are there deadlines, budgets, or other constraints?
- Are there regulatory or compliance requirements?

---

## Estimation Best Practices
1. **Involve the Team**: Estimation should be a **collaborative process** involving the team members who will do the work.
2. **Break Down Work**: Decompose large work items into **smaller, estimable tasks**.
3. **Use Relative Sizing**: For high-level estimation, use **T-Shirt Sizing** or **Story Points**.
4. **Account for Uncertainty**: Use **ranges** (e.g., 3-5 days) or **buffer time** to account for unknowns.
5. **Review and Refine**: Regularly review estimates as more information becomes available.
6. **Track Actuals**: Compare estimates to **actual effort** to improve future estimates.
7. **Avoid Anchoring**: Do not let initial estimates bias the team; encourage independent thinking.

---

## Estimation Pitfalls
| Pitfall | Description | Mitigation |
|---------|-------------|------------|
| **Over-optimism** | Underestimating effort due to optimism | Use historical data; add buffers |
| **Anchoring** | Letting initial estimates bias the team | Encourage independent estimates |
| **Groupthink** | Team members conform to a single estimate | Use anonymous estimation (e.g., Planning Poker) |
| **Ignoring Dependencies** | Not accounting for dependencies | Explicitly document dependencies |
| **Scope Creep** | Adding work without updating estimates | Freeze scope during estimation |

---

## Tools for Estimation
- **Jira**: Use built-in estimation fields (e.g., Story Points, Time Tracking).
- **Trello**: Use labels or custom fields for estimation.
- **Planning Poker Tools**: [Planning Poker Online](https://www.planningpoker.com/), [Scrum Poker](https://www.scrumpoker-online.org/)
- **Spreadsheets**: Use Excel or Google Sheets for parametric estimation.

---

## Example: Estimating an Epic
**Epic**: Enhance User Onboarding Experience

### **Step 1: Decompose into Features**
1. Redesign Onboarding UI
2. Add Interactive Tooltips
3. Improve Onboarding Documentation

### **Step 2: Estimate Features**
| Feature | Estimate (Story Points) | Notes |
|---------|-------------------------|-------|
| Redesign Onboarding UI | 13 | Complex due to UI/UX dependencies |
| Add Interactive Tooltips | 8 | Medium complexity |
| Improve Onboarding Documentation | 5 | Low complexity |

### **Step 3: Decompose Features into Stories**
**Feature**: Add Interactive Tooltips
- **Story 1**: As a user, I want to see tooltips on hover so that I understand how to use the platform. (5 points)
- **Story 2**: As a user, I want tooltips to be dismissible so that I can focus on the content. (3 points)

### **Step 4: Estimate Stories**
Use **Planning Poker** to estimate Stories collaboratively.

### **Step 5: Aggregate Estimates**
- **Epic Estimate**: 13 + 8 + 5 = **26 Story Points**
- **Sprint Capacity**: 20 Story Points per sprint
- **Estimated Duration**: 2 sprints (assuming no dependencies)

---

## Key Takeaways
- **Estimation is not exact**: It is an **approximation** based on available information.
- **Use multiple techniques**: Combine techniques (e.g., T-Shirt Sizing + Planning Poker) for better accuracy.
- **Refine as you go**: Update estimates as more information becomes available.
- **Learn from history**: Use **actual effort** to improve future estimates.