---
title: LoadFromHistory 函数-WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: fa5851658fd21e222a277ea78ad8dcd53009bf17
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973590"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="a0398-102">LoadFromHistory 函数 (WPF 非托管 API 参考) </span><span class="sxs-lookup"><span data-stu-id="a0398-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="a0398-103">此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="a0398-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="a0398-104">由用于 Windows 管理的 Windows Presentation Foundation (WPF) 基础结构使用。</span><span class="sxs-lookup"><span data-stu-id="a0398-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0398-105">语法</span><span class="sxs-lookup"><span data-stu-id="a0398-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0398-106">parameters</span><span class="sxs-lookup"><span data-stu-id="a0398-106">Parameters</span></span>  
 <span data-ttu-id="a0398-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="a0398-107">pHistoryStream</span></span>  
 <span data-ttu-id="a0398-108">指向历史记录信息流的指针。</span><span class="sxs-lookup"><span data-stu-id="a0398-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="a0398-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="a0398-109">pBindCtx</span></span>  
 <span data-ttu-id="a0398-110">指向绑定上下文的指针。</span><span class="sxs-lookup"><span data-stu-id="a0398-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0398-111">要求</span><span class="sxs-lookup"><span data-stu-id="a0398-111">Requirements</span></span>  
 <span data-ttu-id="a0398-112">**平台：** 请参阅 [.NET Framework 系统要求](/dotnet/framework/get-started/system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="a0398-112">**Platforms:** See [.NET Framework System Requirements](/dotnet/framework/get-started/system-requirements).</span></span>  
  
 <span data-ttu-id="a0398-113">**.DLL**</span><span class="sxs-lookup"><span data-stu-id="a0398-113">**DLL:**</span></span>  
  
 <span data-ttu-id="a0398-114">在 .NET Framework 3.0 和3.5： PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="a0398-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="a0398-115">在 .NET Framework 4 及更高版本中： PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="a0398-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="a0398-116">**.NET Framework 版本：**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0398-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0398-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0398-117">See also</span></span>

- [<span data-ttu-id="a0398-118">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="a0398-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
