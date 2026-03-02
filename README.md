# Siren Protocol Reentrancy Exploit — PoC

> **Educational Purpose Only** — This PoC is created for security research and education
> purposes only. It runs against a fork, not mainnet.

## Quick Start

```bash
git clone https://github.com/NomosLabs-Security/poc-siren-protocol-2021
cd poc-siren-protocol-2021
forge install foundry-rs/forge-std --no-git
forge test -vvvv
```

## Details

- **Exploit Date:** 2021-09-03
- **Fork Block:** #18681881
- **Expected Output:** Reentrancy via AMM pool withdraw callback to drain funds
- **Full Analysis:** [NomosLabs Security Intelligence Archive](https://nomoslabs.io/archive/siren-protocol-2021)

## Description

Siren Protocol's options AMM was exploited via a classic reentrancy attack.
The withdrawCapital() function transferred tokens before updating internal
accounting, allowing repeated calls to drain the pool.

## License

MIT — For educational use only.
