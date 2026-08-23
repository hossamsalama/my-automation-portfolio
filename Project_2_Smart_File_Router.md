# Project 2: Smart File Router + Conditional Email Notifier

## What it does
Monitors a Google Drive folder and **intelligently routes files** based on their type. Instead of a one-size-fits-all response, this automation makes decisions:
- **PDF Files** → Logged to Sheets + sends a detailed email to the "Accounts" team.
- **Image Files** (JPG, PNG) → Logged to Sheets + sends a different email to the "Design" team.
- **Other Files** (TXT, DOCX) → Simply logged to Sheets (no email, to avoid clutter).

## Skills Demonstrated
- **Routers**: Splitting a single workflow into multiple parallel paths based on conditions.
- **Filters**: Blocking or allowing data to pass based on specific rules (e.g., file size, MIME type).
- **Error Handling (Skip)**: Ensuring the automation doesn't break if a file fails to process.
- **Advanced Data Mapping**: Passing `File ID` between modules to enrich data.

## How it works (The Smart Logic)
1. A file is added to a specified Google Drive folder.
2. Make.com detects the new file using the "Watch Files" trigger.
3. The "Get a File" module retrieves rich details: Name, Size, MIME Type (to identify if it's a PDF, Image, or other).
4. **The Router splits the workflow:**
   - **Route 1 (PDFs):** If `MIME Type` = `application/pdf` → Log details to Sheets → Send specific email (Subject: "New Invoice/PDF Received").
   - **Route 2 (Images):** If `MIME Type` contains `image` → Log details to Sheets → Send specific email (Subject: "New Design Asset Uploaded").
   - **Route 3 (Others):** If none of the above → Just log details to Sheets (Silent logging to avoid notification overload).
5. **Error Handling:** If the "Get a File" module fails (e.g., network timeout), the automation ignores the error and continues, preventing a full workflow crash.

## Screenshot
https://drive.google.com/file/d/1DlASrV9UlZljz7OxRR-7GyoxwzHE7RII/view?usp=drive_link

## Use Case
A marketing or operations team that needs to triage incoming files automatically. 
- The **Finance team** gets an alert immediately when an invoice (PDF) is uploaded.
- The **Design team** gets a notification when a new image asset is uploaded.
- The **Archiving team** simply has a record of everything else in the spreadsheet without being spammed.

## Technologies Used
- Make.com
- Google Drive (Watch Files, Get a File)
- Google Sheets (Logging)
- Gmail (Conditional Alerts)
- Filters & Routers (Conditional Logic)
