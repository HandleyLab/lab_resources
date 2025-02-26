# Connecting R/RStudio with GitHub: A Complete Guide

## Prerequisites

Before getting started, ensure you have:

- [R](https://cran.r-project.org/) installed on your computer
- [RStudio](https://posit.co/download/rstudio-desktop/) installed on your computer
- A [GitHub](https://github.com/) account
- [Git](https://git-scm.com/downloads) installed on your computer

## Initial Setup

### Step 1: Configure Git in RStudio

First, let's set up your Git identity in RStudio:

```r
# Install the usethis package if you haven't already
install.packages("usethis")

# Load the package
library(usethis)

# Configure your Git identity
use_git_config(
  user.name = "YourGitHubUsername",
  user.email = "your.email@example.com"
)
```

### Step 2: Set Up Authentication

GitHub requires authentication for pushes. The recommended approach is to use a Personal Access Token (PAT):

```r
# Create a GitHub PAT
usethis::create_github_token()
# This will open a browser window to GitHub where you can confirm and create your token

# Store your PAT securely
gitcreds::gitcreds_set()
# You'll be prompted to enter your PAT
```

## Working with Repositories

### Option A: Create a New Project with Version Control

1. In RStudio, go to **File** → **New Project** → **Version Control** → **Git**
2. Enter the repository URL from GitHub, project name, and choose where to save it
3. Click "Create Project"

### Option B: Start with an Existing Local Project

1. Open your project in RStudio
2. Initialize Git:
   ```r
   usethis::use_git()
   # Follow the prompts - typically you'll select "Yes" to commit, restart RStudio, etc.
   ```
3. Connect to GitHub:
   ```r
   usethis::use_github()
   # This creates a new GitHub repository and links your local repo to it
   ```

### Option C: Clone an Existing Repository

1. In RStudio, go to **File** → **New Project** → **Version Control** → **Git**
2. Paste the repository URL from GitHub
3. Choose where to save it locally
4. Click "Create Project"

## Daily Workflow

### Using the RStudio Git Interface

The Git tab is located in the upper-right panel in RStudio:

1. **Pull** before you start working to get the latest changes
2. Make changes to your files
3. **Stage** changed files by checking the boxes next to them
4. Write a descriptive **commit message**
5. Click **Commit** to record your changes locally
6. Click **Push** to send your changes to GitHub

### Using R Commands for Git Operations

You can also use these commands within R:

```r
# Pull latest changes from GitHub
pull()

# Check status of changes
git_status()

# Add and commit changes
git_add("your-file.R")
git_commit("Description of your changes")

# Push changes to GitHub
git_push()
```

## Branch Management

### Creating and Switching Branches

```r
# Create a new branch
usethis::pr_init("new-feature")

# Work on your changes, then commit them

# Push your branch to GitHub and create a PR
usethis::pr_push()
```

### Merging Branches

After your pull request is approved and merged on GitHub:

```r
# Switch back to main branch and update
usethis::pr_finish()
```

## Advanced Features of usethis

The `usethis` package helps with many GitHub-related tasks:

- `use_github_action()` - Set up GitHub Actions workflows
- `use_readme_md()` - Create a README file
- `use_github_labels()` - Configure issue labels
- `browse_github_issues()` - Open issues in browser
- `use_github_release()` - Create GitHub releases

## Troubleshooting

### Common Issues and Solutions

1. **Authentication failures:**
   ```r
   # Reset your GitHub credentials
   gitcreds::gitcreds_set()
   ```

2. **Git not detected:**
   Ensure Git is installed and on your PATH. Restart RStudio after installation.

3. **RStudio doesn't show Git tab:**
   Ensure your project is a Git repository. If not, run `usethis::use_git()`.

4. **Conflicts when pulling:**
   Resolve conflicts in the files, then:
   ```r
   # After resolving conflicts manually
   git_add("file-with-conflict.R")
   git_commit("Resolve merge conflict")
   ```

## Learning Resources

- [Happy Git and GitHub for the useR](https://happygitwithr.com/)
- [RStudio Git Documentation](https://support.posit.co/hc/en-us/articles/200532077-Version-Control-with-Git-and-SVN)
- [usethis package documentation](https://usethis.r-lib.org/)

---

Remember that the `usethis` package simplifies the Git workflow considerably, but understanding the underlying Git concepts is still valuable for troubleshooting and advanced usage.
