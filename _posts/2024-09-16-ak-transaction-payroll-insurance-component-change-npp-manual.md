---
title: "(AK) Transaction - Payroll - Insurance Component - Change NPP (Manual)"
thumbnail: undraw_working_re_ddwy.svg
description: "Create transaction change NPP."
tags: 
  - "Personal"
  - "Web development"
---

## Goals

User creates transactions change NPP for existing transactions.

## Menu Location

Transaction - Payroll - Insurance Component - Change NPP

You can create transaction assignment or transaction change in this page.

## Screen Capture

### New tab menu item

New **Insurance Component** sidebar menu item, validate this

> **Note to self:** Is **Insurance Component** a new side bar item?

### Initial default page state

Tabs:
- **Assign**
- **Change NPP**

Buttons:
- **Transaction**

Selected employee card:
- **Add Employee** button
- **Field Chooser** button
- Employee table

Form card:
- Fields
- Add state buttons:
    - **Save**
    - **Save & Close**
    - **Clear**
- Edit state buttons:
    - **Update**
    - **Update & Close**
    - **Cancel**

### Select NPP BPJS

> **Note to self:** Is it select NPP or NPP BPJS? Then do I change the whole "change NPP" to "change NPP BPJS"?

Select Master NPP BPJS

Side effect:
- Employee selector popup shows employee with the selected Masted NPP BPJS
- The transaction change form NPP BPJS dropdown options will be all the Master excluding the one that was selected

> **Note to self:** What happens to the Side effect above if there is only 1 Mater NPP BPJS?

From here, you can do either [Add employee](#add-employee) or [Create transaction](#create-transaction) first. You **must do both to enable transaction change form Save & Close button**

### Add employee

Steps:
1. Click **Add Employee** button
2. Employee selector popup appears:
    - Listed employees are the ones that:
        - **Have the selected NPP BPJS** in the [Select NPP BPJS](#select-npp-bpjs) screen capture.
        - Employee Status == Active
    - Select at least 1 with checkbox
3. Click **Add Employee**
4. Employee selector popup closes, the selected employees now populate the "Selected Employee Table"

You can remove employee from the "Selected Employee Table" with the "Delete Icon" or the "Delete All button":
- Click **Delete Icon** on 1 row to remove that employee row
- Click **Delete All** on header to remove that employee row

Added employees does not appear in Employee selector popup

### Fill transaction form

Steps:
1. Fill fields:
    - Input Reference Number
    - Select Date
    - Input Description
    - Select Effective Date
    - Select NPP BPJS
        - The Master in options are all the Master excluding the one that was selected in the [Select NPP BPJS](#select-npp-bpjs) screen capture.

### Assign Transaction

1. After doing [Select NPP BPJS](#select-npp-bpjs) screen capture and [Create transaction](#create-transaction) screen capture. The transaction change form Save & Close button is enabled.
2. Click **Save**
3. Transaction list drawer slides from right into viewport
4. Inside the transaction list:
    - The transaction you just assigned **populates** the drawer transaction list and its checkbox should be **ticked**
5. Created toast appears
