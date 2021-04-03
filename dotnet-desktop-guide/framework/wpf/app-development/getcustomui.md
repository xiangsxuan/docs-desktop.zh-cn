---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: e9ef32912c2afb3c99e46e1e14bb3daa5a2e99af
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972708"
---
# <a name="getcustomui"></a>GetCustomUI
由 PresentationHost.exe 调用，以从主机获取自定义进度和错误消息（如果已实现）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a>参数  
 `pwzProgressAssemblyName`  
  
 弄指向包含主机提供的进度用户界面的程序集的指针。  
  
 `pwzProgressClassName`  
  
 弄类的名称，它是宿主提供的进度用户界面，最好是具有的 XAML 文件 <xref:System.Windows.Controls.Page> 是其顶级元素。 此类驻留在指定的程序集中 `pwzProgressAssemblyName` 。  
  
 `pwzErrorAssemblyName`  
  
 弄指向包含宿主提供的错误用户界面的程序集的指针。  
  
 `pwzErrorClassName`  
  
 弄类的名称，它是宿主提供的错误用户界面，最好是具有的 XAML 文件 <xref:System.Windows.Controls.Page> 是它的顶级元素。 此类驻留在指定的程序集中 `pwzErrorAssemblyName` 。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 HRESULT：已忽略。  
  
## <a name="remarks"></a>注解  
 宿主应用程序可能有 PresentationHost.exe 默认用户界面不符合的特定主题。 如果是这种情况，主机应用程序可以实现 [GetCustomUI](getcustomui.md) ，以将进度和错误用户界面返回到 PresentationHost.exe。 PresentationHost.exe 将始终在使用其默认用户界面之前调用 [GetCustomUI](getcustomui.md) 。  
  
 此函数在 Presentationhost.exe 的初始化过程中调用一次。  
  
## <a name="see-also"></a>另请参阅

- [IWpfHostSupport](iwpfhostsupport.md)
