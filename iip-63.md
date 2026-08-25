```
IIP: 63
Title: Canonical IOTX ERC-20 Contract and Token Migration
Author: Raullen Chai (@raullenchai), Qevan Guo (@guo)
Discussions-to: TBD
Status: Draft
Type: Standards Track
Category: Token / Core
Created: 2026-08-25
Requires: IIP-62
```

## Abstract

This IIP implements the first phase of IIP-62 by establishing a new canonical IOTX ERC-20 contract on Ethereum and defining a one-to-one migration framework for eligible IOTX.

The proposal provides:

1. a canonical ERC-20 IOTX contract on Ethereum;
2. an unchanged maximum economic supply of 10,000,000,000 IOTX;
3. one-to-one migration for eligible legacy Ethereum ERC-20 IOTX and liquid native IOTX;
4. verifiable source-claim retirement before or simultaneous with canonical issuance;
5. non-custodial, publicly auditable migration accounting;
6. exchange and custodian migration procedures; and
7. a temporary, supply-constrained migration issuance mechanism that is permanently disabled after all approved migration obligations are complete.

The migration retains the **IOTX** ticker, 18 decimals, one-to-one denomination, holder ownership, and valid economic entitlement. This IIP does not make a locked staking position liquid. A separate Standards Track IIP must define the migration of locked staking positions, delegation, and governance mechanics before the transition established by IIP-62 is considered complete.

## Motivation

IIP-62 establishes Ethereum as the canonical home for IOTX supply, ownership, transfers, staking, and protocol-level governance rights. IOTX currently exists across native IoTeX and legacy Ethereum representations, fragmenting liquidity and requiring exchanges, custodians, wallets, and users to support separate rails.

This IIP begins implementation by creating one canonical Ethereum ERC-20 IOTX and a controlled migration process based on three priorities.

### Supply integrity

Migration must not create additional economic IOTX. Every canonical IOTX issued through migration must correspond to a unique eligible source entitlement that is verifiably and irreversibly retired from economic use.

### Exchange compatibility

The canonical token uses a simple, widely supported ERC-20 architecture. For institutions already supporting legacy Ethereum IOTX, migration resembles a standard ERC-20 contract replacement. Institutions supporting native IOTX perform a one-time inventory migration and may transition deposits and withdrawals to Ethereum.

### No permanent bridge dependency

Cross-chain verification may be used to prove native source retirement during migration, but canonical IOTX supply must not depend on a permanent bridge between Ethereum and IoTeX. After migration, Ethereum provides the authoritative record of canonical IOTX ownership and supply.

## Goals

This IIP aims to:

- deploy one canonical Ethereum IOTX contract;
- retain the `IOTX` ticker and 18 decimals;
- preserve one-to-one denomination and holder entitlement;
- preserve the 10 billion maximum economic supply and all historical retirements;
- migrate eligible liquid legacy ERC-20 and native IOTX;
- preserve locked staking and governance entitlement for later migration;
- support self-custody and exchange-managed migration;
- prevent duplicate claims;
- make migration accounting publicly auditable;
- minimize permanent token-contract privileges; and
- eliminate temporary migration authority after all approved obligations are fulfilled.

## Non-Goals

This IIP does not:

- make existing locked staking positions liquid;
- define final staking, delegation, or governance mechanics on Ethereum;
- redesign staking economics;
- shut down the IoTeX Layer 1;
- define future IoTeX execution architecture;
- establish service- or intelligence-network staking;
- reopen CIOTX claims governed by IIP-56;
- create a token sale, holder bonus, airdrop, or new allocation;
- change the IOTX denomination, decimals, or ticker; or
- create a permanent Ethereum-IoTeX bridge.

## Definitions and Transition States

For this IIP:

- **Canonical IOTX** is IOTX issued by the Ethereum ERC-20 contract specified here.
- **Source claim** is a unique eligible unit of legacy ERC-20, native liquid, or later approved locked/staked IOTX entitlement.
- **Retirement** makes a source claim permanently unavailable for transfer, redemption, or a second migration.
- **Migration activation** enables migration into canonical IOTX under the rules of this IIP.
- **Migration finalization** permanently disables a completed migration path after its claims and accounting are reconciled.
- **Canonical completion** occurs only after eligible liquid assets and existing locked staking and governance entitlements have migration paths approved and activated through Standards Track IIPs.

Deployment of the canonical contract does not by itself complete the transition established by IIP-62. During migration, the existing IoTeX L1 staking and governance systems remain authoritative for positions not yet migrated.

## Specification

### 1. Canonical token

A new ERC-20 contract will be deployed on Ethereum Mainnet with the following parameters:

| Parameter | Value |
|---|---|
| Name | IoTeX Network |
| Symbol | IOTX |
| Decimals | 18 |
| Maximum economic supply | 10,000,000,000 IOTX |
| Contract address | TBD before approval |

After migration activation, this contract becomes the canonical representation for migrated IOTX. The existing Ethereum IOTX contract at `0x6fB3e0A217407EFFf7Ca062D46c26E5d60a14d69` becomes a legacy migration asset and is no longer canonical after its published cutoff.

Ethereum-canonical IOTX carries governance rights over the IoTeX protocol. A separate Standards Track IIP will define how canonical balances, staking positions, delegation, and voting mechanics determine governance participation.

### 2. Canonical token contract requirements

The canonical token contract MUST favor compatibility, auditability, and minimal privileged authority. It SHOULD use widely reviewed ERC-20 components, SHOULD NOT use an upgradeable proxy, and SHOULD be immutable after deployment.

The permanent token MUST NOT include:

- transfer taxes or fee-on-transfer behavior;
- rebasing or reflection mechanics;
- arbitrary balance modification or confiscation;
- transfer blacklists or arbitrary account freezing;
- external transfer hooks;
- hidden mint paths; or
- unrestricted owner minting.

Temporary migration issuance authority MUST be:

- enforced by smart-contract invariants rather than discretionary signer approval;
- bounded by the global supply cap and exact source entitlement;
- publicly observable and independently reproducible;
- usable only after verifiable source retirement;
- incapable of creating ecosystem allocations; and
- permanently revoked after all approved migration obligations are complete.

### 3. Supply invariants

Let:

- `S_MAX = 10,000,000,000 IOTX`;
- `C` be economically active canonical IOTX;
- `N` be eligible liquid native IOTX not yet retired, excluding `L`;
- `E` be eligible legacy ERC-20 IOTX not yet retired;
- `L` be valid locked or staked native IOTX entitlement reserved for later migration; and
- `S_ELIGIBLE` be the reconciled economic supply after excluding historical burns, duplicate representations, and ineligible claims.

At all times:

```text
C + N + E + L <= S_ELIGIBLE <= S_MAX
```

For each source representation:

```text
CanonicalIOTXIssued(source) <= EligibleIOTXRetired(source)
```

No source unit may be claimed twice. Wrapped, bridged, exchange-issued, or derivative IOTX does not create an independent entitlement in addition to its underlying eligible IOTX.

Before activation, a public supply report MUST identify and reconcile:

- the 10 billion maximum supply;
- current economic supply;
- historical burns and other permanent retirements;
- eligible legacy ERC-20 supply;
- eligible native liquid supply;
- native locked and staked entitlement;
- backing balances for non-independent representations;
- migration-ineligible claims; and
- total migration entitlement by source.

The report MUST reconcile to publicly verifiable on-chain data. Historical burns remain retired and do not become migration-eligible because a new contract is deployed.

### 4. Migration eligibility

The following source assets are eligible for one-to-one migration:

1. legitimate legacy Ethereum ERC-20 IOTX at `0x6fB3e0A217407EFFf7Ca062D46c26E5d60a14d69`; and
2. eligible liquid native IOTX on the IoTeX Layer 1.

Existing locked or staked native IOTX retains one-to-one economic entitlement to canonical IOTX but MUST NOT become liquid through migration. Its ownership, principal, remaining lock duration, delegation, rewards, and governance rights remain effective on the existing system until a separate Standards Track IIP activates an economically equivalent canonical position.

CIOTX remains governed by IIP-56 and does not create migration entitlement under this IIP.

Other wrapped, bridged, exchange-issued, or derivative representations—including WIOTX, exchange pegs, bridged tokens on other networks, and liquid staking derivatives—do not create independent entitlement. Where a valid redemption mechanism exists, the representation must first resolve into its eligible underlying source asset or be handled by its responsible issuer or custodian.

### 5. Token and migration contracts

The system separates the permanent token from temporary migration components.

The permanent component is:

- `CanonicalIOTX`: the canonical ERC-20 token.

Temporary components include:

- `MigrationController`;
- `LegacyERC20MigrationVault`;
- `NativeRetirementContract`; and
- `NativeRetirementVerifier`.

The recommended issuance model is **mint-on-retirement**. `CanonicalIOTX` begins with zero supply unless the final audited design establishes a mathematically equivalent non-custodial escrow model. Canonical IOTX is issued only after an eligible source claim has been verifiably retired.

`MigrationController` MUST enforce:

1. the 10 billion global cap;
2. the reconciled `S_ELIGIBLE` cap;
3. a separate allowance for each source class;
4. unique source-claim identifiers and replay protection;
5. issuance no greater than verified retirement;
6. no discretionary multisig or custodian release path; and
7. irreversible shutdown after all approved migration obligations, including locked staking migration, are fulfilled.

Liquid migration paths may be disabled independently when complete. A contract-enforced issuance allowance equal to the reconciled locked staking entitlement MUST remain available exclusively for the staking migration IIP and MUST NOT be canceled, redirected, or used for any other issuance.

## Legacy Ethereum ERC-20 Migration

### Atomic retirement and issuance

`LegacyERC20MigrationVault` accepts legacy Ethereum IOTX and issues canonical IOTX at exactly one-to-one:

```text
User or exchange
      |
      | approve legacy IOTX
      v
LegacyERC20MigrationVault
      |
      | transferFrom legacy IOTX
      | irreversible retirement
      v
MigrationController
      |
      | issue the same amount
      v
Canonical IOTX
```

For amount `X`:

```text
X legacy IOTX retired -> X canonical IOTX issued
```

Retirement and issuance MUST be atomic. If canonical issuance fails, transfer and retirement of the legacy token MUST revert.

If the legacy contract cannot burn, migrated tokens MUST enter an immutable retirement vault with:

- no withdrawal path;
- no proxy or upgrade mechanism;
- no administrator recovery function; and
- a publicly readable retired balance.

Tokens in this vault are permanently retired from economic circulation. Exchanges may migrate legacy ERC-20 custody inventory through the same contract without using the IoTeX L1 or a cross-chain bridge.

## Native IOTX Migration

### Source retirement

Liquid native IOTX MUST be irreversibly retired before or atomically with corresponding canonical issuance.

```text
Native IOTX on IoTeX L1
          |
          v
NativeRetirementContract
          |
          | finalized retirement event
          v
Trust-minimized verification on Ethereum
          |
          v
MigrationController
          |
          v
Canonical IOTX on Ethereum
```

The source-side retirement mechanism MUST:

- make migrated principal permanently unavailable for native transfer;
- emit an unambiguous claim identifier, amount, and Ethereum recipient;
- prevent replay;
- provide deterministic public accounting; and
- define finality and reorganization handling.

### Native retirement verification

Canonical issuance requires trust-minimized verification of a finalized native retirement event. The final implementation MUST specify the proof system, verifier contract, accepted IoTeX finality, event format, replay protection, and failure recovery before approval.

Applicable ZK light-client components from IIP-57 MAY be used. A proof-based or mathematically equivalent non-custodial mechanism is REQUIRED. A multisig, committee, custodian, or other discretionary signer set MUST NOT authorize canonical issuance or become a fallback issuance path.

The verifier is migration-only infrastructure. It MUST NOT become a permanent bridge or retain authority over ordinary canonical IOTX transfers.

### Exchange-assisted native migration

An exchange may migrate native custody inventory in coordinated batches:

1. pause native deposits and withdrawals;
2. reconcile customer liabilities and on-chain inventory;
3. send the agreed inventory to `NativeRetirementContract`;
4. wait for required finality;
5. submit or observe verification on Ethereum;
6. receive exactly the retired amount of canonical IOTX;
7. reconcile source retirement and canonical receipt;
8. update IOTX deposits and withdrawals to Ethereum; and
9. resume service.

Customer ledger balances remain unchanged:

```text
1 IOTX before migration = 1 IOTX after migration
```

An exchange may migrate balances automatically without requiring customers to withdraw and migrate individually.

## Exchange and Custodian Requirements

An institution supporting legacy Ethereum IOTX must update the token contract address, metadata, deposit recognition, withdrawal configuration, and custody inventory. The ticker, decimals, denomination, customer balances, and trading-pair identifiers need not change, subject to internal policy.

An institution supporting native IOTX must additionally retire native custody inventory, discontinue native deposits after its published cutoff, transition withdrawals to Ethereum, and communicate the network change. Continued native-chain support is not required for canonical IOTX custody after that institution completes migration.

Before production migration, IoTeX MUST provide institutions with verified source code, audits, contract addresses, test transactions, supply reconciliation, migration instructions, cutoff procedures, and incident contacts.

## What Does Not Change

The migration does not change:

- the `IOTX` ticker;
- 18 decimals;
- one-to-one holder denomination;
- the 10 billion maximum economic supply;
- valid holder ownership and entitlement; or
- protocol-level governance entitlement associated with canonical IOTX.

The migration does not create a token sale, holder bonus, airdrop, redenomination, or migration-related allocation.

## Activation and Rollout

### Preconditions

Public migration MUST NOT begin until:

- the final specification contains no security-critical TBDs;
- canonical token and migration source code is public;
- deployed contracts are verified on Etherscan and the IoTeX explorer;
- independent audits cover every production component;
- critical and high-severity findings are resolved;
- the supply report and machine-readable reconciliation are public;
- native retirement verification is implemented and tested;
- exchange and custodian documentation is available;
- end-to-end test migrations are complete;
- emergency and recovery procedures are documented; and
- governance approves activation.

### Rollout stages

1. **Final specification:** finalize the supply report, contracts, verification mechanism, and audits.
2. **Institutional integration:** distribute the technical package and coordinate exchange and custodian windows.
3. **Contract activation:** deploy canonical IOTX and activate only approved migration allowances.
4. **Legacy ERC-20 migration:** enable atomic one-to-one self-custody and institutional migration.
5. **Native liquid migration:** enable proof-backed one-to-one native retirement and canonical issuance.
6. **Representation deprecation:** mark completed source representations deprecated after published cutoffs.
7. **Staking and governance migration:** activate the separate Standards Track IIP preserving locked positions and protocol governance.
8. **Canonical completion:** finalize all source accounting and recognize Ethereum as the sole authoritative home for IOTX and staking under IIP-62.

Each stage MUST publish activation conditions and completion evidence. No source representation may be deprecated before affected holders and institutions have a functional migration path and adequate notice.

### Migration window and unresolved claims

The final specification MUST define the start date, minimum migration window, claim cutoff policy, treatment of late or disputed claims, and conditions for extending or closing each path. Expiration MUST NOT silently convert a valid holder entitlement into a discretionary treasury balance.

## Migration Finalization

After all migration paths and outstanding claims are resolved:

1. publish final retirement totals by source;
2. publish final canonical issuance and economic-supply reconciliation;
3. reconcile unused migration allowance;
4. disable source-specific migration paths;
5. permanently revoke all migration issuance authority; and
6. publish a final on-chain and independent supply attestation.

Temporary migration infrastructure MUST NOT retain discretionary authority over canonical IOTX after finalization.

## Public Supply Dashboard

During migration, an official dashboard and machine-readable dataset SHOULD publish:

```text
Maximum economic supply
Reconciled eligible economic supply
Current canonical supply
Legacy ERC-20 outstanding and retired
Native liquid IOTX outstanding and retired
Canonical IOTX issued by source
Locked and staked native entitlement reserved for later migration
Ineligible and non-independent representations
Remaining migration allowance by source
```

The following invariants MUST be independently reproducible:

```text
Canonical issuance <= irreversibly retired eligible claims

Canonical active supply
+ eligible unretired native supply
+ eligible unretired legacy ERC-20 supply
+ valid locked/staked entitlement
<= reconciled eligible economic supply
<= 10,000,000,000 IOTX
```

## Security Considerations

### Token contract risk

The permanent token minimizes attack surface through a reviewed ERC-20 implementation, verified source, immutability, no arbitrary transfer controls, and no discretionary mint function.

### Migration issuance risk

Temporary issuance authority is the largest migration-specific risk. It is constrained by the global cap, reconciled source allowances, verifiable source retirement, replay protection, public monitoring, and permanent revocation. No multisig or custodian may exercise discretionary issuance or release authority.

### Double-claim risk

Every source claim requires a unique identifier. A retired claim cannot be reused, and a derivative representation cannot claim independently when its underlying asset is already eligible.

### Native verification risk

Ethereum MUST NOT issue canonical IOTX from an unfinalized, ambiguous, or unverifiable IoTeX event. The verifier must enforce finality, event validity, recipient binding, amount integrity, and replay protection.

### Staking and governance continuity risk

Liquid migration MUST NOT release locked stake or duplicate voting power. Until a staking position migrates under a separate approved IIP, its staking and governance authority remains exclusively on the existing IoTeX system. After migration, the source position must be retired before its canonical staking and governance rights become active.

### Exchange operational risk

Institutions must reconcile customer liabilities, source inventory, retirement, canonical receipt, deposit cutoffs, and withdrawal configuration. Full inventory migration SHOULD follow successful test transactions.

### Legacy deposit risk

After an institution completes migration, deposits of legacy or native IOTX may be unrecoverable. Institutions and IoTeX SHOULD provide clear notice, network labeling, and cutoff dates.

## Backwards Compatibility

Balances remain economically compatible at one-to-one denomination, but applications and institutions must update to a new Ethereum contract and, for native integrations, a new deposit and withdrawal network.

The existing IoTeX L1 remains operational during the transition. Locked staking positions and governance rights remain there until migrated under a separate Standards Track IIP.

## Test Requirements

Before activation, implementations MUST test at minimum:

- one-to-one legacy migration;
- zero-value and invalid-recipient rejection;
- repeated-claim and replay rejection;
- issuance above source allowance, `S_ELIGIBLE`, or `S_MAX` rejection;
- retirement-vault withdrawal impossibility;
- atomic rollback when canonical issuance fails;
- valid and invalid native proofs;
- source finality and reorganization behavior;
- recipient and amount binding;
- exchange batch migration and reconciliation;
- emergency halt and recovery of migration components;
- source-specific finalization; and
- permanent revocation of issuance authority.

## Audit Requirements

Independent review MUST cover:

- `CanonicalIOTX`;
- `MigrationController`;
- `LegacyERC20MigrationVault`;
- `NativeRetirementContract`;
- `NativeRetirementVerifier`;
- supply reconciliation and deployment configuration;
- administrative roles and emergency controls; and
- migration finalization.

Audit reports, deployed bytecode hashes, compiler settings, and constructor parameters MUST be public before activation.

## Relationship to Existing IIPs

### IIP-62

IIP-62 establishes Ethereum-canonical IOTX and the long-term role of staking as the common economic foundation for service and intelligence networks. IIP-63 implements the canonical token and liquid migration phase without modifying that direction.

### IIP-56

IIP-56 remains authoritative for CIOTX deprecation and claims arising from the historical ioTube incident. IIP-63 does not create migration entitlement for CIOTX.

### IIP-57

Applicable proof-verification components from IIP-57 may verify finalized native retirement events on Ethereum. Unlike a permanent bridge, this verification facilitates one-way canonical migration and does not maintain two permanently interchangeable canonical representations.

## Open Parameters Before Approval

This Draft must be updated with:

- the canonical token contract address and deployed bytecode;
- the final initial-supply and issuance model;
- the reconciled `S_ELIGIBLE` value and per-source allowances;
- the native retirement contract and proof-verification mechanism;
- the relationship to the approved staking and governance migration IIP;
- audit firms, reports, and remediations;
- activation blocks and dates;
- migration windows and late-claim policy;
- emergency and recovery procedures; and
- finalization conditions.

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
