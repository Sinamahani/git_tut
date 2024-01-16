## Session 03: Viewing the Commit History

### Understanding `git log`

The `git log` command is used to review the history of your work, showing commits in reverse chronological order.

```bash
~ git log
```

This command displays the commit history, with the most recent commits at the top, each with its unique identifier and timestamp.

### Adding New Files to the Project

Imagine your project is progressing, and you need to add three new files:

```bash
~ touch page1.html page2.html page3.html
```

After creating these files, you can use a text editor to add content to them. Running `git status` will show these as untracked files:

```bash
~ git status
```

### Recap of Commands Covered

By the end of lesson three, we've explored the following Git commands:

- `git init` - Initialize a new Git repository
- `git status` - Check the status of your working directory and staging area
- `git add <file>` or `git add -A` - Stage changes for commit
- `git commit -m 'message'` - Commit your staged content as a new commit snapshot
- `git log` - Show commit logs

---

## Session 04: Understanding Changes with `git diff`

### Viewing Changes with `git diff`

To see what has changed but not yet staged, use `git diff` with no arguments:

```bash
~ git diff
```

For changes that have been staged but not yet committed:

```bash
~ git diff --staged
```

### Resetting and Checking Out

If you decide you're not happy with the staged changes:

```bash
~ git reset <file>
```

To discard changes in your working directory:

```bash
~ git checkout -- <file>
```

### Summary of Commands

In this lesson, we've learned to:

- Use `git diff HEAD` to see changes since the last commit.
- Use `git diff --staged` to see what's staged but not yet committed.
- Reset staged files with `git reset <file>`.
- Revert changes with `git checkout -- <file>`.

