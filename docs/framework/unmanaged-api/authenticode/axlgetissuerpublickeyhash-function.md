---
title: _AxlGetIssuerPublicKeyHash 函数
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 408b71bf38427d12418e05f8b509fe841bc95ef1
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "42754462"
---
# <a name="axlgetissuerpublickeyhash-function"></a>_AxlGetIssuerPublicKeyHash 函数
检索与用于对指定证书进行签名的私钥关联的公钥的 SHA-1 哈希。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pChainContext`  
 [in] CSP 公钥 Blob。 请参阅[CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob)结构。  
  
 `ppwszPublicKeyHash`  
 [out] 指向 WCHAR * 的指针，用于接收十六进制编码的公钥标记。  
  
## <a name="return-value"></a>返回值  
 如果函数成功，则为 `S_OK`；否则为 `S_FALSE`。  
  
## <a name="see-also"></a>请参阅  
 [验证码](../../../../docs/framework/unmanaged-api/authenticode/index.md)
