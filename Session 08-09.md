## Session 08: Tagging in Git

### Using Tags to Mark Significant Changes

Tags are references that point to specific points in Git history and are often used to mark release points like v1.0, v2.0, etc.

```bash
~ git tag -a v1.0 -m "Release version 1.0"
```

If you want to tag a commit that you've identified in your `git log`, you can specify the commit's checksum:

```bash
~ git tag -a v0.1 <commit-checksum>
```

To view details about the tag, use the `git show` command:

```bash
~ git show v1.0
```

### Pushing Tags to Remote Repository

By default, the `git push` command does not transfer tags to remote repositories. To push a tag to your remote repository:

```bash
~ git push origin v1.0
```

Or push all your tags at once:

```bash
~ git push origin --tags
```

---

## Session 09: Signing Tags and Commits

### Introduction to Digital Signatures

In the world of software development, it's crucial to ensure that the code changes are verified and trusted. This is where GPG (GNU Privacy Guard) comes in, allowing you to sign your work digitally.

### Generating a New GPG Key

To create a new GPG key, use the following command:

```bash
~ gpg --gen-key
```

After generating your keys, list them with:

```bash
~ gpg --list-secret-keys --keyid-format LONG
```

### Adding Your GPG Key to Git

Configure Git to use your GPG key:

```bash
~ git config --global user.signingkey <your-signing-key>
```

To sign a tag:

```bash
~ git tag -s v2.1 -m "Signed version 2.1"
```

Verifying a signed tag:

```bash
~ git show v2.1
```

---

For additional help on any Git function:

```bash
~ git help <command>
```

Explore more advanced features like `git bisect` for debugging or `git blame` to see who made changes:

```bash
~ git bisect
~ git blame
```