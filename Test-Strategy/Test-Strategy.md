# HESK Helpdesk QA Test Strategy

## 1. Project Overview

This project is an end-to-end software quality assurance assessment of the HESK help desk application.

The objective is to evaluate core customer and staff workflows, identify functional defects, validate data consistency across user roles, and document test evidence and results.

## 2. Application Under Test

- Application: HESK Help Desk
- Version: 3.7.11
- Environment: Public HESK Demo
- User Roles: Customer, Staff
- Testing Approach: Manual functional and exploratory testing

## 3. Initial Workflow Validated

Customer ticket submission and staff response workflow:

1. Customer logs into the Customer Portal.
2. Customer submits a support ticket.
3. Spam-prevention validation is completed.
4. Ticket ID is generated.
5. Ticket appears in My Tickets.
6. Initial ticket status is displayed as "New".
7. Staff accesses the ticket through the Staff Panel.
8. Staff submits a response.
9. Ticket status changes to "Replied".
10. Customer can view the staff response.

## 4. Initial Execution Result

The initial end-to-end workflow was successfully executed in the HESK demo environment.

Result: PASS