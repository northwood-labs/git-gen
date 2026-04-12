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

Different enterprises are signing their employees up for different agentic coding tools — [GitHub Copilot], [GitLab Duo Agent Platform], [Claude Code], [Kiro], [Amazon Bedrock], and _so many more_. Perhaps you, like me, use _several_ of them.

Use whatever your enterprise has approved and given you credentials for. These enterprise contracts have all of the IP details in them so that you're not sending proprietary information somewhere you shouldn't.[^1][^2][^3][^4][^5][^6][^7][^8]

## Opinions strongly held

* It uses [Conventional Commits].
* It uses past-tense (e.g., _Added_) instead of present-tense (e.g., _Adding_).
* It completes sentences with periods, even in commit messages.
* The top-level commit message (title) has a max length of 80 characters.
* It uses U.S. English spelling and grammar.
* It explicitly ignores many types of lockfiles (new ones need to be added by hand).

If you want something different, feel free to fork. You are free to change the system prompt.

## Configuring

`git-gen` supports a few different providers, and a few different models for handling the generation.

> [!WARNING]
> Prefer something else? As long as it has a _sensible_ CLI, it should be possible. Open an issue.

### Claude Code (default)

1. You need to have a Claude subscription of some kind, either via [Claude Console](https://platform.claude.com) or [Claude.ai](https://claude.ai).

2. The [`claude` command](https://code.claude.com/docs/en/overview) needs to be installed in your Terminal and on your `$PATH`.

3. You need to be logged-in in your Terminal.

    ```bash
    claude auth login
    ```

4. Log into the CLI, poke around, start a chat, and make sure it's working.

5. Set `GITGEN_PROVIDER` to `claude`.

    ```bash
    export GITGEN_PROVIDER="claude"
    ```

### GitHub Copilot

1. You need to have a GitHub Copilot subscription of some kind.

2. The [`copilot` command](https://docs.github.com/en/copilot/concepts/agents/copilot-cli/about-copilot-cli) needs to be installed in your Terminal and on your `$PATH`.

    > [!NOTE]
    > This is the top-level `copilot` command, not the `gh copilot` subcommand.

3. You need to be logged-in in your Terminal.

    ```bash
    copilot login
    ```

4. Log into the CLI, poke around, start a chat, and make sure it's working.

5. Set `GITGEN_PROVIDER` to `copilot`.

    ```bash
    export GITGEN_PROVIDER="copilot"
    ```

### Kiro CLI

1. You need to have an AWS Kiro subscription of some kind.

2. The [`kiro-cli` command](https://kiro.dev/cli/) needs to be installed in your Terminal and on your `$PATH`.

3. You need to be logged-in in your Terminal.

    ```bash
    kiro-cli login
    ```

4. Log into the CLI, poke around, start a chat, and make sure it's working.

5. Set `GITGEN_PROVIDER` to `kiro`.

    ```bash
    export GITGEN_PROVIDER="kiro"
    ```

### Models

The default model is _Claude Haiku 4.5_. It's smart, fast, cheap, and is available from _several_ providers.

If you'd prefer a different model, you can set `GITGEN_MODEL` to a model that your provider understands, and we'll pass it through to the CLI.

## What about local models?

We're working on it, but no promises at this stage. Local models are great for privacy, but require more effort:

* more finagling to get working properly.
* adjustments to model sizes to work across a variety of machines.
* ensuring the local system has enough RAM to run the model.

[Amazon Bedrock]: https://aws.amazon.com/bedrock/
[Claude Code]: https://claude.com/product/claude-code
[GitHub Copilot]: https://github.com/features/copilot/agents
[GitLab Duo Agent Platform]: https://about.gitlab.com/gitlab-duo-agent-platform/
[Kiro]: https://kiro.dev
[Conventional Commits]: https://www.conventionalcommits.org/en/v1.0.0/

[^1]: [The Trump Administration Accidentally Texted Me Its War Plans](https://www.theatlantic.com/politics/archive/2025/03/trump-administration-accidentally-texted-me-its-war-plans/682151/) (The Atlantic)
[^2]: [How the Trump administration has downplayed the Signal chat scandal](https://www.washingtonpost.com/politics/interactive/2025/trump-administration-signal-chat-leak-response/) (Washington Post)
[^3]: [Fact checking Pete Hegseth’s false statements](https://www.politifact.com/factchecks/2025/mar/26/pete-hegseth/fact-checking-pete-hegseths-false-statement-that-n/) (Politifact)
[^4]: [American Oversight v. Hegseth, 1:25-cv-00883, (D.D.C.)](https://www.courtlistener.com/docket/69788832/american-oversight-v-hegseth/) (CourtListener)
[^5]: [Statement on the comments from Secretary of War Pete Hegseth](https://www.anthropic.com/news/statement-comments-secretary-war) (Anthropic)
[^6]: [Trump’s acting cyber chief uploaded sensitive files into a public version of ChatGPT](https://www.politico.com/news/2026/01/27/cisa-madhu-gottumukkala-chatgpt-00749361) (Politico)
[^7]: [US cyber defense chief accidentally uploaded secret government info to ChatGPT](https://arstechnica.com/tech-policy/2026/01/us-cyber-defense-chief-accidentally-uploaded-secret-government-info-to-chatgpt/) (Ars Technica)
[^8]: [Hacker Uses Claude and ChatGPT to Breach Multiple Government Agencies](https://cybersecuritynews.com/hacker-uses-claude-and-chatgpt-to-breach/) (Cyber Security News)
