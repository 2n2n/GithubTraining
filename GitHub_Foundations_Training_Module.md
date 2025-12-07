# GitHub Foundations Training Module

## 2-Day Comprehensive Training Course

---

## Course Overview

Welcome to the **GitHub Foundations** training course! This comprehensive 2-day program is designed for programmers and project leads who have minimal experience with Git and GitHub. Over the next two days, you'll learn everything you need to confidently use Git and GitHub in your daily work.

### Training Format

Each day is structured as follows:

- **Morning Session (4 hours)**: Lecture and demonstrations covering core concepts
- **Afternoon Session (4 hours)**: Hands-on activities and guided exercises

### Learning Objectives

By the end of this course, you will be able to:

- Use Git effectively for version control
- Navigate and utilize GitHub confidently
- Collaborate in real-world workflows
- Apply DevOps and CI/CD foundations
- Manage privacy, security, and organization settings
- Engage with the GitHub community

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
   git merge feature/login
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

````

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
````

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

## Day 2: Collaboration, DevOps, and Advanced Features

### Morning Session: Advanced Concepts (4 hours)

---

## Domain 3: Collaboration Features

### Topic 3.1: Forking Repositories

**What is Forking?**
Forking creates your own copy of someone else's repository. This allows you to:

- Experiment without affecting the original
- Contribute to open-source projects
- Use others' projects as a starting point

**Fork vs Clone:**

- **Clone**: Copy to your local machine (you need access)
- **Fork**: Copy to your GitHub account (creates your own version)

**Fork Workflow:**

1. Fork the repository on GitHub
2. Clone your fork locally
3. Make changes
4. Push to your fork
5. Create a Pull Request to the original repository

#### Example 3.1: Forking and Contributing

**Scenario**: You want to contribute to an open-source project.

```bash
# 1. Fork the repository on GitHub (click "Fork" button)

# 2. Clone YOUR fork (not the original)
git clone https://github.com/YOUR_USERNAME/original-repo.git
cd original-repo

# 3. Add the original as "upstream" to stay updated
git remote add upstream https://github.com/ORIGINAL_OWNER/original-repo.git

# 4. Create a branch for your contribution
git checkout -b fix/typo-in-readme

# 5. Make your changes
# ... edit files ...

# 6. Commit and push to YOUR fork
git add .
git commit -m "Fix typo in README"
git push -u origin fix/typo-in-readme

# 7. On GitHub, create a Pull Request to the original repository
```

#### Activity 3.1: Fork and Contribute (30 minutes)

**Objective**: Practice the fork workflow.

**Steps:**

1. Find a simple open-source repository (or use a colleague's)
2. Fork the repository
3. Clone your fork locally
4. Add the original as upstream:
   ```bash
   git remote add upstream <original-repo-url>
   ```
5. Create a branch for improvements
6. Make a small improvement (fix a typo, improve documentation)
7. Commit and push to your fork
8. Create a Pull Request to the original repository
9. Verify you can see your PR in the original repo

**Checkpoint**: You should have a Pull Request open to the original repository.

---

### Topic 3.2: Creating and Managing Pull Requests

**Pull Request Best Practices:**

- **Clear title**: Describe what the PR does
- **Detailed description**: Explain why and how
- **Link issues**: Reference related issues
- **Small changes**: Keep PRs focused and reviewable
- **Request reviews**: Ask specific people to review

**PR Review Process:**

1. **Draft PR**: Work in progress (optional)
2. **Open for review**: Ready for feedback
3. **Address feedback**: Make requested changes
4. **Approve**: Reviewer approves the changes
5. **Merge**: Combine into target branch

**Merge Options:**

- **Merge commit**: Creates a merge commit
- **Squash and merge**: Combines all commits into one
- **Rebase and merge**: Replays commits on top of target branch

#### Example 3.2: Professional Pull Request

**Good PR Title:**

```
Add user authentication with JWT tokens
```

**Good PR Description:**

```markdown
## Description

This PR adds JWT-based authentication to the application.

## Changes

- Added `auth.js` module with login/logout functions
- Integrated JWT token storage
- Added protected route middleware

## Related Issues

Closes #42
Related to #35

## Testing

- [x] Unit tests pass
- [x] Manual testing completed
- [x] No breaking changes

## Screenshots

[Add screenshots if UI changes]
```

**Review Checklist:**

- Code follows project style
- Tests are included
- Documentation is updated
- No breaking changes

#### Activity 3.2: Create a Professional PR (25 minutes)

**Objective**: Practice creating well-documented Pull Requests.

**Steps:**

1. Create a new feature branch: `feature/api-endpoints`
2. Add a new file: `api.js` with some API functions
3. Update README.md to document the new API
4. Commit your changes:

```bash
   git add api.js README.md
   git commit -m "Add API endpoints module"
```

5. Push the branch
6. Create a Pull Request with:
   - Clear, descriptive title
   - Detailed description explaining:
     - What you added
     - Why it's needed
     - How to test it
   - Checklist of completed items
7. Request a review (if you have collaborators)
8. Make a small change based on feedback (or simulate it)
9. Push the update to the same branch
10. Verify the PR updates automatically

**Checkpoint**: Your PR should have a professional description and be ready for review.

---

### Topic 3.3: Reviewing and Merging Pull Requests

**Code Review Best Practices:**

- Be constructive and respectful
- Explain the "why" behind suggestions
- Approve when satisfied
- Request changes when needed
- Test the changes locally if possible

**Review Tools:**

- **Line comments**: Comment on specific lines
- **File comments**: General feedback on a file
- **Review summary**: Overall approval or changes requested
- **Suggest changes**: Propose specific code changes

#### Example 3.3: Conducting a Code Review

**Review Process:**

1. Open the Pull Request
2. Review the "Files changed" tab
3. Add line comments on specific code:
   ```javascript
   // Suggestion: Consider adding error handling here
   function fetchData() {
     return fetch(url); // ← Add comment here
   }
   ```
4. Add a general comment:
   ```markdown
   Overall, this looks good! A few suggestions:

   - Add error handling for the API call
   - Consider extracting the URL to a constant
   - Add unit tests for the new function
   ```
5. Submit review with:
   - **Comment**: General feedback
   - **Approve**: Ready to merge
   - **Request changes**: Needs work

**Merging a PR:**

1. Ensure all checks pass
2. Ensure at least one approval (if required)
3. Click "Merge pull request"
4. Choose merge type:
   - **Create a merge commit**: Preserves full history
   - **Squash and merge**: Single commit (cleaner history)
   - **Rebase and merge**: Linear history
5. Confirm merge
6. Delete the branch (recommended)

#### Activity 3.3: Practice Code Review (20 minutes)

**Objective**: Learn to review Pull Requests effectively.

**Steps:**

1. Create a Pull Request with intentionally imperfect code:
   - Add a function with no error handling
   - Use unclear variable names
   - Miss some edge cases
2. Switch to a different browser/account (or ask a colleague)
3. Review the PR:
   - Add at least 3 line comments with suggestions
   - Add a general review comment
   - Request changes
4. Switch back and address the feedback:
   - Make the suggested improvements
   - Push updates to the branch
5. Mark comments as resolved
6. Request another review
7. Get approval and merge

**Checkpoint**: You should have practiced both giving and receiving code review feedback.

---

### Topic 3.4: Using GitHub for Project Management

**GitHub Issues:**

- Track bugs, features, and tasks
- Assign to team members
- Set labels and milestones
- Link to Pull Requests

**Labels:**
Organize issues with labels:

- `bug`: Something isn't working
- `enhancement`: New feature or request
- `documentation`: Documentation improvements
- `good first issue`: Good for newcomers
- `help wanted`: Extra attention needed

**Milestones:**
Group issues into milestones (versions, sprints):

- v1.0.0
- Q1 2024
- Sprint 1

**Projects:**
Visual boards for tracking work:

- Kanban-style boards
- Automatically sync with issues and PRs
- Customizable columns

#### Example 3.4: Setting Up Project Management

**Creating a Project Board:**

1. Go to repository → "Projects" tab
2. Click "New project"
3. Choose template: "Board" (Kanban)
4. Add columns:
   - To Do
   - In Progress
   - In Review
   - Done
5. Create issues and add them to the board
6. Move cards as work progresses

**Using Labels:**

1. Go to Issues → Labels
2. Create custom labels:
   - `priority: high`
   - `priority: low`
   - `component: frontend`
   - `component: backend`
3. Apply labels to issues

**Setting Up Milestones:**

1. Go to Issues → Milestones
2. Click "New milestone"
3. Name it: "v1.0 Release"
4. Set due date
5. Add issues to the milestone

#### Activity 3.4: Set Up Project Management (30 minutes)

**Objective**: Organize work using GitHub's project management tools.

**Steps:**

1. **Create Labels:**

   - Create at least 5 custom labels
   - Apply them to existing issues

2. **Create a Milestone:**

   - Name: "Training Project v1.0"
   - Add 3-5 issues to the milestone

3. **Create a Project Board:**

   - Create a new board
   - Add columns: Backlog, To Do, In Progress, Review, Done
   - Add all your issues to the board
   - Move at least 2 issues through the workflow

4. **Create Issue Templates:**
   - Go to Settings → Issues
   - Set up templates for:
     - Bug report
     - Feature request
   - Create one issue using each template

**Checkpoint**: You should have a functioning project board with organized issues.

---

## Domain 4: Modern Development

### Topic 4.1: Understanding DevOps Principles

**What is DevOps?**
DevOps combines Development and Operations to:

- Automate software delivery
- Improve collaboration
- Increase deployment frequency
- Reduce time to market

**Key Principles:**

- **Automation**: Automate repetitive tasks
- **Continuous Integration (CI)**: Merge code frequently
- **Continuous Deployment (CD)**: Automatically deploy to production
- **Monitoring**: Track application performance
- **Infrastructure as Code**: Manage infrastructure with code

**DevOps Benefits:**

- Faster releases
- Fewer errors
- Better collaboration
- Improved quality

#### Example 4.1: DevOps Workflow

**Traditional Workflow:**

```
Developer → Manual Testing → Deploy → Hope it works
```

**DevOps Workflow:**

```
Developer → Push Code → Automated Tests → Automated Build →
Automated Deployment → Monitoring → Feedback
```

**GitHub's Role:**

- **GitHub Actions**: Automate workflows
- **CI/CD Pipelines**: Test and deploy automatically
- **Environments**: Manage staging and production
- **Secrets**: Secure storage for credentials

#### Activity 4.1: DevOps Concepts Discussion (15 minutes)

**Objective**: Understand how DevOps applies to your work.

**Discussion Questions:**

1. What manual processes in your current workflow could be automated?
2. How often do you deploy code? Could it be more frequent?
3. What happens when code is pushed? Is it tested automatically?
4. How do you track if deployments are successful?

**Reflection:**
Write down 3 ways DevOps principles could improve your current workflow.

---

### Topic 4.2: GitHub Actions for Automation

**What are GitHub Actions?**
GitHub Actions automate workflows directly in your repository:

- Run tests on every push
- Deploy applications
- Send notifications
- Generate documentation
- And much more!

**Key Concepts:**

- **Workflow**: Automated process (defined in YAML)
- **Event**: What triggers the workflow (push, PR, etc.)
- **Job**: Set of steps that run on the same runner
- **Step**: Individual task in a job
- **Action**: Reusable unit of work

**Workflow File Location:**
`.github/workflows/` directory in your repository

#### Example 4.2: Your First GitHub Action

**Simple workflow to run tests:**

Create `.github/workflows/test.yml`:

```yaml
name: Run Tests

# When to run
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

# What to do
jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: "18"

      - name: Install dependencies
        run: npm install

      - name: Run tests
        run: npm test
```

**What this does:**

1. Triggers on push or PR to main
2. Checks out your code
3. Sets up Node.js
4. Installs dependencies
5. Runs tests

#### Activity 4.2: Create Your First GitHub Action (30 minutes)

**Objective**: Set up automated testing with GitHub Actions.

**Steps:**

1. Create the workflows directory:

```bash
mkdir -p .github/workflows
```

2. Create a test workflow file: `.github/workflows/test.yml`

```yaml
   name: CI Tests

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v3

    - name: Setup Node.js
      uses: actions/setup-node@v3
      with:
        node-version: '18'

    - name: Install dependencies
      run: npm install

    - name: Run tests
         run: npm test || echo "No tests yet"
```

3. Commit and push:

```bash
   git add .github/workflows/test.yml
git commit -m "Add CI workflow"
git push
```

4. Go to GitHub → Actions tab
5. Watch your workflow run
6. Check the results

**Checkpoint**: You should see a workflow run in the Actions tab (it may show as failed if there are no tests, which is okay).

---

### Topic 4.3: Building CI/CD Pipelines

**CI/CD Pipeline Stages:**

1. **Build**: Compile/package your application
2. **Test**: Run automated tests
3. **Deploy**: Deploy to staging/production

**Common Pipeline:**

```yaml
Build → Test → Lint → Security Scan → Deploy Staging →
Deploy Production
```

#### Example 4.3: Complete CI/CD Pipeline

**Advanced workflow with multiple jobs:**

```yaml
name: CI/CD Pipeline

on:
  push:
    branches: [ main ]
pull_request:
 branches: [ main ]

jobs:
# Job 1: Run tests
test:
    runs-on: ubuntu-latest
    steps:
   - uses: actions/checkout@v3
   - uses: actions/setup-node@v3
     with:
       node-version: '18'
   - run: npm install
   - run: npm test
   - run: npm run lint

# Job 2: Build application
build:
 runs-on: ubuntu-latest
 needs: test
 steps:
   - uses: actions/checkout@v3
   - uses: actions/setup-node@v3
     with:
       node-version: '18'
   - run: npm install
   - run: npm run build
   - uses: actions/upload-artifact@v3
     with:
       name: dist
       path: dist/

# Job 3: Deploy (only on main branch)
deploy:
 runs-on: ubuntu-latest
 needs: build
 if: github.ref == 'refs/heads/main'
 steps:
   - uses: actions/download-artifact@v3
     with:
       name: dist
   - name: Deploy to production
     run: echo "Deploying to production..."
     # Add your deployment commands here
```

**Pipeline Flow:**

- Tests run first
- Build only runs if tests pass
- Deploy only runs on main branch after build succeeds

#### Activity 4.3: Build a CI/CD Pipeline (40 minutes)

**Objective**: Create a multi-stage CI/CD pipeline.

**Steps:**

1. Create a more complex workflow: `.github/workflows/cicd.yml`

2. Set up multiple jobs:

   - **Lint job**: Check code style
   - **Test job**: Run tests
   - **Build job**: Build the application (depends on test)
   - **Deploy job**: Deploy (only on main, depends on build)

3. Add a simple build script to `package.json`:

   ```json
   "scripts": {
     "build": "echo 'Building...' && mkdir -p dist && echo 'Build complete' > dist/build.txt",
     "lint": "echo 'Linting...' || true",
     "test": "echo 'Running tests...' || true"
   }
   ```

4. Commit and push:

   ```bash
   git add .github/workflows/cicd.yml package.json
   git commit -m "Add CI/CD pipeline"
   git push
   ```

5. Create a Pull Request to trigger the workflow
6. Observe the pipeline running
7. Check that jobs run in the correct order
8. Merge the PR and see deploy job run

**Checkpoint**: You should have a working pipeline with multiple jobs that run in sequence.

---

### Topic 4.4: Code Review Best Practices

**Why Code Reviews Matter:**

- Catch bugs before production
- Share knowledge
- Maintain code quality
- Ensure consistency

**Review Checklist:**

- [ ] Code follows project style guide
- [ ] Logic is correct and efficient
- [ ] Error handling is present
- [ ] Tests are included
- [ ] Documentation is updated
- [ ] No security vulnerabilities
- [ ] Performance considerations addressed

**Giving Good Feedback:**

- Be specific and constructive
- Explain the "why"
- Suggest solutions, don't just point out problems
- Acknowledge good work
- Ask questions when unclear

#### Example 4.4: Effective Code Review

**Poor Review Comment:**

```
This is wrong.
```

**Good Review Comment:**

```
Consider adding error handling here. If the API call fails,
the application will crash. We could wrap this in a try-catch
block and show a user-friendly error message.

Example:
try {
  const data = await fetchData();
} catch (error) {
  showError('Failed to load data. Please try again.');
}
```

**Review Patterns:**

- **Praise**: "Great use of async/await here!"
- **Question**: "Could you explain why we're using this approach?"
- **Suggestion**: "Consider extracting this into a separate function for reusability."
- **Concern**: "This might cause a memory leak. Should we add cleanup?"

#### Activity 4.4: Practice Code Review (25 minutes)

**Objective**: Improve code review skills.

**Steps:**

1. Create a branch with intentionally problematic code:

   - Missing error handling
   - Poor variable names
   - Missing comments
   - No tests

2. Create a Pull Request

3. Review your own code as if you were a reviewer:

   - Add at least 5 constructive comments
   - Mix praise, questions, and suggestions
   - Be specific about improvements

4. Address the feedback:

   - Make the improvements
   - Push updates
   - Mark comments as resolved

5. Write a summary of what you learned

**Checkpoint**: You should have practiced both giving and receiving constructive feedback.

---

## Domain 5: Project Management

### Topic 5.1: Creating and Managing GitHub Projects

**GitHub Projects:**
Visual boards for organizing work:

- Kanban-style boards
- Table views
- Roadmap views
- Automatically sync with issues and PRs

**Project Types:**

- **Board**: Kanban-style columns
- **Table**: Spreadsheet-like view
- **Roadmap**: Timeline view (beta)

**Key Features:**

- Custom fields
- Filters and views
- Automation rules
- Integration with issues and PRs

#### Example 5.1: Setting Up a Project Board

**Creating a Kanban Board:**

1. Go to repository → Projects → New project
2. Choose "Board" template
3. Add columns:

   - **Backlog**: Ideas and future work
   - **To Do**: Ready to start
   - **In Progress**: Currently working
   - **In Review**: PRs open
   - **Done**: Completed work

4. Add issues to the board
5. Create custom fields:

   - Priority (High, Medium, Low)
   - Effort (Story points)
   - Status

6. Set up automation:
   - When issue is assigned → move to "In Progress"
   - When PR is opened → move to "In Review"
   - When PR is merged → move to "Done"

#### Activity 5.1: Create a Project Board (30 minutes)

**Objective**: Set up a functional project board.

**Steps:**

1. Create a new project board
2. Set up columns:

   - Backlog
   - To Do
   - In Progress
   - Review
   - Done

3. Add at least 5 issues to the board
4. Create custom fields:

   - Priority (dropdown)
   - Estimated Time (number)

5. Set up automation rules:

   - Auto-move issues when assigned
   - Auto-move when PR is created
   - Auto-move when PR is merged

6. Create different views:

   - "High Priority" view (filtered)
   - "My Work" view (assigned to you)

7. Move issues through the workflow
8. Verify automation works

**Checkpoint**: You should have a working project board with automation.

---

### Topic 5.2: Integrating Projects with Issues and PRs

**Integration Benefits:**

- Issues automatically appear on boards
- PRs link to issues
- Status updates automatically
- Track progress visually

**Workflow Integration:**

1. Create issue → Appears in "To Do"
2. Assign issue → Moves to "In Progress"
3. Create PR linked to issue → Moves to "Review"
4. Merge PR → Issue closes, moves to "Done"

#### Example 5.2: Integrated Workflow

**Complete workflow example:**

1. **Create Issue:**

   - Title: "Add user dashboard"
   - Assign to yourself
   - Add to project board
   - Automatically appears in "To Do"

2. **Start Work:**

   - Create branch: `feature/user-dashboard`
   - Issue automatically moves to "In Progress" (via automation)

3. **Create PR:**

   - Link PR to issue: "Closes #5"
   - PR appears in "Review" column

4. **Merge PR:**
   - Issue automatically closes
   - Card moves to "Done"
   - Progress tracked automatically

#### Activity 5.2: Practice Integrated Workflow (25 minutes)

**Objective**: Use issues, PRs, and projects together.

**Steps:**

1. Create 3 new issues in your repository
2. Add them all to your project board
3. For each issue:

   - Create a branch
   - Make a small change
   - Create a PR that closes the issue
   - Observe the board update automatically

4. Review one PR and add comments
5. Merge all PRs
6. Verify:
   - All issues are closed
   - All cards are in "Done"
   - Project shows correct progress

**Checkpoint**: Your project board should automatically reflect the status of all issues and PRs.

---

## Day 2 Afternoon: Security, Community, and Hands-On Activities

### Domain 6: Privacy, Security, and Administration

### Topic 6.1: Repository Security

**Security Best Practices:**

- Never commit secrets (API keys, passwords)
- Use branch protection rules
- Enable security features
- Regular dependency updates
- Code scanning

**Common Security Risks:**

- Exposed credentials
- Vulnerable dependencies
- Unprotected main branch
- Missing security policies

#### Example 6.1: Securing a Repository

**Setting up Branch Protection:**

1. Go to Settings → Branches
2. Add rule for `main` branch:
   - Require pull request reviews (at least 1)
   - Require status checks to pass
   - Require branches to be up to date
   - Include administrators

**Using .gitignore:**
Create `.gitignore` to prevent committing secrets:

```
# Environment variables
.env
.env.local
.env.*.local

# API keys
config/secrets.json
*.key
*.pem

# Dependencies
node_modules/
vendor/

# Build outputs
dist/
build/
```

**Enabling Security Features:**

- Settings → Security → Enable:
  - Dependency graph
  - Dependabot alerts
  - Dependabot security updates
  - Code scanning

#### Activity 6.1: Secure Your Repository (25 minutes)

**Objective**: Implement security best practices.

**Steps:**

1. **Create/Update .gitignore:**

   - Add common patterns
   - Add project-specific files

2. **Set up Branch Protection:**

   - Protect main branch
   - Require PR reviews
   - Require status checks

3. **Enable Security Features:**

   - Enable dependency graph
   - Enable Dependabot alerts
   - Enable Dependabot security updates

4. **Add Security Policy:**

   - Create `SECURITY.md`
   - Include reporting instructions

5. **Review Repository:**
   - Check for any exposed secrets
   - Verify .gitignore is working

**Checkpoint**: Your repository should have branch protection and security features enabled.

---

### Topic 6.2: Using Dependabot

**What is Dependabot?**
Automated tool that:

- Monitors dependencies for vulnerabilities
- Creates PRs to update dependencies
- Keeps your project secure

**Dependabot Features:**

- Security updates
- Version updates
- Alerts for vulnerabilities

#### Example 6.2: Dependabot Configuration

**Enable Dependabot:**

1. Settings → Security → Dependabot
2. Enable "Dependabot alerts"
3. Enable "Dependabot security updates"

**Configure Dependabot (optional):**
Create `.github/dependabot.yml`:

```yaml
version: 2
updates:
  - package-ecosystem: "npm"
    directory: "/"
    schedule:
      interval: "weekly"
    open-pull-requests-limit: 5
```

**Dependabot PR Example:**
When a vulnerability is found, Dependabot creates a PR:

```
Title: Bump lodash from 4.17.20 to 4.17.21
Description:
  - Security update for CVE-2021-23337
  - Changelog: [link]
```

#### Activity 6.2: Set Up Dependabot (20 minutes)

**Objective**: Configure automated dependency updates.

**Steps:**

1. Enable Dependabot in repository settings
2. Create `.github/dependabot.yml` configuration
3. If you have a `package.json`, Dependabot will:
   - Scan for vulnerabilities
   - Create PRs for security updates
4. Review any existing Dependabot alerts
5. If alerts exist, create a test PR to update a dependency

**Checkpoint**: Dependabot should be enabled and configured.

---

### Topic 6.3: Managing Organizations and Teams

**GitHub Organizations:**

- Group related repositories
- Manage team access
- Centralized billing
- Organization-level settings

**Teams:**

- Group of users with shared permissions
- Assign repositories to teams
- Set team-level permissions

**Organization Structure:**

```
Organization
├── Teams
│   ├── Developers (write access)
│   ├── Designers (read access)
│   └── Admins (admin access)
└── Repositories
    ├── Frontend (assigned to Developers)
    └── Backend (assigned to Developers)
```

#### Example 6.3: Organization Setup

**Creating an Organization:**

1. Click your profile → Settings → Organizations
2. Click "New organization"
3. Choose plan (Free, Team, Enterprise)
4. Name your organization
5. Add members

**Creating Teams:**

1. Organization → Teams → New team
2. Name: "Frontend Team"
3. Add members
4. Set team visibility (Secret or Visible)

**Assigning Repositories:**

1. Team → Repositories
2. Add repository
3. Set permission level:
   - Read
   - Write
   - Admin

#### Activity 6.3: Explore Organizations (20 minutes)

**Objective**: Understand organization structure (if you have access).

**Steps:**

1. If you have an organization:

   - Explore the organization settings
   - Review teams and members
   - Check repository access

2. If you don't have an organization:

   - Create a test organization (free)
   - Add at least one team
   - Create a repository in the organization
   - Assign the team to the repository

3. Understand permission levels:
   - What can Read users do?
   - What can Write users do?
   - What can Admin users do?

**Note**: This activity may require organization admin access.

---

## Domain 7: Benefits of the GitHub Community

### Topic 7.1: Participating in Open Source

**Why Contribute to Open Source?**

- Learn from others
- Build your portfolio
- Give back to the community
- Network with developers
- Improve your skills

**How to Get Started:**

1. Find projects you use or are interested in
2. Look for "good first issue" labels
3. Read CONTRIBUTING.md
4. Fork and clone the repository
5. Make a small contribution
6. Submit a Pull Request

#### Example 7.1: Finding Your First Contribution

**Where to Find Projects:**

- GitHub Explore: github.com/explore
- Good First Issues: github.com/topics/good-first-issue
- Projects you already use
- Local meetup projects

**What to Contribute:**

- Fix typos in documentation
- Add examples to README
- Fix small bugs
- Improve error messages
- Add tests
- Translate documentation

**Contribution Workflow:**

1. Find an issue labeled "good first issue"
2. Comment: "I'd like to work on this"
3. Fork the repository
4. Create a branch
5. Make your changes
6. Test your changes
7. Submit a PR with clear description
8. Respond to feedback

#### Activity 7.1: Find an Open Source Project (20 minutes)

**Objective**: Identify a project to contribute to.

**Steps:**

1. Browse GitHub Explore or good-first-issue topics
2. Find 3 projects that interest you
3. For each project:

   - Read the README
   - Check for CONTRIBUTING.md
   - Look for "good first issue" labels
   - Review recent activity

4. Choose one project
5. Find an issue you could address
6. Plan your contribution:
   - What would you change?
   - How would you test it?
   - What would your PR look like?

**Deliverable**: A list of potential projects and one chosen issue to work on.

---

### Topic 7.2: Using GitHub Discussions

**GitHub Discussions:**

- Community forums for repositories
- Q&A format
- Announcements
- General discussions

**Discussion Categories:**

- **General**: Open discussion
- **Ideas**: Feature requests and ideas
- **Q&A**: Questions and answers
- **Announcements**: Project updates (moderators only)
- **Show and tell**: Share work

#### Example 7.2: Engaging in Discussions

**Starting a Discussion:**

1. Go to repository → Discussions tab
2. Click "New discussion"
3. Choose category
4. Write your question/idea
5. Use markdown formatting
6. Add relevant labels

**Good Discussion Post:**

```markdown
## Question: How to handle authentication?

I'm trying to implement user authentication but I'm not sure
about the best approach. I've seen the auth.js file but I'm
confused about the token refresh logic.

**Context:**

- Using JWT tokens
- Need to refresh tokens every 15 minutes
- Currently getting 401 errors

**What I've tried:**

- Reading the documentation
- Looking at examples
- Still unclear on refresh timing

Any guidance would be appreciated!
```

#### Activity 7.2: Participate in Discussions (15 minutes)

**Objective**: Use GitHub Discussions for community engagement.

**Steps:**

1. Enable Discussions in your repository (if not already enabled):

   - Settings → General → Features → Discussions

2. Create a discussion:

   - Category: Q&A
   - Ask a question about best practices
   - Or share something you learned

3. If you have collaborators:

   - Ask them to respond
   - Practice the Q&A format

4. Create an "Ideas" discussion:
   - Propose a feature improvement
   - Use markdown formatting
   - Add relevant details

**Checkpoint**: You should have created at least one discussion in your repository.

---

### Topic 7.3: Contributing to Community Projects

**Contribution Etiquette:**

- Be respectful and professional
- Follow the project's guidelines
- Write clear commit messages
- Keep PRs focused and small
- Respond to feedback promptly
- Thank maintainers

**Before Contributing:**

- Read the README
- Check CONTRIBUTING.md
- Review existing issues
- Understand the codebase
- Ask questions if unclear

#### Example 7.3: Making a Quality Contribution

**Complete Contribution Process:**

1. **Research:**

   - Understand the project
   - Find an appropriate issue
   - Read contribution guidelines

2. **Prepare:**

   - Fork the repository
   - Set up development environment
   - Create a branch

3. **Implement:**

   - Write clean, tested code
   - Follow project style
   - Update documentation

4. **Submit:**

   - Write clear PR description
   - Reference the issue
   - Add screenshots if UI changes
   - Request review

5. **Iterate:**
   - Address feedback
   - Update PR as needed
   - Be patient and respectful

#### Activity 7.3: Plan a Community Contribution (20 minutes)

**Objective**: Plan a real contribution to an open-source project.

**Steps:**

1. Choose a project from Activity 7.1
2. Read the project thoroughly:

   - README
   - CONTRIBUTING.md (if exists)
   - Code of Conduct
   - Recent issues and PRs

3. Identify a contribution:

   - Fix a typo
   - Improve documentation
   - Fix a small bug
   - Add an example

4. Plan your approach:

   - What files will you modify?
   - How will you test it?
   - What will your commit message be?
   - What will your PR description say?

5. (Optional) Make the actual contribution:
   - Fork the repository
   - Make the changes
   - Submit a PR

**Deliverable**: A contribution plan or an actual PR to an open-source project.

---

## Day 2 Afternoon: Hands-On Activities

### Activity E: Complete CI/CD Setup (60 minutes)

**Objective**: Build a complete CI/CD pipeline for your project.

**Tasks:**

1. Create a comprehensive workflow that includes:

   - Linting
   - Testing
   - Building
   - Security scanning
   - Deployment (simulated)

2. Set up multiple environments:

   - Development (on every push)
   - Staging (on PR merge to main)
   - Production (manual trigger)

3. Add status badges to your README:

   ```markdown
   ![CI](https://github.com/username/repo/workflows/CI/badge.svg)
   ```

4. Test the pipeline:
   - Push code that passes
   - Push code that fails (intentionally)
   - Verify appropriate behavior

**Deliverables:**

- Working CI/CD pipeline
- Multiple environments configured
- Status badges in README
- Documentation of the pipeline

---

### Activity F: Security Hardening (45 minutes)

**Objective**: Implement comprehensive security measures.

**Tasks:**

1. **Review and secure:**

   - Check for any exposed secrets
   - Update .gitignore
   - Add SECURITY.md policy

2. **Set up branch protection:**

   - Protect main branch
   - Require PR reviews
   - Require status checks
   - Set up required reviewers

3. **Enable security features:**

   - Dependabot alerts
   - Dependabot security updates
   - Code scanning (if available)
   - Dependency graph

4. **Create security documentation:**
   - How to report vulnerabilities
   - Security best practices
   - Update process

**Deliverables:**

- Secured repository
- Branch protection rules
- Security documentation
- Dependabot configured

---

### Activity G: Project Management Setup (45 minutes)

**Objective**: Create a complete project management system.

**Tasks:**

1. **Set up project board:**

   - Create Kanban board
   - Add custom fields
   - Set up automation rules

2. **Organize issues:**

   - Create labels (at least 10)
   - Set up milestones
   - Create issue templates

3. **Create workflow:**

   - Document your process
   - Set up automation
   - Create views for different needs

4. **Populate with work:**
   - Create 5-10 issues
   - Add them to the board
   - Move them through workflow
   - Link PRs to issues

**Deliverables:**

- Functional project board
- Organized issues with labels
- Automated workflow
- Documentation

---

### Activity H: Open Source Contribution (60 minutes)

**Objective**: Make an actual contribution to an open-source project.

**Tasks:**

1. Find a suitable project (use Activity 7.1 results)
2. Identify a contribution opportunity
3. Fork and clone the repository
4. Make your contribution:
   - Follow their guidelines
   - Write clean code
   - Update documentation if needed
5. Submit a Pull Request:
   - Clear title and description
   - Reference related issues
   - Request review
6. Engage with maintainers:
   - Respond to feedback
   - Make requested changes
   - Be professional and patient

**Deliverables:**

- Forked repository
- Pull Request submitted
- Engagement with project maintainers

---

## Course Wrap-Up

### Final Review

**Key Concepts Covered:**

- ✅ Git fundamentals and workflows
- ✅ GitHub repository management
- ✅ Collaboration through Pull Requests
- ✅ CI/CD with GitHub Actions
- ✅ Project management with GitHub
- ✅ Security best practices
- ✅ Open source contribution

### Next Steps

**Continue Learning:**

1. Practice daily with Git and GitHub
2. Contribute to open-source projects
3. Set up CI/CD for your projects
4. Join GitHub community discussions
5. Explore advanced GitHub features

**Resources:**

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [GitHub Learning Lab](https://lab.github.com/)
- [GitHub Skills](https://skills.github.com/)

### Assessment Questions

**Test Your Knowledge:**

1. Explain the difference between `git merge` and `git rebase`
2. When would you use a fork vs a branch?
3. How do you set up branch protection?
4. What are the benefits of CI/CD?
5. How do GitHub Projects help with workflow management?

### Certificate of Completion

Congratulations on completing the GitHub Foundations training! You now have the skills to:

- Use Git effectively in your daily work
- Collaborate using GitHub
- Implement DevOps practices
- Manage projects with GitHub tools
- Contribute to the open-source community

**Keep practicing and happy coding!** 🚀

---

## Appendix: Quick Reference

### Common Git Commands

```bash
# Repository setup
git init                          # Initialize repository
git clone <url>                   # Clone repository
git remote add origin <url>       # Add remote

# Basic workflow
git status                        # Check status
git add <file>                    # Stage file
git commit -m "message"           # Commit changes
git push                          # Push to remote
git pull                          # Pull from remote

# Branching
git branch                        # List branches
git branch <name>                 # Create branch
git checkout <branch>             # Switch branch
git checkout -b <branch>          # Create and switch
git merge <branch>                # Merge branch

# Viewing
git log                           # View history
git log --oneline                 # Compact history
git log --graph --all             # Visual history
git diff                          # See changes
```

### GitHub Workflow Checklist

**Starting a new feature:**

- [ ] Create issue
- [ ] Create branch from main
- [ ] Make changes
- [ ] Commit frequently
- [ ] Push branch
- [ ] Create Pull Request
- [ ] Request review
- [ ] Address feedback
- [ ] Merge when approved
- [ ] Delete branch

**Security checklist:**

- [ ] .gitignore configured
- [ ] No secrets in code
- [ ] Branch protection enabled
- [ ] Dependabot enabled
- [ ] Security policy added

---

_End of Training Module_
