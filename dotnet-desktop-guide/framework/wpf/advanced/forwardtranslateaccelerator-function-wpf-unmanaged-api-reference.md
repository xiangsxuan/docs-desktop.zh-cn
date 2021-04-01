---
title: ForwardTranslateAccelerator 函数-WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: 5e477314117db7be35580b70b84fcc9ad9226e73
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973338"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="400fe-102">ForwardTranslateAccelerator 函数 (WPF 非托管 API 参考) </span><span class="sxs-lookup"><span data-stu-id="400fe-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="400fe-103">此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="400fe-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="400fe-104">由用于 Windows 管理的 Windows Presentation Foundation (WPF) 基础结构使用。</span><span class="sxs-lookup"><span data-stu-id="400fe-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="400fe-105">语法</span><span class="sxs-lookup"><span data-stu-id="400fe-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="400fe-106">参数</span><span class="sxs-lookup"><span data-stu-id="400fe-106">Parameters</span></span>  
 <span data-ttu-id="400fe-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="400fe-107">pMsg</span></span>  
 <span data-ttu-id="400fe-108">指向消息的指针。</span><span class="sxs-lookup"><span data-stu-id="400fe-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="400fe-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="400fe-109">appUnhandled</span></span>  
 <span data-ttu-id="400fe-110">`true` 如果已向应用程序提供处理输入消息的机会，但尚未对其进行处理，则为;否则为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="400fe-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="400fe-111">要求</span><span class="sxs-lookup"><span data-stu-id="400fe-111">Requirements</span></span>  
 <span data-ttu-id="400fe-112">**平台：** 请参阅 [.NET Framework 系统要求](/dotnet/framework/get-started/system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="400fe-112">**Platforms:** See [.NET Framework System Requirements](/dotnet/framework/get-started/system-requirements).</span></span>  
  
 <span data-ttu-id="400fe-113">**.DLL**</span><span class="sxs-lookup"><span data-stu-id="400fe-113">**DLL:**</span></span>  
  
 <span data-ttu-id="400fe-114">在 .NET Framework 3.0 和3.5： PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="400fe-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="400fe-115">在 .NET Framework 4 及更高版本中： PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="400fe-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="400fe-116">**.NET Framework 版本：**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="400fe-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="400fe-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="400fe-117">See also</span></span>

- [<span data-ttu-id="400fe-118">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="400fe-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
