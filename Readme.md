# SOAR EDR Automation with Tines & LimaCharlie

## Overview

Automates incident response using:

- LimaCharlie EDR
- Tines SOAR
- Slack
- Email
- Analyst Approval
- Automated Sensor Isolation

---

## Features

✔ Receive LimaCharlie Detection

✔ Send Slack Alert

✔ Send Email Alert

✔ Analyst Approval Page

✔ One-click Sensor Isolation

✔ Notification when isolation is declined

---

## Architecture

(insert architecture image)

---

## Workflow

1. LimaCharlie detects malicious activity
2. Webhook sends detection to Tines
3. Slack notification sent
4. Email notification sent
5. Analyst receives approval page
6. If YES
      → Sensor isolated
      → Slack confirmation
7. If NO
      → Slack notification only

---

## Technologies

- LimaCharlie
- Tines
- Slack API
- JWT Authentication
- REST APIs

---

## Demo

GIF/video

---


## Screenshots

...
