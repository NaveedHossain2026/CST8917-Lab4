# CST8917 Lab 4: PhotoPipe — Event-Driven Image Processing with Event Grid & Functions

---
**Student Name**: Naveed Hossain             **Student ID**: 0410818822 
**Course**: CST8917 - Serverless Applications
**Semester**: Summer 2026

---
## Demo Video

Video Demo: https://youtu.be/1Ne2oWy8qY0

---



## Setup

1. **Storage account** — create it, enable Blob anonymous access, add two containers (`image-uploads` public-blob, `image-results` private), enable CORS for Blob service (`*`).
2. **Deploy the functions** — set `STORAGE_CONNECTION_STRING` as an app setting on the Function App, enable CORS (`*`) on the Function App itself.
3. **Event Grid** — create a System Topic on the storage account, then two subscriptions: one filtered to `.jpg`/`.png` pointing at `process-image`, one unfiltered pointing at `audit-log`.
4. **Web client** — generate a SAS token from the storage account, open `client.html` through a local server (e.g. VS Code Live Server — not by double-clicking the file), and fill in your storage account name, SAS token, and Function App URL.

Upload a `.jpg`/`.png` to see it processed in the **Results** tab; upload any other file type to see it logged in **Audit Log** only.
