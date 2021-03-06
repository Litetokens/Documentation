# Envoy

## Rules for Litetokens Envoy (LE) Application

Every account in the LITETOKENS network can apply and have the opportunity to become a LE. Every one can vote for LE candidates. The 27 candidates with the most votes will become LEs with the right to generate blocks. The votes are counted every 6 hours and the LEs will change accordingly.

To prevent malicious attack, there is a cost to become a LE candidate. When applying, 9999 XLT will be burned from the applicant's account. Once successful, you can join the LE election.

## LE election

You need LITETOKENS Power (TP) to vote and the amount of TP depends on your current frozen assets. TP is calculated in the following way: 1 TP for 1 frozen XLT.

Every account in the LITETOKENS network has the right to vote for your own LEs

After the release, you don't have any frozen assets and lose all TP accordingly. As a result, all votes become invalid. To prevent this from happening, you can refreeze to vote.

Note that the LITETOKENS network only records your most recent vote, which means that every new vote will negate all previous votes.

+ For example:

    freezebalance password 10,000,000 3 // 10XLT frozen and 10 unit of TP gained
    votewitness password witness1 4 witness2 6 // 4 votes for witness 1 and 6 votes for witness 2 at the same time
    votewitness password witness1 3 witness2 7 // 3 votes for witness 1 and 7 votes for witness 2 at the same time


The final result of the command is 3 votes for witness 1 and 7 votes for witness 2.

## Rewards

1. Rewards for LEs. Every 6 hours, the top 127 LE candidates with the most votes will be rewarded with 115,200 XLT. The reward will be given to each one according to the votes he/she receives. A total amount of 168,192,000 XLT will be given out every year.

2. Block generation rewards. New blocks are generated every 3 seconds in the LITETOKENS network and LEs will receive 32 XLT for every block generated. A total amount of 336,384,000 XLT will be given out.

+ After generating a block, the rewards will go directly into the LE's sub account. LEs cannot use them right away but they can look up. The rewards can be withdrawn every 24 hours, from the sub account directly to the LE's account.
+ The LITETOKENS Foundation will provide rewards for block generation and LEs before January 1, 2021. The LITETOKENS network will not issue additional XLT.

# Committee

### What is the committee?

The committee is used to modify Litetokens network dynamic parameters, such as block generation rewards, transaction fees, etc. The committee consists of the current 27 LEs. Each LE has the right to propose and to vote on proposals. When a proposal receives 18 votes or more, it is approved and its network parameters will be modified in the next maintenance period.

### Create proposal

Only the LE corresponding accounts have the right to propose and other accounts do not. The network dynamic parameters allowed to be modified and their numbers are as follows ( [min,max] ):

+ 0: MAINTENANCE_TIME_INTERVAL, [3 * 27* 1000 , 24 * 3600 * 1000] //Modify the maintenance interval, currently 6*3600 * 1000ms
+ 1: ACCOUNT_UPGRADE_COST, [0,100 000 000 000 000 000] //Modify the cost of upgrading to LE account, currently 9999 Sun
+ 2: CREATE_ACCOUNT_FEE, [0,100 000 000 000 000 000] // Modify the account creation fee, currently 100_000 Sun
+ 3: TRANSACTION_FEE, [0,100 000 000 000 000 000] // Modify the amount of XLT used to gain extra bandwidth, currently 10 Sun/byte
+ 4: ASSET_ISSUE_FEE, [0,100 000 000 000 000 000] // Modify asset issuance fee, currently 1024_000_000 Sun
+ 5: WITNESS_PAY_PER_BLOCK, [0,100 000 000 000 000 000] // Modify LE block generation reward, currently 32_000_000 Sun
+ 6: WITNESS_STANDBY_ALLOWANCE, [0,100 000 000 000 000 000] // Modify the rewards given to the top 127 LE candidates, 115_200_000_000 Sun
+ 7: CREATE_NEW_ACCOUNT_FEE_IN_SYSTEM_CONTRACT, []// Modify the cost of account creation, currently 0 Sun
+ 8: CREATE_NEW_ACCOUNT_BANDWIDTH_RATE, // Use proposals 7 and 8 together to modify the resources or XLT consumption of account creation.
+ 9: ALLOW_CREATION_OF_CONTRACTS, // used to open virtual machines (VMs)
+ 10: REMOVE_THE_POWER_OF_THE_GR // remove the initial GR votes
+ 11: ENERGY_FEE, [0,100 000 000 000 000 000] //sun
+ 12: EXCHANGE_CREATE_FEE, [0,100 000 000 000 000 000] //sun
+ 13: MAX_CPU_TIME_OF_ONE_TX, [0, 1000] //ms

+ API: `createproposal id0 value0 ... idN valueN
id0_N: Parameter number
value0_N: new parameter value `

Note: In the Litetokens network, 1 XLT = 1000_000 Sun.

### Vote on proposals

An proposal only supports votes that are in favor. Those who do not vote show their disagreement. The proposal is valid for 3 days after it is created. Afterwards, if the proposal does not receive enough votes, it becomes invalid. The favorable votes can be cancelled.

+ API: `deleteProposal proposalId
id: The proposal ID increases as time goes on after it is proposed ` is_or_not_add_approval: Approve or cancel approval </0>

### Cancel proposals

The proposer can cancel the proposal before it takes effect.

+ API: `deleteProposal proposalId
id: The proposal ID increases as time goes on after it is proposed `
