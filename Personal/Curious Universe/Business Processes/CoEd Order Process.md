1. Order Confirmation
2. Draft pre-contract
3. Send to Dania for approval
4. Dania sends to Production, PubOps and Polly & Tom
5. Added to MPP
6. Polly raises contract based on info in pre-contracts
```mermaid
flowchart TB
orderConf([Order Confirmation])
preContDraft(Pre-Contract Drafted)
daniaApproval{Send to Dania for approval}
unknown{{Unknown}}
daniaForward(Dania sends to Production, PubOps, Polly & Tom)
mpp("Product(s) added to MPP")
contract([Polly raises contract based on info in pre-contract])

orderConf --> preContDraft --> daniaApproval
daniaApproval -->|Changes Required|unknown
daniaApproval --> |Approved| daniaForward
daniaForward --> mpp --> contract
```