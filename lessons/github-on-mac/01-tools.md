# 1. Check the Mac and install the tools

Confirm that your commands run on the learner’s actual Mac. A cloud session or sandbox might have a shell of its own. If you lack local access, guide the learner to a local session in Claude Desktop. If that option is missing, check Anthropic’s current instructions for Claude Code in Terminal. If local agent access is still unavailable, give the learner short commands to run in macOS Terminal and ask only for specific non-secret results. [Claude Code on desktop](https://code.claude.com/docs/en/desktop)

Check the macOS version, available package manager, and installed versions of Git and GitHub CLI (`gh`). Reuse what already works. If Git requires Apple’s Command Line Tools, start `xcode-select --install` and let the learner approve the system dialog. If Homebrew is already installed, use `brew install gh` for a missing GitHub CLI. Otherwise choose a supported option from GitHub CLI’s official installation instructions. Check that the local agent session can find the installed tools. Have the learner enter any administrator password privately. [Apple Command Line Tools](https://developer.apple.com/documentation/xcode/installing-the-command-line-tools/) · [GitHub CLI installation](https://github.com/cli/cli#installation)

Check the effective Git commit name and email before the first commit. Preserve existing settings if they’re correct. If a value is missing or incorrect, ask the learner what they want to use and offer GitHub’s noreply email option. Use repository-level settings for the practice repository when appropriate. [GitHub commit email settings](https://docs.github.com/en/account-and-profile/how-tos/email-preferences/setting-your-commit-email-address)

[Next: Sign in to GitHub](02-sign-in.md)
