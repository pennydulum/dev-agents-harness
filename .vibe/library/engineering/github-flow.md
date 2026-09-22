# GitHub Flow

This document outlines **GitHub Flow**, a **lightweight, branch-based workflow** for managing projects on GitHub. GitHub Flow is designed to support **teams and projects where deployments are made regularly** and **feedback is continuous**.

---

## Overview
GitHub Flow is a **simple, flexible workflow** that supports:
- **Feature branches**: Isolate work in progress.
- **Pull requests**: Discuss and review code.
- **Continuous deployment**: Deploy branches to production.

It is particularly well-suited for **teams practicing Continuous Integration/Continuous Deployment (CI/CD)**.

---

## Core Principles
1. **Anything in the `main` branch is deployable**: The `main` branch should always be in a state where it can be deployed to production.
2. **Create feature branches for new work**: All new features, bug fixes, or experiments should be developed in a **dedicated branch**.
3. **Submit pull requests for feedback**: Use **pull requests (PRs)** to discuss and review code changes.
4. **Test code in production-like environments**: Ensure code is tested in an environment that mimics production.
5. **Merge pull requests after review**: Once a PR is approved, merge it into `main`.
6. **Deploy to production immediately**: After merging, deploy the changes to production as soon as possible.

---

## Workflow Steps

### **1. Create a Feature Branch**
- **Purpose**: Isolate new work (features, bug fixes, experiments) from the `main` branch.
- **How**:
  ```bash
  git checkout main
  git pull origin main
  git checkout -b feature/new-feature
  ```
- **Naming Convention**: Use a **descriptive name** (e.g., `feature/add-login`, `bugfix/fix-login-error`).

---

### **2. Commit Changes to the Branch**
- **Purpose**: Implement the new feature or fix in the feature branch.
- **Best Practices**:
  - **Small, frequent commits**: Make small, logical changes and commit them frequently.
  - **Descriptive commit messages**: Use clear, concise messages (e.g., `Add login form validation`).
  - **Sign commits**: Use `git commit -S` to sign commits with your GPG key.

---

### **3. Push the Branch to GitHub**
- **Purpose**: Share your changes with the team for review.
- **How**:
  ```bash
  git push origin feature/new-feature
  ```

---

### **4. Open a Pull Request (PR)**
- **Purpose**: Request feedback and review for your changes.
- **How**:
  1. Navigate to your repository on GitHub.
  2. Click **Pull Requests** > **New Pull Request**.
  3. Select your feature branch as the **compare branch** and `main` as the **base branch**.
  4. Add a **clear title and description** for the PR.
  5. Link to any **related issues** (e.g., `Closes #123`).
  6. Click **Create Pull Request**.

- **Best Practices**:
  - **Descriptive title**: Summarize the changes in the PR title.
  - **Detailed description**: Explain the **what**, **why**, and **how** of the changes.
  - **Link to issues**: Reference any related issues or tickets.
  - **Request reviewers**: Assign team members to review the PR.

---

### **5. Discuss and Review the PR**
- **Purpose**: Collaborate with the team to improve the changes.
- **How**:
  - **Reviewers** provide feedback via **comments** on the PR.
  - **Author** addresses feedback by **pushing new commits** to the feature branch.
  - Use **GitHub’s review tools** (e.g., line comments, approvals, requests for changes).

- **Best Practices**:
  - **Be constructive**: Focus on improving the code, not criticizing the author.
  - **Address all feedback**: Ensure all comments are resolved before merging.
  - **Use suggestions**: GitHub allows reviewers to **suggest changes** directly in the PR.

---

### **6. Test the Changes**
- **Purpose**: Ensure the changes work as expected and do not introduce bugs.
- **How**:
  - **Automated tests**: Run CI/CD pipelines (e.g., GitHub Actions) to verify the changes.
  - **Manual testing**: Test the changes locally or in a staging environment.
  - **Code review**: Ensure the changes follow best practices and meet the project’s standards.

---

### **7. Merge the Pull Request**
- **Purpose**: Incorporate the changes into the `main` branch.
- **How**:
  1. Ensure all **feedback is addressed** and the PR is **approved**.
  2. Click **Merge Pull Request** on GitHub.
  3. Choose a **merge strategy** (e.g., **Merge Commit**, **Squash and Merge**, **Rebase and Merge**).
  4. Confirm the merge.

- **Best Practices**:
  - **Squash and Merge**: Use this to **condense multiple commits** into a single commit for a cleaner history.
  - **Require approvals**: Enforce **PR approvals** to ensure quality.
  - **Require status checks**: Ensure all **CI/CD checks pass** before merging.

---

### **8. Deploy to Production**
- **Purpose**: Release the changes to users.
- **How**:
  - Use **GitHub Actions**, **Vercel**, **Netlify**, or other CI/CD tools to **automatically deploy** the `main` branch to production.
  - Alternatively, manually deploy using your **deployment pipeline**.

- **Best Practices**:
  - **Automate deployments**: Use **CI/CD pipelines** to deploy automatically after merging.
  - **Monitor deployments**: Use **logging and monitoring tools** (e.g., Sentry, Datadog) to track deployments.
  - **Rollback plan**: Have a **rollback strategy** in case of issues.

---

## GitHub Flow vs. Git Flow
GitHub Flow and **Git Flow** are both **branch-based workflows**, but they have key differences:

| Feature | GitHub Flow | Git Flow |
|---------|-------------|----------|
| **Branching Model** | Simple (feature branches + `main`) | Complex (feature, develop, release, hotfix branches) |
| **Deployment** | Continuous (deploy `main` to production) | Scheduled (deploy `release` branches) |
| **Release Management** | Not built-in | Built-in (release branches, tags) |
| **Best For** | Continuous delivery, web apps | Versioned software, mobile apps |

---

## Best Practices for GitHub Flow
1. **Keep `main` Deployable**: Always ensure `main` is in a deployable state.
2. **Use Feature Branches**: Isolate work in progress to avoid breaking `main`.
3. **Write Good Commit Messages**: Use **clear, descriptive messages** to document changes.
4. **Review Pull Requests**: Enforce **code reviews** to maintain quality.
5. **Automate Testing**: Use **GitHub Actions** or other CI tools to test changes.
6. **Deploy Frequently**: Deploy small, incremental changes to production often.
7. **Monitor Deployments**: Use **logging and monitoring** to catch issues early.

---

## Tools for GitHub Flow
- **GitHub**: Host repositories, manage PRs, and deploy code.
- **GitHub Actions**: Automate testing, building, and deploying.
- **GitHub CLI (`gh`)**: Manage repositories, PRs, and issues from the command line.
- **Vercel/Netlify**: Deploy web applications automatically from GitHub.
- **Sentry/Datadog**: Monitor deployments and catch errors.

---

## Resources
- [GitHub Flow Documentation](https://docs.github.com/en/get-started/quickstart/github-flow)
- [GitHub Actions](https://docs.github.com/en/actions)
- [GitHub CLI (`gh`)](https://cli.github.com/)
- [Vercel GitHub Integration](https://vercel.com/docs/git/vercel-for-github)
- [Netlify GitHub Integration](https://docs.netlify.com/configure-builds/repo-permissions-link/)