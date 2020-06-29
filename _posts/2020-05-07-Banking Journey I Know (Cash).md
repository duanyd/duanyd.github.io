---
title: Banking Journey I Know (Cash)
commentable: flase
Edit: 2020-05-07
mathjax: true
mermaid: true
tags: Bank Business Cash Fund Pool Management
categories: paper computer original
description: The fund pool is also known as cash management. It is a group fund management system that banks are introducing to large enterprises. Fund account tree to achieve the purpose of efficient utilization and centralized management of corporate funds... [link](https://blog.csdn.net/weixin_37586375/article/details/103752162).
---
> 物来顺应，未来不迎，当时不杂，既过不恋 —— 曾国藩
  
资金池也称为现金管理，是银行正对大企业推出的一项集团资金管理的系统，将上下级树形账户树，按一定规则进行资金归集、请款，通过这颗智能轮动的资金账户树，以达到企业资金高效利用、集中管理的目的。现金池业务主要包括的事项有成员单位账户余额上划、成员企业日间透支、主动拨付与收款、成员企业之间委托借贷以及成员企业向集团总部的上存、下借分别计息等。不同的银行对现金池有具体不同的表述。
以下是某企业资金账户的示意图：
<img src="https://img-blog.csdnimg.cn/20191229114234722.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzU4NjM3NQ==,size_16,color_FFFFFF,t_70" width="100%">

注意大部分银行收入账户和支出账户是同一个，没有区分做收支两条线

**虚拟子账号：**
是一个特殊的存款账户，这个账户不计息、不计提，是签约了资金池协议。

**协议：**
包括资金池产品协议包括归集协议、请款协议，规定了资金池产品的协议规则。

**资金池产品参数维护：**
维护资金池的产品代码、名称、种类、币种、最大层级、状态、生效失效日期等信息

**资金池签约：**
一个存款账户签约资金池后，会设置与资金池相关的规则、生成一个虚拟子账号等，签约时设置如下规则：账户层级、上级账户、主账户、虚拟头寸记账账号、请款顺序、委贷方式、计息方式、请款使用主账户法透标志、主动划拨标志、多边调拨标志、请款限额规则、上存定额浮动额、日（周、月、旬、年）限额、签约日期等基本信息

**资金池归集协议：**
设置了按什么规则进行资金归集，设置以下属性：实时归集类型（归集 、不归集、止付归集）、实时归集发生额条件、定时归集例外清单、定时归集（定时、自动、定时+自动）、定时归集方式（固定归集金额、固定留存金额、按比例归集、全额归集）、定时归集最小发生额条件、定时归集定额金额、定时归集留存余额、定时归集比例等信息

**资金池请款协议：**
设置了按什么规则像上级请款，设置以下属性：实时请款类型（请款、不请款、日间透支）、实时请款方式（差额、全额）、实时请款定额金额（请款时取发生额和定额的较大值）、实时请款最低余额（请款后余额必须达到的最低值）、实时请款例外清单、定时请款标志（批量请款 、不请款、自助请款）、定时请款方式(定额、差额、原额）、定时请款定额金额、定时请款最低余额等信息<br/>
注意：整个资金池签约的过程就是构建资金池账户树的过程

**实时请款：**
如下图，如果E要付一笔款，但是没有钱，它签约了资金池，就会向父账户A请款，A同样没钱，再向父账户（主账户）请款，主账户一般有钱，就会先把钱转给A,A再转给E，这就是一次实时请款。
<img src="https://img-blog.csdnimg.cn/20191229160446383.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzU4NjM3NQ==,size_16,color_FFFFFF,t_70" width="100%">

**实时归集：**
归集是从下往上归的，子账户按一定规则，一旦满足归集条件就会实时归集，如下图E归集到A，A再归集到主账户；同样F、G归集到B，B再归集到主账户
<img src="https://img-blog.csdnimg.cn/20191229160933808.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzU4NjM3NQ==,size_16,color_FFFFFF,t_70" width="100%">

**注意：**归集和请款是资金池的两大核心功能，可以分为实时、定时、批量等类型

**主动划拨：**资金池树中的上下级账户之间的转账就叫主动划拨。包括自助下拨、自助上划

**资金池调拨：**是指资金池树中的兄弟账户之间的转账。

**资金池批量：**
资金池有一大块功能是通过批量完成的，这部分对于客户是不知道的，在日终的时候银行系统会跑资金池的批量，有如下处理：

**1：资金池止付归集解冻：**将签约了支付归集的活期账户的金额归集到上级账户；增加虚拟头寸户余额。

**2：资金池日间透支还款：**将签约了日间透支的账户，通过向上级账户请款到本账户，用以偿还日间透支金额；减少虚拟头寸户余额。

**3：日末批量归集：**将签约资金池的所有账户，按账户层级从大到小按签约规则进行归集。

**4：请款周期限额到期处理：**对已到期的限额记录进行处理，新增下一个周期的限额记录。

**5：资金池内部利息计算：**对签约了计息的资金池账户进行利息计算，根据虚拟头寸余额历史和利率历史计算存款和借款利息，登记存款利息历史记录和借款利息历史记录

**6：内部结息：**对签约了计息的资金池账户进行结息处理，用虚拟头寸账户调用存款虚拟头寸结息组件，计算头寸账户存款利息和借款利息，根据存款借款利息差额来增加或减少虚拟头寸户余额。

最后附上思维导图：github地址为[link](https://github.com/duanyd/XmindOfBankBusiness)
<img src="https://img-blog.csdnimg.cn/20191229164125326.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzU4NjM3NQ==,size_16,color_FFFFFF,t_70" width="100%">
  
