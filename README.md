


# SolArbHunter

A high-performance Solana arbitrage bot designed for discovering and executing profitable trading opportunities across multiple decentralized exchanges (DEXs). Built with both off-chain and on-chain components to ensure accurate and reliable swaps.

---

## Project Layout

* **client/** – Off-chain arbitrage bot logic and execution.
* **program/** – On-chain swap program for handling complex multi-hop swaps.
* **pools/** – Metadata for DEX liquidity pools.
* **onchain-data/** – Historical and live analysis of arbitrage activity.
* **mainnet-fork/** – Fork mainnet state to simulate swap input/output estimates.

Each folder contains its own `README.md` explaining detailed functionality.

---

## Supported DEXs

* Serum
* Aldrin
* Saber
* Mercurial
* Orca

---

## Implementation Notes

* **Unit Testing with Mainnet Forking:** Rust unit tests simulate real swap outcomes to validate quoted amounts match actual results.
* **DEX Interfacing:** Many DEXs lack public SDKs, so interactions are reverse-engineered using the Jupiter Swap SDK as reference.
* **Arbitrage Search:** Uses a brute-force approach for speed and completeness, rather than negative-cycle detection.
* **Swap Input Strategy:** Multiple decreasing input amounts are sent (N, N/2, N/4…) to maximize the chance of capturing profitable opportunities.
* **On-chain Swap Program:** Ensures accurate handling of multi-hop swaps (e.g., A → B → C) where intermediate amounts may vary.

