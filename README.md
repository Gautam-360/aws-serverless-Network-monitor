# AWS Serverless Network Health Monitor

A **Serverless Network Health Monitoring System** built on AWS using **Lambda**, **API Gateway**, **DynamoDB**, and optionally **Cognito** for authentication. Users can submit device status, latency, and connectivity info via a web interface. The project is visually appealing with animated UI and floating network symbols.

---

## Features

- Monitor devices' network health in real-time
- Submit device status (UP/DOWN) and latency
- Alert levels: NORMAL, WARNING, CRITICAL
- Store alerts in **DynamoDB**
- Serverless architecture using **AWS Lambda** and **API Gateway**
- Optional user authentication with **Cognito**
- Beautiful animated frontend hosted on **AWS Amplify**

---

## Architecture
```
Frontend (HTML/JS) ---> API Gateway (HTTP API) ---> Lambda Function ---> DynamoDB ---> Optional: Cognito for Authentication
```
## Prerequisites

- AWS account (Free tier available)
- Node.js / NPM (for local testing if needed)
- GitHub account (to host repo)
- Optional: AWS Amplify for frontend hosting

---

## Step 1: Set up DynamoDB

1. Go to AWS DynamoDB.
2. Create a table named `NetworkAlerts` (or your preferred name).
3. Partition key: `alertId` (String)
4. No sort key needed.

---

## Step 2: Create Lambda Function

1. Go to AWS Lambda → Create Function → Author from scratch.
2. Function name: `NetworkAlertHandler`
3. Runtime: Python 3.11 (or latest supported)
4. Attach execution role with **DynamoDB PutItem permission**.

**Lambda function code example (Python):**

Given lambda code 

## Step 3: Create API Gateway HTTP API
Go to API Gateway → Create HTTP API.

Route: POST /networkalert

Integration: Lambda function (NetworkAlertHandler)

Enable CORS:

Access-Control-Allow-Origin: *

Allowed Methods: POST, OPTIONS

Allowed Headers: Content-Type

Deploy API → Copy the Invoke URL.

## Step 4: Frontend (HTML/JS)
Create index.html (code is given)


## Step 5: Deploy Frontend
Use AWS Amplify to host your HTML/JS.

Connect to GitHub repo or upload manually.

Update API URL in index.html with deployed API Gateway URL.

---

## Screenshots
``` SCREENTSHOTS WILL BE AVAILABLE SOON    ```

---

## License
  MIT License
  
----
### Author
Gautam Kadlaskar – Networking & Cloud Enthusiast

