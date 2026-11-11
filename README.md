# ClearRec: UK Bank Reconciliation Tool

**Live demo:** https://ragip-cpu.github.io/ClearRec-UK-Bank-Reconciliation-Tool/. Click **Generate sample data** for a fresh, random business every time, then open **Reveal answers** to check ClearRec's accuracy yourself.

ClearRec matches a bank statement against a cash book, explains every difference between them, and produces a finished bank reconciliation statement and Excel working paper. It is built for UK businesses (DD/MM/YYYY dates, £, UK banking terms).

## What it does

- **Imports Excel (.xlsx) or CSV files.** It finds the heading row even when bank exports have title rows above it, tags each column automatically, and works out the opening balance from a Balance column.
- **Lets you edit the data like a spreadsheet:** rename headings, add or delete rows and columns, and paste cells straight from Excel.
- **Matches transactions automatically** using:
  - the **amount and a shared reference** (cheque or invoice number), so late-clearing cheques still match
  - the **amount and date** within a set tolerance
  - **same-customer/supplier batches**, where one bank payment settles any number of invoices
  - **mixed batches**, where several cheques are paid in on one deposit slip
- **Flags likely errors for review** rather than auto-correcting them:
  - **transposition errors** (digits swapped, so the difference is divisible by 9)
  - **timing differences** outside the date window
  - similar descriptions with small amount differences
- **Classifies reconciling items:** unpresented cheques, outstanding lodgements, bank charges, direct debits and interest.
- **Produces the reconciliation statement:** adjusted bank balance against adjusted cash book balance, including error corrections.
- **Exports a formatted Excel working paper** with sign-off (prepared and reviewed by), notes, matched items, items to record, items in transit, and both full ledgers.

## Test it yourself

**Generate sample data** creates a new random business on every click: a random month (~250 lines) or quarter (~700 lines), different customers, suppliers and amounts, with a random set of deliberately hidden problems (transposition errors, late-clearing items, batched payments, unpresented cheques, outstanding lodgements, bank charges). The **Sample accuracy check** panel lists everything that was hidden, whether ClearRec found it, and the true closing balance, so anyone can verify the results independently.

## Results

Tested on a full quarter of data (Q4 2026, 709 transactions): **98% matched automatically** and the account reconciled to the penny, with all deliberately planted errors identified. In automated testing across 38 random months and quarters, ClearRec found **every** planted item and reached the true balance every time.

## Privacy

ClearRec runs entirely in the browser. Bank and cash book data are processed on the user's own computer and are **never uploaded to a server**. There is no back end or database.

## How to use

1. Upload or paste the **bank statement** (step 1) and **cash book** (step 2).
2. Check the column tags and enter the cash book opening balance.
3. Click **Reconcile**, review the suggested matches, and match any remaining items by hand.
4. Fill in the sign-off details and click **Download Excel report**.

## Built with

HTML, CSS and JavaScript in a single self-contained file, with no frameworks or external services. Excel files are read and written by the page itself.

---

*Personal project. All sample data is fictional.*
