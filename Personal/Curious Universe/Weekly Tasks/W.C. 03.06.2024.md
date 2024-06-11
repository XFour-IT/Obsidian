# Tasks
- [ ] Fix Sandbox coupling issues
- [ ] Write [[BC Sync Setup Guide]]
- [ ] Upon success, setup sync in prod to allow for people sync rather than team sync
- [ ] Update opportunity lookup on interest tracker to only fetch opportunities that relate to the account
- [ ] Update opportunity associated view to also include account name
- [ ] Setup goals 
	- [ ] Won Opportunities - Actual & In-progress revenue from opportunities
	- [ ] Orders Raised - Value of invoices raised
		- [ ] Power Automate rollup fields
	- [ ] Billed - Invoiced value less credit notes
		- [ ] Power Automate rollup fields
- [ ] Adjust opportunity close reminder alert to not say "above"
	- The warning location has been moved in the New look
- [x] Chase Kelly about syncing series to CRM
- [x] Setup sync in sandbox to allow safe ALM
- [x] Split orders & invoices into two tabs
- [x] Check BPF requirement bug (Sales Feedback only accepting no)
- [x] Speak with DataConcepts re: admin privs
- [x] Check why in progress is shown as 0 on goals (Possibly to do with the metric?)
- [x] Look into syncing from BC using Power Automate
## Scripting Required
- These will take a while to code so did not have time to complete this weekend. 
- [ ] Alert to update territory field at account level when creating an opportunity  
- [ ] JS to default territory but it must be a changeable field [[Territory Matching Implementation Plan]]
# Notes for Andy
- Financial year cannot be updated to 24/25. It can be configured to use start or end but not both. 
- I've set the financial year to use the start date (e.g. FY24 for 24/25) and I've setup the goals again for the new format. 
- A.D. is genuinely referring to the era of the date. Because for some unknown reason, D365 supports BC financial years. 