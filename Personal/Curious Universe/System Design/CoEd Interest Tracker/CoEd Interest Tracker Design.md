> [!danger] Out of Date
> # This page has been superseded!
> **See [[CoEd Interest Tracker v2]] for the latest design**
> For context, see [[23.05.2024 Andy Feedback]] 

***
# High Level Overview
See [[CoEd Interest Tracker Notes]] for context. 
## Features
- Using an editable grid at the view level to allow rapid updates
- Links to customer & opportunity to allow better tracking
## Potential Improvements
- Button in ribbon to allow creation of lead from interest record
- We could use a BPF instead of button to move from the interest to opportunity/ lead
***
# Technical Implementation
New tables, security roles & data may be required. 
## Security Roles
CoEd Uplift: Access to CRU[^1] the Customer Interest & Event tables. 
## Data
Addition of countries as child territories under the CoEd territory. 
## Tables
Customer Interest, Imprint & Events
### Customer Interest
Core table that holds the customer interest data. 

| Column Name           | Data Type                                | Description                                        | Mandatory                                       | Notes                                                                                                                                                      |
| --------------------- | ---------------------------------------- | -------------------------------------------------- | ----------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Country               | Lookup to territory                      | The country that the customer is based in          | Optional                                        | Will require countries to be setup as child territories underneath the existing ones. Alternatively could use a dropdown or lookup to a new country table. |
| Customer              | Lookup to account                        | The customer that has expressed interest           | Form-Level                                      |                                                                                                                                                            |
| Customer Order Status | Dropdown                                 | The status of the order regarding this series      | TBD                                             | Can either be a dropdown that the salesperson selects or an automated column based off the status of the linked opportunity                                |
| Opportunity           | Lookup to opportunity table              | The opportunity related to this series             | Optional                                        | Could amend to look at lead or opportunity                                                                                                                 |
| Series                | Single-line text                         | The series the customer is interested in           | Optional                                        |                                                                                                                                                            |
| Title                 | Single-line text                         | The title the customer is interested in            | Optional                                        |                                                                                                                                                            |
| Imprint               | Lookup to Imprint table                  | The imprint the book will be branded under         | Optional                                        | Lookup to allow future expansion without dev involvement                                                                                                   |
| Date of Interest      | Date only                                | The date the customer expressed interest           | Optional                                        |                                                                                                                                                            |
| Event                 | Lookup to event table                    | The event where the customer expressed interest    | Optional                                        | New event table? Date of interest often holds non-date data                                                                                                |
| Sample Sent           | Choice (Yes, No, Not Needed)             | Has the sample been sent to the customer?          | Optional                                        |                                                                                                                                                            |
| Sample Type           | Multi-select Choice (Physical, PDF, ???) | What type of sample has been sent to the customer? | Optional                                        | Global choice: Physical, PDF, Other                                                                                                                        |
| Other Sample Type     | Short-Text                               |                                                    | Required **if *Sample Type* is set to *Other*** | On form but hidden; business rule to display if *Sample Type* is set to *Other*                                                                            |
### Imprint
Enables future addition of imprints without developer involvement. 

| Column Name | Data Type  | Notes |
| ----------- | ---------- | ----- |
| Name        | Short Text |       |
### Event
Conferences, fairs, etc. that have been attended and subsequently generated interests. 

| Column Name | Data Type              | Notes               |
| ----------- | ---------------------- | ------------------- |
| Event Name  | Short Text             | Primary Name Column |
| Start Date  | Date Only              |                     |
| End Date    | Date Only              |                     |
| Territory   | Lookup to territory    |                     |
| Attendance  | Subgrid of salespeople |                     |
***
[^1]: Create, Read, Update permissions
# Ancillary Tasks
- [ ] View for Customer Interest
- [ ] View for Event
- [ ] View for Imprint
- [ ] Form for Customer Interest
- [ ] Form for Event
- [ ] Form for Imprint
- [ ] Enable editable grid by default on Customer Interest table views