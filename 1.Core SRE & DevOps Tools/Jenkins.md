# 🧱 Section A: Jenkins

## ✅ 1. Introduction

Jenkins is an open-source automation server used to build, test, and deploy software. It enables Continuous Integration (CI) and Continuous Delivery (CD), helping teams automate the software development lifecycle. Jenkins supports a wide range of plugins, integrations, and pipelines, making it a go-to choice for DevOps workflows.

---

## ✅ 2. Key Components

- **Job (Build Job)** – A task or pipeline that performs automation (build/test/deploy).
- **Node/Agent** – A machine that runs Jenkins jobs (can be master or slave).
- **Executor** – A computational slot on a node that runs builds.
- **Pipeline** – A series of steps defined as code (`Jenkinsfile`) for CI/CD.
- **Plugin** – Extends Jenkins’ functionality (e.g., Git, Docker, Slack).
- **SCM (Source Code Management)** – Git, SVN, etc., to pull code.
- **Artifact** – Build output stored for later use.

---

## ✅ 3. Common Commands / UI Features

| Feature | Description |
|---------|-------------|
| **Freestyle Job** | Simple jobs with steps defined in the UI. |
| **Pipeline Job** | Scripted or Declarative pipelines defined as code. |
| **Jenkinsfile** | File stored in repo that defines pipeline stages. |
| **Build Now** | Trigger a manual build. |
| **Build Triggers** | Configure when jobs run (e.g., SCM poll, webhook). |
| **Post-build Actions** | Archive artifacts, email notifications, etc. |
| **Credentials** | Securely store secrets and tokens. |
| **Console Output** | Shows real-time job logs. |
| **Blue Ocean** | Modern UI for pipeline visualization. |

---

## ✅ 4. Pros & Cons

### ✅ Pros:
- Highly extensible with 1800+ plugins
- Mature ecosystem with strong community support
- Supports complex workflows with Pipelines and Jenkinsfiles
- Easy integration with Git, Docker, Kubernetes, etc.
- Can be deployed anywhere: VM, container, cloud

### ❌ Cons:
- UI can be outdated and cluttered (without Blue Ocean)
- Plugin dependency management can become complex
- No native container isolation (unless integrated with Docker)
- Scaling horizontally requires manual setup

---

✅ Jenkins is a powerful tool in the DevOps toolkit for managing automation, builds, and continuous delivery pipelines across teams and environments.

# 🧱 Section B: Jenkins Interview Prep – Basic Questions (40)

This section covers 40 basic Jenkins interview questions with clear explanations, useful for beginners and those preparing for DevOps/SRE roles.

---

### ✅ 1. What is Jenkins?
Jenkins is an open-source automation server used for building, testing, and deploying applications.

---

### ✅ 2. What is CI/CD?
- **CI (Continuous Integration)**: Frequent code integration into a shared repo.
- **CD (Continuous Delivery/Deployment)**: Automated release of code to production.

---

### ✅ 3. What are Jenkins Jobs?
Jobs are tasks configured in Jenkins to perform automation steps like build, test, and deploy.

---

### ✅ 4. What is a Jenkins Pipeline?
A series of automated steps written as code (`Jenkinsfile`) to define the CI/CD process.

---

### ✅ 5. What is a Jenkinsfile?
A file (usually in the root of your repo) that defines pipeline stages and steps using Groovy or Declarative syntax.

---

### ✅ 6. How do you install Jenkins?
- Download `.war` file and run:  
```bash
java -jar jenkins.war
```
- Or install via package manager (`apt`, `yum`, `brew`).

---

### ✅ 7. What are build triggers?
Settings that define when a build should start (e.g., SCM poll, webhook, cron schedule).

---

### ✅ 8. What are Freestyle Projects?
Simple jobs configured via the Jenkins UI with minimal scripting.

---

### ✅ 9. What are the types of Jenkins pipelines?
- **Declarative**: Structured and recommended format.
- **Scripted**: More flexible, written in Groovy.

---

### ✅ 10. What is the difference between Declarative and Scripted pipelines?
- Declarative is simpler and has syntax rules.
- Scripted offers full control and flexibility using Groovy code.

---

### ✅ 11. How do you configure Git in Jenkins?
Add Git plugin, configure credentials, and use repository URL in job configuration.

---

### ✅ 12. How do you trigger a build remotely?
Use the Jenkins REST API or `curl` with a build token.

---

### ✅ 13. What is the purpose of the Jenkins home directory?
Stores all configurations, jobs, logs, and plugins. Default: `/var/lib/jenkins`.

---

### ✅ 14. How do you install plugins in Jenkins?
Via **Manage Jenkins → Manage Plugins** UI.

---

### ✅ 15. How do you backup Jenkins?
Backup the Jenkins home directory, especially the `jobs/`, `plugins/`, and `config.xml`.

---

### ✅ 16. What are Jenkins agents (nodes)?
Additional machines (slaves) that run jobs assigned by the master node.

---

### ✅ 17. What is the master-slave architecture in Jenkins?
The master schedules builds, and slaves (agents) execute them.

---

### ✅ 18. How do you configure agents?
Under **Manage Jenkins → Manage Nodes and Clouds**.

---

### ✅ 19. What is the use of environment variables in Jenkins?
They allow reuse of values and dynamic configuration in pipelines.

---

### ✅ 20. How do you add global environment variables?
Go to **Manage Jenkins → Configure System**, then define under Global Properties.

---

### ✅ 21. What are Jenkins credentials?
Stored secrets used securely inside jobs (SSH keys, tokens, usernames/passwords).

---

### ✅ 22. What are post-build actions?
Steps executed after the build (e.g., archiving artifacts, sending email notifications).

---

### ✅ 23. What are Jenkins artifacts?
Files generated during a job (e.g., binaries, logs) that can be saved and accessed later.

---

### ✅ 24. What is a workspace in Jenkins?
Directory where Jenkins checks out the source code and runs the build.

---

### ✅ 25. What is the Jenkins Blue Ocean?
A modern UI that improves the visualization and usability of pipeline jobs.

---

### ✅ 26. How do you create a parameterized build?
Enable **This project is parameterized** and define input parameters.

---

### ✅ 27. What is the default port Jenkins runs on?
`8080`

---

### ✅ 28. What are stages and steps in a pipeline?
- **Stage**: Logical group (e.g., Build, Test)
- **Step**: Individual command or function

---

### ✅ 29. How do you send notifications in Jenkins?
Using plugins like **Email Extension** or **Slack Notification**.

---

### ✅ 30. How do you set build retention policy?
In job configuration → **Discard Old Builds** section.

---

### ✅ 31. What does `pipeline { agent any }` mean?
It tells Jenkins to use any available agent to run the job.

---

### ✅ 32. How do you restart Jenkins?
```bash
$ sudo systemctl restart jenkins
```
Or via URL: `http://localhost:8080/restart`

---

### ✅ 33. What is SCM polling?
Jenkins periodically checks for changes in source control (e.g., Git) to trigger builds.

---

### ✅ 34. How do you pass parameters between stages?
Use `environment` variables or `script` block with Groovy variables.

---

### ✅ 35. What is the use of `input` step in a pipeline?
Pauses the pipeline to wait for manual approval or input.

---

### ✅ 36. What is a parallel step in Jenkins?
Allows multiple stages or tasks to run concurrently:
```groovy
parallel {
  stage('A') { ... }
  stage('B') { ... }
}
```

---

### ✅ 37. What is Jenkins CLI?
A command-line tool to interact with Jenkins server:
```bash
java -jar jenkins-cli.jar
```

---

### ✅ 38. What is the `when` directive in Declarative Pipeline?
Defines conditions to control stage execution.

---

### ✅ 39. How do you archive artifacts?
Use:
```groovy
archiveArtifacts artifacts: '**/target/*.jar'
```

---

### ✅ 40. What is a build number in Jenkins?
A unique ID assigned to each job run (e.g., `#23`).

---

✅ Next: Intermediate Jenkins Questions  
Let me know when you're ready!
