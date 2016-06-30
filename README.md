# abacus

## Service Details
+ Node.JS

## Requirements
+ Ability to specify date/time range
+ Ability to run script at any time and will only generate new data since the last time it ran
+ Generates two reports, one for payouts of renters and one for billing for farmers
+ Ability to have a master process that controls running multiple instances of abacus so that it can be scaled
  + This would allow us to tell each worker to handle X date/time range and then combine those proposals into a single proposal or proposal group

## Questions?
+ Should this data be published?
+ Proof process? How do we confirm?
  + Something looks fishy, dump all data used to generate data or report?
  + How to handle discrepancy
+ How do we do signed receipts between two users and how do they get reported to us

## Proposal Spec
Two parts, payouts and billing

### Payouts ( Farmer Services )
+ Storage totals from contracts
+ Transfer totals for upload/downloads

### Billing ( Renter Usage )
+ Storage totals from contracts
+ Transfer totals for upload/downloads
+ Consider Audits
+ Other Params or Limitations
  + X amount of SJX in account
  + Total number of farmers running
  + Network Karma ( something to track good or bad netizens )

## API Spec
