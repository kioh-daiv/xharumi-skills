---
name: xharumi-token-detox
description: Monitor token consumption, visualize costs, check ignore files, and automatically fix context issues. Use when the user asks to optimize tokens, check token usage, or complains about high token consumption.
---

# Token Detox

This skill diagnoses high token consumption, visualizes the impact of unignored files, and provides an interactive auto-remediation workflow.

## Step 1: Diagnose Context & Ignore Configs

1. Check if `.claudesignore` exists in the root of the project. If it doesn't, check `.gitignore`.
2. Inspect the contents of these ignore files to see what is currently blocked. Look for missing common culprits:
   - Built assets: `dist/`, `build/`, `.next/`, `out/`
   - Dependencies: `node_modules/`, `vendor/`
   - Media: `*.png`, `*.jpg`, `*.svg`, `*.mp4`, `*.pdf`
   - Large data: `*.csv`, `large_*.json`, SQL dumps.
   - Logs and coverage: `*.log`, `coverage/`

## Step 2: Search and Estimate Cost for Large Files

Find the largest files in the repository that might be accidentally pulled into context.
Run a command like:
`find . -type f -not -path '*/\.*' -not -path '*/node_modules/*' -not -path '*/dist/*' -exec du -k {} + | sort -nr | head -n 10`

**Cost Estimation Rule:**
Assume that **1 KB ≈ 250 tokens**.
Calculate the approximate token footprint of these top large files. Show the token estimation to the user to highlight the "pain" of reading these files.

## Step 3: Assess Conversation Length

Consider the recent context. Have you recently executed commands that dumped massive text to the terminal? Has this conversation been going on for a long time? 

## Step 4: Present Findings and Ask for Auto-Remediation

Output a concise summary using the structure below.
**CRITICAL:** 
1. **Multilingual Support:** You MUST output your response in the same language the user used to trigger the skill (e.g., English, Japanese, or Chinese). Translate the headings and descriptions of the format below accordingly.
2. **Confirmation:** At the very end of your response, you MUST ask the user if they want you to automatically fix the issues.

### 🔍 Token Diagnosis

**1. Ignore File Status:**
- [Findings about .claudesignore]

**2. Heavy Files in Repo (Cost Estimate):**
- [File A] - 100KB (~25,000 tokens per read)
- [File B] - 50KB (~12,500 tokens per read)
*(Only list files that might be unneeded in context)*

**3. Conversation Context:**
- [Assessment of conversation bloat]

---
### 🛠️ Auto-Remediation

I can automatically fix these issues for you right now. 
1. **Update Ignores:** I will append the missing rules to `.claudesignore`.
2. **Clear Context:** I will run `/compact` or `/clear` if your history is bloated.

**Would you like me to execute these fixes automatically? (Yes/No)**
*(If the user replies Yes, immediately apply the changes to .claudesignore and run the appropriate slash commands).*
