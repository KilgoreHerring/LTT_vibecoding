# Shipping - Quick Reference

A short reference for the end-of-session conversation: what production usually looks like for an internal tool, and what the review and approval path involves if you wanted to take a prototype further.

This is deliberately generic. Every organisation has its own systems, teams, and policies - swap in your own where it matters.

---

## What Production Usually Looks Like

For most internal tools, the realistic shape of production is straightforward:

- **A web app on approved cloud hosting** - whatever your organisation has cleared for internal applications, rather than someone's laptop or a personal account.
- **Behind single sign-on** - users log in with their normal organisational identity, and access is controlled centrally.
- **With data in an approved store** - the information the tool relies on lives in a system your organisation already trusts and manages, not in a loose spreadsheet or an unapproved third-party service.

If you're imagining where your prototype would live in production, that's the picture: a hosted web app, behind your organisation's login, with data in an approved place.

---

## Security Review - the Short Version

Any new tool, built in-house or bought in, should go through an information-security review before it goes live. At a high level it covers:

- **Hosting and architecture** - where does the app run, how is it accessed, who can see it?
- **Authentication and access** - is it behind single sign-on? Who is authorised, and how is access granted and removed?
- **Data flow** - what data goes in, where does it go, and does anything leave the organisation?
- **Encryption** - in transit and at rest.
- **Third-party / vendor due diligence** - if a vendor is involved, what are their security credentials and contractual terms, and where does your data sit in their environment?
- **Logging and monitoring** - who can see what is happening with the tool, and how would a problem be spotted?

Whoever owns security in your organisation runs this. New tools generally don't get deployed without it.

---

## Data Classification - the One Question That Drives Everything

Before any of the above, the most important question is: **what data does the tool handle?**

A simple way to think about it is three tiers:

| Tier | What it means |
|---|---|
| **Public / non-confidential** | Information that could be shared outside the organisation without harm. |
| **Internal** | Day-to-day organisational information not meant for the public, but not especially sensitive. |
| **Confidential / restricted** | Sensitive, personal, or otherwise protected information that needs careful handling. |

This matters because public AI tools - including the Claude Code you used in this session - are typically only cleared for non-confidential content. That is exactly why the session uses synthetic or sample data rather than anything real.

If your prototype only ever needs public or non-confidential content, the path to production is light. The moment it touches confidential or restricted data, the conversation gets bigger and the review more thorough.

---

## The Path from Prototype to Pilot

A rough sketch of what taking an idea further looks like:

1. **Find a sponsor** - someone who actually wants the outcome and will back it.
2. **Route it through the right internal team** - whoever owns new tools in your organisation (innovation, IT, or similar).
3. **Security and data-protection review** - alongside any vendor due diligence if a third party is involved.
4. **A scoped pilot** - one team, a clear scope, and defined success criteria.
5. **Review and decide** - scale it, adjust it, or stop.

Short, honest, and specific beats a polished but vague answer every time.

---

## A Closing Note

Often the right answer isn't to build something new at all. If your organisation already has an approved tool that could be configured to do the job, that's usually a much shorter and safer path than a bespoke build. Worth asking the question before you commit to building from scratch.
