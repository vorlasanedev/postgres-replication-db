# Git: Commit and Push an Existing Local Repository

This guide covers how to initialize an existing local folder, commit its contents, and push it to a remote GitHub repository using a specific SSH configuration.

## Prerequisites
- An existing local directory containing your project files.
- A GitHub repository created (e.g., `vorlasanedev/postgres-replication-db`).
- An SSH key configured and mapped in your SSH config file (e.g., `~/.ssh/config`) with a specific host alias (e.g., `github.com-vorlasanedev`).

## Steps

1. **Initialize the Local Repository**
   Navigate to your local project directory and initialize it as a Git repository.
   ```bash
   git init
   ```

2. **Stage and Commit Your Files**
   Add all existing files to the staging area and create your initial commit.
   ```bash
   git add .
   git commit -m "Initial commit"
   ```

3. **Add the Remote Repository**
   Link your local repository to the remote GitHub repository using your SSH host alias.
   ```bash
   git remote add origin git@github.com-vorlasanedev:<username>/<repository-name>.git
   git remote add origin git@github.com-vorlasanedev:vorlasanedev/postgres-replication-db.git
   ```

4. **Rename the Default Branch**
   Rename the default branch to `main`.
   ```bash
   git branch -M main
   ```

5. **Push Your Code**
   Push the `main` branch to the remote repository and set up tracking.
   ```bash
   git push -u origin main
   ```

## Notes
- If you accidentally add the wrong remote, you can remove it using `git remote remove origin` before adding the correct one.
- The host alias (`github.com-vorlasanedev`) ensures that Git uses the correct SSH key defined in your `~/.ssh/config` file.
