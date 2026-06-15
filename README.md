# takehome
A simple one page AI-powered alcohol label verification app as a React artifact.

# Requirements Analysis

After thouroughly reviewing the stakeholder interviews, a clear picture has emerged that there is an urgent need to develop a new Ai-based system to help TTB (Alcohol and Tobacco Tax and Trade Bureau) solving the COLA (Certificate of Label Approval) application efficiently in a timely manner. To address the pain points and user frsutrations, here is the list of key features that the new TTB Label Verification app must have:

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
Based on the requirements gathered, a simple one-page web application would be suffice.

## UX (User Experience)
The UI design is the following:
— An area for user to place a label picture for validation (top left)
— Display beverage type (beer, wine, distilled spirits) common elements on the left:
  Brand name
  Class/type designation
  Alcohol content (with some exceptions for certain wine/beer)
  Net contents
  Name and address of bottler/producer
  Country of origin for imports
  Government Health Warning Statement (mandatory on all alcohol beverages)
— Display the detailed label validation information (center + right side)

## Backend
i have an extended experiece using Anthropic API in the past for a LangChain project. 

# Implementation Details
## A Simple One-Page HTML
The index.html file is available in the source directory.

## Apache Web Server
The index.html is hosted by an Apache Web Server on a Ubuntu machine.

## System Diagram
<img width="289" height="336" alt="image" src="https://github.com/user-attachments/assets/a7057bb4-9bd4-46e3-b16e-a3af9a80a979" />


# How to Test

Upload any alcohol label photo (or an AI-generated one), fill in some application fields, and click Verify label. The batch mode works great with multiple images dropped at once.
