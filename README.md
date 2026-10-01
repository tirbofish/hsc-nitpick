# hsc-nitpick

I hate it when I'm doing my english work and the agent tells me that my essay is fine when I haven;t even linked it back to the main point. 
This skill/plugin aims to get rid of that issue. 

# How to install

## Codex

In the Codex CLI

```bash
codex plugin marketplace add tirbofish/hsc-nitpick
codex plugin add hsc-english-nitpick@hsc-nitpick
```

In the ChatGPT desktop app:
1. Go to plugins
2. Click on **Add** on the top right
3. Click **Add a marketplace**
4. Source: tirbofish/hsc-nitpick, everything else default
5. After clicking add, go to the Personal tab in Plugins, then "HSC Nitpick" and click install

To call it in chat, append `$hsc-english-nitpick` to your prompt and select the HSC English Nitpick skill.

If you already added this marketplace, refresh it with `codex plugin marketplace upgrade hsc-nitpick`, then run the install command above.

## Claude Code

```bash
claude plugin marketplace add tirbofish/hsc-nitpick
claude plugin install hsc-english-nitpick@hsc-nitpick
```

Restart Claude Code after installing, then invoke `/hsc-english-nitpick:hsc-english-nitpick` with the exact essay question and your response.

For local development, run `claude --plugin-dir .` from this repository.

## Gemini

1. Go to [Gemini](https://gemini.google.com)
2. Click on Settings, then Skills
3. Download [SKILL.md](SKILL.md) from this repository
4. Click on the upload button, then upload your downloaded SKILL.md
5. After uploading, click on Create

To call it in chat, append `/hsc-english-nitpick` to your prompt.  

## Package layout

The shared marketplace catalog is `.claude-plugin/marketplace.json`, which both Claude Code and Codex support. Its `source` points to the repository root. Each host has its own plugin manifest, and both load the same `skills/hsc-english-nitpick/` directory, including its reference files.

`SKILL.md` at the repository root is the standalone upload version for Gemini. For agents that install skill directories, copy the complete `skills/hsc-english-nitpick/` directory so its references remain available.
