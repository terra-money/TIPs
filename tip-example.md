# Terra Improvement Proposal (TIP) Example
 
This example is a nonsense proposal created to show how TIPs can be used. This TIP is not real and contains no real info.   

Although this TIP is relatively succinct, the length of a TIP should reflect the complexity of the change.   
 
# TIP # 143: New credit module 
 
**TIP #**: 143
<br>
**Author**: Satoshi
<br>
**Network**: Magellan-7 <!---Add the mainnet version this change will apply to. -->
<br>
**Date**: 25 December 2090
<br>
 
## Summary
 
<!--- A 1-2 sentence non-technical explanation of the change. Summaries should be easily understood by the general community. -->
 
The Credit-swap logic will be moved to its own module.
 
## Motivation
 
<!--- An explanation of why the change is necessary. What is the problem that needs to be solved? Why do these changes need to be implemented? -->
 
The Loan module is being deprecated, but credit is still needed for the protocol to function properly. The credit logic needs to be moved to its own module.
 
## Tech Spec
 
**Modules:** <!--- List affected modules with short notes on alterations. -->
 
- Loan: module deprecated.
- Market: credit determination logic derives from the market module.
- Credit: module created.
 
### Overview
 
<!---A technical summary of the change and how it will solve the problem. -->
 
The Loan module will be deprecated due to its mostly vestigial code. A new module will be created called the Credit module. This module will house all logic for credit swaps made between Credit-coins. The Credit module structure will be based on the market modules determination logic.
 
### Method
 
<!--- An outline of how the change will be implemented. This can include a numbered list of steps necessary for completion. -->
 
1. Copy Market module structure.
2. Deprecate Loan module.
3. Input logic into credit module.
4. A lot more work
5. Some more work.
 
### Code
 
<!--- Include any applicable code blocks or pseudocode describing the changes. -->
 
 
First credit account:
``` go
 
type creditAccountYAML struct {
   Address          sdk.AccAddress `json:"address" yaml:"address"`
   PubKey           string         `json:"public_key" yaml:"public_key"`
   AccountNumber    uint64         `json:"account_number" yaml:"account_number"`
   Sequence         uint64         `json:"sequence" yaml:"sequence"`
   OriginalCredit  sdk.Coins      `json:"original_credit" yaml:"original_credit"`
   DelegatedFree    sdk.Coins      `json:"delegated_free" yaml:"delegated_free"`
   DelegatedCredit sdk.Coins      `json:"delegated_credit" yaml:"delegated_credit"`
   EndTime          int64          `json:"end_time" yaml:"end_time"`
 
   // custom fields based on concrete credit type which can be omitted
   CreditSchedules VestingSchedules `json:"credit_schedules,omitempty" yaml:"vesting_schedules,omitempty"`
}
 
//-----------------------------------------------------------------------------
// Lazy Graded Credit Account
 
// LazyGradedCreditAccount implements the LazyGradedCreditAccount interface. It credits all
// coins according to a predefined schedule.
var _ credexported.CreditAccount = (*LazyGradedCreditAccount)(nil)
var _ authtypes.GenesisAccount = (*LazyGradedCreditAccount)(nil)
 
// NewLazyGradedCreditAccountRaw creates a new LazyGradedCreditAccount object from BaseCreditAccount
func NewLazyGradedCreditAccountRaw(baseCreditAcc *Credtypes.BaseCreditAccount, lazyCreditSchedules CreditSchedules) *LazyGradedCreditAccount {
   return &LazyGradedCreditAccount{
       BaseVestingAccount: baseCreditAcc,
       VestingSchedules:   lazyCreditchedules,
   }
}
```
 
The second credit account:
```go
 
// NewLazyGradedCreditAccount returns a new LazyGradedCreditAccount
func LazyGradedCreditAccount(baseAcc *authtypes.BaseAccount, originalCredit sdk.Coins, lazyCreditSchedules CreditSchedules) *LazyGradedCreditAccount {
   baseCreditAcc := &credittypes.BaseCreditAccount{
       BaseAccount:      baseAcc,
       OriginalCredit:  originalCredit,
       DelegatedFree:    sdk.NewCoins(),
       DelegatedCredit: sdk.NewCoins(),
       EndTime:          0,
   }
 
```
 
### Considerations
 
<!--- Describe any special or general considerations. Is there anything that we should be cautious about? Are there any invariants to keep in mind? -->
 
The Loan module also contains the logic needed to asses `FileAccounts`. This logic must be moved to another module, as outlined in TIP # 123
 
## Timeline
 
<!--- If applicable, include an estimated project completion time. You can break this up into a list of events. -->
 
The anticipated timeline is five weeks to completion.
- 3 weeks engineering
- 2 weeks testing
 
## Test cases
 
<!--- If applicable, include any test cases or preliminary research related to the change. -->
 
All testing shows that module logic will remain untouched. 


