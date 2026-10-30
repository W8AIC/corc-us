# Baofeng UV-5R CHIRP config: CORC edition

These are CHIRP programming files for the **Baofeng UV-5R**. They hold every Central Ohio Radio Club (CORC) FM repeater that a UV-5R can use, plus all of the channels from DELARA's Delaware County config.

| File | What it is |
|---|---|
| `Baofeng_UV-5R_CORC_20261030.img` | CHIRP radio image (UV-5R). Open it in CHIRP and upload it to the radio. |
| `Baofeng_UV-5R_CORC_20261030.csv` | The same channels in CHIRP's standard CSV format, with a source note in the Comment column for each CORC channel. |

> **Please verify before use.** Repeater details change. Check each CORC channel against https://corc.us and with club officers before you program a radio or share this file. You are responsible for transmitting legally on the frequencies you program.

## Loading it in CHIRP (chirp-next)

**Option A, the image (.img).** This keeps DELARA's radio settings.
1. In CHIRP, choose **File > Open** and select `Baofeng_UV-5R_CORC_20261030.img`.
2. Connect the programming cable and choose **Radio > Upload To Radio**. Pick Vendor *Baofeng*, Model *UV-5R*, and your serial port.

**Option B, the CSV (.csv).** Use this for other radio models, or to merge the channels into your own config.
1. Download your radio first with **Radio > Download From Radio**. That gives you a backup and a valid image for your model.
2. Choose **File > Import** and select `Baofeng_UV-5R_CORC_20261030.csv`. Review the channels it brings in, then use **Radio > Upload To Radio**.

Save a backup of your radio's original image before you upload anything.

## CORC channels

All of the CORC repeaters were already in DELARA's file, so no new memory slots were used. The CORC channels were updated in place and given clear `CORC…` names (7 characters at most). Frequencies, offsets, and tones were checked against corc.us and are unchanged. Channel numbers stay the same, so there are no duplicates.

| Ch | New name (old) | Call | Output | Offset | Tone (CHIRP mode) | Location (corc.us) |
|---|---|---|---|---|---|---|
| 11 | CORC76 (W8AIC/V) | W8AIC | 146.760 | −0.6 (in 146.160) | 123.0 (TSQL) | Broad & High, Columbus; AUX TX Oakland Park; voted receivers at Delaware Co., Jersey/Licking Co., Canal Winchester, I-71 & Broad, Bellefontaine, Hilliard, Twin Rivers, Williamsport. CORC Tech Net. |
| 12 | CORC97 (W8AIC/T) | W8RRJ | 146.970 | −0.6 (in 146.370) | 123.0 (TSQL) | Oakland Park; receivers at Delaware Co., Jersey/Licking Co., Canal Winchester, I-71 & Broad |
| 20 | CORC33 (W8NBA) | W8NBA | 147.330 | +0.6 (in 147.930) | 123.0 (TSQL) | Jersey/Licking Co.; receivers at Delaware, Jersey/Licking, Pataskala, I-71 & Broad. IRLP node 8094 |
| 43 | CORC444 (W8AIC/U) | W8AIC | 444.200 | +5.0 (in 449.200) | 151.4 (TSQL) | Broad & High Sts. |
| 44 | CORC442 (K8NIO) | K8NIO | 442.800 | +5.0 (in 447.800) | 151.4 (Tone, TX only) | I-71 & I-70 |

All of these are analog FM (wide). TSQL is used only where RepeaterBook lists a matching downlink tone. K8NIO lists no downlink tone, so that channel uses Tone (encode only).

### Sources
- corc.us repeater table: "CORC Repeater Information by Frequency & Location", WA3UOO, 11/21/2020: https://corc.us/CORC%20Repeater%20Info%20by%20Location-11-21-2020.pdf (linked from https://corc.us/page7.html)
- corc.us site map table (Jul 2014): https://corc.us/page7.html
- 146.76 Tech Net, PL 123.0: https://corc.us/page8.html
- 147.33 IRLP 8094: https://corc.us/page6a.html
- D-STAR (W8CMH): https://corc.us/page10.html
- Cross-check, RepeaterBook: [W8AIC 146.76](https://www.repeaterbook.com/repeaters/details.php?state_id=39&ID=5845), [W8AIC 444.2](https://www.repeaterbook.com/repeaters/details.php?state_id=39&ID=6635), [W8RRJ 146.97](https://www.repeaterbook.com/repeaters/details.php?state_id=39&ID=7205), [W8NBA 147.33](https://www.repeaterbook.com/repeaters/details.php?state_id=39&ID=6636), [K8NIO 442.8](https://www.repeaterbook.com/repeaters/details.php?state_id=39&ID=166)

## CORC repeaters the UV-5R can't use

| Call | Output | Details (corc.us) | Why not |
|---|---|---|---|
| W8RRJ | 52.700 (6 m) | Broad & High; inputs 52.940 (Jersey/Licking), 53.700 (Oakland Park), 51.700 (Powell–Steitz Rd) | 6 m band; the UV-5R covers only 136–174 and 400–520 MHz |
| W8CMH | 444.000 (+5, in 449.000) | I-71 & I-70, D-STAR | Digital D-STAR; the UV-5R is analog FM only |
| W8CMH | 145.490 (−0.6, in 144.890) | I-71 & I-70, D-STAR | Digital D-STAR; RepeaterBook currently shows it **off-air** |

## Open questions for the club
- **K8NIO 442.800:** corc.us lists it in the CORC repeater table, but RepeaterBook shows K8NIO as the sponsor, not CORC. It is named `CORC442` here. Rename it back to `K8NIO` if the club doesn't consider it a CORC machine.
- **146.97 call sign:** DELARA's file named it `W8AIC/T`. corc.us and RepeaterBook both list it as **W8RRJ**.
- **147.33 location:** corc.us says Jersey/Licking Co.; RepeaterBook says Pataskala (also in Licking Co.).
- **6 m:** RepeaterBook also lists W8RRJ **51.700 output / 50.700 input**. corc.us lists 51.700 as an *input* (Powell–Steitz Rd) for the 52.700 system. This doesn't affect the UV-5R.
- The corc.us table is dated 11/21/2020. Please confirm it is still current.

## Credits and license
This file is based on **`Baofeng_UV-5R_for_sharing_20251119.img`** by the **Delaware Amateur Radio Association (DELARA) / K8ES**: https://github.com/K8ES/radio-programming. That original is MIT licensed, © 2025 Delaware Amateur Radio Association, and the license notice must be kept with any copies. Except for the five channel renames above, every DELARA channel and radio setting is unchanged. A byte-level diff of the image shows that only those five name fields and CHIRP's metadata trailer changed.

Built with CHIRP-next from source (git commit `0b4076d9`, kk7ds/chirp) using its Python API: load the original image, rename the channels with `set_memory`, save, then reload and re-export to CSV to verify.
