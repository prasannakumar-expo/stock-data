# Storage Locations — upload BEFORE the stock files

Order: 1) create warehouses 'Snowman - EE' AND 'Obsolete - EE' · 2) import this location CSV · 3) import the stock packs.

- VSRS: 49 tray locations VSS-07 style (55 trays in machine, 6 already in ERP). Count locations 'R01-C04 T18' map to VSS-18 (tray number is the location; rack-cell is the machine's internal address).
- Putaway: 15 PZ racks created. NOT created: 'PL-BL2' and 'PZAL1' (typos of PZ-BL2 / PZ-AL1 — fix in count), '`' (junk code).
- Basement: 37 locations (BS-* shelves as racks, BA-* as floor areas). NOT created: 'BS-DL-' and 'BS-EL-0' (malformed — fix in count, likely BS-DL1/BS-EL0).
- Cold Storage: 11 clean CS racks + CS-FRIDGE. NOT created: 5 combined codes ('CS-AL2&CS-AL1' etc. — multi-location count entries, stock maps to ZN-COLD until re-slotted), 'CS-DL-5' (malformed, likely CS-DL5 which IS created), bare 'FLOOR' (use ZN-COLD).
- Rejection: 36 RZ racks as Quarantine under 'Rejection - EE'. NOT created: 'FLOOR'/'Floor'/'Rejection table' (map to existing ZN-QCREJ), HRR-rack QC-pending positions (already exist under Stores - EE).
- 1st Floor: 4 areas 1STFLR-A..D. Count spelling '1 st FLOOR-A' maps to 1STFLR-A.
- Snowman: ZN-SNOWMAN-VRN requires warehouse 'Snowman - EE' created FIRST (note the spaces — matches ERP convention 'Stores - EE'). Order: warehouse → this location file → stock.
- Scrap/Obsolete now upload (Pavi 14 Aug): ZN-SCRAP and ZN-OBSOLETE under 'Obsolete - EE' (create warehouse first). Material moves out via stock issues when physically removed.
- HRR: all 432 rack positions already in ERP — nothing to create. Count's 'Floor'/'Floor1'/'Floor2' HRR lines map to ZN-HRR-DEFAULT.

## Mapping table — count location → ERP location (covers every location in the packs)

| In the packs | Post to |
|---|---|
| H1: 'FLOOR', 'S1', 'S5', 'T4' | ZN-H1 (all of H1 is one area) |
| 'Rejection store opposite' (QC Rejection, 2 lines) | ZN-QCREJ |
| Outside: 'B' | ZN-OUTSIDE |
| Scrap: 'REJECTION AREA' | ZN-SCRAP |
| Obsolete: 'Obsolete' | ZN-OBSOLETE |
| 'GVT STORE' | ZN-GVT |
| 'CUPBOARD 5' | CUPBOARD-5 |
| Cold: 'REFRIGERATOR' | CS-FRIDGE |
| 'SNOWMAN COLD STORE' | ZN-SNOWMAN-VRN |
| '1 st FLOOR-A/B/C/D' | 1STFLR-A/B/C/D |
| QC Pending pallets P0214/P0215/P0225/P0224/P0226 | racks 6AL4S2 / 6BL4S1 / 6BL4S2 / 6CL4S1 / 6CL4S2 (walk 14 Aug) |
| HRR blank locations (5 lines) / 'Floor', 'Floor1', 'Floor2' | ZN-HRR-DEFAULT |
| Putaway blank locations (37 lines) | PTWY-RACK-1 |
| VSRS 'R01-C04 T18' style | VSS-18 (tray number, zero-padded: T2 → VSS-02) |
| lowercase rack codes ('1al0s1') | uppercase (1AL0S1) |
| Typos PL-BL2 / PZAL1 / BS-DL- / BS-EL-0 / CS-DL-5 | being fixed in 15 Aug audit Job 6; park at zone default until then |
