# GenoSphere MCP — Inbound Access Workflow

This repo documents the launch-phase workflow for handling inbound access requests to the **Helix GenoSphere™ MCP connector** (the Anthropic/Claude directory listing).

## View the diagram

The workflow is a self-contained HTML page: [`index.html`](index.html). With GitHub Pages enabled, it renders live at:

**https://jayshah-eng.github.io/genosphere-mcp-access-workflow/**

The page has two tabs: **Overview (all segments)** and **Health Systems — detailed**.

## Overview flow (all segments)

1. **Intake — three channels**
   - **A. Website form** ([MCP landing page](https://www.helix.com/resources/helix-genosphere-claude-connector) — HubSpot form: name, email, institution; self-selects segment)
   - **B. Email** to the centralized alias `mcp@helix.com`
   - **C. Other sources** (other Helix pages, direct emails to reps, referrals, event leads, directory clicks, Commercial/Partner Success) — all funneled to `mcp@helix.com`
2. **Triage** — form submissions triaged by Marketing (Jay Shah & Charlotte Franco); email/other flagged by the `mcp@helix.com` inbox team; tracked in Excel. Both route to Life Sciences or Health Systems.
3. **Routing** — the commercial owner takes the lead: LS BD for Life Sciences, site DA / Partner Success for Health Systems (like Cohort Builder Explorer).
4. **Legal gate — confirmed BEFORE any demo** *(per Legal, July 14 2026)*
   - **NDA by segment:** LS new prospects sign an institutional NDA (also the lead-gen step); Health Systems partners need **no new NDA** — they're covered by existing collaboration/confidentiality agreements, since the MCP is treated as a feature of the research platform.
   - **ZDR decision (non-negotiable):** does the institution have a Zero-Data-Retention agreement with Anthropic? **No → stop**, don't demo (they can't use it); optionally offer Explorer and log to the [MCP access lead list](https://docs.google.com/spreadsheets/d/11GrxYLOw6jAje_-Yb05B-VQrQCz71MRvH91F1zcghvs/edit). **Yes → proceed**, sending an FYI up front that written ZDR confirmation + platform T&Cs are required (take-it-or-leave-it).
5. **Demo meeting** — MCP overview slides + one access slide + a brief live demo in Claude, at DA discretion (defer until requirements confirmed, or run earlier for strong use cases; JOCs are a natural venue). Run by Basil Khuder / Product (technical + demo only).
6. **Provisioning** — the institution signs the **GenoSphere MCP Access Agreement** (the ZDR side letter; someone with authority, confirms Anthropic ZDR), driven by the commercial owner. Then access is added:
   - **Life Sciences** — centralized: LS files a [DEX ticket](https://myhelix.atlassian.net/servicedesk/customer/portal/26/group/71/create/10929); DEX adds the `anthropic-enterprise-mcp` group per named user.
   - **Health Systems / HRN** — site-controlled: DA files a SUPP ticket → DEX adds the partner to the approved MCP list → partner IT adds users to the MCP group via their Explorer SSO (see below).
7. **Individual activation** — each user enables the connector in Claude → Okta sign-in → accepts platform T&Cs at account creation (checkbox, no DocuSign). The connector verifies group + ZDR + T&Cs on connect and on every tool call; access is Claude-only, read-only, and aggregate-only.

## Health Systems / HRN — detailed workflow

For existing HRN partners, the MCP is treated as a feature of the research platform, so access builds on the Explorer SSO the site already controls (per Partner Success / Cindy).

1. **Partner initiates interest** via Commercial, Partner Success, or the webform.
2. **Partner Success logs the partner** to the [intake tracker](https://docs.google.com/spreadsheets/d/11GrxYLOw6jAje_-Yb05B-VQrQCz71MRvH91F1zcghvs/edit).
3. **DA responds with intro + requirements:** (a) Explorer SSO access, (b) Claude enterprise customer with zero data retention, (c) will sign Helix's ZDR agreement.
4. **Demo — at DA discretion:** defer until requirements are confirmed, or demo earlier for strong interest. JOCs suit a Partner Success demo-lite; Basil supports larger technical groups.
5. **DA submits a SUPP ticket** once requirements are confirmed — partner name, confirmation of Explorer SSO access (just the SSO; users need not be in the Explorer group yet), and the action "Need access to MCP Connector." If no Explorer SSO, complete the Explorer steps first.
6. **DEX adds the partner** to the approved list for MCP.
7. **Partner IT adds users** to the "MCP" user group through their Explorer SSO (site-controlled, like Explorer/Genesis).
8. **Partner IT distributes access** via each user's Claude enterprise account (updates Claude configuration).
9. **User authenticates** following the GenoSphere MCP Getting Started Guide (enable connector → Okta → accept T&Cs).

**Access requirements (all three):** Explorer SSO access · Claude enterprise + zero data retention · signed Helix ZDR agreement.

## Key rules & legal notes

- **ZDR is the gate.** Confirm an Anthropic ZDR agreement (non-negotiable) *before* scheduling any demo — don't waste a demo on someone who can't use the tool.
- **NDA differs by segment.** LS new prospects sign an institutional NDA (lead-gen); HS partners are already covered by collaboration/confidentiality agreements — no new NDA.
- **Two consent levels.** The institution signs the ZDR side letter; each individual accepts platform T&Cs at account creation (checkbox, no signature).
- **Owners.** The commercial owner (DA/Partner Success for HS, LS BD for LS) drives legal prerequisites — Basil is technical/demo only.
- **Open items.** Confirm marketplace-initiated access still enforces T&Cs (Nicole/Matt); clarify SSO for MCP (Jim); unified T&Cs still in development (Legal).

## Links & resources

- [MCP connector landing page](https://www.helix.com/resources/helix-genosphere-claude-connector) — public overview + request form
- [DEX access ticket](https://myhelix.atlassian.net/servicedesk/customer/portal/26/group/71/create/10929) — request the `anthropic-enterprise-mcp` group (LS path)
- [MCP access lead / intake tracker](https://docs.google.com/spreadsheets/d/11GrxYLOw6jAje_-Yb05B-VQrQCz71MRvH91F1zcghvs/edit) — log inbound & not-yet-eligible leads
- **GenoSphere MCP Access Agreement** — the ZDR side letter signed by the institution (Helix internal draft, 2026-07-10)
- **GenoSphere MCP Getting Started Guide** — end-user authentication steps

---

*Internal working document. Reflects Legal input from J. Shah / M. Ziv (July 14, 2026), Health Systems onboarding steps (Partner Success / Cindy), the LSG bi-weekly (June 29, 2026), and the Life Sciences cross-functional (June 26, 2026).*
