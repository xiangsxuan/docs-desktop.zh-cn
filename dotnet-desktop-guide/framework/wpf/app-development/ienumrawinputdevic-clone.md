---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: cd634b4d4a88d83d425b787ed8493f9aa2504988
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970231"
---
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
创建一个与当权枚举器相同状态的原始输入设备枚举器，以循环访问相同的列表。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a>parameters  
 `ppenum`  
  
 弄接收 [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) 接口指针的输出变量的地址。 如果该方法不成功，则不定义此输出变量的值。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 HRESULT：此方法支持标准返回值 E_INVALIDARG、E_OUTOFMEMORY 和 E_UNEXPECTED。  
  
## <a name="remarks"></a>备注  
 此方法可以记录枚举序列中的某个点，以便以后返回到该点。 调用方必须独立于第一个枚举器发布此新枚举器。
