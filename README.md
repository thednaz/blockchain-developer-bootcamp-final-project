# blockchain-developer-bootcamp-final-project

## GoalToken - Goal Setting by Staking Funds

Many people have a hard time fulfilling their goals because there's not enough incentive or motivation to do so. What if we could use the blockchain to provide that motivation? 

A user can stake their funds to achieve a goal by some deadline, and have trusted friends be their referees to keep them honest.

### Staking flow
- A user must connect to their MetaMask wallet to be identified
- They specify:
	- Amount to lock/stake
	- Deadline date and time (deadline is set to +7 days as a grace period)
	- Beneficiary address that funds will go to if goal isn't met (e.g. a charity, anti-charity, friend, etc.)
	- A referee address who will determine if the goal has been attained (usually a trusted friend, but a user can set the referee as themselves for a zero-risk goal)
- Funds are staked and user is issued an equal amount of GoalTokens
	
### Return/Success flow
- Referee determines goal has been achieved on or before deadline (by staker submitting evidence to them), or decides to return money to to user due to extenuating circumstances
- Referee sends a return transaction for the previous staking transaction
- GoalTokens issued to staker are burned
- Original funds are returned to staker
	
### Distribute/Failure flow
- Referee determines goal has not been achieved on or before deadline (by staker's admission of failure or providing insufficient evidence to prove goal has been achieved)
- Referee sends a distribute transaction for the previous staking transaction
- GoalTokens issued to staker are burned
- Original funds are sent to beneficiary address
	
### Timeout flow
- Referee has not sent a return/distribute transaction after deadline + 7 day grace period
- GoalTokens issued to staker are burned and original funds are returned to staker
	
### Possible avenues of expansion
- Have multiple beneficiaries (and split funds between them in case of failure)
- Have multiple referees that need to sign off on return/distribute
