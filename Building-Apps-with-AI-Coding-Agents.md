# Building Apps with AI Coding Agents — Reference Card

SCSP AI+ Expo · May 9, 2026 · Drive Claude in plain English from the Claude desktop app.

---

## PRE-FLIGHT (30 SECONDS)

1. Open the **Claude desktop app**. Start a new **Code session** with `scsp-workshop` (on your desktop) as your working directory. If Claude asks for folder permission, say yes.
2. If you don't have a Claude plan: watch a neighbor or grab one of the 6 free Claude Pro 1-month codes at the front.

---

## 1 BUILD THE PAGE

> I have `facebook_combined.txt.gz` in this folder — the Stanford SNAP Facebook social network (~4,039 anonymized people, ~88k friendships). Look at the file, then propose a plan for an interactive website that visualizes it. **Before you write any code, ask me whatever questions you need** about what I want to see and who I'm building it for. Once we agree on the plan, build it — use the `frontend-design` skill from `github.com/anthropics/skills`, plain English, no jargon. Then start a local server so I can see it.

Claude will look at the data, ask you a few questions, then build the page and start a local server. Answer the questions however you like — there's no wrong answer.

---

## 2 ITERATE ON THE DESIGN

Pick one or write your own:

> Make it more polished — richer colors, hover tooltips with each person's name and friend count.

> Add a search box so I can jump to a specific person by ID.

> For each bridge person, show which friend groups they actually connect, with small color swatches.

---

## 3 DEPLOY TO THE WEB

> Get me ready to publish to GitHub. Install the GitHub command-line tool if I don't have it (use Homebrew on Mac, the official installer on Windows). Then walk me through signing in to my GitHub account.

> Now create a public GitHub repo for this folder and turn on GitHub Pages so anyone can visit the site. Wait until it's actually live, then tell me the URL.

Your URL will look like `https://<your-username>.github.io/scsp-workshop-demo/`

---

## 4 WHEN SOMETHING GOES WRONG

- Paste the error verbatim. Don't paraphrase. *"I got this error: \<paste\>. Look at the file and fix it."*
- **Ask Claude to read first.** *"Look at the file before changing it."*
- **Confused?** Start a new chat to reset.
- **Claude can't help?** Raise a hand or ask a neighbor.

---

## USE SKILL FILES TO EXTEND CLAUDE CODE'S CAPABILITIES

Skills are short instruction files Claude can fetch and follow. Tell Claude *"use the X skill from github.com/anthropics/skills"* and it will pull it in for the rest of your chat.

- `frontend-design` — distinctive, polished web UIs
- `pdf`, `docx`, `xlsx`, `pptx` — read/write those file types
- `canvas-design` — posters, static visual art

Full list: `github.com/anthropics/skills/tree/main/skills`

---

## DATA SAFETY ON CLAUDE

- **Opt out of training data.** Claude.ai → Settings → Privacy → "Help improve Claude" toggle off.
- **The lethal trifecta** ⚠: untrusted input + private data + external action. An attacker's prompt hidden inside the input (a webpage, a doc, an email) can hijack the agent. Be careful what commands you let the agent run when it's working with internet data and private data at the same time.
- **Never paste secrets** (passwords, API keys, tokens) into a prompt. If a file has them, ask Claude to ignore those lines.

---

## STRETCH CHALLENGES (IF YOU FINISH EARLY)

**Beginner** &nbsp; Change the font · add your name · add a GitHub footer link

**Intermediate** &nbsp; Add a degree histogram · make node size scale with degree · add a search box

**Advanced** &nbsp; Compute clustering coefficient · grab `facebook.tar.gz` from the SNAP website and compare the algorithm's groups to the 193 hand-labeled circles · analyze how friends cluster by school, employer, hometown, or birth year
