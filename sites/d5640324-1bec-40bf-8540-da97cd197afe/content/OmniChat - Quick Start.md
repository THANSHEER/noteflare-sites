---
tags:
  - guide
  - plugin
  - demo
title: AI Browser Chat — Quick Start Guide
created: 2026-05-21
---

## My Notes

- **[00:05](https://www.youtube.com/watch?v=-dwLbaCB-_I&t=5)** sfvsdfvsdbs

# 🤖 AI Browser Chat — Quick Start Guide

This note shows you how to get the most out of the **AI Browser Chat** plugin. The plugin embeds ChatGPT, Claude, Gemini, DeepSeek, Perplexity, and Grok directly in your Obsidian sidebar — no copy-paste, no context switching.

---

## Opening the Panel

- Click the **chat icon** in the left ribbon, or
- Press `Ctrl/Cmd+P` and run **Open AI Chat**

---

## Switching Between AIs

Use the **dropdown at the top of the panel** to switch services. A coloured dot shows the active service:

| Service | Colour |
|---|---|
| ChatGPT | Green |
| Claude | Orange |
| Gemini | Blue |
| DeepSeek | Teal |
| Perplexity | Purple |
| Grok | White/Grey |

Your session is preserved per service — switching to Gemini and back to Claude keeps your Claude conversation intact.

---

## Sending Your Notes to AI

### Method 1 — Send selected text

1. Open any note (try [[Learning - How LLMs Work]] or [[Book Notes - Atomic Habits]])
2. Select the text you want to discuss
3. Press `Ctrl/Cmd+P` → **AI Chat: Send selected text to AI**
4. The text lands in the AI's input box — just add your question and send

### Method 2 — Add notes as context

Use the toolbar buttons in the chat panel:

| Button | What it does |
|---|---|
| **Active** | Adds the note you're currently editing |
| **+ Open** | Adds all open tabs at once |
| **+ Note** | Search your vault and pick any note |
| **+ Folder** | Add every note in a folder |

Then click **Add** to inject the content, type your question, and submit.

---

## Example Prompts to Try

Open [[Project Planning]] and send it to Claude:
> *"Summarise the top 3 risks in this project plan and suggest mitigation strategies."*

Open [[Meeting Notes - May 20]] and send to ChatGPT:
> *"Extract all action items from these meeting notes and format them as a Markdown checklist."*

Open [[Research - Payment UX Trends]] and send to Gemini:
> *"Based on this research, what are the 3 most important UX decisions we should make for a payment SDK?"*

Open [[Book Notes - Atomic Habits]] and send to any AI:
> *"How can I apply the Two-Minute Rule to build a daily note-taking habit in Obsidian?"*

---

## Tips

> [!tip] Context Prefix
> In **Settings → AI Chat → Context Prefix**, add a default instruction like:
> `"These are my personal Obsidian notes. Please:`
> Every time you send context, this prefix is prepended automatically.

> [!tip] Send a whole folder
> For a project review, use **+ Folder** to send all notes in `Sample Notes/` at once. Ask:
> *"I have a set of notes about my product launch. Give me a one-page executive summary."*

> [!tip] Auto-clear context
> Enable **Auto-clear context after send** in settings so your context list resets after each send — keeps things tidy when switching topics.

---

## Supported Services

All six services require you to **log in on first use** — AI Browser Chat opens the real website inside Obsidian, so your credentials stay between you and the AI provider. No API keys, no proxies.

- [ChatGPT](https://chatgpt.com) — best for general tasks, coding, writing
- [Claude](https://claude.ai) — best for long documents, nuanced analysis
- [Gemini](https://gemini.google.com) — best for research, Google integration
- [DeepSeek](https://chat.deepseek.com) — strong on coding and reasoning
- [Perplexity](https://perplexity.ai) — best for web-grounded research
- [Grok](https://grok.com) — strong on current events and X/Twitter context
