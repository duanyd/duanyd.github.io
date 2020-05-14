---
title: Banking Journey I Know (Foreign currency exchange)
commentable: flase
Edit: 2020-05-08
mathjax: true
mermaid: true
tags: Bank Business Foreign Exchange
categories: paper computer original
description: Settlement and sale of foreign exchange is a general term for the settlement and sale of foreign exchange... [link](https://blog.csdn.net/weixin_37586375/article/details/103755165).
---
> 愿你历尽千帆，不染岁月风尘；愿你最终得到的，即是当初喜欢的…
  
首先要说明一下，我对结售汇的了解不是很多，做结售汇业务也是一些简单的，国内做的最好的外币业务的要属中国银行了，所以本篇只是对结售汇做一些基础的介绍。
结售汇是结汇与售汇的统称。银行结售汇是指银行为客户及其自身办理的结汇和售汇业务，包括远期结售汇履约和期权行权数据，不包括银行间外汇市场交易数据。银行结售汇统计时点为人民币与外汇兑换行为发生时。
结汇即“外汇结算”，是指外汇收入所有者将其外汇收入出售给外汇指定银行，外汇指定银行按一定汇率付给等值的本币的行为。
售汇即“外汇出售”，是指外汇指定银行将外汇卖给外汇使用者，并根据交易行为发生之日的人民币汇率收取等值人民币的行为。

**汇率维护：**维护相应币种的中间价、汇率信息

**代客结汇：**简单的说就是买入人民币，卖出外币；即外币兑换成人民币

**代客售汇：**就是买入外币，卖出人民币；即人民币兑换成外币

**平盘：**
指银行在办理代客结售汇业务或自身结售汇业务后，通过外汇交易市场将外汇结汇头寸卖出或买入外汇头寸，用于补充售汇头寸的交易。
客户向银行进行结售汇，不能称作“平盘”，只有银行收集个人客户外汇一定数量后，向国际外汇市场转嫁风险时的过程，才叫“平盘”。
例如，开盘价与昨日收盘价相同则称开平盘;当日收盘价等于前一日收盘价则称为收平盘。平盘目前由于很多银行采用总分支体制,银行系统内在国际外汇市场只有有限的几个席位,所以平盘一般分为系统内平盘和系统外平盘。

**系统内平盘：**指的交易行将买卖产生的头寸(多头或者空头)向上级行轧平头寸；交易对手是总行<——>交易行

**系统外平盘：**指的是将交易行向上级行划转的头寸向国内外外汇交易市场买卖外汇的业务；交易对手是总行<——>国外同业

**月末平盘：**月末时，系统自动将未平盘的系统外平盘账户进行平盘，首先使用折算价计算损益：

> 汇兑损益=外币金额折算汇率/100-外币金额成本价/100

记账：

> 盈利：借：系统外平盘 人民币
> 贷：汇兑损益 人民币
> 损失：贷：系统外平盘 人民币
> 借：汇兑损益 人民币

最后附上思维导图：github地址为[link](https://github.com/duanyd/XmindOfBankBusiness)
<img src="https://img-blog.csdnimg.cn/20191229174940993.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzU4NjM3NQ==,size_16,color_FFFFFF,t_70" width="100%">
  
