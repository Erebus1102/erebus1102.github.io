---
title: Layer 1 基础设施
tags:
  - Crypto
  - Financial
  - Transaction
---
> [!TIP] 为什么Layer1链非常重要
	- Market cap is huge
	- Leading market narratives on a multi-year spanThe building blocks of everything else
	- Therefore, large opportunities in investment

---
# Bitcoin
> [!TIP] 
## 安全保障机制
* to remove a block, need to convince 51% of mining power (persistence)
* to block a Tx from being posted, need to convince 51% of mining power (liveliness)
* mining hash power == \$\$\$
	* the more hash rate, the safer a PoW network is
## Bitcoin 挖矿奖励
## Bitcoin 数据结构
![Bitcoin DataStructure](1685841363913.png)
## POW Example
	工作量证明（Proof of work）需要一台计算机随机进行哈希函数，直到得到输出的前导零达到正确的最小数量。例如，于2023年2月9日挖掘的第775,771个区块的哈希值为：00000000000000000003aa2696b1b7248db53a5a7f72d1fd98916c761e954354。该成功哈希的区块奖励为6.25个比特币和0.1360个比特币的手续费。随机数为2,881,347,934，区块中有1,519个交易，区块的总价值为1,665.9645个比特币。需要记住的是，一个哈希是由计算机生成的，随机数从零开始，这个区块被矿工哈希了28亿次才找到一个小于目标的数字。
### Erc-20
---
# Ethereum
> [!TIP] 链上完成图灵完备性的计算
![Ethereum Roadmap](Pasted%20image%2020230604092200.png)

## ETH Consensus Layer 共识层

- Eth1: Proof of Work
	- use GPU to solve keccak256 hash function (no ASIC available)
	- annual inflation：>3%
	- transition：“The Merge“
-  Eth2: Proof of Stake
	- 32 ETH staking validator
	- annual inflation：~0%
	- saves 99.5% energy
## ETH Execution Layer 执行层
![](Pasted%20image%2020230604093654.png)

## Ethereum Virtual Machine
**1. State data**
- Types of account EOA (externally owned account)
	- ie. "wallet
	- private key -> public key
- Smart contract
	- stores code
	- exectutable
**2. State transition**
- State transition is triggered by transaction
- Tx types
	- EOA -> EOA: ETH transfer
	- EOA -> Contract: call function
	- Contract -> Contract: internal call (no signature) 
**3. 编程逻辑 Computing Logic**
- Program languages
	- Solidity (C/C++ inspired)
	- Vyper (Python-like, used by Curve)
	- Yul (Assembly - 1:1 mapping with bytecode)
- Example Solidity contract: https://docs.openzeppelin.com/contracts/4.x/erc20











---
# Reference
- Stanford CS251

---
BackLink： [[content/1-Crypto/0. Crypto Index|0. Crypto Index]]