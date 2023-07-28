**Note:** There is a section for disputed findings below the gas report section

## Summary


### Gas Optimizations

| |Issue|Instances|Total Gas Saved|
|-|:-|:-:|:-:|
| [[G&#x2011;01](#g01-reduce-gas-usage-by-moving-to-solidity-0819-or-later)] | Reduce gas usage by moving to Solidity 0.8.19 or later | 68 |  - |
| [[G&#x2011;02](#g02-using-bools-for-storage-incurs-overhead)] | Using `bool`s for storage incurs overhead | 17 |  290700 |
| [[G&#x2011;03](#g03-avoid-updating-storage-when-the-value-hasnt-changed)] | Avoid updating storage when the value hasn't changed | 26 |  20800 |
| [[G&#x2011;04](#g04-unchecked---can-be-used-on-the-division-of-two-uints-in-order-to-save-gas)] | `unchecked {}`  can be used on the division of two `uint`s in order to save gas | 76 |  1520 |
| [[G&#x2011;05](#g05-remove-or-replace-unused-state-variables)] | Remove or replace unused state variables | 3 |  - |
| [[G&#x2011;06](#g06-multiple-addressid-mappings-can-be-combined-into-a-single-mapping-of-an-addressid-to-a-struct-where-appropriate)] | Multiple `address`/ID mappings can be combined into a single `mapping` of an `address`/ID to a `struct`, where appropriate | 10 |  420 |
| [[G&#x2011;07](#g07-state-variables-only-set-in-the-constructor-should-be-declared-immutable)] | State variables only set in the constructor should be declared `immutable` | 27 |  56619 |
| [[G&#x2011;08](#g08-state-variables-can-be-packed-into-fewer-storage-slots)] | State variables can be packed into fewer storage slots | 6 |  12000 |
| [[G&#x2011;09](#g09-using-storage-instead-of-memory-for-structsarrays-saves-gas)] | Using `storage` instead of `memory` for structs/arrays saves gas | 18 |  75600 |
| [[G&#x2011;10](#g10-state-variables-should-be-cached-in-stack-variables-rather-than-re-reading-them-from-storage)] | State variables should be cached in stack variables rather than re-reading them from storage | 156 |  15132 |
| [[G&#x2011;11](#g11-x--y-costs-more-gas-than-x--x--y-for-state-variablesyxxyx)] | `<x> += <y>` costs more gas than `<x> = <x> + <y>` for state variables | 5 |  565 |
| [[G&#x2011;12](#g12-add-unchecked--for-subtractions-where-the-operands-cannot-underflow-because-of-a-previous-require-or-if-statement)] | Add `unchecked {}` for subtractions where the operands cannot underflow because of a previous `require()` or `if`-statement | 21 |  1785 |
| [[G&#x2011;13](#g13-arraylength-should-not-be-looked-up-in-every-loop-of-a-for-looparray)] | `<array>.length` should not be looked up in every loop of a `for`-loop | 24 |  72 |
| [[G&#x2011;14](#g14-ii-should-be-uncheckediuncheckedi-when-it-is-not-possible-for-them-to-overflow-as-is-the-case-when-used-in-for--and-while-loops)] | `++i`/`i++` should be `unchecked{++i}`/`unchecked{i++}` when it is not possible for them to overflow, as is the case when used in `for`- and `while`-loops | 27 |  1620 |
| [[G&#x2011;15](#g15-private-functions-not-called-by-the-contract-should-be-removed-to-save-deployment-gas)] | `private` functions not called by the contract should be removed to save deployment gas | 1 |  - |
| [[G&#x2011;16](#g16-optimize-names-to-save-gas)] | Optimize names to save gas | 54 |  1188 |
| [[G&#x2011;17](#g17--costs-less-gas-than-)] | `>=` costs less gas than `>` | 2 |  6 |
| [[G&#x2011;18](#g18-internal-functions-not-called-by-the-contract-should-be-removed-to-save-deployment-gas)] | `internal` functions not called by the contract should be removed to save deployment gas | 1 |  - |
| [[G&#x2011;19](#g19-i-costs-less-gas-than-i-especially-when-its-used-in-for-loops---ii---too)] | `++i` costs less gas than `i++`, especially when it's used in `for`-loops (`--i`/`i--` too) | 41 |  205 |
| [[G&#x2011;20](#g20-splitting-require-statements-that-use--saves-gas)] | Splitting `require()` statements that use `&&` saves gas | 7 |  21 |
| [[G&#x2011;21](#g21-using-private-rather-than-public-for-constants-saves-gas)] | Using `private` rather than `public` for constants, saves gas | 17 |  - |
| [[G&#x2011;22](#g22-dont-compare-boolean-expressions-to-boolean-literals)] | Don't compare boolean expressions to boolean literals | 6 |  54 |
| [[G&#x2011;23](#g23-multiple-if-statements-with-mutually-exclusive-conditions-should-be-changed-to-if-else-statements)] | Multiple `if`-statements with mutually-exclusive conditions should be changed to `if`-`else` statements | 2 |  - |
| [[G&#x2011;24](#g24-require-or-revert-statements-that-check-input-arguments-should-be-at-the-top-of-the-function)] | `require()` or `revert()` statements that check input arguments should be at the top of the function | 3 |  - |
| [[G&#x2011;25](#g25-empty-blocks-should-be-removed-or-emit-something)] | Empty blocks should be removed or emit something | 23 |  - |
| [[G&#x2011;26](#g26-superfluous-event-fields)] | Superfluous event fields | 1 |  34 |
| [[G&#x2011;27](#g27-use-custom-errors-rather-than-revertrequire-strings-to-save-gas)] | Use custom errors rather than `revert()`/`require()` strings to save gas | 244 |  - |
| [[G&#x2011;28](#g28-functions-guaranteed-to-revert-when-called-by-normal-users-can-be-marked-payable)] | Functions guaranteed to revert when called by normal users can be marked `payable` | 87 |  1827 |
| [[G&#x2011;29](#g29-constructors-can-be-marked-payable)] | Constructors can be marked `payable` | 50 |  1050 |
| [[G&#x2011;30](#g30-structs-can-be-packed-into-fewer-storage-slots)] | Structs can be packed into fewer storage slots | 5 |  10000 |
| [[G&#x2011;31](#g31-inverting-the-condition-of-an-if-else-statement-wastes-gas)] | Inverting the condition of an `if`-`else`-statement wastes gas | 1 |  - |
| [[G&#x2011;32](#g32-division-by-two-should-use-bit-shifting)] | Division by two should use bit shifting | 3 |  60 |
| [[G&#x2011;33](#g33-structs-can-be-packed-into-fewer-storage-slots-by-truncating-timestamp-bytes)] | Structs can be packed into fewer storage slots by truncating timestamp bytes | 1 |  2000 |
| [[G&#x2011;34](#g34-multiple-accesses-of-a-mappingarray-should-use-a-local-variable-cache)] | Multiple accesses of a mapping/array should use a local variable cache | 10 |  420 |
| [[G&#x2011;35](#g35-internal-functions-only-called-once-can-be-inlined-to-save-gas)] | `internal` functions only called once can be inlined to save gas | 26 |  520 |
| [[G&#x2011;36](#g36-requirerevert-strings-longer-than-32-bytes-cost-extra-gas)] | `require()`/`revert()` strings longer than 32 bytes cost extra gas | 23 |  69 |
| [[G&#x2011;37](#g37-keccak256-should-only-need-to-be-called-on-a-specific-string-literal-once)] | `keccak256()` should only need to be called on a specific string literal once | 3 |  126 |
| [[G&#x2011;38](#g38-usage-of-uintsints-smaller-than-32-bytes-256-bits-incurs-overhead)] | Usage of `uints`/`ints` smaller than 32 bytes (256 bits) incurs overhead | 5 |  110 |
| [[G&#x2011;39](#g39-stack-variable-used-as-a-cheaper-cache-for-a-state-variable-is-only-used-once)] | Stack variable used as a cheaper cache for a state variable is only used once | 1 |  3 |
| [[G&#x2011;40](#g40-consider-using-bytes32-rather-than-a-string)] | Consider using `bytes32` rather than a `string` | 8 |  - |
| [[G&#x2011;41](#g41-the-result-of-function-calls-should-be-cached-rather-than-re-calling-the-function)] | The result of function calls should be cached rather than re-calling the function | 8 |  - |
| [[G&#x2011;42](#g42-use-a-more-recent-version-of-solidity)] | Use a more recent version of solidity | 2 |  - |
| [[G&#x2011;43](#g43-not-using-the-named-return-variables-anywhere-in-the-function-is-confusing)] | Not using the named return variables anywhere in the function is confusing | 69 |  - |
| [[G&#x2011;44](#g44-avoid-contract-existence-checks-by-using-low-level-calls)] | Avoid contract existence checks by using low level calls | 2 |  200 |
| [[G&#x2011;45](#g45-string-literals-passed-to-abiencodeabiencodepacked-should-not-be-split-by-commas)] | String literals passed to `abi.encode()`/`abi.encodePacked()` should not be split by commas | 1 |  21 |

Total: 1191 instances over 45 issues with **494747 gas** saved

Gas totals are estimates based on data from the Ethereum Yellowpaper. The estimates use the lower bounds of ranges and count two iterations of each `for`-loop. All values above are runtime, not deployment, values; deployment values are listed in the individual issue descriptions. The table above as well as its gas numbers do not include any of the excluded findings.

### Disputed Issues

The issues below may be reported by other bots/wardens, but can be penalized/ignored since either the rule or the specified instances are invalid

| |Issue|Instances|
|-|:-|:-:|
| [[D&#x2011;01](#d01-storage-write-removal-bug-on-conditional-early-termination)] | ~~Storage Write Removal Bug On Conditional Early Termination~~ | 16 | 
| [[D&#x2011;02](#d02-do-not-calculate-constant-variables-which-will-save-gas)] | ~~Do not calculate `constant` variables, which will save gas~~ | 5 | 
| [[D&#x2011;03](#d03-use-delete-instead-of-setting-mappingstate-variable-to-zero-to-save-gas)] | ~~Use delete instead of setting mapping/state variable to zero, to save gas~~ | 16 | 
| [[D&#x2011;04](#d04-abiencode-is-less-efficient-than-abiencodepacked)] | ~~`abi.encode()` is less efficient than `abi.encodepacked()`~~ | 17 | 
| [[D&#x2011;05](#d05-contracts-do-not-work-with-fee-on-transfer-tokens)] | ~~Contracts do not work with fee-on-transfer tokens~~ | 72 | 
| [[D&#x2011;06](#d06-tokens-may-be-minted-to-address0x0)] | ~~Tokens may be minted to `address(0x0)`~~ | 10 | 
| [[D&#x2011;07](#d07-contracts-are-not-using-their-oz-upgradeable-counterparts)] | ~~Contracts are not using their OZ Upgradeable counterparts~~ | 59 | 
| [[D&#x2011;08](#d08-change-public-function-visibility-to-external-to-save-gas)] | ~~Change `public` function visibility to `external` to save gas~~ | 70 | 
| [[D&#x2011;09](#d09-save-gas-with-the-use-of-specific-import-statements)] | ~~Save gas with the use of specific import statements~~ | 324 | 
| [[D&#x2011;10](#d10-safetransfer-function-does-not-check-for-contract-existence)] | ~~`safeTransfer` function does not check for contract existence~~ | 2 | 
| [[D&#x2011;11](#d11-shorten-the-array-rather-than-copying-to-a-new-one)] | ~~Shorten the array rather than copying to a new one~~ | 7 | 

Total: 598 instances over 11 issues


## Gas Optimizations


### [G&#x2011;01] Reduce gas usage by moving to Solidity 0.8.19 or later
See [this](https://blog.soliditylang.org/2023/02/22/solidity-0.8.19-release-announcement/#preventing-dead-code-in-runtime-bytecode) link for the full details

*There are 68 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: contracts/Penrose.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/Penrose.sol#L2-L2

```solidity
File: contracts/markets/Market.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/Market.sol#L2-L2

```solidity
File: contracts/markets/MarketERC20.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/MarketERC20.sol#L2-L2

```solidity
File: contracts/markets/bigBang/BigBang.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L2-L2

```solidity
File: contracts/markets/singularity/SGLBorrow.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLBorrow.sol#L2-L2

```solidity
File: contracts/markets/singularity/SGLCollateral.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLCollateral.sol#L2-L2

```solidity
File: contracts/markets/singularity/SGLCommon.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol#L2-L2

```solidity
File: contracts/markets/singularity/SGLLendingCommon.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLendingCommon.sol#L2-L2

```solidity
File: contracts/markets/singularity/SGLLeverage.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLeverage.sol#L2-L2

```solidity
File: contracts/markets/singularity/SGLLiquidation.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L2-L2

```solidity
File: contracts/markets/singularity/SGLStorage.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLStorage.sol#L2-L2

```solidity
File: contracts/markets/singularity/Singularity.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L2-L2

```solidity
File: contracts/usd0/BaseUSDO.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDO.sol#L2-L2

```solidity
File: contracts/usd0/BaseUSDOStorage.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDOStorage.sol#L2-L2

```solidity
File: contracts/usd0/USDO.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/USDO.sol#L2-L2

```solidity
File: contracts/usd0/modules/USDOLeverageModule.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol#L2-L2

```solidity
File: contracts/usd0/modules/USDOMarketModule.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOMarketModule.sol#L2-L2

```solidity
File: contracts/usd0/modules/USDOOptionsModule.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOOptionsModule.sol#L2-L2

```solidity
File: contracts/Balancer.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/Balancer.sol#L2-L2

```solidity
File: contracts/TapiocaWrapper.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/TapiocaWrapper.sol#L2-L2

```solidity
File: contracts/tOFT/BaseTOFT.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFT.sol#L2-L2

```solidity
File: contracts/tOFT/BaseTOFTStorage.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFTStorage.sol#L2-L2

```solidity
File: contracts/tOFT/TapiocaOFT.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/TapiocaOFT.sol#L2-L2

```solidity
File: contracts/tOFT/mTapiocaOFT.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol#L2-L2

```solidity
File: contracts/tOFT/modules/BaseTOFTLeverageModule.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol#L2-L2

```solidity
File: contracts/tOFT/modules/BaseTOFTMarketModule.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTMarketModule.sol#L2-L2

```solidity
File: contracts/tOFT/modules/BaseTOFTOptionsModule.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTOptionsModule.sol#L2-L2

```solidity
File: contracts/tOFT/modules/BaseTOFTStrategyModule.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol#L2-L2

```solidity
File: contracts/Vesting.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/Vesting.sol#L2-L2

```solidity
File: contracts/governance/twTAP.sol

2:   pragma solidity 0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L2-L2

```solidity
File: contracts/option-airdrop/AirdropBroker.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L2-L2

```solidity
File: contracts/option-airdrop/aoTAP.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/aoTAP.sol#L2-L2

```solidity
File: contracts/options/TapiocaOptionBroker.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L2-L2

```solidity
File: contracts/options/TapiocaOptionLiquidityProvision.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L2-L2

```solidity
File: contracts/options/oTAP.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/oTAP.sol#L2-L2

```solidity
File: contracts/tokens/BaseTapOFT.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/BaseTapOFT.sol#L2-L2

```solidity
File: contracts/tokens/LTap.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/LTap.sol#L2-L2

```solidity
File: contracts/tokens/TapOFT.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L2-L2

```solidity
File: contracts/twAML.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/twAML.sol#L2-L2

```solidity
File: contracts/Magnetar/MagnetarV2.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol#L2-L2

```solidity
File: contracts/Magnetar/MagnetarV2Storage.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2Storage.sol#L2-L2

```solidity
File: contracts/Magnetar/modules/MagnetarMarketModule.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L2-L2

```solidity
File: contracts/Multicall/Multicall3.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Multicall/Multicall3.sol#L2-L2

```solidity
File: contracts/Swapper/BaseSwapper.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/BaseSwapper.sol#L2-L2

```solidity
File: contracts/Swapper/CurveSwapper.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/CurveSwapper.sol#L2-L2

```solidity
File: contracts/Swapper/UniswapV2Swapper.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/UniswapV2Swapper.sol#L2-L2

```solidity
File: contracts/Swapper/UniswapV3Swapper.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/UniswapV3Swapper.sol#L2-L2

```solidity
File: contracts/TapiocaDeployer/TapiocaDeployer.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/TapiocaDeployer/TapiocaDeployer.sol#L2-L2

```solidity
File: contracts/oracle/Seer.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/Seer.sol#L2-L2

```solidity
File: contracts/oracle/implementations/ARBTriCryptoOracle.sol

2:   pragma solidity ^0.8.9;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/ARBTriCryptoOracle.sol#L2-L2

```solidity
File: contracts/oracle/implementations/GLPOracle.sol

2:   pragma solidity >=0.8.0;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/GLPOracle.sol#L2-L2

```solidity
File: contracts/oracle/implementations/SGOracle.sol

2:   pragma solidity ^0.8.9;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/SGOracle.sol#L2-L2

```solidity
File: contracts/aave/AaveStrategy.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol#L2-L2

```solidity
File: contracts/balancer/BalancerStrategy.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L2-L2

```solidity
File: contracts/compound/CompoundStrategy.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol#L2-L2

```solidity
File: contracts/convex/ConvexTricryptoStrategy.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L2-L2

```solidity
File: contracts/curve/TricryptoLPStrategy.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L2-L2

```solidity
File: contracts/curve/TricryptoNativeStrategy.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L2-L2

```solidity
File: contracts/glp/GlpStrategy.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol#L2-L2

```solidity
File: contracts/lido/LidoEthStrategy.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol#L2-L2

```solidity
File: contracts/stargate/StargateStrategy.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L2-L2

```solidity
File: contracts/yearn/YearnStrategy.sol

2:   pragma solidity ^0.8.18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol#L2-L2

```solidity
File: contracts/BoringMath.sol

2:   pragma solidity ^0.8.9;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/BoringMath.sol#L2-L2

```solidity
File: contracts/NativeTokenFactory.sol

2:   pragma solidity ^0.8.9;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/NativeTokenFactory.sol#L2-L2

```solidity
File: contracts/YieldBox.sol

24:  pragma solidity ^0.8.9;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBox.sol#L24-L24

```solidity
File: contracts/YieldBoxPermit.sol

3:   pragma solidity ^0.8.0;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxPermit.sol#L3-L3

```solidity
File: contracts/YieldBoxRebase.sol

3:   pragma solidity ^0.8.9;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxRebase.sol#L3-L3

```solidity
File: contracts/YieldBoxURIBuilder.sol

2:   pragma solidity ^0.8.9;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxURIBuilder.sol#L2-L2

</details>

### [G&#x2011;02] Using `bool`s for storage incurs overhead
```solidity
    // Booleans are more expensive than uint256 or any type that takes up a full
    // word because each write operation emits an extra SLOAD to first read the
    // slot's contents, replace the bits taken up by the boolean, and then write
    // back. This is the compiler's defense against contract upgrades and
    // pointer aliasing, and it cannot be disabled.
```
https://github.com/OpenZeppelin/openzeppelin-contracts/blob/58f635312aa21f947cae5f8578638a85aa2519f5/contracts/security/ReentrancyGuard.sol#L23-L27
Use `uint256(1)` and `uint256(2)` for true/false to avoid a Gwarmaccess (**[100 gas](https://gist.github.com/IllIllI000/1b70014db712f8572a72378321250058)**) for the extra SLOAD, and to avoid Gsset (**20000 gas**) when changing from `false` to `true`, after having been `true` in the past

*There are 17 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: contracts/Penrose.sol

39:      bool public paused;

61:      mapping(address => bool) public isSingularityMasterContractRegistered;

63:      mapping(address => bool) public isBigBangMasterContractRegistered;

65:      mapping(address => bool) public isMarketRegistered;

71:      mapping(ISwapper => bool) public swappers;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/Penrose.sol#L39-L39

```solidity
File: contracts/markets/Market.sol

35:      bool public paused;

129:     bool internal initialized;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/Market.sol#L35-L35

```solidity
File: contracts/markets/bigBang/BigBang.sol

46:      mapping(address => mapping(address => bool)) public operators;

52:      bool private _isEthMarket;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L46-L46

```solidity
File: contracts/usd0/BaseUSDOStorage.sol

25:      mapping(uint256 => mapping(address => bool)) public allowedMinter;

28:      mapping(uint256 => mapping(address => bool)) public allowedBurner;

30:      bool public paused;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDOStorage.sol#L25-L25

```solidity
File: contracts/tOFT/mTapiocaOFT.sol

17:      mapping(uint256 => bool) public connectedChains;

21:      mapping(address => bool) public balancers;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol#L17-L17

```solidity
File: contracts/option-airdrop/AirdropBroker.sol

61:      mapping(address => mapping(uint256 => bool)) public userParticipation; // user address => phase => participated

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L61-L61

```solidity
File: contracts/tokens/TapOFT.sol

70:      bool public paused;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L70-L70

```solidity
File: contracts/Magnetar/MagnetarV2Storage.sol

29:      mapping(address => mapping(address => bool)) public isApprovedForAll;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2Storage.sol#L29-L29

</details>

### [G&#x2011;03] Avoid updating storage when the value hasn't changed
If the old value is equal to the new value, not re-storing the value will avoid a Gsreset (**2900 gas**), potentially at the expense of a Gcoldsload (**2100 gas**) or a Gwarmaccess (**100 gas**)

*There are 26 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: contracts/Penrose.sol

256      function setBigBangEthMarketDebtRate(uint256 _rate) external onlyOwner {
257          bigBangEthDebtRate = _rate;
258          emit BigBangEthMarketDebtRate(_rate);
259:     }

263      function setBigBangEthMarket(address _market) external onlyOwner {
264          bigBangEthMarket = _market;
265          emit BigBangEthMarketSet(_market);
266:     }

455      function setFeeTo(address feeTo_) external onlyOwner {
456          feeTo = feeTo_;
457          emit FeeToUpdate(feeTo_);
458:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/Penrose.sol#L256-L259

```solidity
File: contracts/markets/Market.sol

142      function setBorrowOpeningFee(uint256 _val) external onlyOwner {
143          require(_val <= FEE_PRECISION, "Market: not valid");
144          emit LogBorrowingFee(borrowOpeningFee, _val);
145          borrowOpeningFee = _val;
146:     }

151      function setBorrowCap(uint256 _cap) external notPaused onlyOwner {
152          emit LogBorrowCapUpdated(totalBorrowCap, _cap);
153          totalBorrowCap = _cap;
154:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/Market.sol#L142-L146

```solidity
File: contracts/markets/singularity/Singularity.sol

489      function setSingularityConfig(
490          uint256 _lqCollateralizationRate,
491          uint256 _liquidationMultiplier,
492          uint256 _minimumTargetUtilization,
493          uint256 _maximumTargetUtilization,
494          uint64 _minimumInterestPerSecond,
495          uint64 _maximumInterestPerSecond,
496          uint256 _interestElasticity
497      ) external onlyOwner {
498          if (_minimumTargetUtilization > 0) {
499              emit MinimumTargetUtilizationUpdated(
500                  minimumTargetUtilization,
501                  _minimumTargetUtilization
502              );
503              minimumTargetUtilization = _minimumTargetUtilization;
504          }
505  
506          if (_maximumTargetUtilization > 0) {
507              require(
508                  _maximumTargetUtilization < FULL_UTILIZATION,
509                  "SGL: not valid"
510              );
511              emit MaximumTargetUtilizationUpdated(
512                  maximumTargetUtilization,
513                  _maximumTargetUtilization
514              );
515              maximumTargetUtilization = _maximumTargetUtilization;
516              fullUtilizationMinusMax =
517                  FULL_UTILIZATION -
518                  maximumTargetUtilization;
519          }
520  
521          if (_minimumInterestPerSecond > 0) {
522              require(
523                  _minimumInterestPerSecond < maximumInterestPerSecond,
524                  "SGL: not valid"
525              );
526              emit MinimumInterestPerSecondUpdated(
527                  minimumInterestPerSecond,
528                  _minimumInterestPerSecond
529              );
530              minimumInterestPerSecond = _minimumInterestPerSecond;
531          }
532  
533          if (_maximumInterestPerSecond > 0) {
534              require(
535                  _maximumInterestPerSecond > minimumInterestPerSecond,
536                  "SGL: not valid"
537              );
538              emit MaximumInterestPerSecondUpdated(
539                  maximumInterestPerSecond,
540                  _maximumInterestPerSecond
541              );
542              maximumInterestPerSecond = _maximumInterestPerSecond;
543          }
544  
545          if (_interestElasticity > 0) {
546              emit InterestElasticityUpdated(
547                  interestElasticity,
548                  _interestElasticity
549              );
550              interestElasticity = _interestElasticity;
551          }
552  
553          if (_lqCollateralizationRate > 0) {
554              require(
555                  _lqCollateralizationRate <= FEE_PRECISION,
556                  "SGL: not valid"
557              );
558              emit LqCollateralizationRateUpdated(
559                  lqCollateralizationRate,
560                  _lqCollateralizationRate
561              );
562              lqCollateralizationRate = _lqCollateralizationRate;
563          }
564  
565          if (_liquidationMultiplier > 0) {
566              require(_liquidationMultiplier < FEE_PRECISION, "SGL: not valid");
567              emit LiquidationMultiplierUpdated(
568                  liquidationMultiplier,
569                  _liquidationMultiplier
570              );
571              liquidationMultiplier = _liquidationMultiplier;
572          }
573:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L489-L573

```solidity
File: contracts/usd0/BaseUSDO.sol

88       function setMaxFlashMintable(uint256 _val) external onlyOwner {
89           emit MaxFlashMintUpdated(maxFlashMint, _val);
90           maxFlashMint = _val;
91:      }

96       function setFlashMintFee(uint256 _val) external onlyOwner {
97           require(_val < FLASH_MINT_FEE_PRECISION, "USDO: fee too big");
98           emit FlashMintFeeUpdated(flashMintFee, _val);
99           flashMintFee = _val;
100:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDO.sol#L88-L91

```solidity
File: contracts/option-airdrop/AirdropBroker.sol

308      function setTapOracle(
309          IOracle _tapOracle,
310          bytes calldata _tapOracleData
311      ) external onlyOwner {
312          tapOracle = _tapOracle;
313          tapOracleData = _tapOracleData;
314  
315          emit SetTapOracle(_tapOracle, _tapOracleData);
316:     }

318      function setPhase2MerkleRoots(
319          bytes32[4] calldata _merkleRoots
320      ) external onlyOwner {
321          phase2MerkleRoots = _merkleRoots;
322:     }

357      function setPaymentTokenBeneficiary(
358          address _paymentTokenBeneficiary
359      ) external onlyOwner {
360          paymentTokenBeneficiary = _paymentTokenBeneficiary;
361:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L308-L316

```solidity
File: contracts/options/TapiocaOptionBroker.sol

446      function setTapOracle(
447          IOracle _tapOracle,
448          bytes calldata _tapOracleData
449      ) external onlyOwner {
450          tapOracle = _tapOracle;
451          tapOracleData = _tapOracleData;
452  
453          emit SetTapOracle(_tapOracle, _tapOracleData);
454:     }

471      function setPaymentTokenBeneficiary(
472          address _paymentTokenBeneficiary
473      ) external onlyOwner {
474          paymentTokenBeneficiary = _paymentTokenBeneficiary;
475:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L446-L454

```solidity
File: contracts/tokens/LTap.sol

53       function setLockedUntil(uint256 _lockedUntil) external onlyOwner {
54           require(_lockedUntil <= maxLockedUntil, "Too late");
55           lockedUntil = _lockedUntil;
56:      }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/LTap.sol#L53-L56

```solidity
File: contracts/tokens/TapOFT.sol

140      function setGovernanceChainIdentifier(
141          uint256 _identifier
142      ) external onlyOwner {
143          emit GovernanceChainIdentifierUpdated(
144              governanceChainIdentifier,
145              _identifier
146          );
147          governanceChainIdentifier = _identifier;
148:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L140-L148

```solidity
File: contracts/Swapper/UniswapV3Swapper.sol

61       function setPoolFee(uint24 _newFee) external onlyOwner {
62           emit PoolFee(poolFee, _newFee);
63           poolFee = _newFee;
64:      }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/UniswapV3Swapper.sol#L61-L64

```solidity
File: contracts/aave/AaveStrategy.sol

122      function setDepositThreshold(uint256 amount) external onlyOwner {
123          emit DepositThreshold(depositThreshold, amount);
124          depositThreshold = amount;
125:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol#L122-L125

```solidity
File: contracts/balancer/BalancerStrategy.sol

109      function setDepositThreshold(uint256 amount) external onlyOwner {
110          emit DepositThreshold(depositThreshold, amount);
111          depositThreshold = amount;
112:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L109-L112

```solidity
File: contracts/compound/CompoundStrategy.sol

89       function setDepositThreshold(uint256 amount) external onlyOwner {
90           emit DepositThreshold(depositThreshold, amount);
91           depositThreshold = amount;
92:      }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol#L89-L92

```solidity
File: contracts/convex/ConvexTricryptoStrategy.sol

163      function setDepositThreshold(uint256 amount) external onlyOwner {
164          emit DepositThreshold(depositThreshold, amount);
165          depositThreshold = amount;
166:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L163-L166

```solidity
File: contracts/curve/TricryptoLPStrategy.sol

134      function setDepositThreshold(uint256 amount) external onlyOwner {
135          emit DepositThreshold(depositThreshold, amount);
136          depositThreshold = amount;
137:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L134-L137

```solidity
File: contracts/curve/TricryptoNativeStrategy.sol

125      function setDepositThreshold(uint256 amount) external onlyOwner {
126          emit DepositThreshold(depositThreshold, amount);
127          depositThreshold = amount;
128:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L125-L128

```solidity
File: contracts/glp/GlpStrategy.sol

113      function setFeeRecipient(address recipient) external onlyOwner {
114          feeRecipient = recipient;
115:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol#L113-L115

```solidity
File: contracts/lido/LidoEthStrategy.sol

93       function setDepositThreshold(uint256 amount) external onlyOwner {
94           emit DepositThreshold(depositThreshold, amount);
95           depositThreshold = amount;
96:      }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol#L93-L96

```solidity
File: contracts/stargate/StargateStrategy.sol

142      function setDepositThreshold(uint256 amount) external onlyOwner {
143          emit DepositThreshold(depositThreshold, amount);
144          depositThreshold = amount;
145:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L142-L145

```solidity
File: contracts/yearn/YearnStrategy.sol

90       function setDepositThreshold(uint256 amount) external onlyOwner {
91           emit DepositThreshold(depositThreshold, amount);
92           depositThreshold = amount;
93:      }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol#L90-L93

</details>

### [G&#x2011;04] `unchecked {}`  can be used on the division of two `uint`s in order to save gas
The division cannot overflow, since both the numerator and the denominator are non-negative

*There are 76 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: contracts/markets/Market.sol

265:             borrowPartScaled = borrowPart / (10 ** (borrowPartDecimals - 18));

274                  collateralPartInAsset /
275:                 (10 ** (collateralPartDecimals - 18));

283          uint256 liquidationStartsAt = (collateralPartInAssetScaled *
284:             collateralizationRate) / (10 ** ratesPrecision);

288              ((collateralizationRate * collateralPartInAssetScaled) /
289:                 (10 ** ratesPrecision));

291              (collateralizationRate *
292                  ((10 ** ratesPrecision) + liquidationMultiplier)) /
293:             (10 ** ratesPrecision)) * (10 ** (18 - ratesPrecision));

295:         uint256 x = (numerator * 1e18) / denominator;

390              yieldBox.toAmount(
391                  collateralId,
392                  (userCollateralShare[user] *
393                      (EXCHANGE_RATE_PRECISION / FEE_PRECISION) *
394                      collateralizationRate),
395                  false
396              ) /
397:             _exchangeRate;

393:                     (EXCHANGE_RATE_PRECISION / FEE_PRECISION) *

418:                     (EXCHANGE_RATE_PRECISION / FEE_PRECISION) *

438:         max = (collateralAmount * EXCHANGE_RATE_PRECISION) / _exchangeRate;

439:         min = (max * collateralizationRate) / FEE_PRECISION;

453          uint256 rewardPercentage = ((borrowed - startTVLInAsset) *
454:             FEE_PRECISION) / (maxTVLInAsset - startTVLInAsset);

477:         return (shareRatio * userCollateralShare[user]) / (10 ** assetDecimals);

489:         uint256 _quotient = ((_numerator / denominator) + 5) / 10;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/Market.sol#L265-L265

```solidity
File: contracts/markets/bigBang/BigBang.sol

192          uint256 debtPercentage = ((_currentDebt - debtStartPoint) *
193:             DEBT_PRECISION) / (_maxDebtPoint - debtStartPoint);

194          uint256 debt = ((maxDebtRate - minDebtRate) * debtPercentage) /
195:             DEBT_PRECISION +

645:         feeShare = (extraShare * protocolFee) / FEE_PRECISION; // x% of profit goes to fee.

646:         callerShare = (extraShare * callerReward) / FEE_PRECISION; //  y%  of profit goes to caller.

747:         uint256 feeAmount = (amount * borrowOpeningFee) / FEE_PRECISION; // A flat % fee is charged for any borrow

781          uint256 collateralPartInAsset = (yieldBox.toAmount(
782              collateralId,
783              userCollateralShare[user],
784              false
785:         ) * EXCHANGE_RATE_PRECISION) / _exchangeRate;

809              (borrowAmount * liquidationMultiplier) /
810:             FEE_PRECISION;

813:             (amountWithBonus * _exchangeRate) / EXCHANGE_RATE_PRECISION,

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L192-L193

```solidity
File: contracts/markets/singularity/SGLCommon.sol

63               : (uint256(_totalBorrow.elastic) * UTILIZATION_PRECISION) /
64:                  fullAssetAmount;

106:         uint256 feeAmount = (extraAmount * protocolFee) / FEE_PRECISION; // % of interest paid goes to fee

107:         feeFraction = (feeAmount * _totalAsset.base) / fullAssetAmount;

125              uint256 overFactor = ((utilization - maximumTargetUtilization) *
126:                 FACTOR_PRECISION) / fullUtilizationMinusMax;

129              uint256 newInterestPerSecond = (uint256(
130                  _accrueInfo.interestPerSecond
131:             ) * scale) / interestElasticity;

113              uint256 underFactor = ((minimumTargetUtilization - utilization) *
114:                 FACTOR_PRECISION) / minimumTargetUtilization;

118                  (uint256(_accrueInfo.interestPerSecond) * interestElasticity) /
119:                     scale

209:             : (share * _totalAsset.base) / allShare;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol#L63-L64

```solidity
File: contracts/markets/singularity/SGLLendingCommon.sol

63:          uint256 feeAmount = (amount * borrowOpeningFee) / FEE_PRECISION; // A flat % fee is charged for any borrow

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLendingCommon.sol#L63-L63

```solidity
File: contracts/markets/singularity/SGLLiquidation.sol

81           uint256 collateralAmountInAsset = yieldBox.toAmount(
82               collateralId,
83               (collateralShare *
84                   (EXCHANGE_RATE_PRECISION / FEE_PRECISION) *
85                   lqCollateralizationRate),
86               false
87:          ) / _exchangeRate;

84:                  (EXCHANGE_RATE_PRECISION / FEE_PRECISION) *

126                      (borrowAmount * liquidationMultiplier) /
127:                     FEE_PRECISION;

130:                     (amountWithBonus * _exchangeRate) / EXCHANGE_RATE_PRECISION,

182:         uint256 callerShare = (extraShare * callerFee) / FEE_PRECISION; // 1% goes to caller

216          uint256 collateralPartInAsset = (yieldBox.toAmount(
217              collateralId,
218              userCollateralShare[user],
219              false
220:         ) * EXCHANGE_RATE_PRECISION) / _exchangeRate;

236                  (availableBorrowPart * liquidationBonusAmount) /
237:                 FEE_PRECISION;

253              (borrowAmount * liquidationMultiplier) /
254:             FEE_PRECISION;

257:             (amountWithBonus * _exchangeRate) / EXCHANGE_RATE_PRECISION,

278:         feeShare = (extraShare * protocolFee) / FEE_PRECISION; // x% of profit goes to fee.

279:         callerShare = (extraShare * callerReward) / FEE_PRECISION; //  y%  of profit goes to caller.

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L81-L87

```solidity
File: contracts/usd0/USDO.sol

69:          return (amount * flashMintFee) / FLASH_MINT_FEE_PRECISION;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/USDO.sol#L69-L69

```solidity
File: contracts/Balancer.sol

339:         return _amount - ((_amount * _slippage) / SLIPPAGE_PRECISION);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/Balancer.sol#L339-L339

```solidity
File: contracts/Vesting.sol

172:         return (total * (block.timestamp - start)) / duration;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/Vesting.sol#L172-L172

```solidity
File: contracts/governance/twTAP.sol

151:         return (block.timestamp - creation) / EPOCH_DURATION;

236:             result[i] = ((votes * net) / DIST_PRECISION) - claimed[_tokenId][i];

280                  (pool.averageMagnitude + magnitude) /
281:                 pool.totalParticipants; // compute new average magnitude

323:         uint256 w1 = (expiry - creation) / EPOCH_DURATION;

446              (_amount * DIST_PRECISION) /
447:             uint256(totals.netActiveVotes);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L151-L151

```solidity
File: contracts/option-airdrop/AirdropBroker.sol

530:         uint256 rawPaymentAmount = _otcAmountInUSD / _paymentTokenValuation;

535:         paymentAmount = paymentAmount / (10 ** (18 - _paymentTokenDecimals));

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L530-L530

```solidity
File: contracts/options/TapiocaOptionBroker.sol

245                  (pool.averageMagnitude + magnitude) /
246:                 pool.totalParticipants; // compute new average magnitude

551:         uint256 rawPaymentAmount = _otcAmountInUSD / _paymentTokenValuation;

555:         paymentAmount = paymentAmount / (10 ** (18 - _paymentTokenDecimals));

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L245-L246

```solidity
File: contracts/tokens/TapOFT.sol

242:         return ((timestamp - emissionsStartTime) / WEEK) + 1; // Starts at week 1

254:         result = (dso_supply * decay_rate) / DECAY_RATE_DECIMAL;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L242-L242

```solidity
File: contracts/twAML.sol

141:         uint256 target = (_magnitude * _dMax) / _cumulative;

153:                 x = (y / x + x) / 2;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/twAML.sol#L141-L141

```solidity
File: contracts/Magnetar/MagnetarV2.sol

105                  (borrowAmount *
106                      market.liquidationMultiplier() *
107                      market.exchangeRate()) /
108:                     (liquidationMultiplierPrecision * exchangeRatePrecision),

186:         fraction = allShare == 0 ? share : (share * totalAssetBase) / allShare;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol#L105-L108

```solidity
File: contracts/oracle/implementations/ARBTriCryptoOracle.sol

135:         uint256 _g = (TRI_CRYPTO.gamma() * 1 ether) / GAMMA0;

136:         uint256 _a = (TRI_CRYPTO.A() * 1 ether) / A0;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/ARBTriCryptoOracle.sol#L135-L135

```solidity
File: contracts/oracle/implementations/SGOracle.sol

50           uint256 lpPrice = (SG_POOL.totalLiquidity() *
51:              uint256(UNDERLYING.latestAnswer())) / SG_POOL.totalSupply();

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/SGOracle.sol#L50-L51

```solidity
File: contracts/balancer/BalancerStrategy.sol

202              uint256 toWithdraw = (((amount - queued) * (10 ** decimals)) /
203:                 pricePerShare);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L202-L203

```solidity
File: contracts/compound/CompoundStrategy.sol

146              uint256 toWithdraw = (((amount - queued) * (10 ** 18)) /
147:                 pricePerShare);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol#L146-L147

```solidity
File: contracts/glp/GlpStrategy.sol

207          uint256 minTokenReserve = ((vestingNow + vestable) * avgTokenStake) /
208:             totalVestable;

244                  (totalVestable * tokenAvailable) /
245:                 avgTokenStake -

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol#L207-L208

```solidity
File: contracts/yearn/YearnStrategy.sol

114:         uint256 invested = (shares * pricePerShare) / (10 ** vault.decimals());

142              uint256 toWithdraw = (((amount - queued) *
143:                 (10 ** vault.decimals())) / pricePerShare);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol#L114-L114

```solidity
File: contracts/BoringMath.sol

26:          result = (value * mul) / div;

27:          if (roundUp && (result * div) / mul < value) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/BoringMath.sol#L26-L26

```solidity
File: contracts/YieldBoxRebase.sol

32:          share = (amount * totalShares_) / totalAmount;

35:          if (roundUp && (share * totalAmount) / totalShares_ < amount) {

55:          amount = (share * totalAmount) / totalShares_;

58:          if (roundUp && (amount * totalShares_) / totalAmount < share) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxRebase.sol#L32-L32

</details>

### [G&#x2011;05] Remove or replace unused state variables
Saves a storage slot. If the variable is assigned a non-zero value, saves Gsset (**20000 gas**). If it's assigned a zero value, saves Gsreset (**2900 gas**). If the variable remains unassigned, there is no gas savings unless the variable is `public`, in which case the compiler-generated non-payable getter deployment cost is saved. If the state variable is overriding an interface's public function, mark the variable as `constant` or `immutable` so that it does not use a storage slot

*There are 3 instances of this issue:*

```solidity
File: tapioca-bar-audit/contracts/markets/MarketERC20.sol

45:       bytes32 private _PERMIT_TYPEHASH_DEPRECATED_SLOT;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/MarketERC20.sol#L45

```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

112:      string private baseURI;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L112

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol

41:       address[] public rewardTokens;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L41


### [G&#x2011;06] Multiple `address`/ID mappings can be combined into a single `mapping` of an `address`/ID to a `struct`, where appropriate
Saves a storage slot for the mapping. Depending on the circumstances and sizes of types, can avoid a Gsset (**20000 gas**) per mapping combined. Reads and subsequent writes can also be cheaper when a function requires both values and they both fit in the same storage slot. Finally, if both fields are accessed in the same function, can save **~42 gas per access** due to [not having to recalculate the key's keccak256 hash](https://gist.github.com/IllIllI000/ec23a57daa30a8f8ca8b9681c8ccefb0) (Gkeccak256 - 30 gas) and that calculation's associated stack operations.

*There are 10 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: tapioca-bar-audit/contracts/markets/MarketERC20.sol

48        mapping(address => uint256) public override balanceOf;
49        /// @notice owner > spender > allowance mapping.
50        mapping(address => mapping(address => uint256)) public override allowance;
51        /// @notice owner > spender > allowance mapping.
52        mapping(address => mapping(address => uint256)) public allowanceBorrow;
53        /// @notice owner > nonce mapping. Used in `permit`.
54:       mapping(address => uint256) private _nonces;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/MarketERC20.sol#L48-L54

```solidity
File: tapioca-bar-audit/contracts/markets/Market.sol

57        mapping(address => uint256) public userBorrowPart;
58        /// @notice collateral share per user
59:       mapping(address => uint256) public userCollateralShare;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/Market.sol#L57-L59

```solidity
File: tapioca-bar-audit/contracts/Penrose.sol

61        mapping(address => bool) public isSingularityMasterContractRegistered;
62        // Used to check if a BigBang master contract is registered
63        mapping(address => bool) public isBigBangMasterContractRegistered;
64        // Used to check if a SGL/BB is a real market
65:       mapping(address => bool) public isMarketRegistered;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/Penrose.sol#L61-L65

```solidity
File: tapioca-bar-audit/contracts/usd0/BaseUSDOStorage.sol

25        mapping(uint256 => mapping(address => bool)) public allowedMinter;
26        /// @notice addresses allowed to burn USDO
27        /// @dev chainId>address>status
28:       mapping(uint256 => mapping(address => bool)) public allowedBurner;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDOStorage.sol#L25-L28

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

57        mapping(uint256 => mapping(uint256 => uint256)) public aoTAPCalls; // oTAPTokenID => epoch => amountExercised
58    
59        /// @notice Record of participation in phase 2 airdrop
60        /// Only applicable for phase 2. To get subphases on phase 2 we do userParticipation[_user][20+roles]
61        mapping(address => mapping(uint256 => bool)) public userParticipation; // user address => phase => participated
62    
63        /// =====-------======
64        ///      Phase 1
65        /// =====-------======
66    
67        /// @notice user address => eligible TAP amount, 0 means no eligibility
68:       mapping(address => uint256) public phase1Users;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L57-L68

```solidity
File: tap-token-audit/contracts/option-airdrop/aoTAP.sol

36        mapping(uint256 => AirdropTapOption) public options; // tokenId => Option
37:       mapping(uint256 => string) public tokenURIs; // tokenId => tokenURI

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/aoTAP.sol#L36-L37

```solidity
File: tap-token-audit/contracts/options/oTAP.sol

34        mapping(uint256 => TapOption) public options; // tokenId => Option
35:       mapping(uint256 => string) public tokenURIs; // tokenId => tokenURI

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/oTAP.sol#L34-L35

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionBroker.sol

64        mapping(uint256 => Participation) public participants; // tOLPTokenID => Participation
65        mapping(uint256 => mapping(uint256 => uint256)) public oTAPCalls; // oTAPTokenID => epoch => amountExercised
66    
67:       mapping(uint256 => mapping(uint256 => uint256)) public singularityGauges; // epoch => sglAssetId => availableTAP

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L64-L67

```solidity
File: tap-token-audit/contracts/tokens/TapOFT.sol

57        mapping(uint256 => uint256) public emissionForWeek;
58    
59        /// @notice returns the amount minted for a specific week
60        /// @dev week is computed using (timestamp - emissionStartTime) / WEEK
61:       mapping(uint256 => uint256) public mintedInWeek;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L57-L61

```solidity
File: YieldBox/contracts/NativeTokenFactory.sol

24        mapping(uint256 => NativeToken) public nativeTokens;
25        mapping(uint256 => address) public owner;
26:       mapping(uint256 => address) public pendingOwner;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/NativeTokenFactory.sol#L24-L26

</details>

### [G&#x2011;07] State variables only set in the constructor should be declared `immutable`
Avoids a Gsset (**20000 gas**) in the constructor, and replaces the first access in each transaction (Gcoldsload - **2100 gas**) and each access thereafter (Gwarmacces - **100 gas**) with a `PUSH32` (**3 gas**). 

While `string`s are not value types, and therefore cannot be `immutable`/`constant` if not hard-coded outside of the constructor, the same behavior can be achieved by making the current contract `abstract` with `virtual` functions for the `string` accessors, and having a child contract override the functions with the hard-coded implementation-specific values.

*There are 27 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: tapioca-bar-audit/contracts/usd0/BaseUSDO.sol

/// @audit leverageModule (constructor)
75:           leverageModule = USDOLeverageModule(_leverageModule);

/// @audit marketModule (constructor)
76:           marketModule = USDOMarketModule(_marketModule);

/// @audit optionsModule (constructor)
77:           optionsModule = USDOOptionsModule(_optionsModule);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDO.sol#L75

```solidity
File: tapiocaz-audit/contracts/tOFT/BaseTOFT.sol

/// @audit leverageModule (constructor)
74:           leverageModule = BaseTOFTLeverageModule(_leverageModule);

/// @audit strategyModule (constructor)
75:           strategyModule = BaseTOFTStrategyModule(_strategyModule);

/// @audit marketModule (constructor)
76:           marketModule = BaseTOFTMarketModule(_marketModule);

/// @audit optionsModule (constructor)
77:           optionsModule = BaseTOFTOptionsModule(_optionsModule);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFT.sol#L74

```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

/// @audit creation (constructor)
127:          creation = block.timestamp;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L127

```solidity
File: tap-token-audit/contracts/tokens/LTap.sol

/// @audit tapToken (constructor)
36:           tapToken = _tapToken;

/// @audit maxLockedUntil (constructor)
38:           maxLockedUntil = _maxLockedUntil;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/LTap.sol#L36

```solidity
File: tap-token-audit/contracts/Vesting.sol

/// @audit cliff (constructor)
70:           cliff = _cliff;

/// @audit duration (constructor)
71:           duration = _duration;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/Vesting.sol#L70

```solidity
File: tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol

/// @audit marketModule (constructor)
46:           marketModule = MagnetarMarketModule(_marketModule);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol#L46

```solidity
File: tapioca-periph-audit/contracts/oracle/implementations/ARBTriCryptoOracle.sol

/// @audit _name (constructor)
53:           _name = __name;

/// @audit _symbol (constructor)
54:           _symbol = __symbol;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/ARBTriCryptoOracle.sol#L53

```solidity
File: tapioca-periph-audit/contracts/oracle/implementations/SGOracle.sol

/// @audit _name (constructor)
36:           _name = __name;

/// @audit _symbol (constructor)
37:           _symbol = __symbol;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/SGOracle.sol#L36

```solidity
File: tapioca-periph-audit/contracts/oracle/Seer.sol

/// @audit _name (constructor)
42:           _name = __name;

/// @audit _symbol (constructor)
43:           _symbol = __symbol;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/Seer.sol#L42

```solidity
File: tapioca-periph-audit/contracts/Swapper/CurveSwapper.sol

/// @audit curvePool (constructor)
40:           curvePool = _curvePool;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/CurveSwapper.sol#L40

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol

/// @audit poolId (constructor)
70:           poolId = _poolId;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L70

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol

/// @audit curveStEthPool (constructor)
60:           curveStEthPool = ICurveEthStEthPool(_curvePool);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol#L60

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol

/// @audit stgEthPool (constructor)
79:           stgEthPool = _stgEthPool;

/// @audit lpStakingPid (constructor)
83:           lpStakingPid = _stakingPid;

/// @audit lpRouterPid (constructor)
86:           lpRouterPid = addLiquidityRouter.poolId();

/// @audit stgNative (constructor)
88:           stgNative = IERC20(_lpToken);

/// @audit stgTokenReward (constructor)
92:           stgTokenReward = IERC20(lpStaking.stargate());

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L79

</details>

### [G&#x2011;08] State variables can be packed into fewer storage slots
If variables occupying the same slot are both written the same function or by the constructor, avoids a separate Gsset (**20000 gas**). Reads of the variables can also be cheaper

*There are 6 instances of this issue:*

```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

/// @audit Variable ordering with 7 slots instead of the current 8:
///           mapping(32):operators, uint256(32):totalFees, uint256(32):maxDebtRate, uint256(32):minDebtRate, uint256(32):debtRateAgainstEthMarket, uint256(32):debtStartPoint, user-defined(20):accrueInfo, bool(1):_isEthMarket
46:       mapping(address => mapping(address => bool)) public operators;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L46

```solidity
File: tapioca-bar-audit/contracts/markets/Market.sol

/// @audit Variable ordering with 24 slots instead of the current 25:
///           uint256(32):collateralId, uint256(32):assetId, bytes(32):oracleData, uint256(32):exchangeRate, uint256(32):totalCollateralShare, uint256(32):totalBorrowCap, mapping(32):userBorrowPart, mapping(32):userCollateralShare, uint256(32):callerFee, uint256(32):protocolFee, uint256(32):minLiquidatorReward, uint256(32):maxLiquidatorReward, uint256(32):liquidationBonusAmount, uint256(32):collateralizationRate, uint256(32):borrowOpeningFee, uint256(32):liquidationMultiplier, uint256(32):EXCHANGE_RATE_PRECISION, user-defined(20):yieldBox, bool(1):paused, bool(1):initialized, user-defined(20):penrose, user-defined(20):collateral, user-defined(20):asset, address(20):conservator, user-defined(20):oracle, user-defined(20):totalBorrow
21:       YieldBox public yieldBox;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/Market.sol#L21

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLStorage.sol

/// @audit Variable ordering with 11 slots instead of the current 13:
///           mapping(32):_yieldBoxShares, bytes32(32):ASSET_SIG, bytes32(32):COLLATERAL_SIG, uint256(32):lqCollateralizationRate, uint256(32):minimumTargetUtilization, uint256(32):maximumTargetUtilization, uint256(32):fullUtilizationMinusMax, uint256(32):interestElasticity, user-defined(20):accrueInfo, uint64(8):minimumInterestPerSecond, user-defined(20):totalAsset, uint64(8):maximumInterestPerSecond, user-defined(20):liquidationQueue, uint64(8):startingInterestPerSecond
42:       ISingularity.AccrueInfo public accrueInfo;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLStorage.sol#L42

```solidity
File: tapioca-bar-audit/contracts/usd0/BaseUSDOStorage.sol

/// @audit Variable ordering with 5 slots instead of the current 6:
///           mapping(32):allowedMinter, mapping(32):allowedBurner, uint256(32):flashMintFee, uint256(32):maxFlashMint, address(20):conservator, bool(1):paused
22:       address public conservator;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDOStorage.sol#L22

```solidity
File: tapiocaz-audit/contracts/tOFT/BaseTOFTStorage.sol

/// @audit Variable ordering with 3 slots instead of the current 4:
///           uint256(32):hostChainID, user-defined(20):yieldBox, uint8(1):_decimalCache, address(20):erc20
26:       IYieldBoxBase public yieldBox;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFTStorage.sol#L26

```solidity
File: tap-token-audit/contracts/tokens/TapOFT.sol

/// @audit Variable ordering with 5 slots instead of the current 6:
///           uint256(32):dso_supply, mapping(32):emissionForWeek, mapping(32):mintedInWeek, uint256(32):governanceChainIdentifier, address(20):minter, bool(1):paused
42:       uint256 public dso_supply = 53_313_405 * 1e18;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L42


### [G&#x2011;09] Using `storage` instead of `memory` for structs/arrays saves gas
When fetching data from a storage location, assigning the data to a `memory` variable causes all fields of the struct/array to be read from storage, which incurs a Gcoldsload (**2100 gas**) for *each* field of the struct/array. If the fields are read from the new memory variable, they incur an additional `MLOAD` rather than a cheap stack read. Instead of declearing the variable with the `memory` keyword, declaring the variable with the `storage` keyword and caching any fields that need to be re-read in stack variables, will be much cheaper, only incuring the Gcoldsload for the fields actually read. The only time it makes sense to read the whole struct/array into a `memory` variable, is if the full struct/array is being returned by the function, is being passed to a function that requires `memory`, or if the array/struct is being read from another `memory` array/struct

*There are 18 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

513:          IBigBang.AccrueInfo memory _accrueInfo = accrueInfo;

525:          Rebase memory _totalBorrow = totalBorrow;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L513

```solidity
File: tapioca-bar-audit/contracts/markets/Market.sol

316:          Rebase memory _totalBorrow = totalBorrow;

412:          Rebase memory _totalBorrow = totalBorrow;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/Market.sol#L316

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol

203:          Rebase memory _totalAsset = totalAsset;

232:          Rebase memory _totalAsset = totalAsset;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol#L203

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLLendingCommon.sol

74:           Rebase memory _totalAsset = totalAsset;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLendingCommon.sol#L74

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol

79:           Rebase memory _totalBorrow = totalBorrow;

105:          Rebase memory _totalBorrow = totalBorrow;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L79

```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

263:          TWAMLPool memory pool = twAML;

536:              TWAMLPool memory pool = twAML;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L263

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionBroker.sol

222:          TWAMLPool memory pool = twAML[lock.sglAssetID];

308:          Participation memory participation = participants[oTAPPosition.tOLP];

312:              TWAMLPool memory pool = twAML[lock.sglAssetID];

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L222

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol

131:          uint256[] memory _singularities = singularities;

304:              uint256[] memory _singularities = singularities;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L131

```solidity
File: tapioca-periph-audit/contracts/Multicall/Multicall3.sol

48:               Result memory result = returnData[i];

71:               Result memory result = returnData[i];

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Multicall/Multicall3.sol#L48

</details>

### [G&#x2011;10] State variables should be cached in stack variables rather than re-reading them from storage
The instances below point to the second+ access of a state variable within a function. Caching of a state variable replaces each Gwarmaccess (**100 gas**) with a much cheaper stack read. Other less obvious fixes/optimizations include having local memory caches of state variable structs, or having local caches of state variable contracts/addresses.

*There are 156 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

/// @audit totalFees on line 446
447:          feeShares = yieldBox.toShare(assetId, totalFees, false);

/// @audit totalFees on line 447
449:          if (totalFees > 0) {

/// @audit totalFees on line 449
450:              asset.approve(address(yieldBox), totalFees);

/// @audit totalFees on line 450
456:                  totalFees,

/// @audit _isEthMarket on line 156
157:          if (!_isEthMarket) {

/// @audit _isEthMarket on line 472
474:          if (!_isEthMarket) {

/// @audit maxDebtRate on line 190
194:          uint256 debt = ((maxDebtRate - minDebtRate) * debtPercentage) /

/// @audit maxDebtRate on line 194
/// @audit maxDebtRate on line 198
198:          if (debt > maxDebtRate) return maxDebtRate;

/// @audit maxDebtRate on line 476
483:                  emit MaxDebtRateUpdated(maxDebtRate, _maxDebtRate);

/// @audit minDebtRate on line 182
194:          uint256 debt = ((maxDebtRate - minDebtRate) * debtPercentage) /

/// @audit minDebtRate on line 194
196:              minDebtRate;

/// @audit minDebtRate on line 478
482:                  require(_maxDebtRate > minDebtRate, "BigBang: not valid");

/// @audit debtStartPoint on line 192
193:              DEBT_PRECISION) / (_maxDebtPoint - debtStartPoint);

/// @audit yieldBox on line 347
349:              yieldBox.transfer(from, address(swapper), assetId, supplyShare);

/// @audit yieldBox on line 447
450:              asset.approve(address(yieldBox), totalFees);

/// @audit yieldBox on line 450
452:              yieldBox.depositAsset(

/// @audit yieldBox on line 551
557:          emit LogAddCollateral(skim ? address(yieldBox) : from, to, share);

/// @audit yieldBox on line 590
596:          yieldBox.transfer(

/// @audit yieldBox on line 596
608:          uint256 balanceBefore = yieldBox.balanceOf(address(this), assetId);

/// @audit yieldBox on line 608
619:          uint256 balanceAfter = yieldBox.balanceOf(address(this), assetId);

/// @audit yieldBox on line 648
649:          yieldBox.transfer(address(this), msg.sender, assetId, callerShare);

/// @audit yieldBox on line 700
704:              yieldBox.transfer(from, address(this), _tokenId, share);

/// @audit yieldBox on line 761
762:          yieldBox.depositAsset(assetId, address(this), to, amount, 0);

/// @audit yieldBox on line 762
764:          share = yieldBox.toShare(assetId, amount, false);

/// @audit yieldBox on line 781
811:          collateralShare = yieldBox.toShare(

/// @audit penrose on line 127
129:          owner = address(penrose);

/// @audit penrose on line 129
131:          address _asset = penrose.usdoToken();

/// @audit penrose on line 131
141:          assetId = penrose.usdoAssetId();

/// @audit penrose on line 141
156:          _isEthMarket = collateralId == penrose.wethAssetId();

/// @audit penrose on line 181
184:          uint256 _ethMarketTotalDebt = BigBang(penrose.bigBangEthMarket())

/// @audit collateralId on line 143
156:          _isEthMarket = collateralId == penrose.wethAssetId();

/// @audit collateralId on line 551
556:          _addTokens(from, collateralId, share, oldTotalCollateralShare, skim);

/// @audit collateralId on line 599
611:              collateralId,

/// @audit collateralId on line 782
812:              collateralId,

/// @audit asset on line 445
450:              asset.approve(address(yieldBox), totalFees);

/// @audit asset on line 758
761:          asset.approve(address(yieldBox), amount);

/// @audit assetId on line 347
349:              yieldBox.transfer(from, address(swapper), assetId, supplyShare);

/// @audit assetId on line 349
356:              assetId,

/// @audit assetId on line 397
416:          uint256 shareOwed = yieldBox.toShare(assetId, amountOwed, true);

/// @audit assetId on line 447
453:                  assetId,

/// @audit assetId on line 590
608:          uint256 balanceBefore = yieldBox.balanceOf(address(this), assetId);

/// @audit assetId on line 608
612:              assetId,

/// @audit assetId on line 612
619:          uint256 balanceAfter = yieldBox.balanceOf(address(this), assetId);

/// @audit assetId on line 648
649:          yieldBox.transfer(address(this), msg.sender, assetId, callerShare);

/// @audit assetId on line 762
764:          share = yieldBox.toShare(assetId, amount, false);

/// @audit totalBorrow on line 182
186:          uint256 _currentDebt = totalBorrow.elastic;

/// @audit totalBorrow on line 415
421:              uint256 partOut = totalBorrow.toBase(amountOut, false);

/// @audit totalBorrow on line 726
726:          (totalBorrow, amount) = totalBorrow.sub(part, true);

/// @audit totalBorrow on line 749
749:          (totalBorrow, part) = totalBorrow.add(amount + feeAmount, true);

/// @audit totalBorrow on line 749
751:              totalBorrowCap == 0 || totalBorrow.elastic <= totalBorrowCap,

/// @audit totalBorrow on line 807
822:          totalBorrow.elastic -= uint128(borrowAmount);

/// @audit totalBorrow on line 822
823:          totalBorrow.base -= uint128(borrowPart);

/// @audit totalBorrowCap on line 751
751:              totalBorrowCap == 0 || totalBorrow.elastic <= totalBorrowCap,

/// @audit EXCHANGE_RATE_PRECISION on line 785
813:              (amountWithBonus * _exchangeRate) / EXCHANGE_RATE_PRECISION,

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L447

```solidity
File: tapioca-bar-audit/contracts/markets/Market.sol

/// @audit paused on line 247
248:          emit PausedUpdated(paused, val);

/// @audit exchangeRate on line 345
349:              rate = exchangeRate;

/// @audit minLiquidatorReward on line 216
222:                  _maxLiquidatorReward > minLiquidatorReward,

/// @audit minLiquidatorReward on line 451
456:          int256 diff = int256(minLiquidatorReward) - int256(maxLiquidatorReward);

/// @audit maxLiquidatorReward on line 456
459:              int256(maxLiquidatorReward);

/// @audit collateralizationRate on line 284
288:              ((collateralizationRate * collateralPartInAssetScaled) /

/// @audit collateralizationRate on line 288
291:              (collateralizationRate *

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/Market.sol#L248

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol

/// @audit totalAsset on line 50
72:                   totalAsset,

/// @audit totalAsset on line 72
90:                   totalAsset,

/// @audit totalAsset on line 229
232:          Rebase memory _totalAsset = totalAsset;

/// @audit ASSET_SIG on line 245
246:                  _yieldBoxShares[from][ASSET_SIG] = 0; //some assets accrue in time

/// @audit ASSET_SIG on line 246
248:                  _yieldBoxShares[from][ASSET_SIG] -= share;

/// @audit minimumTargetUtilization on line 112
113:              uint256 underFactor = ((minimumTargetUtilization - utilization) *

/// @audit minimumTargetUtilization on line 113
114:                  FACTOR_PRECISION) / minimumTargetUtilization;

/// @audit maximumTargetUtilization on line 124
125:              uint256 overFactor = ((utilization - maximumTargetUtilization) *

/// @audit minimumInterestPerSecond on line 121
122:                  _accrueInfo.interestPerSecond = minimumInterestPerSecond; // 0.25% APR minimum

/// @audit maximumInterestPerSecond on line 132
133:                  newInterestPerSecond = maximumInterestPerSecond; // 1000% APR maximum

/// @audit interestElasticity on line 115
118:                  (uint256(_accrueInfo.interestPerSecond) * interestElasticity) /

/// @audit interestElasticity on line 118
127:              uint256 scale = interestElasticity +

/// @audit interestElasticity on line 127
131:              ) * scale) / interestElasticity;

/// @audit startingInterestPerSecond on line 83
84:                   _accrueInfo.interestPerSecond = startingInterestPerSecond;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol#L72

```solidity
File: tapioca-bar-audit/contracts/Penrose.sol

/// @audit paused on line 273
274:          emit PausedUpdated(paused, val);

/// @audit usdoAssetId on line 302
310:          emit UsdoTokenUpdated(_usdoToken, usdoAssetId);

/// @audit feeTo on line 508
532:                  feeTo,

/// @audit feeTo on line 532
536:              yieldBox.transfer(address(this), feeTo, assetId, feeShares);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/Penrose.sol#L274

```solidity
File: tapioca-bar-audit/contracts/usd0/BaseUSDO.sol

/// @audit paused on line 116
117:          emit PausedUpdated(paused, val);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDO.sol#L117

```solidity
File: tapiocaz-audit/contracts/TapiocaWrapper.sol

/// @audit tapiocaOFTs on line 86
/// @audit tapiocaOFTs on line 89
89:           return tapiocaOFTs[tapiocaOFTs.length - 1];

/// @audit harvestableTapiocaOFTs on line 98
99:               harvestableTapiocaOFTs[i].harvestFees();

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/TapiocaWrapper.sol#L89

```solidity
File: tapiocaz-audit/contracts/tOFT/BaseTOFT.sol

/// @audit erc20 on line 371
374:              IERC20(erc20).safeTransfer(_toAddress, _amount);

/// @audit _decimalCache on line 85
86:           return _decimalCache;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFT.sol#L374

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol

/// @audit erc20 on line 215
217:              .buildSwapData(erc20, swapData.tokenOut, amount, 0, false, false);

/// @audit erc20 on line 272
275:              IERC20(erc20).safeTransfer(_toAddress, _amount);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol#L217

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol

/// @audit yieldBox on line 182
184:          _erc20.approve(address(yieldBox), _amount);

/// @audit yieldBox on line 184
185:          yieldBox.depositAsset(_assetId, _from, _to, _amount, _share);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol#L184

```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

/// @audit rewardTokens on line 456
457:          rewardTokens.push(token);

/// @audit lastProcessedWeek on line 434
437:          WeekTotals storage totals = weekTotals[lastProcessedWeek];

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L457

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

/// @audit paymentTokenBeneficiary on line 369
378:                      paymentTokenBeneficiary,

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L378

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionBroker.sol

/// @audit paymentTokenBeneficiary on line 483
492:                      paymentTokenBeneficiary,

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L492

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol

/// @audit singularities on line 304
313:                      singularities.pop();

/// @audit singularities on line 321
322:                      singularities.pop();

/// @audit singularities on line 338
340:              total += activeSingularities[sglAssetIDToAddress[singularities[i]]]

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L313

```solidity
File: tap-token-audit/contracts/tokens/BaseTapOFT.sol

/// @audit twTap on line 135
138:          try twTap.participate(to, amount, duration) {} catch Error(

/// @audit twTap on line 222
225:          try twTap.claimAndSendRewards(tokenID, rewardTokens) {

/// @audit twTap on line 307
310:          try twTap.exitPositionAndSendTap(tokenID) returns (uint256 _amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/BaseTapOFT.sol#L138

```solidity
File: tap-token-audit/contracts/tokens/TapOFT.sol

/// @audit governanceChainIdentifier on line 119
120:          if (_getChainId() == governanceChainIdentifier) {

/// @audit paused on line 153
154:          emit PausedUpdated(paused, val);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L120

```solidity
File: tap-token-audit/contracts/Vesting.sol

/// @audit start on line 168
170:          if (block.timestamp < start + cliff) return 0;

/// @audit start on line 170
171:          if (block.timestamp >= start + duration) return total;

/// @audit start on line 171
/// @audit duration on line 171
172:          return (total * (block.timestamp - start)) / duration;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/Vesting.sol#L170

```solidity
File: tapioca-periph-audit/contracts/Swapper/CurveSwapper.sol

/// @audit curvePool on line 102
103:          address tokenOut = curvePool.coins(tokenIndexes[1]);

/// @audit curvePool on line 152
153:          address tokenOut = curvePool.coins(uint256(uint128(j)));

/// @audit curvePool on line 153
155:          uint256 outputAmount = curvePool.get_dy(i, j, amountIn);

/// @audit curvePool on line 155
160:          _safeApprove(tokenIn, address(curvePool), amountIn);

/// @audit curvePool on line 160
161:          curvePool.exchange(i, j, amountIn, amountOutMin);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/CurveSwapper.sol#L103

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol

/// @audit swapper on line 104
112:              result = swapper.getOutputAmount(swapData, "");

/// @audit swapper on line 184
192:              uint256 calcAmount = swapper.getOutputAmount(swapData, "");

/// @audit swapper on line 192
194:              swapper.swap(swapData, minAmount, address(this), "");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol#L112

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol

/// @audit poolId on line 152
172:              poolId,

/// @audit poolId on line 172
181:          vault.joinPool(poolId, address(this), address(this), joinPoolRequest);

/// @audit poolId on line 222
245:              poolId,

/// @audit poolId on line 245
257:          vault.exitPool(poolId, address(this), payable(this), exitRequest);

/// @audit poolId on line 274
291:              poolId,

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L172

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol

/// @audit swapper on line 134
142:              result = swapper.getOutputAmount(swapData, "");

/// @audit swapper on line 171
172:          rewardToken.approve(address(swapper), 0);

/// @audit swapper on line 197
198:                  ISwapper.SwapData memory swapData = swapper.buildSwapData(

/// @audit swapper on line 198
206:                  uint256 calcAmount = swapper.getOutputAmount(swapData, "");

/// @audit swapper on line 206
208:                  swapper.swap(swapData, minAmount, address(this), "");

/// @audit lpGetter on line 153
155:          result = lpGetter.removeLiquidityWeth(lpBalance, minAmount);

/// @audit lpGetter on line 180
181:          wrappedNative.approve(address(lpGetter), 0);

/// @audit lpGetter on line 311
314:              uint256 lpAmount = lpGetter.addLiquidityWeth(amount, minAmount);

/// @audit lpGetter on line 335
337:              lpGetter.removeLiquidityWeth(lpBalance, minAmount);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L142

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol

/// @audit swapper on line 116
124:              result = swapper.getOutputAmount(swapData, "");

/// @audit swapper on line 142
143:          rewardToken.approve(address(swapper), 0);

/// @audit swapper on line 170
178:                  uint256 calcAmount = swapper.getOutputAmount(swapData, "");

/// @audit swapper on line 178
180:                  swapper.swap(swapData, minAmount, address(this), "");

/// @audit lpGetter on line 73
76:           lpToken = IERC20(lpGetter.lpToken());

/// @audit lpGetter on line 151
152:          wrappedNative.approve(address(lpGetter), 0);

/// @audit lpGetter on line 185
187:                  uint256 lpAmount = lpGetter.addLiquidityWeth(

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L124

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol

/// @audit swapper on line 107
115:              result = swapper.getOutputAmount(swapData, "");

/// @audit swapper on line 133
134:          rewardToken.approve(address(swapper), 0);

/// @audit swapper on line 161
169:                  uint256 calcAmount = swapper.getOutputAmount(swapData, "");

/// @audit swapper on line 169
171:                  swapper.swap(swapData, minAmount, address(this), "");

/// @audit lpGetter on line 75
78:           IERC20(lpGetter.lpToken()).approve(_lpGauge, type(uint256).max);

/// @audit lpGetter on line 78
79:           IERC20(lpGetter.lpToken()).approve(_lpGetter, type(uint256).max);

/// @audit lpGetter on line 142
143:          wrappedNative.approve(address(lpGetter), 0);

/// @audit lpGetter on line 187
189:          result = lpGetter.removeLiquidityWeth(lpBalance, minAmount);

/// @audit lpGetter on line 231
233:              lpGetter.removeLiquidityWeth(lpBalance, minAmount);

/// @audit lpGetter on line 248
250:          uint256 lpAmount = lpGetter.addLiquidityWeth(amount, minAmount);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L115

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol

/// @audit swapper on line 123
131:              result = swapper.getOutputAmount(swapData, "");

/// @audit swapper on line 150
151:          stgTokenReward.approve(address(swapper), 0);

/// @audit swapper on line 173
181:                  uint256 calcAmount = swapper.getOutputAmount(swapData, "");

/// @audit swapper on line 181
184:                  swapper.swap(swapData, minAmount, address(this), "");

/// @audit lpStakingPid on line 197
200:          lpStaking.withdraw(lpStakingPid, toWithdraw);

/// @audit stgNative on line 88
89:           stgNative.approve(_lpStaking, type(uint256).max);

/// @audit stgNative on line 89
90:           stgNative.approve(address(router), type(uint256).max);

/// @audit stgTokenReward on line 92
94:           stgTokenReward.approve(_swapper, type(uint256).max);

/// @audit stgTokenReward on line 151
153:          stgTokenReward.approve(_swapper, type(uint256).max);

/// @audit stgTokenReward on line 166
168:              uint256 stgBalanceAfter = stgTokenReward.balanceOf(address(this));

/// @audit stgTokenReward on line 168
174:                      address(stgTokenReward),

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L131

</details>

### [G&#x2011;11] `<x> += <y>` costs more gas than `<x> = <x> + <y>` for state variables
Using the addition operator instead of plus-equals saves **[113 gas](https://gist.github.com/IllIllI000/cbbfb267425b898e5be734d4008d4fe8)**

*There are 5 instances of this issue:*

```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

446:          totalFees += balance;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L446

```solidity
File: tap-token-audit/contracts/tokens/TapOFT.sol

204:          dso_supply -= mintedInWeek[week - 1];

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L204

```solidity
File: tap-token-audit/contracts/Vesting.sol

115:          _totalClaimed += _claimable;

143:          _totalAmount += _amount;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/Vesting.sol#L115

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol

125:              feesPending -= feeAmount;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol#L125


### [G&#x2011;12] Add `unchecked {}` for subtractions where the operands cannot underflow because of a previous `require()` or `if`-statement
`require(a <= b); x = b - a` => `require(a <= b); unchecked { x = b - a }`

*There are 21 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: tapioca-bar-audit/contracts/markets/MarketERC20.sol

/// @audit require() on line 142
146:                  balanceOf[msg.sender] = srcBalance - amount; // Underflow is checked

/// @audit require() on line 167
181:                  balanceOf[from] = srcBalance - amount; // Underflow is checked

/// @audit require() on line 174
177:                      allowance[from][msg.sender] = spenderAllowance - amount; // Underflow is checked

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/MarketERC20.sol#L146

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol

/// @audit if-condition on line 112
113:              uint256 underFactor = ((minimumTargetUtilization - utilization) *

/// @audit if-condition on line 124
125:              uint256 overFactor = ((utilization - maximumTargetUtilization) *

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol#L113

```solidity
File: tapioca-periph-audit/contracts/Swapper/CurveSwapper.sol

/// @audit require() on line 164
166:          return balanceAfter - balanceBefore;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/CurveSwapper.sol#L166

```solidity
File: tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol

/// @audit if-condition on line 623
630:                          _removeAmount - repayed,

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L630

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol

/// @audit require() on line 264
268:          return wrappedNativeBalanceAfter - wrappedNativeBalanceBefore;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L268

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol

/// @audit if-condition on line 180
181:              uint256 aaveAmount = aaveBalanceAfter - aaveBalanceBefore;

/// @audit if-condition on line 258
261:              uint256 toWithdraw = amount - queued;

/// @audit if-condition on line 268
269:                  amount += (obtainedWrapped - toWithdraw);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol#L181

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol

/// @audit if-condition on line 199
202:              uint256 toWithdraw = (((amount - queued) * (10 ** decimals)) /

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L202

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol

/// @audit if-condition on line 144
146:              uint256 toWithdraw = (((amount - queued) * (10 ** 18)) /

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol#L146

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol

/// @audit if-condition on line 167
168:                  uint256 crvAmount = crvBalanceAfter - crvBalanceBefore;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L168

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol

/// @audit if-condition on line 158
159:                  uint256 crvAmount = crvBalanceAfter - crvBalanceBefore;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L159

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol

/// @audit if-condition on line 269
274:              gmxRewardRouter.unstakeEsGmx(vestable - freeEsGmx);

/// @audit if-condition on line 311
312:              gmxRewardRouter.stakeEsGmx(freeEsGmx - buffer);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol#L274

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol

/// @audit if-condition on line 149
150:              uint256 toWithdraw = amount - queued; //1:1 between eth<>stEth

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol#L150

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol

/// @audit if-condition on line 170
171:                  uint256 stgAmount = stgBalanceAfter - stgBalanceBefore;

/// @audit if-condition on line 249
251:              uint256 toWithdraw = amount - queued;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L171

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol

/// @audit if-condition on line 140
142:              uint256 toWithdraw = (((amount - queued) *

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol#L142

</details>

### [G&#x2011;13] `<array>.length` should not be looked up in every loop of a `for`-loop
The overheads outlined below are _PER LOOP_, excluding the first loop
* storage arrays incur a Gwarmaccess (**100 gas**)
* memory arrays use `MLOAD` (**3 gas**)
* calldata arrays use `CALLDATALOAD` (**3 gas**)

Caching the length changes each of these to a `DUP<N>` (**3 gas**), and gets rid of the extra `DUP<N>` needed to store the stack offset

*There are 24 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

215:          for (uint256 i = 0; i < calls.length; i++) {

666:          for (uint256 i = 0; i < users.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L215

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol

45:                   for (uint256 i = 0; i < maxBorrowParts.length; i++) {

107:          for (uint256 i = 0; i < users.length; i++) {

384:          for (uint256 i = 0; i < users.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L45

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/Singularity.sol

187:          for (uint256 i = 0; i < calls.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L187

```solidity
File: tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol

255:          for (uint256 i = 0; i < approvals.length; ) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol#L255

```solidity
File: tapioca-bar-audit/contracts/usd0/modules/USDOMarketModule.sol

244:          for (uint256 i = 0; i < approvals.length; ) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOMarketModule.sol#L244

```solidity
File: tapioca-bar-audit/contracts/usd0/modules/USDOOptionsModule.sol

245:          for (uint256 i = 0; i < approvals.length; ) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOOptionsModule.sol#L245

```solidity
File: tapiocaz-audit/contracts/TapiocaWrapper.sol

98:           for (uint256 i = 0; i < harvestableTapiocaOFTs.length; i++) {

140:          for (uint256 i = 0; i < _call.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/TapiocaWrapper.sol#L98

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol

285:          for (uint256 i = 0; i < approvals.length; ) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol#L285

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTMarketModule.sol

261:          for (uint256 i = 0; i < approvals.length; ) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTMarketModule.sol#L261

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTOptionsModule.sol

260:          for (uint256 i = 0; i < approvals.length; ) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTOptionsModule.sol#L260

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

332:              for (uint256 i = 0; i < _users.length; i++) {

336:              for (uint256 i = 0; i < _users.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L332

```solidity
File: tap-token-audit/contracts/tokens/BaseTapOFT.sol

333:          for (uint256 i = 0; i < approvals.length; ) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/BaseTapOFT.sol#L333

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol

156:          for (uint256 i = 0; i < poolTokens.length; i++) {

225:          for (uint256 i = 0; i < poolTokens.length; i++) {

277:          for (uint256 i = 0; i < poolTokens.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L156

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol

195:          for (uint256 i = 0; i < tokens.length; i++) {

255:          for (uint256 i = 0; i < tempData.tokens.length; i++) {

273:          for (uint256 i = 0; i < tempData.tokens.length; i++) {

280:          for (uint256 i = 0; i < tempData.tokens.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L195

</details>

### [G&#x2011;14] `++i`/`i++` should be `unchecked{++i}`/`unchecked{i++}` when it is not possible for them to overflow, as is the case when used in `for`- and `while`-loops
The `unchecked` keyword is new in solidity version 0.8.0, so this only applies to that version or higher, which these instances are. This saves **30-40 gas [per loop](https://gist.github.com/hrkrshnn/ee8fabd532058307229d65dcd5836ddc#the-increment-in-for-loop-post-condition-can-be-made-unchecked)**

*There are 27 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

215:          for (uint256 i = 0; i < calls.length; i++) {

666:          for (uint256 i = 0; i < users.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L215

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol

45:                   for (uint256 i = 0; i < maxBorrowParts.length; i++) {

107:          for (uint256 i = 0; i < users.length; i++) {

384:          for (uint256 i = 0; i < users.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L45

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/Singularity.sol

187:          for (uint256 i = 0; i < calls.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L187

```solidity
File: tapiocaz-audit/contracts/TapiocaWrapper.sol

98:           for (uint256 i = 0; i < harvestableTapiocaOFTs.length; i++) {

140:          for (uint256 i = 0; i < _call.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/TapiocaWrapper.sol#L98

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

332:              for (uint256 i = 0; i < _users.length; i++) {

336:              for (uint256 i = 0; i < _users.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L332

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol

339:          for (uint256 i = 0; i < len; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L339

```solidity
File: tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol

202:          for (uint256 i = 0; i < length; i++) {

973:          for (uint256 i = 0; i < len; i++) {

1004:         for (uint256 i = 0; i < len; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol#L202

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol

156:          for (uint256 i = 0; i < poolTokens.length; i++) {

225:          for (uint256 i = 0; i < poolTokens.length; i++) {

277:          for (uint256 i = 0; i < poolTokens.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L156

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol

195:          for (uint256 i = 0; i < tokens.length; i++) {

255:          for (uint256 i = 0; i < tempData.tokens.length; i++) {

273:          for (uint256 i = 0; i < tempData.tokens.length; i++) {

280:          for (uint256 i = 0; i < tempData.tokens.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L195

```solidity
File: YieldBox/contracts/NativeTokenFactory.sol

129:          for (uint256 i = 0; i < len; i++) {

141:          for (uint256 i = 0; i < len; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/NativeTokenFactory.sol#L129

```solidity
File: YieldBox/contracts/YieldBox.sol

309:          for (uint256 i = 0; i < len; i++) {

320:          for (uint256 i = 0; i < len; i++) {

339:          for (uint256 i = 0; i < len; i++) {

345:          for (uint256 i = 0; i < len; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBox.sol#L309

</details>

### [G&#x2011;15] `private` functions not called by the contract should be removed to save deployment gas


*There is one instance of this issue:*

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/Singularity.sol

631       function _executeViewModule(
632           Module _module,
633           bytes memory _data
634:      ) private view returns (bytes memory returnData) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L631-L634


### [G&#x2011;16] Optimize names to save gas
`public`/`external` function names and `public` member variable names can be optimized to save gas. See [this](https://gist.github.com/IllIllI000/a5d8b486a8259f9f77891a919febd1a9) link for an example of how it works. Below are the interfaces/abstract contracts that can be optimized so that the most frequently-called functions use the least amount of gas possible during method lookup. Method IDs that have two leading zero bytes can save **128 gas** each during deployment, and renaming functions to have lower method IDs will save **22 gas** per call, [per sorted position shifted](https://medium.com/joyso/solidity-how-does-function-name-affect-gas-consumption-in-smart-contract-47d270d8ac92)

*There are 54 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

/// @audit init(), getTotalDebt(), getDebtRate(), execute(), updateOperator(), accrue(), borrow(), repay(), addCollateral(), removeCollateral(), liquidate(), buyCollateral(), sellCollateral(), refreshPenroseFees(), setBigBangConfig()
39:   contract BigBang is BoringOwnable, Market {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L39

```solidity
File: tapioca-bar-audit/contracts/markets/MarketERC20.sol

/// @audit approveBorrow(), permitBorrow()
24:   contract MarketERC20 is IERC20, IERC20Permit, EIP712 {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/MarketERC20.sol#L24

```solidity
File: tapioca-bar-audit/contracts/markets/Market.sol

/// @audit setBorrowOpeningFee(), setBorrowCap(), setMarketConfig(), updatePause(), computeClosingFactor(), computeTVLInfo(), updateExchangeRate(), computeLiquidatorReward()
14:   abstract contract Market is MarketERC20, BoringOwnable {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/Market.sol#L14

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLBorrow.sol

/// @audit borrow(), repay()
8:    contract SGLBorrow is SGLLendingCommon {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLBorrow.sol#L8

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLCollateral.sol

/// @audit addCollateral(), removeCollateral()
8:    contract SGLCollateral is SGLLendingCommon {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLCollateral.sol#L8

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol

/// @audit accrue(), getInterestDetails()
9:    contract SGLCommon is SGLStorage {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol#L9

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLLeverage.sol

/// @audit multiHopBuyCollateral(), multiHopSellCollateral(), sellCollateral(), buyCollateral()
10:   contract SGLLeverage is SGLLendingCommon {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLeverage.sol#L10

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/Singularity.sol

/// @audit init(), computeAllowedLendShare(), yieldBoxShares(), execute(), addAsset(), removeAsset(), addCollateral(), removeCollateral(), borrow(), repay(), sellCollateral(), buyCollateral(), multiHopBuyCollateral(), multiHopSellCollateral(), liquidate(), withdrawFeesEarned(), refreshPenroseFees(), setSingularityConfig(), setLiquidationQueueConfig()
37:   contract Singularity is SGLCommon {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L37

```solidity
File: tapioca-bar-audit/contracts/Penrose.sol

/// @audit singularityMarkets(), bigBangMarkets(), singularityMasterContractLength(), bigBangMasterContractLength(), withdrawAllMarketFees(), setBigBangEthMarketDebtRate(), setBigBangEthMarket(), updatePause(), setConservator(), setUsdoToken(), registerSingularityMasterContract(), registerBigBangMasterContract(), registerSingularity(), addSingularity(), registerBigBang(), addBigBang(), executeMarketFn(), setFeeTo(), setSwapper(), _getMasterContractLength()
32:   contract Penrose is BoringOwnable, BoringFactory {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/Penrose.sol#L32

```solidity
File: tapioca-bar-audit/contracts/usd0/BaseUSDO.sol

/// @audit setMaxFlashMintable(), setFlashMintFee(), setConservator(), updatePause(), setMinterStatus(), setBurnerStatus(), triggerSendFrom(), exerciseOption(), initMultiHopBuy(), removeAsset(), sendForLeverage(), sendAndLendOrRepay()
46:   contract BaseUSDO is BaseUSDOStorage, ERC20Permit {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDO.sol#L46

```solidity
File: tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol

/// @audit initMultiHopBuy(), sendForLeverage(), multiHop(), leverageUp(), leverageUpInternal()
19:   contract USDOLeverageModule is BaseUSDOStorage {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol#L19

```solidity
File: tapioca-bar-audit/contracts/usd0/modules/USDOMarketModule.sol

/// @audit removeAsset(), sendAndLendOrRepay(), remove(), lend(), lendInternal()
21:   contract USDOMarketModule is BaseUSDOStorage {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOMarketModule.sol#L21

```solidity
File: tapioca-bar-audit/contracts/usd0/modules/USDOOptionsModule.sol

/// @audit triggerSendFrom(), exerciseOption(), sendFromDestination(), exercise(), exerciseInternal()
16:   contract USDOOptionsModule is BaseUSDOStorage {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOOptionsModule.sol#L16

```solidity
File: tapiocaz-audit/contracts/Balancer.sol

/// @audit checker(), rebalance(), initConnectedOFT(), addRebalanceAmount()
34:   contract Balancer is Owned {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/Balancer.sol#L34

```solidity
File: tapiocaz-audit/contracts/TapiocaWrapper.sol

/// @audit tapiocaOFTLength(), harvestableTapiocaOFTsLength(), lastTOFT(), harvestFees(), executeTOFT(), executeCalls(), createTOFT()
26:   contract TapiocaWrapper is Ownable {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/TapiocaWrapper.sol#L26

```solidity
File: tapiocaz-audit/contracts/tOFT/BaseTOFT.sol

/// @audit triggerSendFrom(), exerciseOption(), initMultiSell(), removeCollateral(), sendToStrategy(), retrieveFromStrategy(), sendToYBAndBorrow(), sendForLeverage()
15:   contract BaseTOFT is BaseTOFTStorage, ERC20Permit {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFT.sol#L15

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol

/// @audit initMultiSell(), sendForLeverage(), multiHop(), leverageDown(), leverageDownInternal()
21:   contract BaseTOFTLeverageModule is BaseTOFTStorage {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol#L21

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTMarketModule.sol

/// @audit removeCollateral(), sendToYBAndBorrow(), borrow(), borrowInternal(), remove()
20:   contract BaseTOFTMarketModule is BaseTOFTStorage {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTMarketModule.sol#L20

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTOptionsModule.sol

/// @audit triggerSendFrom(), exerciseOption(), sendFromDestination(), exercise(), exerciseInternal()
16:   contract BaseTOFTOptionsModule is BaseTOFTStorage {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTOptionsModule.sol#L16

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol

/// @audit sendToStrategy(), retrieveFromStrategy(), strategyDeposit(), depositToYieldbox(), strategyWithdraw()
16:   contract BaseTOFTStrategyModule is BaseTOFTStorage {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol#L16

```solidity
File: tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol

/// @audit wrap(), unwrap(), updateConnectedChain(), updateBalancerState(), extractUnderlying()
9:    contract mTapiocaOFT is BaseTOFT {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol#L9

```solidity
File: tapiocaz-audit/contracts/tOFT/TapiocaOFT.sol

/// @audit wrap(), unwrap()
21:   contract TapiocaOFT is BaseTOFT {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/TapiocaOFT.sol#L21

```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

/// @audit currentWeek(), getParticipation(), claimable(), participate(), claimRewards(), claimAndSendRewards(), releaseTap(), exitPosition(), exitPositionAndSendTap(), advanceWeek(), distributeReward(), addRewardToken()
71:   contract TwTAP is TWAML, ONFT721, ERC721Permit {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L71

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

/// @audit getOTCDealDetails(), participate(), exerciseOption(), newEpoch(), aoTAPBrokerClaim(), setTapOracle(), setPhase2MerkleRoots(), registerUserForPhase(), setPaymentToken(), setPaymentTokenBeneficiary(), collectPaymentTokens()
43:   contract AirdropBroker is Pausable, BoringOwnable, FullMath {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L43

```solidity
File: tap-token-audit/contracts/option-airdrop/aoTAP.sol

/// @audit isApprovedOrOwner(), attributes(), exists(), setTokenURI(), mint(), brokerClaim()
32:   contract AOTAP is ERC721, ERC721Permit, BaseBoringBatchable, BoringOwnable {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/aoTAP.sol#L32

```solidity
File: tap-token-audit/contracts/options/oTAP.sol

/// @audit isApprovedOrOwner(), attributes(), exists(), setTokenURI(), mint(), brokerClaim()
30:   contract OTAP is ERC721, ERC721Permit, BaseBoringBatchable {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/oTAP.sol#L30

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionBroker.sol

/// @audit getOTCDealDetails(), participate(), exitPosition(), exerciseOption(), newEpoch(), oTAPBrokerClaim(), setTapOracle(), setPaymentToken(), setPaymentTokenBeneficiary(), collectPaymentTokens()
53:   contract TapiocaOptionBroker is Pausable, BoringOwnable, TWAML {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L53

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol

/// @audit getLock(), getSingularities(), getSingularityPools(), getTotalPoolDeposited(), isApprovedOrOwner(), lock(), unlock(), setSGLPoolWEight(), registerSingularity(), unregisterSingularity()
48:   contract TapiocaOptionLiquidityProvision is

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L48

```solidity
File: tap-token-audit/contracts/tokens/BaseTapOFT.sol

/// @audit lockTwTapPosition(), claimRewards(), unlockTwTapPosition(), setTwTap()
31:   abstract contract BaseTapOFT is OFTV2 {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/BaseTapOFT.sol#L31

```solidity
File: tap-token-audit/contracts/tokens/LTap.sol

/// @audit deposit(), redeem(), setLockedUntil()
23:   contract LTap is BoringOwnable, ERC20Permit {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/LTap.sol#L23

```solidity
File: tap-token-audit/contracts/tokens/TapOFT.sol

/// @audit setGovernanceChainIdentifier(), updatePause(), setMinter(), timestampToWeek(), getCurrentWeek(), getCurrentWeekEmission(), emitForWeek(), extractTAP(), removeTAP()
26:   contract TapOFT is BaseTapOFT, ERC20Permit {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L26

```solidity
File: tap-token-audit/contracts/Vesting.sol

/// @audit claimable(), claimable(), vested(), vested(), totalClaimed(), claim(), registerUser(), init()
10:   contract Vesting is BoringOwnable, ReentrancyGuard {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/Vesting.sol#L10

```solidity
File: tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol

/// @audit singularityMarketInfo(), bigBangMarketInfo(), getCollateralAmountForShare(), getCollateralSharesForBorrowPart(), getAmountForBorrowPart(), getBorrowPartForAmount(), getAmountForAssetFraction(), getFractionForAmount(), burst(), withdrawToChain(), depositAddCollateralAndBorrowFromMarket(), depositRepayAndRemoveCollateralFromMarket(), mintFromBBAndLendOnSGL(), exitPositionAndRemoveCollateral()
30:   contract MagnetarV2 is Ownable, MagnetarV2Storage {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol#L30

```solidity
File: tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol

/// @audit withdrawToChain(), depositAddCollateralAndBorrowFromMarket(), depositRepayAndRemoveCollateralFromMarket(), mintFromBBAndLendOnSGL(), exitPositionAndRemoveCollateral()
20:   contract MagnetarMarketModule is MagnetarV2Storage {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L20

```solidity
File: tapioca-periph-audit/contracts/Multicall/Multicall3.sol

/// @audit multicall(), multicallValue()
22:   contract Multicall3 is Ownable {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Multicall/Multicall3.sol#L22

```solidity
File: tapioca-periph-audit/contracts/oracle/implementations/ARBTriCryptoOracle.sol

/// @audit coins(), get_dy(), exchange(), get_virtual_price(), gamma(), A()
10:   interface ICurvePool {

/// @audit get(), peek(), peekSpot(), symbol(), name()
30:   contract ARBTriCryptoOracle is ITOracle {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/ARBTriCryptoOracle.sol#L10

```solidity
File: tapioca-periph-audit/contracts/oracle/implementations/SGOracle.sol

/// @audit deltaCredit(), totalLiquidity(), localDecimals(), token()
7:    interface IStargatePool {

/// @audit get(), peek(), peekSpot(), symbol(), name()
23:   contract SGOracle is IOracle {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/SGOracle.sol#L7

```solidity
File: tapioca-periph-audit/contracts/oracle/Seer.sol

/// @audit get(), peek(), peekSpot(), symbol(), name()
7:    contract Seer is ITOracle, OracleMulti {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/Seer.sol#L7

```solidity
File: tapioca-periph-audit/contracts/TapiocaDeployer/TapiocaDeployer.sol

/// @audit deploy(), computeAddress(), computeAddress()
7:    contract TapiocaDeployer {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/TapiocaDeployer/TapiocaDeployer.sol#L7

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol

/// @audit compoundAmount(), setDepositThreshold(), setMultiSwapper(), compound()
29:   contract AaveStrategy is BaseERC20Strategy, BoringOwnable, ReentrancyGuard {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol#L29

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol

/// @audit compoundAmount(), setDepositThreshold(), compound(), updateCache()
28:   contract BalancerStrategy is BaseERC20Strategy, BoringOwnable, ReentrancyGuard {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L28

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol

/// @audit compoundAmount(), setDepositThreshold(), compound()
28:   contract CompoundStrategy is BaseERC20Strategy, BoringOwnable, ReentrancyGuard {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol#L28

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol

/// @audit compoundAmount(), setDepositThreshold(), setMultiSwapper(), setTricryptoLPGetter(), compound()
31:   contract ConvexTricryptoStrategy is

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L31

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol

/// @audit compoundAmount(), setDepositThreshold(), setMultiSwapper(), setTricryptoLPGetter(), compound()
30:   contract TricryptoLPStrategy is

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L30

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol

/// @audit compoundAmount(), setDepositThreshold(), setMultiSwapper(), setTricryptoLPGetter(), compound()
30:   contract TricryptoNativeStrategy is

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L30

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol

/// @audit uniswapV3SwapCallback(), harvest(), harvestGmx(), setFeeRecipient(), withdrawFees()
23:   contract GlpStrategy is BaseERC20Strategy, BoringOwnable {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol#L23

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol

/// @audit compoundAmount(), setDepositThreshold(), compound()
30:   contract LidoEthStrategy is BaseERC20Strategy, BoringOwnable, ReentrancyGuard {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol#L30

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol

/// @audit compoundAmount(), setDepositThreshold(), setMultiSwapper(), compound()
35:   contract StargateStrategy is BaseERC20Strategy, BoringOwnable, ReentrancyGuard {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L35

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol

/// @audit compoundAmount(), setDepositThreshold(), compound()
30:   contract YearnStrategy is BaseERC20Strategy, BoringOwnable, ReentrancyGuard {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol#L30

```solidity
File: YieldBox/contracts/NativeTokenFactory.sol

/// @audit transferOwnership(), claimOwnership(), createToken(), mint(), burn(), batchMint(), batchBurn()
21:   contract NativeTokenFactory is AssetRegister {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/NativeTokenFactory.sol#L21

```solidity
File: YieldBox/contracts/YieldBox.sol

/// @audit depositAsset(), depositNFTAsset(), depositETHAsset(), withdraw(), transfer(), batchTransfer(), transferMultiple(), name(), symbol(), decimals(), assetTotals(), toShare(), toAmount(), amountOf(), deposit(), depositETH()
50:   contract YieldBox is YieldBoxPermit, BoringBatchable, NativeTokenFactory, ERC721TokenReceiver, ERC1155TokenReceiver {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBox.sol#L50

```solidity
File: YieldBox/contracts/YieldBoxURIBuilder.sol

/// @audit name(), symbol(), decimals(), uri()
11:   contract YieldBoxURIBuilder {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxURIBuilder.sol#L11

</details>

### [G&#x2011;17] `>=` costs less gas than `>`
The compiler uses opcodes `GT` and `ISZERO` for solidity code that uses `>`, but only requires `LT` for `>=`, [which saves **3 gas**](https://gist.github.com/IllIllI000/3dc79d25acccfa16dee4e83ffdc6ffde)

*There are 2 instances of this issue:*

```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

797           borrowPart = maxBorrowPart > availableBorrowPart
798               ? availableBorrowPart
799:              : maxBorrowPart;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L797-L799

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol

240           borrowPart = maxBorrowPart > availableBorrowPart
241               ? availableBorrowPart
242:              : maxBorrowPart;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L240-L242


### [G&#x2011;18] `internal` functions not called by the contract should be removed to save deployment gas
If the functions are required by an interface, the contract should inherit from that interface and use the `override` keyword

*There is one instance of this issue:*

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol

254       function _getAmountForBorrowPart(
255           uint256 borrowPart
256:      ) internal view returns (uint256) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol#L254-L256


### [G&#x2011;19] `++i` costs less gas than `i++`, especially when it's used in `for`-loops (`--i`/`i--` too)
Saves **5 gas per loop**

*There are 41 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

215:          for (uint256 i = 0; i < calls.length; i++) {

666:          for (uint256 i = 0; i < users.length; i++) {

669:                  liquidatedCount++;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L215

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol

45:                   for (uint256 i = 0; i < maxBorrowParts.length; i++) {

107:          for (uint256 i = 0; i < users.length; i++) {

384:          for (uint256 i = 0; i < users.length; i++) {

387:                  liquidatedCount++;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L45

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/Singularity.sol

187:          for (uint256 i = 0; i < calls.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L187

```solidity
File: tapiocaz-audit/contracts/TapiocaWrapper.sol

98:           for (uint256 i = 0; i < harvestableTapiocaOFTs.length; i++) {

140:          for (uint256 i = 0; i < _call.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/TapiocaWrapper.sol#L98

```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

278:              pool.totalParticipants++; // Save participation

537:              pool.totalParticipants--;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L278

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

288:          epoch++;

332:              for (uint256 i = 0; i < _users.length; i++) {

336:              for (uint256 i = 0; i < _users.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L288

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionBroker.sol

243:              pool.totalParticipants++; // Save participation

325:              pool.totalParticipants--;

423:          epoch++;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L243

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol

308:              for (uint256 i = 0; i < sglLength; i++) {

339:          for (uint256 i = 0; i < len; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L308

```solidity
File: tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol

202:          for (uint256 i = 0; i < length; i++) {

973:          for (uint256 i = 0; i < len; i++) {

1004:         for (uint256 i = 0; i < len; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol#L202

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol

156:          for (uint256 i = 0; i < poolTokens.length; i++) {

225:          for (uint256 i = 0; i < poolTokens.length; i++) {

277:          for (uint256 i = 0; i < poolTokens.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L156

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol

195:          for (uint256 i = 0; i < tokens.length; i++) {

255:          for (uint256 i = 0; i < tempData.tokens.length; i++) {

273:          for (uint256 i = 0; i < tempData.tokens.length; i++) {

280:          for (uint256 i = 0; i < tempData.tokens.length; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L195

```solidity
File: YieldBox/contracts/BoringMath.sol

28:               result++;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/BoringMath.sol#L28

```solidity
File: YieldBox/contracts/NativeTokenFactory.sol

129:          for (uint256 i = 0; i < len; i++) {

141:          for (uint256 i = 0; i < len; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/NativeTokenFactory.sol#L129

```solidity
File: YieldBox/contracts/YieldBoxRebase.sol

28:           totalAmount++;

36:               share++;

51:           totalAmount++;

59:               amount++;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxRebase.sol#L28

```solidity
File: YieldBox/contracts/YieldBox.sol

309:          for (uint256 i = 0; i < len; i++) {

320:          for (uint256 i = 0; i < len; i++) {

339:          for (uint256 i = 0; i < len; i++) {

345:          for (uint256 i = 0; i < len; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBox.sol#L309

</details>

### [G&#x2011;20] Splitting `require()` statements that use `&&` saves gas
See [this issue](https://github.com/code-423n4/2022-01-xdefi-findings/issues/128) which describes the fact that there is a larger deployment gas cost, but with enough runtime calls, the change ends up being cheaper by **3 gas**

*There are 7 instances of this issue:*

```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

133           require(
134               address(_collateral) != address(0) &&
135                   address(_asset) != address(0) &&
136                   address(_oracle) != address(0),
137               "BigBang: bad pair"
138:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L133-L138

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/Singularity.sol

100           require(
101               address(_collateral) != address(0) &&
102                   address(_asset) != address(0) &&
103                   address(_oracle) != address(0),
104               "SGL: bad pair"
105:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L100-L105

```solidity
File: tapioca-bar-audit/contracts/Penrose.sol

237           require(
238               markets_.length == swappers_.length &&
239                   swappers_.length == swapData_.length,
240               "Penrose: length mismatch"
241:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/Penrose.sol#L237-L241

```solidity
File: tapioca-periph-audit/contracts/Swapper/BaseSwapper.sol

102           require(
103               success && (data.length == 0 || abi.decode(data, (bool))),
104               "BaseSwapper::safeApprove: approve failed"
105:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/BaseSwapper.sol#L102-L105

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol

376           require(
377               success && (data.length == 0 || abi.decode(data, (bool))),
378               "OperationsLib::safeApprove: approve failed"
379:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L376-L379

```solidity
File: YieldBox/contracts/YieldBox.sol

127:          require(asset.tokenType != TokenType.Native && asset.tokenType != TokenType.ERC721, "YieldBox: can't deposit type");

199:          require(asset.tokenType == TokenType.ERC20 && asset.contractAddress == address(wrappedNative), "YieldBox: not wrappedNative");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBox.sol#L127


### [G&#x2011;21] Using `private` rather than `public` for constants, saves gas
If needed, the values can be read from the verified contract source code, or if there are multiple values there can be a single getter function that [returns a tuple](https://github.com/code-423n4/2022-08-frax/blob/90f55a9ce4e25bceed3a74290b854341d8de6afa/src/contracts/FraxlendPair.sol#L156-L178) of the values of all currently-public constants. Saves **3406-3606 gas** in deployment gas due to the compiler not having to create non-payable getter functions for deployment calldata, not having to store the bytes of the value outside of where it's used, and not adding another entry to the method ID table

*There are 17 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: tapioca-bar-audit/contracts/Penrose.sol

45:       uint256 public immutable tapAssetId;

53:       uint256 public immutable wethAssetId;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/Penrose.sol#L45

```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

84:       uint256 public constant EPOCH_DURATION = 7 days;

111:      uint256 public immutable HOST_CHAIN_ID;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L84

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

69:       uint256 public constant PHASE_1_DISCOUNT = 50 * 1e4; // 50%

84:       uint256 public constant PHASE_3_AMOUNT_PER_USER = 714;

85:       uint256 public constant PHASE_3_DISCOUNT = 50 * 1e4;

93:       uint256 public constant PHASE_4_DISCOUNT = 33 * 1e4;

95:       uint256 public constant EPOCH_DURATION = 2 days;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L69

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionBroker.sol

78:       uint256 public immutable EPOCH_DURATION; // 7 days = 604800

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L78

```solidity
File: tap-token-audit/contracts/tokens/TapOFT.sol

41:       uint256 public constant INITIAL_SUPPLY = 46_686_595 * 1e18; // Everything minus DSO

49:       uint256 public constant WEEK = 604800;

53:       uint256 public immutable emissionsStartTime;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L41

```solidity
File: tapioca-periph-audit/contracts/oracle/implementations/ARBTriCryptoOracle.sol

40:       uint256 public constant GAMMA0 = 28_000_000_000_000; // 2.8e-5

41:       uint256 public constant A0 = 2 * 3 ** 3 * 10_000;

42:       uint256 public constant DISCOUNT0 = 1_087_460_000_000_000; // 0.00108..

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/ARBTriCryptoOracle.sol#L40

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol

48:       uint256 public immutable pid;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L48

</details>

### [G&#x2011;22] Don't compare boolean expressions to boolean literals
`if (<x> == true)` => `if (<x>)`, `if (<x> == false)` => `if (!<x>)`

*There are 6 instances of this issue:*

```solidity
File: tapioca-bar-audit/contracts/Penrose.sol

175:              isSingularityMasterContractRegistered[mc] == true,

183:              isBigBangMasterContractRegistered[mc] == true,

322:              isSingularityMasterContractRegistered[mcAddress] == false,

344:              isBigBangMasterContractRegistered[mcAddress] == false,

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/Penrose.sol#L175

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

426:              userParticipation[msg.sender][subPhase] == false,

450:              userParticipation[tokenIDToAddress][3] == false,

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L426


### [G&#x2011;23] Multiple `if`-statements with mutually-exclusive conditions should be changed to `if`-`else` statements
If two conditions are the same, their blocks should be combined

*There are 2 instances of this issue:*

```solidity
File: tapioca-bar-audit/contracts/markets/Market.sol

264           if (borrowPartDecimals > 18) {
265               borrowPartScaled = borrowPart / (10 ** (borrowPartDecimals - 18));
266           }
267           if (borrowPartDecimals < 18) {
268               borrowPartScaled = borrowPart * (10 ** (18 - borrowPartDecimals));
269:          }

272           if (collateralPartDecimals > 18) {
273               collateralPartInAssetScaled =
274                   collateralPartInAsset /
275                   (10 ** (collateralPartDecimals - 18));
276           }
277           if (collateralPartDecimals < 18) {
278               collateralPartInAssetScaled =
279                   collateralPartInAsset *
280                   (10 ** (18 - collateralPartDecimals));
281:          }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/Market.sol#L264-L269


### [G&#x2011;24] `require()` or `revert()` statements that check input arguments should be at the top of the function
Checks that involve constants should come before checks that involve state variables, function calls, and calculations. By doing these checks first, the function is able to revert before wasting a Gcoldsload (**2100 gas***) in a function that may ultimately revert in the unhappy case.

*There are 3 instances of this issue:*

```solidity
File: tapioca-bar-audit/contracts/usd0/BaseUSDO.sol

/// @audit expensive op on line 115
116:          require(val != paused, "USDO: same state");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDO.sol#L116

```solidity
File: tap-token-audit/contracts/tokens/BaseTapOFT.sol

/// @audit expensive op on line 96
104:          require(duration > 0, "TapOFT: Small duration");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/BaseTapOFT.sol#L104

```solidity
File: tap-token-audit/contracts/tokens/TapOFT.sol

/// @audit expensive op on line 221
222:          require(_amount > 0, "amount not valid");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L222


### [G&#x2011;25] Empty blocks should be removed or emit something
The code should be refactored such that they no longer exist, or the block should do something useful, such as emitting an event or reverting. If the contract is meant to be extended, the contract should be `abstract` and the function signatures be added without any default implementation. If the block is an empty `if`-statement block to avoid doing subsequent checks in the else-if/else conditions, the else-if/else conditions should be nested under the negation of the if-statement, because they involve different classes of checks, which may lead to the introduction of errors when the code is later modified (`if (x) {...} else if (y) {...} else {...}` => `if (!x) { if (y) {...} else {...} }`). Empty `receive()`/`fallback() payable` functions that are not used, can be removed to save deployment gas.

*There are 23 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol

267:                  {} catch Error(string memory reason) {

282:                  {} catch Error(string memory reason) {

298:                  {} catch Error(string memory reason) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol#L267

```solidity
File: tapioca-bar-audit/contracts/usd0/modules/USDOMarketModule.sol

256:                  {} catch Error(string memory reason) {

271:                  {} catch Error(string memory reason) {

287:                  {} catch Error(string memory reason) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOMarketModule.sol#L256

```solidity
File: tapioca-bar-audit/contracts/usd0/modules/USDOOptionsModule.sol

257:                  {} catch Error(string memory reason) {

272:                  {} catch Error(string memory reason) {

288:                  {} catch Error(string memory reason) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOOptionsModule.sol#L257

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol

297:                  {} catch Error(string memory reason) {

312:                  {} catch Error(string memory reason) {

328:                  {} catch Error(string memory reason) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol#L297

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTMarketModule.sol

273:                  {} catch Error(string memory reason) {

288:                  {} catch Error(string memory reason) {

304:                  {} catch Error(string memory reason) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTMarketModule.sol#L273

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTOptionsModule.sol

272:                  {} catch Error(string memory reason) {

287:                  {} catch Error(string memory reason) {

303:                  {} catch Error(string memory reason) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTOptionsModule.sol#L272

```solidity
File: tap-token-audit/contracts/tokens/BaseTapOFT.sol

138:          try twTap.participate(to, amount, duration) {} catch Error(

344:              {} catch Error(string memory reason) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/BaseTapOFT.sol#L138

```solidity
File: tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol

707:          {} catch {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L707

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol

273:              try gmxVester.withdraw() {} catch {}

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol#L273

</details>

### [G&#x2011;26] Superfluous event fields
`block.timestamp` and `block.number` are added to event information by default so adding them manually wastes gas

*There is one instance of this issue:*

```solidity
File: tapioca-bar-audit/contracts/Penrose.sol

138:      event ProtocolWithdrawal(IMarket[] markets, uint256 timestamp);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/Penrose.sol#L138


### [G&#x2011;27] Use custom errors rather than `revert()`/`require()` strings to save gas
Custom errors are available from solidity version 0.8.4. Custom errors save [**~50 gas**](https://gist.github.com/IllIllI000/ad1bd0d29a0101b25e57c293b4b0c746) each time they're hit by [avoiding having to allocate and store the revert string](https://blog.soliditylang.org/2021/04/21/custom-errors/#errors-in-depth). Not defining the strings also save deployment gas

*There are 244 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

133           require(
134               address(_collateral) != address(0) &&
135                   address(_asset) != address(0) &&
136                   address(_oracle) != address(0),
137               "BigBang: bad pair"
138:          );

219:              require(success || !revertOnFail, _getRevertMsg(result));

344:          require(penrose.swappers(swapper), "SGL: Invalid swapper");

371:          require(amountOut >= minAmountOut, "SGL: not enough");

391:          require(penrose.swappers(swapper), "SGL: Invalid swapper");

413:          require(amountOut >= minAmountOut, "SGL: not enough");

476:                  require(_minDebtRate < maxDebtRate, "BigBang: not valid");

482:                  require(_maxDebtRate > minDebtRate, "BigBang: not valid");

496                   require(
497                       _liquidationMultiplier < FEE_PRECISION,
498                       "BigBang: not valid"
499:                  );

593:          require(penrose.swappers(swapper), "BigBang: Invalid swapper");

680:          require(liquidatedCount > 0, "SGL: no users found");

699               require(
700                   share <= yieldBox.balanceOf(address(this), _tokenId) - total,
701                   "BigBang: too much"
702:              );

750           require(
751               totalBorrowCap == 0 || totalBorrow.elastic <= totalBorrowCap,
752               "BigBang: borrow cap reached"
753:          );

820:          require(borrowAmount != 0, "SGL: solvent");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L133-L138

```solidity
File: tapioca-bar-audit/contracts/markets/MarketERC20.sol

142:              require(srcBalance >= amount, "ERC20: balance too low");

144:                  require(to != address(0), "ERC20: no zero address"); // Moved down so low balance calls safe some gas

167:              require(srcBalance >= amount, "ERC20: balance too low");

173                       require(
174                           spenderAllowance >= amount,
175                           "ERC20: allowance too low"
176:                      );

179:                  require(to != address(0), "ERC20: no zero address"); // Moved down so other failed calls safe some gas

261:          require(block.timestamp <= deadline, "ERC20Permit: expired deadline");

277:          require(signer == owner, "ERC20Permit: invalid signature");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/MarketERC20.sol#L142

```solidity
File: tapioca-bar-audit/contracts/markets/Market.sol

116:          require(!paused, "Market: paused");

126:          require(_isSolvent(from, exchangeRate), "Market: insolvent");

131:          require(!initialized, "Market: initialized");

143:          require(_val <= FEE_PRECISION, "Market: not valid");

172:              require(_borrowOpeningFee <= FEE_PRECISION, "Market: not valid");

193:              require(_callerFee <= FEE_PRECISION, "Market: not valid");

198:              require(_protocolFee <= FEE_PRECISION, "Market: not valid");

203               require(
204                   _liquidationBonusAmount < FEE_PRECISION,
205                   "Market: not valid"
206:              );

211:              require(_minLiquidatorReward < FEE_PRECISION, "Market: not valid");

212               require(
213                   _minLiquidatorReward < maxLiquidatorReward,
214                   "Market: not valid"
215:              );

220:              require(_maxLiquidatorReward < FEE_PRECISION, "Market: not valid");

221               require(
222                   _maxLiquidatorReward > minLiquidatorReward,
223                   "Market: not valid"
224:              );

234               require(
235                   _collateralizationRate <= FEE_PRECISION,
236                   "Market: not valid"
237:              );

246:          require(msg.sender == conservator, "Market: unauthorized");

247:          require(val != paused, "Market: same state");

344:              require(rate > 0, "Market: invalid rate");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/Market.sol#L116

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol

187               require(
188                   share <= yieldBox.balanceOf(address(this), _assetId) - total,
189                   "SGL: too much"
190:              );

240:          require(_totalAsset.base >= 1000, "SGL: min limit");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol#L187-L190

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLLendingCommon.sol

66            require(
67                totalBorrowCap == 0 || totalBorrow.base <= totalBorrowCap,
68                "SGL: borrow cap reached"
69:           );

75:           require(_totalAsset.base >= 1000, "SGL: min limit");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLendingCommon.sol#L66-L69

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLLeverage.sol

29            require(
30                penrose.swappers(ISwapper(externalData.swapper)),
31                "SGL: Invalid swapper"
32:           );

65            require(
66                penrose.swappers(ISwapper(externalData.swapper)),
67                "SGL: Invalid swapper"
68:           );

104:          require(penrose.swappers(swapper), "SGL: Invalid swapper");

126:          require(amountOut >= minAmountOut, "SGL: not enough");

155:          require(penrose.swappers(swapper), "SGL: Invalid swapper");

182:          require(amountOut >= minAmountOut, "SGL: not enough");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLeverage.sol#L29-L32

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol

152:          require(allBorrowAmount != 0, "SGL: solvent");

264:          require(borrowAmount != 0, "SGL: solvent");

327:          require(penrose.swappers(swapper), "SGL: Invalid swapper");

397:          require(liquidatedCount > 0, "SGL: no users found");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L152

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/Singularity.sol

100           require(
101               address(_collateral) != address(0) &&
102                   address(_asset) != address(0) &&
103                   address(_oracle) != address(0),
104               "SGL: bad pair"
105:          );

191:              require(success || !revertOnFail, _getRevertMsg(result));

507               require(
508                   _maximumTargetUtilization < FULL_UTILIZATION,
509                   "SGL: not valid"
510:              );

522               require(
523                   _minimumInterestPerSecond < maximumInterestPerSecond,
524                   "SGL: not valid"
525:              );

534               require(
535                   _maximumInterestPerSecond > minimumInterestPerSecond,
536                   "SGL: not valid"
537:              );

554               require(
555                   _lqCollateralizationRate <= FEE_PRECISION,
556                   "SGL: not valid"
557:              );

566:              require(_liquidationMultiplier < FEE_PRECISION, "SGL: not valid");

582:              require(_liquidationQueue.onlyOnce(), "SGL: LQ not initalized");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L100-L105

```solidity
File: tapioca-bar-audit/contracts/Penrose.sol

174           require(
175               isSingularityMasterContractRegistered[mc] == true,
176               "Penrose: MC not registered"
177:          );

182           require(
183               isBigBangMasterContractRegistered[mc] == true,
184               "Penrose: MC not registered"
185:          );

190:          require(!paused, "Penrose: paused");

237           require(
238               markets_.length == swappers_.length &&
239                   swappers_.length == swapData_.length,
240               "Penrose: length mismatch"
241:          );

242:          require(address(swappers_[0]) != address(0), "Penrose: zero address");

243:          require(address(markets_[0]) != address(0), "Penrose: zero address");

272:          require(msg.sender == conservator, "Penrose: unauthorized");

273:          require(val != paused, "Penrose: same state");

282:          require(_conservator != address(0), "Penrose: address not valid");

321           require(
322               isSingularityMasterContractRegistered[mcAddress] == false,
323               "Penrose: MC registered"
324:          );

343           require(
344               isBigBangMasterContractRegistered[mcAddress] == false,
345               "Penrose: MC registered"
346:          );

438               require(
439                   isSingularityMasterContractRegistered[
440                       masterContractOf[mc[i]]
441                   ] || isBigBangMasterContractRegistered[masterContractOf[mc[i]]],
442                   "Penrose: MC not registered"
443:              );

446:                  require(success[i], _getRevertMsg(result[i]));

505:          require(swappers[swapper], "Penrose: Invalid swapper");

506:          require(isMarketRegistered[address(market)], "Penrose: Invalid market");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/Penrose.sol#L174-L177

```solidity
File: tapioca-bar-audit/contracts/usd0/BaseUSDO.sol

97:           require(_val < FLASH_MINT_FEE_PRECISION, "USDO: fee too big");

106:          require(_conservator != address(0), "USDO: address not valid");

115:          require(msg.sender == conservator, "USDO: unauthorized");

116:          require(val != paused, "USDO: same state");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDO.sol#L97

```solidity
File: tapioca-bar-audit/contracts/usd0/USDO.sol

26:           require(!paused, "USDO: paused");

68:           require(token == address(this), "USDO: token not valid");

87:           require(token == address(this), "USDO: token not valid");

88:           require(maxFlashLoan(token) >= amount, "USDO: amount too big");

89:           require(amount > 0, "USDO: amount not valid");

93            require(
94                receiver.onFlashLoan(msg.sender, token, amount, fee, data) ==
95                    FLASH_MINT_CALLBACK_SUCCESS,
96                "USDO: failed"
97:           );

100:          require(_allowance >= (amount + fee), "USDO: repay not approved");

110:          require(allowedMinter[_getChainId()][msg.sender], "USDO: unauthorized");

119:          require(allowedBurner[_getChainId()][msg.sender], "USDO: unauthorized");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/USDO.sol#L26

```solidity
File: tapiocaz-audit/contracts/tOFT/BaseTOFT.sol

46:           require(block.chainid == hostChainID, "TOFT_host");

354               require(
355                   allowance(_fromAddress, msg.sender) >= _amount,
356                   "TOFT_allowed"
357:              );

364:          require(msg.value > 0, "TOFT_0");

381:          require(sent, "TOFT_failed");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFT.sol#L46

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol

281:          require(sent, "TOFT_failed");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol#L281

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol

56:           require(amount > 0, "TOFT_0");

98:           require(amount > 0, "TOFT_0");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol#L56

```solidity
File: tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol

93:           require(!balancers[msg.sender], "TOFT_auth");

105:          require(connectedChains[block.chainid], "TOFT_host");

106:          require(!balancers[msg.sender], "TOFT_auth");

142:          require(balancers[msg.sender], "TOFT_auth");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol#L93

```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

257:          require(_duration >= EPOCH_DURATION, "twTAP: Lock not a week");

313:          require(expiry < type(uint56).max, "twTAP: too long");

365:          require(msg.sender == address(tapOFT), "twTAP: only tapOFT");

390:          require(msg.sender == address(tapOFT), "twTAP: only tapOFT");

433           require(
434               lastProcessedWeek == currentWeek(),
435               "twTAP: Advance week first"
436:          );

473           require(
474               msg.sender == tokenOwner ||
475                   _to == tokenOwner ||
476                   isApprovedForAll(tokenOwner, msg.sender) ||
477                   getApproved(_tokenId) == msg.sender,
478               "twTAP: cannot claim"
479:          );

530:          require(position.expiry <= block.timestamp, "twTAP: Lock not expired");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L257

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

158:          require(aoTapOption.expiry > block.timestamp, "adb: Option expired");

167           require(
168               paymentTokenOracle.oracle != IOracle(address(0)),
169               "adb: Payment token not supported"
170:          );

174:          require(eligibleTapAmount >= _tapAmount, "adb: Too high");

177:          require(tapAmount >= 1e18, "adb: Too low");

203:          require(cachedEpoch > 0, "adb: Airdrop not started");

204:          require(cachedEpoch <= 4, "adb: Airdrop ended");

233:          require(aoTapOption.expiry > block.timestamp, "adb: Option expired");

242           require(
243               paymentTokenOracle.oracle != IOracle(address(0)),
244               "adb: Payment token not supported"
245:          );

246           require(
247               aoTAP.isApprovedOrOwner(msg.sender, _aoTAPTokenID),
248               "adb: Not approved or owner"
249:          );

255:          require(eligibleTapAmount >= _tapAmount, "adb: Too high");

258:          require(chosenAmount >= 1e18, "adb: Too low");

281           require(
282               block.timestamp >= lastEpochUpdate + EPOCH_DURATION,
283               "adb: too soon"
284:          );

329:          require(_users.length == _amounts.length, "adb: invalid input");

368           require(
369               paymentTokenBeneficiary != address(0),
370               "adb: Payment token beneficiary not set"
371:          );

392:          require(_eligibleAmount > 0, "adb: Not eligible");

419           require(
420               MerkleProof.verify(_merkleProof, phase2MerkleRoots[_role], leaf),
421               "adb: Not eligible"
422:          );

425           require(
426               userParticipation[msg.sender][subPhase] == false,
427               "adb: Already participated"
428:          );

447:          require(PCNFT.ownerOf(_tokenID) == msg.sender, "adb: Not eligible");

449           require(
450               userParticipation[tokenIDToAddress][3] == false,
451               "adb: Already participated"
452:          );

467:          require(_eligibleAmount > 0, "adb: Not eligible");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L158

```solidity
File: tap-token-audit/contracts/option-airdrop/aoTAP.sol

46:           require(msg.sender == broker, "AOTAP: only onlyBroker");

98            require(
99                _isApprovedOrOwner(msg.sender, _tokenId),
100               "AOTAP: only approved or owner"
101:          );

129           require(
130               _isApprovedOrOwner(msg.sender, _tokenId),
131               "AOTAP: only approved or owner"
132:          );

140:          require(broker == address(0), "AOTAP: only once");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/aoTAP.sol#L46

```solidity
File: tap-token-audit/contracts/options/oTAP.sol

40:           require(msg.sender == broker, "OTAP: only onlyBroker");

84            require(
85                _isApprovedOrOwner(msg.sender, _tokenId),
86                "OTAP: only approved or owner"
87:           );

116           require(
117               _isApprovedOrOwner(msg.sender, _tokenId),
118               "OTAP: only approved or owner"
119:          );

127:          require(broker == address(0), "OTAP: only once");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/oTAP.sol#L40

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionBroker.sol

170           require(
171               paymentTokenOracle.oracle != IOracle(address(0)),
172               "tOB: Payment token not supported"
173:          );

175:          require(isPositionActive, "tOB: Option expired");

187:          require(eligibleTapAmount >= _tapAmount, "tOB: Too high");

190:          require(tapAmount >= 1e18, "tOB: Too low");

219:          require(isPositionActive, "tOB: Position is not active");

220:          require(lock.lockDuration >= EPOCH_DURATION, "tOB: Duration too short");

224           require(
225               tOLP.isApprovedOrOwner(msg.sender, _tOLPTokenID),
226               "tOB: Not approved or owner"
227:          );

297:          require(oTAP.exists(_oTAPTokenID), "tOB: oTAP position does not exist");

303           require(
304               block.timestamp >= lock.lockTime + lock.lockDuration,
305               "tOB: Lock not expired"
306:          );

368           require(
369               paymentTokenOracle.oracle != IOracle(address(0)),
370               "tOB: Payment token not supported"
371:          );

372           require(
373               oTAP.isApprovedOrOwner(msg.sender, _oTAPTokenID),
374               "tOB: Not approved or owner"
375:          );

376:          require(isPositionActive, "tOB: Option expired");

388:          require(eligibleTapAmount >= _tapAmount, "tOB: Too high");

391:          require(chosenAmount >= 1e18, "tOB: Too low");

414           require(
415               block.timestamp >= lastEpochUpdate + EPOCH_DURATION,
416               "tOB: too soon"
417:          );

419:          require(singularities.length > 0, "tOB: No active singularities");

482           require(
483               paymentTokenBeneficiary != address(0),
484               "tOB: Payment token beneficiary not set"
485:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L170-L173

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol

177:          require(_lockDuration > 0, "tOLP: lock duration must be > 0");

178:          require(_amount > 0, "tOLP: amount must be > 0");

181:          require(sglAssetID > 0, "tOLP: singularity not active");

212:          require(_exists(_tokenId), "tOLP: Expired position");

215           require(
216               block.timestamp >=
217                   lockPosition.lockTime + lockPosition.lockDuration,
218               "tOLP: Lock not expired"
219:          );

220           require(
221               activeSingularities[_singularity].sglAssetID ==
222                   lockPosition.sglAssetID,
223               "tOLP: Invalid singularity"
224:          );

226           require(
227               _isApprovedOrOwner(msg.sender, _tokenId),
228               "tOLP: not owner nor approved"
229:          );

263           require(
264               activeSingularities[singularity].sglAssetID > 0,
265               "tOLP: not registered"
266:          );

281:          require(assetID > 0, "tOLP: invalid asset ID");

282           require(
283               activeSingularities[singularity].sglAssetID == 0,
284               "tOLP: already registered"
285:          );

301:          require(sglAssetID > 0, "tOLP: not registered");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L177

```solidity
File: tap-token-audit/contracts/tokens/BaseTapOFT.sol

104:          require(duration > 0, "TapOFT: Small duration");

222:          require(twTap.ownerOf(tokenID) == to, "TapOFT: Not owner");

307:          require(twTap.ownerOf(tokenID) == to, "TapOFT: Not owner");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/BaseTapOFT.sol#L104

```solidity
File: tap-token-audit/contracts/tokens/LTap.sol

47:           require(block.timestamp > lockedUntil, "Still locked");

54:           require(_lockedUntil <= maxLockedUntil, "Too late");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/LTap.sol#L47

```solidity
File: tap-token-audit/contracts/tokens/TapOFT.sol

89:           require(!paused, "TAP: paused");

118:          require(_lzEndpoint != address(0), "LZ endpoint not valid");

127               require(
128                   totalSupply() == INITIAL_SUPPLY,
129                   "initial supply not valid"
130:              );

153:          require(val != paused, "TAP: same state");

161:          require(_minter != address(0), "address not valid");

198:          require(_getChainId() == governanceChainIdentifier, "chain not valid");

221:          require(msg.sender == minter, "unauthorized");

222:          require(_amount > 0, "amount not valid");

225:          require(emissionForWeek[week] >= _amount, "exceeds allowable amount");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L89

```solidity
File: tap-token-audit/contracts/Vesting.sol

68:           require(_duration > 0, "Vesting: no vesting");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/Vesting.sol#L68

```solidity
File: tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol

205                   require(
206                       _action.call.length > 0,
207                       string.concat(
208                           "MagnetarV2: Missing call for action with index",
209                           string(abi.encode(i))
210                       )
211:                  );

714:          require(msg.value == valAccumulator, "MagnetarV2: value mismatch");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol#L205-L211

```solidity
File: tapioca-periph-audit/contracts/Magnetar/MagnetarV2Storage.sol

337:          require(_from == msg.sender, "MagnetarV2: operator not approved");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2Storage.sol#L337

```solidity
File: tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol

456                       require(
457                           participateData.tOLPTokenId == tOLPTokenId,
458                           "Magnetar: tOLPTokenId mismatch"
459:                      );

464               require(
465                   lockData.target != address(0),
466                   "Magnetar: lock target mismatch"
467:              );

468:              require(tOLPTokenId != 0, "Magnetar: tOLPTokenId 0");

510               require(
511                   removeAndRepayData.exitData.oTAPTokenID > 0,
512                   "Magnetar: oTAPTokenID 0"
513:              );

527               require(
528                   ownerOfTapTokenId == user || ownerOfTapTokenId == address(this),
529                   "Magnetar: oTAPTokenID owner mismatch"
530:              );

556                       require(
557                           tOLPId == removeAndRepayData.unlockData.tokenId,
558                           "Magnetar: tOLPId mismatch"
559:                      );

743:          require(withdrawData.length > 0, "MagnetarV2: withdrawData is empty");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L456-L459

```solidity
File: tapioca-periph-audit/contracts/Multicall/Multicall3.sol

90:           require(msg.value == valAccumulator, "Multicall3: value mismatch");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Multicall/Multicall3.sol#L90

```solidity
File: tapioca-periph-audit/contracts/Swapper/BaseSwapper.sol

102           require(
103               success && (data.length == 0 || abi.decode(data, (bool))),
104               "BaseSwapper::safeApprove: approve failed"
105:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/BaseSwapper.sol#L102-L105

```solidity
File: tapioca-periph-audit/contracts/Swapper/CurveSwapper.sol

156:          require(outputAmount >= amountOutMin, "insufficient-amount-out");

164:          require(balanceAfter > balanceBefore, "swap failed");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/CurveSwapper.sol#L156

```solidity
File: tapioca-periph-audit/contracts/TapiocaDeployer/TapiocaDeployer.sol

28            require(
29                address(this).balance >= amount,
30                "Create2: insufficient balance"
31:           );

32            require(
33                bytecode.length != 0,
34                string.concat(
35                    "Create2: bytecode length is zero for contract ",
36                    contractName
37                )
38:           );

43            require(
44                addr != address(0),
45                string.concat(
46                    "Create2: Failed on deploy for contract ",
47                    contractName
48                )
49:           );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/TapiocaDeployer/TapiocaDeployer.sol#L28-L31

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol

255:          require(available >= amount, "AaveStrategy: amount not valid");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol#L255

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol

184           require(
185               lpBalanceAfter > lpBalanceBefore,
186               "BalancerStrategy: vault deposit failed"
187:          );

196:          require(available >= amount, "BalancerStrategy: amount not valid");

208           require(
209               amount <= wrappedNative.balanceOf(address(this)),
210               "BalancerStrategy: not enough"
211:          );

263           require(
264               wrappedNativeBalanceAfter > wrappedNativeBalanceBefore,
265               "BalancerStrategy: vault withdrawal failed"
266:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L184-L187

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol

141:          require(available >= amount, "CompoundStrategy: amount not valid");

155           require(
156               wrappedNative.balanceOf(address(this)) >= amount,
157               "CompoundStrategy: not enough"
158:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol#L141

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol

245           require(
246               tempData.rewardContracts.length == tempData.tokens.length,
247               "ConvexTricryptoStrategy: claim data not valid"
248:          );

249           require(
250               tempData.rewardContracts.length > 0,
251               "ConvexTricryptoStrategy: nothing to claim for"
252:          );

325           require(
326               available >= amount,
327               "ConvexTricryptoStrategy: amount not valid"
328:          );

340           require(
341               wrappedNative.balanceOf(address(this)) >= amount,
342               "ConvexTricryptoStrategy: not enough"
343:          );

363           require(
364               successEmtptyApproval,
365               "OperationsLib::safeApprove: approval reset failed"
366:          );

376           require(
377               success && (data.length == 0 || abi.decode(data, (bool))),
378               "OperationsLib::safeApprove: approve failed"
379:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L245-L248

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol

234:          require(available >= amount, "TricryptoLPStrategy: amount not valid");

242           require(
243               lpToken.balanceOf(address(this)) >= amount,
244               "TricryptoLPStrategy: not enough"
245:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L234

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol

221           require(
222               available >= amount,
223               "TricryptoNativeStrategy: amount not valid"
224:          );

235           require(
236               wrappedNative.balanceOf(address(this)) >= amount,
237               "TricryptoNativeStrategy: not enough"
238:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L221-L224

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol

60:           require(address(weth) == _gmxRewardRouter.weth(), "WETH mismatch");

62:           require(_glpRewardRouter.gmx() == address(0), "Bad GLP reward router");

66:           require(_gmx != address(0), "Bad GMX reward router");

91:           require(msg.sender == address(gmxWethPool), "Not the pool");

333:          require(amountOut * priceDenom >= gmxAmount * priceNum, "Not enough");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol#L60

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol

131:              require(!stEth.isStakingPaused(), "LidoStrategy: staking paused");

146:          require(available >= amount, "LidoStrategy: amount not valid");

162:          require(queued >= amount, "LidoStrategy: not enough");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol#L131

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol

246:          require(available >= amount, "StargateStrategy: amount not valid");

262           require(
263               amount <= wrappedNative.balanceOf(address(this)),
264               "Stargate: not enough"
265:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L246

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol

137:          require(available >= amount, "YearnStrategy: amount not valid");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol#L137

```solidity
File: YieldBox/contracts/BoringMath.sol

6:            require(a <= type(uint128).max, "BoringMath: uint128 Overflow");

11:           require(a <= type(uint64).max, "BoringMath: uint64 Overflow");

16:           require(a <= type(uint32).max, "BoringMath: uint32 Overflow");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/BoringMath.sol#L6

```solidity
File: YieldBox/contracts/NativeTokenFactory.sol

46:           require(msg.sender == owner[tokenId], "NTF: caller is not the owner");

59:               require(newOwner != address(0) || renounce, "NTF: zero address");

77:           require(msg.sender == _pendingOwner, "NTF: caller != pending owner");

117:          require(assets[tokenId].tokenType == TokenType.Native, "NTF: Not native");

139:          require(assets[tokenId].tokenType == TokenType.Native, "NTF: Not native");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/NativeTokenFactory.sol#L46

```solidity
File: YieldBox/contracts/YieldBoxPermit.sol

51:           require(block.timestamp <= deadline, "YieldBoxPermit: expired deadline");

58:           require(signer == owner, "YieldBoxPermit: invalid signature");

80:           require(block.timestamp <= deadline, "YieldBoxPermit: expired deadline");

87:           require(signer == owner, "YieldBoxPermit: invalid signature");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxPermit.sol#L51

```solidity
File: YieldBox/contracts/YieldBox.sol

127:          require(asset.tokenType != TokenType.Native && asset.tokenType != TokenType.ERC721, "YieldBox: can't deposit type");

175:          require(asset.tokenType == TokenType.ERC721, "YieldBox: not ERC721");

199:          require(asset.tokenType == TokenType.ERC20 && asset.contractAddress == address(wrappedNative), "YieldBox: not wrappedNative");

232:          require(asset.tokenType != TokenType.Native, "YieldBox: can't withdraw Native");

317:          require(to != address(0), "No 0 address");

340:              require(tos[i] != address(0), "YieldBox: to not set"); // To avoid a bad UI from burning funds

360:          require(operator != address(0), "YieldBox: operator not set"); // Important for security

361:          require(operator != address(this), "YieldBox: can't approve yieldBox");

382:          require(operator != address(0), "YieldBox: operator not set"); // Important for security

383:          require(operator != address(this), "YieldBox: can't approve yieldBox");

395:          require(assetId < assetCount(), "YieldBox: asset not valid");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBox.sol#L127

</details>

### [G&#x2011;28] Functions guaranteed to revert when called by normal users can be marked `payable`
If a function modifier such as `onlyOwner` is used, the function will revert if a normal user tries to pay the function. Marking the function as `payable` will lower the gas cost for legitimate callers because the compiler will not include checks for whether a payment was provided. The extra opcodes avoided are 
`CALLVALUE`(2),`DUP1`(3),`ISZERO`(3),`PUSH2`(3),`JUMPI`(10),`PUSH1`(3),`DUP1`(3),`REVERT`(0),`JUMPDEST`(1),`POP`(2), which costs an average of about **21 gas per call** to the function, in addition to the extra deployment cost

*There are 87 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

101:      function init(bytes calldata data) external onlyOnce {

442       function refreshPenroseFees(
443           address
444:      ) external onlyOwner notPaused returns (uint256 feeShares) {

466       function setBigBangConfig(
467           uint256 _minDebtRate,
468           uint256 _maxDebtRate,
469           uint256 _debtRateAgainstEthMarket,
470           uint256 _liquidationMultiplier
471:      ) external onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L101

```solidity
File: tapioca-bar-audit/contracts/markets/Market.sol

142:      function setBorrowOpeningFee(uint256 _val) external onlyOwner {

151:      function setBorrowCap(uint256 _cap) external notPaused onlyOwner {

158       function setMarketConfig(
159           uint256 _borrowOpeningFee,
160           IOracle _oracle,
161           bytes calldata _oracleData,
162           address _conservator,
163           uint256 _callerFee,
164           uint256 _protocolFee,
165           uint256 _liquidationBonusAmount,
166           uint256 _minLiquidatorReward,
167           uint256 _maxLiquidatorReward,
168           uint256 _totalBorrowCap,
169           uint256 _collateralizationRate
170:      ) external onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/Market.sol#L142

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/Singularity.sol

62:       function init(bytes calldata data) external onlyOnce {

477       function refreshPenroseFees(
478           address feeTo
479:      ) external onlyOwner notPaused returns (uint256 feeShares) {

489       function setSingularityConfig(
490           uint256 _lqCollateralizationRate,
491           uint256 _liquidationMultiplier,
492           uint256 _minimumTargetUtilization,
493           uint256 _maximumTargetUtilization,
494           uint64 _minimumInterestPerSecond,
495           uint64 _maximumInterestPerSecond,
496           uint256 _interestElasticity
497:      ) external onlyOwner {

576       function setLiquidationQueueConfig(
577           ILiquidationQueue _liquidationQueue,
578           address _bidExecutionSwapper,
579           address _usdoSwapper
580:      ) external onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L62

```solidity
File: tapioca-bar-audit/contracts/Penrose.sol

256:      function setBigBangEthMarketDebtRate(uint256 _rate) external onlyOwner {

263:      function setBigBangEthMarket(address _market) external onlyOwner {

281:      function setConservator(address _conservator) external onlyOwner {

291:      function setUsdoToken(address _usdoToken) external onlyOwner {

317       function registerSingularityMasterContract(
318           address mcAddress,
319           IPenrose.ContractType contractType_
320:      ) external onlyOwner {

339       function registerBigBangMasterContract(
340           address mcAddress,
341           IPenrose.ContractType contractType_
342:      ) external onlyOwner {

381       function addSingularity(
382           address mc,
383           address _contract
384:      ) external onlyOwner registeredSingularityMasterContract(mc) {

414       function addBigBang(
415           address mc,
416           address _contract
417:      ) external onlyOwner registeredBigBangMasterContract(mc) {

424       function executeMarketFn(
425           address[] calldata mc,
426           bytes[] memory data,
427           bool forceSuccess
428       )
429           external
430           onlyOwner
431           notPaused
432:          returns (bool[] memory success, bytes[] memory result)

455:      function setFeeTo(address feeTo_) external onlyOwner {

464:      function setSwapper(ISwapper swapper, bool enable) external onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/Penrose.sol#L256

```solidity
File: tapioca-bar-audit/contracts/usd0/BaseUSDO.sol

88:       function setMaxFlashMintable(uint256 _val) external onlyOwner {

96:       function setFlashMintFee(uint256 _val) external onlyOwner {

105:      function setConservator(address _conservator) external onlyOwner {

125:      function setMinterStatus(address _for, bool _status) external onlyOwner {

134:      function setBurnerStatus(address _for, bool _status) external onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDO.sol#L88

```solidity
File: tapiocaz-audit/contracts/Balancer.sol

219       function initConnectedOFT(
220           address _srcOft,
221           uint16 _dstChainId,
222           address _dstOft,
223           bytes memory _ercData
224:      ) external onlyOwner {

250       function addRebalanceAmount(
251           address _srcOft,
252           uint16 _dstChainId,
253           uint256 _amount
254:      ) external onlyValidDestination(_srcOft, _dstChainId) onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/Balancer.sol#L219-L224

```solidity
File: tapiocaz-audit/contracts/TapiocaWrapper.sol

154       function createTOFT(
155           address _erc20,
156           bytes calldata _bytecode,
157           bytes32 _salt,
158           bool _linked
159:      ) external onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/TapiocaWrapper.sol#L154-L159

```solidity
File: tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol

116       function updateConnectedChain(
117           uint256 _chain,
118           bool _status
119:      ) external onlyOwner {

131       function updateBalancerState(
132           address _balancer,
133           bool _status
134:      ) external onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol#L116-L119

```solidity
File: tapiocaz-audit/contracts/tOFT/TapiocaOFT.sol

85        function unwrap(
86            address _toAddress,
87            uint256 _amount
88:       ) external onlyHostChain {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/TapiocaOFT.sol#L85-L88

```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

455:      function addRewardToken(IERC20 token) external onlyOwner returns (uint256) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L455

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

308       function setTapOracle(
309           IOracle _tapOracle,
310           bytes calldata _tapOracleData
311:      ) external onlyOwner {

318       function setPhase2MerkleRoots(
319           bytes32[4] calldata _merkleRoots
320:      ) external onlyOwner {

324       function registerUserForPhase(
325           uint256 _phase,
326           address[] calldata _users,
327           uint256[] calldata _amounts
328:      ) external onlyOwner {

344       function setPaymentToken(
345           ERC20 _paymentToken,
346           IOracle _oracle,
347           bytes calldata _oracleData
348:      ) external onlyOwner {

357       function setPaymentTokenBeneficiary(
358           address _paymentTokenBeneficiary
359:      ) external onlyOwner {

365       function collectPaymentTokens(
366           address[] calldata _paymentTokens
367:      ) external onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L308-L311

```solidity
File: tap-token-audit/contracts/option-airdrop/aoTAP.sol

109       function mint(
110           address _to,
111           uint128 _expiry,
112           uint128 _discount,
113           uint256 _amount
114:      ) external onlyBroker returns (uint256 tokenId) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/aoTAP.sol#L109-L114

```solidity
File: tap-token-audit/contracts/options/oTAP.sol

96        function mint(
97            address _to,
98            uint128 _expiry,
99            uint128 _discount,
100           uint256 _tOLP
101:      ) external onlyBroker returns (uint256 tokenId) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/oTAP.sol#L96-L101

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionBroker.sol

446       function setTapOracle(
447           IOracle _tapOracle,
448           bytes calldata _tapOracleData
449:      ) external onlyOwner {

458       function setPaymentToken(
459           ERC20 _paymentToken,
460           IOracle _oracle,
461           bytes calldata _oracleData
462:      ) external onlyOwner {

471       function setPaymentTokenBeneficiary(
472           address _paymentTokenBeneficiary
473:      ) external onlyOwner {

479       function collectPaymentTokens(
480           address[] calldata _paymentTokens
481:      ) external onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L446-L449

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol

259       function setSGLPoolWEight(
260           IERC20 singularity,
261           uint256 weight
262:      ) external onlyOwner updateTotalSGLPoolWeights {

276       function registerSingularity(
277           IERC20 singularity,
278           uint256 assetID,
279           uint256 weight
280:      ) external onlyOwner updateTotalSGLPoolWeights {

297       function unregisterSingularity(
298           IERC20 singularity
299:      ) external onlyOwner updateTotalSGLPoolWeights {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L259-L262

```solidity
File: tap-token-audit/contracts/tokens/BaseTapOFT.sol

326:      function setTwTap(address _twTap) external onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/BaseTapOFT.sol#L326

```solidity
File: tap-token-audit/contracts/tokens/LTap.sol

53:       function setLockedUntil(uint256 _lockedUntil) external onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/LTap.sol#L53

```solidity
File: tap-token-audit/contracts/tokens/TapOFT.sol

140       function setGovernanceChainIdentifier(
141           uint256 _identifier
142:      ) external onlyOwner {

152:      function updatePause(bool val) external onlyOwner {

160:      function setMinter(address _minter) external onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L140-L142

```solidity
File: tap-token-audit/contracts/Vesting.sol

130:      function registerUser(address _user, uint256 _amount) external onlyOwner {

151:      function init(IERC20 _token, uint256 _seededAmount) external onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/Vesting.sol#L130

```solidity
File: tapioca-periph-audit/contracts/Swapper/UniswapV3Swapper.sol

61:       function setPoolFee(uint24 _newFee) external onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/UniswapV3Swapper.sol#L61

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol

122:      function setDepositThreshold(uint256 amount) external onlyOwner {

129:      function setMultiSwapper(address _swapper) external onlyOwner {

209:      function emergencyWithdraw() external onlyOwner returns (uint256 result) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol#L122

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol

109:      function setDepositThreshold(uint256 amount) external onlyOwner {

120:      function emergencyWithdraw() external onlyOwner returns (uint256 result) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L109

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol

89:       function setDepositThreshold(uint256 amount) external onlyOwner {

100:      function emergencyWithdraw() external onlyOwner returns (uint256 result) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol#L89

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol

148:      function emergencyWithdraw() external onlyOwner returns (uint256 result) {

163:      function setDepositThreshold(uint256 amount) external onlyOwner {

170:      function setMultiSwapper(address _swapper) external onlyOwner {

179:      function setTricryptoLPGetter(address _lpGetter) external onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L148

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol

134:      function setDepositThreshold(uint256 amount) external onlyOwner {

141:      function setMultiSwapper(address _swapper) external onlyOwner {

150:      function setTricryptoLPGetter(address _lpGetter) external onlyOwner {

199:      function emergencyWithdraw() external onlyOwner returns (uint256 result) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L134

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol

125:      function setDepositThreshold(uint256 amount) external onlyOwner {

132:      function setMultiSwapper(address _swapper) external onlyOwner {

141:      function setTricryptoLPGetter(address _lpGetter) external onlyOwner {

182:      function emergencyWithdraw() external onlyOwner returns (uint256 result) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L125

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol

104:      function harvestGmx(uint256 priceNum, uint256 priceDenom) public onlyOwner {

113:      function setFeeRecipient(address recipient) external onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol#L104

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol

93:       function setDepositThreshold(uint256 amount) external onlyOwner {

104:      function emergencyWithdraw() external onlyOwner returns (uint256 result) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol#L93

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol

142:      function setDepositThreshold(uint256 amount) external onlyOwner {

149:      function setMultiSwapper(address _swapper) external onlyOwner {

193:      function emergencyWithdraw() external onlyOwner returns (uint256 result) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L142

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol

90:       function setDepositThreshold(uint256 amount) external onlyOwner {

101:      function emergencyWithdraw() external onlyOwner returns (uint256 result) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol#L90

```solidity
File: YieldBox/contracts/NativeTokenFactory.sol

56:       function transferOwnership(uint256 tokenId, address newOwner, bool direct, bool renounce) public onlyOwner(tokenId) {

109:      function mint(uint256 tokenId, address to, uint256 amount) public onlyOwner(tokenId) {

127:      function batchMint(uint256 tokenId, address[] calldata tos, uint256[] calldata amounts) public onlyOwner(tokenId) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/NativeTokenFactory.sol#L56

</details>

### [G&#x2011;29] Constructors can be marked `payable`
Payable functions cost less gas to execute, since the compiler does not have to add extra checks to ensure that a payment wasn't provided. A constructor can safely be marked as payable, since only the deployer would be able to pass funds, and the project itself would not pass any funds.

*There are 50 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

98:       constructor() MarketERC20("Tapioca BigBang") {}

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L98

```solidity
File: tapioca-bar-audit/contracts/markets/MarketERC20.sol

109:      constructor(string memory name) EIP712(name, "1") {}

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/MarketERC20.sol#L109

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLStorage.sol

148:      constructor() MarketERC20("Tapioca Singularity") {}

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLStorage.sol#L148

```solidity
File: tapioca-bar-audit/contracts/Penrose.sol

86        constructor(
87            YieldBox _yieldBox,
88            IERC20 tapToken_,
89            IERC20 wethToken_,
90:           address _owner

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/Penrose.sol#L86-L90

```solidity
File: tapioca-bar-audit/contracts/usd0/BaseUSDO.sol

67        constructor(
68            address _lzEndpoint,
69            IYieldBoxBase _yieldBox,
70            address _owner,
71            address payable _leverageModule,
72            address payable _marketModule,
73            address payable _optionsModule
74:       ) BaseUSDOStorage(_lzEndpoint, _yieldBox) ERC20Permit("USDO") {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDO.sol#L67-L74

```solidity
File: tapioca-bar-audit/contracts/usd0/BaseUSDOStorage.sol

70        constructor(
71            address _lzEndpoint,
72            IYieldBoxBase _yieldBox
73:       ) OFTV2("USDO", "USDO", 8, _lzEndpoint) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDOStorage.sol#L70-L73

```solidity
File: tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol

22        constructor(
23            address _lzEndpoint,
24            IYieldBoxBase _yieldBox
25:       ) BaseUSDOStorage(_lzEndpoint, _yieldBox) {}

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol#L22-L25

```solidity
File: tapioca-bar-audit/contracts/usd0/modules/USDOMarketModule.sol

25        constructor(
26            address _lzEndpoint,
27            IYieldBoxBase _yieldBox
28:       ) BaseUSDOStorage(_lzEndpoint, _yieldBox) {}

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOMarketModule.sol#L25-L28

```solidity
File: tapioca-bar-audit/contracts/usd0/modules/USDOOptionsModule.sol

19        constructor(
20            address _lzEndpoint,
21            IYieldBoxBase _yieldBox
22:       ) BaseUSDOStorage(_lzEndpoint, _yieldBox) {}

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOOptionsModule.sol#L19-L22

```solidity
File: tapioca-bar-audit/contracts/usd0/USDO.sol

35        constructor(
36            address _lzEndpoint,
37            IYieldBoxBase _yieldBox,
38            address _owner,
39            address payable _leverageModule,
40            address payable _marketModule,
41            address payable _optionsModule
42        )
43            BaseUSDO(
44                _lzEndpoint,
45                _yieldBox,
46                _owner,
47                _leverageModule,
48                _marketModule,
49                _optionsModule
50:           )

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/USDO.sol#L35-L50

```solidity
File: tapiocaz-audit/contracts/Balancer.sol

122       constructor(
123           address _routerETH,
124           address _router,
125           address _owner
126:      ) Owned(_owner) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/Balancer.sol#L122-L126

```solidity
File: tapiocaz-audit/contracts/TapiocaWrapper.sol

67:       constructor(address _owner) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/TapiocaWrapper.sol#L67

```solidity
File: tapiocaz-audit/contracts/tOFT/BaseTOFT.sol

50        constructor(
51            address _lzEndpoint,
52            address _erc20,
53            IYieldBoxBase _yieldBox,
54            string memory _name,
55            string memory _symbol,
56            uint8 _decimal,
57            uint256 _hostChainID,
58            address payable _leverageModule,
59            address payable _strategyModule,
60            address payable _marketModule,
61            address payable _optionsModule
62        )
63            BaseTOFTStorage(
64                _lzEndpoint,
65                _erc20,
66                _yieldBox,
67                _name,
68                _symbol,
69                _decimal,
70                _hostChainID
71            )
72:           ERC20Permit(string(abi.encodePacked("TapiocaOFT-", _name)))

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFT.sol#L50-L72

```solidity
File: tapiocaz-audit/contracts/tOFT/BaseTOFTStorage.sol

45        constructor(
46            address _lzEndpoint,
47            address _erc20,
48            IYieldBoxBase _yieldBox,
49            string memory _name,
50            string memory _symbol,
51            uint8 _decimal,
52            uint256 _hostChainID
53        )
54            OFTV2(
55                string(abi.encodePacked("TapiocaOFT-", _name)),
56                string(abi.encodePacked("t", _symbol)),
57                _decimal / 2,
58                _lzEndpoint
59:           )

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFTStorage.sol#L45-L59

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol

25        constructor(
26            address _lzEndpoint,
27            address _erc20,
28            IYieldBoxBase _yieldBox,
29            string memory _name,
30            string memory _symbol,
31            uint8 _decimal,
32            uint256 _hostChainID
33        )
34            BaseTOFTStorage(
35                _lzEndpoint,
36                _erc20,
37                _yieldBox,
38                _name,
39                _symbol,
40                _decimal,
41                _hostChainID
42:           )

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol#L25-L42

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTMarketModule.sol

24        constructor(
25            address _lzEndpoint,
26            address _erc20,
27            IYieldBoxBase _yieldBox,
28            string memory _name,
29            string memory _symbol,
30            uint8 _decimal,
31            uint256 _hostChainID
32        )
33            BaseTOFTStorage(
34                _lzEndpoint,
35                _erc20,
36                _yieldBox,
37                _name,
38                _symbol,
39                _decimal,
40                _hostChainID
41:           )

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTMarketModule.sol#L24-L41

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTOptionsModule.sol

19        constructor(
20            address _lzEndpoint,
21            address _erc20,
22            IYieldBoxBase _yieldBox,
23            string memory _name,
24            string memory _symbol,
25            uint8 _decimal,
26            uint256 _hostChainID
27        )
28            BaseTOFTStorage(
29                _lzEndpoint,
30                _erc20,
31                _yieldBox,
32                _name,
33                _symbol,
34                _decimal,
35                _hostChainID
36:           )

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTOptionsModule.sol#L19-L36

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol

20        constructor(
21            address _lzEndpoint,
22            address _erc20,
23            IYieldBoxBase _yieldBox,
24            string memory _name,
25            string memory _symbol,
26            uint8 _decimal,
27            uint256 _hostChainID
28        )
29            BaseTOFTStorage(
30                _lzEndpoint,
31                _erc20,
32                _yieldBox,
33                _name,
34                _symbol,
35                _decimal,
36                _hostChainID
37:           )

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol#L20-L37

```solidity
File: tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol

49        constructor(
50            address _lzEndpoint,
51            address _erc20,
52            IYieldBoxBase _yieldBox,
53            string memory _name,
54            string memory _symbol,
55            uint8 _decimal,
56            uint256 _hostChainID,
57            address payable _leverageModule,
58            address payable _strategyModule,
59            address payable _marketModule,
60            address payable _optionsModule
61        )
62            BaseTOFT(
63                _lzEndpoint,
64                _erc20,
65                _yieldBox,
66                _name,
67                _symbol,
68                _decimal,
69                _hostChainID,
70                _leverageModule,
71                _strategyModule,
72                _marketModule,
73                _optionsModule
74:           )

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol#L49-L74

```solidity
File: tapiocaz-audit/contracts/tOFT/TapiocaOFT.sol

33        constructor(
34            address _lzEndpoint,
35            address _erc20,
36            IYieldBoxBase _yieldBox,
37            string memory _name,
38            string memory _symbol,
39            uint8 _decimal,
40            uint256 _hostChainID,
41            address payable _leverageModule,
42            address payable _strategyModule,
43            address payable _marketModule,
44            address payable _optionsModule
45        )
46            BaseTOFT(
47                _lzEndpoint,
48                _erc20,
49                _yieldBox,
50                _name,
51                _symbol,
52                _decimal,
53                _hostChainID,
54                _leverageModule,
55                _strategyModule,
56                _marketModule,
57                _optionsModule
58:           )

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/TapiocaOFT.sol#L33-L58

```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

115       constructor(
116           address payable _tapOFT,
117           address _owner,
118           address _layerZeroEndpoint,
119           uint256 _hostChainID,
120           uint256 _minGas
121       )
122           ONFT721("Time Weighted TAP", "twTAP", _minGas, _layerZeroEndpoint)
123:          ERC721Permit("Time Weighted TAP")

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L115-L123

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

98        constructor(
99            address _aoTAP,
100           address payable _tapOFT,
101           address _pcnft,
102           address _paymentTokenBeneficiary,
103:          address _owner

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L98-L103

```solidity
File: tap-token-audit/contracts/option-airdrop/aoTAP.sol

39        constructor(
40            address _owner
41:       ) ERC721("Airdrop Option TAP", "aoTAP") ERC721Permit("Airdrop Option TAP") {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/aoTAP.sol#L39-L41

```solidity
File: tap-token-audit/contracts/options/oTAP.sol

37:       constructor() ERC721("Option TAP", "oTAP") ERC721Permit("Option TAP") {}

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/oTAP.sol#L37

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionBroker.sol

81        constructor(
82            address _tOLP,
83            address _oTAP,
84            address payable _tapOFT,
85            address _paymentTokenBeneficiary,
86            uint256 _epochDuration,
87:           address _owner

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L81-L87

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol

67        constructor(
68            address _yieldBox,
69            address _owner
70        )
71            ERC721("TapiocaOptionLiquidityProvision", "tOLP")
72:           ERC721Permit("TapiocaOptionLiquidityProvision")

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L67-L72

```solidity
File: tap-token-audit/contracts/tokens/BaseTapOFT.sol

44        constructor(
45            string memory _name,
46            string memory _symbol,
47            uint8 _sharedDec,
48            address _lzEndpoint
49:       ) OFTV2(_name, _symbol, _sharedDec, _lzEndpoint) {}

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/BaseTapOFT.sol#L44-L49

```solidity
File: tap-token-audit/contracts/tokens/LTap.sol

32        constructor(
33            IERC20 _tapToken,
34            uint256 _maxLockedUntil
35:       ) ERC20("LTAP", "LTAP") ERC20Permit("LTAP") {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/LTap.sol#L32-L35

```solidity
File: tap-token-audit/contracts/tokens/TapOFT.sol

107       constructor(
108           address _lzEndpoint,
109           address _contributors,
110           address _earlySupporters,
111           address _supporters,
112           address _lbp,
113           address _dao,
114           address _airdrop,
115           uint256 _governanceChainId,
116           address _conservator
117:      ) BaseTapOFT("TapOFT", "TAP", 8, _lzEndpoint) ERC20Permit("TapOFT") {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L107-L117

```solidity
File: tap-token-audit/contracts/Vesting.sol

67:       constructor(uint256 _cliff, uint256 _duration, address _owner) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/Vesting.sol#L67

```solidity
File: tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol

44:       constructor(address _owner, address payable _marketModule) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol#L44

```solidity
File: tapioca-periph-audit/contracts/oracle/implementations/ARBTriCryptoOracle.sol

44        constructor(
45            string memory __name,
46            string memory __symbol,
47            ICurvePool pool,
48            AggregatorV2V3Interface btcFeed,
49            AggregatorV2V3Interface ethFeed,
50            AggregatorV2V3Interface usdtFeed,
51:           AggregatorV2V3Interface wbtcFeed

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/ARBTriCryptoOracle.sol#L44-L51

```solidity
File: tapioca-periph-audit/contracts/oracle/implementations/GLPOracle.sol

10:       constructor(IGmxGlpManager glpManager_) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/GLPOracle.sol#L10

```solidity
File: tapioca-periph-audit/contracts/oracle/implementations/SGOracle.sol

30        constructor(
31            string memory __name,
32            string memory __symbol,
33            IStargatePool pool,
34:           AggregatorV2V3Interface _underlying

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/SGOracle.sol#L30-L34

```solidity
File: tapioca-periph-audit/contracts/oracle/Seer.sol

12        constructor(
13            string memory __name,
14            string memory __symbol,
15            uint8 _decimals,
16            address[] memory addressInAndOutUni,
17            IUniswapV3Pool[] memory _circuitUniswap,
18            uint8[] memory _circuitUniIsMultiplied,
19            uint32 _twapPeriod,
20            uint16 observationLength,
21            uint8 _uniFinalCurrency,
22            address[] memory _circuitChainlink,
23            uint8[] memory _circuitChainIsMultiplied,
24            uint32 _stalePeriod,
25            address[] memory guardians,
26            bytes32 _description
27        )
28            OracleMulti(
29                addressInAndOutUni,
30                _circuitUniswap,
31                _circuitUniIsMultiplied,
32                _twapPeriod,
33                observationLength,
34                _uniFinalCurrency,
35                _circuitChainlink,
36                _circuitChainIsMultiplied,
37                _stalePeriod,
38                guardians,
39                _description
40:           )

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/Seer.sol#L12-L40

```solidity
File: tapioca-periph-audit/contracts/Swapper/CurveSwapper.sol

36        constructor(
37            ICurvePool _curvePool,
38            IYieldBox _yieldBox
39:       ) validAddress(address(_curvePool)) validAddress(address(_yieldBox)) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/CurveSwapper.sol#L36-L39

```solidity
File: tapioca-periph-audit/contracts/Swapper/UniswapV2Swapper.sol

30        constructor(
31            address _router,
32            address _factory,
33            IYieldBox _yieldBox
34        )
35            validAddress(_router)
36            validAddress(_factory)
37:           validAddress(address(_yieldBox))

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/UniswapV2Swapper.sol#L30-L37

```solidity
File: tapioca-periph-audit/contracts/Swapper/UniswapV3Swapper.sol

45        constructor(
46            IYieldBox _yieldBox,
47            ISwapRouter _swapRouter,
48            IUniswapV3Factory _factory
49        )
50            validAddress(address(_yieldBox))
51            validAddress(address(_swapRouter))
52:           validAddress(address(_factory))

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/UniswapV3Swapper.sol#L45-L52

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol

58        constructor(
59            IYieldBox _yieldBox,
60            address _token,
61            address _lendingPool,
62            address _incentivesController,
63            address _receiptToken,
64            address _multiSwapper
65:       ) BaseERC20Strategy(_yieldBox, _token) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol#L58-L65

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol

58        constructor(
59            IYieldBox _yieldBox,
60            address _token,
61            address _vault,
62            bytes32 _poolId,
63            address _bal,
64            address _helpers
65:       ) BaseERC20Strategy(_yieldBox, _token) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L58-L65

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol

50        constructor(
51            IYieldBox _yieldBox,
52            address _token,
53            address _cToken
54:       ) BaseERC20Strategy(_yieldBox, _token) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol#L50-L54

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol

84        constructor(
85            IYieldBox _yieldBox,
86            address _token,
87            address _rewadPool,
88            address _booster,
89            address _zap,
90            address _lpGetter,
91            address _multiSwapper
92:       ) BaseERC20Strategy(_yieldBox, _token) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L84-L92

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol

63        constructor(
64            IYieldBox _yieldBox,
65            address _token,
66            address _lpGauge,
67            address _lpGetter,
68            address _minter,
69            address _multiSwapper
70:       ) BaseERC20Strategy(_yieldBox, ITricryptoLPGetter(_lpGetter).lpToken()) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L63-L70

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol

62        constructor(
63            IYieldBox _yieldBox,
64            address _token,
65            address _lpGauge,
66            address _lpGetter,
67            address _minter,
68            address _multiSwapper
69:       ) BaseERC20Strategy(_yieldBox, _token) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L62-L69

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol

53        constructor(
54            IYieldBox _yieldBox,
55            IGmxRewardRouterV2 _gmxRewardRouter,
56            IGmxRewardRouterV2 _glpRewardRouter,
57            IERC20 _sGlp
58:       ) BaseERC20Strategy(_yieldBox, address(_sGlp)) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol#L53-L58

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol

52        constructor(
53            IYieldBox _yieldBox,
54            address _token,
55            address _stEth,
56            address _curvePool
57:       ) BaseERC20Strategy(_yieldBox, _token) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol#L52-L57

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol

67        constructor(
68            IYieldBox _yieldBox,
69            address _token,
70            address _ethRouter,
71            address _lpStaking,
72            uint256 _stakingPid,
73            address _lpToken,
74            address _swapper,
75            address _stgEthPool
76:       ) BaseERC20Strategy(_yieldBox, _token) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L67-L76

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol

51        constructor(
52            IYieldBox _yieldBox,
53            address _token,
54            address _vault
55:       ) BaseERC20Strategy(_yieldBox, _token) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol#L51-L55

```solidity
File: YieldBox/contracts/YieldBoxPermit.sol

40:       constructor(string memory name) EIP712(name, "1") {}

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxPermit.sol#L40

```solidity
File: YieldBox/contracts/YieldBox.sol

91:       constructor(IWrappedNative wrappedNative_, YieldBoxURIBuilder uriBuilder_) YieldBoxPermit("YieldBox") {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBox.sol#L91

</details>

### [G&#x2011;30] Structs can be packed into fewer storage slots
Each slot saved can avoid an extra Gsset (**20000 gas**) for the first setting of the struct. Subsequent reads as well as writes have smaller gas savings

*There are 5 instances of this issue:*

```solidity
File: tapiocaz-audit/contracts/TapiocaWrapper.sol

/// @audit Variable ordering with 2 slots instead of the current 3:
///           bytes(32):bytecode, address(20):toft, bool(1):revertOnFailure
27        struct ExecutionCall {
28            address toft;
29            bytes bytecode;
30            bool revertOnFailure;
31:       }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/TapiocaWrapper.sol#L27-L31

```solidity
File: tapioca-periph-audit/contracts/Magnetar/MagnetarV2Storage.sol

/// @audit Variable ordering with 3 slots instead of the current 4:
///           uint256(32):value, bytes(32):call, address(20):target, uint16(2):id, bool(1):allowFailure
78        struct Call {
79            uint16 id;
80            address target;
81            uint256 value;
82            bool allowFailure;
83            bytes call;
84:       }

/// @audit Variable ordering with 6 slots instead of the current 7:
///           uint256(32):value, uint256(32):deadline, bytes32(32):r, bytes32(32):s, address(20):owner, uint8(1):v, address(20):spender
91        struct PermitData {
92            address owner;
93            address spender;
94            uint256 value;
95            uint256 deadline;
96            uint8 v;
97            bytes32 r;
98            bytes32 s;
99:       }

/// @audit Variable ordering with 5 slots instead of the current 6:
///           uint256(32):deadline, bytes32(32):r, bytes32(32):s, address(20):owner, uint8(1):v, address(20):spender
101       struct PermitAllData {
102           address owner;
103           address spender;
104           uint256 deadline;
105           uint8 v;
106           bytes32 r;
107           bytes32 s;
108:      }

/// @audit Variable ordering with 5 slots instead of the current 6:
///           uint256(32):collateralAmount, uint256(32):borrowAmount, bytes(32):withdrawData, address(20):market, bool(1):extractFromSender, bool(1):deposit, bool(1):withdraw, address(20):user
212       struct HelperBorrowData {
213           address market;
214           address user;
215           uint256 collateralAmount;
216           uint256 borrowAmount;
217           bool extractFromSender;
218           bool deposit;
219           bool withdraw;
220           bytes withdrawData;
221:      }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2Storage.sol#L78-L84


### [G&#x2011;31] Inverting the condition of an `if`-`else`-statement wastes gas
Flipping the `true` and `false` blocks instead saves ***[3 gas](https://gist.github.com/IllIllI000/44da6fbe9d12b9ab21af82f14add56b9)***

*There is one instance of this issue:*

```solidity
File: tapiocaz-audit/contracts/TapiocaWrapper.sol

190           if (!_linked) {
191               TapiocaOFT toft = TapiocaOFT(
192                   payable(
193                       Create2.deploy(
194                           0,
195                           keccak256(
196                               abi.encodePacked(
197                                   keccak256(_bytecode),
198                                   address(this),
199                                   _erc20,
200                                   _salt
201                               )
202                           ),
203                           _bytecode
204                       )
205                   )
206               );
207               oft = address(toft);
208           } else {
209               mTapiocaOFT toft = mTapiocaOFT(
210                   payable(
211                       Create2.deploy(
212                           0,
213                           keccak256(
214                               abi.encodePacked(
215                                   keccak256(_bytecode),
216                                   address(this),
217                                   _erc20,
218                                   _salt
219                               )
220                           ),
221                           _bytecode
222                       )
223                   )
224               );
225               oft = address(toft);
226:          }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/TapiocaWrapper.sol#L190-L226


### [G&#x2011;32] Division by two should use bit shifting
`<x> / 2` is the same as `<x> >> 1`. While the compiler uses the `SHR` opcode to accomplish both, the version that uses division incurs an overhead of [**20 gas**](https://gist.github.com/IllIllI000/ec0e4e6c4f52a6bca158f137a3afd4ff) due to `JUMP`s to and from a compiler utility function that introduces checks which can be avoided by using `unchecked {}` around the division by two

*There are 3 instances of this issue:*

```solidity
File: tapiocaz-audit/contracts/tOFT/BaseTOFTStorage.sol

57:               _decimal / 2,

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFTStorage.sol#L57

```solidity
File: tap-token-audit/contracts/twAML.sol

150:              uint256 x = y / 2 + 1;

153:                  x = (y / x + x) / 2;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/twAML.sol#L150


### [G&#x2011;33] Structs can be packed into fewer storage slots by truncating timestamp bytes
By using a `uint32` rather than a larger type for variables that track timestamps, one can save gas by using fewer storage slots per struct, at the expense of the protocol breaking after the year 2106 (when `uint32` wraps). If this is an acceptable tradeoff, each slot saved can avoid an extra Gsset (**20000 gas**) for the first setting of the struct. Subsequent reads as well as writes have smaller gas savings

*There is one instance of this issue:*

```solidity
File: tap-token-audit/contracts/Vesting.sol

/// @audit Variable ordering with 3 slots instead of the current 4:
///           uint256(32):amount, uint256(32):claimed, uint32(4):latestClaimTimestamp, bool(1):revoked
32        struct UserData {
33            uint256 amount;
34            uint256 claimed;
35            uint256 latestClaimTimestamp;
36            bool revoked;
37:       }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/Vesting.sol#L32-L37


### [G&#x2011;34] Multiple accesses of a mapping/array should use a local variable cache
The instances below point to the second+ access of a value inside a mapping/array, within a function. Caching a mapping's value in a local `storage` or `calldata` variable when the value is accessed [multiple times](https://gist.github.com/IllIllI000/ec23a57daa30a8f8ca8b9681c8ccefb0), saves **~42 gas per access** due to not having to recalculate the key's keccak256 hash (Gkeccak256 - **30 gas**) and that calculation's associated stack operations. Caching an array's struct avoids recalculating the array offsets into memory/calldata

*There are 10 instances of this issue:*

```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

/// @audit weekTotals[<etc>] on line 343
344:          weekTotals[w1 + 1].netActiveVotes -= int256(votes);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L344

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

/// @audit paymentTokens[_paymentToken] on line 349
350:          paymentTokens[_paymentToken].oracleData = _oracleData;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L350

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionBroker.sol

/// @audit paymentTokens[_paymentToken] on line 463
464:          paymentTokens[_paymentToken].oracleData = _oracleData;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L464

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol

/// @audit activeSingularities[_singularity] on line 180
187:          activeSingularities[_singularity].totalDeposited += _amount;

/// @audit activeSingularities[_singularity] on line 221
247:          activeSingularities[_singularity].totalDeposited -= lockPosition.amount;

/// @audit activeSingularities[singularity] on line 264
267:          activeSingularities[singularity].poolWeight = weight;

/// @audit activeSingularities[singularity] on line 283
287:          activeSingularities[singularity].sglAssetID = assetID;

/// @audit activeSingularities[singularity] on line 287
288:          activeSingularities[singularity].poolWeight = weight > 0 ? weight : 1;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L187

```solidity
File: tap-token-audit/contracts/Vesting.sol

/// @audit users[_user] on line 86
86:           return _vested(users[_user].amount) - users[_user].claimed;

/// @audit users[<etc>] on line 116
117:          users[msg.sender].latestClaimTimestamp = block.timestamp;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/Vesting.sol#L86


### [G&#x2011;35] `internal` functions only called once can be inlined to save gas
Not inlining costs **20 to 40 gas** because of two extra `JUMP` instructions and additional stack operations needed for function calls.

*There are 26 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

483:      function _claimRewards(uint256 _tokenId, address _to) internal {

499       function _claimRewardsOn(
500           uint256 _tokenId,
501           address _to,
502:          IERC20[] memory _rewardTokens

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L483

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

390:      function _participatePhase1() internal returns (uint256 oTAPTokenID) {

410       function _participatePhase2(
411           bytes calldata _data
412:      ) internal returns (uint256 oTAPTokenID) {

442       function _participatePhase3(
443           bytes calldata _data
444:      ) internal returns (uint256 oTAPTokenID) {

465:      function _participatePhase4() internal returns (uint256 oTAPTokenID) {

487       function _processOTCDeal(
488           ERC20 _paymentToken,
489           PaymentTokenOracle memory _paymentTokenOracle,
490           uint256 tapAmount,
491:          uint256 discount

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L390

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionBroker.sol

508       function _processOTCDeal(
509           ERC20 _paymentToken,
510           PaymentTokenOracle memory _paymentTokenOracle,
511           uint256 tapAmount,
512:          uint256 discount

559:      function _emitToGauges(uint256 _epochTAP) internal {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L508-L512

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol

336:      function _computeSGLPoolWeights() internal view returns (uint256) {

348:      function _isPositionActive(uint256 tokenId) internal view returns (bool) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L336

```solidity
File: tap-token-audit/contracts/tokens/TapOFT.sol

253:      function _computeEmission() internal view returns (uint256 result) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L253

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol

225:      function _currentBalance() internal view override returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol#L225

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol

130:      function _currentBalance() internal view override returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L130

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol

113:      function _currentBalance() internal view override returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol#L113

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol

291:      function _currentBalance() internal view override returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L291

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol

210:      function _currentBalance() internal view override returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L210

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol

196:      function _currentBalance() internal view override returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L196

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol

118:      function _currentBalance() internal view override returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol#L118

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol

214:      function _currentBalance() internal view override returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L214

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol

111:      function _currentBalance() internal view override returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol#L111

```solidity
File: YieldBox/contracts/YieldBox.sol

247       function _withdrawNFT(
248           Asset storage asset,
249           uint256 assetId,
250           address from,
251           address to
252:      ) internal returns (uint256 amountOut, uint256 shareOut) {

270       function _withdrawFungible(
271           Asset storage asset,
272           uint256 assetId,
273           address from,
274           address to,
275           uint256 amount,
276           uint256 share
277:      ) internal returns (uint256 amountOut, uint256 shareOut) {

316:      function _transferBatch(address from, address to, uint256[] calldata ids, uint256[] calldata values) internal override {

371:      function _setApprovalForAll(address _owner, address operator, bool approved) internal override {

394:      function _setApprovalForAsset(address _owner, address operator, uint256 assetId, bool approved) internal override {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBox.sol#L247-L252

</details>

### [G&#x2011;36] `require()`/`revert()` strings longer than 32 bytes cost extra gas
Each extra memory word of bytes past the original 32 [incurs an MSTORE](https://gist.github.com/hrkrshnn/ee8fabd532058307229d65dcd5836ddc#consider-having-short-revert-strings) which costs **3 gas**

*There are 23 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

368           require(
369               paymentTokenBeneficiary != address(0),
370               "adb: Payment token beneficiary not set"
371:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L368-L371

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionBroker.sol

297:          require(oTAP.exists(_oTAPTokenID), "tOB: oTAP position does not exist");

482           require(
483               paymentTokenBeneficiary != address(0),
484               "tOB: Payment token beneficiary not set"
485:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L297

```solidity
File: tapioca-periph-audit/contracts/Magnetar/MagnetarV2Storage.sol

337:          require(_from == msg.sender, "MagnetarV2: operator not approved");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2Storage.sol#L337

```solidity
File: tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol

527               require(
528                   ownerOfTapTokenId == user || ownerOfTapTokenId == address(this),
529                   "Magnetar: oTAPTokenID owner mismatch"
530:              );

743:          require(withdrawData.length > 0, "MagnetarV2: withdrawData is empty");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L527-L530

```solidity
File: tapioca-periph-audit/contracts/Swapper/BaseSwapper.sol

102           require(
103               success && (data.length == 0 || abi.decode(data, (bool))),
104               "BaseSwapper::safeApprove: approve failed"
105:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/BaseSwapper.sol#L102-L105

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol

184           require(
185               lpBalanceAfter > lpBalanceBefore,
186               "BalancerStrategy: vault deposit failed"
187:          );

196:          require(available >= amount, "BalancerStrategy: amount not valid");

263           require(
264               wrappedNativeBalanceAfter > wrappedNativeBalanceBefore,
265               "BalancerStrategy: vault withdrawal failed"
266:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L184-L187

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol

141:          require(available >= amount, "CompoundStrategy: amount not valid");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol#L141

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol

245           require(
246               tempData.rewardContracts.length == tempData.tokens.length,
247               "ConvexTricryptoStrategy: claim data not valid"
248:          );

249           require(
250               tempData.rewardContracts.length > 0,
251               "ConvexTricryptoStrategy: nothing to claim for"
252:          );

325           require(
326               available >= amount,
327               "ConvexTricryptoStrategy: amount not valid"
328:          );

340           require(
341               wrappedNative.balanceOf(address(this)) >= amount,
342               "ConvexTricryptoStrategy: not enough"
343:          );

363           require(
364               successEmtptyApproval,
365               "OperationsLib::safeApprove: approval reset failed"
366:          );

376           require(
377               success && (data.length == 0 || abi.decode(data, (bool))),
378               "OperationsLib::safeApprove: approve failed"
379:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L245-L248

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol

234:          require(available >= amount, "TricryptoLPStrategy: amount not valid");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L234

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol

221           require(
222               available >= amount,
223               "TricryptoNativeStrategy: amount not valid"
224:          );

235           require(
236               wrappedNative.balanceOf(address(this)) >= amount,
237               "TricryptoNativeStrategy: not enough"
238:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L221-L224

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol

246:          require(available >= amount, "StargateStrategy: amount not valid");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L246

```solidity
File: YieldBox/contracts/YieldBoxPermit.sol

58:           require(signer == owner, "YieldBoxPermit: invalid signature");

87:           require(signer == owner, "YieldBoxPermit: invalid signature");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxPermit.sol#L58

</details>

### [G&#x2011;37] `keccak256()` should only need to be called on a specific string literal once
It should be saved to an immutable variable, and the variable used instead. If the hash is being used as a part of a function selector, the cast to `bytes4` should also only be done once

*There are 3 instances of this issue:*

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol

366                   keccak256(
367                       "onERC1155Received(address,address,uint256,uint256,bytes)"
368:                  )

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L366-L368

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol

358:                  bytes4(keccak256("approve(address,uint256)")),

371:                  bytes4(keccak256("approve(address,uint256)")),

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L358


### [G&#x2011;38] Usage of `uints`/`ints` smaller than 32 bytes (256 bits) incurs overhead
> When using elements that are smaller than 32 bytes, your contract’s gas usage may be higher. This is because the EVM operates on 32 bytes at a time. Therefore, if the element is smaller than that, the EVM must use more operations in order to reduce the size of the element from 32 bytes to the desired size.

https://docs.soliditylang.org/en/v0.8.11/internals/layout_in_storage.html
Each operation involving a `uint8` costs an extra [**22-28 gas**](https://gist.github.com/IllIllI000/9388d20c70f9a4632eb3ca7836f54977) (depending on whether the other operand is also a variable of type `uint8`) as compared to ones involving `uint256`, due to the compiler having to clear the higher bits of the memory word before operating on the `uint8`, as well as the associated stack operations of doing so. Use a larger size then downcast where needed

*There are 5 instances of this issue:*

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

/// @audit uint64 lastEpochUpdate
287:          lastEpochUpdate = uint64(block.timestamp);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L287

```solidity
File: YieldBox/contracts/BoringMath.sol

/// @audit uint128 c
7:            c = uint128(a);

/// @audit uint64 c
12:           c = uint64(a);

/// @audit uint32 c
17:           c = uint32(a);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/BoringMath.sol#L7

```solidity
File: YieldBox/contracts/NativeTokenFactory.sol

/// @audit uint32 tokenId
92:           tokenId = assets.length.to32();

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/NativeTokenFactory.sol#L92


### [G&#x2011;39] Stack variable used as a cheaper cache for a state variable is only used once
If the variable is only accessed once, it's cheaper to use the state variable directly that one time, and save the **3 gas** the extra stack assignment would spend

*There is one instance of this issue:*

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

160:          uint256 cachedEpoch = epoch;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L160


### [G&#x2011;40] Consider using `bytes32` rather than a `string`
Using the `bytes` types for fixed-length strings is more efficient than having the EVM have to incur the overhead of string processing. Consider whether the value _needs_ to be a `string`. A good reason to keep it as a `string` would be if the variable is defined in an interface that this project does not own.

*There are 8 instances of this issue:*

```solidity
File: contracts/oracle/Seer.sol

8:       string public _name;

9:       string public _symbol;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/Seer.sol#L8-L8

```solidity
File: contracts/oracle/implementations/ARBTriCryptoOracle.sol

31:      string public _name;

32:      string public _symbol;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/ARBTriCryptoOracle.sol#L31-L31

```solidity
File: contracts/oracle/implementations/SGOracle.sol

24:      string public _name;

25:      string public _symbol;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/SGOracle.sol#L24-L24

```solidity
File: contracts/glp/GlpStrategy.sol

26:      string public constant override name = "sGLP";

27       string public constant override description =
28:          "Holds staked GLP tokens and compounds the rewards";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol#L26-L26


### [G&#x2011;41] The result of function calls should be cached rather than re-calling the function
The instances below point to the second+ call of the function within a single function

*There are 8 instances of this issue:*

```solidity
File: tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol

/// @audit market.oracle() on line 918
930:          (, info.oracleExchangeRate) = IOracle(market.oracle()).peek(

/// @audit market.oracleData() on line 919
931:              market.oracleData()

/// @audit market.oracle() on line 918
933:          info.spotExchangeRate = IOracle(market.oracle()).peekSpot(

/// @audit market.oracleData() on line 919
934:              market.oracleData()

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol#L930

```solidity
File: tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol

/// @audit marketInterface.collateralId() on line 264
279:                      marketInterface.collateralId(),

/// @audit bigBang.assetId() on line 627
629:                          bigBang.assetId(),

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L279

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol

/// @audit stakedRewardToken.cooldown() on line 172
175:              stakedRewardToken.cooldown();

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol#L175

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol

/// @audit lpGetter.lpToken() on line 78
79:           IERC20(lpGetter.lpToken()).approve(_lpGetter, type(uint256).max);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L79


### [G&#x2011;42] Use a more recent version of solidity
Use a solidity version of at least 0.8.2 to get simple compiler automatic inlining
Use a solidity version of at least 0.8.3 to get better struct packing and cheaper multiple storage reads
Use a solidity version of at least 0.8.4 to get custom errors, which are cheaper at deployment than `revert()/require()` strings
Use a solidity version of at least 0.8.10 to have external calls skip contract existence checks if the external call has a return value

*There are 2 instances of this issue:*

```solidity
File: tapioca-periph-audit/contracts/oracle/implementations/GLPOracle.sol

2:    pragma solidity >=0.8.0;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/GLPOracle.sol#L2

```solidity
File: YieldBox/contracts/YieldBoxPermit.sol

3:    pragma solidity ^0.8.0;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxPermit.sol#L3


### [G&#x2011;43] Not using the named return variables anywhere in the function is confusing
Consider changing the variable to be an unnamed one, since the variable is never assigned, nor is it returned by name. If the optimizer is not turned on, leaving the code as it is will also waste gas for the stack variable.

*There are 69 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol

/// @audit amount
76        function getCollateralAmountForShare(
77            IMarket market,
78            uint256 share
79:       ) public view returns (uint256 amount) {

/// @audit collateralShares
89        function getCollateralSharesForBorrowPart(
90            IMarket market,
91            uint256 borrowPart,
92            uint256 liquidationMultiplierPrecision,
93            uint256 exchangeRatePrecision
94:       ) public view returns (uint256 collateralShares) {

/// @audit amount
117       function getAmountForBorrowPart(
118           IMarket market,
119           uint256 borrowPart
120:      ) public view returns (uint256 amount) {

/// @audit part
133       function getBorrowPartForAmount(
134           IMarket market,
135           uint256 amount
136:      ) public view returns (uint256 part) {

/// @audit amount
150       function getAmountForAssetFraction(
151           ISingularity singularity,
152           uint256 fraction
153:      ) public view returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol#L76-L79

```solidity
File: tapioca-periph-audit/contracts/oracle/implementations/ARBTriCryptoOracle.sol

/// @audit success
/// @audit rate
71        function get(
72            bytes calldata
73:       ) external virtual returns (bool success, uint256 rate) {

/// @audit success
/// @audit rate
82        function peek(
83            bytes calldata
84:       ) external view virtual returns (bool success, uint256 rate) {

/// @audit rate
92        function peekSpot(
93            bytes calldata
94:       ) external view virtual returns (uint256 rate) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/ARBTriCryptoOracle.sol#L71-L73

```solidity
File: tapioca-periph-audit/contracts/oracle/implementations/GLPOracle.sol

/// @audit success
/// @audit rate
24        function get(
25            bytes calldata
26:       ) public view override returns (bool success, uint256 rate) {

/// @audit success
/// @audit rate
32        function peek(
33            bytes calldata
34:       ) public view override returns (bool success, uint256 rate) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/GLPOracle.sol#L24-L26

```solidity
File: tapioca-periph-audit/contracts/oracle/implementations/SGOracle.sol

/// @audit _maxPrice
49:       function _get() internal view returns (uint256 _maxPrice) {

/// @audit success
/// @audit rate
61        function get(
62            bytes calldata
63:       ) external virtual returns (bool success, uint256 rate) {

/// @audit success
/// @audit rate
72        function peek(
73            bytes calldata
74:       ) external view virtual returns (bool success, uint256 rate) {

/// @audit rate
82        function peekSpot(
83            bytes calldata
84:       ) external view virtual returns (uint256 rate) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/SGOracle.sol#L49

```solidity
File: tapioca-periph-audit/contracts/oracle/Seer.sol

/// @audit success
/// @audit rate
52        function get(
53            bytes calldata
54:       ) external virtual returns (bool success, uint256 rate) {

/// @audit success
/// @audit rate
64        function peek(
65            bytes calldata
66:       ) external view virtual returns (bool success, uint256 rate) {

/// @audit rate
75        function peekSpot(
76            bytes calldata
77:       ) external view virtual returns (uint256 rate) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/Seer.sol#L52-L54

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol

/// @audit name_
83:       function name() external pure override returns (string memory name_) {

/// @audit description_
88        function description()
89            external
90            pure
91            override
92:           returns (string memory description_)

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol#L83

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol

/// @audit name_
85:       function name() external pure override returns (string memory name_) {

/// @audit description_
90        function description()
91            external
92            pure
93            override
94:           returns (string memory description_)

/// @audit result
100:      function compoundAmount() external pure returns (uint256 result) {

/// @audit amount
130:      function _currentBalance() internal view override returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L85

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol

/// @audit name_
65:       function name() external pure override returns (string memory name_) {

/// @audit description_
70        function description()
71            external
72            pure
73            override
74:           returns (string memory description_)

/// @audit result
80:       function compoundAmount() public pure returns (uint256 result) {

/// @audit amount
113:      function _currentBalance() internal view override returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol#L65

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol

/// @audit name_
115:      function name() external pure override returns (string memory name_) {

/// @audit description_
120       function description()
121           external
122           pure
123           override
124:          returns (string memory description_)

/// @audit amount
291:      function _currentBalance() internal view override returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L115

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol

/// @audit name_
89:       function name() external pure override returns (string memory name_) {

/// @audit description_
94        function description()
95            external
96            pure
97            override
98:           returns (string memory description_)

/// @audit amount
210:      function _currentBalance() internal view override returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L89

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol

/// @audit name_
88:       function name() external pure override returns (string memory name_) {

/// @audit description_
93        function description()
94            external
95            pure
96            override
97:           returns (string memory description_)

/// @audit amount
196:      function _currentBalance() internal view override returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L88

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol

/// @audit name_
69:       function name() external pure override returns (string memory name_) {

/// @audit description_
74        function description()
75            external
76            pure
77            override
78:           returns (string memory description_)

/// @audit result
84:       function compoundAmount() public pure returns (uint256 result) {

/// @audit amount
118:      function _currentBalance() internal view override returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol#L69

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol

/// @audit name_
101:      function name() external pure override returns (string memory name_) {

/// @audit description_
106       function description()
107           external
108           pure
109           override
110:          returns (string memory description_)

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L101

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol

/// @audit name_
66:       function name() external pure override returns (string memory name_) {

/// @audit description_
71        function description()
72            external
73            pure
74            override
75:           returns (string memory description_)

/// @audit result
81:       function compoundAmount() public pure returns (uint256 result) {

/// @audit amount
111:      function _currentBalance() internal view override returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol#L66

```solidity
File: YieldBox/contracts/YieldBox.sol

/// @audit amount
102:      function _tokenBalanceOf(Asset storage asset) internal view returns (uint256 amount) {

/// @audit amountOut
/// @audit shareOut
118       function depositAsset(
119           uint256 assetId,
120           address from,
121           address to,
122           uint256 amount,
123           uint256 share
124:      ) public allowed(from, assetId) returns (uint256 amountOut, uint256 shareOut) {

/// @audit amountOut
/// @audit shareOut
168       function depositNFTAsset(
169           uint256 assetId,
170           address from,
171           address to
172:      ) public allowed(from, assetId) returns (uint256 amountOut, uint256 shareOut) {

/// @audit amountOut
/// @audit shareOut
196:      function depositETHAsset(uint256 assetId, address to, uint256 amount) public payable returns (uint256 amountOut, uint256 shareOut) {

/// @audit amountOut
/// @audit shareOut
223       function withdraw(
224           uint256 assetId,
225           address from,
226           address to,
227           uint256 amount,
228           uint256 share
229:      ) public allowed(from, assetId) returns (uint256 amountOut, uint256 shareOut) {

/// @audit amountOut
/// @audit shareOut
247       function _withdrawNFT(
248           Asset storage asset,
249           uint256 assetId,
250           address from,
251           address to
252:      ) internal returns (uint256 amountOut, uint256 shareOut) {

/// @audit amountOut
/// @audit shareOut
270       function _withdrawFungible(
271           Asset storage asset,
272           uint256 assetId,
273           address from,
274           address to,
275           uint256 amount,
276           uint256 share
277:      ) internal returns (uint256 amountOut, uint256 shareOut) {

/// @audit amountOut
/// @audit shareOut
500:      function depositETH(IStrategy strategy, address to, uint256 amount) public payable returns (uint256 amountOut, uint256 shareOut) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBox.sol#L102

</details>

### [G&#x2011;44] Avoid contract existence checks by using low level calls
Prior to 0.8.10 the compiler inserted extra code, including `EXTCODESIZE` (**100 gas**), to check for contract existence for external function calls. In more recent solidity versions, the compiler will not insert these checks if the external call has a return value. Similar behavior can be achieved in earlier versions by using low-level calls, since low level calls never check for contract existence

*There are 2 instances of this issue:*

```solidity
File: YieldBox/contracts/YieldBoxURIBuilder.sol

/// @audit toHexString()
90:                   abi.encodePacked("ERC1155:", uint256(uint160(asset.contractAddress)).toHexString(20), "/", asset.tokenId.toString())

/// @audit toHexString()
106:                  ? abi.encodePacked(',"tokenAddress":"', uint256(uint160(asset.contractAddress)).toHexString(20), '"')

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxURIBuilder.sol#L90


### [G&#x2011;45] String literals passed to `abi.encode()`/`abi.encodePacked()` should not be split by commas
String literals can be split into multiple parts and still be considered as a single string literal. Adding commas between each chunk makes it no longer a single string, and instead multiple strings. EACH new comma costs [***21 gas***](https://gist.github.com/IllIllI000/837d1b36c16c9bfe1010f9f775a09bbf) due to stack operations and separate `MSTORE`s

*There is one instance of this issue:*

```solidity
File: YieldBox/contracts/YieldBoxURIBuilder.sol

/// @audit 1 commas
61:                   return string(abi.encodePacked("ERC1155", " (", asset.strategy.name(), ")"));

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxURIBuilder.sol#L61

## Disputed Issues

The issues below may be reported by other bots/wardens, but can be penalized/ignored since either the rule or the specified instances are invalid


### [D&#x2011;01] ~~Storage Write Removal Bug On Conditional Early Termination~~
In solidity versions 0.8.13 through 0.8.16, there is a [bug](https://blog.soliditylang.org/2022/09/08/storage-write-removal-before-conditional-termination/) involving the use of the Yul functions `return()` and `stop()`. If those functions aren't called, or if the Solidity version doesn't match, the finding is invalid.

*There are 16 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: contracts/Penrose.sol

478          assembly {
479              // Slice the sighash.
480              _returnData := add(_returnData, 0x04)
481:         }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/Penrose.sol#L478-L481

```solidity
File: contracts/markets/Market.sol

378          assembly {
379              // Slice the sighash.
380              _returnData := add(_returnData, 0x04)
381:         }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/Market.sol#L378-L381

```solidity
File: contracts/usd0/BaseUSDOStorage.sol

93           assembly {
94               // Slice the sighash.
95               _returnData := add(_returnData, 0x04)
96:          }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDOStorage.sol#L93-L96

```solidity
File: contracts/tOFT/BaseTOFTStorage.sol

73           assembly {
74               // Slice the sighash.
75               _returnData := add(_returnData, 0x04)
76:          }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFTStorage.sol#L73-L76

```solidity
File: contracts/governance/twTAP.sol

573          assembly {
574              chainId := chainid()
575:         }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L573-L575

```solidity
File: contracts/twAML.sol

21           assembly {
22               let mm := mulmod(a, b, not(0))
23               prod0 := mul(a, b)
24               prod1 := sub(sub(mm, prod0), lt(mm, prod0))
25:          }

33               assembly {
34                   result := div(prod0, denominator)
35:              }

50           assembly {
51               remainder := mulmod(a, b, denominator)
52:          }

54           assembly {
55               prod1 := sub(prod1, gt(remainder, prod0))
56               prod0 := sub(prod0, remainder)
57:          }

64           assembly {
65               denominator := div(denominator, twos)
66:          }

69           assembly {
70               prod0 := div(prod0, twos)
71:          }

75           assembly {
76               twos := add(div(sub(0, twos), twos), 1)
77:          }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/twAML.sol#L21-L25

```solidity
File: contracts/Magnetar/MagnetarV2.sol

1082         assembly {
1083             // Slice the sighash.
1084             _returnData := add(_returnData, 0x04)
1085:        }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol#L1082-L1085

```solidity
File: contracts/Multicall/Multicall3.sol

98           assembly {
99               // Slice the sighash.
100              _returnData := add(_returnData, 0x04)
101:         }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Multicall/Multicall3.sol#L98-L101

```solidity
File: contracts/TapiocaDeployer/TapiocaDeployer.sol

40           assembly {
41               addr := create2(amount, add(bytecode, 0x20), mload(bytecode), salt)
42:          }

73           assembly {
74               let ptr := mload(0x40) // Get free memory pointer
75   
76               // |                   | ↓ ptr ...  ↓ ptr + 0x0B (start) ...  ↓ ptr + 0x20 ...  ↓ ptr + 0x40 ...   |
77               // |-------------------|---------------------------------------------------------------------------|
78               // | bytecodeHash      |                                                        CCCCCCCCCCCCC...CC |
79               // | salt              |                                      BBBBBBBBBBBBB...BB                   |
80               // | deployer          | 000000...0000AAAAAAAAAAAAAAAAAAA...AA                                     |
81               // | 0xFF              |            FF                                                             |
82               // |-------------------|---------------------------------------------------------------------------|
83               // | memory            | 000000...00FFAAAAAAAAAAAAAAAAAAA...AABBBBBBBBBBBBB...BBCCCCCCCCCCCCC...CC |
84               // | keccak(start, 85) |            ↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑↑ |
85   
86               mstore(add(ptr, 0x40), bytecodeHash)
87               mstore(add(ptr, 0x20), salt)
88               mstore(ptr, deployer) // Right-aligned with 12 preceding garbage bytes
89               let start := add(ptr, 0x0b) // The hashed data starts at the final garbage byte which we will set to 0xff
90               mstore8(start, 0xff)
91               addr := keccak256(start, 85)
92:          }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/TapiocaDeployer/TapiocaDeployer.sol#L40-L42

</details>

### [D&#x2011;02] ~~Do not calculate `constant` variables, which will save gas~~
The compiler automatically expands simple expressions into their literal values, so manually doing the expansion [doesn't save gas](https://twitter.com/GalloDaSballo/status/1543729080926871557), and this finding is invalid

*There are 5 instances of this issue:*

```solidity
File: contracts/markets/MarketERC20.sol

29       bytes32 private constant _PERMIT_TYPEHASH =
30           keccak256(
31               "Permit(address owner,address spender,uint256 value,uint256 nonce,uint256 deadline)"
32:          );

33       bytes32 private constant _PERMIT_TYPEHASH_BORROW =
34           keccak256(
35               "PermitBorrow(address owner,address spender,uint256 value,uint256 nonce,uint256 deadline)"
36:          );

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/MarketERC20.sol#L29-L32

```solidity
File: contracts/usd0/BaseUSDOStorage.sol

38       bytes32 internal constant FLASH_MINT_CALLBACK_SUCCESS =
39:          keccak256("ERC3156FlashBorrower.onFlashLoan");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDOStorage.sol#L38-L39

```solidity
File: contracts/YieldBoxPermit.sol

27       bytes32 private constant _PERMIT_TYPEHASH =
28:          keccak256("Permit(address owner,address spender,uint256 assetId,uint256 nonce,uint256 deadline)");

31       bytes32 private constant _PERMIT_ALL_TYPEHASH =
32:          keccak256("PermitAll(address owner,address spender,uint256 nonce,uint256 deadline)");

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxPermit.sol#L27-L28


### [D&#x2011;03] ~~Use delete instead of setting mapping/state variable to zero, to save gas~~
Using delete instead of assigning zero to state variables does not save any extra gas with the optimizer [on](https://gist.github.com/IllIllI000/ef8ec3a70aede7f12433fe63dc418515#with-the-optimizer-set-at-200-runs) (saves 5-8 gas with optimizer completely off), so this finding is invalid, especially since if they were interested in gas savings, they'd have the optimizer enabled.

*There are 16 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: contracts/markets/bigBang/BigBang.sol

460:             totalFees = 0;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L460-L460

```solidity
File: contracts/markets/singularity/SGLCommon.sol

246:                 _yieldBoxShares[from][ASSET_SIG] = 0; //some assets accrue in time

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol#L246-L246

```solidity
File: contracts/markets/singularity/SGLLendingCommon.sol

51:              _yieldBoxShares[from][COLLATERAL_SIG] = 0; //accrues in time

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLendingCommon.sol#L51-L51

```solidity
File: contracts/markets/singularity/Singularity.sol

467:         accrueInfo.feesEarnedFraction = 0;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L467-L467

```solidity
File: contracts/Vesting.sol

138:         data.claimed = 0;

140:         data.latestClaimTimestamp = 0;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/Vesting.sol#L138-L138

```solidity
File: contracts/governance/twTAP.sol

160:             participant.multiplier = 0;

293:                     pool.cumulative = 0;

547:                     pool.cumulative = 0;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L160-L160

```solidity
File: contracts/option-airdrop/AirdropBroker.sol

395:         phase1Users[msg.sender] = 0;

470:         phase4Users[msg.sender] = 0;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L395-L395

```solidity
File: contracts/options/TapiocaOptionBroker.sol

256:                     pool.cumulative = 0;

318:                     pool.cumulative = 0;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L256-L256

```solidity
File: contracts/balancer/BalancerStrategy.sol

161:                 maxAmountsIn[i] = 0;

230:                 minAmountsOut[i] = 0;

281:             minAmountsOut[i] = 0;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L161-L161

</details>

### [D&#x2011;04] ~~`abi.encode()` is less efficient than `abi.encodepacked()`~~
`abi.encodePacked()` does not always save gas over `abi.encode()` and in fact often costs [more](https://gist.github.com/IllIllI000/2ee970e4f05af4d2a3d89a56b5cc93a5) gas. The [comparison](https://github.com/ConnorBlockchain/Solidity-Encode-Gas-Comparison) sometimes linked to itself even shows that when addresses are involved, the packed flavor costs more gas. Furthermore, the test was done on Solidity 0.4.24, and there have been a lot of changes since then. Without more specific tests or explanations, it's not correct to say that the change always saves gas.

*There are 17 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: contracts/usd0/modules/USDOLeverageModule.sol

72:          bytes memory lzPayload = abi.encode(

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol#L72-L72

```solidity
File: contracts/usd0/modules/USDOMarketModule.sol

40:          bytes memory lzPayload = abi.encode(

78:          bytes memory lzPayload = abi.encode(

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOMarketModule.sol#L40-L40

```solidity
File: contracts/usd0/modules/USDOOptionsModule.sol

32:          bytes memory lzPayload = abi.encode(

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOOptionsModule.sol#L32-L32

```solidity
File: contracts/Balancer.sol

316:                 dstNativeAddr: abi.encode(

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/Balancer.sol#L316-L316

```solidity
File: contracts/tOFT/modules/BaseTOFTLeverageModule.sol

56:          bytes memory lzPayload = abi.encode(

89:          bytes memory lzPayload = abi.encode(

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol#L56-L56

```solidity
File: contracts/tOFT/modules/BaseTOFTMarketModule.sol

56:          bytes memory lzPayload = abi.encode(

105:         bytes memory lzPayload = abi.encode(

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTMarketModule.sol#L56-L56

```solidity
File: contracts/tOFT/modules/BaseTOFTOptionsModule.sol

47:          bytes memory lzPayload = abi.encode(

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTOptionsModule.sol#L47-L47

```solidity
File: contracts/tOFT/modules/BaseTOFTStrategyModule.sol

60:          bytes memory lzPayload = abi.encode(

102:         bytes memory lzPayload = abi.encode(

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol#L60-L60

```solidity
File: contracts/tokens/BaseTapOFT.sol

96:          bytes memory lzPayload = abi.encode(

172:         bytes memory lzPayload = abi.encode(

266:         bytes memory lzPayload = abi.encode(

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/BaseTapOFT.sol#L96-L96

```solidity
File: contracts/YieldBoxPermit.sol

53:          bytes32 structHash = keccak256(abi.encode(_PERMIT_TYPEHASH, owner, spender, assetId, _useNonce(owner), deadline));

82:          bytes32 structHash = keccak256(abi.encode(_PERMIT_ALL_TYPEHASH, owner, spender, _useNonce(owner), deadline));

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxPermit.sol#L53-L53

</details>

### [D&#x2011;05] ~~Contracts do not work with fee-on-transfer tokens~~
An ERC20 token being used, in and of itself, is not evidence of a fee-on-transfer issue; there must be other evidence that the balance accounting gets broken, and these lines do not contain such evidence.

*There are 72 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: contracts/Penrose.sol

292:         usdoToken = IERC20(_usdoToken);

298:                     IERC20(_usdoToken)

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/Penrose.sol#L292-L292

```solidity
File: contracts/markets/bigBang/BigBang.sol

116:                     IERC20,

140:         asset = IERC20(_asset);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L116-L116

```solidity
File: contracts/markets/singularity/Singularity.sol

83:                      IERC20,

85:                      IERC20,

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L83-L83

```solidity
File: contracts/usd0/modules/USDOLeverageModule.sol

217:         IERC20(swapData.tokenOut).approve(externalData.tOft, amountOut);

289:                     IERC20Permit(approvals[i].target).permit(

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol#L217-L217

```solidity
File: contracts/usd0/modules/USDOMarketModule.sol

278:                     IERC20Permit(approvals[i].target).permit(

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOMarketModule.sol#L278-L278

```solidity
File: contracts/usd0/modules/USDOOptionsModule.sol

279:                     IERC20Permit(approvals[i].target).permit(

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOOptionsModule.sol#L279-L279

```solidity
File: contracts/TapiocaWrapper.sol

160:         if (address(tapiocaOFTsByErc20[_erc20]) != address(0x0)) {

161:             revert TapiocaWrapper__AlreadyDeployed(_erc20);

165:             _createTOFT(_erc20, _bytecode, _salt, _linked)

167:         if (address(iOFT.erc20()) != _erc20) {

172:         tapiocaOFTsByErc20[_erc20] = iOFT;

177:         emit CreateOFT(iOFT, _erc20);

217:                                 _erc20,

199:                                 _erc20,

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/TapiocaWrapper.sol#L160-L160

```solidity
File: contracts/tOFT/BaseTOFT.sol

65:              _erc20,

460:                     IERC20(address(this))

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFT.sol#L65-L65

```solidity
File: contracts/tOFT/BaseTOFTStorage.sol

61:          erc20 = _erc20;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFTStorage.sol#L61-L61

```solidity
File: contracts/tOFT/TapiocaOFT.sol

48:              _erc20,

74:          if (erc20 == address(0)) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/TapiocaOFT.sol#L48-L48

```solidity
File: contracts/tOFT/mTapiocaOFT.sol

64:              _erc20,

94:          if (erc20 == address(0)) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol#L64-L64

```solidity
File: contracts/tOFT/modules/BaseTOFTLeverageModule.sol

36:              _erc20,

215:         IERC20(erc20).approve(externalData.swapper, amount);

217:             .buildSwapData(erc20, swapData.tokenOut, amount, 0, false, false);

319:                     IERC20Permit(approvals[i].target).permit(

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol#L36-L36

```solidity
File: contracts/tOFT/modules/BaseTOFTMarketModule.sol

35:              _erc20,

295:                     IERC20Permit(approvals[i].target).permit(

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTMarketModule.sol#L35-L35

```solidity
File: contracts/tOFT/modules/BaseTOFTOptionsModule.sol

30:              _erc20,

294:                     IERC20Permit(approvals[i].target).permit(

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTOptionsModule.sol#L30-L30

```solidity
File: contracts/tOFT/modules/BaseTOFTStrategyModule.sol

31:              _erc20,

184:         _erc20.approve(address(yieldBox), _amount);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol#L31-L31

```solidity
File: contracts/tokens/BaseTapOFT.sol

335:                 IERC20Permit(approvals[i].target).permit(

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/BaseTapOFT.sol#L335-L335

```solidity
File: contracts/Magnetar/modules/MagnetarMarketModule.sol

157:             IERC20(collateralAddress).approve(

234:             IERC20(assetAddress).approve(address(yieldBox), depositAmount);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L157-L157

```solidity
File: contracts/aave/AaveStrategy.sol

66:          wrappedNative = IERC20(_token);

72:          rewardToken = IERC20(stakedRewardToken.REWARD_TOKEN());

73:          receiptToken = IERC20(_receiptToken);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol#L66-L66

```solidity
File: contracts/balancer/BalancerStrategy.sol

66:          wrappedNative = IERC20(_token);

67:          bal = IERC20(_bal);

78:          IERC20(address(pool)).approve(_vault, type(uint256).max);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L66-L66

```solidity
File: contracts/compound/CompoundStrategy.sol

55:          wrappedNative = IERC20(_token);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol#L55-L55

```solidity
File: contracts/convex/ConvexTricryptoStrategy.sol

93:          wrappedNative = IERC20(_token);

102:         lpToken = IERC20(booster.poolInfo(pid).lptoken);

103:         rewardToken = IERC20(rewardPool.rewardToken());

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L93-L93

```solidity
File: contracts/curve/TricryptoLPStrategy.sol

71:          wrappedNative = IERC20(_token);

76:          lpToken = IERC20(lpGetter.lpToken());

77:          rewardToken = IERC20(lpGauge.crv_token());

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L71-L71

```solidity
File: contracts/curve/TricryptoNativeStrategy.sol

70:          wrappedNative = IERC20(_token);

76:          rewardToken = IERC20(lpGauge.crv_token());

78:          IERC20(lpGetter.lpToken()).approve(_lpGauge, type(uint256).max);

79:          IERC20(lpGetter.lpToken()).approve(_lpGetter, type(uint256).max);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L70-L70

```solidity
File: contracts/glp/GlpStrategy.sol

59:          weth = IERC20(_yieldBox.wrappedNative());

68:          gmx = IERC20(_gmx);

69:          esGmx = IERC20(_gmxRewardRouter.esGmx());

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol#L59-L59

```solidity
File: contracts/lido/LidoEthStrategy.sol

58:          wrappedNative = IERC20(_token);

62:          IERC20(_stEth).approve(_curvePool, type(uint256).max);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol#L58-L58

```solidity
File: contracts/stargate/StargateStrategy.sol

77:          wrappedNative = IERC20(_token);

88:          stgNative = IERC20(_lpToken);

92:          stgTokenReward = IERC20(lpStaking.stargate());

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L77-L77

```solidity
File: contracts/yearn/YearnStrategy.sol

56:          wrappedNative = IERC20(_token);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol#L56-L56

```solidity
File: contracts/YieldBoxURIBuilder.sol

28:                  IERC20 token = IERC20(asset.contractAddress);

58:                  IERC20 token = IERC20(asset.contractAddress);

72:              IERC20 token = IERC20(asset.contractAddress);

94:              IERC20 token = IERC20(asset.contractAddress);

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxURIBuilder.sol#L28-L28

</details>

### [D&#x2011;06] ~~Tokens may be minted to `address(0x0)`~~
In the cases below, `_mint()` prevents minting to `address(0x0)`

*There are 10 instances of this issue:*

```solidity
File: contracts/usd0/USDO.sol

81       function flashLoan(
82           IERC3156FlashBorrower receiver,
83           address token,
84           uint256 amount,
85           bytes calldata data
86       ) external override notPaused returns (bool) {
87           require(token == address(this), "USDO: token not valid");
88           require(maxFlashLoan(token) >= amount, "USDO: amount too big");
89           require(amount > 0, "USDO: amount not valid");
90           uint256 fee = flashFee(token, amount);
91           _mint(address(receiver), amount);
92   
93           require(
94               receiver.onFlashLoan(msg.sender, token, amount, fee, data) ==
95                   FLASH_MINT_CALLBACK_SUCCESS,
96               "USDO: failed"
97           );
98   
99           uint256 _allowance = allowance(address(receiver), address(this));
100          require(_allowance >= (amount + fee), "USDO: repay not approved");
101          _approve(address(receiver), address(this), _allowance - (amount + fee));
102          _burn(address(receiver), amount + fee);
103          return true;
104:     }

109      function mint(address _to, uint256 _amount) external notPaused {
110          require(allowedMinter[_getChainId()][msg.sender], "USDO: unauthorized");
111          _mint(_to, _amount);
112          emit Minted(_to, _amount);
113:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/USDO.sol#L81-L104

```solidity
File: contracts/tOFT/BaseTOFT.sol

348      function _wrap(
349          address _fromAddress,
350          address _toAddress,
351          uint256 _amount
352      ) internal virtual {
353          if (_fromAddress != msg.sender) {
354              require(
355                  allowance(_fromAddress, msg.sender) >= _amount,
356                  "TOFT_allowed"
357              );
358          }
359          IERC20(erc20).safeTransferFrom(_fromAddress, address(this), _amount);
360          _mint(_toAddress, _amount);
361:     }

363      function _wrapNative(address _toAddress) internal virtual {
364          require(msg.value > 0, "TOFT_0");
365          _mint(_toAddress, msg.value);
366:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFT.sol#L348-L361

```solidity
File: contracts/tokens/LTap.sol

41       function deposit(uint256 amount) external {
42           tapToken.transferFrom(msg.sender, address(this), amount);
43           _mint(msg.sender, amount);
44:      }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/LTap.sol#L41-L44

```solidity
File: contracts/tokens/TapOFT.sol

220      function extractTAP(address _to, uint256 _amount) external notPaused {
221          require(msg.sender == minter, "unauthorized");
222          require(_amount > 0, "amount not valid");
223  
224          uint256 week = _timestampToWeek(block.timestamp);
225          require(emissionForWeek[week] >= _amount, "exceeds allowable amount");
226          _mint(_to, _amount);
227          mintedInWeek[week] += _amount;
228          emit Minted(msg.sender, _to, _amount);
229:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L220-L229

```solidity
File: contracts/NativeTokenFactory.sol

109      function mint(uint256 tokenId, address to, uint256 amount) public onlyOwner(tokenId) {
110          _mint(to, tokenId, amount);
111:     }

127      function batchMint(uint256 tokenId, address[] calldata tos, uint256[] calldata amounts) public onlyOwner(tokenId) {
128          uint256 len = tos.length;
129          for (uint256 i = 0; i < len; i++) {
130              _mint(tos[i], tokenId, amounts[i]);
131          }
132:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/NativeTokenFactory.sol#L109-L111

```solidity
File: contracts/YieldBox.sol

168      function depositNFTAsset(
169          uint256 assetId,
170          address from,
171          address to
172      ) public allowed(from, assetId) returns (uint256 amountOut, uint256 shareOut) {
173          // Checks
174          Asset storage asset = assets[assetId];
175          require(asset.tokenType == TokenType.ERC721, "YieldBox: not ERC721");
176  
177          // Effects
178          _mint(to, assetId, 1);
179  
180          // Interactions
181          IERC721(asset.contractAddress).safeTransferFrom(from, address(asset.strategy), asset.tokenId);
182  
183          asset.strategy.deposited(1);
184  
185          emit Deposited(msg.sender, from, to, assetId, 1, 1, 1, 1, true);
186  
187          return (1, 1);
188:     }

196      function depositETHAsset(uint256 assetId, address to, uint256 amount) public payable returns (uint256 amountOut, uint256 shareOut) {
197          // Checks
198          Asset storage asset = assets[assetId];
199          require(asset.tokenType == TokenType.ERC20 && asset.contractAddress == address(wrappedNative), "YieldBox: not wrappedNative");
200  
201          // Effects
202          uint256 share = amount._toShares(totalSupply[assetId], _tokenBalanceOf(asset), false);
203  
204          _mint(to, assetId, share);
205  
206          // Interactions
207          wrappedNative.deposit{ value: amount }();
208          // Strategies always receive wrappedNative (supporting both wrapped and raw native tokens adds too much complexity)
209          wrappedNative.safeTransfer(address(asset.strategy), amount);
210          asset.strategy.deposited(amount);
211  
212          emit Deposited(msg.sender, msg.sender, to, assetId, amount, share, amountOut, shareOut, false);
213  
214          return (amount, share);
215:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBox.sol#L168-L188


### [D&#x2011;07] ~~Contracts are not using their OZ Upgradeable counterparts~~
The rule is true only when the contract being defined is upgradeable, which isn't the case for these invalid examples

*There are 59 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: contracts/markets/MarketERC20.sol

5:   import {IERC20Permit} from "@openzeppelin/contracts/token/ERC20/extensions/draft-ERC20Permit.sol";

6:   import "@openzeppelin/contracts/utils/cryptography/EIP712.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/MarketERC20.sol#L5-L5

```solidity
File: contracts/usd0/BaseUSDO.sol

8:   import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

9:   import "@openzeppelin/contracts/token/ERC20/extensions/draft-ERC20Permit.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDO.sol#L8-L8

```solidity
File: contracts/usd0/BaseUSDOStorage.sol

8:   import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

9:   import "@openzeppelin/contracts/token/ERC20/extensions/draft-ERC20Permit.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDOStorage.sol#L8-L8

```solidity
File: contracts/Balancer.sol

7:   import "@openzeppelin/contracts/token/ERC20/extensions/IERC20Metadata.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/Balancer.sol#L7-L7

```solidity
File: contracts/TapiocaWrapper.sol

8:   import "@openzeppelin/contracts/utils/Create2.sol";

9:   import "@openzeppelin/contracts/access/Ownable.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/TapiocaWrapper.sol#L8-L8

```solidity
File: contracts/tOFT/BaseTOFTStorage.sol

9:   import "@openzeppelin/contracts/token/ERC20/extensions/draft-ERC20Permit.sol";

10:  import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

11:  import "@openzeppelin/contracts/utils/introspection/ERC165.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFTStorage.sol#L9-L9

```solidity
File: contracts/Vesting.sol

4:   import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

5:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/Vesting.sol#L4-L4

```solidity
File: contracts/governance/twTAP.sol

6:   import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

7:   import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L6-L6

```solidity
File: contracts/option-airdrop/AirdropBroker.sol

4:   import "@openzeppelin/contracts/utils/cryptography/MerkleProof.sol";

6:   import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

7:   import "@openzeppelin/contracts/token/ERC20/IERC20.sol";

8:   import "@openzeppelin/contracts/security/Pausable.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L4-L4

```solidity
File: contracts/option-airdrop/aoTAP.sol

6:   import "@openzeppelin/contracts/token/ERC721/ERC721.sol";

7:   import "@openzeppelin/contracts/token/ERC20/IERC20.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/aoTAP.sol#L6-L6

```solidity
File: contracts/options/TapiocaOptionBroker.sol

5:   import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

6:   import "@openzeppelin/contracts/security/Pausable.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L5-L5

```solidity
File: contracts/options/TapiocaOptionLiquidityProvision.sol

5:   import "@openzeppelin/contracts/token/ERC1155/IERC1155Receiver.sol";

7:   import "@openzeppelin/contracts/token/ERC1155/IERC1155.sol";

8:   import "@openzeppelin/contracts/token/ERC721/ERC721.sol";

9:   import "@openzeppelin/contracts/token/ERC20/IERC20.sol";

10:  import "@openzeppelin/contracts/security/Pausable.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L5-L5

```solidity
File: contracts/options/oTAP.sol

5:   import "@openzeppelin/contracts/token/ERC721/ERC721.sol";

6:   import "@openzeppelin/contracts/token/ERC20/IERC20.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/oTAP.sol#L5-L5

```solidity
File: contracts/tokens/BaseTapOFT.sol

5:   import "@openzeppelin/contracts/token/ERC20/extensions/draft-ERC20Permit.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/BaseTapOFT.sol#L5-L5

```solidity
File: contracts/tokens/LTap.sol

5:   import "@openzeppelin/contracts/token/ERC20/extensions/draft-ERC20Permit.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/LTap.sol#L5-L5

```solidity
File: contracts/tokens/TapOFT.sol

4:   import {ERC20Permit} from "@openzeppelin/contracts/token/ERC20/extensions/draft-ERC20Permit.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L4-L4

```solidity
File: contracts/Magnetar/MagnetarV2.sol

5:   import "@openzeppelin/contracts/access/Ownable.sol";

6:   import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol#L5-L5

```solidity
File: contracts/Magnetar/modules/MagnetarMarketModule.sol

8:   import "@openzeppelin/contracts/utils/introspection/IERC165.sol";

9:   import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

10:  import "@openzeppelin/contracts/token/ERC721/IERC721.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L8-L8

```solidity
File: contracts/Multicall/Multicall3.sol

4:   import "@openzeppelin/contracts/access/Ownable.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Multicall/Multicall3.sol#L4-L4

```solidity
File: contracts/Swapper/BaseSwapper.sol

4:   import "@openzeppelin/contracts/access/Ownable.sol";

5:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

6:   import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/BaseSwapper.sol#L4-L4

```solidity
File: contracts/Swapper/CurveSwapper.sol

4:   import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/CurveSwapper.sol#L4-L4

```solidity
File: contracts/Swapper/UniswapV3Swapper.sol

9:   import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/UniswapV3Swapper.sol#L9-L9

```solidity
File: contracts/oracle/implementations/ARBTriCryptoOracle.sol

5:   import {Math} from "@openzeppelin/contracts/utils/math/Math.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/implementations/ARBTriCryptoOracle.sol#L5-L5

```solidity
File: contracts/aave/AaveStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol#L4-L4

```solidity
File: contracts/balancer/BalancerStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L4-L4

```solidity
File: contracts/compound/CompoundStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol#L4-L4

```solidity
File: contracts/convex/ConvexTricryptoStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L4-L4

```solidity
File: contracts/curve/TricryptoLPStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L4-L4

```solidity
File: contracts/curve/TricryptoNativeStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L4-L4

```solidity
File: contracts/lido/LidoEthStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol#L4-L4

```solidity
File: contracts/stargate/StargateStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L4-L4

```solidity
File: contracts/yearn/YearnStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol#L4-L4

```solidity
File: contracts/YieldBox.sol

36:  import "@openzeppelin/contracts/utils/Strings.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBox.sol#L36-L36

```solidity
File: contracts/YieldBoxPermit.sol

5:   import "@openzeppelin/contracts/utils/cryptography/EIP712.sol";

6:   import "@openzeppelin/contracts/utils/cryptography/ECDSA.sol";

7:   import "@openzeppelin/contracts/utils/Counters.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxPermit.sol#L5-L5

</details>

### [D&#x2011;08] ~~Change `public` function visibility to `external` to save gas~~
Both `public` and `external` functions use the same amount of gas (both deployment and runtime gas), so this finding is invalid

*There are 70 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: contracts/Penrose.sol

199      function singularityMarkets()
200          public
201          view
202          returns (address[] memory markets)
203:     {

209:     function bigBangMarkets() public view returns (address[] memory markets) {

214:     function singularityMasterContractLength() public view returns (uint256) {

219:     function bigBangMasterContractLength() public view returns (uint256) {

232      function withdrawAllMarketFees(
233          IMarket[] calldata markets_,
234          ISwapper[] calldata swappers_,
235          IPenrose.SwapData[] calldata swapData_
236:     ) public notPaused {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/Penrose.sol#L199-L203

```solidity
File: contracts/markets/Market.sol

256      function computeClosingFactor(
257          uint256 borrowPart,
258          uint256 collateralPartInAsset,
259          uint256 borrowPartDecimals,
260          uint256 collateralPartDecimals,
261          uint256 ratesPrecision
262:     ) public view returns (uint256) {

305      function computeTVLInfo(
306          address user,
307          uint256 _exchangeRate
308      )
309          public
310          view
311          returns (uint256 amountToSolvency, uint256 minTVL, uint256 maxTVL)
312:     {

356      function computeLiquidatorReward(
357          address user,
358          uint256 _exchangeRate
359:     ) public view returns (uint256) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/Market.sol#L256-L262

```solidity
File: contracts/markets/MarketERC20.sol

116:     function nonces(address owner) public view returns (uint256) {

201      function approveBorrow(
202          address spender,
203          uint256 amount
204:     ) public returns (bool) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/MarketERC20.sol#L116-L116

```solidity
File: contracts/markets/bigBang/BigBang.sol

242      function borrow(
243          address from,
244          address to,
245          uint256 amount
246:     ) public notPaused solvent(from) returns (uint256 part, uint256 share) {

263      function repay(
264          address from,
265          address to,
266          bool,
267          uint256 part
268:     ) public notPaused allowedBorrow(from, part) returns (uint256 amount) {

282      function addCollateral(
283          address from,
284          address to,
285          bool skim,
286          uint256 amount,
287          uint256 share
288:     ) public allowedBorrow(from, share) notPaused {

296      function removeCollateral(
297          address from,
298          address to,
299          uint256 share
300:     ) public notPaused solvent(from) allowedBorrow(from, share) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L242-L246

```solidity
File: contracts/markets/singularity/SGLBorrow.sol

21       function borrow(
22           address from,
23           address to,
24           uint256 amount
25:      ) public notPaused solvent(from) returns (uint256 part, uint256 share) {

45       function repay(
46           address from,
47           address to,
48           bool skim,
49           uint256 part
50:      ) public notPaused allowedBorrow(from, part) returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLBorrow.sol#L21-L25

```solidity
File: contracts/markets/singularity/SGLCollateral.sol

21       function addCollateral(
22           address from,
23           address to,
24           bool skim,
25           uint256 amount,
26           uint256 share
27:      ) public notPaused allowedBorrow(from, share) {

35       function removeCollateral(
36           address from,
37           address to,
38           uint256 share
39:      ) public notPaused solvent(from) allowedBorrow(from, share) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLCollateral.sol#L21-L27

```solidity
File: contracts/markets/singularity/SGLCommon.sol

17:      function accrue() public {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol#L17-L17

```solidity
File: contracts/markets/singularity/SGLStorage.sol

154:     function symbol() public view returns (string memory) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLStorage.sol#L154-L154

```solidity
File: contracts/markets/singularity/Singularity.sol

204      function addAsset(
205          address from,
206          address to,
207          bool skim,
208          uint256 share
209:     ) public notPaused allowedLend(from, share) returns (uint256 fraction) {

219      function removeAsset(
220          address from,
221          address to,
222          uint256 fraction
223:     ) public notPaused returns (uint256 share) {

235      function addCollateral(
236          address from,
237          address to,
238          bool skim,
239          uint256 amount,
240          uint256 share
241:     ) public {

259:     function removeCollateral(address from, address to, uint256 share) public {

277      function borrow(
278          address from,
279          address to,
280          uint256 amount
281:     ) public returns (uint256 part, uint256 share) {

296      function repay(
297          address from,
298          address to,
299          bool skim,
300          uint256 part
301:     ) public returns (uint256 amount) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L204-L209

```solidity
File: contracts/usd0/modules/USDOLeverageModule.sol

93:      function multiHop(bytes memory _payload) public {

133      function leverageUp(
134          address module,
135          uint16 _srcChainId,
136          bytes memory _srcAddress,
137          uint64 _nonce,
138          bytes memory _payload
139:     ) public {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol#L93-L93

```solidity
File: contracts/usd0/modules/USDOMarketModule.sol

104:     function remove(bytes memory _payload) public {

134      function lend(
135          address module,
136          uint16 _srcChainId,
137          bytes memory _srcAddress,
138          uint64 _nonce,
139          bytes memory _payload
140:     ) public {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOMarketModule.sol#L104-L104

```solidity
File: contracts/usd0/modules/USDOOptionsModule.sol

103:     function sendFromDestination(bytes memory _payload) public {

138      function exercise(
139          address module,
140          uint16 _srcChainId,
141          bytes memory _srcAddress,
142          uint64 _nonce,
143          bytes memory _payload
144:     ) public {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOOptionsModule.sol#L103-L103

```solidity
File: contracts/tOFT/modules/BaseTOFTLeverageModule.sol

111:     function multiHop(bytes memory _payload) public {

148      function leverageDown(
149          address module,
150          uint16 _srcChainId,
151          bytes memory _srcAddress,
152          uint64 _nonce,
153          bytes memory _payload
154:     ) public {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol#L111-L111

```solidity
File: contracts/tOFT/modules/BaseTOFTMarketModule.sol

126      function borrow(
127          address module,
128          uint16 _srcChainId,
129          bytes memory _srcAddress,
130          uint64 _nonce,
131          bytes memory _payload
132:     ) public payable {

204:     function remove(bytes memory _payload) public {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTMarketModule.sol#L126-L132

```solidity
File: contracts/tOFT/modules/BaseTOFTOptionsModule.sol

118:     function sendFromDestination(bytes memory _payload) public {

153      function exercise(
154          address module,
155          uint16 _srcChainId,
156          bytes memory _srcAddress,
157          uint64 _nonce,
158          bytes memory _payload
159:     ) public {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTOptionsModule.sol#L118-L118

```solidity
File: contracts/tOFT/modules/BaseTOFTStrategyModule.sol

122      function strategyDeposit(
123          address module,
124          uint16 _srcChainId,
125          bytes memory _srcAddress,
126          uint64 _nonce,
127          bytes memory _payload,
128          IERC20 _erc20
129:     ) public {

188      function strategyWithdraw(
189          uint16 _srcChainId,
190          bytes memory _payload
191:     ) public {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol#L122-L129

```solidity
File: contracts/governance/twTAP.sol

155      function getParticipation(
156          uint _tokenId
157:     ) public view returns (Participation memory participant) {

397:     function advanceWeek(uint256 _limit) public {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L155-L157

```solidity
File: contracts/Magnetar/MagnetarV2.sol

76       function getCollateralAmountForShare(
77           IMarket market,
78           uint256 share
79:      ) public view returns (uint256 amount) {

89       function getCollateralSharesForBorrowPart(
90           IMarket market,
91           uint256 borrowPart,
92           uint256 liquidationMultiplierPrecision,
93           uint256 exchangeRatePrecision
94:      ) public view returns (uint256 collateralShares) {

117      function getAmountForBorrowPart(
118          IMarket market,
119          uint256 borrowPart
120:     ) public view returns (uint256 amount) {

133      function getBorrowPartForAmount(
134          IMarket market,
135          uint256 amount
136:     ) public view returns (uint256 part) {

150      function getAmountForAssetFraction(
151          ISingularity singularity,
152          uint256 fraction
153:     ) public view returns (uint256 amount) {

171      function getFractionForAmount(
172          ISingularity singularity,
173          uint256 amount
174:     ) public view returns (uint256 fraction) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol#L76-L79

```solidity
File: contracts/Multicall/Multicall3.sol

41       function multicall(
42           Call[] calldata calls
43:      ) public payable returns (Result[] memory returnData) {

63       function multicallValue(
64           CallValue[] calldata calls
65:      ) public payable returns (Result[] memory returnData) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Multicall/Multicall3.sol#L41-L43

```solidity
File: contracts/balancer/BalancerStrategy.sol

117:     function compound(bytes memory) public {}

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L117-L117

```solidity
File: contracts/compound/CompoundStrategy.sol

80:      function compoundAmount() public pure returns (uint256 result) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol#L80-L80

```solidity
File: contracts/curve/TricryptoNativeStrategy.sol

103:     function compoundAmount() public returns (uint256 result) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L103-L103

```solidity
File: contracts/glp/GlpStrategy.sol

104:     function harvestGmx(uint256 priceNum, uint256 priceDenom) public onlyOwner {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol#L104-L104

```solidity
File: contracts/lido/LidoEthStrategy.sol

84:      function compoundAmount() public pure returns (uint256 result) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol#L84-L84

```solidity
File: contracts/yearn/YearnStrategy.sol

81:      function compoundAmount() public pure returns (uint256 result) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol#L81-L81

```solidity
File: contracts/NativeTokenFactory.sol

56:      function transferOwnership(uint256 tokenId, address newOwner, bool direct, bool renounce) public onlyOwner(tokenId) {

73:      function claimOwnership(uint256 tokenId) public {

90:      function createToken(string calldata name, string calldata symbol, uint8 decimals, string calldata uri) public returns (uint32 tokenId) {

109:     function mint(uint256 tokenId, address to, uint256 amount) public onlyOwner(tokenId) {

116:     function burn(uint256 tokenId, address from, uint256 amount) public allowed(from, tokenId) {

127:     function batchMint(uint256 tokenId, address[] calldata tos, uint256[] calldata amounts) public onlyOwner(tokenId) {

138:     function batchBurn(uint256 tokenId, address[] calldata froms, uint256[] calldata amounts) public {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/NativeTokenFactory.sol#L56-L56

```solidity
File: contracts/YieldBox.sol

168      function depositNFTAsset(
169          uint256 assetId,
170          address from,
171          address to
172:     ) public allowed(from, assetId) returns (uint256 amountOut, uint256 shareOut) {

223      function withdraw(
224          uint256 assetId,
225          address from,
226          address to,
227          uint256 amount,
228          uint256 share
229:     ) public allowed(from, assetId) returns (uint256 amountOut, uint256 shareOut) {

303:     function transfer(address from, address to, uint256 assetId, uint256 share) public allowed(from, assetId) {

307:     function batchTransfer(address from, address to, uint256[] calldata assetIds_, uint256[] calldata shares_) public {

336:     function transferMultiple(address from, address[] calldata tos, uint256 assetId, uint256[] calldata shares) public allowed(from, assetId) {

477      function deposit(
478          TokenType tokenType,
479          address contractAddress,
480          IStrategy strategy,
481          uint256 tokenId,
482          address from,
483          address to,
484          uint256 amount,
485          uint256 share
486:     ) public returns (uint256 amountOut, uint256 shareOut) {

500:     function depositETH(IStrategy strategy, address to, uint256 amount) public payable returns (uint256 amountOut, uint256 shareOut) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBox.sol#L168-L172

</details>

### [D&#x2011;09] ~~Save gas with the use of specific import statements~~
Importing whole files rather than specific identifiers [does not waste gas](https://ethereum.stackexchange.com/questions/138876/does-solidity-optimizer-eliminate-unused-internal-functions-of-libraries), so this finding is invalid

*There are 324 instances of this issue:*

<details>
<summary>see instances</summary>


```solidity
File: contracts/Penrose.sol

4:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

5:   import "@boringcrypto/boring-solidity/contracts/BoringFactory.sol";

7:   import "tapioca-sdk/dist/contracts/YieldBox/contracts/YieldBox.sol";

8:   import "tapioca-sdk/dist/contracts/YieldBox/contracts/interfaces/IYieldBox.sol";

9:   import "tapioca-sdk/dist/contracts/YieldBox/contracts/strategies/ERC20WithoutStrategy.sol";

10:  import "tapioca-periph/contracts/interfaces/ISingularity.sol";

11:  import "tapioca-periph/contracts/interfaces/IPenrose.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/Penrose.sol#L4-L4

```solidity
File: contracts/markets/Market.sol

4:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

5:   import "@boringcrypto/boring-solidity/contracts/libraries/BoringRebase.sol";

7:   import "tapioca-sdk/dist/contracts/YieldBox/contracts/YieldBox.sol";

8:   import "tapioca-periph/contracts/interfaces/IOracle.sol";

9:   import "tapioca-periph/contracts/interfaces/IPenrose.sol";

10:  import "./MarketERC20.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/Market.sol#L4-L4

```solidity
File: contracts/markets/MarketERC20.sol

6:   import "@openzeppelin/contracts/utils/cryptography/EIP712.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/MarketERC20.sol#L6-L6

```solidity
File: contracts/markets/bigBang/BigBang.sol

4:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

5:   import "@boringcrypto/boring-solidity/contracts/ERC20.sol";

7:   import "tapioca-periph/contracts/interfaces/IBigBang.sol";

8:   import "tapioca-periph/contracts/interfaces/ISendFrom.sol";

9:   import "tapioca-periph/contracts/interfaces/ISwapper.sol";

12:  import "../Market.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L4-L4

```solidity
File: contracts/markets/singularity/SGLBorrow.sol

4:   import "./SGLLendingCommon.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLBorrow.sol#L4-L4

```solidity
File: contracts/markets/singularity/SGLCollateral.sol

4:   import "./SGLLendingCommon.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLCollateral.sol#L4-L4

```solidity
File: contracts/markets/singularity/SGLCommon.sol

4:   import "./SGLStorage.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol#L4-L4

```solidity
File: contracts/markets/singularity/SGLLendingCommon.sol

4:   import "./SGLCommon.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLendingCommon.sol#L4-L4

```solidity
File: contracts/markets/singularity/SGLLeverage.sol

4:   import "./SGLLendingCommon.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLeverage.sol#L4-L4

```solidity
File: contracts/markets/singularity/SGLLiquidation.sol

4:   import "./SGLCommon.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L4-L4

```solidity
File: contracts/markets/singularity/SGLStorage.sol

4:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

5:   import "@boringcrypto/boring-solidity/contracts/libraries/BoringERC20.sol";

6:   import "@boringcrypto/boring-solidity/contracts/libraries/BoringRebase.sol";

8:   import "tapioca-periph/contracts/interfaces/ISwapper.sol";

9:   import "tapioca-periph/contracts/interfaces/IPenrose.sol";

10:  import "tapioca-periph/contracts/interfaces/ISingularity.sol";

11:  import "tapioca-periph/contracts/interfaces/ILiquidationQueue.sol";

12:  import "tapioca-sdk/dist/contracts/YieldBox/contracts/YieldBox.sol";

14:  import "../Market.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/SGLStorage.sol#L4-L4

```solidity
File: contracts/markets/singularity/Singularity.sol

4:   import "./SGLCommon.sol";

5:   import "./SGLLiquidation.sol";

6:   import "./SGLCollateral.sol";

7:   import "./SGLBorrow.sol";

8:   import "./SGLLeverage.sol";

10:  import "tapioca-periph/contracts/interfaces/ISendFrom.sol";

11:  import "tapioca-sdk/dist/contracts/libraries/LzLib.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L4-L4

```solidity
File: contracts/usd0/BaseUSDO.sol

5:   import "tapioca-sdk/dist/contracts/token/oft/v2/OFTV2.sol";

8:   import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

9:   import "@openzeppelin/contracts/token/ERC20/extensions/draft-ERC20Permit.sol";

12:  import "tapioca-periph/contracts/interfaces/IYieldBoxBase.sol";

14:  import "tapioca-periph/contracts/interfaces/ICommonData.sol";

16:  import "./BaseUSDOStorage.sol";

17:  import "./modules/USDOLeverageModule.sol";

18:  import "./modules/USDOMarketModule.sol";

19:  import "./modules/USDOOptionsModule.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDO.sol#L5-L5

```solidity
File: contracts/usd0/BaseUSDOStorage.sol

5:   import "tapioca-sdk/dist/contracts/token/oft/v2/OFTV2.sol";

8:   import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

9:   import "@openzeppelin/contracts/token/ERC20/extensions/draft-ERC20Permit.sol";

12:  import "tapioca-periph/contracts/interfaces/IYieldBoxBase.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/BaseUSDOStorage.sol#L5-L5

```solidity
File: contracts/usd0/USDO.sol

4:   import "tapioca-sdk/dist/contracts/interfaces/ILayerZeroEndpoint.sol";

5:   import "tapioca-periph/contracts/interfaces/IERC3156FlashLender.sol";

6:   import "./BaseUSDO.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/USDO.sol#L4-L4

```solidity
File: contracts/usd0/modules/USDOLeverageModule.sol

5:   import "tapioca-sdk/dist/contracts/libraries/LzLib.sol";

9:   import "tapioca-periph/contracts/interfaces/ISwapper.sol";

10:  import "tapioca-periph/contracts/interfaces/ITapiocaOFT.sol";

11:  import "tapioca-periph/contracts/interfaces/ISingularity.sol";

12:  import "tapioca-periph/contracts/interfaces/IPermitBorrow.sol";

13:  import "tapioca-periph/contracts/interfaces/IPermitAll.sol";

15:  import "../BaseUSDOStorage.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol#L5-L5

```solidity
File: contracts/usd0/modules/USDOMarketModule.sol

5:   import "tapioca-sdk/dist/contracts/libraries/LzLib.sol";

8:   import "@boringcrypto/boring-solidity/contracts/libraries/BoringRebase.sol";

10:  import "tapioca-periph/contracts/interfaces/ITapiocaOFT.sol";

11:  import "tapioca-periph/contracts/interfaces/IMagnetar.sol";

12:  import "tapioca-periph/contracts/interfaces/IMarket.sol";

13:  import "tapioca-periph/contracts/interfaces/ISingularity.sol";

14:  import "tapioca-periph/contracts/interfaces/IPermitBorrow.sol";

15:  import "tapioca-periph/contracts/interfaces/IPermitAll.sol";

17:  import "../BaseUSDOStorage.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOMarketModule.sol#L5-L5

```solidity
File: contracts/usd0/modules/USDOOptionsModule.sol

5:   import "tapioca-sdk/dist/contracts/libraries/LzLib.sol";

8:   import "tapioca-periph/contracts/interfaces/IPermitBorrow.sol";

9:   import "tapioca-periph/contracts/interfaces/IPermitAll.sol";

10:  import "tapioca-periph/contracts/interfaces/ITapiocaOptionsBroker.sol";

11:  import "tapioca-periph/contracts/interfaces/ISendFrom.sol";

12:  import "../BaseUSDOStorage.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-bar-audit/contracts/usd0/modules/USDOOptionsModule.sol#L5-L5

```solidity
File: contracts/Balancer.sol

4:   import "tapioca-periph/contracts/interfaces/ITapiocaOFT.sol";

5:   import "tapioca-periph/contracts/interfaces/IStargateRouter.sol";

6:   import "@rari-capital/solmate/src/auth/Owned.sol";

7:   import "@openzeppelin/contracts/token/ERC20/extensions/IERC20Metadata.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/Balancer.sol#L4-L4

```solidity
File: contracts/TapiocaWrapper.sol

4:   import "./tOFT/TapiocaOFT.sol";

5:   import "./tOFT/mTapiocaOFT.sol";

6:   import "tapioca-periph/contracts/interfaces/ITapiocaOFT.sol";

8:   import "@openzeppelin/contracts/utils/Create2.sol";

9:   import "@openzeppelin/contracts/access/Ownable.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/TapiocaWrapper.sol#L4-L4

```solidity
File: contracts/tOFT/BaseTOFT.sol

4:   import "./BaseTOFTStorage.sol";

7:   import "./modules/BaseTOFTLeverageModule.sol";

8:   import "./modules/BaseTOFTStrategyModule.sol";

9:   import "./modules/BaseTOFTMarketModule.sol";

10:  import "./modules/BaseTOFTOptionsModule.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFT.sol#L4-L4

```solidity
File: contracts/tOFT/BaseTOFTStorage.sol

5:   import "tapioca-sdk/dist/contracts/token/oft/v2/OFTV2.sol";

6:   import "tapioca-sdk/dist/contracts/libraries/LzLib.sol";

9:   import "@openzeppelin/contracts/token/ERC20/extensions/draft-ERC20Permit.sol";

10:  import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

11:  import "@openzeppelin/contracts/utils/introspection/ERC165.sol";

14:  import "tapioca-periph/contracts/interfaces/IYieldBoxBase.sol";

15:  import "tapioca-periph/contracts/interfaces/ITapiocaOFT.sol";

16:  import "tapioca-periph/contracts/interfaces/ICommonData.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFTStorage.sol#L5-L5

```solidity
File: contracts/tOFT/TapiocaOFT.sol

3:   import "./BaseTOFT.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/TapiocaOFT.sol#L3-L3

```solidity
File: contracts/tOFT/mTapiocaOFT.sol

3:   import "./BaseTOFT.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol#L3-L3

```solidity
File: contracts/tOFT/modules/BaseTOFTLeverageModule.sol

5:   import "tapioca-sdk/dist/contracts/libraries/LzLib.sol";

9:   import "tapioca-periph/contracts/interfaces/ISwapper.sol";

10:  import "tapioca-periph/contracts/interfaces/IMagnetar.sol";

11:  import "tapioca-periph/contracts/interfaces/ISingularity.sol";

12:  import "tapioca-periph/contracts/interfaces/IPermitBorrow.sol";

13:  import "tapioca-periph/contracts/interfaces/IPermitAll.sol";

14:  import "tapioca-periph/contracts/interfaces/ITapiocaOptionsBroker.sol";

15:  import "tapioca-periph/contracts/interfaces/ITapiocaOptionLiquidityProvision.sol";

17:  import "../BaseTOFTStorage.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol#L5-L5

```solidity
File: contracts/tOFT/modules/BaseTOFTMarketModule.sol

5:   import "tapioca-sdk/dist/contracts/libraries/LzLib.sol";

9:   import "tapioca-periph/contracts/interfaces/ISwapper.sol";

10:  import "tapioca-periph/contracts/interfaces/ITapiocaOFT.sol";

11:  import "tapioca-periph/contracts/interfaces/IMagnetar.sol";

12:  import "tapioca-periph/contracts/interfaces/IMarket.sol";

13:  import "tapioca-periph/contracts/interfaces/IPermitBorrow.sol";

14:  import "tapioca-periph/contracts/interfaces/IPermitAll.sol";

16:  import "../BaseTOFTStorage.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTMarketModule.sol#L5-L5

```solidity
File: contracts/tOFT/modules/BaseTOFTOptionsModule.sol

5:   import "tapioca-sdk/dist/contracts/libraries/LzLib.sol";

8:   import "tapioca-periph/contracts/interfaces/IPermitBorrow.sol";

9:   import "tapioca-periph/contracts/interfaces/IPermitAll.sol";

10:  import "tapioca-periph/contracts/interfaces/ITapiocaOptionsBroker.sol";

12:  import "../BaseTOFTStorage.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTOptionsModule.sol#L5-L5

```solidity
File: contracts/tOFT/modules/BaseTOFTStrategyModule.sol

5:   import "tapioca-sdk/dist/contracts/libraries/LzLib.sol";

9:   import "tapioca-periph/contracts/interfaces/ISwapper.sol";

10:  import "tapioca-periph/contracts/interfaces/ITapiocaOFT.sol";

12:  import "../BaseTOFTStorage.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol#L5-L5

```solidity
File: contracts/Vesting.sol

4:   import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

5:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

6:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/Vesting.sol#L4-L4

```solidity
File: contracts/governance/twTAP.sol

6:   import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

7:   import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

8:   import "tapioca-sdk/dist/contracts/util/ERC4494.sol";

9:   import "../tokens/TapOFT.sol";

10:  import "../twAML.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L6-L6

```solidity
File: contracts/option-airdrop/AirdropBroker.sol

4:   import "@openzeppelin/contracts/utils/cryptography/MerkleProof.sol";

5:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

6:   import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

7:   import "@openzeppelin/contracts/token/ERC20/IERC20.sol";

8:   import "@openzeppelin/contracts/security/Pausable.sol";

9:   import "tapioca-periph/contracts/interfaces/IOracle.sol";

10:  import "../tokens/TapOFT.sol";

11:  import "../twAML.sol";

12:  import "./aoTAP.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L4-L4

```solidity
File: contracts/option-airdrop/aoTAP.sol

5:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

6:   import "@openzeppelin/contracts/token/ERC721/ERC721.sol";

7:   import "@openzeppelin/contracts/token/ERC20/IERC20.sol";

9:   import "tapioca-sdk/dist/contracts/util/ERC4494.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/option-airdrop/aoTAP.sol#L5-L5

```solidity
File: contracts/options/TapiocaOptionBroker.sol

4:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

5:   import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

6:   import "@openzeppelin/contracts/security/Pausable.sol";

7:   import "tapioca-periph/contracts/interfaces/IOracle.sol";

8:   import "./TapiocaOptionLiquidityProvision.sol";

9:   import "../tokens/TapOFT.sol";

10:  import "../twAML.sol";

11:  import "./oTAP.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L4-L4

```solidity
File: contracts/options/TapiocaOptionLiquidityProvision.sol

5:   import "@openzeppelin/contracts/token/ERC1155/IERC1155Receiver.sol";

6:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

7:   import "@openzeppelin/contracts/token/ERC1155/IERC1155.sol";

8:   import "@openzeppelin/contracts/token/ERC721/ERC721.sol";

9:   import "@openzeppelin/contracts/token/ERC20/IERC20.sol";

10:  import "@openzeppelin/contracts/security/Pausable.sol";

11:  import "tapioca-sdk/dist/contracts/util/ERC4494.sol";

12:  import "tapioca-sdk/dist/contracts/YieldBox/contracts/interfaces/IYieldBox.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L5-L5

```solidity
File: contracts/options/oTAP.sol

5:   import "@openzeppelin/contracts/token/ERC721/ERC721.sol";

6:   import "@openzeppelin/contracts/token/ERC20/IERC20.sol";

7:   import "tapioca-sdk/dist/contracts/util/ERC4494.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/oTAP.sol#L5-L5

```solidity
File: contracts/tokens/BaseTapOFT.sol

5:   import "@openzeppelin/contracts/token/ERC20/extensions/draft-ERC20Permit.sol";

7:   import "tapioca-periph/contracts/interfaces/ITapiocaOFT.sol";

8:   import "tapioca-sdk/dist/contracts/token/oft/v2/OFTV2.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/BaseTapOFT.sol#L5-L5

```solidity
File: contracts/tokens/LTap.sol

4:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

5:   import "@openzeppelin/contracts/token/ERC20/extensions/draft-ERC20Permit.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/LTap.sol#L4-L4

```solidity
File: contracts/tokens/TapOFT.sol

5:   import "./BaseTapOFT.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/tokens/TapOFT.sol#L5-L5

```solidity
File: contracts/Magnetar/modules/MagnetarMarketModule.sol

16:  import "../MagnetarV2Storage.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L16-L16

```solidity
File: contracts/Multicall/Multicall3.sol

4:   import "@openzeppelin/contracts/access/Ownable.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Multicall/Multicall3.sol#L4-L4

```solidity
File: contracts/Swapper/BaseSwapper.sol

4:   import "@openzeppelin/contracts/access/Ownable.sol";

5:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

6:   import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

7:   import "tapioca-sdk/dist/contracts/YieldBox/contracts/interfaces/IYieldBox.sol";

9:   import "../interfaces/ISwapper.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/BaseSwapper.sol#L4-L4

```solidity
File: contracts/Swapper/CurveSwapper.sol

4:   import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

5:   import "./interfaces/ICurvePool.sol";

6:   import "./BaseSwapper.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/CurveSwapper.sol#L4-L4

```solidity
File: contracts/Swapper/UniswapV2Swapper.sol

4:   import "./interfaces/IUniswapV2Factory.sol";

5:   import "./interfaces/IUniswapV2Router02.sol";

6:   import "./BaseSwapper.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/UniswapV2Swapper.sol#L4-L4

```solidity
File: contracts/Swapper/UniswapV3Swapper.sol

4:   import "@uniswap/v3-periphery/contracts/interfaces/ISwapRouter.sol";

5:   import "@uniswap/v3-core/contracts/interfaces/IUniswapV3Pool.sol";

6:   import "@uniswap/v3-core/contracts/interfaces/IUniswapV3Factory.sol";

7:   import "@uniswap/v3-periphery/contracts/libraries/TransferHelper.sol";

8:   import "@uniswap/v3-periphery/contracts/interfaces/IQuoterV2.sol";

9:   import "@openzeppelin/contracts/token/ERC20/utils/SafeERC20.sol";

11:  import "./libraries/OracleLibrary.sol";

12:  import "./BaseSwapper.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Swapper/UniswapV3Swapper.sol#L4-L4

```solidity
File: contracts/oracle/Seer.sol

4:   import "./OracleMulti.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/oracle/Seer.sol#L4-L4

```solidity
File: contracts/aave/AaveStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

6:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

7:   import "@boringcrypto/boring-solidity/contracts/interfaces/IERC20.sol";

8:   import "@boringcrypto/boring-solidity/contracts/libraries/BoringERC20.sol";

10:  import "tapioca-sdk/dist/contracts/YieldBox/contracts/strategies/BaseStrategy.sol";

11:  import "../../tapioca-periph/contracts/interfaces/ISwapper.sol";

12:  import "./interfaces/IStkAave.sol";

13:  import "./interfaces/ILendingPool.sol";

14:  import "./interfaces/IIncentivesController.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol#L4-L4

```solidity
File: contracts/balancer/BalancerStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

6:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

7:   import "@boringcrypto/boring-solidity/contracts/interfaces/IERC20.sol";

8:   import "@boringcrypto/boring-solidity/contracts/libraries/BoringERC20.sol";

10:  import "tapioca-sdk/dist/contracts/YieldBox/contracts/strategies/BaseStrategy.sol";

11:  import "./interfaces/IBalancerVault.sol";

12:  import "./interfaces/IBalancerPool.sol";

13:  import "./interfaces/IBalancerHelpers.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L4-L4

```solidity
File: contracts/compound/CompoundStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

6:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

7:   import "@boringcrypto/boring-solidity/contracts/interfaces/IERC20.sol";

8:   import "@boringcrypto/boring-solidity/contracts/libraries/BoringERC20.sol";

10:  import "tapioca-sdk/dist/contracts/YieldBox/contracts/strategies/BaseStrategy.sol";

12:  import "../../tapioca-periph/contracts/interfaces/INative.sol";

13:  import "./interfaces/ICToken.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol#L4-L4

```solidity
File: contracts/convex/ConvexTricryptoStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

6:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

7:   import "@boringcrypto/boring-solidity/contracts/interfaces/IERC20.sol";

8:   import "@boringcrypto/boring-solidity/contracts/libraries/BoringERC20.sol";

10:  import "tapioca-sdk/dist/contracts/YieldBox/contracts/strategies/BaseStrategy.sol";

11:  import "../../tapioca-periph/contracts/interfaces/ISwapper.sol";

12:  import "../curve/interfaces/ITricryptoLPGetter.sol";

14:  import "./interfaces/IConvexBooster.sol";

15:  import "./interfaces/IConvexRewardPool.sol";

16:  import "./interfaces/IConvexZap.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L4-L4

```solidity
File: contracts/curve/TricryptoLPStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

6:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

7:   import "@boringcrypto/boring-solidity/contracts/interfaces/IERC20.sol";

8:   import "@boringcrypto/boring-solidity/contracts/libraries/BoringERC20.sol";

10:  import "tapioca-sdk/dist/contracts/YieldBox/contracts/strategies/BaseStrategy.sol";

11:  import "../../tapioca-periph/contracts/interfaces/ISwapper.sol";

13:  import "./interfaces/ITricryptoLPGetter.sol";

14:  import "./interfaces/ITricryptoLPGauge.sol";

15:  import "./interfaces/ICurveMinter.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L4-L4

```solidity
File: contracts/curve/TricryptoNativeStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

6:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

7:   import "@boringcrypto/boring-solidity/contracts/interfaces/IERC20.sol";

8:   import "@boringcrypto/boring-solidity/contracts/libraries/BoringERC20.sol";

10:  import "tapioca-sdk/dist/contracts/YieldBox/contracts/strategies/BaseStrategy.sol";

11:  import "../../tapioca-periph/contracts/interfaces/ISwapper.sol";

13:  import "./interfaces/ITricryptoLPGetter.sol";

14:  import "./interfaces/ITricryptoLPGauge.sol";

15:  import "./interfaces/ICurveMinter.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L4-L4

```solidity
File: contracts/glp/GlpStrategy.sol

5:   import "@boringcrypto/boring-solidity/contracts/interfaces/IERC20.sol";

6:   import "@boringcrypto/boring-solidity/contracts/libraries/BoringERC20.sol";

7:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

9:   import "@uniswap/v3-core/contracts/interfaces/IUniswapV3Pool.sol";

11:  import "tapioca-sdk/dist/contracts/YieldBox/contracts/enums/YieldBoxTokenType.sol";

12:  import "tapioca-sdk/dist/contracts/YieldBox/contracts/strategies/BaseStrategy.sol";

14:  import "../interfaces/IFeeCollector.sol";

15:  import "../interfaces/gmx/IGlpManager.sol";

16:  import "../interfaces/gmx/IGmxRewardDistributor.sol";

17:  import "../interfaces/gmx/IGmxRewardRouter.sol";

18:  import "../interfaces/gmx/IGmxRewardTracker.sol";

19:  import "../interfaces/gmx/IGmxVester.sol";

20:  import "../interfaces/gmx/IGmxVault.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol#L5-L5

```solidity
File: contracts/lido/LidoEthStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

6:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

7:   import "@boringcrypto/boring-solidity/contracts/interfaces/IERC20.sol";

8:   import "@boringcrypto/boring-solidity/contracts/libraries/BoringERC20.sol";

10:  import "tapioca-sdk/dist/contracts/YieldBox/contracts/strategies/BaseStrategy.sol";

12:  import "./interfaces/IStEth.sol";

13:  import "./interfaces/ICurveEthStEthPool.sol";

14:  import "../../tapioca-periph/contracts/interfaces/INative.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol#L4-L4

```solidity
File: contracts/stargate/StargateStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

6:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

7:   import "@boringcrypto/boring-solidity/contracts/interfaces/IERC20.sol";

8:   import "@boringcrypto/boring-solidity/contracts/libraries/BoringERC20.sol";

10:  import "tapioca-sdk/dist/contracts/YieldBox/contracts/strategies/BaseStrategy.sol";

11:  import "../../tapioca-periph/contracts/interfaces/ISwapper.sol";

13:  import "./interfaces/IRouter.sol";

14:  import "./interfaces/IRouterETH.sol";

15:  import "./interfaces/ILPStaking.sol";

16:  import "../../tapioca-periph/contracts/interfaces/INative.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L4-L4

```solidity
File: contracts/yearn/YearnStrategy.sol

4:   import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

6:   import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

7:   import "@boringcrypto/boring-solidity/contracts/interfaces/IERC20.sol";

8:   import "@boringcrypto/boring-solidity/contracts/libraries/BoringERC20.sol";

10:  import "tapioca-sdk/dist/contracts/YieldBox/contracts/strategies/BaseStrategy.sol";

12:  import "./interfaces/IYearnVault.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol#L4-L4

```solidity
File: contracts/NativeTokenFactory.sol

3:   import "./AssetRegister.sol";

4:   import "./BoringMath.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/NativeTokenFactory.sol#L3-L3

```solidity
File: contracts/YieldBox.sol

26:  import "./interfaces/IWrappedNative.sol";

27:  import "./interfaces/IStrategy.sol";

28:  import "@boringcrypto/boring-solidity/contracts/interfaces/IERC721.sol";

29:  import "@boringcrypto/boring-solidity/contracts/interfaces/IERC1155.sol";

30:  import "@boringcrypto/boring-solidity/contracts/libraries/Base64.sol";

31:  import "@boringcrypto/boring-solidity/contracts/Domain.sol";

32:  import "./ERC721TokenReceiver.sol";

33:  import "./ERC1155TokenReceiver.sol";

34:  import "./ERC1155.sol";

35:  import "@boringcrypto/boring-solidity/contracts/BoringBatchable.sol";

36:  import "@openzeppelin/contracts/utils/Strings.sol";

37:  import "./AssetRegister.sol";

38:  import "./NativeTokenFactory.sol";

39:  import "./YieldBoxRebase.sol";

40:  import "./YieldBoxURIBuilder.sol";

41:  import "./YieldBoxPermit.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBox.sol#L26-L26

```solidity
File: contracts/YieldBoxPermit.sol

5:   import "@openzeppelin/contracts/utils/cryptography/EIP712.sol";

6:   import "@openzeppelin/contracts/utils/cryptography/ECDSA.sol";

7:   import "@openzeppelin/contracts/utils/Counters.sol";

8:   import "./interfaces/IYieldBox.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxPermit.sol#L5-L5

```solidity
File: contracts/YieldBoxRebase.sol

5:   import "./interfaces/IStrategy.sol";

6:   import "@boringcrypto/boring-solidity/contracts/interfaces/IERC1155.sol";

7:   import "@boringcrypto/boring-solidity/contracts/libraries/Base64.sol";

8:   import "@boringcrypto/boring-solidity/contracts/libraries/BoringAddress.sol";

9:   import "@boringcrypto/boring-solidity/contracts/libraries/BoringERC20.sol";

10:  import "@boringcrypto/boring-solidity/contracts/Domain.sol";

11:  import "./ERC1155TokenReceiver.sol";

12:  import "./ERC1155.sol";

13:  import "@boringcrypto/boring-solidity/contracts/BoringBatchable.sol";

14:  import "@boringcrypto/boring-solidity/contracts/BoringFactory.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxRebase.sol#L5-L5

```solidity
File: contracts/YieldBoxURIBuilder.sol

3:   import "@openzeppelin/contracts/utils/Strings.sol";

4:   import "@boringcrypto/boring-solidity/contracts/libraries/Base64.sol";

5:   import "@boringcrypto/boring-solidity/contracts/libraries/BoringERC20.sol";

6:   import "./interfaces/IYieldBox.sol";

7:   import "./NativeTokenFactory.sol";

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/YieldBox/contracts/YieldBoxURIBuilder.sol#L3-L3

</details>

### [D&#x2011;10] ~~`safeTransfer` function does not check for contract existence~~
The examples below are either not token transfers, or are making high-level `transfer()`/`transferFrom()` calls (which check for contract existence), or are from a library that checks for contract existence.

*There are 2 instances of this issue:*

```solidity
File: contracts/tOFT/BaseTOFT.sol

379      function _safeTransferETH(address to, uint256 amount) internal {
380          (bool sent, ) = to.call{value: amount}("");
381          require(sent, "TOFT_failed");
382:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/BaseTOFT.sol#L379-L382

```solidity
File: contracts/tOFT/modules/BaseTOFTLeverageModule.sol

279      function _safeTransferETH(address to, uint256 amount) private {
280          (bool sent, ) = to.call{value: amount}("");
281          require(sent, "TOFT_failed");
282:     }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol#L279-L282


### [D&#x2011;11] ~~Shorten the array rather than copying to a new one~~
None of these examples are of filtering out entries from an array.

*There are 7 instances of this issue:*

```solidity
File: contracts/governance/twTAP.sol

170          uint256[] memory result = new uint256[](len);
171  
172          Participation memory position = participants[_tokenId];
173:         uint256 votes;

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/governance/twTAP.sol#L170-L173

```solidity
File: contracts/options/TapiocaOptionLiquidityProvision.sol

134          SingularityPool[] memory pools = new SingularityPool[](len);
135          unchecked {
136              for (uint256 i = 0; i < len; ++i) {
137:                 pools[i] = activeSingularities[

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L134-L137

```solidity
File: contracts/Magnetar/MagnetarV2.sol

970          SingularityInfo[] memory result = new SingularityInfo[](len);
971  
972          Rebase memory _totalAsset;
973:         for (uint256 i = 0; i < len; i++) {

1001         BigBangInfo[] memory result = new BigBangInfo[](len);
1002 
1003         IBigBang.AccrueInfo memory _accrueInfo;
1004:        for (uint256 i = 0; i < len; i++) {

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol#L970-L973

```solidity
File: contracts/convex/ConvexTricryptoStrategy.sol

254          uint256[] memory balancesBefore = new uint256[](tempData.tokens.length);
255          for (uint256 i = 0; i < tempData.tokens.length; i++) {
256              balancesBefore[i] = IERC20(tempData.tokens[i]).balanceOf(
257:                 address(this)

272          uint256[] memory balancesAfter = new uint256[](tempData.tokens.length);
273          for (uint256 i = 0; i < tempData.tokens.length; i++) {
274              balancesAfter[i] = IERC20(tempData.tokens[i]).balanceOf(
275:                 address(this)

279          uint256[] memory finalBalances = new uint256[](tempData.tokens.length);
280          for (uint256 i = 0; i < tempData.tokens.length; i++) {
281              finalBalances[i] = balancesAfter[i] - balancesBefore[i];
282:         }

```
https://github.com/code-423n4/2023-07-tapioca/blob/e6eef060495b31173578570215e80f9e95330b9a/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L254-L257