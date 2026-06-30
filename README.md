# 📂 n8n Workflow - Gmail to Google Drive Investment Document Automation

## Overview

This project demonstrates how to automate the management of investment-related documents using **n8n**.

The workflow monitors Gmail for new emails, identifies investment-related messages, downloads attachments, and uploads them to Google Drive. This helps organize important financial documents such as dividend notices, shareholder communications, annual reports, mutual fund statements, and tax documents.

---

## Business Problem

Investment documents are often scattered across email inboxes, making them difficult to locate and manage.

Manually downloading and organizing these documents is repetitive and time-consuming.

This workflow automates the process by identifying relevant emails and securely storing their attachments in Google Drive.

---

## Solution

The workflow performs the following actions:

1. Monitor Gmail for new emails.
2. Download email attachments.
3. Identify investment-related documents.
4. Upload attachments to Google Drive.
5. Organize documents for easy access.

---

## Workflow


Gmail Trigger
      │
      ▼
Check Attachment
      │
      ▼
(Optional) AI Classification
      │
      ▼
Google Drive Upload


---

## Features

- Gmail integration
- Automatic attachment download
- Google Drive integration
- Low-code workflow using n8n
- Easily extendable with AI-powered document classification
- Supports organization by company or document type

---

## Tech Stack

| Technology | Purpose |
|------------|---------|
| n8n | Workflow automation |
| Gmail API | Email monitoring |
| Google Drive API | File storage |
| Docker | Local deployment |
| OAuth 2.0 | Google authentication |
| JavaScript Expressions | Workflow logic |

---

## Prerequisites

- Docker Desktop
- n8n (Self-hosted)
- Google Account
- Gmail API enabled
- Google Drive API enabled
- Google OAuth Client ID & Client Secret

---

## Current Constraints

While developing this project locally, the following limitation was encountered:

- Gmail integration requires **Google OAuth 2.0 authentication**.
- Google blocks authentication for applications that are not verified or are not configured correctly.
- When running n8n locally, additional OAuth configuration (Authorized Redirect URI, OAuth Consent Screen, Client ID, and Client Secret) is required.
- Without a valid OAuth access token, the Gmail Trigger cannot authenticate and returns an error similar to:

```
Unable to sign without access token
```

or

```
Access blocked: This app has not completed the Google verification process.
```

As a result, the Gmail trigger could not be fully demonstrated in the local development environment.

---

## Future Enhancements

- AI-based investment document classification
- Automatic folder creation by company
- Organize documents by type:
  - Dividend
  - Shareholder Notice
  - Annual Report
  - Mutual Fund Statement
  - Tax Documents
- OCR support for scanned PDFs
- Duplicate document detection
- Metadata extraction
- Google Sheets logging
- Email notifications

---

## Repository Structure


├── workflow.json
├── README.md
├── screenshots


---

## Learning Outcomes

This project helped me gain practical experience with:

- Workflow orchestration using n8n
- Gmail and Google Drive integrations
- OAuth 2.0 authentication
- Cloud automation
- Business process automation
- Designing extensible AI workflows

---

## Future AI Enhancement

The workflow can be extended by integrating an LLM (such as Ollama or OpenAI) to automatically extract:

- Company Name
- Document Type
- Statement Date
- Dividend Details
- Tax Information

This would enable automatic organization of documents into folders such as:

```
Investment Documents/
├── Infosys/
│   ├── Dividend/
│   ├── Annual Reports/
│   └── Shareholder Notices/
├── TCS/
├── HDFC Mutual Fund/
└── Zerodha/
```

---

## Author

**Chaitra T**

Building AI-powered business automation workflows using n8n, Python, and Large Language Models.
