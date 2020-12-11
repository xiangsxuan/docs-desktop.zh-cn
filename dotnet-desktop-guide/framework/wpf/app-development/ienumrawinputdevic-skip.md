---
title: IEnumRAWINPUTDEVIC:Skip
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: a74f71345a22f6d766c2d5966ca5d2cb33ab756e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973319"
---
# <a name="ienumrawinputdevicskip"></a><span data-ttu-id="82276-102">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="82276-102">IEnumRAWINPUTDEVIC:Skip</span></span>
<span data-ttu-id="82276-103">指示枚举器跳过枚举中的下一个 `celt` 元素，以便对 [IEnumRAWINPUTDEVIC： next](ienumrawinputdevic-next.md) 的下一次调用将不返回这些元素。</span><span class="sxs-lookup"><span data-stu-id="82276-103">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82276-104">语法</span><span class="sxs-lookup"><span data-stu-id="82276-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip( [in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82276-105">parameters</span><span class="sxs-lookup"><span data-stu-id="82276-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="82276-106">中要跳过的元素数。</span><span class="sxs-lookup"><span data-stu-id="82276-106">[in] Number of elements to be skipped.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="82276-107">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="82276-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="82276-108">HRESULT：如果提供的元素数量为 `celt`，则值为 S_OK；否则为 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="82276-108">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
