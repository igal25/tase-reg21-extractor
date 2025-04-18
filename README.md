📄 Automated Extraction of TASE Filings: Regulation 21 Table
This Python project automates the extraction of executive compensation data from financial reports filed by Israeli public companies on the Maya TASE website. It specifically targets "תקנה 21" (Regulation 21) tables, which summarize compensation of executives and directors, and exports this data into a structured CSV for research or regulatory analysis.

✨ Features
✅ Fully automated browsing and filtering of reports using Playwright.

📥 Selectively downloads and parses PDF documents via PyMuPDF (fitz).

📑 Searches each PDF for Regulation 21 tables by identifying the keyword "תקנה 21:".

📊 Accurately extracts tabular data (names, roles, compensation components).

🔍 Advanced logic to handle:

Split Hebrew words (e.g. “מנכ"ל” mistakenly split into parts).

Text directionality (RTL) issues.

Removal of irrelevant footnotes, parentheses, or asterisks.

🧠 Smart parsing to keep fields in correct alignment under 17 specific headers.

🇮🇱 Supports Hebrew text and ensures proper encoding (utf-8-sig) for Excel compatibility.

🔄 Continues to next report/page automatically, with robustness to UI delays and failures.

📁 Output Format
The exported file is a CSV named תקנה_21.csv with the following headers:

csv
Copy
Edit
חברה,שם,תפקיד,היקף משרה,שיעור החזקה בהון,שכר,מענק,תגמול מבוסס מניות,דמי ניהול,החזר הוצאות,עמלה,אחר - ניהול דירקטורים,ריבית,דמי שכירות,אחר,סה"כ (באלפי ש"ח)
Each row represents one executive's compensation line item parsed from the Regulation 21 table.

⚙️ Technologies Used
Playwright: for headless browsing and interaction with Maya website.

PyMuPDF (fitz): for reading text with precise positional information from PDFs.

pdfminer.six: (loaded but deprecated in this version) for fallback text extraction.

asyncio: for non-blocking performance.

csv, re, tempfile: for structured output and robust file handling.

🧠 Use Cases
Academic research in finance and corporate governance.

Regulatory trend analysis on DEI/ESG policies.

Natural language processing (NLP) pipelines for Hebrew-language documents.

Public transparency and data scraping projects.

🔍 Missing / Future Work
 Support for multiple-page tables (currently stops at the first matching page).

 Fallback to pdfminer when fitz fails to read content.

 Smarter fuzzy-matching when "תקנה 21" is formatted inconsistently.
