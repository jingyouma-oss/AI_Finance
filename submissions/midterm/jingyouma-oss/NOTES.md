# Mid-term strategy notes

**Name:** Jingyou Ma

**GitHub:** jingyouma-oss

**Wallet:** PENDING - add the funded Base Sepolia wallet address before submission

## What my strategy does
My `risk-adjusted-yield` bot deploys idle tUSDC into either LendA or LendB. It scores each pool as `supply APR - 0.5% x utilization`, chooses the higher score, keeps 10% of wallet cash liquid, and caps each order at both 5,000 tUSDC and 5% of pool cash. Immediately before execution it scans again, then verifies that the wallet received lending shares after the transaction confirms.

## Why it should make money
Suppliers earn the pool's lending APR, but a high headline APR can coincide with high utilization and poor withdrawal liquidity. The utilization penalty favors a better balance of yield and liquidity rather than blindly chasing the largest APR. The reserve, liquidity cap, minimum score, minimum order, and five-minute cooldown reduce concentration, market-impact, and repeated-transaction risk.

## What would make it lose
The strategy can lose or become temporarily illiquid if a lending contract fails, borrowers default beyond the protocol's protection, utilization rises abruptly, or the pool's rate falls after deposit. RPC failure, gas shortages, stale reads, and transaction reverts can also prevent execution. Testnet tUSDC has no guaranteed real-world value, and the reported annual yield is an estimate rather than realized instant profit.

## Evidence
- Transaction hash: PENDING - run one funded live transaction and paste its Basescan URL
- Leaderboard screenshot: PENDING - capture the dashboard after the confirmed transaction
