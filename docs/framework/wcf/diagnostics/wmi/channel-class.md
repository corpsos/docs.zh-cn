---
title: Channel 类
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 108d5f8e3cd092863dbd48e2bb9d180798b091a4
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197868"
---
# <a name="channel-class"></a>Channel 类
通道  
  
## <a name="syntax"></a>语法  
  
```csharp
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a>方法  
 Channel 类未定义任何方法。  
  
## <a name="properties"></a>属性  
 Channel 类具有以下属性。  
  
### <a name="localaddress"></a>LocalAddress  
 数据类型：String  
  
 访问类型：只读  
  
 通道的本地终结点。  
  
### <a name="ref"></a>ref  
 数据类型：Endpoint  
  
 访问类型：只读  
  
 对通道所连接到的终结点的引用。  
  
### <a name="remoteaddress"></a>RemoteAddress  
 数据类型：String  
  
 访问类型：只读  
  
 与通道相关联的远程地址。  
  
### <a name="sessionid"></a>SessionId  
 数据类型：String  
  
 访问类型：只读  
  
 当前会话的 ID（如果有）。  
  
### <a name="type"></a>类型  
 数据类型：String  
  
 访问类型：只读  
  
 通道的类型。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Channels.ChannelBase>
