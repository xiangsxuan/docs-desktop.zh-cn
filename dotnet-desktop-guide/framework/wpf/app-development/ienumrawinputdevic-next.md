---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: c7450a9ababa9cf3cb02d572f5ed84f0791d74e4
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970227"
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="3dc58-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="3dc58-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="3dc58-103">枚举 `celt` 枚举器列表中的下一个 [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) 结构，将它们 `rgelt` 与中的枚举元素的实际数目一起返回 `pceltFetched` 。</span><span class="sxs-lookup"><span data-stu-id="3dc58-103">Enumerates the next `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dc58-104">语法</span><span class="sxs-lookup"><span data-stu-id="3dc58-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3dc58-105">参数</span><span class="sxs-lookup"><span data-stu-id="3dc58-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="3dc58-106">中返回的 [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) 结构的数目 `rgelt` 。</span><span class="sxs-lookup"><span data-stu-id="3dc58-106">[in] Number of [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="3dc58-107">[out] celt 大小（或更大）的数组，用于接收枚举的 RAWINPUTDEVICE 结构。</span><span class="sxs-lookup"><span data-stu-id="3dc58-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="3dc58-108">[out] 指向 `rgelt` 中实际提供的元素数量的指针。</span><span class="sxs-lookup"><span data-stu-id="3dc58-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="3dc58-109">如果 `NULL` 为一，则调用方可传入 `rgelt`。</span><span class="sxs-lookup"><span data-stu-id="3dc58-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="3dc58-110">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="3dc58-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="3dc58-111">HRESULT：如果提供的元素数量为 `celt`，则值为 S_OK；否则为 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="3dc58-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
