# 6. Travel Rule implementation (FATF Recommendation 16)

The Travel Rule requires VASPs to collect and transmit originator and
beneficiary information with virtual-asset transfers above a threshold. Quoting
the rule is easy; operating it is where programmes struggle.

## What data must travel (IVMS101-style)
- **Originator:** name, account/wallet reference, and a physical address, national
  ID, or customer ID (per the regime's threshold rules).
- **Beneficiary:** name and account/wallet reference.

A simplified validator for these fields is in the companion repo
[`regtech-toolkit`](https://github.com/Niphridium/regtech-toolkit)
(`travel_rule_validator.py`).

## The hard parts (and how to handle them)
- **Interoperability** — counterparty VASPs use different messaging protocols
  (e.g. IVMS101 over various transports). Pick a protocol/provider that interoperates,
  and define a fallback when a counterparty can't receive data.
- **Unhosted / self-hosted wallets** — there's no VASP on the other side. Set a
  policy: risk-based collection of beneficiary info, optional wallet attribution
  checks, and limits/EDD for higher-risk cases.
- **The "sunrise" problem** — your jurisdiction enforces the rule before the
  counterparty's does. Document how you handle inbound/outbound transfers in that gap.
- **Thresholds** — apply the de-minimis threshold correctly; below it, reduced
  data may apply, but monitoring still does.

## Minimum viable controls
- [ ] Threshold logic implemented and tested
- [ ] Required-field validation on every transfer (block/queue on failure)
- [ ] Counterparty VASP due diligence before exchanging data
- [ ] Unhosted-wallet policy with risk-based EDD
- [ ] Record-keeping of transmitted/received data
