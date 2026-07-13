# GenoSphere MCP — Inbound Access Workflow

This repo documents the launch-phase workflow for handling inbound access requests to the **Helix GenoSphere™ MCP connector** (the Anthropic/Claude directory listing).

## View the diagram

The workflow is a self-contained HTML page: [`index.html`](index.html). With GitHub Pages enabled, it renders live at:

**https://jayshah-eng.github.io/genosphere-mcp-access-workflow/**

## The flow at a glance

1. **Intake — three channels**
   - **A. Website form** (HubSpot, linked from the connector listing + resource page)
   - **B. Email** to the centralized alias `mcp@helix.com`
   - **C. Other sources** (other Helix pages, direct emails to reps, referrals, event leads, Anthropic-directory clicks) — all funneled to `mcp@helix.com`
2. **Triage** — form submissions triaged by Marketing (Jay Shah & Charlotte Franco); email/other flagged by the `mcp@helix.com` inbox team. Both route to Life Sciences or Health Systems.
3. **Routing** — the segment owner (LS BD, or HS BD / site DA) qualifies the requester; new prospects get a demo, slides, and NDA.
4. **Demo meeting** — run by Basil Khuder / Product with BD & DA support: MCP overview slides, how-to-access walkthrough, and a brief live demo.
5. **Provisioning** — BD and/or DAs confirm eligibility, enterprise/ZDR agreement, and T&Cs, then hand off to access owners:
   - **Life Sciences** — centralized: BD files a DEX ticket; DEX adds the `anthropic-enterprise-mcp` group.
   - **Health Systems / HRN** — site-controlled: the site adds the MCP group per user, like Explorer/Genesis today.
6. **Technical authorization** — the connector verifies group + enterprise/ZDR + current T&Cs on connect and on every tool call; access is Claude-only, read-only, and aggregate-only.

## Key rules

- No user gets access on Day 1 — everyone needs a new MCP-specific IdP group, including existing Explorer users.
- All serviceable partners must have an Anthropic enterprise agreement with zero-data retention, via a corporate (not personal) Claude account.
- Out-of-region (outside North America & Europe), academic, and general-public requests are not serviceable at launch — they are logged to the interested-parties list.

---

*Internal working document. Reflects the workflow discussed in the LSG bi-weekly (June 29, 2026) and the Life Sciences cross-functional (June 26, 2026). Provisioning owners and the exact ticketing path are to be finalized by the group.*
