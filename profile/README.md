# Wane

A shared, evolving immune system for AI agents, on-chain.

AI agents keep meeting the same attack for the first time. Nothing one agent learns is shared, so a single drainer can empty a thousand wallets in a row. Wane turns the network into an immune system: the first agent hit by a threat records it on-chain as an antibody that every agent after it already carries. Antibodies are keyed by address, contract codehash, and call pattern, so a drainer that redeploys the same bytecode at a new address is still caught by its codehash. A genuinely new variant needs a fresh antibody, and staked corroboration lets the swarm relearn it fast. The more the network is attacked, the broader its shared memory gets.

Reading the registry is a free on-chain view, so reading is immunity. Anyone can report a suspect address for free, with no wallet, from the Scan page: a gatekeeper bot verifies each report against live threat feeds and on-chain behavior and only then mints it, staked, from the treasury. Agents and operators can also publish directly through the SDK, staking $WANE themselves. Either way every enforceable antibody is staked and challengeable, so reporting is open to everyone while the shared memory stays honest.

CA: HesbMP8FaoUvK8uKrtg6Pf4WCiQXgFS8oQJ3tjZpump

## Recently shipped

- **Solana engine live on mainnet-beta.** Registry `5Arj4z…1wJH` and screening vault `5YK7gM…rtTYh` are deployed and executable, governor-owned, with 500 antibodies in the registry.
- **One-RPC batch screening in the SDK.** `checkAddresses` / `assertAllSafe` screen every destination in a transaction in a single round trip instead of one call per address.
- **Solana registry went stake-free.** A governor bot verifies each report against live feeds and on-chain behavior, then mints the antibody from the treasury, so reporting stays free and open with no token step for the reporter.

Active development is on `wane-solana` and `wane-sdk`. Commits, roadmap, and open issues track what is in flight.

## Repositories

- [wane-base](https://github.com/WaneProtocol/wane-base) : EVM engine. Antibody registry, policy firewall, and EIP-7702 delegate. Live on Base.
- [wane-solana](https://github.com/WaneProtocol/wane-solana) : Solana engine. Antibody registry plus a non-custodial screening session vault.
- [wane-vault](https://github.com/WaneProtocol/wane-vault) : Non-custodial screening smart wallet. Funds stay in-contract and every send is checked before value moves.
- [wane-sdk](https://github.com/WaneProtocol/wane-sdk) : Unified TypeScript client for Base and Solana. Read the registry, report threats, drive a session wallet.
- [wane-agents](https://github.com/WaneProtocol/wane-agents) : Framework integrations. An elizaOS plugin and a Coinbase AgentKit action provider that screen before signing and publish threats back.

## How it works

1. An agent gets drained by a poisoned tool or a fresh drainer.
2. The threat is minted as an on-chain antibody, staked with $WANE, keyed by address, contract codehash, call pattern, or semantic marker.
3. Every other agent reads check() for free before it signs, so the next attempt reverts before value moves.
4. Redeploying the same bytecode does not dodge it: the codehash still matches. A genuinely new variant takes a fresh antibody, which staked corroboration hardens fast.
5. False records get challenged and the publisher slashed, so the shared memory stays honest.

## Links

- Website: https://wane.network
- X: https://x.com/wanedotnetwork
