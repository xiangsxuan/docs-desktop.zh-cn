---
title: CreateIDispatchSTAForwarder 函数-WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: f7f60c53125eaaafe88b8777f3b560d5d1e083b2
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971947"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>CreateIDispatchSTAForwarder 函数 (WPF 非托管 API 参考) 
此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。  
  
 由 Windows Presentation Foundation (WPF) 基础结构用于线程和 Windows 管理。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a>参数  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 pDispatchDelegate  
 指向接口的指针 `IDispatch` 。  
  
 ppForwarder  
 指向接口的地址的指针 `IDispatch` 。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅 [.NET Framework 系统要求](/dotnet/framework/get-started/system-requirements)。  
  
 **.DLL**  
  
 在 .NET Framework 3.0 和3.5： PresentationHostDLL.dll  
  
 在 .NET Framework 4 及更高版本中： PresentationHost_v0400.dll  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [WPF 非托管 API 参考](wpf-unmanaged-api-reference.md)
