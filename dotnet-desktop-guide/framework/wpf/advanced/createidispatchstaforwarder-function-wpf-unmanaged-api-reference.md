---
title: CreateIDispatchSTAForwarder 函数-WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: f7f60c53125eaaafe88b8777f3b560d5d1e083b2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971947"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="a3c5b-102">CreateIDispatchSTAForwarder 函数 (WPF 非托管 API 参考) </span><span class="sxs-lookup"><span data-stu-id="a3c5b-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="a3c5b-103">此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="a3c5b-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="a3c5b-104">由 Windows Presentation Foundation (WPF) 基础结构用于线程和 Windows 管理。</span><span class="sxs-lookup"><span data-stu-id="a3c5b-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3c5b-105">语法</span><span class="sxs-lookup"><span data-stu-id="a3c5b-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3c5b-106">parameters</span><span class="sxs-lookup"><span data-stu-id="a3c5b-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a3c5b-107">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="a3c5b-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="a3c5b-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="a3c5b-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="a3c5b-109">指向接口的指针 `IDispatch` 。</span><span class="sxs-lookup"><span data-stu-id="a3c5b-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="a3c5b-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="a3c5b-110">ppForwarder</span></span>  
 <span data-ttu-id="a3c5b-111">指向接口的地址的指针 `IDispatch` 。</span><span class="sxs-lookup"><span data-stu-id="a3c5b-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3c5b-112">要求</span><span class="sxs-lookup"><span data-stu-id="a3c5b-112">Requirements</span></span>  
 <span data-ttu-id="a3c5b-113">**平台：** 请参阅 [.NET Framework 系统要求](/dotnet/framework/get-started/system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="a3c5b-113">**Platforms:** See [.NET Framework System Requirements](/dotnet/framework/get-started/system-requirements).</span></span>  
  
 <span data-ttu-id="a3c5b-114">**.DLL**</span><span class="sxs-lookup"><span data-stu-id="a3c5b-114">**DLL:**</span></span>  
  
 <span data-ttu-id="a3c5b-115">在 .NET Framework 3.0 和3.5： PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="a3c5b-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="a3c5b-116">在 .NET Framework 4 及更高版本中： PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="a3c5b-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="a3c5b-117">**.NET Framework 版本：**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3c5b-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c5b-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3c5b-118">See also</span></span>

- [<span data-ttu-id="a3c5b-119">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="a3c5b-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
