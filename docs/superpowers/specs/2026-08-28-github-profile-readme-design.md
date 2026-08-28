# GitHub Profile README — Design

**Date:** 2026-08-28
**Repo:** `ozykhan/ozykhan` (special profile repo; README.md renders on github.com/ozykhan)

## Purpose

A landing page for both recruiters and open-source visitors: who Faruk is, what he
builds, and how to reach him. Middle-ground visual density — tidy text plus badges
and one stats card, no clutter.

## Voice and framing

Title: **Software Engineer** (not Infrastructure & Platform Engineer). Tone and
facts follow the SWE resume (v9, UK/EU): backend services in TypeScript/Node.js
and Go on AWS and Kubernetes, deployed by pipelines he built himself; 5+ years at
startups shipping products end to end; engineering background that runs from
hardware to cloud.

## Structure (single README.md)

1. **Header** — `# Hi, I'm Faruk 👋` plus one-line title:
   *Software engineer — from hardware to cloud.*
2. **About** — ~4 lines drawn from the resume summary: TypeScript/Node.js and Go
   backend services on AWS/Kubernetes; on-chain marketplace backend and batch
   inference API to the telemetry backend of a 40K-node decentralized inference
   network; currently building SEO Potion and Piper.
3. **Featured work** — bullet list with links:
   - **Piper** (github.com/piperbox/piper) — developer-first open-source PaaS:
     `git push` to a live HTTPS URL on hardware you own, even behind CGNAT.
   - **SEO Potion** (seopotion.co) — AI SEO content platform; owns the backend
     and infrastructure (Hono API, Lambda workers, MongoDB, AWS CDK).
   - **GEPA** — published evolutionary prompt-optimization algorithm built on
     Step Functions and Lambda at Dria; plus **HollowDB**, a decentralized
     key-value store on Arweave that reached up to 90% of the chain's
     transactions.
4. **Tech stack** — shields.io badge rows grouped per the resume's skills table:
   - Languages: TypeScript, JavaScript, Node.js, Go
   - Data: Redis/KeyDB, PostgreSQL, MongoDB, SQLite
   - Cloud (AWS): Lambda, ECS, EKS, S3, SQS, Step Functions, CDK
   - Infrastructure: Kubernetes, Docker, ArgoCD, GitHub Actions, NATS, Caddy
5. **GitHub stats** — one `github-readme-stats` card for user `ozykhan`,
   `theme=default` with light/dark handled via the `#gh-dark-mode-only` /
   `#gh-light-mode-only` trick or `transparent` theme (implementation choice;
   keep to one card).
6. **Contact** — email `fcanozkan@gmail.com` · `linkedin.com/in/fcanozkan` ·
   `x.com/fcanozkan` (plain links or small badges, matching section 4's style).

## Out of scope

- No streak counters, typing animations, visitor counters, or trophy walls.
- No repo pin cards (Piper lives under `piperbox`; SEO Potion is closed source).
- No workflow automation (e.g. auto-updating blog feeds) — static README only.

## Delivery

Create `README.md` at repo root, commit, and (with user approval) create the
`ozykhan/ozykhan` GitHub repo if it doesn't exist and push.

## Success criteria

Renders correctly on the GitHub profile page in both light and dark themes; all
links resolve; content matches the SWE resume's claims.
