---
name: maintain-obsidian-vault
description: Audit and maintain an Obsidian or Markdown vault by finding orphan notes, broken or missing links, stale context, and unclear authority; ask exactly five validation questions per batch, apply approved local edits, keep an audit log, and optionally set up a daily review. Use when a user asks to update, connect, clean up, or routinely review their Obsidian or Markdown knowledge base.
metadata:
  author: Paul E. Remollena
  license: MIT
  version: 1.0.0
---

# Maintain Obsidian Vault

Help the owner keep an Obsidian or Markdown vault accurate, connected, useful, and safe. The goal is not to create the densest graph. The goal is to make important notes easy to find, correctly linked, current, and clear about which file is authoritative.

Installing or reading this skill does not grant file access and does not authorize edits. Confirm the scope and permissions first.

## First-run setup: ask exactly five questions

Ask these five questions together. Keep them simple. Do not inspect or change the vault until the owner answers them.

1. Where is your Obsidian vault or Markdown folder? Please give the exact folder path, or upload the files if I cannot access your computer.
2. Where is your existing audit or update log? If you do not have one, may I create a note named `Obsidian Maintenance Log` inside a `00 - System` then `Logs` folder in the vault?
3. Can I directly access and edit the files on this laptop or PC, or should I work only with files you upload or paste here?
4. Which folders may I inspect and update, and which folders, private topics, archives, attachments, or generated files must I leave alone?
5. Do you want this review to run every day? If yes, what time and timezone should I use, and should I only notify you when there are useful questions or a problem?

If an answer is incomplete, ask only the smallest follow-up needed. Never ask for passwords, tokens, recovery codes, private keys, or unrestricted remote access.

## Permission states

Classify the working mode before acting:

- **Direct local access:** The AI can read the approved folder. It may edit only after the owner has authorized edits for this audit.
- **Read-only local access:** Inspect and propose exact changes, but do not modify files.
- **Uploaded or pasted files only:** Audit only the supplied material. Never imply the whole vault was checked.
- **No usable access:** Explain what access or files are missing and stop. Do not guess.

Daily scheduling is a separate action. If the owner says yes, use the environment's supported reminder or automation feature and show the exact schedule before saving it. If scheduling is unavailable, provide a copy-paste daily prompt instead. Never claim a schedule exists without verifying it.

## Build the inventory

Work locally unless the owner explicitly requests another destination.

1. Confirm the vault root and approved scope.
2. Find Markdown files in scope. Exclude `.git`, `.obsidian`, dependency folders, build output, caches, exports, archives, trash, generated documentation, and any folder the owner marked off-limits unless the current task specifically requires one.
3. Parse both Obsidian wiki links such as `[[Note]]` and normal Markdown links whose destinations point to notes in the approved vault.
4. Record, without changing files:
   - notes with no meaningful incoming links;
   - notes with no useful outgoing links;
   - unresolved links or links to missing targets;
   - duplicate or near-duplicate titles that may point to different files;
   - important notes that do not identify their parent hub, source, owner, status, or controlling authority when those fields matter;
   - stale or conflicting statements that require the owner's judgment.
5. Read enough surrounding content to understand whether a connection is real. A shared word, person name, or folder is not sufficient proof of a meaningful link.

Treat an orphan as a review signal, not an automatic defect. Daily notes, logs, raw captures, templates, indexes, attachments, and intentionally standalone records may be valid without backlinks.

## Prioritize findings

Review in this order unless the owner chooses another priority:

1. People, active projects, and companies or organizations.
2. Current responsibilities, decisions, deadlines, owners, and source-of-truth files.
3. Hubs, maps of content, operating systems, and reusable procedures.
4. Supporting knowledge and older material.
5. Cosmetic graph improvements.

Prioritize a question when the answer would prevent wrong advice, reconnect active work, resolve conflicting facts, identify the correct authority, or make a high-value note findable. Do not spend the owner's attention on low-value link decoration while material questions remain.

## Ask exactly five validation questions per batch

Present exactly five independent, high-value questions at a time. If fewer than five real questions remain, present the smaller final batch and state that no other high-value question was found. Do not invent filler questions.

Each question must contain:

- the exact note or files involved, with clickable local links when the interface supports them;
- the issue in plain language;
- one recommended answer or change;
- a short reason for the recommendation;
- the exact decision needed from the owner.

Use this format:

```markdown
### Question 1 of 5
Files: clickable link to Note A; clickable link to Project Hub

Issue: Note A has no meaningful connection to the active project, so it may be missed during future reviews.

Recommendation: Add `[[Project Hub]]` under `Related` in Note A and add `[[Note A]]` to the hub's supporting notes.

Why: This creates a real two-way route without changing the note's meaning.

Decision: Approve, change, skip, or explain the correct relationship.
```

Do not combine several unrelated decisions into one question merely to stay within the five-question limit. If one answer controls later questions, ask the upstream question first and save dependent questions for the next batch.

## Apply answers safely

After the owner answers a batch:

1. Restate the approved changes briefly.
2. Edit only the approved files and preserve their existing style, frontmatter, headings, filenames, and unrelated content.
3. Do not delete, merge, rename, move, split, archive, publish, upload, or change privacy status unless the owner separately approves that exact action.
4. Never create a link whose relationship is uncertain. Preserve ambiguity as an open question.
5. Re-scan the changed files and confirm that links resolve and no duplicate content or malformed Markdown was introduced.
6. Append a dated entry to the approved audit log containing:
   - files checked;
   - questions asked;
   - owner decisions;
   - files changed;
   - links added or repaired;
   - unresolved items;
   - verification result.
7. Show the owner the changed files and a concise before-and-after summary.
8. Present the next batch of five high-value questions in the same response unless the owner asked to pause, the agreed daily limit was reached, or no high-value question remains. State the exact stopping reason.

If a write or verification fails, stop editing, preserve the visible error, record what was and was not changed, and do not claim completion.

## Daily review behavior

If the owner approves a daily review:

- Run only at the confirmed time and timezone.
- Start by checking whether the vault path and permissions still work.
- Review new or changed in-scope Markdown first, then unresolved high-value items from the log.
- Ask one batch of exactly five questions by default. If fewer than five high-value questions exist, send only the real questions. If nothing useful changed, stay quiet unless the owner requested a daily confirmation.
- Do not repeat a question that was answered, deliberately skipped, or snoozed until its recorded review date unless new evidence changes it.
- Do not edit files without the previously agreed edit authority. A schedule does not expand permissions.

Suggested automation instruction:

```text
Audit my approved Obsidian or Markdown folders using the maintain-obsidian-vault skill. Read the maintenance log first so you do not repeat resolved questions. Check new or changed Markdown, orphan notes, unresolved links, meaningful missing connections, stale context, and conflicting authority. Ask exactly five high-value validation questions in one batch. Include clickable links, one recommendation, a brief reason, and the exact decision needed. If fewer than five real questions exist, ask only those. Stay quiet when nothing useful changed unless I requested a daily confirmation. Do not delete, move, rename, publish, upload, or edit outside the approved scope.
```

## Completion standard

A review cycle is complete only when:

- the inspected scope and access mode are stated;
- every reported finding is tied to real file evidence;
- approved edits were applied and rechecked;
- the audit log was updated or the lack of log access was disclosed;
- unresolved items and the next review point are clear;
- no deletion, upload, publication, or permission expansion was implied.

## Boundaries

- The recipient's vault is the recipient's private context. Do not copy another person's identity, company facts, private rules, or answers into it.
- Never upload vault contents, filenames, extracted text, reports, or metadata unless the owner explicitly requests that destination and understands what will be shared.
- Do not treat backlinks as proof that a note is true, current, or authoritative.
- Do not make mass links from keyword matches.
- Do not silently overwrite conflicting facts. Ask the owner.
- Do not expose secrets found during an audit. Stop, identify the file at the minimum necessary level, and recommend moving the secret to an appropriate secure store.

## Attribution

Created by Paul E. Remollena as part of Kairos Public. Licensed under the MIT License.
