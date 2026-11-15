# 2. Connect GitHub and keep credentials private

## Browser sign-in and Keychain

Check for an existing GitHub CLI login with `gh auth status --hostname github.com`. Preserve other accounts and working credential helpers. If the correct account needs to sign in, use:

```sh
gh auth login --hostname github.com --git-protocol https --web
```

The learner completes approval at GitHub in their usual browser using the one-time device code from their login command. If your shell can’t run the interactive flow, have them run the command in their own Terminal and say “done” when they finish. They enter their own password or passkey and handle any two-factor prompts. Pause screen or browser observation for those steps. [GitHub CLI sign-in](https://cli.github.com/manual/gh_auth_login)

The assistant doesn’t need to control a browser for this. If a separate task needs browser access, check whether the learner has Cowork’s built-in browser, Claude in Chrome, or desktop computer use. If available and needed, guide the learner through granting access to GitHub. If unavailable, give them exact clicks and continue through the CLI. [Cowork’s built-in browser](https://support.claude.com/en/articles/16607400-use-the-built-in-browser-in-claude-cowork) · [Claude in Chrome](https://support.claude.com/en/articles/12012173-get-started-with-claude-in-chrome)

Check the active account using `gh api user --jq .login`. Confirm that GitHub CLI uses macOS Keychain for the credential. GitHub CLI can fall back to plaintext if secure storage is unavailable. If that happens, fix secure storage and guide the learner through revoking and replacing the affected credential before using it. If HTTPS Git authentication needs setup, check for existing helpers and other accounts, then use `gh auth setup-git --hostname github.com`. [GitHub CLI credential storage](https://cli.github.com/manual/gh_auth_login) · [Git credential setup](https://cli.github.com/manual/gh_auth_setup-git)

## When a separate API token is needed

The browser login already gives GitHub CLI a token. Use a separate personal access token only when the learner’s workflow calls for one. Ask which password manager they use. Help them choose an expiration and the narrowest permissions the workflow needs. Check permissions for creating repositories separately from permissions for pushing to an existing repository. Let the learner create and save the token privately while screen and browser access are paused. [GitHub personal access tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)

Use the password manager’s supported credential integration or a direct pipe to a client that accepts the secret on standard input. When a client requires an environment variable, a launcher such as 1Password’s `op run` can resolve a secret reference and pass the value to the specific client. Keep only the reference in the configuration. Keep unlock and biometric approval with the learner. Never launch an agent or general shell with the token in its environment. If the existing manager lacks a safe integration, use the Keychain-backed GitHub CLI login for GitHub. [1Password process-scoped credentials](https://www.1password.dev/cli/reference/commands/run)

Keep secret values out of chat, screenshots, command arguments, shell history, remote URLs, files, and logs. Avoid clipboard reads, shell tracing, environment dumps, token-display commands, and credential-helper commands that print secrets. Verify access by account name and successful operations.

[Next: Test with a private repository](03-practice.md)
