This note outlines the process of setting up a virtual relationship between a virtual table from Business Central and a native CRM table. This process assumes that the underlying BC sync is already setup. 
## Enable Sync
1. Set the virtual tables to visible within the "Business Central Config" app in Dataverse. 
## Create relationship
1. Create the key for the BC ID within the native parent table. 
2. Create a new "Synthetic Relation" and set the data in line with the table below. Use logical names throughout

| Tab     | Field            | Data                                                                            |
| ------- | ---------------- | ------------------------------------------------------------------------------- |
| General | Relation Name    | A sensible, unique name                                                         |
|         | Native Table     | The name of the CRM **parent** table                                            |
|         | Native Table Key | The name of they **key** that was created in step 1                             |
|         | Virtual Table    | The name of the virtual table in CRM                                            |
| Mapping | Native columns   | The name of the column on the parent table that contains it's unique ID         |
|         | Virtual columns  | The name of the column on the child table that contains it's parent's unique ID |
### Account Example
This example creates a relationship between the **CRM** account table and the **virtual** sales invoice table. 
1. Create a key for the "Account Number" field on the account table in CRM
2. Create a new "Synthetic Relation" with the following data

| Tab     | Field            | Data                       |
| ------- | ---------------- | -------------------------- |
| General | Relation Name    | crmaccounttobcsalesorder   |
|         | Native Table     | account                    |
|         | Native Table Key | cre2e_bcaccountnumber      |
|         | Virtual Table    | dyn365bc_salesinvoice_v2_0 |
| Mapping | Native columns   | accountnumber              |
|         | Virtual columns  | dyn365bc_customernumber    |