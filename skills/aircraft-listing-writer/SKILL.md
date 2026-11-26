---
name: aircraft-listing-writer
description: Turns seller notes, spec sheets, or logbook summaries into a standard aircraft-for-sale listing (Facebook group post, full spec sheet, and one-line index entry) for piston, turboprop, jet, and helicopter sales. Use when drafting, cleaning up, or standardizing an aircraft listing, or when a seller asks what information a listing needs.
license: MIT
metadata:
  version: 1.0.0
  origin: ECC
  domain: aviation
---

# Aircraft Listing Writer

Write aircraft-for-sale listings in one consistent format, so buyers can compare aircraft at a glance and moderators can spot missing data quickly.

## When to Use

- A seller sends loose notes, a broker spec sheet, or photos of a panel and logbooks and wants a listing
- A listing needs to be standardized before it is approved in an aircraft sales group
- Someone asks "what should I include in my listing?"
- A listing must be shortened for a social post, or expanded into a full spec sheet

Do not use this skill to judge whether an aircraft is airworthy or to set a price. Valuation and airworthiness are separate decisions made by the buyer, an inspector, and a valuation source.

## How It Works

1. **Collect the facts.** Pull every figure from what the seller provided. Never invent, estimate, or "round up" a number.
2. **Fill the field list** below. Any required field the seller did not supply is written as `TBC by seller`. It is never left out silently.
3. **Run the consistency checks** (see Core Knowledge) and list anything that does not add up under "Questions for the seller".
4. **Produce the three outputs**: the social post, the full spec sheet, and the index line.
5. **Add the standard footer** (buyer due-diligence notice).

## Field List

### Required

| Field | Notes |
|-------|-------|
| Year, make, model | As shown on the data plate / registration certificate, e.g. `1978 Piper PA-28-181 Archer II` |
| Registration | Full registration mark, e.g. `N-XXXXX`, `OK-XXX`, `D-EXXX` |
| Price and currency | Always explicit: `USD 145,000`, `EUR 132,000`, or `Price on request`. Add `VAT paid` / `VAT not paid` / `VAT n/a` for aircraft in the EU |
| Location | City and country, plus ICAO airport code if known |
| TTAF | Total time airframe, hours, with the date of the logbook entry it comes from |
| Engine(s) | Make, model, and time since overhaul (SMOH / SFRM / STOH as applicable) or time since new (TSN). Turbines: TSN, CSN, and hot-section (HSI) status |
| Engine TBO | The manufacturer's recommended time between overhauls, so buyers can see remaining time |
| Propeller(s) | Make/model and time since overhaul (SPOH) or since new |
| Damage history | `No damage history (NDH)` only if the seller confirms it. Otherwise describe the damage and whether the repair is documented |
| Inspection status | Date of last annual (FAA) or ARC expiry (EASA Part-ML / Part-M), plus 100-hour or phase status if relevant |
| Logbooks | `Complete since new`, `Complete since <year>`, or a description of missing logs |
| Seller type | Owner, broker, or dealer |

### Recommended

| Field | Notes |
|-------|-------|
| Avionics | Full list. Call out ADS-B Out (US), 8.33 kHz radios and Mode S (Europe), GPS/WAAS/LPV approach capability, and autopilot model |
| Useful load / max takeoff weight | With units (lb or kg) |
| Paint and interior | Year done and condition out of 10 |
| Airworthiness directives (ADs) | Recurring ADs and any notable ones complied with |
| Hangared / tied down | Affects corrosion risk |
| Export / import status | Export-ready, deregistration needed, known import duties |
| Programs | Engine or maintenance programs (for turbines and jets) and whether they transfer |
| Reason for sale | Optional, but buyers trust it |

## Core Knowledge

### Consistency checks

Flag each failed check as a question for the seller. Do not "correct" the figure yourself.

- Engine time since overhaul must not exceed TTAF. Engine time since new may exceed TTAF only if the engine came from another airframe, so ask.
- If engine time since overhaul is greater than the TBO, the listing must say `past TBO` or `run-out`. Never hide it.
- Annual or ARC date older than 12 months means the inspection has lapsed. Write the actual date, never just "fresh annual".
- The registration prefix should match the stated registry country (for example `N` = USA, `OK` = Czech Republic, `D` = Germany, `G` = United Kingdom, `OE` = Austria, `SP` = Poland, `OM` = Slovakia, `HB` = Switzerland, `C` = Canada). An aircraft based in a different country from its registry is common, so note it but don't treat it as an error.
- The registration visible in the photos should match the listing.
- Avionics in the list should match what is visible in the panel photo.
- Every hour figure should come with the date it was recorded.

### Units and formatting

- Hours to one decimal place when the seller gives them (`2,431.6 hrs`). Otherwise whole hours.
- Dates as `YYYY-MM` or `YYYY-MM-DD`, never just "recent".
- Currency code before the amount (`EUR 89,500`), never a bare `$` or `€` symbol in an international group.
- Weights in lb or kg as the seller gives them. Do not convert unless asked, and if you do, show both.

### Social post rules

- Social feeds cut posts off after the first few lines, so the first three lines must carry year/make/model, price, location, TTAF, and engine time.
- Short lines, one fact per line, at most one emoji per line.
- No "best deal ever", "won't last", or other pressure language. It reads like a scam and gets reported.
- Contact through the group's messaging only. Don't post phone numbers or emails in the public text unless the seller explicitly asks.

## Output Formats

Produce all three unless asked for one.

### 1. Social post

```text
FOR SALE: <Year> <Make> <Model> | <Registration>
<Currency> <Price> | <City, Country (ICAO)>
TTAF <hrs> | Engine <SMOH/TSN> <hrs> (TBO <hrs>) | Prop <SPOH> <hrs>

Avionics: <short list>
Damage history: <NDH / description>
Annual/ARC: <date>
Logs: <status>

<One or two sentences on condition, from the seller's own words>

Seller: <owner/broker/dealer>. Message for logbook scans and viewing.
Buyers should arrange an independent pre-buy inspection and verify registration and title.
```

### 2. Full spec sheet

A markdown table with every field from the Field List, followed by:

- **Questions for the seller**: every `TBC by seller` field and every failed consistency check
- **Photo checklist**: exterior from all four sides, panel (powered on), engine bay, data plate, logbook pages showing the latest annual/ARC and engine overhaul

### 3. Index line

```text
<Year> | <Make> | <Model> | <Registration> | <Currency> <Price> | <Country> | TTAF <hrs> | <Engine time label> <hrs> | <NDH yes/no/TBC>
```

## Examples

**Input (seller notes):** "selling my archer, 78, 2400 tt, engine 650 since major, garmin 430w and gfc500, annual done in march, no accidents, 145k, based at LKPR"

**Output (social post):**

```text
FOR SALE: 1978 Piper PA-28-181 Archer II | TBC by seller
145,000 (currency TBC by seller) | Prague, Czech Republic (LKPR)
TTAF 2,400 hrs | Engine SMOH 650 hrs (TBO TBC by seller) | Prop TBC by seller

Avionics: Garmin GNS 430W, Garmin GFC 500 autopilot
Damage history: No damage history (seller confirms)
Annual/ARC: March (year TBC)
Logs: TBC by seller

Seller: owner. Message for logbook scans and viewing.
Buyers should arrange an independent pre-buy inspection and verify registration and title.
```

**Questions for the seller:** registration mark; currency ("145k" could be USD or EUR); prop make and time; year of the March annual/ARC; logbook completeness; engine model, so the TBO can be stated; date the 2,400-hour TTAF was recorded.

## Anti-Patterns

- **Implying airworthiness.** Never state or imply that an aircraft is airworthy, and never drop the pre-buy inspection notice.
- **Filling gaps with guesses.** Never invent or estimate figures. Unknown means `TBC by seller`.
- **Presenting seller claims as facts.** Attribute condition claims to the seller ("seller describes paint as 8/10").
- **Publishing registry personal data.** Don't put owner names, addresses, or phone numbers from registry records in the listing.
- **Hiding bad news.** Past-TBO engines, lapsed inspections, and damage history go in the listing, not in a later message.
