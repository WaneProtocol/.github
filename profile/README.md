# Wane

A shared, evolving immune system for AI agents, on-chain.

AI agents keep meeting the same attack for the first time. Nothing one agent learns is shared, so a single drainer can empty a thousand wallets in a row. Wane turns the network into an immune system: the first agent hit by a threat records it on-chain as an antibody that every agent after it already carries. The antibody follows the threat by its code and behavior as it mutates, so the shared memory keeps pace with the attack and the network gets harder to drain the more it is attacked.

Reading the registry is a free on-chain view, so reading is immunity. Publishing a threat stakes $WANE and can be challenged, so the shared memory stays honest.

## Repositories

- [wane-base](https://github.com/WaneProtocol/wane-base) : EVM engine. Antibody registry, policy firewall, EIP-7702 delegate, and the $WANE token. Live on Base.
- [wane-solana](https://github.com/WaneProtocol/wane-solana) : Solana engine. Antibody registry plus a non-custodial screening session vault.
- [wane-vault](https://github.com/WaneProtocol/wane-vault) : Non-custodial screening smart wallet. Funds stay in-contract and every send is checked before value moves.
- [wane-sdk](https://github.com/WaneProtocol/wane-sdk) : Unified TypeScript client for Base and Solana. Read the registry, report threats, drive a session wallet.
- [wane-agents](https://github.com/WaneProtocol/wane-agents) : Framework integrations. An elizaOS plugin and a Coinbase AgentKit action provider that screen before signing and publish threats back.

## How it works

1. An agent gets drained by a poisoned tool or a fresh drainer.
2. The threat is minted as an on-chain antibody, staked with $WANE, keyed by address, contract codehash, call pattern, or semantic marker.
3. Every other agent reads check() for free before it signs, so the next attempt reverts before value moves.
4. A redeploy does not dodge it: the markers match the threat as it mutates.
5. False records get challenged and the publisher slashed, so the shared memory stays honest.

## Links

- Website: https://wane.network
- X: https://x.com/wanedotnetwork
