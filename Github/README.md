# GitHub Notes

## What is Git?

Git is a version control system that is free and open-source.

## What is Version Control (VC)?

Version control is a way for programmers to track code changes. It helps in:

- Tracking bugs
- Reviewing changes made, when, and by whom
- Reverting to previous versions of code if needed

## What is GitKraken?

GitKraken is a Git client that provides a graphical interface to manage Git repositories.

## Git Commands

Here are some common Git commands you should be familiar with:

- **clone**: Bring a repository that is hosted somewhere like GitHub into a folder on your local machine.
- **add**: Track your files and changes in Git.
- **commit**: Save your files in Git.
- **push**: Upload Git commits to a remote repository, like GitHub.
- **pull**: Download changes from a remote repository to your local machine (opposite of push).

## Git Account

1. Create a new account using your email.
2. Redirect to your profile page or overview.
3. Click on "New repository", name it, and create it with a README file.
4. Update the README with your profile or career summary.

You can see all commit history by clicking on the "Commits" button in the repository. Clicking on a specific commit will show you which lines were added or deleted.

## Cloning through VS Code

1. Go to the repository on GitHub, click on "Code", and copy the HTTPS link.
2. Open VS Code and navigate to the folder where you want to keep the repository locally.
3. Open the terminal in VS Code, and run the following command:

```sh
 git clone <paste the copied HTTPS link>
```

This will clone the repository locally.

To check hidden files of Git in Windows, use:

```sh
ls -Force
```

In macOS or Linux, use:

```sh
ls -la
```

## Git Status

1. Update any file and save it.
2. Open the terminal and run the following command to check which files have changed:
   ```sh
   git status
   ```
