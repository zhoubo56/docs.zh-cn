---
title: 在微服务中应用简化的 CQRS 和 DDD 模式
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 在微服务中应用简化的 CQRS 和 DDD 模式
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 5557a3d83d1f5f3016ff411157db1652d3ac50e2
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106079"
---
# <a name="applying-simplified-cqrs-and-ddd-patterns-in-a-microservice"></a>在微服务中应用简化的 CQRS 和 DDD 模式

CQRS 是一种分离数据读取与写入模型的体系结构模式。 相关术语[命令查询分离 (CQS)](https://martinfowler.com/bliki/CommandQuerySeparation.html)最初由 Bertrand Meyer 在其《面向对象软件构造》一书中定义。 基本思想是可以将系统操作划分为两个界限明显的类别：

-   查询。 这些查询返回结果，不改变系统的状态，且没有副作用。

-   命令。 这些命令会更改系统状态。

CQS 是一个简单的概念 - 说明同一对象中的方法是查询还是命令。 每种方法要么返回状态，要么更改状态，不会二者兼具。 即使是单个存储库模式对象也符合 CQS。 CQS 被视为 CQRS 的基本原则。

[命令和查询职责分离 (CQRS)](https://martinfowler.com/bliki/CQRS.html) 由 Greg Young 提出并由 Udi Dahan 等人大力推广。 它基于 CQS 原则，只是更为详细。 它可以视为基于命令和事件的模式，另外在异步消息方面可选。 在很多情况下，CQRS 涉及到更高级的方案，比如另外构建一个用于读取（查询）而非写入（更新）的物理数据库。 此外，更先进的 CQRS 系统会为更新数据库实现[事件源 (ES)](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)，因此只能将事件存储在域模型中，而不能存储当前状态数据。 但是，这不是本指南中使用的方法；我们正使用最简单的 CQRS 方法，只是将查询从命令中分离出来。

CQRS 的分离操作通过将查询操作分到一层中而将命令分到另一层中来实现。 每一层都有自己的数据模型（注意，我们说的是模型，不一定是其他数据库），并且使用自己的模式和技术组合来构建。 更重要的是，这两层可以共处于同一层级或同一个微服务中，如本指南中使用的示例（订购微服务）。 也可以在不同的微服务或进程上实现，以便彼此毫不影响地分别进行优化和横向扩展。

CQRS 表示有两个对象用于读/写操作，而在其他上下文中有一个对象。 可以添加一个非规范化读取数据库，如要了解这些数据库，请参阅更高级的 CQRS 文献。 但是我们在这里没有使用这种方法，因为在此处，我们的目标是更灵活地查询，而不是使用 DDD 模式的约束（如聚合）限制查询。

这种服务的一个例子就是 eShopOnContainers 引用应用程序的订购微服务。 该服务基于简化的 CQRS 方法实现微服务。 使用单个数据源或数据库、两个逻辑模型和事务域的 DDD 模式，如图 9-2 所示。

![](./media/image2.png)

**图 9-2**。 基于简化 CQRS 和 DDD 的微服务

应用程序层可以是 Web API 本身。 此处的重要设计是微服务已经从 CQRS 模式之后的命令、域模型和事务中将查询和 ViewModel（特别为客户端应用程序创建的数据模型）拆分开了。 这种方法使查询独立于 DDD 模式的限制和约束，这些模式只对事务和更新有意义，如后面的章节所述。


>[!div class="step-by-step"]
[上一页](index.md)
[下一页](eshoponcontainers-cqrs-ddd-microservice.md)
