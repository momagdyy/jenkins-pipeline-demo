# Jenkins CI/CD — Questions & Answers

---

## Q1: What is CI/CD?

**CI/CD** stands for **Continuous Integration / Continuous Delivery (or Deployment)**.

It is a set of practices and automation pipelines that streamline software development and release.

- **Continuous Integration (CI):** Developers frequently merge code changes into a shared repository. Each merge triggers automated builds and tests to catch bugs early.

- **Continuous Delivery (CD):** Code that passes CI is automatically prepared and ready to be deployed to production at any time (requires manual approval to deploy).

- **Continuous Deployment (CD):** Goes one step further — every passing change is automatically deployed to production without manual intervention.

**The Goal:** Deliver software faster, with higher quality, and with less risk.

---

## Q2: What are Three CI/CD Tools?

| Tool | Description |
|------|-------------|
| **Jenkins** | Open-source, self-hosted automation server — highly extensible via plugins |
| **GitHub Actions** | Native CI/CD built into GitHub — YAML-based workflows triggered by repo events |
| **GitLab CI/CD** | Built into GitLab — pipeline defined via `.gitlab-ci.yml` |

---

## Q3: What is a Jenkins Pipeline?

A **Jenkins Pipeline** is a suite of plugins that supports implementing and integrating **continuous delivery pipelines** into Jenkins.

It defines the entire build/test/deploy process as **code** (called *Pipeline as Code*), stored in a file called a **Jenkinsfile**.

A pipeline typically flows through stages like:

```
Code → Build → Test → Deploy
```

It allows you to version, review, and audit your entire CI/CD process just like application code.

---

## Q4: What Language is Jenkins Based On?

Jenkins is built on **Java**.

It runs on the **JVM (Java Virtual Machine)** and requires a Java runtime (JDK 11 or 17+) to operate.

---

## Q5: What Scripting Language is Jenkins Pipeline Syntax Based On?

Jenkins Pipeline syntax is based on **Groovy** — a dynamic language for the JVM.

There are two styles:

- **Declarative Pipeline** → Structured Groovy DSL (easier, recommended)
- **Scripted Pipeline** → Full Groovy code (more flexible, more complex)

---

## Q6: What are the Ways to Write a Pipeline in Jenkins?

There are **two main ways:**

### 1. Declarative Pipeline
Structured, opinionated syntax. Uses a `pipeline {}` block.

```groovy
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
    }
}
```

### 2. Scripted Pipeline
Full Groovy scripting power. Uses a `node {}` block.

```groovy
node {
    stage('Build') {
        echo 'Building...'
    }
}
```

### Where to write it:

| Location | Description |
|----------|-------------|
| **Inline** | Directly in the Jenkins job configuration UI |
| **Jenkinsfile** | Stored in your source code repository (recommended best practice) |

---

*Created by Megz — Jenkins CI/CD Lab*
