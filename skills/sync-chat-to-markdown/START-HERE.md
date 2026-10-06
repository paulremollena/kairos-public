# Start Here: Sync Chat to Markdown

This package helps ChatGPT save important decisions, outcomes, corrections, owners, deadlines, and next actions into your own private Markdown files before a chat is archived.

## Install or test it

1. Open the raw `SKILL.md` link from GitHub.
2. Give that link to ChatGPT and say:

   > Read this skill completely. Help me configure it for my own private Markdown files. Do not copy another person's personal or company context. Start by checking what file access you actually have.

3. Tell ChatGPT where your Markdown files live and which folders are private, read-only, excluded, or safe to update.
4. Run one supervised test using a completed, low-risk chat.
5. Check that ChatGPT:
   - saves only validated decisions and outcomes;
   - updates the correct existing file instead of creating duplicates;
   - shows exact file changes;
   - asks to sync before archiving;
   - asks separately before actually archiving.

## Important limitation

The skill does not give ChatGPT access to your laptop, GitHub repository, or files. For direct automatic updates, your ChatGPT workspace must already have authorized write access to the correct Markdown destination. Without that access, ChatGPT can prepare the exact Markdown update, but you must save it manually.

## Suggested private files

Use your existing structure if you already have one. A new setup usually needs only:

- `AGENTS.md` — tells AI where to start and which file controls each topic;
- `user.md` — stable preferences and working style;
- project, company, or people files — verified facts and decisions for each subject;
- `handoff.md` — current work, open decisions, owner, and next checkpoint;
- `memory.md` — a short index of durable context.

Do not put passwords, tokens, financial credentials, customer data, private HR information, or authentication sessions into these files or GitHub.

## Trial prompt

> Use the sync-chat-to-markdown skill for this completed task. First give me the six-field completion report. Ask whether we should proceed with sync context. If I say yes, reconcile the full conversation into the smallest relevant Markdown files, show every file changed with exact line counts and unified diffs, and then ask separately whether I want to archive the chat. Do not archive during the sync step.
