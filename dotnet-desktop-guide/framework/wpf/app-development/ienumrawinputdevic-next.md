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
# <a name="ienumrawinputdevicnext"></a>IEnumRAWINPUTDEVIC:Next
枚举 `celt` 枚举器列表中的下一个 [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) 结构，将它们 `rgelt` 与中的枚举元素的实际数目一起返回 `pceltFetched` 。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a>参数  
 `celt`  
  
 中返回的 [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) 结构的数目 `rgelt` 。  
  
 `rgelt`  
  
 [out] celt 大小（或更大）的数组，用于接收枚举的 RAWINPUTDEVICE 结构。  
  
 `pceltFetched`  
  
 [out] 指向 `rgelt` 中实际提供的元素数量的指针。 如果 `NULL` 为一，则调用方可传入 `rgelt`。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 HRESULT：如果提供的元素数量为 `celt`，则值为 S_OK；否则为 S_FALSE。
