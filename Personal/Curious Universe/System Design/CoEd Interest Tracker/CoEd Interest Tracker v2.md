> [!important] Version 2.1
# Acceptance Criteria
- [x] Customer Interest Table as detailed in [[#Columns]]
	- [x] Identify [[redundant columns]]
	- [x] Remove [[redundant columns]]
- [x] [[#Country Table]]
- [x] The *All Customer Interests*, Active, Inactive show only the columns *Customer*, *Series* & *Interest*
- [x] *All Interests*, *Active Interests* & *Inactive Interests* views as detailed in [[#Views]]
- [x] "Expressions of Interest" tab on account form
	- Customer Interest Subgrid
	- Default view is *All Interests*
	- User can change views between: *All*, *Active* & *Inactive* ***Interests***
- [x] The Customer Interest Table is **not** on sitemap
- [x] The name column is set to {*Customer*} - {*Series*} using a [workflow](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/overview-realtime-workflows)
- [x] [[#Import Country Codes]] into sandbox
- [x] IN CU CRM NOT CU COED - Modify site map and under "App Settings" add new group "Reference Data". Add Countries to the reference data section. See [[Sitemap Glossary]] for more info.
- [x] Enable quick create form for Customer Interest table
- [x] Quick Create form with all fields from editable grid
- [x] Main form with all fields from editable grid
- [x] AWAIT BL APPROVAL
- [x] Deploy to prod
- [ ] [[#Import Country Codes]] to prod
## Customer Interest Table
A table called *Customer Interest*. 
## Columns

| Column Name         | Data Type                                                                   | Description                                      | Mandatory |
| ------------------- | --------------------------------------------------------------------------- | ------------------------------------------------ | --------- |
| Name                | Primary Name (System)                                                       |                                                  | No        |
| Customer            | Lookup to the account table                                                 | Which customer has expressed interest?           | Yes       |
| Series              | Lookup to series list                                                       | What series is the customer interested in?       | Yes       |
| Interest            | Interested/ Not Interested/ Rightsholder                                    | Where is the customer in the pipeline?           |           |
| Status Reason       | **Active**<br>Interested<br><br>**Inactive**<br>Not Interested Rightsholder |                                                  | Yes       |
| From                | Date                                                                        | Start date of interest                           | Yes       |
| To                  | Date                                                                        | End date of interest                             | Yes       |
| Event               | Short text                                                                  | Which event did the customer show interest?      | No        |
| Notes               | Long text                                                                   | Any additional information?                      | No        |
| Country             | Lookup to the [[#Country Table]]                                            | The country of interest                          | Yes       |
| Sample Sent         | Optionset Complete/ Not Required)                                           | Has a physical sample been sent to the customer? | No        |
| PDF Sent            | Optionset (Complete/ Not Required)                                          | Has a PDF sample been sent to the customer?      | No        |
| Related Opportunity | Lookup to opportunity                                                       |                                                  | No        |
### Views
**This only applies to the *Interests* views not the *Customer Interests* views.**  
| Series | Interest | Country | From | To | Event | Sample Sent | PDF Sent | Notes | Opportunity |
#### For reference
![[View Design.png]]
## Country Table
### Columns
| Column Name  | Data Type                         | Description                                   | Required |
| ------------ | --------------------------------- | --------------------------------------------- | -------- |
| Name         | Primary Name Column (**DEFAULT**) | The name of the country                       | Yes      |
| Country Code | Short Text                        | The ISO 3166 2 character code for the country | Yes      |
## Import Country Codes
File: https://github.com/lukes/ISO-3166-Countries-with-Regional-Codes/blob/master/all/all.csv
### Mapping

| D365 Column  | File Column |
| ------------ | ----------- |
| Name         | name        |
| Country Code | alpha-2     |

# Future Implementations
## Flows

## Ribbon Buttons
All ribbon buttons need to be made for the subgrid
### Create Opportunity
PowerFx button to create an opportunity from the customer interest record
# Requirement Gathering
Customer interest table in line with Andy spreadsheet
## Other features
- [[Create Opp]] button
- When linked opp is closed, interest set to rightsholder
- If not interested, unable to create/ link opportunity
[[CoEd Opportunity Enhancements]]
# Past Versions
See [[CoEd Interest Tracker]] for v1
## v2.0
### Acceptance Criteria
- [x] Customer Interest Table as detailed below
	- [x] Identify [[Redundant Columns]]
	- [ ] Remove redundant columns
- [x] The *All Customer Interests*, Active, Inactive show only the columns *Customer*, *Series* & *Interest*
- [x] The *All Interests*, *Active Interests* & *Inactive Interests* views show only the columns *Series*, *Interest*, *From*, *To*, *Event*, *Notes*
- [x] "Expressions of Interest" tab on account form
	- Customer Interest Subgrid
	- Default view is *All Interests*
	- User can change views between: *All*, *Active* & *Inactive* ***Interests***
- [x] The Customer Interest Table is **not** on sitemap
- [x] The name column is set to {*Customer*} - {*Series*} using a [workflow](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/overview-realtime-workflows)

| Column Name   | Data Type                                                                   | Description                                 | Mandatory |
| ------------- | --------------------------------------------------------------------------- | ------------------------------------------- | --------- |
| Name          | Primary Name (System)                                                       |                                             | No        |
| Customer      | Lookup to the account table                                                 | Which customer has expressed interest?      | Yes       |
| Series        | Lookup to series list                                                       | What series is the customer interested in?  | Yes       |
| Interest      | Interested/ Not Interested/ Rightsholder                                    | Where is the customer in the pipeline?      |           |
| Status Reason | **Active**<br>Interested<br><br>**Inactive**<br>Not Interested Rightsholder |                                             | Yes       |
| From          | Date                                                                        | Start date of interest                      | Yes       |
| To            | Date                                                                        | End date of interest                        | No        |
| Event         | Short text                                                                  | Which event did the customer show interest? | No        |
| Notes         | Long text                                                                   | Any additional information?                 | No        |