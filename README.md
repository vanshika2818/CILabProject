# CI Lab Project: Jenkins CI/CD Implementation

## 1. Project Overview
This repository contains a full Jenkins CI/CD lab implementation. It demonstrates a distributed Master-Agent architecture to automate the lifecycle of a Java-based application.

### Repository Structure
- `src/`: Core Java source code and unit tests.
- `scripts/`: Automation scripts, including `sample.py`.
- `docker/`: Configuration for containerizing the application.
- `Jenkinsfile`: The Pipeline-as-Code definition.
- `pom.xml`: Maven project configuration.

---

## 2. Installation Guide
Follow these steps to set up the environment:

### Prerequisites
- **Java JDK 17+**: Required for the application and Jenkins.
- **Apache Maven**: Required to handle builds and dependencies.
- **Jenkins**: Ensure Jenkins is running and the "Pipeline" and "Git" plugins are installed.

### Setup Instructions
1. **Clone the Project**:
   `git clone <your-repo-url>`
2. **Configure Jenkins**:
   - Create a new **Pipeline Job**.
   - Under **Pipeline**, select "Pipeline script from SCM".
   - Link your GitHub repository URL and set the branch to `main`.

---

## 3. User Manual
### Running the Pipeline
- **Manual Trigger**: Click **Build Now** on the Jenkins project dashboard.
- **Automated Trigger**: Pushing code to the `main` branch will trigger the pipeline if Webhooks are configured.

### Viewing Results
- **Stage View**: Monitor the progress of Checkout, Build, Test, and Deploy stages.
- **Console Output**: Access logs by clicking on a specific build number to verify the execution of tasks like `echo 'Building project'` or the output of `sample.py`.

---

## 4. Troubleshooting Guide
| Issue | Potential Solution |
| :--- | :--- |
| **Build Failure** | Check the **Console Output** for Java compilation or Maven dependency errors. |
| **Script Errors** | Ensure Python is installed and accessible in the system PATH for `sample.py`. |
| **Agent Offline** | Verify that the Jenkins Agent (Slave) has a stable connection to the Master. |
| **Permission Denied** | Use `chmod +x` on any shell scripts within the `scripts/` directory. |

---

## 5. Jenkins Pipeline (Logic)
The `Jenkinsfile` in this repo follows a structured pipeline:
- **Checkout**: Pulls code from the repository.
- **Build**: Compiles the project (e.g., using `mvn clean compile`).
- **Test**: Executes unit tests and Python validation scripts.
- **Deploy**: Prepares the final artifact for delivery.
