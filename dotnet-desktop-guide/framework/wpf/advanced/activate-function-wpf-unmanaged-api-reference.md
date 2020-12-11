---
title: 激活函数 WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: c97069613a96009d0b9bb84e55c37b29c2d3ea5b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970500"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a> (WPF 非托管 API 引用中激活函数) 

此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。

由用于 Windows 管理的 Windows Presentation Foundation (WPF) 基础结构使用。

## <a name="syntax"></a>语法

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a>parameters

`pParameters`\
指向窗口的激活参数的指针。

`ppInner`\
一个指针，指向包含指向对象的指针的单元素缓冲区的地址 <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> 。

## <a name="requirements"></a>要求

**平台：** 请参阅 [.NET Framework 系统要求](/dotnet/framework/get-started/system-requirements)。

**.DLL**

在 .NET Framework 3.0 和3.5： PresentationHostDLL.dll

在 .NET Framework 4 及更高版本中： PresentationHost_v0400.dll

**.NET Framework 版本：**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]

## <a name="see-also"></a>另请参阅

- [WPF 非托管 API 参考](wpf-unmanaged-api-reference.md)
