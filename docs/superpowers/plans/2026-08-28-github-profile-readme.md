# GitHub Profile README Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create the `README.md` for the `ozykhan/ozykhan` special profile repo so it renders as Faruk's profile landing page, then publish it to GitHub.

**Architecture:** A single static `README.md` at the repo root. No workflows, no scripts. Badges come from shields.io, the stats card from github-readme-stats.vercel.app with `theme=transparent` so it reads correctly in both GitHub light and dark themes.

**Tech Stack:** GitHub-flavored Markdown, shields.io badges, github-readme-stats, `gh` CLI for publishing.

## Global Constraints

- Title is **Software Engineer** — never "Infrastructure & Platform Engineer".
- Public email is `fcanozkan@gmail.com` (not f.canozkan@gmail.com).
- Contact handles: `linkedin.com/in/fcanozkan`, `x.com/fcanozkan`, GitHub `ozykhan`.
- Exactly one stats card. No streak counters, typing animations, visitor counters, trophy walls, or repo pin cards.
- Facts must match the SWE resume (v9 UK/EU): TypeScript/Node.js and Go backend services on AWS and Kubernetes; 5+ years at startups; 40K-node decentralized inference network telemetry backend; hardware-to-cloud background; currently building SEO Potion and Piper.
- Publishing to GitHub (Task 2) requires the user's explicit go-ahead in chat before creating the repo or pushing.

---

### Task 1: Write README.md and commit

**Files:**
- Create: `README.md` (repo root)

**Interfaces:**
- Consumes: nothing (first task).
- Produces: a committed `README.md` on `main` that Task 2 pushes verbatim.

- [ ] **Step 1: Verify the external links the README will reference**

Run:

```bash
for url in \
  "https://github.com/piperbox/piper" \
  "https://seopotion.co" \
  "https://x.com/fcanozkan" \
  "https://www.linkedin.com/in/fcanozkan" \
  "https://github-readme-stats.vercel.app/api?username=ozykhan&show_icons=true&theme=transparent&hide_border=true&rank_icon=github" \
  ; do echo "$url => $(curl -s -o /dev/null -w '%{http_code}' -L --max-time 15 "$url")"; done
```

Expected: `200` for each (LinkedIn may return `999` and x.com may return `403` to bots — both are fine; those services block curl but the links work in browsers). If `piperbox/piper` or `seopotion.co` is not reachable with 200, STOP and report to the user instead of shipping a dead link.

- [ ] **Step 2: Create `README.md` with exactly this content**

````markdown
# Hi, I'm Faruk 👋

**Software engineer — from hardware to cloud.**

I build backend services in TypeScript/Node.js and Go on AWS and Kubernetes, deployed by pipelines I built myself. 5+ years at startups shipping products end to end — from an on-chain marketplace backend and a batch inference API to the telemetry backend of a 40K-node decentralized inference network. My engineering background runs from PCBs and Raspberry Pi fleets all the way up to multi-region clusters.

Currently building [SEO Potion](https://seopotion.co) and [Piper](https://github.com/piperbox/piper).

## Featured work

- **[Piper](https://github.com/piperbox/piper)** — developer-first open-source PaaS: `git push` to a live HTTPS URL on hardware you own, even a Raspberry Pi behind CGNAT with no public IP.
- **[SEO Potion](https://seopotion.co)** — AI SEO content platform, live in production. I own the backend and infrastructure: Hono API, SQS-triggered Lambda workers over MongoDB, defined in AWS CDK.
- **GEPA & HollowDB** — at Dria I built GEPA, a published evolutionary prompt-optimization algorithm running on Step Functions and Lambda, and HollowDB, a decentralized key-value store on Arweave that reached up to 90% of the chain's transactions.

## Tech stack

**Languages**

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-5FA04E?style=flat&logo=nodedotjs&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat&logo=go&logoColor=white)

**Data**

![Redis](https://img.shields.io/badge/Redis%20%2F%20KeyDB-FF4438?style=flat&logo=redis&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat&logo=mongodb&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white)

**Cloud (AWS)**

![Lambda](https://img.shields.io/badge/Lambda-FF9900?style=flat&logo=awslambda&logoColor=white)
![ECS](https://img.shields.io/badge/ECS-FF9900?style=flat&logo=amazonecs&logoColor=white)
![EKS](https://img.shields.io/badge/EKS-FF9900?style=flat&logo=amazoneks&logoColor=white)
![S3](https://img.shields.io/badge/S3-569A31?style=flat&logo=amazons3&logoColor=white)
![SQS](https://img.shields.io/badge/SQS-FF4F8B?style=flat&logo=amazonsqs&logoColor=white)
![Step Functions](https://img.shields.io/badge/Step%20Functions-FF4F8B?style=flat)
![CDK](https://img.shields.io/badge/CDK-232F3E?style=flat&logo=amazonwebservices&logoColor=white)

**Infrastructure**

![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![ArgoCD](https://img.shields.io/badge/ArgoCD-EF7B4D?style=flat&logo=argo&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat&logo=githubactions&logoColor=white)
![NATS](https://img.shields.io/badge/NATS-27AAE1?style=flat&logo=natsdotio&logoColor=white)
![Caddy](https://img.shields.io/badge/Caddy-1F88C0?style=flat&logo=caddy&logoColor=white)

## GitHub stats

![Faruk's GitHub stats](https://github-readme-stats.vercel.app/api?username=ozykhan&show_icons=true&theme=transparent&hide_border=true&rank_icon=github)

## Contact

📫 [fcanozkan@gmail.com](mailto:fcanozkan@gmail.com) · [LinkedIn](https://www.linkedin.com/in/fcanozkan) · [X](https://x.com/fcanozkan)
````

- [ ] **Step 3: Verify the badge URLs resolve**

Run:

```bash
grep -o 'https://img\.shields\.io/[^)]*' README.md | while read -r u; do echo "$u => $(curl -s -o /dev/null -w '%{http_code}' -L --max-time 15 "$u")"; done
```

Expected: `200` for every badge. A `404` means a bad `logo=` slug — fix the slug (check simpleicons.org) or drop the `logo` parameter for that badge, and re-run until all are 200.

- [ ] **Step 4: Visually check the rendered markdown**

Render `README.md` to HTML (any local renderer, e.g. open a preview in the browser pane) and confirm: headings render, all badges display as images, the stats card image loads, no raw markdown artifacts. This is a static file — the render check is the test.

- [ ] **Step 5: Commit**

```bash
git add README.md
git commit -m "Add GitHub profile README

Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>"
```

---

### Task 2: Publish to GitHub (gated on explicit user approval)

**Files:**
- None created or modified; pushes the existing `main` branch.

**Interfaces:**
- Consumes: the committed `README.md` from Task 1.
- Produces: a public `ozykhan/ozykhan` repo whose README renders on github.com/ozykhan.

- [ ] **Step 1: Confirm with the user in chat**

Ask: "Ready to publish — this creates the public repo `ozykhan/ozykhan` and pushes the README so it appears on your profile. Go ahead?" Do NOT proceed without a clear yes in chat. This step publishes public content and cannot be silently assumed.

- [ ] **Step 2: Check whether the repo already exists**

```bash
gh repo view ozykhan/ozykhan --json url 2>&1
```

Expected: either repo details (it exists — skip creation, just add the remote) or a "Could not resolve" error (create it in Step 3).

- [ ] **Step 3: Create the repo (only if missing) and push**

```bash
gh repo create ozykhan/ozykhan --public --source . --remote origin --push
```

If the repo already existed:

```bash
git remote add origin https://github.com/ozykhan/ozykhan.git
git push -u origin main
```

Expected: push succeeds with `main` tracking `origin/main`.

- [ ] **Step 4: Verify the profile renders**

Open `https://github.com/ozykhan` in the browser pane. Confirm the README appears on the profile page, badges and the stats card load, and section headings render. Report the result to the user with the profile URL.
