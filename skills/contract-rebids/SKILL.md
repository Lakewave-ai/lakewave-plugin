---
name: contract-rebids
description: Find public-sector contracts that are ending soon (state, county, city, K-12 and higher education) with Lakewave, then the people to contact about the rebid. Use when the user asks about expiring government contracts, rebids, renewals, competitive takeouts, incumbent vendors, or SLED opportunities in a state or category.
---

# Public-sector rebids and competitive takeouts

A contract that is ending is a purchase the agency has to make again. Lakewave lists them with the agency, the incumbent vendor, the title, the end date, the amount where public, and a source link. Looking them up is free.

## Steps

1. **Set the window.** Ask for states (two-letter codes, such as `CA,TX`), how far ahead to look (`months`, default 6) and any terms such as a product, vendor or category (`terms`, for example `network`, `firewall`, `Cisco`). `tech_only` is on by default; turn it off for non-technology categories. Set `statewide_only` for statewide vehicles only.
2. **Pull the list** with `contracts_ending`. Use `page` for more results.
3. **Rank for the user.** Group by agency or incumbent, sort by end date, and call out the largest amounts and the contracts held by a competitor of the user. Always keep the source link so the user can check the record.
4. **Offer the people step.** For the agencies the user picks, offer to find the buyers with `find_people` (for example IT director, CIO, procurement manager), following the prospect-accounts skill and its budget check. That step costs 4 credits per verified person.

## Rules

- Report dates, amounts and vendors exactly as returned. Say "not listed" rather than estimating a missing amount.
- End dates can change through extensions; suggest the user confirm with the source link before committing to a pursuit.
