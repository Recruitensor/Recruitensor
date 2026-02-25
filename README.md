# Recruitensor - The Intelligent Talent Layer for Bittensor

Recruitensor is a Bittensor subnet that decentralises and incentivises talent acquisition for the Bittensor ecosystem. Despite over 128 active subnets, network growth is bottlenecked by a shortage of skilled miners and builders. There is no dedicated recruiting infrastructure. Onboarding relies on hackathons, word of mouth, and manual outreach. Recruitensor solves this by turning recruitment into a verifiable, on-chain commodity.

## Emission and Reward Logic

- For miners, 2 separate reward pools: onboarding incentives and retention incentives
- Onboarding incentives would be if the new miner performs productive work for a subnet in the first 7 to 14 days
- Retention incentives would be if the miner continues to provide productive work past 30+ days. This is an escrow-like pool that unlocks for miners if the prospect showcases long-term value on the network
- Miners can earn short-term and long-term rewards based on the recruits they onboard, and they need to hold a certain amount of alpha tokens to claim these rewards

Emission Split Breakdown:

- 21% Short-Term Wins (Miners 75%, Recruit 25%): If a recruit performs productive work in the first 7–14 days, the miner and recruit are paid.
- 20% Long-Term Retention (Miners 80%, Recruit 20%): This is the "Escrow" pool. If the recruit stays 30+ days, the big rewards unlock.
- 41% Validators for real-time scoring.
- 13% Subnet Owner.
- 5% Treasury: Set aside exclusively for funding future hackathons and "Recruitensor" workshops.

### Incentive and Mechanism Design

- Miners earn the subnet's alpha token upon validation of a recruit's contributions, with rewards scaled by the recruit's impact (e.g., 1 Alpha token base + bonuses for recruits earning >5 TAO in 30 days).
- Recruitensor will create bounties for each project. Bitcast charges a 10 TAO fee per subnet brief. This will be the same process with Recruitensor- 10 TAO per brief. 5 TAO up front and 5 TAO after 30-day retention of miners

## Incentive Alignment for Miners and Validators

- Miners aligned via performance-based rewards, staking the alpha token as collateral for each recruitment claim, earning yields on verified and retained recruits
- Validators stake the alpha token to participate in scoring, and accurate validations boost emissions
- Discrepancies lead to slashing collateral

Mechanisms to Discourage Low-Quality or Adversarial Behaviour

- Submissions require on-chain proofs
- Anti-Spam / Proof of Effort: Frictionless participation usually invites bots. To keep the leaderboard honest, Proof of Effort metrics are implemented.
- Focus on Conversion: "Performing outreach is good, but conversion into actual referrals is my main target. I pay for results, not just noise."
- If someone submits unverified claims, their collateral (Alpha tokens) will be slashed to keep the network clean.
- AI is also used to filter out low-quality spam in the recruitment packages.
- Time-locked rewards to prevent pump and dump
- A.I. to reduce spam

How This Design Qualifies as a Genuine “Proof of Intelligence” or “Proof of Effort”

- Proof of Effort (The Narrative): Instead of complex JSON hashes, the design centers on "Recruitment Packages"—verifiable digital breadcrumbs that show you brought someone into the fold.
- Proof of effort where miners conduct real-world efforts to educate and perform outreach to perform verifiable digital commodities (recruitment packages)
- Performing outreach is good, but converting it into actual referrals should be the main target, not the outreach itself; the payment is based on conversions, not effort.
- Commoditises human capital as a foundational input for AI subnets
- Effort proven through objective metrics like recruit retention and contributions

High-Level Algorithm Describing Task Assignment, Submission, Validation, Scoring, and Reward Allocation:

- Task assignment: Validators broadcast open recruitment bounties (e.g., "Recruit AI devs for Subnet 1") via the subnet's chain.
- Submission: Miners submit recruitment packages (recruit wallet, referral proof, initial contribution hash) with staked alpha tokens.
- Upon confirmation of the participation of the referral in the subnet he/she was referred to, the recruiter would get their reward.
- Validation: Validators query on-chain data/APIs (e.g., Bittensor explorer for emissions, GitHub for commits) to verify over a certain time horizon
- Scoring: The scoring is tuned to prioritize retention. Use the weighted formula:



  Score = 0.4 × (Retention Days / 30) + 0.3 × (Recruit TAO Earned) + 0.3 × (Contribution Depth)

Benchmarks for Miner Scoring

Miners are scored on a hybrid benchmark: skills/experience (resume validation via ZK/GitHub) for entry + recruit performance (TAO earned/retention) for rewards.

- Compute Subnets Benchmark (e.g., inference, agent swarms): Focused on output provided — uptime (95%+) via heartbeat, emissions earned, and speed/accuracy (measured via Bittensor API). Synthetic tests (random tasks via RAG) prevent overfitting.
- Non-Compute Subnets Benchmark (e.g., code-gen, data): Skills shown via GitHub (commits/PRs) + quiz (dynamic, subnet-specific via RAG) + output (merged PRs/commits). Resume weight fades after 90 days, shifting to pure contributions.

## Miner Design

- Virtual Miner Model: We want to eliminate the "terminal-only" barrier. In the revised design, we move toward a Virtual Miner model. You don't need to be a Linux wizard to help us grow.
- Wallet-Entry Leaderboard: As soon as you provide your wallet address, you are automatically enrolled in the active "Recruiter Leaderboard."
- Miner Tasks: Miners act as recruiters, identifying and onboarding devs, contributors, and more across these subnets through channels like X, Discord, LinkedIn, or hackathons.
- Tasks include: creating referral links/bounties, providing onboarding guides (e.g., key registration tutorials), and submitting proof packages for validation. They monitor recruits' progress to ensure contributions.
- The Workflow:

- Drop Wallet: You enter the ecosystem via a simple interface.
- Pick a Bounty: You see a list of subnets; some need coders, others need data providers or testers, etc.
- Refer & Earn: You use your referral codes or guides to onboard others.
- Automatic Tracking: My validators use on-chain oracles to see if your "Recruit" is actually producing work.

Expected Input → Output Format:

- Input: Bounty details from validators (e.g., "Target: Code-gen devs; Reward: 5 Alpha tokens").
- Output: hashed for immutability and submitted on-chain

Performance dimensions:

- Quality: Recruit retention rate (e.g., 90% active after 30 days) and contribution depth (e.g., TAO earned or commits).
- Speed: Time from recruitment to first contribution (target <7 days).
- Accuracy:Skill match to bounty (e.g., specific coding language, GPU/compute requirements) with a focus on matching the target subnet's prerequisites. This is measured via automated parsing and, most critically, is verified by the recruit's successful emission receipt on the target subnet.

### Miner Reputation Tiers

Recruitsor uses a four-tier reputation system to progressively reward miners who deliver high-quality, long-term recruits. Tier status is determined by two on-chain inputs that must both be satisfied: Alpha token holdings and a rolling 30-day Reputation Score. Advancing through tiers unlocks higher-value bounties, reduced staking collateral, and increased emission yield — creating a compounding incentive to prioritise recruit quality over raw volume.

## Tier Benefit Matrix

|     |     |     |     |     |
| --- | --- | --- | --- | --- |
| Tier | Alpha Held | Bounty Access | Collateral Reduction | Emission Yield Boost |
| Novice | 0 – 499 | Standard bounties | Standard (50% off first 30 days) | Base rate |
| Veteran | 500 – 1,999 | Standard + mid-value bounties | 10% reduction | +5% on verified recruits |
| Elite | 2,000 – 4,999 | All bounties incl. high-value briefs | 25% reduction | +12% on verified recruits |
| Legendary | 5,000+ | All + exclusive enterprise briefs (priority) | 40% reduction | +20% + compounding retention bonus |

## How Tiers Are Earned

Both criteria must be met simultaneously. Status is recalculated each epoch (~7 days). Downward movement only triggers after two consecutive epochs below the threshold.

1\. Alpha Token Holdings

Verified on-chain in real time. Flash-staking is mitigated by averaging snapshots across multiple points within each epoch.

2\. Reputation Score

A normalised 0.00–1.00 score derived from:

Score = 0.4 × (Retention Days / 30) + 0.3 × (Recruit TAO Earned) + 0.3 × (Contribution Depth)

|     |     |     |     |
| --- | --- | --- | --- |
| Tier | Recruits Retained (30+ days) | Recruit TAO Earned (cumulative) | Min. Reputation Score |
| Novice | 0 – 4 | 0 – 10 TAO | < 0.30 |
| Veteran | 5 – 14 | 10 – 50 TAO | ≥ 0.30 |
| Elite | 15 – 29 | 50 – 150 TAO | ≥ 0.55 |
| Legendary | 30+ | 150+ TAO | ≥ 0.75 |

## Anti-Gaming Safeguards

- Slashing applies equally at all tiers regardless of reputation status.
- Score decay: the 30-day rolling window means that inactivity can drop a miner's score within a single epoch.
- Flash-staking prevention: Alpha holdings are snapshot-averaged across each epoch, not point-in-time.
- A two-epoch grace window protects against short-term volatility but not against sustained underperformance.

## Integration with Emission Logic

Yield multipliers at Veteran, Elite, and Legendary tiers are applied within the existing miner-allocated emission pools (21% Short-Term Wins, 20% Long-Term Retention). They redistribute competitive share based on tier-adjusted scoring weights — total emission supply remains unchanged.

### AI Agent Recruitment

Recruiters can build AI agents as miners on Recruitensor to automate recruitment, especially on platforms like Moltbook (a social network for AI agents with 1.5M+ registered agents and 12M+ posts). The AI agent recruiter acts as a "miner" in Talent Tensolr, recruiting other AI agents to mine Bittensor subnets and earning alpha token rewards.

- Building the AI Agent Recruiter: Use OpenClaw (primary framework for Moltbook agents, with 100,000+ installations) or lighter alternatives like ZeroClaw/PicoClaw (lower RAM usage for efficient deployment). The recruiter agent uses function calling to deploy child agents via Chutes (Bittensor's serverless platform).
- Recruiting on Moltbook: The recruiter agent posts in submolts (e.g., m/technical, m/security, m/philosophy) with bounties like "Deploy to Bittensor Subnet 19 for inference – earn TAO + alpha tokens." Use scheduled posts (event-based or random) to seed discussions, respond to trending topics (e.g., AI earning opportunities), and create m/bittensor-mining. Virality: Hire other agents for tasks (scheduled bounties) and share skills. Measure: 1,000+ posts in 30 days via API.
- Developing Skills for Recruits: Recruitensor protocol creates skills via RAG analysis of CrunchDAO rankings (subnet-mining.crunchdao.com for benchmarks/performance), SubnetAlpha.ai (subnet details/incentives), and examples from Ridges/Affine (autonomous agent submissions). These skills (e.g., hotkey registration, mining loop, uptime optimization) are provided to recruiters to give to recruits, enabling agents to become legitimate miners. Skills are verifiable: validators check deployment hashes + emissions.
- Agent Verification: Validators verify agents via the Chutes deployment hash (proving uniqueness) and emissions (proving productive mining). The recruiter agent monitors child agents via the Bittensor API and claims rewards in Recruitensor upon success.
- Chutes Integration: AI agents are hosted and verified via Chutes (Bittensor's official agent deployment platform). Miners deploy agents using Chutes in minutes; validators confirm via Chutes hash + emissions.

## Validation design

- Validators run nodes to fetch and score packages using on-chain oracles (e.g., Bittensor API for key activity, GitHub API for proofs).
- Methodology: Automated checks for verifiability (e.g., signature validation) + quantitative scoring (as above)
- Validators could provide miners with specific skills and expertise to look for each active subnet on Bittensor, e.g., Gittensor for open-source/repositories/pull requests; Autoppia/Ridges/Sundaebar for A.I. Agent skills, etc. Could be a complete list of skills related to each subnet that miners can easily look for either inside or outside of their respective networks
- Materials will be analysed and organised via RAG with each subnet incentive mechanism, and step by step mining process will be explained to easily onboard viable and able recruits

Miners are responsible for recruiting individuals (or AI agents) who meet the specific prerequisites of the target subnet. Since unverified third-party platforms (like LinkedIn) are unreliable, skill validation will be primarily conducted through on-chain proofs:

- Primary Check (The Gold Standard): Validators confirm the recruit is earning emissions on the target subnet. Receiving emissions serves as definitive proof of productive work and meeting the subnet's core operational requirements (e.g., having the required compute resources, running the correct code).
- Secondary/Initial Filter: For subnets that require open-source experience (e.g., Gittensor), validators will leverage on-chain oracles (e.g., GitHub API) to evaluate verifiable metrics like GitHub commit history and account age to ensure a baseline level of genuine experience.

## Business Logic & Market Rationale

### The Problem the Subnet Aims to Solve and Why It Matters:

- Bittensor's growth is bottlenecked by developer scarcity
- Despite 128 subnets, attracting skilled miners/builders is manual and inefficient. This subnet solves talent acquisition by decentralising recruitment, turning it into a commoditised service
- It matters because faster dev onboarding accelerates AI innovation, increases network TVL (via more staking), and positions Bittensor as a talent flywheel in decentralised AI

### Competing Solutions, Both Within the Bittensor Ecosystem and Outside of It

- No Bittensor recruiting subnet
- No Bittensor recruiting service exists
- Growth relies on hackathons, Opentensor recruiting, word of mouth, mostly crypto participants
- Opentensor posted a miner listing on LinkedIn, Gitcoin and Gittensor incentivizes open source contributions but not mining other subnets

### Why This Use Case Is Well-Suited to a Bittensor Subnet:

- Recruitment fits Bittensor's marketplace model
- Miners produce competitive commodities (verified talents), validators ensure quality, and incentives align via emissions.
- Bootstrapping other subnets without central gatekeepers
- Decentralised verification prevents fraud, and tokenomics create sustainable economics absent in traditional platforms

### Whether There Is a Plausible Path to Long-Term Adoption and Sustainable Business

- Adoption via integration with existing subnets
- Sustainability from transaction fees (e.g., 1% on bounties to treasury) and potential fees to subnets (a la Bitcast 10 TAO charge per brief)
- Alpha token value appreciation as dev base grows

## Go-To-Market Strategy

### Initial Target Users & Use Cases

- Existing Bittensor miners and validators from active subnets who can act as recruiters (miners) by leveraging their networks.
- Could offer initial setup/registration rewards perhaps (5-10% of miner emissions) with an anti-spam quiz for real dedicated miners to claim initial emission and have them move forward to the next stage of rewards, potentially gamify the experience

### Pilot partners

- Utilise Opentensor/Unsupervised Capital/Tao Synergies/Stillcore Capital to integrate their grant programs to fund recruit bounties
- Onboard coding schools and get top students as potential miner recruits
- Hackathon organizers

### Anchor use cases

- Bootstrap low activity subnets to spark their productivity
- Utilise a Coinbase Earn type program, gamifying the learning process of mining on Bittensor. Set aside a small % of miner emissions towards people doing free mini courses like setting up a miner and getting alpha token rewards for it, setting the stage for next steps of actually mining
- Onboard devs from ecosystems like Fetch AI or Ocean Protocol, using their transferable skills to Bittensor

### Distribution & Growth Channels

- X, YouTube, Reddit, LinkedIn
- Hackathons, summits, partnerships,
- Could use part of the treasury towards paid ads, perhaps sell otc to investors and use funds towards initiatives
- Referral link system with codes to scale the onboarding and recruiting, and increase the chance of vitality of sign-ups and getting long-term contributions

## Incentives for Early Participation: Bootstrapping strategies for miners, validators, and users

The goal for miners is to lower the barrier to entry and offer immediate, tangible rewards to generate initial recruitment volume while mitigating spam.

- Initial Setup/Registration Reward (The Quick Win):

- Incentive: Offer a small percentage of miner emissions (e.g., 5-10% of the normal short-term reward) as an initial alpha token reward for completing the account setup.
- Anti-Spam Filter: Pair this reward with a mandatory, simple anti-spam quiz (as noted in the Initial Target Users) focused on understanding the Recruitensor mission and core mechanism (e.g., "What is the primary focus of the scoring formula?"). This ensures dedication from early participants.

- Gamified Onboarding (The Coinbase Earn Model):

- Incentive: Implement a "Recruit-Start" mini-course (aligned with the Anchor use cases idea). Set aside a small percentage of miner emissions to reward users for completing steps like:

1. Setting up a wallet address (earning enrollment in the Recruiter Leaderboard).
2. Creating their first referral link/bounty.
3. Submitting a mock or verified initial "Recruitment Package" proof.

- Goal: Guide them through the complete workflow and convert them from passive interest to active participation.

- Reduced Staking Collateral:

- Incentive: For the first 30 days, temporarily reduce the staked alpha token collateral required for a recruitment submission.
- Goal: Encourage high-volume submissions early on by reducing the financial risk, while maintaining the slashing threat for unverified/spam claims to protect the network.

2\. Validators (Scorers & Verifiers)

The goal for validators is to incentivize the crucial initial infrastructure and accurate, real-time scoring.

- Validator Boosted Emissions:

- Incentive: Offer an additional emission bonus on top of the standard 41% split for the first month or until a minimum number of submissions (e.g., 500 Recruitment Packages) have been validated.
- Goal: Reward early validators for bearing the initial load of setup and scoring, securing the network's core function.

- Priority Staking Pools:

- Incentive: Create a special pool for early validators, offering a slightly higher yield on their staked alpha tokens if their validation accuracy remains above a high threshold (e.g., 95%) during the bootstrap phase.
- Goal: Promote high-quality, non-adversarial validation from day one, which is key to establishing trust in the scoring mechanism.

3\. Recruits / Users (The Talent)

The goal for recruits is to provide an immediate reason to engage and a clear, path to long-term contribution.

- Guaranteed Short-Term Reward:

- Incentive: Aggressively market the 21% Short-Term Wins portion of the emission split. The message should be: "Contribute for 7-14 days and get a guaranteed short-term reward in RECR."
- Goal: Overcome the initial friction of joining a new subnet and quickly convert referred users into active contributors.

- Integration with Grant Programs:

- Incentive: Immediately utilize the planned Pilot partners (Opentensor, Unsupervised Capital, etc.) to integrate their grant programs.
- Strategy: Frame the first bounties as "Recruit-Grants," where a successful 7-day contribution not only earns the miner a reward but also puts the recruit on a fast track for a larger development grant from a partner.

- Transferable Skills Bounty:

- Incentive: Launch specific, high-reward bounties targeting devs from partner ecosystems like Fetch AI or Ocean Protocol.
- Goal: Leverage existing communities with transferable skills to quickly populate the subnet with high-quality talent, validating the use case.

## Governance

Recruitensor governance is tied directly to reputation tier and Alpha token holdings, ensuring that decision-making power reflects demonstrated commitment to the network — not just capital. All registered miners may vote; tier determines weight and scope of participation.

## Voting Rights by Tier

Voting weight scales with tier. A Legendary miner's vote carries 8x the weight of a Novice, reflecting their deeper on-chain track record and Alpha stake. The table below outlines what each tier can participate in.

|     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- |
| Tier | Vote Weight | Treasury Spend | Scoring Parameters | Bounty Policy | Upgrade Proposals |
| Novice | 1x | Vote on allocations | No | No | No |
| Veteran | 2x | Vote on allocations | No | Vote on policy | No |
| Elite | 4x | Vote + propose grants | Vote on weights | Vote on policy | Co-sign proposals |
| Legendary | 8x | Vote + propose grants | Vote on weights | Vote + propose changes | Submit + co-sign proposals |

## Treasury Spend

All miners, regardless of tier, can vote on how the 5% emissions and 30% fees Treasury allocation is deployed. Proposals are submitted by Elite and Legendary miners and require a simple majority to pass. Eligible spend categories are fixed at the protocol level and include hackathon funding, Recruitensor workshops, ecosystem partnerships, and paid growth initiatives. Treasury votes are held on a quarterly basis, or on an ad hoc basis when a proposal reaches a minimum co-sign threshold from Elite and Legendary miners.

## Scoring Parameter Adjustments

Elite and Legendary miners may vote on adjustments to the weighting of the Reputation Score formula — for example, shifting the balance between retention, TAO earned, and contribution depth. Changes require a two-thirds supermajority and a minimum 14-day voting window to prevent rapid manipulation of the scoring environment.

## Bounty Policy

Veteran and above may vote on bounty policy changes such as minimum reward thresholds, eligible subnet categories, and fee structures for subnet briefs. Legendary miners may also submit new policy proposals directly. Approved changes take effect at the start of the following epoch.

## Protocol Upgrades

Upgrade proposals — covering changes to emission splits, validation logic, or core subnet parameters — must be submitted by a Legendary miner and co-signed by at least two Elite miners before going to a network-wide vote. Approved upgrades require a two-thirds supermajority and a 21-day implementation delay to allow miners to adjust.

## Anti-Capture Safeguards

- Voting weight is capped per wallet to prevent any single actor from dominating outcomes, regardless of Alpha holdings.
- Tier status must be active and verified at the time of voting — holdings alone are insufficient if Reputation Score thresholds are not met.
- Treasury proposals are subject to a 7-day public comment period before a vote is called.
