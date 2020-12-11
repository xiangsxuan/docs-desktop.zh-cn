---
title: SaveToHistory 函数-WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- SaveToHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: 6dd101a3-44ad-4143-b228-772156f9b8ff
ms.openlocfilehash: f8cd39fce3f9bc41c315d4e19f95fd19d8bf9d93
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973391"
---
# <a name="savetohistory-function-wpf-unmanaged-api-reference"></a>SaveToHistory 函数 (WPF 非托管 API 参考) 
此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。  
  
 由用于 Windows 管理的 Windows Presentation Foundation (WPF) 基础结构使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SaveToHistory(  
   __in_ecount(1) IStream* pHistoryStream  
)  
```  
  
## <a name="parameters"></a>parameters  
 pHistoryStream  
 指向历史记录流的指针。  
  
## <a name="requirements"></a>要求  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅 [.NET Framework 系统要求](/dotnet/framework/get-started/system-requirements)。  
  
 **.DLL**  
  
 在 .NET Framework 3.0 和3.5： PresentationHostDLL.dll  
  
 在 .NET Framework 4 及更高版本中： PresentationHost_v0400.dll  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [WPF 非托管 API 参考](wpf-unmanaged-api-reference.md)
