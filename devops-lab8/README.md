# Hello World Jenkins Job

## Objective
Create and execute a Jenkins Freestyle project that retrieves a shell script from GitHub and prints `Hello, Jenkins!` in the build console.

## Prerequisites
- Jenkins
- Git
- GitHub account
- A public GitHub repository

## Repository
- **Repository:** [devops-lab8](https://github.com/harshithhraya/devops-lab8)
- **Script:** `hello-world.sh`
- **Jenkins Job:** `HelloWorld`

## Step 1: Create the Shell Script

Create a file named `hello-world.sh` in the GitHub repository with the following content:

```bash
#!/bin/bash
echo "Hello, Jenkins!"
```

Commit the file to the `main` branch.

## Step 2: Create a Jenkins Job

1. Open Jenkins at `http://localhost:8080`.
2. Click **New Item**.
3. Enter `HelloWorld` as the job name.
4. Select **Freestyle project**.
5. Click **OK**.

## Step 3: Configure Source Code Management

1. Open **Source Code Management**.
2. Select **Git**.
3. Enter the repository URL:

   `https://github.com/harshithhraya/devops-lab8.git`

4. Configure the branch specifier as `*/main`.
5. Leave credentials as none because the repository is public.

## Step 4: Configure the Build Step

1. Navigate to **Build Steps**.
2. Select **Add build step → Execute shell**.
3. Enter the command:

```bash
echo "Hello, Jenkins!"
```

4. Click **Save**.

## Step 5: Execute the Job

1. Open the `HelloWorld` job.
2. Click **Build Now**.
3. Open build `#1`.
4. Click **Console Output**.

## Step 6: Verify the Result

The successful console output includes:

```text
Hello, Jenkins!
Finished: SUCCESS
```

**Result:** The Jenkins Freestyle project successfully cloned the GitHub repository and executed the shell command.

## What I Learned

- Creating Jenkins Freestyle projects
- Integrating Jenkins with GitHub
- Configuring Git source code management
- Executing shell commands through Jenkins
- Inspecting build logs and verifying build status
