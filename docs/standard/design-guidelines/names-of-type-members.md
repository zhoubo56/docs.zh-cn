---
title: 类型成员的名称
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], names
- methods [.NET Framework], names
- type members
- properties [.NET Framework], names
- fields, names
- field names
- names [.NET Framework], type members
- members [.NET Framework], type
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25fe93b63c518f54ee72300f26dfcb3f3ad21d76
ms.sourcegitcommit: b6baf91310f6867223f0f32d596b451592b917b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2018
ms.locfileid: "33575344"
---
# <a name="names-of-type-members"></a>类型成员的名称
类型由以下成员构成：方法、属性、事件、构造函数和字段。 以下各节介绍命名类型成员的准则。  
  
## <a name="names-of-methods"></a>方法的名称  
 方法是执行操作的方式，设计准则要求方法名称为谓词或谓词短语。 遵循此准则，还有利于区分方法名称与属性和类型名称，后者为名词或形容词性短语。  
  
 **✓ DO** 用谓词或谓词短语为方法命名。  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a>属性的名称  
 与其他成员不同，应向属性给定名词性短语或形容词性名称。 这是因为属性是指数据，属性的名称应反映这一点。 属性名称总是采用帕斯卡大小写。  
  
 **✓ DO** 使用名词、名词性短语或形容词为属性命名。  
  
 **X DO NOT** 拥有与“Get”方法同名的属性，如以下示例所示：  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 此模式通常意味着该属性事实上是一种方法。  
  
 **✓ DO** 用描述集合中项目的复数短语（而不是使用单数短语后接“List”或“Collection”）为集合属性命名。  
  
 **✓ DO** 用肯定性短语（`CanSeek` 而非 `CantSeek`）为布尔属性命名。 还可选择为布尔属性添加“Is”、“Can”或“Has”，但仅在可带来益处时这么做。  
  
 **✓ CONSIDER** 为属性提供与其类型相同的名称。  
  
 例如，以下属性可正确获取和设置名为 `Color` 的枚举值，因此属性名为 `Color`：  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a>事件的名称  
 事件始终指操作，可以是即将发生的，也可以是已经发生的。 因此，对于方法，事件用谓词命名，并用谓词时态指示引发事件的时间。  
  
 **✓ DO** 用谓词或谓词短语为事件命名。  
  
 示例包括`Clicked`、`Painting` 和 `DroppedDown`。  
  
 **✓ DO** 使用现在时和过去时，为事件名称赋予之前和之后的概念。  
  
 例如，窗口关闭之前引发的事件称为 `Closing`，窗口关闭之后引发的事件称为 `Closed`。  
  
 **X DO NOT** 使用 “Before” 或 “After” 前缀和后缀来指示事件之前或之后。 应按前述使用现在时态和过去时态。  
  
 **✓ DO** 使用 “EventHandler” 后缀来命名事件处理程序（委托，用作事件类型），如以下示例所示：  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 **✓ DO** 在事件处理程序中使用名为 `sender` 和 `e` 的两个参数。  
  
 sender 参数表示引发事件的对象。 sender 参数的类型通常是 `object`，即使可以使用更具体的类型。  
  
 **✓ DO** 为事件参数类名称添加“EventArgs”后缀。  
  
## <a name="names-of-fields"></a>字段的名称  
 字段命名准则适用于静态公开字段和受保护的字段。 原则不涉及内部和专用字段，而[成员设计准则](../../../docs/standard/design-guidelines/member.md)不允许使用公开字段或受保护的实例字段。  
  
 **✓ DO** 在字段名称中使用 PascalCasing。  
  
 **✓ DO** 使用名词、名词短语或形容词来命名字段。  
  
 **X DO NOT** 在字段名称中使用前缀。  
  
 例如，不要使用 "g_" 或 "s_" 来指示静态字段。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。* 保留所有权利。  
  
 由 Pearson Education, Inc 许可，转载自 [Framework 设计准则：可重用 .NET 库的约定、惯用法和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日作为 Microsoft Windows 开发系列的一部分发布。  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
