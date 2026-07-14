# Setup Guide

## Prerequisites
- Tines Account
- LimaCharlie Account
- Slack Workspace
- Email Account

## 1. Create a LimaCharlie Organization
- Sign up for LimaCharlie.
- Create a new organization.

## 2. Install the LimaCharlie Agent
- Download the Windows sensor.
- Install it on the endpoint.
- Verify the sensor appears online in the LimaCharlie console.

## 3. Create a Detection Rule
- Create a D&R rule to detect malicious process execution (e.g., LaZagne).
- Configure the rule to trigger a webhook.

## 4. Configure Tines
- Create a new Story.
- Add the Webhook action.
- Import the provided story JSON.

## 5. Configure Slack
- Create a Slack App.
- Generate a Bot OAuth Token.
- Add the `chat:write` permission.
- Connect the credential in Tines.

## 6. Configure Email
- Create the email credential.
- Add the HTML email template.

## 7. Configure LimaCharlie API
- Generate a JWT API token.
- Add it as a credential in Tines.
- Configure the HTTP Request action for sensor isolation.

## 8. Test the Workflow
- Execute LaZagne (or another test detection).
- Verify:
  - Slack alert
  - Email alert
  - User prompt
  - Sensor isolation (if approved)
