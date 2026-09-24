# What Artikl never auto-fills

**For design-partner walks** · Artikl prepares · the CA decides · never auto-files · never touches GSTN

Use with the public demo: https://tingtingtong.github.io/artikl/demo/

---

## Maker vs checker

| Role | Who | Does |
|---|---|---|
| **Maker** | Artikl (+ articled clerk) | Extract, blank uncertain fields, raise exceptions |
| **Checker** | CA / partner | Clear / defer / drop every **high**; decide mediums; **sign off** |

Sign-off stays blocked while any high is open. There is no file button.

---

## We never auto-fill these (leave blank + exception)

| Topic | Why (notice / liability risk) | Exception code(s) |
|---|---|---|
| ITC eligibility | Blocked or doubtful credit claimed → notice | `ITC_UNCLEAR` |
| Place of supply | Wrong CGST/SGST vs IGST | `POS_AMBIGUOUS` |
| Reverse charge | GTA / RCM booked wrong | `RCM_SUSPECT` |
| Credit note vs invoice | Wrong voucher type in books | `CN_VS_INV` |
| Party GSTIN | Invalid / cancelled / missing | `GSTIN_INVALID` |
| Invoice not in 2B | Claiming ITC with no 2B line | `2B_UNMATCHED` |
| Tax / amount ≠ 2B | Partial match — don’t average | `2B_PARTIAL` |
| HSN vs rate fight | Wrong rate on face vs 2B | `HSN_RATE_AMBIG` |
| Party not in books | Wrong ledger / suspense junk | `PARTY_UNMAPPED` |
| Low extract confidence | Guessing invents numbers | `LOW_CONF_EXTRACT` |
| Unreadable doc | Dark / blurry WhatsApp image | `DOC_UNREADABLE` |
| Likely duplicate | Double-booking | `DUP_SUSPECT` |

**Rule:** blank is safer than a confident wrong number. The 95% accuracy bar is for **clean PDFs only** — messy dumps will exception more, and that is correct.

---

## What we will fill (when confidence is clear)

Party name, date, voucher type, taxable amount, tax breakup, HSN/SAC, GSTIN, narration — **only** when extract confidence clears the threshold **and** no high/medium rule forces a blank.

---

## What we never do (say every walk)

1. Never write to GSTN / never scrape the portal (2B is **client-uploaded**).  
2. Never auto-file GSTR-1 / 2B / 3B or any return.  
3. Never invent a value to clear an exception or to hit a fill-rate target.  
4. Never let sign-off succeed with open **high** exceptions.

---

## One line for the CA

*If Artikl isn’t sure, the cell stays empty and the reason is on the row. You decide. Filing stays with you on the portal.*
