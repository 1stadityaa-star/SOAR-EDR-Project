# Architecture

## Overview

This project demonstrates a Security Orchestration, Automation, and Response (SOAR) workflow that integrates LimaCharlie EDR, Tines, Slack, and Email notifications.

The goal is to automatically notify analysts of malicious activity and allow them to isolate an endpoint with a single approval.

---

## Architecture Diagram

<img width="3464" height="3464" alt="Picsart_26-07-14_20-52-07-258 jpg" src="https://github.com/user-attachments/assets/33a6c67c-ae52-447a-96f5-382719a494f8" />


---

## Components

### LimaCharlie

LimaCharlie acts as the Endpoint Detection and Response (EDR) platform.

Responsibilities:

- Monitor endpoint activity
- Detect malicious processes
- Trigger Detection & Response (D&R) rules
- Send alerts to Tines via webhook
- Isolate compromised endpoints

---

### Tines

Tines acts as the SOAR platform.

Responsibilities:

- Receive detection alerts
- Parse detection details
- Send notifications
- Present analyst approval form
- Execute isolation actions
- Orchestrate the entire workflow

---

### Slack

Used for real-time SOC notifications.

Notifications include:

- Detection details
- Isolation status
- Analyst decisions

---

### Email

Used as an additional notification channel.

Provides:

- Detection details
- Investigation information
- Detection link

---

### User Prompt

Allows an analyst to approve or reject endpoint isolation.

Options:

- Yes → Isolate endpoint
- No → Do not isolate endpoint

---

## Data Flow

1. Endpoint executes a suspicious tool.
2. LimaCharlie detects the activity.
3. Detection is sent to Tines through a webhook.
4. Tines sends alerts to Slack and Email.
5. Tines displays an approval prompt.
6. Analyst chooses an action.

### If Approved

- Tines calls the LimaCharlie Isolation API.
- Endpoint is isolated.
- Slack receives confirmation.

### If Rejected

- Endpoint remains active.
- Slack receives a notification indicating isolation was declined.

---

## Security Controls

- JWT authentication for LimaCharlie API access
- Analyst approval before containment
- Automated notification and audit trail
- Centralized incident response workflow

---

## Technologies Used

- LimaCharlie EDR
- Tines SOAR
- Slack API
- Email Integration
- REST API
- JWT Authentication
