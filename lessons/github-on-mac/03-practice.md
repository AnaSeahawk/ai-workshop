# 3. Test with a private repository

Use the verified personal GitHub account, a fresh local folder, and a unique name for a **private** practice repository. Use a plain README with no personal data. This exercise creates a repository and two local copies.

1. Create the repository with `gh repo create OWNER/NAME --private`, substituting the verified account and chosen repository name. Confirm the owner, URL, and private visibility through GitHub CLI before pushing.
2. Initialize Git in the first fresh folder, commit the README on `main`, add the verified HTTPS remote, and push with `git push -u origin main`.
3. Clone the repository over HTTPS into a second fresh folder. Compare its commit ID to the first copy.
4. Make a small README edit in the first copy, commit, and push it. In the second copy, run `git pull --ff-only` and compare the commit IDs again. This checks that the second copy received an actual update.
5. If any command fails, check the account, destination, authentication, and current state before retrying. Before retrying creation, check whether GitHub already created the repository.

Keep the repository and both copies for practice. Tell the learner the verified GitHub username, repository link, both local folder paths, which operations passed, and how to reopen a local Code session. If a step remains blocked, identify what’s missing.

[GitHub CLI repository creation](https://cli.github.com/manual/gh_repo_create) · [Git pull](https://git-scm.com/docs/git-pull) · [Back to the workshop](../../README.md)
