# Automated Network Request Management in ServiceNow

An automated workflow solution built using ServiceNow to simplify network service request submission, record management, approval processing, email notification generation, and catalog task closure.

## Project Overview

The **Automated Network Request Management** project demonstrates how ServiceNow Service Catalog and Flow Designer can be used to organize and automate network request processing.

Users submit requests through a catalog form. The system processes the submitted information, creates a database record, generates an email notification record, and routes the request for approval. Based on the approval outcome, the workflow follows the appropriate processing branch.

## Objectives

* Simplify network service request submission.
* Dynamically display form fields based on user selections.
* Store request information in a custom ServiceNow table.
* Automate approval processing using Flow Designer.
* Generate email notification records.
* Manage approval outcomes and catalog task completion.
* Maintain a structured request-processing workflow.

## Key Features

* **Service Catalog:** A dedicated Network Request form for submitting service requests.
* **Dynamic UI Policy:** Displays the existing identification field when the user selects an existing connection.
* **Requester Information:** Captures relevant requester details.
* **Custom Database Table:** Stores network request information.
* **Flow Designer Automation:** Connects request processing actions in a structured flow.
* **Approval Workflow:** Routes requests to the configured approver.
* **Conditional Processing:** Supports separate Approved and Rejected branches.
* **Email Notification:** Generates a notification record containing the configured recipient, subject, and message.
* **Catalog Task Management:** Supports catalog task closure after processing.

## Technology and Platform

* ServiceNow Service Catalog
* ServiceNow Flow Designer
* Catalog UI Policies
* Custom ServiceNow Tables
* Approval Actions
* Email Notification Records
* ServiceNow Catalog Tasks
* JavaScript for ServiceNow configuration and scripting, where applicable

## Workflow

1. The user submits a Network Request through the Service Catalog.
2. The UI Policy dynamically controls the visibility of the existing identification field.
3. Flow Designer retrieves the submitted catalog variables.
4. The workflow creates a record in the custom table `u_database_table`.
5. An email notification record is generated.
6. The request is sent for approval.
7. The workflow evaluates the approval outcome.
8. The Approved or Rejected branch updates the record accordingly.
9. The associated catalog task can be closed after processing.

## Implementation Components

| Component                          | Purpose                              |
| ---------------------------------- | ------------------------------------ |
| Network Request Catalog Item       | Collects network request information |
| Catalog UI Policy                  | Controls dynamic field visibility    |
| Requester Information Variable Set | Collects requester details           |
| `u_database_table`                 | Stores request records               |
| Network Request Automation         | Coordinates the workflow             |
| Ask For Approval                   | Handles approval processing          |
| Approved / Rejected Branches       | Processes approval outcomes          |
| Email Notification Record          | Stores the generated notification    |
| Catalog Task                       | Tracks request processing            |

## Testing and Observed Results

The following results were observed during testing:

* The existing identification field became visible when Existing was selected.
* A flow execution completed, and the approval condition evaluated to True.
* Database record `DAT0001015` showed Approval Status as Approved.
* Catalog task `SCTASK0010008` showed State as Closed Complete.
* An email notification record was generated with the subject `Network Request Received - Pending Approval`.

**Known limitations:**

* Actual external email delivery has not been verified because an active SMTP account was not configured.
* The requester phone number did not automatically populate for the administrator in the tested configuration.
* The Rejected branch and all database field mappings should be considered verified only when supported by actual test evidence.
Project Resources
Project Demo Drive Folder: https://drive.google.com/drive/folders/1PAaBuybnLuN8JptoJ27fXBuDrTUFdcjM?usp=sharing




