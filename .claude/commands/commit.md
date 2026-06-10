Review all staged and unstaged changes, then suggest a commit message following the format:

```
feat: [short description of changes]
```

Rules:
- Use `feat:` prefix for new features/additions
- Use `fix:` prefix for bug fixes
- Use `chore:` prefix for config, tooling, or dependency changes
- Keep it concise (under 72 characters)
- Use lowercase after the prefix

After suggesting the message, STOP. Do NOT run `git add`, `git commit`, or `git push` unless the user explicitly approves the message and asks you to proceed.

Never include `Co-Authored-By` trailers in commit messages for this project.
