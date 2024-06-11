# Emergency Calls
| Cat | Description                                                                | Response target      |
| --- | -------------------------------------------------------------------------- | -------------------- |
| 1   | Imminent death                                                             | 7 mins               |
| 2   | Emergency                                                                  | 18 mins              |
| 3   | Urgent                                                                     | 2 hours              |
| 4   | Less urgent                                                                | 3 hours              |
| 5   | Referrals/ signposting<br>Anything that *really* doesn't need an Ambulance | No response required |
Cat1: 11 seconds from incident "live" to ambulance dispatch
ISEC: Gives vague location to Ambulance service
AML - Advanced Mobile Location: SMS message to 999 which gives exact location from GPS
If any core risk identifiers, immediately send pred. lvl.1 call. 
API into BHF defib map
Internal LAS defib with auto-contact to PoCs in defib locations
**Caller may not be at the location of the emergency**
# Problems with the current system
- No data gets sent to Ambulance service if a caller doesn't have native 
- Call handlers don't have access to the internet - Ordnance Survey data currently used to identify addresses
	- Tube stations are an issue
		- Multiple address sources
		- Location is relatively unspecific
	- LAS has made internal "hacks" to fix the issues presented by the address limitations from CAD
	- LAS doesn't use district field because London. District field is used to contain any codes from TfL/ NR
# Triage systems
The second a call is triaged at cat1, the ambulance is dispatched even if the human dispatcher hasn't opened the incident yet. 
Cat1 Response types
1. DCA (Double crew ambulance)
2. FRU/ CRU/ MRU/ TRU/ C1 only
3. Paramedic
4. Emergency Responder/ Community First Responder/ FPOS1/ FPOS2
## NHS Pathways
Unknown data - relatively open source
## MPDS - Medical Priority Dispatch System
- Every possible circumstance is broken down into a list of relevant questions
- Based on outcome of call, triage determinant code. Defines what and how emergent. 
## Emergency Call Priority Group
NHS England
Assigns priority to every triage code
Gets imported into CAD
# Resiliency
- 100% SLA
- Two completely distinct ISDN trunks. Alongside, two distinct SIP trunks. 
- In catastrophic circumstances, call handlers can do everything on paper
	- Fax machines between all ambulance stations & dispatchers
- Redundant system to copy all data from CAD to redundant backup that can be printed
# Socials
@skylar@tilde.zone
@lasskylar