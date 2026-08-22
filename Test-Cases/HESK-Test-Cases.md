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






---

## TC-003 — Invalid Spam Prevention Code

**Test Case ID:** TC-003  
**Title:** Verify ticket submission is blocked when an invalid spam-prevention code is entered  
**Module:** Customer Portal / Ticket Submission  
**Priority:** High  
**Test Type:** Negative / Security Validation  
**Preconditions:**
- Customer is logged into the HESK Customer Portal.
- Support category is available.
- HESK demo environment is accessible.

### Test Steps

| Step | Action | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| 1 | Select the Support category | Support ticket form is displayed | Support ticket form displayed | Pass |
| 2 | Enter a valid Subject | Subject is accepted | Subject accepted | Pass |
| 3 | Enter a valid Message | Message is accepted | Message accepted | Pass |
| 4 | Enter an intentionally incorrect spam-prevention code | Invalid code should be rejected | Invalid code entered | Pass |
| 5 | Select Submit Ticket | Ticket submission should be blocked with an appropriate validation error | System displayed "Wrong security number" | Pass |

### Expected Result

The system should prevent ticket submission when an invalid spam-prevention/security code is entered and provide an appropriate validation message.

### Actual Result

The system prevented ticket submission and displayed the error message:

**"Wrong security number"**

### Final Result

**PASS**

### Defect

No defect identified.

### Evidence

Evidence will be captured during formal test execution and stored in:

`/Evidence/TC-003/`











---

## TC-004 — Attachment Upload

**Test Case ID:** TC-004  
**Title:** Verify customer can attach a supported file to a support ticket  
**Module:** Customer Portal / Ticket Submission / Attachments  
**Priority:** Medium  
**Test Type:** Functional  
**Preconditions:**
- Customer is logged into the HESK Customer Portal.
- Support category is available.
- HESK demo environment is accessible.
- A non-sensitive test PNG file is available.

### Test Steps

| Step | Action | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| 1 | Select the Support category | Support ticket form is displayed | Support ticket form displayed | Pass |
| 2 | Enter valid Subject and Message | Ticket information is accepted | Information accepted | Pass |
| 3 | Select Add File and choose a supported PNG test file | File should be accepted and attached | Demo displayed "Sorry, this function has been disabled in DEMO mode!" | Blocked |
| 4 | Submit the ticket with the attachment | Ticket should be submitted with the attachment | Not executed because attachment functionality is disabled | Blocked |

### Expected Result

A supported attachment should be accepted and associated with the support ticket.

### Actual Result

The HESK public demo displayed:

**"Sorry, this function has been disabled in DEMO mode!"**

The attachment functionality could not be tested in the public demo environment.

### Final Result

**BLOCKED**

### Defect

No defect raised because the behavior is an explicit demo-environment restriction rather than an application defect.

### Evidence

Evidence will be captured during formal test execution and stored in:

`/Evidence/TC-004/`





---

## TC-005 — Ticket Priority Consistency

**Test Case ID:** TC-005  
**Title:** Verify selected ticket priority is correctly retained across customer and staff views  
**Module:** Customer Portal / Ticket Management / Staff Panel  
**Priority:** Medium  
**Test Type:** Functional / Data Consistency  
**Preconditions:**
- Customer is logged into the HESK Customer Portal.
- Support category is available.
- HESK demo environment is accessible.

### Test Steps

| Step | Action | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| 1 | Select the Support category | Support ticket form is displayed | Support form displayed | Pass |
| 2 | Select High priority | High priority is selected | High priority selected | Pass |
| 3 | Enter valid Subject and Message | Ticket information is accepted | Information accepted | Pass |
| 4 | Enter valid spam-prevention code and submit | Ticket is created successfully | Ticket created successfully | Pass |
| 5 | Open the ticket from My Tickets | Customer should see High priority | Customer view displayed High priority | Pass |
| 6 | Open the same ticket from the Staff Panel | Staff should see High priority | Staff view displayed High priority | Pass |

### Expected Result

The priority selected by the customer should be retained correctly and displayed consistently in both the customer and staff views.

### Actual Result

The selected **High** priority was displayed as **High** on both the customer and staff sides.

### Final Result

**PASS**

### Defect

No defect identified.

### Evidence

Formal evidence will be captured during the test execution cycle.







---

## TC-006 — Ticket Resolution and Status Synchronization

**Test Case ID:** TC-006  
**Title:** Verify staff can resolve a ticket and the resolved status is reflected for the customer  
**Module:** Staff Panel / Ticket Management / Customer Portal  
**Priority:** High  
**Test Type:** Functional / End-to-End / Data Consistency  
**Preconditions:**
- Customer ticket exists.
- Staff has access to the ticket.
- Ticket status is New.
- Ticket has High priority.

### Test Steps

| Step | Action | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| 1 | Open the ticket in the Staff Panel | Ticket details are displayed | Ticket displayed | Pass |
| 2 | Change Ticket Status from New to Resolved | Resolved status can be selected | Resolved selected | Pass |
| 3 | Save/update the ticket | Ticket status changes to Resolved | Ticket resolved successfully | Pass |
| 4 | Verify ticket priority | High priority should remain unchanged | Priority remained High | Pass |
| 5 | Open the same ticket from the Customer Portal | Customer should see the updated ticket status | Customer displayed Resolved | Pass |
| 6 | Verify ticket conversation | Original ticket information should remain available | Original information remained available | Pass |

### Expected Result

A staff member should be able to resolve a ticket successfully. The Resolved status should be synchronized to the customer view without changing unrelated ticket information.

### Actual Result

The staff member successfully changed the ticket status from **New** to **Resolved**. The customer view also displayed **Resolved**, while the ticket priority remained **High**.

### Final Result

**PASS**

### Defect

No defect identified.

### Evidence

Formal evidence will be captured during the test execution cycle.






---

## TC-007 — Knowledgebase Article Access

**Test Case ID:** TC-007  
**Title:** Verify customer can access and view a Knowledgebase article  
**Module:** Customer Portal / Knowledgebase  
**Priority:** Medium  
**Test Type:** Functional / Navigation  
**Preconditions:**
- Customer is logged into the HESK Customer Portal.
- Knowledgebase is available.

### Test Steps

| Step | Action | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| 1 | Open the Knowledgebase | Knowledgebase page is displayed | Knowledgebase displayed | Pass |
| 2 | Select "Welcome to HESK demo" | Article should open | Article opened successfully | Pass |
| 3 | Verify article title | Article title should be displayed | Title displayed | Pass |
| 4 | Verify article content | Article content should be displayed | Content displayed | Pass |
| 5 | Verify article category | Article category should be displayed | Category displayed | Pass |
| 6 | Navigate back to the Knowledgebase | User should return to the Knowledgebase | Navigation completed successfully | Pass |

### Expected Result

The customer should be able to access a Knowledgebase article and view its title, category, and content without errors.

### Actual Result

The "Welcome to HESK demo" article opened successfully. The title, category, and content were displayed, and navigation back to the Knowledgebase was successful.

### Final Result

**PASS**

### Defect

No defect identified.

### Evidence

Formal evidence will be captured during the test execution cycle.






---

## TC-008 — My Tickets Information Display

**Test Case ID:** TC-008  
**Title:** Verify customer can view key information for existing tickets  
**Module:** Customer Portal / My Tickets  
**Priority:** Medium  
**Test Type:** Functional / Data Display  
**Preconditions:**
- Customer is logged into the HESK Customer Portal.
- At least one ticket has been created for the customer.

### Test Steps

| Step | Action | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| 1 | Open My Tickets | Customer's ticket list should be displayed | Ticket list displayed | Pass |
| 2 | Locate the "High priority ticket validation test" ticket | Ticket should be available in the list | Ticket found | Pass |
| 3 | Verify Ticket ID | Ticket ID should be displayed | Ticket ID displayed | Pass |
| 4 | Verify Subject | Correct ticket subject should be displayed | Subject displayed correctly | Pass |
| 5 | Verify Status | Current ticket status should be displayed | Status displayed as Resolved | Pass |
| 6 | Verify Date | Ticket date should be displayed | Date displayed | Pass |

### Expected Result

The My Tickets page should display key information for the customer's existing tickets, including Ticket ID, Subject, Status, and Date.

### Actual Result

The ticket list displayed the Ticket ID, correct Subject, Resolved status, and Date for the tested ticket.

### Final Result

**PASS**

### Defect

No defect identified.

### Evidence

Formal evidence will be captured during the test execution cycle.







---

## TC-009 — Find Ticket by Tracking ID

**Test Case ID:** TC-009  
**Title:** Verify staff can locate a ticket using its Tracking ID  
**Module:** Staff Panel / Ticket Search  
**Priority:** Medium  
**Test Type:** Functional / Search  
**Preconditions:**
- Staff has access to the HESK Staff Panel.
- At least one customer ticket exists.
- A valid Tracking ID is available.

### Test Steps

| Step | Action | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| 1 | Open the Staff Panel | Staff dashboard is displayed | Staff Panel displayed | Pass |
| 2 | Navigate to Find a Ticket | Ticket search interface is displayed | Find a Ticket interface displayed | Pass |
| 3 | Select Tracking ID under Search in | Tracking ID search option is selected | Tracking ID selected | Pass |
| 4 | Enter the Tracking ID for "Unable to connect to company Wi-Fi" | Tracking ID is accepted | Tracking ID accepted | Pass |
| 5 | Select Find Ticket | Matching ticket should be returned | Correct ticket returned | Pass |
| 6 | Verify ticket subject | Subject should match the searched ticket | "Unable to connect to company Wi-Fi" displayed | Pass |
| 7 | Verify ticket status and priority | Current values should be displayed correctly | Replied / Medium displayed | Pass |

### Expected Result

The Staff Panel should locate and display the correct ticket when a valid Tracking ID is entered.

### Actual Result

HESK successfully located the ticket associated with the supplied Tracking ID. The returned ticket displayed the expected subject, **Replied** status, and **Medium** priority.

### Final Result

**PASS**

### Defect

No defect identified.

### Evidence

Formal evidence will be captured during the test execution cycle.