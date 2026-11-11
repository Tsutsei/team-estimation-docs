---
layout: page
title: User guide
permalink: /guide/
---

## Start a session
Open **Apps › Estimation Sessions › New session**, or start from where the work items are:
- backlog: **••• › Estimate the backlog**,
- a sprint: its **••• › Estimate this sprint**,
- work item search: **Apps › Estimate these work items**.

Then choose:
1. **Type** – *Sizing board* (everyone moves the cards on one shared board) or *Planning poker* (private votes, then a reveal).
2. Options of the sizing board: **Take turns** (one card per person, then the next person) and **Relative sizing** (lanes A, B, C… from small to large; the values are set at the end).
3. **Field** – where the estimate is saved: story points, another number field, the original time estimate, a single-line text field, or the priority.
4. **Scale** – Fibonacci, modified Fibonacci, powers of two, linear, T-shirt sizes saved as points, time scales, or **Custom** (for example `1, 2, 3, 5, 8` or `S=2, M=5, L=8`). Jira administrators can save a custom scale for everyone.
5. **Work items** – pick the space and "backlog", "open sprints", "future sprints" or "all unfinished", optionally only work items without an estimate. The choices write the JQL, which you can edit. **Find work items**, untick what you want to leave out (up to 300), and **Create session**.

Send the address of the session to your team – opening it joins the session.

## Sizing board
Drag a card to the lane with its size (or use the menu on the card). Everyone sees every move at once. Useful extras:
- **★** pins a card as a reference for its lane.
- **Examples** on a lane shows finished work items with that estimate.
- **Not sure** is a lane for cards that need a talk; they are not saved.
- With **Take turns**, the banner shows whose turn it is. Move one card or **Pass**; a moderator can skip someone.
- With **Relative sizing**, add lanes with **+ Lane** and finish with **Set lane values**.

## Planning poker (live or async)
1. Everyone drags the cards to the size they think is right. The votes are private: others only see that you voted.
2. A moderator clicks **Reveal votes** (or **Reveal** on one card). Cards with full agreement move to their lane. The others stay in "To discuss" and show everyone's vote.
3. Discuss and drag the card to the agreed size – or let **Use the majority** decide the rest (a tie goes to the larger estimate). **Vote again** hides a card and clears its votes for another round. Votes can still be changed after the reveal.

For async estimation simply leave the session open: people vote when they have time, and you reveal when enough votes are in.

## Save to Jira
A moderator clicks **Save to Jira**. The app compares with Jira first:
- estimates that are already the same are not written,
- estimates **changed in Jira during the session** are listed – tick the ones the session should overwrite,
- everything else is written to the estimate field, with your permissions.

If Jira refuses a work item, the reason is shown (most often the field is missing on the edit screen of that work type).

## Moderators
The creator of a session is its moderator. Click a participant to make them a co-moderator. Jira administrators can moderate every session. Moderators reveal, add or remove work items, close, reopen, delete and save.

**Results** shows the estimates and votes as a table to copy into a spreadsheet.
