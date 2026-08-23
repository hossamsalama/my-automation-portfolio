# Project 1: Google Drive → Google Sheets Automation

## What it does
Automatically logs new files added to a Google Drive folder into a Google Sheet with file name, creation date, file size, and a clickable link.

## Skills Demonstrated
- Triggers & Actions (Google Drive, Google Sheets)
- Data Mapping (Enrichment with "Get a File")
- File Monitoring (Watch Files)
- Email Notifications

## How it works
1. A file is added to a specified Google Drive folder.
2. Make.com detects the new file.
3. The "Get a File" module retrieves all file details (name, size, link).
4. The file details are added as a new row in Google Sheets.
5. An email notification is sent with the file summary.

## Screenshot
https://drive.google.com/file/d/1wHz2n0jzghyGEx9iUHUWqCR7e9JaZyiJ/view?usp=drive_link

## Use Case
Businesses that need to track uploaded documents (invoices, reports, images) in a central spreadsheet without manual data entry.

## Technologies Used
- Make.com
- Google Drive
- Google Sheets
- Gmail
