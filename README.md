# Eduard Codrean

On-chain data engineer. I build pipelines on EVM chain data in Python and SQL, and I check what they produce against the chain itself before I trust a number.

A lot of my work so far has been about the errors that don't crash anything: an explorer API that answers HTTP 200 with an error inside, a page that stops at 1,000 rows, a missing price read as 0, a rate limit reported as missing data.

## Projects

**[onchain-tieout](https://github.com/Am0MuK/onchain-tieout)**: rebuilds a wallet's ETH and ERC-20 balances from Etherscan V2 history and checks them against JSON-RPC state at the same block, with a probable cause for every difference. On a public wallet (vitalik.eth) it produced 10,476 balance rows, 8,281 of them exact. Its first live run found bugs in its own code that the offline tests had missed: pages capped at 1,000 rows, a block too large to paginate, and rate-limit errors reported as data.

**[mev-scout](https://github.com/Am0MuK/mev-scout)**: read-only measurement of MEV on EVM chains. Aave V3 liquidations over 12 months on 12 chains, same-chain DEX arbitrage on Arbitrum, and cross-chain arbitrage between Arbitrum, Base and Optimism. The pass/fail rule for "should a newcomer build a bot in 2026?" was fixed before any data was collected. No niche passed.

**[lp-sim](https://github.com/Am0MuK/lp-sim)**: simulator for Uniswap V3 range strategies. It rebuilds per-tick liquidity from Mint and Burn events, and its fee accounting matched the pools' on-chain fee counters to within 0.3% on three stable pools, the largest with 62,484 swaps. 1,464 strategy runs on 8 stable pools, none passed the 15% target fixed in advance.

A private multi-chain pipeline (16+ chains, 20+ protocols, 1,700+ tests) runs a balance check against the chain after every run. I used it for my own German tax return.

## How I work

I write the specification and the test plan. AI coding agents write much of the first version. I review the code and check the results against real chain data, and I publish the verdict even when the answer is no.

## Stack

Python · SQL (PostgreSQL, SQLite) · Dune · Uniswap V3 math · Etherscan and Blockscout APIs · archive RPC · Docker · Grafana · Linux

## Writing

Articles on silent failures in DeFi data (LinkedIn, DEV.to, Paragraph).

## Contact

kontakt@defisteuer.de
