---
title: "IMetaDataValidate 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataValidate
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataValidate
helpviewer_keywords: IMetaDataValidate interface [.NET Framework metadata]
ms.assetid: db98608a-e85c-4f50-9d7b-5f57a426ddb6
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a30de0ca9554d93e000a07af80b34bcd10814dfb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imetadatavalidate-interface"></a><span data-ttu-id="5e64e-102">IMetaDataValidate 接口</span><span class="sxs-lookup"><span data-stu-id="5e64e-102">IMetaDataValidate Interface</span></span>
<span data-ttu-id="5e64e-103">提供验证元数据签名的方法。</span><span class="sxs-lookup"><span data-stu-id="5e64e-103">Provides methods to validate metadata signatures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5e64e-104">方法</span><span class="sxs-lookup"><span data-stu-id="5e64e-104">Methods</span></span>  
  
|<span data-ttu-id="5e64e-105">方法</span><span class="sxs-lookup"><span data-stu-id="5e64e-105">Method</span></span>|<span data-ttu-id="5e64e-106">描述</span><span class="sxs-lookup"><span data-stu-id="5e64e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5e64e-107">ValidateMetaData 方法</span><span class="sxs-lookup"><span data-stu-id="5e64e-107">ValidateMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-validatemetadata-method.md)|<span data-ttu-id="5e64e-108">验证在当前元数据范围内的对象的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="5e64e-108">Validates the metadata signatures of the objects in the current metadata scope.</span></span>|  
|[<span data-ttu-id="5e64e-109">ValidatorInit 方法</span><span class="sxs-lookup"><span data-stu-id="5e64e-109">ValidatorInit Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-validatorinit-method.md)|<span data-ttu-id="5e64e-110">设置一个标志，该标志指定当前元数据范围内的模块类型，并注册验证错误的指定回调方法。</span><span class="sxs-lookup"><span data-stu-id="5e64e-110">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5e64e-111">要求</span><span class="sxs-lookup"><span data-stu-id="5e64e-111">Requirements</span></span>  
 <span data-ttu-id="5e64e-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5e64e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e64e-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5e64e-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5e64e-114">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5e64e-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5e64e-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e64e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e64e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e64e-116">See Also</span></span>  
 [<span data-ttu-id="5e64e-117">元数据接口</span><span class="sxs-lookup"><span data-stu-id="5e64e-117">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)