---
title: CorSymAddrKind 枚举
ms.date: 03/30/2017
api_name:
- CorSymAddrKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymAddrKind
helpviewer_keywords:
- CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98cf49714829b4b2f80e0240c2ebde7fa6c280e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425400"
---
# <a name="corsymaddrkind-enumeration"></a>CorSymAddrKind 枚举
指示内存地址的类型。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|指示的 Microsoft 中间语言 (MSIL) 本地变量或参数索引。|  
|`ADDR_NATIVE_RVA`|指示模块中的相对虚拟地址。|  
|`ADDR_NATIVE_REGISTER`|指示 CPU 寄存器。|  
|`ADDR_NATIVE_REGREL`|表示第一个地址是寄存器，第二个地址是的偏移量。|  
|`ADDR_NATIVE_OFFSET`|指示基址中的偏移量。|  
|`ADDR_NATIVE_REGREG`|指示第一个地址是一个寄存器中，低部分和第二个地址是高的部分。|  
|`ADDR_NATIVE_REGSTK`|指示第一个地址是寄存器的低部分、 第二个是高的部分中，第三个是的偏移量。|  
|`ADDR_NATIVE_STKREG`|指示第一个地址是寄存器，第二个是的偏移量，并且第三个是寄存器的高部分。|  
|`ADDR_BITFIELD`|表示的第一个地址是字段的开始，第二个地址是字段长度。|  
|`ADDR_NATIVE_ISECTOFFSET`|指示第一个地址是部分和第二个地址是的偏移量。|  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>请参阅  
 [诊断符号存储区枚举](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
