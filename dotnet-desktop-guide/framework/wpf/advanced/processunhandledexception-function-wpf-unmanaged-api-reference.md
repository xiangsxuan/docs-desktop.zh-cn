---
title: ProcessUnhandledException 函数-WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 7de12e0d21a6add88ce602ea00b7f7b3aaf0c197
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973142"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a>ProcessUnhandledException 函数 (WPF 非托管 API 参考) 
此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。  
  
 由 Windows Presentation Foundation (WPF) 基础结构用于异常处理。  
  
## <a name="syntax"></a>语法  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a>parameters  
 errorMsg  
 错误消息。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅 [.NET Framework 系统要求](/dotnet/framework/get-started/system-requirements)。  
  
 **.DLL**  
  
 在 .NET Framework 3.0 和3.5： PresentationHostDLL.dll  
  
 在 .NET Framework 4 及更高版本中： PresentationHost_v0400.dll  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [WPF 非托管 API 参考](wpf-unmanaged-api-reference.md)
