#  AI Resume Screening System using n8n

>  Fully automated hiring workflow — no downloads required. Explore everything directly in this repository.

---

##  Overview

This project is an **automated resume screening system** built using **n8n (self-hosted with Docker)**.

It evaluates candidates, ranks them, and automates hiring decisions such as:

* Shortlisting candidates
* Sending interview emails
* Sending rejection emails
* Storing results in Google Sheets

---

##  Live Demo

###  Candidate Dashboard (Real-Time)

 **[Candidate Data](https://docs.google.com/spreadsheets/d/14pISN7MmYG9fAv7H-QGLJIA8vfQRkwXw3RcREVsAQCw/edit?gid=0#gid=0)**

>  This sheet updates automatically from the n8n workflow

---

##  Workflow File

 **[View Workflow JSON](workflow/Resume_Screening.json)**

---
### Backend Workflow Architecture

![Backend Architecture](docs/Backend.png)

---
##  How It Works

```mermaid
flowchart TD
A[Load Candidates] --> B[Score Resume]
B --> C[Rank Candidates]
C --> D{Score >= 75}
D -->|Yes| E[Save + Send Interview Email]
D -->|No| F[Save + Send Rejection Email]
```

---

##  Features

*  Resume scoring using keyword matching (JavaScript logic)
*  Candidate ranking system
*  Google Sheets integration (live results)
*  Automated email system (Gmail API)
*  Fully automated workflow (n8n)
*  Runs locally using Docker
*  No paid APIs used

---

##  Tech Stack

* n8n
* Docker
* JavaScript
* Google Sheets API
* Gmail API
* OAuth2
* ngrok

---

##  Sample Output

| Candidate    | Score | Status   |
| ------------ | ----- | -------- |
| Priya Sharma | 84    | Selected |
| Rahul Verma  | 65    | Rejected |

---

##  Repository Structure

```
workflow/
docs/
.env.example
.gitignore
README.md
```

---

##  Email Templates
###  Accepted Candidate

![Accepted](docs/Accepted.png)

---

###  Rejected Candidate

![Rejected](docs/Rejected.png)

---

##  Setup Guide

 **[View Setup Instructions](docs/setup_guide.md)**

 ## Author

Himanshu  
 Email: himanshu.bohra2423@gmail.com <br>
 LinkedIn: https://www.linkedin.com/in/himanshubohra24/ 
