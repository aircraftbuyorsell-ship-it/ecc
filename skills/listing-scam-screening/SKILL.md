---
name: listing-scam-screening
description: Screens aircraft, engine, and parts listings and buyer/seller conversations in aviation marketplaces and sales groups for fraud signals (below-market pricing, deposit and fake-escrow schemes, stolen photos, registry mismatches, forged release certificates, overpayment scams) and recommends a moderation decision with verification steps. Use when approving posts in an aircraft sales group, when a member reports a suspicious listing, or before a buyer sends money.
license: MIT
metadata:
  version: 1.0.0
  origin: ECC
  domain: aviation
---

# Listing Scam Screening

Help moderators and buyers spot fraudulent aircraft, engine, and parts listings early, using evidence rather than gut feeling. Recommend a decision, but leave the final call to a human moderator.

## When to Use

- Reviewing posts waiting for approval in an aircraft sales group
- A member reports a listing or a seller as suspicious
- A buyer asks "is this legit?" before paying a deposit
- A seller gets an offer that looks too good (buyer-side scams)
- Reviewing engine or parts listings that rely on release paperwork

## How It Works

1. **Collect the evidence**: listing text, photos, price, seller profile facts (account age, history in the group), and any messages the buyer or seller shares.
2. **Check each signal group** in Core Knowledge. Record every signal found, with the exact evidence (quote or photo reference).
3. **Run the verification steps** that are possible with available tools: registry lookup, valuation comparison, reverse image search. Note which steps could not be run.
4. **Score the risk** using the Decision Framework.
5. **Write the recommendation** in the output format, including the private questions to send to the poster.

## Core Knowledge

### Signal groups

**Price**
- More than about 25–30% below comparable aircraft (same type, similar times and avionics) with no stated reason such as damage or a run-out engine
- Round "urgent" prices with a story: divorce, deployment, death in the family, relocation abroad

**Seller identity and profile**
- Recently created account, few connections, no aviation history in the group
- Profile name does not match the registered owner, and the poster is not a disclosed broker
- Many different aircraft types listed at bargain prices by the same account
- Profile location does not match the aircraft location, and the seller cannot explain it

**Registration and aircraft identity**
- Registration in the photos differs from the listing, or is edited out or blurred in every photo
- Registry record shows a different make, model, or serial number, or the registration is deregistered, cancelled, or reserved
- Serial number on the data plate photo does not match the registry
- The same photos appear in an older listing with a different registration, price, or seller

**Photos**
- Photos found elsewhere (reverse image search hits on other listings, manufacturer brochures, or old sales sites)
- Watermarks or logos from another dealer
- No photos of the logbooks, data plate, or powered-on panel, and the seller refuses to provide them
- Panel photo does not show the avionics claimed in the text

**Communication**
- Pushes to move off-platform quickly (to a messaging app or personal email)
- Cannot answer basic technical questions: TTAF, engine time since overhaul, last annual/ARC date, home airport
- Refuses a live video walk-around or an in-person viewing, or "the aircraft is in storage abroad and can't be seen"
- Sends logbook scans with inconsistent handwriting, dates, or signatures, or will only send selected pages

**Payment and closing**
- Asks for a deposit to "hold" the aircraft before any viewing or inspection
- Asks for payment to a personal account, a third party, crypto, or gift cards
- Insists on an escrow or title company they chose themselves, especially a recently registered website or a name that imitates a known aviation escrow company
- A "shipping agent" or "ferry company" handles delivery and must be paid up front
- Refuses an independent pre-buy inspection

**Engines and parts**
- Release certificates (FAA Form 8130-3, EASA Form 1) that are low resolution, have mismatched part or serial numbers, or come from a repair station that cannot be found
- Seller will not let the buyer contact the issuing repair station
- "Zero-time" or "new" claims without a traceable overhaul or manufacturer record

**Buyer-side scams (protecting sellers)**
- Overpayment: the "buyer" sends more than the price and asks for a refund of the difference
- Fake transfer confirmations or screenshots, with pressure to release logbooks or the aircraft before funds clear
- A "buyer's agent" or "inspector" the seller must pay first

### Verification steps

Use whichever are available. Always say which were run and which were not.

1. **Registry lookup**: compare registration, make, model, serial number, and status. US registrations are public in the FAA registry. In the EU, owner details are often restricted, so compare aircraft details only.
2. **Valuation comparison**: compare the asking price with a valuation tool or recent comparable sales, and state the size of the gap.
3. **Reverse image search** on two or three photos, including the panel.
4. **Proof-of-possession request** (sent privately): a photo of the data plate or the registration on the fuselage, next to a handwritten note with today's date and the group name, or a short live video walk-around.
5. **Escrow check**: tell the buyer to choose the escrow or title company themselves and to verify its phone number from an independent source, never from a link the seller sent.

## Decision Framework

| Risk | Typical evidence | Recommended action |
|------|------------------|--------------------|
| LOW | No signals, or one minor signal with a plausible explanation | Approve |
| MEDIUM | One or two moderate signals (new account, missing logbook photos, price gap with an explanation) | Hold the post and send the private verification questions. Approve once answered |
| HIGH | A strong signal (registry mismatch, stolen photos, deposit before viewing) or three or more moderate signals | Keep it hidden. Request proof of possession. Escalate to a senior admin |
| BLOCK | Confirmed stolen photos with a different registration, a confirmed registry mismatch the seller can't explain, a fake escrow site, or a payment request to a third party | Reject the post and recommend a ban to the admin team. Keep the evidence. Consider warning members who have already engaged |

A single strong signal outweighs several weak ones. A real seller can usually clear a MEDIUM rating within a day, so never treat MEDIUM as an accusation.

## Output Format

```markdown
## Scam Screening: [Year Make Model, Registration] by [poster]

**Risk: LOW / MEDIUM / HIGH / BLOCK**

### Signals found
- [signal group] [signal]. Evidence: "[quote]" / photo [n]

### Verification
- Registry lookup: [match / mismatch: details / not run]
- Valuation gap: [x% below/above comparable / not run]
- Reverse image search: [no hits / hits: where / not run]

### Private message to the poster
[Polite questions and verification requests. No accusations.]

### Recommendation
[Approve / Hold pending verification / Hide and escalate / Reject and recommend ban]
Final decision: moderator.
```

## Examples

**Listing:** 2008 Cirrus SR22 G3 listed at USD 120,000 by an account created three weeks ago. Seller says they are "working offshore" and asks for a USD 5,000 refundable deposit to an escrow website they link. The registration is blurred in all photos.

**Screening result:** Risk **BLOCK** if the escrow site checks out as newly registered or fake; **HIGH** before that check. Signals: price far below typical market for the type and year (confirm with a valuation tool); new account; "offshore" story; deposit before viewing; seller-chosen escrow link; registration hidden in every photo. Private message: ask for the registration, a data-plate photo with a dated note, and a live video call; tell the buyer to choose their own escrow company. Recommendation: keep hidden and escalate to a senior admin.

## Anti-Patterns

- **Public accusations.** Never call anyone a scammer in public comments. Hold or hide the post, handle it privately, and keep the evidence for the admin team.
- **Deciding instead of recommending.** A human moderator makes the final call on rejections and bans.
- **Signals without evidence.** Quote the evidence for every signal, or leave the signal out.
- **Reposting registry personal data.** Don't share owner names, addresses, or other personal data in the group, even when they reveal a mismatch.
- **Overstating checks.** If verification steps could not be run, say so. Never present an unchecked listing as "verified".
