#  Setup Guide - AI Resume Screening System

This guide explains how to run the project locally using **n8n + Docker**.

---

##  Prerequisites

Make sure you have:

* Docker installed → https://docs.docker.com/get-docker/
* Google Account
* ngrok (optional for OAuth) → https://ngrok.com/

---

##  Step 1: Run n8n using Docker

```bash
docker run -it --rm \
-p 5678:5678 \
-v ~/.n8n:/home/node/.n8n \
n8nio/n8n
```

---

##  Step 2: Open n8n

Go to:

http://localhost:5678

---

##  Step 3: Import Workflow

1. Open n8n dashboard
2. Click **Import Workflow**
3. Upload:

```
workflow/Resume_Screening_Complete.json
```

---

##  Step 4: Setup Credentials

### Google Sheets

* Create OAuth2 credentials in Google Cloud Console
* Enable:

  * Google Sheets API
  * Google Drive API
* Add redirect URI:

```
http://localhost:5678/rest/oauth2-credential/callback
```

---

### Gmail

* Enable Gmail API
* Use same OAuth credentials
* Add redirect URI (same as above)

---

##  Step 5 (Optional): Use ngrok

If OAuth fails locally:

```bash
ngrok http 5678
```

Update redirect URI:

```
https://your-ngrok-url/rest/oauth2-credential/callback
```

---

##  Step 6: Run Workflow

* Click **Execute Workflow**
* Check:

  * Google Sheet updates
  * Emails are sent

---

##  Sample Flow

* Candidates loaded → scored → ranked
* If score ≥ 75 → selected
* Else → rejected

---

##  Common Errors & Fixes

###  OAuth Redirect Error

 Fix:

* Use ngrok
* Update redirect URI

---

###  Email Not Sending

 Fix:

* Reconnect Gmail credentials
* Check API enabled

---

###  Google Sheets Not Updating

 Fix:

* Ensure sheet is selected
* Check column mapping

---

###  Workflow Not Running

 Fix:

* Check all nodes are configured (no red icons)

---

##  Notes

* No paid APIs used
* All scoring done via JavaScript logic
* Fully self-hosted using Docker

---

