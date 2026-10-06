---
name: sync-chat-to-markdown
description: Reconcile completed or ongoing ChatGPT work into a private Markdown knowledge base, preserve validated decisions and next actions, show exact file diffs, and use separate confirmation gates for context sync and chat archiving. Use when a user wants conversations, decisions, outcomes, or project status consistently captured in Markdown before a chat is archived.
metadata:
  author: Paul E. Remollena
  license: MIT
  version: 1.0.0
---

# Sync Chat to Markdown

Keep important work from living only inside chat history. At a meaningful completion point, reconcile the conversation into the owner's private Markdown files, show exactly what changed, and ask separately before archiving the chat.

This skill supplies a workflow, not file or account access. Never claim a file was synchronized, a repository was updated, or a chat was archived unless the environment performed and verified that action.

## First-run setup

Before the first sync, establish these items. Reuse saved answers in later chats instead of asking again.

1. The exact Markdown folder, vault, repository, or uploaded-file set that the owner wants to maintain.
2. Which files or folders are authoritative, private, read-only, excluded, or safe to update.
3. Whether the AI has direct write access, read-only access, uploaded files only, or no usable file access.
4. The owner's preferred completion fields and exact sync and archive questions, if any.
5. Whether the environment can archive chats. File access does not authorize archiving, and archive access does not authorize file edits.

If no usable Markdown destination exists, provide a proposed update in the chat and clearly label it **Not yet saved**. Do not pretend that chat memory is a durable knowledge base.

## Keep a small context structure

Use the owner's existing structure when one exists. Do not create duplicate authorities merely to follow this example. For a new setup, recommend only the smallest useful files:

- A routing note: where the AI starts and which files control each topic.
- A user-context note: stable user preferences, communication style, and personal operating rules.
- One authority file per active person, company, project, or operating system when the subject is independently reusable.
- A handoff note: current work state, open decisions, owners, and the next checkpoint.
- A memory index: a short route to durable context, not a copy of every conversation.

Keep raw chat transcripts out of authority files unless the owner explicitly needs them as evidence. Save validated outcomes, decisions, corrections, owners, deadlines, limitations, and reusable lessons.

## Completion and sync gates

At the end of substantive work, first report:

- `Overall status`: Complete, Partially complete, Awaiting decision, or Blocked.
- `Completed`: what was actually done and verified.
- `Remaining`: required unfinished work, or None.
- `Decision needed`: the exact decision still required, or None.
- `Recommended next action`: one specific best move, marked required or optional.
- `Archive readiness`: whether this is a one-off completed chat or part of an active recurring process.

For a completed one-off task, say:

`Okay, I think we're done here. We completed the original request.`

Then ask:

`Do we proceed with sync context?`

A yes authorizes the Markdown reconciliation only. It does not authorize archiving, deleting, publishing, pushing to GitHub, or changing unrelated files.

After a verified sync report, ask:

`Do you really want to proceed with archiving?`

Archive only after that separate confirmation and only when the environment supports it. If the chat belongs to an active recurring audit, monitoring loop, automation, or continuing project, do not recommend archiving merely because one cycle ended.

## Sync workflow

1. Read enough of the full conversation to capture the original request, later corrections, approvals, rejected ideas, execution, proof, and unresolved work.
2. Search the smallest relevant Markdown area before creating a file. Prefer the current specific authority over a new note.
3. Classify each material item:
   - confirmed current;
   - already recorded;
   - exploratory or proposed;
   - historical;
   - superseded or rejected;
   - conflicting;
   - unclear;
   - sensitive or restricted.
4. Promote only confirmed, verified, reusable, or provenance-worthy information. Do not promote praise, repetition, generic advice, unused drafts, credentials, or personal data that belongs in a restricted file.
5. Update the smallest relevant files. Preserve existing headings, links, naming conventions, privacy classifications, and unrelated content.
6. Re-read every changed file and run the five-way check below.
7. Show every changed Markdown file with a clickable link when supported, exact `+added / -removed` counts, and the relevant unified diff. If nothing changed, state `No Markdown file changed` and explain why.
8. Recheck required work and only then request the separate archive confirmation.

## Five-way reconciliation check

Before reporting a sync as complete, verify:

1. **Instruction to action:** Every material request is marked done, not done, or changed.
2. **Corrections and supersessions:** Later corrections control, and rejected or replaced ideas are not restored as current.
3. **Execution and proof:** Discussion, approval, attempted work, verified implementation, and live results are clearly distinguished.
4. **Retrieval and continuity:** A future chat can find the right authority, owner, current state, next action, and checkpoint without rereading the whole conversation.
5. **Transfer safety and relevance:** Private or recipient-specific facts stay in the correct restricted files; generic instructions remain free of another person's identity, company data, credentials, or private context.

If a material conflict or unclear fact would change the record, pause that promotion and ask one focused question. Continue safe updates that do not depend on the answer.

## Git and repository behavior

Editing local Markdown, committing changes, pushing to GitHub, and archiving a chat are separate actions.

- Never push private files to a public repository.
- Confirm repository visibility, destination, branch, and write authority before a push.
- Never store tokens, passwords, recovery codes, customer records, payment data, or authenticated sessions in Markdown or Git.
- Do not overwrite remote divergence or force-push. Stop and explain the conflict.
- After an authorized push, verify the remote commit and provide the exact review link.

## Failure behavior

- **Read-only access:** propose an exact patch and label it not applied.
- **Uploaded files only:** update only the supplied files and disclose that the rest of the knowledge base was not checked.
- **No archive control:** finish the sync, then tell the owner how to archive manually.
- **Write or verification failure:** state which files changed, which did not, and what must be retried. Do not claim completion.
- **Sensitive or conflicting content:** keep it out of general files and request the smallest necessary decision.

## Adoption recommendation

Use this skill in a supervised trial for several completed tasks before making it the default. Confirm that the chosen files, privacy boundaries, completion wording, sync question, diff format, and archive behavior fit the owner's actual ChatGPT workspace.

## Attribution

Created by Paul E. Remollena as part of Kairos Public. Licensed under the MIT License.
