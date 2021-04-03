---
title: FilterInputMessage
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
- FilterInputMessage method [WPF]
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
ms.openlocfilehash: 1453946766e33843ae9e56f7a7f4dbf1678b81b5
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972709"
---
# <a name="filterinputmessage"></a>FilterInputMessage
除非返回 E_NOTIMP，否则每当收到一条消息时都会由 PresentationHost.exe 调用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
## <a name="parameters"></a>参数  
 `pMsg`  
  
 [in] 发送给正在获得原始输入的窗口的 WM_INPUT 消息。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 HRESULT：  
  
 S_OK - 筛选器未处理该消息，且可能执行进一步处理。  
  
 S_FALSE - 筛选器已处理此消息，且应执行进一步处理。  
  
 E_NOTIMPL –如果返回此值，则不会再次调用 [FilterInputMessage](filterinputmessage.md) 。 这可能会从以下主机应用程序返回：仅对向 PresentationHost.exe 提供自定义进度和错误用户界面有兴趣且对从 PresentationHost.exe 向自身转发原始输入消息不感兴趣。  
  
## <a name="remarks"></a>注解  
 PresentationHost.exe 是各种原始输入设备（包括键盘、鼠标和远程控件）的目标。 有时，主机应用程序中的行为取决于输入，否则将由 PresentationHost.exe 消耗。 例如，主机应用程序可能依靠接收特定输入消息来确定是否显示特定的用户界面元素。  
  
 若要允许主机应用程序接收所需的输入消息以提供这些行为，PresentationHost.exe 通过调用 [FilterInputMessage](filterinputmessage.md)将相应的原始输入消息转发到托管应用程序。  
  
 托管应用程序通过使用一组原始输入设备（ (人体学接口设备）注册来接收原始输入消息，) 由 [GetRawInputDevices](getrawinputdevices.md)返回。  
  
## <a name="see-also"></a>另请参阅

- [WM_INPUT 消息](/windows/desktop/inputdev/wm-input)
