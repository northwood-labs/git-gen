# git-gen

Have AI review your changes and recommend a commit message.

## Usage

After developing something really cool…

```bash
# Stage the changes you want to run AI over.
git add .

# Ask AI to review your diff, and compose an appropriate commit message.
git gen
```

It then opens whatever editor you have configured as your [git core.editor](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration#_core_editor), and allows you to make any final edits before committing.

## IP safety

Different enterprises are signing their employees up for different agentic coding tools — [GitHub CoPilot], [GitLab Duo Agent Platform], [Claude Code], [Kiro], [Amazon Bedrock], and _so many more_. Perhaps you, like me, use _several_ of them.

Use whatever your enterprise has approved and given you credentials for. These enterprise contracts have all of the IP details in them so that you're not sending proprietary intellectual property to some rando.

Or be like the former Fox news personality and current U.S. Secretary of “War”, Pete Hegseth[^1][^2][^3][^4][^5] and his associates[^6][^7][^8].

## Opinions

[Amazon Bedrock]: https://aws.amazon.com/bedrock/
[Claude Code]: https://claude.com/product/claude-code
[GitHub CoPilot]: https://github.com/features/copilot/agents
[GitLab Duo Agent Platform]: https://about.gitlab.com/gitlab-duo-agent-platform/
[Kiro]: https://kiro.dev

[^1] https://www.theatlantic.com/politics/archive/2025/03/trump-administration-accidentally-texted-me-its-war-plans/682151/
[^2] https://www.washingtonpost.com/politics/interactive/2025/trump-administration-signal-chat-leak-response/
[^3] https://www.politifact.com/factchecks/2025/mar/26/pete-hegseth/fact-checking-pete-hegseths-false-statement-that-n/
[^4] https://www.courtlistener.com/docket/69788832/american-oversight-v-hegseth/
[^5] https://www.anthropic.com/news/statement-comments-secretary-war
[^6] https://www.politico.com/news/2026/01/27/cisa-madhu-gottumukkala-chatgpt-00749361
[^7] https://arstechnica.com/tech-policy/2026/01/us-cyber-defense-chief-accidentally-uploaded-secret-government-info-to-chatgpt/
[^8] https://cybersecuritynews.com/hacker-uses-claude-and-chatgpt-to-breach/
