# Contributing to EventChain

First off, thanks for taking the time to contribute! 🎉
EventChain is an open-source project and we welcome contributions of all kinds—bug fixes, features, documentation improvements, and more.

This document explains the standard workflow for contributing to EventChain using Git and GitHub.

---

## Table of Contents

* [Getting Started](#getting-started)
* [Forking and Cloning the Repository](#forking-and-cloning-the-repository)
* [Creating Branches](#creating-branches)
* [Committing and Pushing Changes](#committing-and-pushing-changes)
* [Opening a Pull Request](#opening-a-pull-request)
* [Syncing Your Fork](#syncing-your-fork)
* [Best Practices](#best-practices)

---

## Getting Started

Before contributing, make sure you have:

* A GitHub account
* Git installed locally
* Basic knowledge of Git commands

---

## Forking and Cloning the Repository

### Step 1: Fork the repository

1. Navigate to the EventChain repository on GitHub
2. Click the **Fork** button (top-right corner)
3. This creates a copy of the repository under your GitHub account

### Step 2: Clone your fork locally

Go to your preferred working directory and run:

```bash
git clone https://github.com/<your-username>/EventChain.git
cd EventChain
```

### Useful Git Commands

```bash
git status        # Check the current status
git add .         # Stage all changes
git commit -m "Your commit message"
git push          # Push commits to GitHub
git pull          # Pull latest changes
```

---

## Creating Branches

⚠️ **Do not make changes directly on the `main` branch.**

Always create a new branch for your work.

```bash
git checkout -b <your-branch-name>
```

Example:

```bash
git checkout -b fix-auth-bug
```

If needed, switch branches using:

```bash
git switch <your-branch-name>
```

Now you can start working on your feature or bug fix.

---

## Committing and Pushing Changes

After making your changes:

```bash
git add .
git commit -m "Fix: resolve authentication issue"
git push origin <your-branch-name>
```

This will push your branch to your forked repository.

---

## Opening a Pull Request

1. Go to your forked repository on GitHub
2. Click **Compare & Pull Request**
3. Set the base repository and branch to:

   ```
   bitflipper19:main
   ```
4. Fill out the Pull Request following `PULL_REQUEST_TEMPLATE.md`
5. Link the related issue using `#issue_id`

### Review Process

* Maintainers will review and test your Pull Request
* Changes may be requested
* Once approved, your PR will be merged
* Contribution points will be awarded based on impact and quality

---

## Syncing Your Fork

EventChain is actively developed, so keeping your fork up to date is important.

### Syncing on GitHub

1. Go to your forked repository
2. Click **Sync fork**
3. Update your fork with the latest upstream changes

### Syncing Locally

Make sure you are on the `main` branch:

```bash
git branch
```

If you’re not on `main`, switch:

```bash
git switch main
```

Pull the latest changes:

```bash
git pull origin main
```

Your local repository is now up to date.

---

## Best Practices

* Write clear and meaningful commit messages
* Keep Pull Requests focused on a single issue or feature
* Sync your fork before starting new work
* Follow existing code style and conventions
* Be respectful and collaborative in discussions

---

## Happy Contributing! 🚀

Every contribution helps improve EventChain.
If you have questions or need guidance, feel free to open an issue or start a discussion.

We’re excited to have you on board! 🎉

---
