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

#### How do we calculate?
(manual process)
  + Calculate per Farmer per Contract
    + GBh for Storage Contracts by farmer
    + GBh for Transfer by farmer

### Billing ( Renter Usage )
+ Storage totals from contracts
+ Transfer totals for upload/downloads
+ Consider Audits
+ Other Params or Limitations
  + X amount of SJX in account
  + Total number of farmers running
  + Network Karma ( something to track good or bad netizens )

#### How do we calculate?
(manual process)

### Data format for first step
  + Storage Usage GBh per time period
  + Transfer GHh per time period

## Execution Plan Phases
  1) Create mongodb query to use for now to aggregate billing data
    + This will work until audits are live as audits clear the download counts that this script will use
  2) Build basic service to use audits to do billing
  3) Reassess and build into microservices with queueing to make robust

## Questions
  + Does the money received from api users go directly to farmers or keep separate
  + Does the data for download count include date/time?
    + If not, we need to add that so that we can query for time ranges
    + We can decode the date/time from the mongo entry
    + Add completion date/time to download
  + How do we handle contracts that failed an audit part way through?

## Things we need that don't exist
  + Download times/speed as reported by the renter (end user) and by the farmer
  + Transfer date/time for download

## API Spec
