---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: cd634b4d4a88d83d425b787ed8493f9aa2504988
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970231"
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="d794a-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="d794a-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="d794a-103">创建一个与当权枚举器相同状态的原始输入设备枚举器，以循环访问相同的列表。</span><span class="sxs-lookup"><span data-stu-id="d794a-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d794a-104">语法</span><span class="sxs-lookup"><span data-stu-id="d794a-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d794a-105">参数</span><span class="sxs-lookup"><span data-stu-id="d794a-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="d794a-106">弄接收 [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) 接口指针的输出变量的地址。</span><span class="sxs-lookup"><span data-stu-id="d794a-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="d794a-107">如果该方法不成功，则不定义此输出变量的值。</span><span class="sxs-lookup"><span data-stu-id="d794a-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d794a-108">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="d794a-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="d794a-109">HRESULT：此方法支持标准返回值 E_INVALIDARG、E_OUTOFMEMORY 和 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="d794a-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d794a-110">注解</span><span class="sxs-lookup"><span data-stu-id="d794a-110">Remarks</span></span>  
 <span data-ttu-id="d794a-111">此方法可以记录枚举序列中的某个点，以便以后返回到该点。</span><span class="sxs-lookup"><span data-stu-id="d794a-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="d794a-112">调用方必须独立于第一个枚举器发布此新枚举器。</span><span class="sxs-lookup"><span data-stu-id="d794a-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
