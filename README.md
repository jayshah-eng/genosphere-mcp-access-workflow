# GenoSphere MCP — Inbound Access Workflow

This repo documents the launch-phase workflow for handling inbound access requests to the **Helix GenoSphere™ MCP connector** (the Anthropic/Claude directory listing).

## View the diagram

The workflow is a self-contained HTML page: [`index.html`](index.html). With GitHub Pages enabled, it renders live at:

**https://jayshah-eng.github.io/genosphere-mcp-access-workflow/**

## The flow at a glance

1. **Intake — three channels**
   - **A. Website form** (HubSpot — name, email, institution; self-selects segment)
   - **B. Email** to the centralized alias `mcp@helix.com`
   - **C. Other sources** (other Helix pages, direct emails to reps, referrals, event leads, directory clicks) — all funneled to `mcp@helix.com`
2. **Triage** — form submissions triaged by Marketing (Jay Shah & Charlotte Franco); email/other flagged by the `mcp@helix.com` inbox team; tracked in Excel. Both route to Life Sciences or Health Systems.
3. **Routing** — the commercial owner picks up the request: LS BD for Life Sciences, site DA for Health Systems (like Cohort Builder Explorer).
4. **Legal gate — confirmed BEFORE any demo** *(per Legal, July 14 2026)*
   - **NDA by segment:** LS new prospects sign an institutional NDA (also the lead-gen step); Health Systems partners need **no new NDA** — they're covered by existing collaboration/confidentiality agreements, since the MCP is treated as a feature of the research platform.
   - **ZDR decision (non-negotiable):** does the institution have a Zero-Data-Retention agreement with Anthropic? **No → stop**, don't demo (they can't use it); optionally offer Explorer and log as a lead. **Yes → proceed**, sending an FYI up front that written ZDR confirmation + platform T&Cs are required (take-it-or-leave-it).
5. **Demo meeting** — MCP overview slides + one access slide + a brief live demo in Claude. Run by Basil Khuder / Product (technical + demo only).
6. **Provisioning** — the institution signs the **ZDR side letter** (someone with authority; confirms Anthropic ZDR), driven by the commercial owner. Then access is added:
   - **Life Sciences** — centralized: LS files a DEX ticket; DEX adds the `anthropic-enterprise-mcp` group per named user.
   - **Health Systems / HRN** — site-controlled: the site adds the MCP group per named user, like Explorer/Genesis today.
7. **Individual activation** — each user enables the connector in Claude → Okta sign-in → accepts platform T&Cs at account creation (checkbox, no DocuSign). The connector verifies group + ZDR + T&Cs on connect and on every tool call; access is Claude-only, read-only, and aggregate-only.

## Key rules & legal notes

- **ZDR is the gate.** Confirm an Anthropic ZDR agreement (non-negotiable) *before* scheduling any demo — don't waste a demo on someone who can't use the tool.
- **NDA differs by segment.** LS new prospects sign an institutional NDA (lead-gen); HS partners are already covered by collaboration/confidentiality agreements — no new NDA.
- **Two consent levels.** The institution signs the ZDR side letter; each individual accepts platform T&Cs at account creation (checkbox, no signature).
- **Owners.** The commercial owner (DA for HS, LS BD for LS) drives legal prerequisites — Basil is technical/demo only.
- **Open items.** Confirm marketplace-initiated access still enforces T&Cs (Nicole/Matt); clarify SSO for MCP (Jim); unified T&Cs still in development (Legal).

---

*Internal working document. Reflects Legal input from J. Shah / M. Ziv (July 14, 2026), the LSG bi-weekly (June 29, 2026), and the Life Sciences cross-functional (June 26, 2026). To be finalized Thursday.*
