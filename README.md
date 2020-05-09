# Onest Blockchain Whitepaper

## Targets
- Turning the blockchain worker system into a public funding system
- Segregating of `transaction utility` and `voting utility`
- Balance the reward and demand between transaction and vote utilitiy 
- Reward workers and loyal utility holders with VOTE
- Allow a natural market selection of VOTE users

## Utility Flow
![utility-flow](https://raw.githubusercontent.com/Onest-io/onest-whitepaper/master/utility-flow.png)

## ONS
Every BTS holder gets rewarded with the same amount of ONS on the new chain. ONS will no longer be used for the function "voting". ONS utility is used for blockchain transaction to reward only Block Producer.

### ONS-power
ONS-power is a new core function to lock ONS. Locked ONS can't be used as collateral or transferred to another account.

```
tau=150; // days
t=0; // days
t_active = 0; // days

ONS_power = locked_ONS * (1 - e^(-t/tau))

if (new day)
{
t = t + 1
t_active = t_active + 1
}

if (t > 450)
{
t = 450
}

if (t_active > 300)
{
t = 0
}

if (locked_ONS increased)
{
t = t * (locked_ONS_old/locked_ONS_new)
t_active = 0
}

if (locked_ONS decreased)
{
t = 0
t_active = 0
}
```

### ONS vesting
Removing ONS from locked ONS, needs 30 days vesting time, until ONS becomes liquid again. 

## VOTE
Blockchain creates every day 10 Millionen VOTE, which rewards the worker system and ONS-power. 

- 6.18 Million VOTE are distributed on active worker proposals, depending on the total worker VOTE-power.
- 3.82 Million VOTE are distributed to staked ONS, depending on ONS-power.

### VOTE-power
The voter can define the emission type over time (constant or linear decrease) and the emission duration (max. 150d). The longer the time period, the lower the VOTE-power. 

`1 VOTE-power` is generated, when 1 VOTE is burnt per day.

`const. VOTE-power = (total burnt VOTE on voting) / (total days for voting)`

The max. VOTE-power is limited by the available ONS-power of the voter account. For 1 VOTE-power 9.5 ONS-power are needed. 

### VOTE-proxy
The ONS-power account can select a proxy for the next 300 days, which recives every day, the daily VOTE reward.  

### VOTE use cases
VOTE can only be used once, by burning itself. 

#### Vote for or against a OIPS
A OIP has 30 active vote days, after the total net VOTE becomes consensus. 

#### Vote for or against a worker
Each active worker earns new VOTE, depending on the net VOTE-power percentage, compared to the total net worker VOTE-power.

##### Worker payout
Vesting is enabled after 14 days, when 20% of the total needed worker VOTE got raindropped during the first 20% of the worker time. Worker gets deactivated, when requirements for vesting is not fulfilled or is fully funded or is out of timetable (max. 365 days).

##### Worker refund
When an active worker doesn't accomplish the requirements for vesting, the collected VOTE are used, to give both VOTE parties a proportional refund.

When the raindropped VOTE from a worker are higher, than the total burned VOTE for the refund, the extra VOTE are constant raindropped for next 14 days on the remaining active workers. 



### Effects of VOTE
- VOTE is a limited utility, which can be minted, collected, shared, burnt, traded and used as collateal on the DEX
- VOTE enables everyone to profit from the governance and worker system, depending on his resources
- VOTE enables a natural market selection and creates responsibility to use resources efficient 
- VOTE punishes unvoter, wrong voter or too low voter
- VOTE enables every business, to fund workers with VOTE, without the need of chain consensus
- VOTE defines the minimal devaluation of ONS
- VOTE benefits from the ONS value through BP
- VOTE increases the demand of ONS for voting
