---
title: IEnumRAWINPUTDEVIC:Skip
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: a74f71345a22f6d766c2d5966ca5d2cb33ab756e
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973319"
---
# <a name="ienumrawinputdevicskip"></a>IEnumRAWINPUTDEVIC:Skip
指示枚举器跳过枚举中的下一个 `celt` 元素，以便对 [IEnumRAWINPUTDEVIC： next](ienumrawinputdevic-next.md) 的下一次调用将不返回这些元素。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Skip( [in] ULONG celt);  
```  
  
## <a name="parameters"></a>参数  
 `celt`  
  
 中要跳过的元素数。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 HRESULT：如果提供的元素数量为 `celt`，则值为 S_OK；否则为 S_FALSE。
