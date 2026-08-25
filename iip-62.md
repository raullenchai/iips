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

IOTX exists across native and Ethereum-based representations, with utility tied primarily to gas, governance, staking, and block production on the sovereign IoTeX Layer 1. This fragments IOTX ownership and liquidity and couples its purpose to one blockchain.

This IIP proposes a longer-term model with two distinct layers:

1. **Ethereum as the canonical home for IOTX.** Ethereum becomes the authoritative layer for IOTX supply, ownership, transfers, and staking. Follow-up migration IIPs will provide eligible native IOTX and legacy Ethereum ERC-20 IOTX with a one-to-one path into one canonical Ethereum asset, with the maximum economic supply unchanged at 10,000,000,000 IOTX.
2. **IoTeX as a foundation for open service and intelligence networks.** IOTX staking provides a common economic foundation for participation, commitment, delegation, and accountability across independently operated networks.

The existing IoTeX Layer 1 continues operating during the transition. Follow-up Standards Track IIPs will define the implementation sequence for establishing Ethereum as the canonical home for IOTX supply, ownership, transfers, and staking while preserving continuity for applications, users, delegates, and stakers.

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

The guiding principle is:

> **Collectively built. Individually sovereign. Continuously improving.**

### Continuity with the IoTeX mission

IoTeX has spent years working at the boundary between digital systems and the real world: devices, machine identity, real-world data, DePIN, verification, physical infrastructure, and trusted computation. As AI becomes capable of reasoning and acting, these previously separate pieces can become parts of a continuously learning intelligence system.

```text
Models             -> reasoning
Data               -> knowledge and memory
Sensors            -> senses
Robots and machines -> action
Compute            -> capacity
Humans             -> goals, creativity, and judgment
Verification       -> reliable feedback and learning
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

## Effect of Approval

Approval of this IIP through IoTeX governance establishes Ethereum-canonical IOTX and an open, continuously learning intelligence network as the long-term direction. IOTX staking becomes the common participation and commitment layer from which specialized networks can emerge. Approval provides a strategic mandate for the follow-up proposals needed to pursue that direction.

Approval does not authorize implementation. Token migration, contract deployment, L1 or L2 changes, and modifications to token-holder or staking rights each require a separate Standards Track IIP with a specification, security analysis, implementation plan, and governance approval.

## Motivation

### One canonical IOTX and deeper liquidity

Native IOTX and legacy ERC-20 IOTX create ambiguity about the authoritative record of supply and ownership while dividing market-making inventory, exchange access, on-chain liquidity, collateral utility, and institutional support across separate rails.

One canonical IOTX on Ethereum provides a single record of supply, ownership, transfers, and staking. It also allows exchanges, custodians, liquidity providers, DeFi applications, and users to converge on one asset and established Ethereum infrastructure.

### Separate the network mission from the blockchain

IoTeX's long-term differentiation can extend beyond general-purpose EVM blockspace. Device identity, trusted real-world data, DePIN verification, private or verifiable AI, compute coordination, and machine-to-machine services all require networks of operators that perform work and can be held economically accountable for that work.

Under this direction, the IoTeX Network is defined by the service and intelligence networks it enables, not solely by the blockchain it operates.

### Enable new networks through staking

Today, IOTX staking primarily supports delegate selection, governance, and L1 consensus. Under this direction, it becomes the persistent participation and commitment layer for new service and intelligence networks.

Staking can express operator eligibility, capacity, commitment, delegation, and accountability. Networks with objectively verifiable failures can also place bonded IOTX at risk. Operators earn service revenue, while community holders can support them through delegation or pooled staking without operating infrastructure themselves.

### Economic flywheel

The long-term model should connect application usage to sustainable demand for service and intelligence networks secured by IOTX staking:

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

The flywheel requires a measurable relationship between network usage and IOTX demand. As the amount, value, or risk of work assigned to an operator grows, the IOTX that operator must acquire or attract through delegation and place at risk must grow with it.

Future Standards Track IIPs must define this relationship for each specialized network, including operator eligibility, stake-to-capacity or stake-to-risk requirements, delegation, revenue distribution, and penalties. A service that creates activity but no credible requirement for bonded IOTX should not be presented as contributing to IOTX utility or this economic flywheel.

## Proposed Direction

### 1. Ethereum-canonical IOTX

IoTeX should establish one canonical IOTX asset on Ethereum while retaining the **IOTX** ticker.

The canonical asset will become the recognized representation of IOTX for supply, ownership, transfers, staking, ecosystem accounting, and institutional integration. A future Standards Track IIP must determine whether the existing legacy ERC-20 contract can safely serve this role or whether a new contract is required.

The canonical contract design should favor simple and auditable supply controls, minimized privileged authority, transparent governance, and broad compatibility with Ethereum infrastructure.

The permanent canonical token and the temporary migration system should be separated. The token contract should remain minimal and minimally privileged, while migration-specific verification, accounting, and temporary issuance authority reside in dedicated contracts that can be permanently disabled after migration.

### 2. Supply and migration principles

Any future implementation must preserve the following invariants:

- The maximum economic supply remains **10,000,000,000 IOTX**.
- Each eligible source IOTX receives no more than one canonical IOTX.
- Migration uses a **1:1 denomination** and does not redenominate holders.
- A migrated source claim must be irreversibly burned, retired, or accounted for through a supply-constrained, verifiable, non-custodial smart-contract escrow before its canonical counterpart becomes economically active.
- The migration process must prevent double claims across all eligible source representations.
- Supply, retirement, escrow, and migration accounting must be publicly auditable.

Eligible native IOTX and legitimate legacy Ethereum ERC-20 IOTX must receive migration paths defined by later IIPs.

### 3. Preserve staking commitments

Moving the canonical asset must not automatically release existing staking commitments.

The directional principle is unambiguous: one old IOTX must migrate into one canonical IOTX whether it is liquid or staked. If an IOTX position is locked before migration, changing the canonical home of IOTX must not make it liquid.

```text
Before migration                     After migration
on IoTeX L1                          on Ethereum

1,000,000 native IOTX                1,000,000 canonical IOTX
staked                               staked
locked until date X       1:1        locked until date X
        |----------------------------->|
```

An existing locked staking position must migrate into an economically equivalent locked position. Migration must preserve:

- ownership;
- principal;
- remaining lock duration; and
- economically material staking rights.

Ethereum-canonical IOTX will carry governance rights over the IoTeX protocol, with canonical staking positions serving as the basis for governance participation.

A later Standards Track IIP must define delegate representation, voting mechanics, accumulated rewards, auto-stake settings, contract-based staking, and exceptional cases.

This principle protects existing commitments while allowing the same staking foundation to enable new service and intelligence networks.

### 4. IOTX staking enables service and intelligence networks

The IoTeX Network is an open environment in which independently operated service and intelligence networks can emerge. Canonical IOTX staking provides a common economic foundation for participation, commitment, delegation, and accountability across these networks.

Potential specialized networks include:

- **AI inference networks:** discover, route, and execute inference using appropriate models and compute.
- **AI training networks:** support fine-tuning, specialization, continual learning, distributed training, and model improvement.
- **Compute networks:** discover and allocate GPU, CPU, edge, agent, or specialized compute.
- **Data networks:** find, authorize access to, license, provide, and validate datasets and real-world observations.
- **Verification networks:** independently evaluate inference, computation, data, claims, experiments, and agent execution.
- **Research and discovery networks:** run persistent loops from goals and hypotheses through search, experimentation, evaluation, learning, and revised hypotheses.
- **Physical intelligence networks:** connect sensors, devices, machines, vehicles, robots, wearables, and other real-world systems to intelligence that can observe and act.
- **Identity and attestation networks:** establish device and machine identity, provenance, trusted state, and accountable participation.

Each network should emerge in response to demonstrated demand and specify its work, users, revenue model, operator requirements, performance conditions, and security assumptions. IoTeX should not create artificial services merely to manufacture staking utility.

The staking foundation should distinguish operator responsibility from community participation. Operators bond IOTX to qualify for work and back defined commitments. Community holders may support operators through staking or delegation and receive an appropriate share of eligible rewards without transferring ownership of their principal.

Existing delegates will have a path to operate one or more specialized networks, while community holders can continue staking or delegating toward the operators and networks they support.

The continuity principle is: preserve the staking base first, then use it to enable useful new service and intelligence networks as demand appears.

Slashing applies only when faults are objective, attributable, and independently verifiable. Other networks may use reputation, withheld payment, limited job eligibility, or similar accountability mechanisms.

Operator economics should be supported by service fees and real network revenue. These networks can serve applications across IoTeX, Ethereum, Ethereum L2s, other networks, and off-chain systems.

## Rationale

### Why Ethereum?

Ethereum provides a stronger shared home for IOTX across four dimensions:

- **Economic security:** assets and contracts inherit Ethereum's mature security rather than requiring IoTeX to finance and defend an independent asset and staking layer.
- **Ecosystem:** canonical IOTX gains direct access to established custody, wallets, smart contracts, DeFi, stablecoins, interoperability, and developer and security tooling.
- **Liquidity:** IOTX connects more directly to on-chain markets, collateral systems, market makers, institutional custody, and liquidity across Ethereum L2s.
- **Integration:** exchanges, custodians, wallets, and institutions can reuse Ethereum infrastructure instead of maintaining a separate native-chain integration.

Moving only the token contract while leaving staking dependent on a separate sovereign chain would not fully resolve fragmentation. It would require a permanent mechanism between Ethereum-canonical IOTX and the chain where staking records remain authoritative. That mechanism would become critical IOTX infrastructure: a compromise, accounting failure, or prolonged outage could fragment backing, disrupt staking, or create competing claims on the same economic IOTX.

Ethereum therefore becomes the canonical home for both IOTX and staking. This is specialization: Ethereum provides secure, liquid, broadly integrated asset infrastructure, while IoTeX focuses on service and intelligence networks that connect people, AI, devices, machines, data, compute, and the real world. The existing IoTeX L1 provides execution during the transition; follow-up IIPs determine transition mechanics without reopening canonicality.

### Why service and intelligence networks?

The intelligence loop requires independently operated models, data, compute, tools, observations, and physical-world capabilities. The IoTeX Network helps people, AI, machines, and applications discover these resources, establish identity and permissions, match demand with capacity, measure work, verify results, and compensate contributors. This work spans multiple networks and execution environments; blockchain execution is a substrate for the mission, not the mission itself.

### Why IOTX staking?

IOTX staking expresses economic participation and commitment across IoTeX service and intelligence networks. Operators that wish to earn from these networks must acquire or attract delegated IOTX and commit it against defined responsibilities. As demand for useful operator capacity grows, required or delegated IOTX grows with it.

Staking can represent participation, capacity, delegation, reputation, access, accountability, or slashable security, depending on the network. Each network must identify what staking enables, how performance is measured, and how IOTX demand relates to useful work. Replacing IOTX as the common economic foundation requires separate governance approval.

## Relationship to Existing IIPs

### IIP-57

The ZK light-client and bridge architecture proposed by [IIP-57](iip-57.md) can support secure Ethereum interoperability during the transition from the current L1-centered architecture. Follow-up Standards Track IIPs must specify how applicable components are retained or adapted under the direction established by IIP-62.

### IIP-56

[IIP-56](iip-56.md) governs the deprecation and wind-down of CIOTX following the historical ioTube incident. Consistent with that existing process, CIOTX is not designated as an eligible source asset for the future canonical IOTX migration, and this proposal does not reopen or extend CIOTX claims.

## Backwards Compatibility

This Informational IIP makes no immediate protocol or contract change. Implementing IIPs must address compatibility through long migration windows, explicit activation conditions, exchange and custodian coordination, application guidance, transparent supply accounting, and recovery procedures.

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

Any migration escrow must enforce supply conservation through publicly auditable, non-custodial smart-contract logic. Canonical IOTX may be released only against verifiable retirement of an eligible source claim; release authority must not depend on discretionary control by a multisig or other custodian.

## Follow-up Proposals

Implementation of this direction should be divided into independently reviewable Standards Track IIPs, including:

1. [IIP-63](iip-63.md), which specifies the canonical IOTX contract, supply-accounting rules, and native and legacy ERC-20 liquid migration mechanisms;
2. existing staking-position and governance migration;
3. IoTeX Network operator and staking architecture;
4. initial service-specific protocols and economics; and
5. any change to IoTeX L1 execution or settlement.

Each proposal should include concrete specifications, threat models, test cases, audits, activation criteria, and rollback or recovery procedures appropriate to its scope.

## References

- [IIP-56: Deprecation of CIOTX Across All Networks](iip-56.md)
- [IIP-57: Trustless Bridge: Replacing Keys with Proofs](iip-57.md)
- [IIP-63: Canonical IOTX ERC-20 Contract and Token Migration](iip-63.md)

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
