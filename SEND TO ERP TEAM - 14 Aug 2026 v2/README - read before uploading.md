# UPLOAD TO ERP — folders are Warehouse - Zone - Status

**Calibrated 14 Aug 2026 evening.** App portion = LIVE control sheet pulled 14 Aug 13:29 — includes every line the floor entered through 13–14 Aug (the 123 lines the data team flagged as missing are IN). VSRS = machine export 14 Aug 08:58. Putaway = sheet updated 10–14 Aug. HRR includes the closing walk (aisle 6 counted for the first time). Duplicate submission at RZ-DL4 removed (−8,979). Rejection-zone lines rerouted out of Stores-EE.

**READY** = upload its Raw Data tab (skip red held rows and blue QC-pending rows until their notes clear). **HELD** = cannot ship yet, reason inside. **NOT COUNTED** = placeholder.

Every workbook: Sheet 1 Raw Data (reconciliation view) · Sheet 2 Location Detail (line-level, for placing stock at Storage Locations) · Sheet 3 Discrepancies & To-Dos · Sheet 4 Info for Uploader. Amber = split (zone's share of an item that also sits elsewhere). Red = held (code not in item master). Blue = walker-flagged QC Pending.

| Folder | Rows | Counted units (master tie) | Note |
|---|---|---|---|
| Stores-EE - HRR - READY | 652 | 954,514.5 | live app + walk 14 Aug |
| Stores-EE - VSRS - READY | 622 | 869,312 | machine export 14 Aug 08:58 |
| Obsolete-EE - Scrap - READY | 7 | 175,329 | upload 'just in case' (Pavi 14 Aug); create warehouse 'Obsolete - EE' first; file shows 202,302 because 2 rows are pre-converted to master UOM |
| Stores-EE - 1st Floor - READY | 288 | 127,663 | confirmed 14 Aug |
| QC Rejection-EE - QC Rejection - READY | 292 | 103,873 | duplicate removed −8,979 |
| Stores-EE - Putaway - READY | 141 | 61,372.5 | new sheet 10–14 Aug |
| Stores-EE - Cold Storage - READY | 45 | 47,755 | file shows 5,927,984 because 16 rows are pre-converted to master UOM (drums→grams, bottles→ml, rolls→metres) — same stock, master units |
| Stores-EE - H1 - READY | 658 | 30,402 | 10 Aug boxes |
| Snowman-EE - Snowman - READY | 2 | 25,848 | ERP team must CREATE warehouse 'Snowman - EE' first (spaces — ERP convention) (Pavi ruling 14 Aug); pallet counts ledger-confirmed, cells-per-pallet assumed |
| QC Rejection-EE - Rejection Zone - READY | 147 | 19,465 | incl. 24 new lines 12–14 Aug |
| Stores-EE - Basement - READY | 130 | 16,119 | ties to live app |
| Stores-EE - GVT Store - READY | 2 | 1,600 | |
| Stores-EE - Cupboards - READY | 16 | 848 | |
| QC Pending-EE - QC Pending - READY | 3 | 280 | |
| Obsolete-EE - Obsolete - READY | 4 | 47 | upload 'just in case'; warehouse 'Obsolete - EE' to be created first |
| Stores-EE - Outside - READY | 1 | 11 | |
| Stores-EE - FG - NOT COUNTED | — | — | nothing there or moved to Stores |

**Grand total in counted units ties to the calibrated master: 2,434,439.0.**

**SPLIT RULE (critical):** amber rows are one zone's SHARE of an item that also sits in another zone of the SAME warehouse. ERP Stock Reconciliation SETS the balance — the ERP team must SUM the shares across zone files into one figure per item+warehouse. Uploading zone files one after another without summing erases the earlier share. The two cell codes (P0008794-A, P0002327-A: Cold Storage + GVT Store) are the highest-value case.

**Withheld from this package:** only Stores-EE - FG - NOT COUNTED (nothing there). (Cold Storage and Scrap files display master-UOM quantities where conversion factors are confirmed — the counted-unit figures above are the tie.)

**QC PENDING = TOP-UP (Pavi, 14 Aug):** QC_Pending - EE already holds stock in ERP. Do NOT Stock-Reconcile that warehouse to our figures — that flushes the existing balance. Post our QC Pending quantities as an ADDITION (Material Receipt), or reconcile to existing + ours. Applies to the QC Pending pack and any blue QC rows routed there.

**Rejection Zone = QC Rejection (Pavi, 14 Aug):** the two folders are the SAME physical area and the same warehouse. Treat their two files as one upload — SUM figures for any item appearing in both (amber rows flag them).

**Order of import:** 1) warehouses 'Snowman - EE' + 'Obsolete - EE' · 2) storage-locations CSV · 3) 'Item check list (5 gates)' — create missing items, decide the batch/serial approach (286 of our uploaded codes are batch/serial-tracked = 787,217 units, qty-only upload) and the valuation-rate + difference-account questions with Finance · 4) stock packs, posting date 14 Aug 2026, all zones of a warehouse together.

Classification for planning: usable 2,104,762 · QC Pending 5,115 · rejected/scrap/obsolete 298,714 · offsite Snowman 25,848. SCM plans ONLY from the SCM report's PLAN WITH THIS column / the STOCK CHECKER.

ERP Stock Reconciliation SETS balances per item+warehouse — upload all zones of a warehouse the same day. Traceability deferred (13 Aug). Material moves daily: every movement through the app, packs regenerated never edited. 15 Aug audit plan closes the last ~3% (see AUDIT PLAN PDF + SIGN-OFF workbook).

**Location mapping:** every count location resolves via the table in 'UPLOAD FIRST - location notes.md' — no location should need a question back.

**UOM names:** see the 'UOM rename table' tab in the Item check list before importing.

**Contact & rejects:** all rulings — Pavi (pavilan@exponent.energy). Task force 15 Aug: Arun (arunkumar@exponent.energy), Tejas (tejas.bl@exponent.energy). Send any import reject list to Pavi the same day — files regenerate the same evening. Still open from Finance: difference account name + rate policy for the 597 unrated codes. Still open from Pavi (15 Aug): blue-row destination, P0015846-A unit.
