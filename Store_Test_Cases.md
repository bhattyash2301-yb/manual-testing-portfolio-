# STORE MODULE – TEST CASE DOCUMENT

| Company | Branch | Software Version | Financial Year |
|---|---|---|---|
| ABC | XYZ | 4.1.2.4 | 2025-2026 |

---

## TC-01 — Create new purchase entry with valid data

| Module | Priority | Status | Dept Code | Prod Type / Process | Tested By | Tested Date |
|---|---|---|---|---|---|---|
| Store Purchase Entry | High | PASS | STORE | — | PRAFUL | 11/08/2026 |

**Precondition:** User logged in as PRAFUL (SURAT ADMIN)

**Test Steps**

1. Open 'Store Purchase Entry'
2. Click 'Entry Details' tab
3. Enter Purchase Date: 11/AUG/2026
4. Enter Purchase No: 12331
5. Enter P. Invoice No: 1 | Term Days: 90
6. Select Party: MOUNTAIN DIAM (RINKAL)
7. Select Branch: Kakadiam LLP
8. Select Item: KATORA (S.NO.), Sub Item: MATHALA (ANJANI)
9. Enter Qty: 5 | Rate: 3000
10. Click 'Add' → Click 'Save'

**Test Data / Input Values**

- Purchase Date: 11/AUG/2026
- Purchase No: 12331 | Challan No: 1
- Party: MOUNTAIN DIAM (RINKAL)
- Branch: Kakadiam LLP
- Item: KATORA (S.NO.)
- Sub Item: MATHALA (ANJANI)
- Qty: 5 | Rate: 3000
- Gross Amt: 15,000 | Net Amt: 15,000
- CGST/SGST/IGST: 0 | Due Date: 09/NOV/2026

**Expected Result**

- Entry saved successfully with Purchase No 12331
- Grid shows: KATORA (S.NO.) | MATHALA (ANJANI)
- Qty: 5 | Rate: 3000 | Gross Amt: 15,000.000
- Net Amount: 15,000 | Remark: NEW
- Footer totals: Qty 5 | Rate 3000 | Net Amt 15,000

**Actual Result:** Entry saved; all values match expected output

**Screenshots / Ref:** Image1 – Store Purchase Entry

**Serial Numbers:** Not yet assigned at this stage

---

## TC-02 — Generate serial numbers (Katora No.) for purchased items

| Module | Priority | Status | Dept Code | Prod Type / Process | Tested By | Tested Date |
|---|---|---|---|---|---|---|
| Store Serial No Create | High | PASS | STORE | — | PRAFUL | 11/08/2026 |

**Precondition:** TC-01 completed; Purchase No 12331 in Pending Stock

**Test Steps**

1. Go to 'Store Serial No Create' tab
2. Left panel shows Pending Stock with Purchase No 12331
3. Select row: Purchase No 12331, Party: MOUNTAIN, Qty 5, Rate 3000, Amt 15000
4. Item: KATORA (S.NO.) | Sub Item: MATHALA (ANJANI)
5. System auto-populates 5 serial rows
6. Verify Katora Nos: M-1250, M-1251, M-1252, M-1253, M-1254
7. Click 'Save'

**Test Data / Input Values**

- Purchase No: 12331 | Lot SRNO: 0
- Item: KATORA (S.NO.) | Sub Item: MATHALA (ANJANI)
- Sr 1: M-1250, Qty 1, Rate 3000, Amt 3000
- Sr 2: M-1251, Qty 1, Rate 3000, Amt 3000
- Sr 3: M-1252, Qty 1, Rate 3000, Amt 3000
- Sr 4: M-1253, Qty 1, Rate 3000, Amt 3000
- Sr 5: M-1254, Qty 1, Rate 3000, Amt 3000

**Expected Result**

- 5 serial numbers created: M-1250 to M-1254
- Each Katora: Qty 1 | Rate 3000 | Amt 3000
- Footer totals: Count 5 | Qty 5 | Rate 3000 | Amt 15,000
- Lot SRNO updated from 0 → 5
- Record saved successfully

**Actual Result:** 5 serial nos M-1250–M-1254 created; totals correct

**Screenshots / Ref:** Image2 – Store Serial No Create

**Serial Numbers:** M-1250, M-1251, M-1252, M-1253, M-1254

---

## TC-03 — Issue stock to Dept PSRT (POL FACTORY) – Production 1

| Module | Priority | Status | Dept Code | Prod Type / Process | Tested By | Tested Date |
|---|---|---|---|---|---|---|
| Stock Issue | High | PASS | PSRT | PRODUCTION 1 / POL FACTORY | PRAFUL | 11/08/2026 |

**Precondition:** TC-02 completed; M-1250–M-1254 in STORE stock

**Test Steps**

1. Open 'Stock Issue' tab
2. Set Date: 11/AUG/2026 | Dept Code: PSRT
3. Prod. Type: PRODUCTION 1 | Process: POL FACTORY
4. PO No: 1
5. Select Item: KATORA (S.NO.) | Sub Item: MATHALA (ANJANI)
6. Item Condition: New | Qty: 5 | Rate: 3000
7. Click 'Add' → verify row in grid
8. Click 'Save'

**Test Data / Input Values**

- Date: 11/AUG/2026
- Dept Code: PSRT | PO No: 1
- Prod. Type: PRODUCTION 1
- Process: POL FACTORY
- Item: KATORA (S.NO.)
- Sub Item: MATHALA (ANJANI)
- Item Condition: New
- Qty: 5 | Rate: 3000 | Amount: 15,000
- Remark: NEW

**Expected Result**

- Stock issue record saved successfully
- Grid shows: KATORA (S.NO.) | MATHALA (ANJANI)
- Item Condition: New | Qty: 5.000
- Rate: 3000.000 | Amount: 15,000.000 | Remark: NEW
- Barcode column: 0
- Footer totals: Qty 5 | Rate 3000 | Amt 15,000
- Balance QTY: 0 (all issued)

**Actual Result:** Stock issue saved; PSRT received 5 Katora units

**Screenshots / Ref:** Image3 – Stock Issue (PSRT)

**Serial Numbers:** M-1250, M-1251, M-1252, M-1253, M-1254

---

## TC-04 — Verify closing stock for single Katora No. M-1250 (PSRT)

| Module | Priority | Status | Dept Code | Prod Type / Process | Tested By | Tested Date |
|---|---|---|---|---|---|---|
| Store Report Viewer | Medium | PASS | PSRT | POL FACTORY | PRAFUL | 11/08/2026 |

**Precondition:** TC-03 stock issue completed

**Test Steps**

1. Open 'STORE REPORT VIEWER'
2. From Date / To Date: 11-AUG-2026
3. Report Type: STOCK | Report: SERIAL NO. STOCK
4. Item Type: ASSETS | Item: KATORA (S.NO.)
5. Apply filter: Katora No = M-1250
6. Click Show/Refresh

**Test Data / Input Values**

- Date Range: 11-AUG-2026 to 11-AUG-2026
- Report Type: STOCK
- Report: SERIAL NO. STOCK
- Item Type: ASSETS
- Item: KATORA (S.NO.)
- Katora No Filter: M-1250

**Expected Result**

- 1 record visible:
  - SR 2566 | PSRT | POL FACTORY | 5TH.FLR.-SO.
  - ASSETS | KATORA (S.NO.) | MATHALA (ANJANI)
  - PCS. | SR No: 0 | Katora No: M-1250
  - Qty: 1.000 | Rate: 3000.00 | Amt: 3000.000
- Footer: Count 1 | Qty 1.000 | Rate 3000 | Amt 3000

**Actual Result:** Report shows exactly 1 record for M-1250 with correct values

**Screenshots / Ref:** Image4 – Store Report Viewer (M-1250 only)

**Serial Numbers:** M-1250

---

## TC-05 — Verify closing stock for all 5 Katora Nos (M-125x filter) at PSRT

| Module | Priority | Status | Dept Code | Prod Type / Process | Tested By | Tested Date |
|---|---|---|---|---|---|---|
| Store Report Viewer | Medium | PASS | PSRT | POL FACTORY | PRAFUL | 11/08/2026 |

**Precondition:** TC-03 completed

**Test Steps**

1. Open 'STORE REPORT VIEWER'
2. Date: 11-AUG-2026 | Report: SERIAL NO. STOCK
3. Item Type: ASSETS | Item: KATORA (S.NO.)
4. Apply filter: Katora No contains 'M-125'
5. Click Show/Refresh

**Test Data / Input Values**

- Katora No Filter: M-125 (partial match)
- Expected: M-125, M-1250, M-1251, M-1252, M-1253, M-1254

**Expected Result**

- 6 records visible (row 175 is pre-existing M-125 at PSRBA-2/MATAWADI)
- Rows 2566–2570: PSRT | POL FACTORY | 5TH.FLR.-SO.
  - M-1250,M-1251,M-1252,M-1253,M-1254 each Qty 1, Rate 3000, Amt 3000
- Footer: Count 6 | Total Qty 6.000 | Amt 18,000.000

**Actual Result:** 6 records shown; PSRT rows for M-1250–M-1254 all correct

**Screenshots / Ref:** Image5 – Store Report Viewer (M-125x all rows)

**Serial Numbers:** M-125, M-1250, M-1251, M-1252, M-1253, M-1254

---

## TC-06 — Verify Stock Issue Detail report for PSRT issue

| Module | Priority | Status | Dept Code | Prod Type / Process | Tested By | Tested Date |
|---|---|---|---|---|---|---|
| Store Report Viewer | Medium | PASS | PSRT | POL FACTORY | PRAFUL | 11/08/2026 |

**Precondition:** TC-03 completed

**Test Steps**

1. STORE REPORT VIEWER
2. Date: 11-AUG-2026
3. Report Type: STOCK ISSUE | Report: STOCK ISSUE DETAIL
4. Item Type: ASSETS | Item: KATORA (S.NO.)
5. Click Show/Refresh

**Test Data / Input Values**

- Report Type: STOCK ISSUE
- Report: STOCK ISSUE DETAIL
- Item: KATORA (S.NO.) | Item Type: ASSETS

**Expected Result**

- 1 row:
  - Date: 11/08/26 | PO No: 1 | Dept: PSRT
  - Process: POL FACTORY | Location: 5TH.FLR.-SO.
  - Item Type: ASSETS | Item: KATORA (S.NO.)
  - Sub Item: MATHALA (ANJANI) | Unit: PCS.
  - Remark: NEW | Qty: 5.00 | Rate: 3000 | Amt: 15,000 | Status: PENDING
- Footer: Qty 5 | Rate 3000 | Amt 15,000

**Actual Result:** Single PSRT issue row displayed; status PENDING as expected

**Screenshots / Ref:** Image6 – Stock Issue Detail Report

**Serial Numbers:** M-1250, M-1251, M-1252, M-1253, M-1254

---

## TC-07 — Return all 5 Katora items from PSRT to Store (Working condition)

| Module | Priority | Status | Dept Code | Prod Type / Process | Tested By | Tested Date |
|---|---|---|---|---|---|---|
| Return | High | PASS | PSRT | PRODUCTION 1 / POL FACTORY | PRAFUL | 11/08/2026 |

**Precondition:** TC-03 stock issue to PSRT completed

**Test Steps**

1. Open 'Return' tab
2. Date: 11/AUG/2026 | Dept Code: PSRT
3. Location: 5TH.FLR.-SOUTH-W
4. Prod. Type: PRODUCTION 1 | Process: POL FACTORY
5. Item: KATORA (S.NO.) | Sub Item: MATHALA (ANJANI)
6. Item Condition: Working | Qty: 5 | Rate: 3000
7. Click 'Series' button
8. Select all 5 serial nos (M-1250 to M-1254) → OK
9. Click 'Add' → Click 'Save'

**Test Data / Input Values**

- Date: 11/AUG/2026 | Bill Date: 11/AUG/2026
- Return No: 633 | Dept Code: PSRT
- Location: 5TH.FLR.-SOUTH-W
- Prod. Type: PRODUCTION 1 | Process: POL FACTORY
- Item: KATORA (S.NO.) | Sub Item: MATHALA (ANJANI)
- Item Condition: Working | Qty: 5 | Rate: 3000 | Amt: 15,000
- Serial Nos: M-1250, M-1251, M-1252, M-1253, M-1254

**Expected Result**

- Return No 633 saved in Add Mode
- Grid row: KATORA (S.NO.) | MATHALA (ANJANI)
  - Item Condition: Working | Qty: 5 | Rate: 3000 | Amt: 15,000
  - Rej Qty: 0 | Rej Rate: 0 | Rej Amt: 0
- Balance QTY resets to 0
- All 5 serials (M-1250–M-1254) checked in series popup

**Actual Result:** Return 633 saved; all 5 Katora nos returned from PSRT

**Screenshots / Ref:** Image7, Image8 – Return (PSRT)

**Serial Numbers:** M-1250, M-1251, M-1252, M-1253, M-1254

---

## TC-08 — Verify stock moved back to STORE (BASEMENT) after return

| Module | Priority | Status | Dept Code | Prod Type / Process | Tested By | Tested Date |
|---|---|---|---|---|---|---|
| Store Report Viewer | High | PASS | STORE | POL FACTORY | PRAFUL | 11/08/2026 |

**Precondition:** TC-07 return from PSRT completed

**Test Steps**

1. STORE REPORT VIEWER
2. Date: 11-AUG-2026 | Report: SERIAL NO. STOCK
3. Item Type: ASSETS | Item: KATORA (S.NO.)
4. Filter Katora No: M-125
5. Check location column for returned items

**Test Data / Input Values**

- Katora No Filter: M-125
- Expected Locations after return:
  - PSRBA-2/MATAWADI: M-125 (pre-existing)
  - STORE/BASEMENT: M-1250, M-1251, M-1252, M-1253, M-1254

**Expected Result**

- 6 records:
  - Row 175: PSRBA-2 | MATAWADI | SR 872 | M-125 | Qty 1
  - Rows 3-7: STORE | BASEMENT | M-1250–M-1254 each Qty 1, Amt 3000
- Footer: Count 6 | Qty 6 | Amt 18,000

**Actual Result:** Items M-1250–M-1254 now show STORE/BASEMENT after return

**Screenshots / Ref:** Image9 – Serial No Stock (Post Return)

**Serial Numbers:** M-1250, M-1251, M-1252, M-1253, M-1254

---

## TC-09 — Verify Stock Return Detail report after PSRT return

| Module | Priority | Status | Dept Code | Prod Type / Process | Tested By | Tested Date |
|---|---|---|---|---|---|---|
| Store Report Viewer | Medium | PASS | PSRT | POL FACTORY | PRAFUL | 11/08/2026 |

**Precondition:** TC-07 completed

**Test Steps**

1. STORE REPORT VIEWER
2. Date: 11-AUG-2026
3. Report Type: STOCK RETURN | Report: STOCK RETURN DETAIL
4. Item Type: ASSETS | Item: KATORA (S.NO.)
5. Click Show/Refresh

**Test Data / Input Values**

- Report Type: STOCK RETURN
- Report: STOCK RETURN DETAIL
- Item Type: ASSETS | Item: KATORA (S.NO.)

**Expected Result**

- 1 record:
  - Date: 11/08/26 | Dept: PSRT | Process: POL FACTORY
  - Location: 5TH.FLR.-SO. | ASSETS | KATORA (S.NO.) | MATHALA (ANJANI)
  - PCS. | Rej Qty: 0 | Rej Amt: 0
  - Return Qty: 5.00 | Rate: 3000 | Amt: 15,000
- Footer: Rej 0 | Return Qty 5 | Amt 15,000

**Actual Result:** Return detail shows PSRT return of 5 Katoras at 15,000

**Screenshots / Ref:** Image10 – Stock Return Detail

**Serial Numbers:** M-1250, M-1251, M-1252, M-1253, M-1254

---

## TC-10 — Issue 4 Katora items to Dept PSAC-2 (POL FACTORY – Production 2)

| Module | Priority | Status | Dept Code | Prod Type / Process | Tested By | Tested Date |
|---|---|---|---|---|---|---|
| Stock Issue | High | PASS | PSAC-2 | PRODUCTION 2 / POL FACTORY | PRAFUL | 11/08/2026 |

**Precondition:** TC-07 return to STORE completed; at least 4 units available

**Test Steps**

1. Open 'Stock Issue' tab
2. Date: 11/AUG/2026 | Dept Code: PSAC-2
3. Prod. Type: PRODUCTION 2 | Process: POL FACTORY
4. PO No: 1
5. Select Item: KATORA (S.NO.) | Sub Item: MATHALA (ANJANI)
6. Item Condition: New | Qty: 4 | Rate: 3000
7. Click 'Add' → Click 'Save'

**Test Data / Input Values**

- Date: 11/AUG/2026 | Dept Code: PSAC-2
- Prod. Type: PRODUCTION 2 | Process: POL FACTORY
- PO No: 1
- Item: KATORA (S.NO.) | Sub Item: MATHALA (ANJANI)
- Item Condition: New
- Qty: 4 | Rate: 3000 | Amount: 12,000
- Remark: NEW

**Expected Result**

- Stock issue saved for PSAC-2
- Grid: KATORA (S.NO.) | MATHALA (ANJANI)
  - Condition: New | Qty: 4.000 | Rate: 3000 | Amt: 12,000
  - Barcode: 0 | Remark: NEW
- Footer totals: Qty 4 | Rate 3000 | Amt 12,000
- Balance QTY: 0

**Actual Result:** PSAC-2 stock issue of 4 Katoras saved successfully

**Screenshots / Ref:** Image11 – Stock Issue (PSAC-2)

**Serial Numbers:** M-1250, M-1251, M-1252, M-1253 (4 of 5)

---

## TC-11 — Verify Stock Issue Detail shows 2 issue records (PSRT + PSAC-2)

| Module | Priority | Status | Dept Code | Prod Type / Process | Tested By | Tested Date |
|---|---|---|---|---|---|---|
| Store Report Viewer | Medium | PASS | PSRT, PSAC-2 | POL FACTORY | PRAFUL | 11/08/2026 |

**Precondition:** TC-03 & TC-10 completed

**Test Steps**

1. STORE REPORT VIEWER
2. Date: 11-AUG-2026
3. Report Type: STOCK ISSUE | Report: STOCK ISSUE DETAIL
4. Item Type: ASSETS | Item: KATORA (S.NO.)
5. Click Show/Refresh

**Test Data / Input Values**

- Report Type: STOCK ISSUE | Report: STOCK ISSUE DETAIL
- Date: 11-AUG-2026

**Expected Result**

- 2 rows:
  - Row 1: 11/08/26 | PO 1 | PSRT  | POL FACTORY | 5TH.FLR.-SO.
    - ASSETS | KATORA | MATHALA (ANJANI) | NEW | Qty 5 | Amt 15,000 | PENDING
  - Row 2: 11/08/26 | PO 1 | PSAC-2 | POL FACTORY | 1ST.FLR.-SO.
    - ASSETS | KATORA | MATHALA (ANJANI) | NEW | Qty 4 | Amt 12,000 | PENDING
- Footer: Count 2 | Qty 9 | Rate 3000 | Amt 27,000

**Actual Result:** Both issue rows visible; totals Qty 9, Amt 27,000 correct

**Screenshots / Ref:** Image12 – Stock Issue Detail (2 depts)

**Serial Numbers:** M-1250–M-1254 (PSRT) | 4 items (PSAC-2)

---

## TC-12 — Verify closing stock at PSAC-2 location (M-125x filter)

| Module | Priority | Status | Dept Code | Prod Type / Process | Tested By | Tested Date |
|---|---|---|---|---|---|---|
| Store Report Viewer | Medium | PASS | PSAC-2 | POL FACTORY | PRAFUL | 11/08/2026 |

**Precondition:** TC-10 issue to PSAC-2 completed

**Test Steps**

1. STORE REPORT VIEWER
2. Date: 11-AUG-2026 | Report: SERIAL NO. STOCK
3. Item Type: ASSETS | Item: KATORA (S.NO.)
4. Filter: Katora No contains 'M-125'
5. Click Show/Refresh

**Test Data / Input Values**

- Katora No Filter: M-125

**Expected Result**

- 6 records total:
  - Row 175: PSRBA-2 | MATAWADI | M-125 | Qty 1
  - Rows 2566-2570: PSAC-2 | 1ST.FLR.-SO. | M-1250–M-1254 each Qty 1, Amt 3000
- Footer: Count 6 | Qty 6 | Amt 18,000

**Actual Result:** PSAC-2 now holds M-1250–M-1254; totals correct

**Screenshots / Ref:** Image13 – Serial No Stock (PSAC-2)

**Serial Numbers:** M-1250, M-1251, M-1252, M-1253, M-1254

---

## TC-13 — Return 3 Katora items from PSAC-2 to Store (Working, Remark: RETURN 3)

| Module | Priority | Status | Dept Code | Prod Type / Process | Tested By | Tested Date |
|---|---|---|---|---|---|---|
| Return | High | PASS | PSAC-2 | PRODUCTION 2 / POL FACTORY | PRAFUL | 11/08/2026 |

**Precondition:** TC-10 stock issue to PSAC-2 completed

**Test Steps**

1. Open 'Return' tab
2. Date: 11/AUG/2026 | Bill Date: 11/AUG/2026
3. Return No: 634 | Dept Code: PSAC-2
4. Location: 1ST.FLR.-SOUTH-E
5. Prod. Type: PRODUCTION 2 | Process: POL FACTORY
6. Item: KATORA (S.NO.) | Sub Item: MATHALA (ANJANI)
7. Item Condition: Working | Qty: 3 | Rate: 3000 | Remark: RETURN 3
8. Click 'Add' → Click 'Save'

**Test Data / Input Values**

- Return No: 634 | Dept Code: PSAC-2
- Location: 1ST.FLR.-SOUTH-E
- Prod. Type: PRODUCTION 2 | Process: POL FACTORY
- Item: KATORA (S.NO.) | Sub Item: MATHALA (ANJANI)
- Item Condition: Working | Qty: 3
- Rate: 3000 | Amount: 9000 | Remark: RETURN 3

**Expected Result**

- Return saved in Edit Mode
- Grid row: KATORA (S.NO.) | MATHALA (ANJANI)
  - Condition: Working | Qty: 3.000 | Rate: 3000 | Amt: 9000
  - Rej Qty: 0 | Rej Rate: 0 | Rej Amt: 0 | Remark: RETURN 3
- Balance QTY: 0
- Footer: Qty 3 | Rate 3000 | Amt 9000

**Actual Result:** Return 634 saved; 3 Katoras returned from PSAC-2 with remark RETURN 3

**Screenshots / Ref:** Image14 – Return (PSAC-2)

**Serial Numbers:** 3 of 5 (M-1250, M-1251, M-1252)

---

## TC-14 — Verify stock redistribution after PSAC-2 partial return (3 items)

| Module | Priority | Status | Dept Code | Prod Type / Process | Tested By | Tested Date |
|---|---|---|---|---|---|---|
| Store Report Viewer | Medium | PASS | STORE / PSAC-2 | POL FACTORY | PRAFUL | 11/08/2026 |

**Precondition:** TC-13 PSAC-2 return completed

**Test Steps**

1. STORE REPORT VIEWER
2. Date: 11-AUG-2026 | Report: SERIAL NO. STOCK
3. Filter Katora No: M-125
4. Click Show/Refresh

**Test Data / Input Values**

- Katora No Filter: M-125

**Expected Result**

- 6 records:
  - Row 175: PSRBA-2 | MATAWADI | M-125 | Qty 1
  - Rows 3-5: STORE | BASEMENT | M-1250,M-1251,M-1252 (returned)
  - Rows 2566-2567: PSAC-2 | 1ST.FLR.-SO. | M-1253,M-1254 (still with dept)
- Footer: Count 6 | Qty 6 | Amt 18,000

**Actual Result:** 3 returned to STORE/BASEMENT; 2 remain at PSAC-2

**Screenshots / Ref:** Image15 – Serial No Stock Post PSAC-2 Return

**Serial Numbers:** M-1250,M-1251,M-1252 (STORE) | M-1253,M-1254 (PSAC-2)

---

## TC-15 — Verify Stock Return Detail shows both return entries (PSAC-2 + PSRT)

| Module | Priority | Status | Dept Code | Prod Type / Process | Tested By | Tested Date |
|---|---|---|---|---|---|---|
| Store Report Viewer | Medium | PASS | PSAC-2, PSRT | POL FACTORY | PRAFUL | 11/08/2026 |

**Precondition:** TC-07 & TC-13 completed

**Test Steps**

1. STORE REPORT VIEWER
2. Date: 11-AUG-2026
3. Report Type: STOCK RETURN | Report: STOCK RETURN DETAIL
4. Item Type: ASSETS | Item: KATORA (S.NO.)
5. Click Show/Refresh

**Test Data / Input Values**

- Report Type: STOCK RETURN | Report: STOCK RETURN DETAIL

**Expected Result**

- 2 rows:
  - Row 1: 11/08/26 | PSAC-2 | POL FACTORY | 1ST.FLR.-SO.
    - KATORA | MATHALA (ANJANI) | Remark: RETURN 3
    - Rej Qty: 0 | Rej Amt: 0 | Return Qty: 3 | Rate: 3000 | Amt: 9000
  - Row 2: 11/08/26 | PSRT  | POL FACTORY | 5TH.FLR.-SO.
    - KATORA | MATHALA (ANJANI)
    - Rej Qty: 0 | Rej Amt: 0 | Return Qty: 5 | Rate: 3000 | Amt: 15,000
- Footer: Count 2 | Rej 0 | Total Return Qty 8 | Amt 24,000

**Actual Result:** Both returns visible; Amt 9000+15000=24,000 correct

**Screenshots / Ref:** Image16 – Stock Return Detail (Both)

**Serial Numbers:** PSAC-2: 3 items | PSRT: 5 items

---

# TEST EXECUTION SUMMARY – STORE MODULE

**Tested By: YASH BHATT** | **Test Date: 11-AUG-2026**

| TC ID | Test Scenario (Short) | Module | Priority | Status | Remarks |
|---|---|---|---|---|---|
| TC-01 | Create new purchase entry | Store Purchase Entry | High | PASS |  |
| TC-02 | Generate Katora serial numbers (M-1250–M-1254) | Store Serial No Create | High | PASS |  |
| TC-03 | Issue 5 Katoras to PSRT (Production 1) | Stock Issue | High | PASS |  |
| TC-04 | Verify single Katora M-1250 in stock report | Store Report Viewer | Medium | PASS |  |
| TC-05 | Verify all 5 Katoras in stock report (PSRT) | Store Report Viewer | Medium | PASS |  |
| TC-06 | Check Stock Issue Detail – PSRT entry | Store Report Viewer | Medium | PASS |  |
| TC-07 | Return all 5 Katoras from PSRT | Return | High | PASS |  |
| TC-08 | Verify stock back at STORE/BASEMENT | Store Report Viewer | High | PASS |  |
| TC-09 | Check Stock Return Detail – PSRT | Store Report Viewer | Medium | PASS |  |
| TC-10 | Issue 4 Katoras to PSAC-2 (Production 2) | Stock Issue | High | PASS |  |
| TC-11 | Verify Stock Issue Detail – PSRT + PSAC-2 | Store Report Viewer | Medium | PASS |  |
| TC-12 | Verify closing stock at PSAC-2 location | Store Report Viewer | Medium | PASS |  |
| TC-13 | Return 3 Katoras from PSAC-2 (RETURN 3) | Return | High | PASS |  |
| TC-14 | Verify stock post PSAC-2 partial return | Store Report Viewer | Medium | PASS |  |
| TC-15 | Final Stock Return Detail – both returns | Store Report Viewer | Medium | PASS |  |

**Total: 15 Test Cases** — ✓ PASS: 15   ✗ FAIL: 0   ⏳ PENDING: 0
