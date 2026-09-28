---
tags:
  - project
  - planning
  - demo
title: Q3 Product Launch Plan
created: 2026-05-01
status: in-progress
---

# 🚀 Q3 Product Launch Plan

## Overview

We're launching **NovaPay** — a contactless payment SDK for mobile developers — by **August 15, 2026**. This note tracks milestones, blockers, and open questions.

## Goals

- [ ] Ship public beta by July 1
- [ ] Onboard 10 design partners before launch
- [ ] Write full API documentation
- [ ] Record 3 demo videos (iOS, Android, React Native)
- [ ] Submit to Product Hunt on launch day

## Timeline

| Phase | Owner | Due |
|---|---|---|
| Core SDK feature freeze | Backend team | Jun 15 |
| Beta partner invites sent | Growth | Jun 20 |
| Docs site live | DevRel | Jul 10 |
| Marketing landing page | Design | Jul 25 |
| Press embargo lifted | PR | Aug 14 |
| Public launch | All | Aug 15 |

## Risks & Blockers

> [!warning] Open Blockers
> - Payment processor contract not signed yet — affects all beta testing
> - iOS App Store review time is unpredictable (7–14 days)
> - Two senior engineers are on leave in July

> [!tip] Mitigation Ideas
> - Start App Store submission by July 1 to absorb review delays
> - Use existing test merchant accounts for beta until contract finalises

## Decisions

| Decision | Owner | Date |
|---|---|---|
| Apple Pay deferred to v1.1 | Mohammed | May 20 |
| Biometric auth opt-in at launch, opt-out by v1.1 | Sara | May 20 |
| Webhook retry logic deferred to v1.1 | Mohammed | May 20 |
| Palette B (deep teal + warm white) selected for brand | Liam | May 20 |

## Open Questions

1. ~~Should we support **Apple Pay** at launch or defer to v1.1?~~ → Deferred to v1.1 ✅
2. What's our SLA commitment for the beta?
3. Do we need a separate staging environment for design partners?

## Action Items

- [x] Mohammed — Chase legal on processor contract (due May 20)
- [ ] Priya — Follow up with 3 beta prospects (due May 24)
- [ ] Liam — Share brand guidelines draft (due Jun 5)
- [ ] Sara — Confirm P1 iOS crash fix merged (due May 25)
- [ ] Mohammed — Schedule CEO logo review (due May 28)

## Notes from Last Sync (May 20)

- CEO confirmed budget for influencer campaign
- Design team needs 2 more weeks on brand refresh — brand guidelines due Jun 5
- Engineering estimates 6 weeks to close all P1 bugs
- 6 of 10 design partners confirmed; 3 prospects still in conversation
- P1 bug: iOS crash on 3DS auth — root cause found, fix in review, ETA May 25
- React Native bridge ~200ms overhead on Android — acceptable for launch, optimize in v1.1

## Related

- [[Research - Payment UX Trends]]
- [[Meeting Notes - May 20]]


---

feat/update-the-name