# HESK Helpdesk Test Cases

## Test Case Summary

| Test Case ID | Test Scenario | Priority | Type | Status |
|---|---|---|---|---|
| TC-001 | Verify customer can successfully submit a support ticket | High | Functional / End-to-End | Pass |

---

## TC-001 — Customer Successfully Submits Support Ticket

**Test Case ID:** TC-001  
**Title:** Verify customer can successfully submit a support ticket  
**Module:** Customer Portal / Ticket Submission  
**Priority:** High  
**Test Type:** Functional, Positive, End-to-End  
**Preconditions:**
- Customer has access to the HESK Customer Portal.
- HESK demo environment is available.
- Valid test data is available.

### Test Data

**Subject:**
> Unable to connect to company Wi-Fi

**Description:**
> I am unable to connect my laptop to the company Wi-Fi network. I have restarted the laptop and tried reconnecting several times, but the issue persists.

**Priority:** Normal/Medium

### Test Steps

| Step | Action | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| 1 | Log in to the HESK Customer Portal | Customer dashboard is displayed | Customer dashboard displayed successfully | Pass |
| 2 | Select "Submit a ticket" | Ticket submission form is displayed | Ticket submission form displayed successfully | Pass |
| 3 | Enter valid ticket information | Data is accepted without validation errors | Data accepted successfully | Pass |
| 4 | Enter the displayed spam-prevention code | Code is accepted | Code accepted successfully | Pass |
| 5 | Submit the ticket | Ticket is successfully created | Ticket submitted successfully | Pass |
| 6 | Review the confirmation message | Confirmation and ticket ID are displayed | Confirmation and ticket ID displayed | Pass |
| 7 | Open "My Tickets" | Newly created ticket is displayed | Ticket displayed successfully | Pass |
| 8 | Open the newly created ticket | Ticket details are displayed and status is "New" | Ticket displayed with status "New" | Pass |

### Expected Result

A customer should be able to submit a valid support ticket successfully. HESK should generate a unique ticket ID, display a confirmation message, and make the ticket available under "My Tickets" with the appropriate initial status.

### Actual Result

The ticket was successfully submitted. HESK generated a ticket ID, displayed a confirmation message, and the ticket appeared under "My Tickets" with status **New**.

### Final Result

**PASS**

### Evidence

Evidence will be captured during formal test execution and stored in:

`/Evidence/TC-001/`












---

## TC-002 — Required Field Validation

**Test Case ID:** TC-002  
**Title:** Verify required fields prevent submission when left blank  
**Module:** Customer Portal / Ticket Submission  
**Priority:** High  
**Test Type:** Negative / Validation  
**Preconditions:**
- Customer is logged into the HESK Customer Portal.
- Support category is available.
- HESK demo environment is accessible.

### Test Scenario A — Subject Left Blank

| Step | Action | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| 1 | Select the Support category | Support ticket form is displayed | Support ticket form displayed | Pass |
| 2 | Leave Subject blank | Subject remains empty | Subject remained empty | Pass |
| 3 | Enter valid message content | Message is accepted | Message accepted | Pass |
| 4 | Enter valid spam-prevention code | Code is accepted | Code accepted | Pass |
| 5 | Select Submit Ticket | Submission should be blocked and validation should be displayed | Browser displayed "Please fill out this field." | Pass |

### Test Scenario B — Message Left Blank

| Step | Action | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| 1 | Enter a valid Subject | Subject is accepted | Subject accepted | Pass |
| 2 | Leave Message blank | Message remains empty | Message remained empty | Pass |
| 3 | Enter valid spam-prevention code | Code is accepted | Code accepted | Pass |
| 4 | Select Submit Ticket | Submission should be blocked and validation should be displayed | Browser displayed "Please fill out this field." | Pass |

### Expected Result

The application should prevent ticket submission when required fields are empty and provide appropriate validation feedback.

### Actual Result

Submission was prevented when either Subject or Message was left blank. The browser displayed the validation message **"Please fill out this field."**

### Final Result

**PASS**

### Defect

No defect identified.

### Evidence

Evidence will be captured during formal test execution and stored in:

`/Evidence/TC-002/`