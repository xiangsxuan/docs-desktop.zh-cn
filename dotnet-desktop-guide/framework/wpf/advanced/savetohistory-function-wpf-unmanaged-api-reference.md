---
title: SaveToHistory 函数-WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- SaveToHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: 6dd101a3-44ad-4143-b228-772156f9b8ff
ms.openlocfilehash: f8cd39fce3f9bc41c315d4e19f95fd19d8bf9d93
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973391"
---
# <a name="savetohistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="50a7f-102">SaveToHistory 函数 (WPF 非托管 API 参考) </span><span class="sxs-lookup"><span data-stu-id="50a7f-102">SaveToHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="50a7f-103">此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="50a7f-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="50a7f-104">由用于 Windows 管理的 Windows Presentation Foundation (WPF) 基础结构使用。</span><span class="sxs-lookup"><span data-stu-id="50a7f-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50a7f-105">语法</span><span class="sxs-lookup"><span data-stu-id="50a7f-105">Syntax</span></span>  
  
```cpp  
HRESULT SaveToHistory(  
   __in_ecount(1) IStream* pHistoryStream  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="50a7f-106">parameters</span><span class="sxs-lookup"><span data-stu-id="50a7f-106">Parameters</span></span>  
 <span data-ttu-id="50a7f-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="50a7f-107">pHistoryStream</span></span>  
 <span data-ttu-id="50a7f-108">指向历史记录流的指针。</span><span class="sxs-lookup"><span data-stu-id="50a7f-108">A pointer to the history stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50a7f-109">要求</span><span class="sxs-lookup"><span data-stu-id="50a7f-109">Requirements</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50a7f-110">要求</span><span class="sxs-lookup"><span data-stu-id="50a7f-110">Requirements</span></span>  
 <span data-ttu-id="50a7f-111">**平台：** 请参阅 [.NET Framework 系统要求](/dotnet/framework/get-started/system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="50a7f-111">**Platforms:** See [.NET Framework System Requirements](/dotnet/framework/get-started/system-requirements).</span></span>  
  
 <span data-ttu-id="50a7f-112">**.DLL**</span><span class="sxs-lookup"><span data-stu-id="50a7f-112">**DLL:**</span></span>  
  
 <span data-ttu-id="50a7f-113">在 .NET Framework 3.0 和3.5： PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="50a7f-113">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="50a7f-114">在 .NET Framework 4 及更高版本中： PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="50a7f-114">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="50a7f-115">**.NET Framework 版本：**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50a7f-115">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50a7f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50a7f-116">See also</span></span>

- [<span data-ttu-id="50a7f-117">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="50a7f-117">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
