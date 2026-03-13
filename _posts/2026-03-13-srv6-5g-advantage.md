---
title: SRv6技术的优势及在5G-Advanced核心网的应用
date: 2026-03-13
categories:
  - SRv6
  - 5G
tags:
  - SRv6
  - Segment Routing
  - 5G-Advanced
  - 网络切片
  - SFC
  - DetNet
source: ZTE 技术杂志
source_url: https://www.zte.com.cn/china/about/magazine/zte-technologies/2021/11-cn/4/6.html
---

# SRv6技术的优势及在5G-Advanced核心网的应用

> 来源：[ZTE 技术杂志](https://www.zte.com.cn)

## 概述

SRv6（Segment Routing over IPv6，基于IPv6的段路由）是基于源路由理念设计，在IPv6网络转发数据分组的一种技术，是当下最热门的Segment Routing和IPv6两种网络技术的结合体。

SRv6的Native IPv6属性保证了网络任意节点的可达性，而其强大的网络可编程能力能更好地满足网络业务的SLA需求，使其成为IPv6时代最有前景的网络技术。

## SRv6技术的三大优势

### 1. 简化网络协议

- 通过扩展IGP/BGP，去掉LDP和RSVP-TE等MPLS隧道技术，简化控制面
- 数据面直接使用IPv6地址作为转发标签，去除了MPLS标签
- 控制面和数据面都实现统一承载，极大地简化了网络协议

### 2. Native IP属性

- 通过IPv6扩展报文头实现，没有改变IPv6报文封装结构，保持兼容性
- 依赖IPv6可达性可实现任意IPv6节点之间的互通，跨域部署更简单
- 普通中间节点仅支持IPv6转发即可，无需特殊转发逻辑
- 可以打破运营商网络和数据中心网络之间的界限

### 3. 网络可编程能力

SRv6的网络可编程能力体现在SRH（Segment Routing Header）扩展头中，SRH中有三层编程空间：

#### a) Segment List
- 将多个Segment有序组合进行路径编程
- 根据业务意图、网络状态等智能选择最佳路径并实时调整

#### b) SRv6 SID
- 128位IPv6地址形式，标准格式为"Locator:Function:Args"
- 可以灵活分为多段，每段长度可以变化，具备灵活编程能力
- Locator表示到达该节点的路由信息
- Function和Args分别表示在该节点执行的具体功能和所需的参数
- 既能表示路由，又能表示接口、设备、业务和应用

#### c) Optional TLV
- 用于进一步自定义功能
- 支持SFC（业务功能链）、OAM、DetNet（确定性网络）、VPN、APN6等高级特性

## SRv6在5G-Advanced核心网的应用

### 1. 网络切片

- 采用SID中的Locator作为虚网切片的唯一标识
- 根据SRv6 SID识别报文所属的虚拟网络
- 使用虚网切片定义的拓扑和资源进行转发处理
- 为不同网络切片业务提供差异化转发路径和相互隔离的网络资源

### 2. 服务功能链（SFC）

- 将SF相关的SID插入SRv6报文头的SID List中
- 利用SRv6的流量工程能力整合Overlay、Underlay和服务链
- 对SF设备要求更低（支持IPv6转发或L2透传即可）
- 可以部署在任何支持IPv6的网络上

### 3. 确定性网络（DetNet）

- 数据封装在SRv6报文头中
- 显式路径被编码在SR Policy的SRH中
- 提供稳定的转发服务，保证网络拓扑变化时不受影响
- 支持服务保护（包复制、消除和排序）和拥塞控制
- 提供有界时延、低抖动、零分组丢失的确定性网络服务

### 4. APN6（基于IPv6的应用感知网络）

- 将应用信息携带在SRv6报文中传递进入网络
- 使网络感知应用及其SLA需求
- 根据报文中的应用信息匹配网络对应策略
- 进行流量调度和资源调整
- 实现网络能力与业务需求的无缝结合

## 总结

SRv6作为未来网络的基础性技术，正处在高速发展阶段。2020年中兴通讯支撑中国电信实现了全球最大SRv6商用网络。随着5G、IoT、云业务的快速发展，SRv6技术必将发挥更加重要的作用。以SRv6技术为代表的IPv6+技术正引领未来网络从万物互联到万物"智"联的变革。