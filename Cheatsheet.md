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
