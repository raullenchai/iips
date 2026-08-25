```
IIP: <to be assigned>
Title: Ethereum-Canonical IOTX and the Evolution of the IoTeX Network
Author: ghclean (@ghclean)
Discussions-to: TBD
Status: Draft
Type: Informational
Created: 2026-08-24
```

## Simple Summary

This IIP proposes a long-term direction for IoTeX: establish IOTX on Ethereum as the single canonical monetary asset and evolve IoTeX into a decentralized service and security network for user-owned AI, devices, DePIN, and real-world applications. Operators would stake IOTX to provide useful, verifiable services across this network.

This is a directional proposal. It does not deploy a new token, initiate a token migration, shut down the IoTeX Layer 1, select a rollup architecture, or define final staking parameters. Those actions require separate Standards Track IIPs.

## Abstract

IOTX currently exists across a history of native and Ethereum-based representations, while its primary utility has been tied to gas, governance, staking, and block production on the sovereign IoTeX Layer 1. This architecture has supported the network to date, but it also fragments monetary settlement and closely couples the purpose of IOTX to the continued operation of a specific blockchain.

This IIP proposes a longer-term model with two distinct layers:

1. **Ethereum as the canonical monetary and staking settlement layer for IOTX.** A future migration would provide eligible native IOTX and legacy Ethereum ERC-20 IOTX with a one-to-one path into one canonical Ethereum asset, subject to a maximum economic supply of 10,000,000,000 IOTX.
2. **IoTeX as a decentralized utility network.** Operators would stake or bond IOTX to provide useful services such as device identity, data attestation, AI inference, compute, DePIN verification, and other forms of verifiable off-chain work.

The IoTeX Layer 1 may continue operating during this evolution. Whether it remains a sovereign L1, becomes an Ethereum-secured execution environment, or is supplemented by other execution environments is outside the scope of this IIP and must be decided separately.

## Motivation

### One canonical monetary asset

The historical coexistence of native IOTX and legacy ERC-20 IOTX creates ambiguity about which representation is the monetary source of truth. It also requires exchanges, custodians, wallets, and users to support different settlement rails for assets carrying the same name.

A single canonical IOTX on Ethereum would provide one monetary settlement layer and allow integrations to use established Ethereum token, custody, and settlement infrastructure.

### Separate the network mission from the blockchain

IoTeX's long-term differentiation can extend beyond general-purpose EVM blockspace. Device identity, trusted real-world data, DePIN verification, private or verifiable AI, compute coordination, and machine-to-machine services all require networks of operators that perform work and can be held economically accountable for that work.

Under this direction, the IoTeX Network is defined by the services it coordinates, not solely by the blockchain it operates.

### Give staking durable utility

Today, IOTX staking primarily supports delegate selection, governance, and L1 consensus. If the role of IoTeX evolves, staking should evolve with it.

IOTX staking can provide service-level cryptoeconomic security: operators bond IOTX, qualify to perform work, earn fees or incentives, and face penalties for objectively attributable failures. Community holders may support operators through delegation or pooled staking without being required to operate infrastructure themselves.

### Support a product-led network

Network services should respond to real product and developer demand. Applications should be able to purchase useful services without requiring every end user to understand or directly acquire IOTX. Payment abstraction may allow applications to pay in fiat, stablecoins, or other supported assets while the underlying protocol uses IOTX for operator bonding, settlement, incentives, or security.

### Economic flywheel

The long-term model should connect application usage to sustainable demand for network services and cryptoeconomic security:

```text
Application demand
        |
        v
IoTeX services
        |
        v
Operator revenue
        |
        v
IOTX bonding and staking
        |
        v
Cryptoeconomic security
        |
        v
More reliable services
        |
        v
More application demand
```

Future Standards Track IIPs should define how service revenue, operator bonding requirements, protocol reserves, and other mechanisms create sustainable economic demand for IOTX without requiring end users to interact directly with the token. This IIP does not prescribe token buybacks or any other specific value-accrual mechanism.

## Proposed Direction

### 1. Ethereum-canonical IOTX

IoTeX should work toward one canonical IOTX asset on Ethereum.

The canonical asset should become the recognized monetary representation of IOTX for settlement, staking, ecosystem accounting, and institutional integration. A future Standards Track IIP must determine whether the existing legacy ERC-20 contract can safely serve this role or whether a new contract is required.

The canonical contract design should favor simple and auditable supply controls, minimized privileged authority, transparent governance, and broad compatibility with Ethereum infrastructure.

### 2. Supply and migration principles

Any future implementation should preserve the following invariants:

- The maximum economic supply remains **10,000,000,000 IOTX**.
- Each eligible source IOTX receives no more than one canonical IOTX.
- Migration uses a **1:1 denomination** and does not redenominate holders.
- A migrated source claim must be irreversibly burned, retired, or accounted for against a supply-constrained reserve before its canonical counterpart becomes economically active.
- The migration process must prevent double claims across all eligible source representations.
- Supply, retirement, escrow, and migration accounting must be publicly auditable.

Eligible native IOTX and legitimate legacy Ethereum ERC-20 IOTX should receive migration paths defined by later IIPs.

**CIOTX is excluded.** CIOTX is deprecated under [IIP-56](iip-56.md) and does not create a claim on canonical IOTX under this proposal. This IIP neither reopens nor extends the CIOTX claims and wind-down process.

### 3. Preserve staking commitments

Moving the canonical asset must not automatically release existing staking commitments.

Where technically possible, an existing locked staking position should migrate into an economically equivalent locked position. Ownership, principal, and remaining lock duration should be preserved. A later Standards Track IIP must define the treatment of delegates, voting rights, accumulated rewards, auto-stake settings, contract-based staking, and exceptional cases.

This principle protects existing commitments while allowing the purpose of staking to evolve.

### 4. IoTeX utility network

The IoTeX Network should progressively support independently operated service networks secured by IOTX. Potential service categories include:

- device and machine identity;
- hardware and software attestation;
- real-world and DePIN event verification;
- sensor, machine, and user-authorized data services;
- AI inference, model routing, and inference verification;
- GPU, CPU, edge, and agent compute;
- automation and off-chain execution;
- proofs, indexing, monitoring, and other verification services; and
- infrastructure supporting IoTeX or third-party execution environments.

These categories describe a direction, not an authorization to create incentives for services without demonstrated demand. Each service network should specify the work performed, consumers of the service, payment model, operator requirements, measurable performance conditions, and security assumptions.

### 5. Operator and community staking

Future staking systems should distinguish between operator responsibility and community participation.

Operators may bond IOTX to become eligible for jobs, demonstrate economic commitment, and back defined service guarantees. Community holders may delegate or stake in support of operators and receive an appropriate share of eligible rewards without transferring ownership of their principal to those operators.

Slashing should apply only when faults are objective, attributable, and independently verifiable. Services that cannot define safe slashing conditions may use reputation, withheld payment, limited job eligibility, or other mechanisms instead.

Over time, operator economics should increasingly be supported by service fees and real network revenue. Temporary bootstrap incentives may be considered separately, but this IIP does not propose new issuance or perpetual inflation.

### 6. Chain-agnostic services

IoTeX utility services should not be restricted to a single execution environment. They may serve applications on IoTeX, Ethereum, Ethereum L2s, or other networks where demand exists.

This allows the IoTeX Network to grow as a service and security layer even if its execution architecture changes over time.

### 7. Execution remains a separate decision

This IIP does not prescribe the final architecture of the IoTeX blockchain.

The existing IoTeX L1 may continue to provide execution while the utility network develops. A future proposal may evaluate state-preserving migration to an Ethereum-secured execution environment, continued sovereign L1 operation, or a hybrid architecture. Such a proposal must independently address application state, chain history, addresses, gas, data availability, sequencing, proving, exits, governance, and operational continuity.

No L1 shutdown or L2 migration is authorized by this IIP.

## Conceptual Architecture

```text
Ethereum
  canonical IOTX + staking + monetary settlement
                         |
                         v
IoTeX Utility Network
  operators bonded by IOTX
  |- device identity and attestation
  |- DePIN and real-world verification
  |- AI inference and verification
  |- data, compute, and automation
  |- proofs and infrastructure services
                         |
                         +--> IoTeX L1 or future execution environment
                         +--> Ethereum and Ethereum L2s
                         +--> other networks
```

The blockchain is an execution environment used by the network. It is not, by itself, the full definition of the network.

## Rationale

### Why Ethereum?

Ethereum provides a widely integrated settlement environment for fungible tokens, custody, smart-contract staking, and institutional infrastructure. Making Ethereum the canonical monetary layer can reduce ambiguity around IOTX without requiring every IoTeX utility service to execute directly on Ethereum.

### Why a utility network?

Useful off-chain and real-world services require operators, service discovery, payments, monitoring, and economic accountability. IOTX can coordinate these functions and secure operator commitments even when the services are consumed across multiple blockchains or by applications that abstract blockchain interaction from users.

### Chainlink as a conceptual precedent

Chainlink demonstrates a useful separation between a token's settlement environment and the decentralized networks that use it. LINK is used for service payments and cryptoeconomic security, while node operators provide oracle and computation services across many networks. Chainlink staking allows node operators and community participants to back defined service performance with staked LINK.

IoTeX should not copy Chainlink's products or staking implementation directly. The relevant precedent is architectural: an Ethereum-based token can coordinate and secure a broader network of independently operated services. IoTeX can apply that pattern to devices, DePIN, real-world data, AI, compute, and verification.

### Why retain staking?

Staking should represent an economically meaningful commitment to correct service operation, governance, or both. Retaining staking also provides continuity for holders and delegates, but continuity alone is insufficient: each future staking use must identify what is being secured and how performance is measured.

## Relationship to Existing IIPs

### IIP-57

This proposal does **not** supersede [IIP-57](iip-57.md). IIP-57 proposes a ZK light-client bridge while preserving IoTeX as a sovereign L1. That work can improve Ethereum interoperability while the current L1 continues to operate.

This IIP addresses a broader and longer-term question: where IOTX should ultimately be canonical and what the IoTeX Network should exist to provide. If the community later proposes changing the L1 or bridge architecture, the relationship to IIP-57 must be specified in a separate Standards Track IIP.

### IIP-56

[IIP-56](iip-56.md) governs the deprecation of CIOTX following the ioTube incident. This proposal follows that deprecation and does not designate CIOTX as an eligible source asset for the future canonical IOTX migration.

## Alternatives Considered

### Keep native IOTX permanently canonical

This preserves the existing sovereign architecture and avoids a canonical-asset migration. It also preserves the long-term coupling between IOTX monetary settlement and operation of the IoTeX L1.

### Make Ethereum IOTX canonical while permanently retaining two sovereign systems

This may simplify asset integration but would require a permanent mechanism between Ethereum-canonical IOTX and a sovereign IoTeX chain representation. Such a mechanism could become critical monetary infrastructure and should not be adopted as a permanent design without a separate security analysis.

### Immediately migrate the L1 to an Ethereum L2

This would combine monetary and execution changes into one decision before state migration, application compatibility, staking, and operator economics are sufficiently specified. This IIP therefore separates the long-term direction from any execution migration.

## Backwards Compatibility

As an Informational IIP, this proposal makes no immediate protocol or contract change and therefore has no direct backwards-compatibility impact.

Future Standards Track IIPs implementing this direction will introduce significant compatibility considerations. They must provide long migration windows, explicit activation conditions, exchange and custodian coordination, application guidance, transparent supply accounting, and recovery procedures.

## Security Considerations

Future implementations must address at least:

- canonical token contract and administrative-key security;
- conservation of the 10 billion IOTX economic supply;
- source-token retirement and double-claim prevention;
- verification of native-chain migration events;
- migration of locked staking state;
- exchange and custodian migration integrity;
- governance and emergency powers;
- objective operator performance and slashing evidence; and
- progressive minimization of privileged trust.

This IIP does not select a migration proof system, bridge, committee, rollup, or staking contract.

## Follow-up Proposals

Implementation of this direction should be divided into independently reviewable Standards Track IIPs, including:

1. canonical IOTX contract and supply-accounting rules;
2. native and legacy ERC-20 migration mechanisms;
3. existing staking-position migration;
4. utility-network operator and staking architecture;
5. initial service-specific protocols and economics; and
6. any change to IoTeX L1 execution or settlement.

Each proposal should include concrete specifications, threat models, test cases, audits, activation criteria, and rollback or recovery procedures appropriate to its scope.

## References

- [IIP-56: Deprecation of CIOTX Across All Networks](iip-56.md)
- [IIP-57: Trustless Bridge: Replacing Keys with Proofs](iip-57.md)
- [Chainlink Economics](https://chain.link/economics)
- [Chainlink Staking](https://chain.link/economics/staking)
- [Chainlink Developer Documentation](https://docs.chain.link/)

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
