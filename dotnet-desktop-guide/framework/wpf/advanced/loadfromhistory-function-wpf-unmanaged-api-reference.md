---
title: LoadFromHistory 函数-WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: fa5851658fd21e222a277ea78ad8dcd53009bf17
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973590"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a>LoadFromHistory 函数 (WPF 非托管 API 参考) 
此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。  
  
 由用于 Windows 管理的 Windows Presentation Foundation (WPF) 基础结构使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a>参数  
 pHistoryStream  
 指向历史记录信息流的指针。  
  
 pBindCtx  
 指向绑定上下文的指针。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅 [.NET Framework 系统要求](/dotnet/framework/get-started/system-requirements)。  
  
 **.DLL**  
  
 在 .NET Framework 3.0 和3.5： PresentationHostDLL.dll  
  
 在 .NET Framework 4 及更高版本中： PresentationHost_v0400.dll  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [WPF 非托管 API 参考](wpf-unmanaged-api-reference.md)
