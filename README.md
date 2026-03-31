# Nano Banana Flow Generator

AI system for mass-generating Facebook/Instagram story ad visuals using Google Flow platform and Claude Code automation.

## What does it do?

You give Claude a client website link + a Flow project link, and it:
1. Reads the website — extracts product info, pricing, benefits, testimonials, style
2. Writes 50 sales-focused prompts tailored to that product
3. Opens Flow in Chrome and automatically submits prompts one after another
4. Images generate in the background (~30 sec per image)

## Setup (one time)

### 1. Claude Code CLI
```bash
# Install Claude Code
npm install -g @anthropic-ai/claude-code

# Verify it works
claude --version
```
You need an Anthropic account with an active plan (Pro/Team).

### 2. "Claude in Chrome" Extension
1. Open Chrome
2. Go to Chrome Web Store
3. Search for "Claude in Chrome" (by Anthropic)
4. Install the extension
5. Log in with the same Anthropic account

This extension is KEY — it gives Claude access to the browser (clicks, typing, reading pages).

### 3. Google Account
- Log in at https://labs.google/fx/tools/flow/ with a Google account
- It's free, no API keys needed

## Usage

```bash
# Clone/download this folder
cd nanobanana-flow-generator

# Start Claude Code in this folder
claude
```

Claude automatically reads the `CLAUDE.md` file which explains the entire workflow.

### Example command:

```
Read the website https://example.com and create 50 FB story visuals (9:16).
Send them here: https://labs.google/fx/tools/flow/project/YOUR-PROJECT-ID
```

### First, create a Flow project:
1. Go to https://labs.google/fx/tools/flow/
2. Click "New Project" (+)
3. (Optional) Upload reference images — product logo, packaging photo
4. Copy the project URL from the browser
5. Give that URL to Claude

## Notes

- Flow is free but has a soft limit on generation (usually 200+ images works fine)
- Text on images is AI-generated and sometimes inaccurate — for final ads, add text in Canva/Photoshop
- If the Chrome MCP connection drops during a session, just say "continue" and Claude will reconnect
- Prompts are in English because Nano Banana understands English better, but text overlay can be in any language
