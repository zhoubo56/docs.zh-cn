---
title: '&lt;endpointBehaviors&gt; 的 &lt;behavior&gt;'
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: e275fbc1b14469553094a4df838930be53937de2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33363294"
---
# <a name="ltbehaviorgt-of-ltendpointbehaviorsgt"></a>&lt;endpointBehaviors&gt; 的 &lt;behavior&gt;
`behavior` 元素包含终结点行为的设置集合。 每个行为都按其 `name` 进行索引。 终结点可以通过此名称链接到每个行为。 从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。 有关默认配置和无名称的绑定和行为的详细信息，请参阅[简化配置](../../../../../docs/framework/wcf/simplified-configuration.md)和[简化配置 WCF 服务](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。  
  
 \<system.ServiceModel>  
\<行为 >  
\<endpointBehaviors>  
\<行为 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <endpointBehaviors>  
       <behavior name="String" />  
    </endpointBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|name|一个包含行为的配置名称的唯一字符串。 此值是用户定义的一个字符串，该字符串必须是唯一的，因为它将充当元素的标识字符串。 从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。 有关默认配置和无名称的绑定和行为的详细信息，请参阅[简化配置](../../../../../docs/framework/wcf/simplified-configuration.md)和[简化配置 WCF 服务](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|指定用于向服务验证客户端身份的凭据。|  
|[\<callbackDebug >](../../../../../docs/framework/configure-apps/file-schema/wcf/callbackdebug.md)|指定服务调试 Windows Communication Foundation (WCF) 回调对象。|  
|[\<callbackTimeouts >](../../../../../docs/framework/configure-apps/file-schema/wcf/callbacktimeouts.md)|指定客户端回调的超时。|  
|[\<clientVia >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientvia.md)|指定消息应采用的路由。|  
|[\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer.md)|包含 DataContractSerializer 的配置数据。|  
|[\<dispatcherSynchronization >](../../../../../docs/framework/configure-apps/file-schema/wcf/dispatchersynchronization.md)|指定允许服务进行异步答复的终结点行为。|  
|[\<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)|启用终结点行为，此行为使得可以使用 ASP.NET AJAX 网页中的服务。 此行为只应该使用结合使用\<webHttpBinding > 标准绑定，或\<webMessageEncoding > 绑定元素。|  
|[\<endpointDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|指定终结点的各种发现设置，例如终结点的可发现性、范围以及对终结点元数据的任何自定义扩展。|  
|[\<soapProcessing >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md)|定义用于封送不同绑定类型和消息版本之间消息的客户端终结点行为。|  
|[\<v e >](../../../../../docs/framework/configure-apps/file-schema/wcf/synchronousreceive-element.md)|指定服务或客户端应用程序中用于接收消息的运行时行为。 它不具有任何属性或子元素。|  
|[\<transactedBatching >](../../../../../docs/framework/configure-apps/file-schema/wcf/transactedbatching.md)|指定接收操作是否支持事务批处理。|  
|[\<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)|通过配置指定终结点上的 WebHttpBehavior。 此行为与结合使用时， \<webHttpBinding > 标准绑定，启用 Web 编程模型的 WCF 服务。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<endpointBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|终结点行为元素的集合。|
