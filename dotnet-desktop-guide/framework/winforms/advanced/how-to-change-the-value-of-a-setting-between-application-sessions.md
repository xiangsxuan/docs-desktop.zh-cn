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
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="903d3-102">如何：在应用程序会话间更改设置的值</span><span class="sxs-lookup"><span data-stu-id="903d3-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="903d3-103">有时，在编译和部署应用程序后，您可能需要在应用程序会话之间更改设置的值。</span><span class="sxs-lookup"><span data-stu-id="903d3-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="903d3-104">例如，你可能想要更改连接字符串以指向正确的数据库位置。</span><span class="sxs-lookup"><span data-stu-id="903d3-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="903d3-105">由于设计时工具在编译和部署应用程序后不可用，因此必须在文件中手动更改设置值。</span><span class="sxs-lookup"><span data-stu-id="903d3-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="903d3-106">在应用程序会话之间更改设置的值</span><span class="sxs-lookup"><span data-stu-id="903d3-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1. <span data-ttu-id="903d3-107">使用 Microsoft 记事本或其他一些文本编辑器或 XML 编辑器，打开与应用程序关联的 .config 文件。</span><span class="sxs-lookup"><span data-stu-id="903d3-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2. <span data-ttu-id="903d3-108">找到要更改的设置的条目。</span><span class="sxs-lookup"><span data-stu-id="903d3-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="903d3-109">其外观应类似于下面所示的示例。</span><span class="sxs-lookup"><span data-stu-id="903d3-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3. <span data-ttu-id="903d3-110">为设置键入新值，并保存该文件。</span><span class="sxs-lookup"><span data-stu-id="903d3-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="903d3-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="903d3-111">See also</span></span>

- [<span data-ttu-id="903d3-112">使用应用程序设置和用户设置</span><span class="sxs-lookup"><span data-stu-id="903d3-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="903d3-113">应用程序设置概述</span><span class="sxs-lookup"><span data-stu-id="903d3-113">Application Settings Overview</span></span>](application-settings-overview.md)
