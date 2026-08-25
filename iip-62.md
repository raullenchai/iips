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

IOTX currently exists across a history of native and Ethereum-based representations, while its primary utility has been tied to gas, governance, staking, and block production on the sovereign IoTeX Layer 1. This architecture has supported the network to date, but it also fragments monetary settlement, liquidity and closely couples the purpose of IOTX to the continued operation of a specific blockchain.

This IIP proposes a longer-term model with two distinct layers:

1. **Ethereum as the canonical monetary and staking settlement layer for IOTX.** Follow-up migration IIPs will provide eligible native IOTX and legacy Ethereum ERC-20 IOTX with a one-to-one path into one canonical Ethereum asset, subject to a maximum economic supply of 10,000,000,000 IOTX (unchanged).
2. **IoTeX as a decentralized network of services and intelligence.** Operators stake or bond IOTX to provide useful services and intelligence such as device identity, data attestation, AI inference, compute, DePIN verification, and other forms of verifiable off-chain work.

The existing IoTeX Layer 1 continues operating during the transition. Follow-up Standards Track IIPs will define the implementation sequence for moving canonical monetary and staking settlement to Ethereum while preserving continuity for applications, users, delegates, and stakers.

## Long-Term Vision

> **Build a global intelligence that belongs to everyone, is controlled by no one, and never stops learning.**

This vision is not one giant AI built by one company, and it is not limited to building another conversational assistant. It is a living intelligence built by everyone.

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

## Effect of Approval

Approval of this IIP through IoTeX governance establishes Ethereum-canonical IOTX and the evolution of IoTeX toward an open, continuously learning intelligence network as the long-term architectural direction. It provides a strategic mandate for the research, design, and follow-up proposals needed to pursue that direction.

Approval does not authorize a token migration, contract deployment, L1 shutdown, L2 migration, other change to the existing IoTeX L1, or modification of current token-holder or staking rights. Each such change requires a separate Standards Track IIP with its own specification, security analysis, implementation plan, and governance approval.

## Motivation

### One canonical monetary asset

The historical coexistence of native IOTX and legacy ERC-20 IOTX creates ambiguity about which representation is the monetary source of truth. It also requires exchanges, custodians, wallets, and users to support different settlement rails for assets carrying the same name.

A single canonical IOTX on Ethereum provides one monetary settlement layer and allows integrations to use established Ethereum token, custody, and settlement infrastructure.

### Reduce structural liquidity fragmentation

Liquidity fragmentation has been a persistent problem for the IoTeX ecosystem. Native IOTX and legacy ERC-20 IOTX have existed on separate settlement rails, and not every exchange, custodian, market maker, wallet, or application supports both. Moving between representations has not always been frictionless or uniformly available.

This divides market-making inventory, exchange access, on-chain liquidity, collateral utility, and institutional support. Even when different representations refer to the same underlying economic asset, fragmented rails can produce uneven access, shallower liquidity, and weaker price convergence.

Establishing one canonical IOTX on Ethereum removes a structural source of fragmentation and enables exchanges, custodians, liquidity providers, DeFi applications, and users to converge over time on one settlement asset and one broadly supported integration rail.

### Separate the network mission from the blockchain

IoTeX's long-term differentiation can extend beyond general-purpose EVM blockspace. Device identity, trusted real-world data, DePIN verification, private or verifiable AI, compute coordination, and machine-to-machine services all require networks of operators that perform work and can be held economically accountable for that work.

Under this direction, the IoTeX Network is defined by the services it coordinates, not solely by the blockchain it operates.

### Give staking durable utility

Today, IOTX staking primarily supports delegate selection, governance, and L1 consensus. As IoTeX evolves into a service and security network, staking evolves with it.

IOTX staking can provide service-level cryptoeconomic security: operators bond IOTX, qualify to perform work, earn fees or incentives, and face penalties for objectively attributable failures. Community holders may support operators through delegation or pooled staking without being required to operate infrastructure themselves.

### Support a product-led network

Network services should respond to real product and developer demand. Applications should consume useful services from operators whose eligibility, capacity, and economic commitments are backed by IOTX. Infrastructure should be built in response to demonstrated usage rather than speculative assumptions about future demand.

Existing and emerging IoTeX applications, including local-first AI products such as Rapid, can provide an early window into this larger system. Product usage can reveal demand for external models, private data and memory, tools, compute, long-running research, verification, other agents, and physical-world access. No individual application defines the protocol or the long-term vision.

### Economic flywheel

The long-term model should connect application usage to sustainable demand for network services and cryptoeconomic security:

```text
Application demand
        |
        v
IoTeX services
        |
        v
Operator revenue and capacity
        |
        v
Required IOTX bonding and staking
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

The flywheel requires a measurable relationship between network usage and IOTX demand. As the amount, value, or risk of work assigned to an operator grows, the IOTX that operator must acquire or attract through delegation and place at risk must grow with it.

Future Standards Track IIPs must define this relationship for each specialized network, including operator eligibility, stake-to-capacity or stake-to-risk requirements, delegation, revenue distribution, and penalties. A service that creates activity but no credible requirement for bonded IOTX should not be presented as contributing to IOTX utility or this economic flywheel.

## Proposed Direction

### 1. Ethereum-canonical IOTX

IoTeX should establish one canonical IOTX asset on Ethereum.

The canonical asset will become the recognized monetary representation of IOTX for settlement, staking, ecosystem accounting, and institutional integration. A future Standards Track IIP must determine whether the existing legacy ERC-20 contract can safely serve this role or whether a new contract is required.

The canonical contract design should favor simple and auditable supply controls, minimized privileged authority, transparent governance, and broad compatibility with Ethereum infrastructure.

### 2. Supply and migration principles

Any future implementation must preserve the following invariants:

- The maximum economic supply remains **10,000,000,000 IOTX**.
- Each eligible source IOTX receives no more than one canonical IOTX.
- Migration uses a **1:1 denomination** and does not redenominate holders.
- A migrated source claim must be irreversibly burned, retired, or accounted for against a supply-constrained reserve before its canonical counterpart becomes economically active.
- The migration process must prevent double claims across all eligible source representations.
- Supply, retirement, escrow, and migration accounting must be publicly auditable.

Eligible native IOTX and legitimate legacy Ethereum ERC-20 IOTX must receive migration paths defined by later IIPs.

### 3. Preserve staking commitments

Moving the canonical asset must not automatically release existing staking commitments.

The directional principle is unambiguous: one old IOTX must migrate into one canonical IOTX whether it is liquid or staked. If an IOTX position is locked before migration, changing the canonical settlement layer must not make it liquid.

```text
Before migration                     After migration

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

A later Standards Track IIP must define the treatment of delegates, voting rights, accumulated rewards, auto-stake settings, contract-based staking, and exceptional cases.

This principle protects existing commitments while allowing the purpose of staking to evolve.

### 4. IoTeX Network

The IoTeX Network is a decentralized service and security network. One canonical IOTX asset and one persistent staking foundation support many specialized networks as real demand emerges.

```text
                         IOTX staking
                              |
        +---------------------+---------------------+
        |                     |                     |
        v                     v                     v
 AI inference           AI training          Verification
    networks                networks             networks
        |                     |                     |
        +-------------+-------+-------+-------------+
                      |               |
                      v               v
             Research and          Data and
          discovery networks    compute networks
                      |
                      v
             Physical intelligence
            devices, machines, and
              real-world systems
```

Potential specialized networks include:

- **AI inference networks:** discover, route, and execute inference using appropriate models and compute.
- **AI training networks:** support fine-tuning, specialization, continual learning, distributed training, and model improvement.
- **Compute networks:** discover and allocate GPU, CPU, edge, agent, or specialized compute.
- **Data networks:** find, authorize access to, license, provide, and validate datasets and real-world observations.
- **Verification networks:** independently evaluate inference, computation, data, claims, experiments, and agent execution.
- **Research and discovery networks:** run persistent loops from goals and hypotheses through search, experimentation, evaluation, learning, and revised hypotheses.
- **Physical intelligence networks:** connect sensors, devices, machines, vehicles, robots, wearables, and other real-world systems to intelligence that can observe and act.
- **Identity and attestation networks:** establish device and machine identity, provenance, trusted state, and accountable participation.

These networks do not all need to exist immediately or share identical designs. Each should emerge in response to demonstrated demand and specify the work performed, consumers of the service, payment model, operator requirements, measurable performance conditions, and security assumptions. IoTeX should not create artificial services merely to manufacture staking utility.

### 5. Operator and community staking

Future staking systems should distinguish between operator responsibility and community participation.

Operators bond IOTX to become eligible for jobs, demonstrate economic commitment, and back defined service guarantees. Community holders may delegate or stake in support of operators and receive an appropriate share of eligible rewards without transferring ownership of their principal to those operators.

Existing delegates will have a path to become operators across one or more specialized networks. Over time, a delegate can operate inference, training, research, data, compute, verification, or physical-world infrastructure. Community holders will be able to continue staking or delegating while choosing which operators or networks they support.

The continuity principle is: preserve the staking base first, then allow useful new forms of work to emerge progressively as demand appears.

Slashing should apply only when faults are objective, attributable, and independently verifiable. Services that cannot define safe slashing conditions may use reputation, withheld payment, limited job eligibility, or other mechanisms instead.

Operator economics should be supported by service fees and real network revenue.

### 6. Chain-agnostic services

IoTeX Network services are not restricted to a single execution environment. They can serve applications on IoTeX, Ethereum, Ethereum L2s, or other networks where demand exists.

This allows the IoTeX Network to grow as a service and security layer across an evolving execution architecture.

## Conceptual Architecture

```text
Ethereum
  canonical IOTX + monetary and staking settlement
                         |
                         v
               persistent IOTX staking
                         |
       +-----------------+------------------+
       |                 |                  |
       v                 v                  v
 AI and research    Data and compute    Verification and
    networks           networks        physical intelligence
       |                 |                  |
       +-----------------+------------------+
                         |
                         v
                    IoTeX Network
                         |
                         +--> IoTeX execution
                         +--> Ethereum and Ethereum L2s
                         +--> other networks and off-chain systems
```

The blockchain is an execution environment used by the network. It is not, by itself, the full definition of the network.

## Rationale

### Why Ethereum?

Ethereum provides a substantially stronger shared foundation for the monetary and staking layer of IOTX across several dimensions.

First, Ethereum provides deep and mature economic security for assets and contracts settled on it. A smaller sovereign network must continuously finance, maintain, and defend its own monetary settlement and security layer. Sovereign monetary settlement is not the differentiated value IoTeX is built to create under this direction.

Second, Ethereum provides a rich surrounding ecosystem of custody, wallets, smart contracts, institutional settlement, DeFi, liquidity, stablecoins, interoperability, developer tooling, security tooling, account infrastructure, exchanges, custodians, and applications. Canonical IOTX on Ethereum can participate more directly in this environment instead of remaining dependent on a separate settlement rail.

Third, Ethereum provides stronger connectivity to capital and liquidity. It is a primary settlement environment for stablecoins, on-chain markets, collateral systems, market makers, institutional custody, and liquidity across Ethereum L2s. This connectivity can benefit IOTX without requiring all IoTeX services to execute on Ethereum.

Fourth, Ethereum reduces recurring integration burdens for exchanges, custodians, wallets, and institutional partners that already support Ethereum. This is an important practical benefit, but it is not the strategic reason for the proposal. Exchange friction exposed the architectural problem; it did not create it.

Moving only the token contract while leaving the monetary and staking core dependent on a separate sovereign settlement layer would not fully resolve fragmentation. It would require a permanent mechanism between Ethereum-canonical IOTX and the chain where staking claims remain authoritative. That mechanism would become critical monetary infrastructure: a compromise, accounting failure, or prolonged outage could fragment backing, disrupt staking, or create competing claims on the same economic IOTX.

For that reason, this direction moves canonical IOTX and its persistent staking settlement to the same Ethereum foundation. The existing IoTeX L1 provides execution during the transition, while Ethereum becomes the source of monetary truth. The transition mechanics remain subject to separate Standards Track IIPs.

The reason for choosing Ethereum is broader than exchange convenience. IoTeX should own the layers where it can create differentiated value and rely on shared infrastructure where differentiation is limited. IoTeX's differentiated value lies in coordinating devices, machines, AI, DePIN, real-world data, compute, and verifiable services. Ethereum's differentiated value lies in monetary settlement, economic security, liquidity, custody, and interoperability.

The proposal therefore shifts IoTeX from vertically owning every layer of the stack toward owning the layers where IoTeX can create differentiated value. This is specialization: Ethereum provides canonical monetary and staking settlement, while IoTeX builds the service and security networks that connect intelligence to devices, machines, data, compute, and the real world. Follow-up governance determines the execution transition mechanics without reopening the canonicality decision established by this IIP.

### Why a service and security network?

Useful off-chain and real-world services require operators, service discovery, payments, monitoring, and economic accountability. IOTX can coordinate these functions and secure operator commitments even when the services are consumed across multiple blockchains or by applications that abstract blockchain interaction from users.

The core work of the IoTeX Network is to help applications, people, AI, and machines discover and use models, data, compute, tools, observations, and physical-world capabilities provided by independent operators. It should establish identity and permissions, match demand with resources, measure work, verify results, route compensation, and turn reliable feedback into further learning.

This work spans many specialized networks and execution environments. Blockchain execution is an implementation substrate for the mission; maintaining an independent settlement layer is not the mission.

### Why IOTX?

IOTX represents economic membership and security capacity in the IoTeX Network. Operators that wish to earn from IoTeX-coordinated services must acquire or attract delegated IOTX and place that economic value at risk against defined service commitments. As demand for economically useful operator capacity grows, the amount of IOTX required or delegated to secure that capacity grows with it.

IOTX is therefore an indispensable security asset rather than an optional payment or reward overlay. Each specialized network must establish a credible link between the work it coordinates and the IOTX required to qualify for, perform, or secure that work. Replacing IOTX as the endogenous security collateral of the IoTeX Network would require separate governance approval.

### Chainlink as a conceptual precedent

Chainlink demonstrates a useful separation between a token's settlement environment and the decentralized networks that use it. LINK is used for service payments and cryptoeconomic security, while node operators provide oracle and computation services across many networks. Chainlink staking allows node operators and community participants to back defined service performance with staked LINK.

IoTeX does not need to replicate Chainlink's products or staking model. The more relevant precedent is architectural: an Ethereum-based token can serve as the coordination and security layer for a broader network of independently operated services. IoTeX can apply this model to devices, DePIN infrastructure, real-world data, AI, compute, and verification.

### Why retain staking?

Staking represents an economically meaningful commitment to correct service operation, governance, or both. Retaining staking also provides continuity for holders and delegates, but continuity alone is insufficient: each future staking use must identify what is being secured and how performance is measured.

## Relationship to Existing IIPs

### IIP-57

The ZK light-client components proposed by [IIP-57](iip-57.md) remain relevant infrastructure for secure Ethereum interoperability during the transition from the current L1-centered architecture. IIP-57's bridge architecture can support that transition, and applicable components can be retained or adapted.

This IIP establishes the broader long-term direction: Ethereum is the canonical monetary and staking settlement layer, and the IoTeX Network exists to provide decentralized services and security. Follow-up Standards Track IIPs must specify how the L1 and bridge architecture transition and how applicable IIP-57 components are retained or adapted.

### IIP-56

[IIP-56](iip-56.md) governs the deprecation and wind-down of CIOTX following the historical ioTube incident. Consistent with that existing process, CIOTX is not designated as an eligible source asset for the future canonical IOTX migration, and this proposal does not reopen or extend CIOTX claims.

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
4. IoTeX Network operator and staking architecture;
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
