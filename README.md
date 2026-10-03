# customer-support-ticket-priority-agentforce
Salesforce and Agentforce based Customer Support Ticket Priority Prediction and Automated Assignment System.
# Customer Support Ticket Priority Prediction and Automated Assignment System Using Agentforce

## 📌 Project Overview

The Customer Support Ticket Priority Prediction and Automated Assignment System is a Salesforce and Agentforce based solution designed to automate customer support ticket prioritization and assignment.

The system retrieves the latest support ticket associated with a customer Account, analyzes the ticket description, determines its priority as High, Medium, or Low, and triggers the appropriate Salesforce automation.

For High-priority tickets, the system automatically creates an urgent handling Task and assigns the ticket to the configured senior support level.

---

## 🎯 Objectives

- Automatically classify support tickets as High, Medium, or Low priority.
- Retrieve the latest support ticket associated with a customer Account.
- Analyze ticket descriptions using configured urgency conditions.
- Automatically create an urgent Task for High-priority tickets.
- Assign High-priority tickets to the appropriate support level.
- Provide ticket analysis through Agentforce.
- Reduce repetitive manual support operations.
- Improve consistency in ticket prioritization and assignment.

---

## 🏗️ System Architecture

The implemented system consists of:

- Salesforce CRM
- Support Ticket Intelligence custom object
- Account and Contact records
- Auto-Launched Salesforce Flow
- Agentforce
- Support Ticket Priority Analysis subagent
- Flow-based Agentforce Action
- Salesforce Task automation

### Workflow

Customer / Support Request

↓

Account Identification

↓

Latest Support Ticket Retrieval

↓

Ticket Description Analysis

↓

Priority Classification

↓

High / Medium / Low Decision

↓

Agent Assignment

↓

Urgent Task Creation for High Priority

↓

Agentforce Response

---

## 🤖 Agentforce

The Agentforce subagent used in this project is:

**Support Ticket Priority Analysis**

### Responsibilities

The subagent:

1. Accepts the customer Account Name.
2. Retrieves the latest support ticket.
3. Analyzes the ticket description.
4. Determines the ticket priority.
5. Triggers the backend Salesforce Flow.
6. Creates an urgent Task for High-priority tickets.
7. Assigns the appropriate support level.
8. Returns the result to the user.

---

## ⚙️ Priority Classification

| Priority | Conditions |
|---|---|
| High | urgent, not working, failure |
| Medium | issue, slow, delay |
| Low | None of the configured High/Medium conditions |

### High Priority

When a ticket is classified as High:

- Priority is set to High.
- An `Urgent Ticket Handling` Task is created.
- Task priority is set to High.
- Task status is set to Not Started.
- The ticket is assigned to the configured senior support level.

### Medium Priority

The ticket is classified as Medium and the system returns a medium-priority handling message.

### Low Priority

The ticket is classified as Low and is queued for processing.

---

## 🗃️ Salesforce Data Model

### Custom Object

**Support Ticket Intelligence**

API Name:

```text
Support_Ticket_Intelligence__c
