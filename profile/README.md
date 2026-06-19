# Wane

Shared on-chain immune memory and a non-custodial screening layer for AI agents.
When one agent gets drained, the threat is recorded once as an antibody that every
other agent reads before it signs. Threats wane.

## Repositories

- [wane](https://github.com/WaneProtocol/wane) : EVM engine. Antibody registry, policy firewall, EIP-7702 delegate, and the $WANE token. Live on Base.
- [wane-solana](https://github.com/WaneProtocol/wane-solana) : Solana engine. Antibody registry plus a non-custodial screening session vault.
- [wane-vault](https://github.com/WaneProtocol/wane-vault) : Non-custodial screening smart wallet. Funds stay in-contract and every send is checked before value moves.
- [wane-sdk](https://github.com/WaneProtocol/wane-sdk) : Unified TypeScript client for Base and Solana. Read the registry, report threats, drive a session wallet.

## How it works

1. An agent gets drained by a poisoned tool or a fresh drainer.
2. The threat is minted as an on-chain antibody, staked with $WANE.
3. Every other agent reads check() for free before signing, so the next attempt reverts before value moves.
4. False records get challenged and the publisher slashed, so the shared memory stays honest.

## Links

- Website: https://wane.network
- X: https://x.com/wanedotnetwork
