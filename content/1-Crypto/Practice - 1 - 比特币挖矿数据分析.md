---
title: Practice - 1 - 比特币挖矿数据分析
tags:
  - Crypto
  - Financial
  - Transaction
---
# 1. 概念部分
## 1.1 矿业分析所涉及的概念
- 矿机：
	- 矿机算力：[[content/1-Crypto/Practice - 1 - 比特币挖矿数据分析#1.3. 算力基本单位|算力基本单位]]
	- 矿机功率：[[content/1-Crypto/Practice - 1 - 比特币挖矿数据分析#1.4. 矿机能效比|矿机能效比-功率]]
	- 能效比：[[content/1-Crypto/Practice - 1 - 比特币挖矿数据分析#1.4. 矿机能效比|矿机能效比]]
	- 电费：[[content/1-Crypto/Practice - 1 - 比特币挖矿数据分析#1.5. 电费|电费]]
- BTC 网络：
	- 挖矿难度： [[content/1-Crypto/Practice - 1 - 比特币挖矿数据分析#1.6. 挖矿难度与全网算力|挖矿难度与全网算力]]
	- 全网算力：[[content/1-Crypto/Practice - 1 - 比特币挖矿数据分析#1.6. 挖矿难度与全网算力|挖矿难度与全网算力]]
	- Known Pools Hashrate：[[content/1-Crypto/Practice - 1 - 比特币挖矿数据分析#1.6. 挖矿难度与全网算力|挖矿难度与全网算力]]
	- Network Hashrate：[[content/1-Crypto/Practice - 1 - 比特币挖矿数据分析#1.6. 挖矿难度与全网算力|挖矿难度与全网算力]]
	- 电费占比：[[#2.1. 手动核算挖矿成本]]
	- 平均挖矿成本/关机币价：[[#2.2. 矿机回本周期的计算]]
	- 经验分析和逻辑推理：[[#3. BTC 投资分析]]
## 1.2. 挖矿设备示例
- 矿机设备的重点单位包含三个： T、W、J/T
## 1.3. 算力基本单位
>[! Tip]
> 在实际分析中，往往采用缩写如 100 T，就是 100 THash/s，如 460 E，就是 460 EHash/s。在行业表述中，算力常常叫做 Hashrate
> - KH/s：1 KH/s=1000 H/s
> - MH/s：1 MH/s=1000 KH/s
> - GH/s：1 GH/s =1000 MH/s
> - TH/s：1 TH/s =1000 GH/s
> - PH/s：1 PH/s =1000 TH/s
> - EH/s：1 EH/s =1000 PH/s
## 1.4. 矿机能效比
$$
能效比 = 功耗/算力
$$
>[!eXAMPLE] 
>	设 S 19 系列矿机参数如下：110 T 算力，功耗 3.3 kw
>	- 则其能效比为：3.3 kw/110 T = 30 J/T
>**30 J/T 表达每 Thash 的算力在 1 s 内消耗的的能量，直接表达效率**
>能效比越小、矿机性能越高。能效比也是最重要的矿机参数
## 1.5. 电费
>[!tip] 很难知道全球平均电费价格，根据经验以及行业信息获取
>1 度电=1 kwh=1 kw 的机器运行一小时=3,600,000J
>3kw的矿机运行1小时，花费是3度电。
## 1.6. 挖矿难度与全网算力
>[!tip]
>- BTC 网络理论上是 10 min 一个区块；
>- BTC 挖矿难度每隔 2016 个区块调整一次，约 2 周时间；
>- 根据挖矿难度和出块时间可以反推出全网理论算力；
>- 全网实际算力是由统计各个矿池的算力数据求和而来。
- 全网实际算力：Knows Pools Hashrate
$$
\begin{gather}
D*2^{32}time=Network\ Hashrate\ \\time: 出块时间\\D: Difficulty\ 挖矿难度
\end{gather}
$$
- 全网理论算力：Network Hashrate
>[!eXAMPLE] 如果实际算力高于理论算力，那么，在这个 2016 区块的周期内，将会发生: 出块时缩短。即，挖矿难度调整时间比 2 周时间短
> $$If\ time=10\ min=60\ s, Difficulty\ = 52.35\ Thash$$
> $$52.35*2^{32} /1000000/600=Network\ Hashrate=374.735\ Ehash$$
- 当两者数值不一致的时候，将影响出块速度与矿池盈利，不影响挖矿成本分析
# 2 . 挖矿成本分析
## 2.1. 手动核算挖矿成本
>[!eXAMPLE] 限定一天时间, 求能挖出多少 BTC
>- 基本参数
> 	 - 矿机：算力 110 T，功耗 33 kw
> 	 - 电费：0.45￥/度电
> 	 - KnownPools Hashrate：450E
>  - BTC：
> 	 - 区块奖励：6.25 btc/block
> 	 - 出块时间：10 min
> 	 - 每天全网挖出来：900BTC
$$
\begin{gather}
单台矿机算力占全网算力的比例=单台矿机占全网出币量的比例\\
BTC价值=BTC数量*价格\\
关机币价（成本价）推算，按照：电费=挖出btc价值\\
\end{gather}
$$
$$
\begin{gather}
3kw*24h*0.45￥=100T/450E*900BTC*关机币价\\
\text{关机币价}=3kw*24h*0.45￥/(100T/450E*900BTC)\\
\end{gather}
$$
## 2.2. 矿机回本周期的计算
![[content/notes/images/1704076418648.png]]
>[!eXAMPLE] 假如 BTC 当前价格为27000USD，全网算力、电费等基本参数不变
每天产生利润：
$$0.000204545*（27000-21522）=1.12 USD $$
$$回本周期（天）=设备价格÷每日利润 $$
假如购买价格是 $$1000美金，1000÷1.12=892.86天 大约为29个月，即2.44年$$
- 估算部分
	- 全球矿机的能效比: 30J/T
	- 全球挖矿平均电费: 0.45￥/度
- 确定部分
	- 全网的实际算力 Known Pools Hashrate
	- 区块奖励: 6.25BTC/Block
	- 每天挖矿 BTC 数量: 900btc
	- 出块基本时间: 10min
	- 每天的时间: 24h
	- 汇率: 7.36CNY/USD
- 忽略部分
	- 网络费用
确定部分、估算部分、忽略部分，三者都可能随着时间推移而发生重大变化
**例如**：*区块奖励2024年4月，发生减半*；*汇率也是6.3-7.4之间波动*；*算力的波动*更是每天在发生。区分三个部分的参数，会让我们在矿业数据核算中知道数据的来源与变化的依据
# 3. BTC 投资分析
## 3.1. BTC 长牛市场分析
>[!tip] 通过指数性数据证明 BTC 处在长牛之中或 BTC 长期牛市的可能终结
>- **当前 BTC 呈现的风险：**
>	- BTC 价格波动剧烈，一个季度甚至一个月波动 30%+
>	- 大量投资者进入加密领域亏损严重
>	- BTC 崩盘新闻时有发生
>	- 无法与实体经济结合
>	- 监管问题一直存在，无法得到妥善解决 BTC 经常会被利用，涉及到一些违规行为
- 按照矿业数据，如果 KnownPools Hashrate 在 1-2 个季度出现连续下跌，而不继续上涨，那么，BTC 的长牛行情就可能终结
## 3.2. BTC关机币价对投资的参考性
- 思考:
	- 一个商品的价格是由供需决定的
	- 供需是难以把握的
	- 从全球来看，BTC 关机币价在短期内是由全网算力决定的全网算力为什么增加? 1、预期; 2、资金进入的方式。
- 结论:
	- BTC 矿业是制造业: 制造业滞后市场，需要预判市场，请深刻理解这句话: 经验和逻辑: BTC 挖矿成本价与当前币价关系是经验总结，不是逻辑推理
	- 当前币价: 不代表不会跌破关机币价;
	- 全网算力: 每天都在波动，周期拉长，趋势一直向上;
	- 矿工费: BTC 生态如果能起来，参数的忽略部分 (网络费用 or 矿工费) 就需要纳入核算; 减半前后: 根据经验，全网算力会在减半前后，降低 20-30%+，而后继续增长。
## 3.3. Hash Ribbons 介绍与应用
- **Hash Ribbons：** 这是一个粗糙、不能单一使用的指标，但是对我们有一定的启发性
	- 比特币矿工投降：30 DMA 跌破 60 DMA，表明算力下降。这由深粉色垂直线表示。
	- 矿工投降结束：30 日线重回 60 日线上方。这由浅粉色垂直线表示。
	- 比特币买入信号：30日均线回到60日均线之上，与比特币价格上涨同时发生
![[content/notes/images/Pasted image 20240101104503.png]]
此指标包含三个内容，但**其实真正有参考性的是前两个，尤其是第一个**，30 日算力下穿 60 日算力时候，矿工在投降，这里其实已经开始需要关注。
- 长期布局：长期来看一定会在一定时间后上穿回去。即，时间区间定投参考，红色区域。
- 短期布局波段：其买入点也有一定参考性。


---
BackLink： [[content/1-Crypto/0. Crypto Index|0. Crypto Index]]