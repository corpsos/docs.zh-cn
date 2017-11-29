---
title: "ICorProfilerFunctionControl::SetCodegenFlags 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionControl.SetCodegenFlags
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: eb212b0fb777e960d7121dadaf4715b44306db6a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a><span data-ttu-id="9638e-102">ICorProfilerFunctionControl::SetCodegenFlags 方法</span><span class="sxs-lookup"><span data-stu-id="9638e-102">ICorProfilerFunctionControl::SetCodegenFlags Method</span></span>
<span data-ttu-id="9638e-103">设置从一个或多个标志[COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)枚举控制代码生成中实时 (JIT) 重新编译函数。</span><span class="sxs-lookup"><span data-stu-id="9638e-103">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9638e-104">语法</span><span class="sxs-lookup"><span data-stu-id="9638e-104">Syntax</span></span>  
  
```  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9638e-105">参数</span><span class="sxs-lookup"><span data-stu-id="9638e-105">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="9638e-106">[in]从一个或多个标志[COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="9638e-106">[in] One or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9638e-107">备注</span><span class="sxs-lookup"><span data-stu-id="9638e-107">Remarks</span></span>  
 <span data-ttu-id="9638e-108">探查器获取通过此接口的实例[icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="9638e-108">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="9638e-109">`SetCodegenFlags`允许探查器控制重新编译函数的代码生成。</span><span class="sxs-lookup"><span data-stu-id="9638e-109">`SetCodegenFlags` allows the profiler to control the code generation for the recompiled function.</span></span> <span data-ttu-id="9638e-110">与所有其他 JIT 重新编译参数一样，代码生成标志将应用于函数的所有实例。</span><span class="sxs-lookup"><span data-stu-id="9638e-110">As with all other JIT recompilation parameters, the code generation flags apply to all instances of the function.</span></span>  
  
 <span data-ttu-id="9638e-111">JIT 编译器认为这些编译标志，以及其他编译函数时，由其他源中，指定的标志。</span><span class="sxs-lookup"><span data-stu-id="9638e-111">The JIT compiler considers these compilation flags, along with other flags specified by other sources, when compiling a function.</span></span>  <span data-ttu-id="9638e-112">其他源包括调试器，探查器在启动时通过使用设置的全局标志[icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)方法 (使用值`COR_PRF_DISABLE_INLINING`和`COR_PRF_DISABLE_OPTIMIZATIONS`)，和探查器的[Icorprofilercallback:: Jitinlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="9638e-112">The other sources include the debugger, global flags set by the profiler on startup by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method (with the values `COR_PRF_DISABLE_INLINING` and `COR_PRF_DISABLE_OPTIMIZATIONS`), and the profiler’s [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback.</span></span>  <span data-ttu-id="9638e-113">JIT 编译器赋予优先级与请求最少量的优化的源。</span><span class="sxs-lookup"><span data-stu-id="9638e-113">The JIT compiler gives precedence to a source that requests the least amount of optimizing.</span></span>  <span data-ttu-id="9638e-114">例如，如果探查器指定`COR_PRF_DISABLE_INLINING`上启动，但未指定`COR_PRF_CODEGEN_DISABLE_INLINING`中[icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)回调，内联仍处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="9638e-114">For example, if the profiler specifies `COR_PRF_DISABLE_INLINING` on startup, but does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, inlining is still disabled.</span></span>  <span data-ttu-id="9638e-115">同样，如果未指定探查器`COR_PRF_CODEGEN_DISABLE_INLINING`中`SetCodegenFlags`，但然后禁用通过使用内联[icorprofilercallback:: Jitinlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)回调，内联处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="9638e-115">Similarly, if the profiler does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, but then disables inlining by using the [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback, inlining is disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9638e-116">要求</span><span class="sxs-lookup"><span data-stu-id="9638e-116">Requirements</span></span>  
 <span data-ttu-id="9638e-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9638e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9638e-118">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9638e-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9638e-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9638e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9638e-120">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9638e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9638e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9638e-121">See Also</span></span>  
 [<span data-ttu-id="9638e-122">ICorProfilerFunctionControl 接口</span><span class="sxs-lookup"><span data-stu-id="9638e-122">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)