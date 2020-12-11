---
title: 如何：在应用程序会话间更改设置的值
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 95e613cb280813cd75d887d3cf147d7c897bc2e6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970666"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a>如何：在应用程序会话间更改设置的值
有时，在编译和部署应用程序后，您可能需要在应用程序会话之间更改设置的值。 例如，你可能想要更改连接字符串以指向正确的数据库位置。 由于设计时工具在编译和部署应用程序后不可用，因此必须在文件中手动更改设置值。  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a>在应用程序会话之间更改设置的值  
  
1. 使用 Microsoft 记事本或其他一些文本编辑器或 XML 编辑器，打开与应用程序关联的 .config 文件。  
  
2. 找到要更改的设置的条目。 其外观应类似于下面所示的示例。  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3. 为设置键入新值，并保存该文件。  
  
## <a name="see-also"></a>另请参阅

- [使用应用程序设置和用户设置](using-application-settings-and-user-settings.md)
- [应用程序设置概述](application-settings-overview.md)
