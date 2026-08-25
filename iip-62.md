```
IIP: 62
Title: Ethereum-Canonical IOTX and the Evolution of the IoTeX Network
Author: Raullen Chai (@raullenchai), Qevan Guo (@guo)
Discussions-to: TBD
Status: Draft
Type: Informational
Created: 2026-08-24
```

## Abstract

This IIP defines an architectural direction for IoTeX's long-term mission: build a global intelligence that belongs to everyone, is controlled by no one, and never stops learning. People, AI, devices, and machines can contribute questions, knowledge, data, models, compute, experiments, observations, and real-world capabilities while preserving individual sovereignty.

The proposal establishes two principles:

1. **Ethereum becomes the canonical home for IOTX.** Ethereum becomes the authoritative layer for IOTX supply, ownership, transfers, and, over time, staking and protocol governance.
2. **IoTeX becomes a foundation for open service and intelligence networks.** IOTX staking provides a common economic foundation for participation, commitment, delegation, and accountability across independently operated networks.

IOTX currently exists across native and Ethereum-based representations, fragmenting ownership, liquidity, custody, and integration while coupling its utility to one blockchain. Eligible IOTX will receive a one-to-one path into canonical Ethereum IOTX. The **IOTX** ticker, 18 decimals, holder denomination, and maximum economic supply of **10,000,000,000 IOTX** remain unchanged.

This IIP establishes strategic direction only. It does not deploy a contract, migrate a balance, change an existing staking position, or shut down the IoTeX Layer 1. Those actions require separate Standards Track IIPs. [IIP-63](iip-63.md) is the first implementation proposal and specifies the canonical ERC-20 contract and liquid-IOTX migration framework.

## What This IIP Decides

Approval establishes the following architectural decisions:

- Ethereum will become the canonical home for IOTX supply, ownership, transfers, staking, and protocol-level governance rights.
- IOTX will retain the ticker `IOTX`, 18 decimals, and one-to-one denomination.
- The maximum economic supply will remain 10,000,000,000 IOTX, and historical burns will remain retired.
- Each eligible source IOTX may create no more than one canonical IOTX.
- An eligible source claim must be verifiably retired before or as its canonical counterpart becomes economically active.
- Migration must prevent duplicate economic claims across representations and remain publicly auditable.
- The permanent canonical token will be separated from temporary migration contracts and authority.
- The IoTeX Layer 1 will continue operating during a staged transition.
- Existing staking commitments and protocol governance rights will be preserved during migration.
- IOTX staking will become the common participation and commitment layer from which service and intelligence networks can emerge.

## What This IIP Does Not Decide

This IIP does not:

- deploy or activate the canonical ERC-20 contract;
- establish migration dates or move any user or institutional balance;
- select the final migration proof system or staking contract;
- change an existing staking lock, delegation, reward, or governance right;
- require immediate shutdown of the IoTeX Layer 1;
- define the final execution architecture of the IoTeX Network;
- authorize issuance beyond existing economic entitlement; or
- establish operator, revenue, penalty, or slashing rules for a future network.

Each implementation decision requires a Standards Track IIP with its own specification, security analysis, testing, activation plan, and governance approval.

## Motivation

### Establish one canonical IOTX and deeper liquidity

Native IOTX and legacy ERC-20 IOTX create ambiguity about the authoritative record of supply and ownership while dividing market-making inventory, exchange access, on-chain liquidity, collateral utility, custody, and institutional support across separate rails.

One canonical IOTX on Ethereum provides a single record of supply, ownership, transfers, and staking. It also allows exchanges, custodians, liquidity providers, DeFi applications, and users to converge on one asset and established Ethereum infrastructure.

### Use shared infrastructure where IoTeX does not need to differentiate

Operating an independent asset and staking layer requires IoTeX to maintain its own economic security, custody and exchange integrations, wallets, interoperability, and developer and security tooling. Ethereum already provides mature shared infrastructure across these areas, together with deep liquidity, stablecoins, DeFi, and institutional connectivity.

IoTeX should own the layers where it can create differentiated value and rely on shared infrastructure where differentiation is limited.

### Separate the IoTeX mission from a specific blockchain

IoTeX's differentiation extends beyond general-purpose EVM blockspace. Device identity, trusted real-world data, DePIN verification, AI, compute, and machine-to-machine services require networks of operators that provide useful capabilities and can be held accountable for their commitments.

The IoTeX Network should therefore be defined by the service and intelligence networks it enables, not solely by the blockchain it operates. Blockchain execution is an implementation substrate for the mission, not the mission itself.

### Enable new networks through staking

Today, IOTX staking primarily supports delegate selection, governance, and L1 consensus. Under this direction, it becomes the persistent participation and commitment layer for new service and intelligence networks.

Staking can express operator eligibility, capacity, commitment, delegation, and accountability. Networks with objectively verifiable failures can also place bonded IOTX at risk. Operators can earn service revenue, while community holders can support them through delegation or pooled staking without operating infrastructure themselves.

### Economic flywheel

The long-term model connects application usage to sustainable demand for networks and IOTX staking:

```text
Application demand
        |
        v
Service and intelligence networks
        |
        v
Operator revenue and capacity
        |
        v
Required IOTX bonding and staking
        |
        v
Operator commitment and accountability
        |
        v
More reliable networks
        |
        v
More application demand
```

As the amount, value, or risk of work assigned to an operator grows, the IOTX that operator must acquire or attract through delegation and commit must grow with it. Each specialized network must define operator eligibility, stake-to-capacity or stake-to-risk requirements, delegation, revenue distribution, and penalties. Activity without a credible requirement for bonded IOTX should not be presented as contributing to this flywheel.

## Proposed Direction

### Ethereum-canonical IOTX

IoTeX will establish a new canonical ERC-20 IOTX on Ethereum while retaining the **IOTX** ticker and 18 decimals. [IIP-63](iip-63.md) specifies the new contract and initial liquid-migration framework.

The canonical contract should favor simple and auditable supply controls, minimal privileged authority, transparent governance, and broad compatibility with Ethereum infrastructure.

The permanent canonical token and temporary migration system must be separated. The token contract should remain minimal and minimally privileged, while migration-specific verification, accounting, and temporary issuance authority reside in dedicated contracts that can be permanently disabled after all approved migration obligations are complete.

### Economic invariants

All implementation proposals must preserve the following invariants.

#### Maximum supply

The maximum economic supply remains **10,000,000,000 IOTX**. Migration does not create an allocation or revive historically burned IOTX.

#### One-to-one denomination

Each eligible source unit may receive no more than:

```text
1 source IOTX -> 1 canonical IOTX
```

There is no redenomination.

#### No duplicate claims

A migrated source claim must be irreversibly burned, retired, or accounted for through a supply-constrained, verifiable, non-custodial smart-contract escrow before its canonical counterpart becomes economically active. No source unit may create more than one economically active canonical claim.

#### Public accounting

Supply, retirement, escrow, and migration accounting must be publicly auditable. At minimum, the community must be able to verify eligible source supply, historical retirements, migrated and retired source supply, canonical issuance by source, remaining migration entitlement, locked staking entitlement, and total canonical supply.

Eligible native IOTX and legitimate legacy Ethereum ERC-20 IOTX must receive migration paths defined by Standards Track IIPs. CIOTX remains governed by IIP-56 and does not create an independent migration entitlement.

### A staged transition

Canonicalization occurs in independently reviewable phases.

#### Phase A — Canonical token and liquid migration

[IIP-63](iip-63.md) deploys the canonical Ethereum ERC-20 contract and defines one-to-one migration for eligible liquid legacy ERC-20 and native IOTX, including exchange and custodian procedures.

Liquid migration may begin before existing staking positions migrate, but deployment of the token does not by itself complete the transition established by this IIP.

#### Phase B — Existing staking and governance commitments

Moving IOTX to Ethereum must not automatically release an existing staking commitment. One old IOTX must become one canonical IOTX whether it is liquid or staked, and a locked position must remain locked for its remaining duration.

```text
Before migration                     After migration
on IoTeX L1                          on Ethereum

1,000,000 native IOTX                1,000,000 canonical IOTX
staked                               staked
locked until date X       1:1        locked until date X
        |----------------------------->|
```

Migration must preserve ownership, principal, remaining lock duration, and economically material staking rights. Ethereum-canonical IOTX carries governance rights over the IoTeX protocol, with canonical staking positions serving as the basis for governance participation.

A separate Standards Track IIP must define delegate representation, voting mechanics, accumulated rewards, auto-stake settings, contract-based staking, and exceptional cases. Until a position migrates, its staking and governance authority remains on the existing IoTeX system. Full canonical completion requires an approved and activated path for these positions.

#### Phase C — Service and intelligence networks

The preserved staking base becomes a common economic foundation from which specialized service and intelligence networks can emerge as real demand appears.

#### Phase D — Future execution architecture

Any material change to the role, execution model, or lifecycle of the IoTeX Layer 1 requires separate governance approval. Ethereum-canonical IOTX does not by itself shut down the L1.

## IOTX Staking Enables Service and Intelligence Networks

The IoTeX Network is an open environment in which independently operated service and intelligence networks can emerge. Canonical IOTX staking provides a common economic foundation for participation, commitment, delegation, and accountability across these networks.

Potential networks include:

- **AI inference networks:** discover, route, and execute inference using appropriate models and compute.
- **AI training networks:** support fine-tuning, specialization, continual learning, distributed training, and model improvement.
- **Compute networks:** discover and allocate GPU, CPU, edge, agent, or specialized compute.
- **Data networks:** authorize, license, provide, and validate datasets and real-world observations.
- **Verification networks:** evaluate inference, computation, data, claims, experiments, and agent execution.
- **Research and discovery networks:** run persistent loops from goals and hypotheses through experimentation, evaluation, learning, and revision.
- **Physical intelligence networks:** connect sensors, devices, machines, vehicles, robots, and wearables to intelligence that can observe and act.
- **Identity and attestation networks:** establish identity, provenance, trusted state, and accountable participation.

Each network should emerge in response to demonstrated demand and specify its work, users, revenue model, operator requirements, performance conditions, and security assumptions. IoTeX should not create artificial services merely to manufacture staking utility.

The staking architecture should distinguish operator responsibility from community participation. Operators bond IOTX to qualify for work and back defined commitments. Community holders may support operators through staking or delegation without transferring ownership of their principal.

Existing delegates will have a path to operate one or more specialized networks, while community holders can continue staking toward the operators and networks they support.

> **The continuity principle is: preserve the staking base first, then use it to enable useful new service and intelligence networks as demand appears.**

Slashing applies only when faults are objective, attributable, and independently verifiable. Other networks may use reputation, withheld payment, limited job eligibility, or similar accountability mechanisms. Operator economics should be supported by service fees and real network revenue.

These networks can serve applications across IoTeX, Ethereum, Ethereum L2s, other networks, and off-chain systems.

## Long-Term Vision

> **Build a global intelligence that belongs to everyone, is controlled by no one, and never stops learning.**

This vision is not one giant AI built by one company, and it is not limited to building another conversational assistant. Global intelligence does not imply a single global model. It can emerge from independently owned models, agents, people, machines, datasets, and specialized networks learning and working together.

Anyone should be able to contribute a question, an idea, knowledge, data, a model, compute, an experiment, a tool, an observation, feedback, or physical-world capability. Humans, AI, and machines should be able to explore together: trying things, observing what happens, learning from the results, and continuously asking better questions.

The objective is an intelligence that becomes not only more knowledgeable, but better at learning itself. When it encounters something it does not know, it should become increasingly capable of determining what information is missing, where that information may exist, which resources can help, what experiment should be performed, how the result can be verified, what was learned, and what should be tried next.

```text
Ask
 |
 v
Explore
 |
 v
Form hypotheses
 |
 v
Find resources
 |
 v
Act and experiment
 |
 v
Observe
 |
 v
Verify
 |
 v
Learn and improve
 |
 v
Ask better questions
 |
 +------------------------> repeat
```

Over time, this can move intelligence beyond answering questions and toward autonomous research, discovery, long-running experimentation, learning from real-world feedback, and collaboration among people and increasingly capable machines.

The world's intelligence should not belong to one machine, one company, or one country. People should retain sovereignty over their own data, memory, identity, models, agents, devices, and permissions while still being able to contribute to and benefit from a much larger collective intelligence.

> **Collectively built. Individually sovereign. Continuously improving.**

### Continuity with the IoTeX mission

IoTeX has spent years working at the boundary between digital systems and the real world: devices, machine identity, real-world data, DePIN, verification, physical infrastructure, and trusted computation. As AI becomes capable of reasoning and acting, these previously separate pieces can become parts of a continuously learning intelligence system.

```text
Models              -> reasoning
Data                -> knowledge and memory
Sensors             -> senses
Robots and machines -> action
Compute             -> capacity
Humans              -> goals, creativity, and judgment
Verification        -> reliable feedback and learning
```

Devices are no longer merely data sources. Machines can observe, AI can reason, robots can act, and humans can provide goals, knowledge, creativity, and judgment. The long-term opportunity is to bring these capabilities together without requiring participants to surrender control of themselves or their information to a central intelligence provider.

### The intelligence loop

IoTeX enables the capabilities through which intelligence can discover resources, perform work, observe results, verify outcomes, learn, and improve:

```text
Discover resources
models / data / compute
        |
        v
Act and experiment
inference / research / physical systems
        |
        v
Observe
data / sensors / real-world feedback
        |
        v
Verify
verification / identity / attestation
        |
        v
Learn and improve
training / research / model improvement
        |
        +----------------------> discover again
```

Specialized networks provide capabilities at different stages of this loop. Data and compute networks help find resources; inference and physical intelligence networks act; sensors and data networks observe; verification and attestation networks validate outcomes; training networks improve models; and research networks can orchestrate the full cycle. Together, they allow intelligence to learn from both digital systems and the real world.

## Why Ethereum?

Ethereum provides a stronger shared home for IOTX across four dimensions:

- **Economic security:** assets and contracts inherit Ethereum's mature security rather than requiring IoTeX to finance and defend an independent asset and staking layer.
- **Ecosystem:** canonical IOTX gains direct access to established custody, wallets, smart contracts, DeFi, stablecoins, interoperability, and developer and security tooling.
- **Liquidity:** IOTX connects more directly to on-chain markets, collateral systems, market makers, institutional custody, and liquidity across Ethereum L2s.
- **Integration:** exchanges, custodians, wallets, and institutions can reuse Ethereum infrastructure instead of maintaining a separate native-chain integration.

Moving only the token contract while leaving staking dependent on a separate sovereign chain would not fully resolve fragmentation. It would require a permanent mechanism between Ethereum-canonical IOTX and the chain where staking records remain authoritative. That mechanism would become critical IOTX infrastructure: a compromise, accounting failure, or prolonged outage could fragment backing, disrupt staking, or create competing claims on the same economic IOTX.

Ethereum therefore becomes the canonical home for both IOTX and staking. This is specialization: Ethereum provides secure, liquid, broadly integrated asset infrastructure, while IoTeX focuses on service and intelligence networks that connect people, AI, devices, machines, data, compute, and the real world. The existing IoTeX L1 provides execution during the transition; follow-up IIPs determine transition mechanics without reopening canonicality.

## Effect of Approval

Approval establishes the decisions listed in this IIP and provides a strategic mandate for the Standards Track proposals needed to implement them. It does not authorize implementation by itself.

Token migration, contract deployment, L1 or L2 changes, and modifications to token-holder or staking rights each require a separate Standards Track IIP with a specification, security analysis, implementation plan, and governance approval.

## Relationship to Existing IIPs

### IIP-56

[IIP-56](iip-56.md) governs the deprecation and wind-down of CIOTX following the historical ioTube incident. Consistent with that process, CIOTX is not an eligible source asset for canonical migration, and this IIP does not reopen or extend CIOTX claims.

### IIP-57

The ZK light-client and bridge architecture proposed by [IIP-57](iip-57.md) can support secure Ethereum interoperability and verification of source retirement during the transition. Applicable components may be retained or adapted, but canonical IOTX does not permanently depend on a bridge for its economic validity.

### IIP-63

[IIP-63](iip-63.md) is the first implementation proposal under IIP-62. It specifies the new canonical ERC-20 contract, supply accounting, legacy ERC-20 and liquid native migration, source retirement, exchange and custodian procedures, activation, and security requirements.

Existing staking-position and governance migration remains outside IIP-63 and requires a separate Standards Track IIP.

## Backwards Compatibility

This Informational IIP makes no immediate protocol or contract change. Implementing IIPs must address compatibility through long migration windows, explicit activation conditions, exchange and custodian coordination, application guidance, transparent supply accounting, and recovery procedures.

## Security Considerations

Implementation proposals must address at minimum:

- canonical token contract and administrative-key security;
- conservation of the 10 billion IOTX economic supply;
- historical burns and source-token retirement;
- duplicate-claim and replay prevention;
- native-chain finality and event verification;
- migration of locked staking and governance state;
- exchange and custodian reconciliation;
- objective operator performance and slashing evidence;
- emergency powers and incident response; and
- progressive elimination of temporary authority.

The permanent canonical token must have materially less privileged control than the temporary migration system. Migration-specific verification, accounting, and issuance authority must reside in dedicated contracts that can be permanently disabled.

Any migration escrow must enforce supply conservation through publicly auditable, non-custodial smart-contract logic. Canonical IOTX may be released only against verifiable retirement of an eligible source claim; release authority must not depend on discretionary control by a multisig, committee, or other custodian.

## Follow-Up Proposals

Implementation should be divided into independently reviewable Standards Track IIPs covering:

1. [IIP-63](iip-63.md): canonical ERC-20 IOTX, supply accounting, and liquid-token migration;
2. existing staking-position and protocol-governance migration;
3. canonical IOTX staking and delegation architecture;
4. service-specific protocols and economics; and
5. any material change to IoTeX L1 execution or settlement.

Each proposal should include concrete specifications, threat models, test cases, audit requirements, activation criteria, and emergency procedures appropriate to its scope.

## References

- [IIP-56: Deprecation of CIOTX Across All Networks](iip-56.md)
- [IIP-57: Trustless Bridge: Replacing Keys with Proofs](iip-57.md)
- [IIP-63: Canonical IOTX ERC-20 Contract and Token Migration](iip-63.md)

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
