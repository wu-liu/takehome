# takehome
A simple one page AI-powered alcohol label verification app as a React artifact.

# Requirements Analysis
This is a great take-home project spec. Let me build a solid AI-powered alcohol label verification app as a React artifact. I'll design the UI thoughtfully for the compliance agent audience (accessible, clear, efficient) and wire it to the Anthropic API for vision + text analysis.Now I'll build the full app. This is a substantial React artifact with the Anthropic API powering the vision analysis.Here's the full TTB Label Verification app, built to address everything from the stakeholder interviews. Here's what's packed in:

## Core verification
— upload any label image and the AI checks brand name, class/type, alcohol content, net contents, the government warning statement, and producer info against what you've entered from the COLA application. Results show pass/fail/warn per field with found vs. expected values and a timing readout (Sarah's "5 second" requirement is baked in — you'll see the elapsed time on each result card).

## Government warning is strict
— per Jenny's notes, the AI explicitly checks for `GOVERNMENT WARNING:` in all caps/bold, exact wording, and flags creative modifications as fails.

## Fuzzy judgment
— following Dave's concern about `STONE'S THROW` vs `Stone's Throw`, the prompt instructs the AI to treat obvious case/punctuation variants as WARNs rather than hard FAILs, while still flagging them for human review.

## Batch upload
— drop multiple images at once and the sidebar shows a queue with per-file progress. Addresses Janet's long-standing request from Seattle.

## Image quality handling
— if the label is at a bad angle or glare-obscured, the AI sets affected fields to WARN rather than rejecting outright, with an explanation in the agent notes.

## Agent notes section
— each result ends with 2–3 sentences of observations for the reviewer: unusual elements, image quality issues, things needing human judgment.


# System Design Considerations
## Overall Consideration
## UI
## Backend
# Implementation Details

# How to Build & Test

**To test it:** upload any alcohol label photo (or an AI-generated one), fill in some application fields, and click Verify label. The batch mode works great with multiple images dropped at once.
