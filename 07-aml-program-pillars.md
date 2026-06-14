# 7. AML programme pillars

What a regulator actually examines. A licence is granted to a programme that
works on day one — policies plus the people, tooling and evidence to run them.

## The pillars
1. **Risk-based approach & EWRA** — a documented enterprise-wide risk assessment
   driving everything else; refreshed periodically.
2. **KYC / CDD / EDD** — identity verification, beneficial ownership, risk-tiered
   due diligence, ongoing review. (Checklist generator: `kyc_checklist.py` in the
   toolkit.)
3. **Sanctions & PEP screening** — at onboarding and ongoing rescreening, with
   fuzzy matching and a clear escalation path.
4. **Transaction monitoring** — documented, tunable rules + (optionally) anomaly
   models, with an alert→case workflow. Explainable, not black-box.
5. **Travel Rule** — see [section 6](06-travel-rule.md).
6. **SAR/STR reporting** — detection → MLRO decision → filing, with records.
7. **Governance & training** — clear roles, three lines of defence, regular staff
   training with evidence.
8. **Record-keeping** — typically 5+ years, retrievable for audit/examination.
9. **Independent audit** — periodic testing of control effectiveness.

## The evidence test
For each pillar, ask: *if an examiner asked me to prove this works, what would I
show?* If the answer is "the policy document" and nothing else, it's not done.
You need the policy **and** the system, the logs, the sample cases and the
training records.

## Tooling
Reference implementations of several pillars (monitoring, screening, scoring,
SAR drafting, reporting) live in the companion repository
[`regtech-toolkit`](https://github.com/Niphridium/regtech-toolkit) — all on
synthetic data.
