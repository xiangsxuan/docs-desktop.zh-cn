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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973338"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a>ForwardTranslateAccelerator 函数 (WPF 非托管 API 参考) 
此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。  
  
 由用于 Windows 管理的 Windows Presentation Foundation (WPF) 基础结构使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a>parameters  
 pMsg  
 指向消息的指针。  
  
 appUnhandled  
 `true` 如果已向应用程序提供处理输入消息的机会，但尚未对其进行处理，则为;否则为 `false` 。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅 [.NET Framework 系统要求](/dotnet/framework/get-started/system-requirements)。  
  
 **.DLL**  
  
 在 .NET Framework 3.0 和3.5： PresentationHostDLL.dll  
  
 在 .NET Framework 4 及更高版本中： PresentationHost_v0400.dll  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [WPF 非托管 API 参考](wpf-unmanaged-api-reference.md)
