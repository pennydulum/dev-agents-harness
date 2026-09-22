# Library

This directory contains **reference materials** for agents in the `.vibe/` ecosystem. These resources provide **additional context, best practices, and external knowledge** to support agents in their tasks.

---

## Structure
```text
.vibe/library/
├── agile/              # Agile methodologies and frameworks
│   ├── scrum-guide.md
│   └── kanban-guide.md
├── pmbook/            # Project Management Body of Knowledge (PMBOK)
│   └── terminology.md
└── engineering/        # Engineering best practices
    ├── github-flow.md
    ├── ci-cd.md
    └── testing-strategy.md
```

---

## Agile
### **Scrum Guide**
- **Description**: The official guide to **Scrum**, including roles, artifacts, and events.
- **Resource**: [Scrum Guide](https://scrumguides.org)

### **Kanban Guide**
- **Description**: Principles and practices for **Kanban**, including workflow visualization and WIP limits.
- **Resource**: [Kanban University](https://kanban.university)

---

## PMBOK (Project Management Body of Knowledge)
### **Terminology**
- **Description**: Key terms and definitions from the **PMBOK Guide**, including:
  - Project
  - Stakeholder
  - Scope
  - Schedule
  - Cost
  - Quality
  - Risk
  - Procurement
  - Integration

---

## Engineering
### **GitHub Flow**
- **Description**: A **lightweight, branch-based workflow** for GitHub projects.
- **Key Concepts**:
  - **Main Branch**: Always deployable.
  - **Feature Branches**: Created for new features, bug fixes, or experiments.
  - **Pull Requests**: Used to discuss and review code.
  - **Merge**: Feature branches are merged into `main` after review.
- **Resource**: [GitHub Flow](https://docs.github.com/en/get-started/quickstart/github-flow)

### **CI/CD (Continuous Integration/Continuous Deployment)**
- **Description**: Best practices for **automating testing, building, and deployment**.
- **Key Concepts**:
  - **Continuous Integration (CI)**: Automatically test code changes.
  - **Continuous Deployment (CD)**: Automatically deploy code changes to production.
  - **Pipelines**: Define workflows for CI/CD (e.g., GitHub Actions, GitLab CI).
- **Tools**:
  - GitHub Actions
  - GitLab CI
  - Jenkins
  - CircleCI

### **Testing Strategy**
- **Description**: Best practices for **testing software** to ensure quality and reliability.
- **Types of Testing**:
  - **Unit Testing**: Test individual components or functions.
  - **Integration Testing**: Test interactions between components.
  - **End-to-End Testing**: Test the entire application flow.
  - **Performance Testing**: Test system performance under load.
  - **Security Testing**: Test for vulnerabilities and compliance.
- **Tools**:
  - Jest (JavaScript)
  - pytest (Python)
  - JUnit (Java)
  - Selenium (Browser Automation)
  - Postman (API Testing)

---

## Adding to the Library
To add new resources to the library:
1. **Create a new directory** for a new category (e.g., `data-science/`).
2. **Add files** for specific topics (e.g., `data-science/pandas-guide.md`).
3. **Link to external resources** where applicable (e.g., official documentation, tutorials).

---

## Usage
- **Reference**: Use the library to **inform decisions** and **guide workflows**.
- **Extend**: Add new resources as needed to support agents.
- **Share**: The library is **shared across all agents** in the `.vibe/` ecosystem.