---
title: ProcessUnhandledException 函数-WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 7de12e0d21a6add88ce602ea00b7f7b3aaf0c197
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973142"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="bbe59-102">ProcessUnhandledException 函数 (WPF 非托管 API 参考) </span><span class="sxs-lookup"><span data-stu-id="bbe59-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="bbe59-103">此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="bbe59-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="bbe59-104">由 Windows Presentation Foundation (WPF) 基础结构用于异常处理。</span><span class="sxs-lookup"><span data-stu-id="bbe59-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbe59-105">语法</span><span class="sxs-lookup"><span data-stu-id="bbe59-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbe59-106">parameters</span><span class="sxs-lookup"><span data-stu-id="bbe59-106">Parameters</span></span>  
 <span data-ttu-id="bbe59-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="bbe59-107">errorMsg</span></span>  
 <span data-ttu-id="bbe59-108">错误消息。</span><span class="sxs-lookup"><span data-stu-id="bbe59-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbe59-109">要求</span><span class="sxs-lookup"><span data-stu-id="bbe59-109">Requirements</span></span>  
 <span data-ttu-id="bbe59-110">**平台：** 请参阅 [.NET Framework 系统要求](/dotnet/framework/get-started/system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="bbe59-110">**Platforms:** See [.NET Framework System Requirements](/dotnet/framework/get-started/system-requirements).</span></span>  
  
 <span data-ttu-id="bbe59-111">**.DLL**</span><span class="sxs-lookup"><span data-stu-id="bbe59-111">**DLL:**</span></span>  
  
 <span data-ttu-id="bbe59-112">在 .NET Framework 3.0 和3.5： PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="bbe59-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="bbe59-113">在 .NET Framework 4 及更高版本中： PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="bbe59-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="bbe59-114">**.NET Framework 版本：**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbe59-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe59-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbe59-115">See also</span></span>

- [<span data-ttu-id="bbe59-116">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="bbe59-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)