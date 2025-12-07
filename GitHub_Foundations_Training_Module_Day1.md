# GitHub Foundations Training Module - Day 1

## Git Fundamentals and Repository Management

---

## Course Overview

Welcome to **Day 1** of the **GitHub Foundations** training course! This comprehensive 2-day program is designed for programmers and project leads who have minimal experience with Git and GitHub. Today, you'll learn the fundamentals of Git and how to work with GitHub repositories.

### Training Format

Each day is structured as follows:

- **Morning Session (4 hours)**: Lecture and demonstrations covering core concepts
- **Afternoon Session (4 hours)**: Hands-on activities and guided exercises

### Learning Objectives

By the end of Day 1, you will be able to:

- Use Git effectively for version control
- Navigate and utilize GitHub confidently
- Create and manage repositories
- Work with branches and pull requests
- Collaborate using basic GitHub workflows

---

## Prerequisites Checklist

Before starting, please ensure you have completed the following:

- [ ] **Git installed** (latest stable version) - Verify with: `git --version`
- [ ] **GitHub account created** (free account at github.com)
- [ ] **GitHub Desktop installed** (optional but recommended)
- [ ] **Code editor installed** (VS Code recommended)
- [ ] **Command line access** (Terminal on Mac/Linux, Git Bash on Windows)
- [ ] **Git configured** with your name and email:
  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "your.email@example.com"
  ```

---

## Day 1: Git Fundamentals and Repository Management

### Morning Session: Core Concepts (4 hours)

---

## Domain 1: Introduction to Git and GitHub

### Topic 1.1: Understanding Git and Version Control

**What is Git?**
Git is a distributed version control system that tracks changes in your code over time. Think of it as a time machine for your code that allows you to:

- Save snapshots of your work at any point
- Track who made what changes and when
- Revert to previous versions if something breaks
- Work on multiple features simultaneously without conflicts

**Why Use Git?**

- **Collaboration**: Multiple people can work on the same project without overwriting each other's work
- **History**: Every change is tracked, so you can see what happened and why
- **Safety**: Easy to undo mistakes and experiment without fear
- **Branching**: Work on features in isolation before merging them

**Key Terminology:**

- **Repository (repo)**: A folder containing your project and its version history
- **Commit**: A snapshot of your code at a specific point in time
- **Branch**: A parallel version of your code where you can make changes
- **Merge**: Combining changes from different branches
- **Local vs Remote**: Local is on your computer, remote is on GitHub's servers

**The Basic Git Workflow:**

1. **Modify** files in your working directory
2. **Stage** changes (tell Git which files to include)
3. **Commit** changes (save a snapshot with a message)
4. **Push** to remote (upload to GitHub)

#### Example 1.1: Visualizing Git Workflow

Imagine you're working on a simple web page project:

```
Day 1: Initial commit
├── index.html (created)
└── style.css (created)
Commit message: "Initial project setup"

Day 2: Added navigation
├── index.html (modified - added nav bar)
└── style.css (modified - added nav styles)
Commit message: "Add navigation bar"

Day 3: Created about page
├── index.html (unchanged)
├── style.css (unchanged)
└── about.html (new file)
Commit message: "Add about page"
```

Each commit creates a snapshot you can return to. If the navigation breaks something, you can revert to Day 1's version.

**Command Example:**

```bash
# Check the status of your repository
git status

# See the commit history
git log --oneline

# Output might look like:
# a1b2c3d Add about page
# e4f5g6h Add navigation bar
# i7j8k9l Initial project setup
```

#### Activity 1.1: Your First Git Repository (15 minutes)

**Objective**: Create a local Git repository and make your first commit.

**Steps:**

1. Open your terminal/command line
2. Create a new directory for practice:
   ```bash
   mkdir my-first-repo
   cd my-first-repo
   ```
3. Initialize a Git repository:
   ```bash
   git init
   ```
4. Create a simple text file:
   ```bash
   echo "# My First Project" > README.md
   ```
5. Check the status:
   ```bash
   git status
   ```
   You should see `README.md` listed as an untracked file.
6. Stage the file:
   ```bash
   git add README.md
   ```
7. Make your first commit:
   ```bash
   git commit -m "Initial commit: Add README"
   ```
8. View your commit history:
   ```bash
   git log
   ```

**Checkpoint**: You should see your commit in the log with your name, email, and commit message.

---

### Topic 1.2: Working with Git Commands

**Essential Git Commands:**

1. **`git init`**: Initialize a new repository
2. **`git clone <url>`**: Copy an existing repository from GitHub
3. **`git add <file>`**: Stage files for commit
4. **`git commit -m "message"**: Save changes with a descriptive message
5. **`git status`**: See what files have changed
6. **`git log`**: View commit history
7. **`git push`**: Upload commits to GitHub
8. **`git pull`**: Download changes from GitHub
9. **`git branch`**: List, create, or delete branches
10. **`git checkout`** or **`git switch`**: Switch between branches

**Understanding the Three States:**

- **Working Directory**: Files you're currently editing
- **Staging Area**: Files you've marked to be included in the next commit
- **Repository**: Committed snapshots stored in Git

#### Example 1.2: Complete Workflow Demonstration

Let's walk through a complete workflow for adding a feature:

```bash
# 1. Check current status
git status
# Output: "nothing to commit, working tree clean"

# 2. Create a new feature file
echo "function calculateTotal() { return 0; }" > calculator.js

# 3. Check status again
git status
# Output: calculator.js is untracked

# 4. Stage the file
git add calculator.js

# 5. Check status
git status
# Output: calculator.js is staged (green)

# 6. Commit with a descriptive message
git commit -m "Add calculator function skeleton"

# 7. Modify the file
echo "function calculateTotal(items) {
  return items.reduce((sum, item) => sum + item.price, 0);
}" > calculator.js

# 8. Stage and commit the update
git add calculator.js
git commit -m "Implement calculateTotal function with reduce"

# 9. View history
git log --oneline
# Output:
# b2c3d4e Implement calculateTotal function with reduce
# a1b2c3d Add calculator function skeleton
```

**Best Practices:**

- Write clear, descriptive commit messages
- Commit often (small, logical changes)
- Use present tense in commit messages ("Add feature" not "Added feature")

#### Activity 1.2: Practice Git Workflow (20 minutes)

**Objective**: Practice the complete Git workflow with multiple commits.

**Scenario**: You're building a simple to-do list application.

**Steps:**

1. In your `my-first-repo` directory, create a file structure:

   ```bash
   echo "// To-do list app" > app.js
   echo "body { font-family: Arial; }" > styles.css
   ```

2. Stage and commit these files:

   ```bash
   git add app.js styles.css
   git commit -m "Add initial app files"
   ```

3. Modify `app.js` to add a function:

   ```bash
   echo "// To-do list app
   function addTodo(task) {
     console.log('Adding:', task);
   }" > app.js
   ```

4. Commit the change:

   ```bash
   git add app.js
   git commit -m "Add addTodo function"
   ```

5. View your commit history:

   ```bash
   git log --oneline --graph
   ```

6. Check what files have changed since the last commit:
   ```bash
   git status
   ```

**Deliverable**: You should have at least 3 commits in your repository.

---

### Topic 1.3: Understanding Branches and Merging

**What are Branches?**
Branches allow you to work on different features or experiments without affecting the main codebase. Think of branches as parallel universes for your code.

**Common Branching Strategy:**

- **main/master**: The production-ready code
- **feature/**: New features being developed
- **bugfix/**: Fixes for bugs
- **hotfix/**: Urgent production fixes

**Branch Workflow:**

1. Create a new branch from main
2. Make changes on the branch
3. Commit changes to the branch
4. Merge the branch back to main when complete

#### Example 1.3: Branching Scenario

Imagine you're working on a website and want to add a login feature:

```bash
# Start on main branch
git branch
# Output: * main

# Create a new branch for the login feature
git checkout -b feature/login
# or: git switch -c feature/login

# Make changes
echo "function login(username, password) { ... }" > auth.js
git add auth.js
git commit -m "Add login function"

# Continue working on the feature
echo "function logout() { ... }" >> auth.js
git add auth.js
git commit -m "Add logout function"

# Switch back to main
git checkout main

# Merge the feature branch
git merge feature/login

# Delete the feature branch (optional)
git branch -d feature/login
```

**Visual Representation:**

```
main:     A---B---C-----------F (merge)
                \           /
feature/login:   D---E------
```

#### Activity 1.3: Working with Branches (25 minutes)

**Objective**: Create branches, make changes, and merge them.

**Steps:**

1. Ensure you're on the main branch:

   ```bash
   git checkout main
   ```

2. Create a new branch for a feature:

   ```bash
   git checkout -b feature/user-profile
   ```

3. Create a new file on this branch:

   ```bash
   echo "class UserProfile { constructor(name) { this.name = name; } }" > user-profile.js
   ```

4. Commit the change:

   ```bash
   git add user-profile.js
   git commit -m "Add UserProfile class"
   ```

5. Switch back to main:

   ```bash
   git checkout main
   ```

6. Verify the file doesn't exist on main:

   ```bash
   ls
   # user-profile.js should not be here
   ```

7. Merge the feature branch:

   ```bash
   git merge feature/user-profile
   ```

8. Verify the file now exists on main:

   ```bash
   ls
   # user-profile.js should now be here
   ```

9. View branch structure:
   ```bash
   git log --oneline --graph --all
   ```

**Checkpoint**: You should see a merge commit in your history showing the branch was merged.

---

### Topic 1.4: Navigating GitHub

**What is GitHub?**
GitHub is a cloud-based platform that hosts Git repositories. It provides:

- Remote storage for your code
- Web interface for viewing and managing repositories
- Collaboration tools (Issues, Pull Requests, Discussions)
- Project management features
- CI/CD automation

**Key GitHub Concepts:**

- **Repository**: A project on GitHub
- **Issue**: A way to track bugs, tasks, or feature requests
- **Pull Request (PR)**: A proposal to merge changes into a repository
- **Fork**: Your own copy of someone else's repository
- **Star**: Bookmark repositories you find interesting

#### Example 1.4: GitHub Interface Tour

**Main Repository Page Elements:**

1. **Code tab**: View files and folders
2. **Issues tab**: Track bugs and feature requests
3. **Pull requests tab**: Review and merge changes
4. **Actions tab**: View CI/CD workflows
5. **Settings tab**: Configure repository options

**Creating a Repository on GitHub:**

1. Click the "+" icon → "New repository"
2. Name your repository (e.g., "my-first-project")
3. Choose visibility (Public or Private)
4. Initialize with README (optional)
5. Click "Create repository"

**Connecting Local Repository to GitHub:**

```bash
# After creating a repo on GitHub, connect your local repo:
git remote add origin https://github.com/yourusername/my-first-project.git
git branch -M main
git push -u origin main
```

#### Activity 1.4: Create and Connect Your First GitHub Repository (20 minutes)

**Objective**: Create a GitHub repository and push your local code to it.

**Steps:**

1. Go to github.com and sign in
2. Click the "+" icon in the top right → "New repository"
3. Name it: `github-training-practice`
4. Description: "Practice repository for GitHub Foundations training"
5. Choose **Private** (for now)
6. **Do NOT** initialize with README, .gitignore, or license
7. Click "Create repository"

8. In your terminal, navigate to your `my-first-repo` directory

9. Add the remote repository:

   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/github-training-practice.git
   ```

   (Replace YOUR_USERNAME with your actual GitHub username)

10. Rename your branch to main (if needed):

    ```bash
    git branch -M main
    ```

11. Push your code to GitHub:

    ```bash
    git push -u origin main
    ```

12. Refresh your GitHub repository page - you should see all your files!

**Checkpoint**: Your local repository should now be visible on GitHub with all your commits.

---

### Topic 1.5: GitHub Issues and Pull Requests

**GitHub Issues:**
Issues are used to track:

- Bug reports
- Feature requests
- Tasks
- Questions or discussions

**Pull Requests:**
Pull Requests (PRs) are the way to propose changes to a repository:

1. Create a branch with your changes
2. Push the branch to GitHub
3. Open a Pull Request
4. Review and discuss the changes
5. Merge when approved

#### Example 1.5: Creating Your First Pull Request

**Scenario**: You want to add a README file to your repository.

```bash
# 1. Create a new branch
git checkout -b add-readme

# 2. Create a README file
echo "# My Project
This is a description of my project.
## Features
- Feature 1
- Feature 2" > README.md

# 3. Commit the change
git add README.md
git commit -m "Add comprehensive README"

# 4. Push the branch to GitHub
git push -u origin add-readme
```

**On GitHub:**

1. You'll see a banner suggesting to create a Pull Request
2. Click "Compare & pull request"
3. Add a title and description
4. Click "Create pull request"
5. Review the changes in the "Files changed" tab
6. Click "Merge pull request" when ready
7. Delete the branch after merging

#### Activity 1.5: Create an Issue and Pull Request (25 minutes)

**Objective**: Practice the GitHub collaboration workflow.

**Steps:**

1. On your GitHub repository, go to the "Issues" tab
2. Click "New issue"
3. Create an issue titled: "Add documentation for setup"
4. Add a description: "We need instructions on how to set up and run this project locally."
5. Click "Submit new issue"

6. In your terminal, create a branch to address this issue:

   ```bash
   git checkout -b docs/setup-instructions
   ```

7. Create a SETUP.md file:

   ```bash
   echo "# Setup Instructions

   ## Prerequisites
   - Node.js installed
   - Git installed

   ## Installation
   1. Clone the repository
   2. Run npm install
   3. Start the application

   ## Usage
   Run the app with: npm start" > SETUP.md
   ```

8. Commit and push:

   ```bash
   git add SETUP.md
   git commit -m "Add setup instructions (closes #1)"
   git push -u origin docs/setup-instructions
   ```

9. On GitHub, create a Pull Request:

   - Title: "Add setup instructions"
   - Description: "This PR adds setup instructions as requested in #1"
   - Link the issue by typing "#1" in the description

10. Review your PR and merge it

**Checkpoint**: Your issue should be automatically closed when the PR is merged.

---

## Domain 2: Working with GitHub Repositories

### Topic 2.1: Managing Repository Settings

**Key Repository Settings:**

- **General**: Name, description, visibility
- **Access**: Collaborators and permissions
- **Branches**: Default branch, branch protection
- **Features**: Issues, Projects, Wiki, Discussions
- **Security**: Security policy, dependency graph
- **Actions**: GitHub Actions settings
- **Pages**: GitHub Pages configuration

**Repository Visibility:**

- **Public**: Anyone can view
- **Private**: Only collaborators can view

**Permissions:**

- **Read**: Can view and clone
- **Write**: Can push changes
- **Admin**: Full control including settings

#### Example 2.1: Configuring Repository Settings

**Setting up a repository for team collaboration:**

1. **Enable Features:**

   - Go to Settings → General
   - Enable Issues, Projects, Wiki (as needed)

2. **Add Collaborators:**

   - Settings → Collaborators
   - Add team members with appropriate permissions

3. **Configure Default Branch:**

   - Settings → Branches
   - Set default branch (usually `main`)

4. **Add Topics:**

   - On the main repository page
   - Click the gear icon next to "About"
   - Add topics like: `javascript`, `web-development`, `training`

5. **Add Description:**
   - Update the repository description
   - Add a website URL if applicable

#### Activity 2.1: Configure Your Repository (15 minutes)

**Objective**: Set up your repository with proper settings.

**Steps:**

1. Go to your repository on GitHub
2. Click "Settings"
3. In "General" settings:
   - Add a description: "Training repository for GitHub Foundations course"
   - Add topics: `training`, `git`, `github`
4. Scroll to "Features" section:
   - Ensure Issues are enabled
   - Enable Projects
5. Go to "Collaborators" (if you have team members):
   - Add a collaborator with Write access
6. Go back to the main repository page
7. Verify your changes are visible

**Checkpoint**: Your repository should have a description and topics visible on the main page.

---

### Topic 2.2: Working with Files in a Repository

**File Operations:**

- **Add**: Create new files via web interface or locally
- **Edit**: Modify existing files
- **Delete**: Remove files
- **Rename**: Change file names (GitHub tracks this as delete + add)

**File Versioning:**
Every change to a file creates a new version. You can:

- View file history
- Compare versions
- Revert to previous versions
- See who made what changes (blame view)

#### Example 2.2: File Management Workflow

**Adding a file via GitHub web interface:**

1. Click "Add file" → "Create new file"
2. Name the file (e.g., `config.json`)
3. Add content:
   ```json
   {
     "appName": "My App",
     "version": "1.0.0"
   }
   ```
4. Scroll down to "Commit new file"
5. Write commit message: "Add configuration file"
6. Choose "Commit directly to the main branch"
7. Click "Commit new file"

**Editing a file:**

1. Click on the file name
2. Click the pencil icon (✏️)
3. Make your changes
4. Commit with a descriptive message

**Viewing file history:**

1. Click on a file
2. Click "History" button
3. See all commits that modified this file
4. Click any commit to see what changed

#### Activity 2.2: File Management Practice (20 minutes)

**Objective**: Practice adding, editing, and managing files.

**Steps:**

1. **Add a file via GitHub web interface:**

   - Create `package.json` with:
     ```json
     {
       "name": "github-training-practice",
       "version": "1.0.0",
       "description": "Practice repository"
     }
     ```
   - Commit with message: "Add package.json"

2. **Edit the file:**

   - Open `package.json`
   - Click the pencil icon
   - Add a "scripts" section:
     ```json
     "scripts": {
       "start": "node app.js"
     }
     ```
   - Commit: "Add start script"

3. **Clone the repository locally** (if you haven't already):

   ```bash
   cd ~
   git clone https://github.com/YOUR_USERNAME/github-training-practice.git
   cd github-training-practice
   ```

4. **Make a local change:**

   - Edit `package.json` locally
   - Add: `"author": "Your Name"`
   - Commit and push:

   ```bash
     git add package.json
     git commit -m "Add author field"
     git push
   ```

5. **View file history on GitHub:**
   - Click on `package.json`
   - Click "History"
   - You should see all three commits

**Checkpoint**: You should have made changes both via web interface and locally, and see them in the history.

---

### Topic 2.3: Using GitHub Desktop (Optional)

**GitHub Desktop Benefits:**

- Visual interface for Git operations
- Easier for beginners
- See changes before committing
- Visual branch management
- Built-in diff viewer

**Key Features:**

- Repository management
- Branch visualization
- Commit history
- Conflict resolution
- Push/pull operations

#### Example 2.3: GitHub Desktop Workflow

**Making a commit in GitHub Desktop:**

1. Open GitHub Desktop
2. Select your repository
3. Make changes to files
4. GitHub Desktop shows changed files in the left panel
5. Select files to stage
6. Write commit message
7. Click "Commit to main"
8. Click "Push origin" to upload

**Creating a branch:**

1. Click "Current branch" dropdown
2. Click "New branch"
3. Name it (e.g., `feature/new-ui`)
4. Make changes
5. Commit and push
6. Create Pull Request from the app

#### Activity 2.3: Try GitHub Desktop (15 minutes)

**Objective**: Get familiar with GitHub Desktop interface.

**Steps:**

1. Open GitHub Desktop
2. Add your repository:
   - File → Add Local Repository
   - Or: File → Clone Repository (from GitHub)
3. Make a small change to a file
4. Observe how GitHub Desktop shows the diff
5. Stage the change
6. Write a commit message
7. Commit the change
8. Push to GitHub
9. Verify the change appears on GitHub

**Note**: This is optional - you can continue using command line if preferred.

---

## Day 1 Afternoon: Hands-On Activities

### Activity Session Overview

The afternoon session focuses on practical application of the morning's concepts. Work through these activities at your own pace, but aim to complete all of them.

---

### Activity A: Complete Project Setup (45 minutes)

**Objective**: Set up a complete project with proper Git workflow.

**Scenario**: You're starting a new project for a simple blog application.

**Tasks:**

1. Create a new repository on GitHub called `blog-app`
2. Clone it locally
3. Create the following file structure:
   ```
   blog-app/
   ├── index.html
   ├── styles.css
   ├── app.js
   └── README.md
   ```
4. Make initial commit with all files
5. Create a `feature/articles` branch
6. Add an `articles.html` file on the branch
7. Commit and push the branch
8. Create a Pull Request on GitHub
9. Merge the Pull Request
10. Pull the changes locally to update your main branch

**Deliverables:**

- Repository with proper structure
- At least 2 branches created
- 1 Pull Request created and merged
- Clean commit history

---

### Activity B: Branching and Merging Practice (60 minutes)

**Objective**: Master branching workflows.

**Scenario**: You need to work on multiple features simultaneously.

**Tasks:**

1. Start from your `blog-app` repository
2. Create three feature branches:
   - `feature/user-authentication`
   - `feature/comment-system`
   - `feature/search-functionality`
3. On each branch, create a corresponding file:
   - `auth.js` on the auth branch
   - `comments.js` on the comments branch
   - `search.js` on the search branch
4. Make at least 2 commits on each branch
5. Merge `feature/user-authentication` into main
6. Create a Pull Request for `feature/comment-system`
7. Resolve a merge conflict (intentionally create one):
   - Modify the same line in `index.html` on both main and `feature/search-functionality`
   - Attempt to merge and resolve the conflict
8. Delete merged branches

**Deliverables:**

- Multiple branches with commits
- Successful merge
- Resolved merge conflict
- Clean branch structure

---

### Activity C: Issue and PR Workflow (45 minutes)

**Objective**: Practice the complete collaboration workflow.

**Tasks:**

1. Create 3 issues in your repository:
   - "Add error handling"
   - "Improve styling"
   - "Add unit tests"
2. For each issue, create a branch and address it:
   - Branch name should reference the issue (e.g., `fix/add-error-handling`)
   - Make changes to address the issue
   - Commit with message that references the issue (e.g., "Add error handling, closes #1")
3. Create Pull Requests for each branch
4. Review your own PRs (check the "Files changed" tab)
5. Merge all PRs
6. Verify issues are automatically closed

**Deliverables:**

- 3 issues created
- 3 Pull Requests created and merged
- All issues automatically closed
- Clean commit messages referencing issues

---

### Activity D: Repository Management (30 minutes)

**Objective**: Configure and manage repository settings.

**Tasks:**

1. Update repository settings:
   - Add a detailed description
   - Add relevant topics (at least 5)
   - Enable Wiki (if available)
   - Set up a repository template (if applicable)
2. Create a `.gitignore` file:
   - Add common patterns (node_modules, .env, etc.)
3. Add a LICENSE file (choose MIT or Apache 2.0)
4. Create a CONTRIBUTING.md file with contribution guidelines
5. Set up branch protection (if you have admin access):
   - Require pull request reviews
   - Require status checks to pass

**Deliverables:**

- Fully configured repository
- Proper `.gitignore` file
- LICENSE and CONTRIBUTING files
- Branch protection rules (if applicable)

---

### Day 1 Wrap-Up

**Review Questions:**

1. What is the difference between `git add` and `git commit`?
2. How do branches help in collaborative development?
3. What is the purpose of a Pull Request?
4. When would you use `git pull` vs `git push`?

**Key Takeaways:**

- Git tracks changes through commits
- Branches enable parallel development
- GitHub provides collaboration tools
- Pull Requests enable code review before merging

**Preparation for Day 2:**

- Ensure your GitHub account is set up
- Have at least one repository with multiple branches
- Be ready to work with collaborators

---

_End of Day 1 Training Module_
