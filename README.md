# Data Utilities

A set of small, single-page web tools for everyday data processing: name formatting, email lookup, reference code extraction, and Excel report generation. The landing page (`index.html`) is styled like X (Twitter), with the tools listed in a left sidebar and a feed in the middle.

**Live page:** https://joremacerado1999-lgtm.github.io/data-utilities/

## Tools

| Tool | File | What it does |
| --- | --- | --- |
| For Summary Template | `summary-tool.html` | Fixes your file from INDEXONE so it becomes your SUMMARY TEMPLATE. |
| Name Fixer | `name-fixer.html` | Fixes the names of FIELD MAN from OPENCI. |
| Email Lookup | `email-lookup.html` | Paste the FINAL and copy the EMAIL ADDRESS. |
| Get Reference Code | `reference-code.html` | Extracts the file from DLX and gets your correct REFERENCE CODE. |
| Placement | `placement-lookup.html` | Finds BANK and PLACEMENT from a CH CODE using the uploaded Excel file. |
| PIF NEW ENDO Mapper | `pif-new-endo-mapper.html` | Generates SUMMARY PIF HOMELOAN NEW ENDO from your PIF Excel file. |
| For Passes | `for-passes.html` | Extracts data from the RESULT sheet, filters BANK = "PIF HOME LOAN", splits CANCEL rows, and creates a UNIQ sheet. |

## Project structure

```
data-utilities/
├── index.html                  # landing page with sidebar and tool list
├── summary-tool.html
├── name-fixer.html
├── email-lookup.html
├── reference-code.html
├── placement-lookup.html
├── pif-new-endo-mapper.html
├── for-passes.html
└── README.md
```

Each tool is a standalone HTML file. There is no build step and no dependencies to install for the landing page.

## Run locally

Open `index.html` in a browser, or serve the folder:

```bash
python -m http.server 8000
```

Then go to http://localhost:8000.

## Deploy with GitHub Pages

1. Push the files to the repository root on the `main` branch.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set the source to **Deploy from a branch**, choose `main` and `/ (root)`, then save.
4. After a minute or two the site is live at the URL above.

## Add a new tool

1. Put the new tool's HTML file in the repo root.
2. Open `index.html` and add one line to the `TOOLS` array in the script:

```js
{ icon: "🧾", name: "My New Tool", tag: "short label", href: "my-new-tool.html",
  desc: "One sentence on what it does." },
```

The sidebar, the feed, and the search box all update from that single entry.

## Themes

The landing page has three display modes, the same as X: **Light**, **Dim**, and **Dark**. The choice is saved in the browser.

## A note on data

These tools are for internal use. Do not commit real data files (for example `PLACEMENT.xlsx`, `correct_names.xlsx`, or any export containing account or loan details) to a public repository. If the repo is public, add them to a `.gitignore` or keep the repo private.

## License

For internal use only. All rights reserved.
