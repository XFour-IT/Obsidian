# Brief Requirements from Jen
- Be able to view interest activity from different CoEd team members
- Easily filter by title rather than having to go into each customer/ opportunity 
- Good reporting
- Ability to open opportunity directly from an interest record
- Exclusivity reporting - on a per territory basis
# Initial Ideas
- Use of leads (Particularly at fairs/ conferences)
- Use of new entities to record interest
	- New entity for series
		- Child products
		- We may be able to use some OOTB features but I suspect this would be incompatible with the BC sync
	- Subgrids on accounts & series to record interests
## Notes from Andy
**Key purpose is to identify which customers are interested in which products**
| Series | Customer | Interest | Timeline
- Series are recorded in BC as parents of series
- Need to investigate: 
	- Syncing of series from BC
	- Filtering out child 
# Jen's Existing Sheet
| Country | Customer | Customer Order Status | Series           | Title                                 | Imprint | Date of Interest | Sample Sent | PDF sent | Notes |
| ------- | -------- | --------------------- | ---------------- | ------------------------------------- | ------- | ---------------- | ----------- | -------- | ----- |
| Poland  | ABC Corp | Confirmed             | Sparkly Art      | Various                               | Bookoli | 30/04/2021       | 01/01/1970  | 2024     | ...   |
|         |          | Not available         | Know & Glow      | Hello Baby                            | Hinkler | Bologna21        | Already has | Y        |       |
|         |          | Rejected              | Baby Record Book | My First Vehicles<br>My First Animals | Both    | FF19             | NYP         | X        |       |
# System Design
[[CoEd Interest Tracker Design]]