# Onest Blockchain Whitepaper

## Targets
- Turning the blockchain worker system into a public funding system
- Segregating of `transaction utility` and `voting utility`
- Balance the reward and demand between transaction and vote utilitiy 
- Reward workers and loyal utility holders with VOTE
- Allow a natural market selection of VOTE users

## Utility Flow
![utility-flow](https://raw.githubusercontent.com/Onest-io/onest-whitepaper/master/utility-flow.png)

### ONS
Every BTS holder gets rewarded with the same amount of ONS on the new chain. ONS will no longer be used for the function "voting".

#### ONS-power
ONS-power is a new core function to lock ONS, which gets rewarded with new VOTE. Locked ONS can't be used as collateral or transferred to another account.

```
tau=150; // days
t=0; // days
t_active = 0; // days

ONS_power = amount_ONS * (1 - e^(-t/tau))

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

if (amount_ONS increased)
{
t = t * (amount_ONS_old/amount_ONS_new)
t_active = 0
}

if (amount_ONS decreased)
{
t = 0
30 day time lock until removed ONS can be vested
t_active = 0
}
```

### VOTE
Blockchain creates every day 10 Millionen VOTE, which rewards the worker system and ONS-power.

#### VOTE-power
The voter can define the emission type over time (constant or linear decrease) and the emission duration (max. 150d), when voting for a worker, BP or committee member. The longer the time period, the lower the VOTE-power. 

#### Effects of VOTE
- VOTE is a limited utility, which can be minted, collected, shared, burnt, traded and used as collateal on the DEX
- VOTE enables everyone to profit from the governance and worker system, depending on his resources
- VOTE enables a natural market selection and creates responsibility to use resources efficient 
- VOTE punishes unvoter, wrong voter or too low voter
- VOTE enables every business, to fund workers with VOTE, without the need of chain consensus
- VOTE defines the minimal devaluation of ONS
- VOTE benefits from the ONS value through BP
- VOTE increases the demand of ONS for voting
