README 
What this is

This archive contains Red code snippets extracted from Red Intermediate Guide and organized per chapter. Extraction relied on XML parsing of the DOCX and pattern-based detection of Red code (functions, refinements, series ops, I/O helpers, small CLIs, tests).

Source: 

Red Intermediate Guide

Folder layout

01 - Chapter 1/, 02 - Chapter 2/, …
Each chapter folder contains files like:

01-app.red — snippets that start with Red [ … ] or look like an entrypoint

02-save-safe.red — the atomic write helper

03-test-helper.red — the minimal expect harness

Other snippets are named by the first function found or fall back to snippet

Also included:

INDEX.md — human-readable list of all extracted files

manifest.json — machine-readable manifest of chapters and files

How I extracted the code

Parsed the DOCX XML and walked all paragraphs.

Marked any paragraph as “code” if it matched common Red patterns (e.g., function [, make map! [, do %, append, foreach, attempt, either/all/any, comments ;, %paths, round/to, copy/deep, collect/keep, switch, etc.), or if the paragraph style looked like a code style.

Grouped consecutive “code” paragraphs into a single block, split when narrative paragraphs resumed.

Assigned each block to the most recent Chapter N heading.

Saved each block as a .red file with a numbered prefix to preserve order.

Limits and accuracy notes

If a snippet is heavily mixed with prose or uses unusual formatting, it may not be picked up.

Short one-liners embedded inside sentences are ignored to avoid false positives.

The book’s content is long, so a few blocks may be split or merged if the original formatting blurred boundaries.

If you want, I can tighten the rules (for example, include any paragraph with a semicolon ; or %path), or broaden them to capture more edge cases.

How to use

You can drop any chapter folder into a Red project and open the .red files as references.

Many snippets are “building block” examples, not complete apps. Look for files named app.red or those beginning with Red [ … ] for entry points.
