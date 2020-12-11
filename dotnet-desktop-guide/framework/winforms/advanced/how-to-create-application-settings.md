---
title: 如何：创建应用程序设置
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], creating
ms.assetid: 1e7aa347-af75-41e5-89ca-f53cab704f72
ms.openlocfilehash: 1c7bcb5b9166cf8fcb01f11d701ea4ebca713ee7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970575"
---
# <a name="how-to-create-application-settings"></a>如何：创建应用程序设置

使用托管代码时，你可以创建新的应用程序设置并将其绑定窗体或窗体控件的属性上，以便在运行时自动加载和保存这些设置。  
  
 在以下过程中，手动创建从 <xref:System.Configuration.ApplicationSettingsBase> 派生的包装类。 对于此类，你可以为每个想要公开的应用程序设置添加可公开访问的属性。  
  
 你还可以使用 Visual Studio 设计器中的最小代码执行该过程。  另请参阅 [如何：使用设计器创建应用程序设置](/previous-versions/visualstudio/visual-studio-2010/wabtadw6(v=vs.100))。  
  
### <a name="to-create-new-application-settings-programmatically"></a>以编程的方式创建新的应用程序设置  
  
1. 向你的项目添加新类，并对其重命名。 对于此过程，我们将调用此类 `MyUserSettings` 。 更改类定义，以使类从 <xref:System.Configuration.ApplicationSettingsBase> 派生。  
  
2. 为你需要的每个应用程序设置定义此包装类的属性，并将该属性应用到 <xref:System.Configuration.ApplicationScopedSettingAttribute> 或 <xref:System.Configuration.UserScopedSettingAttribute>，具体取决于设置的作用域。 有关设置作用域的详细信息，请参阅 [应用程序设置概述](application-settings-overview.md)。 现在，代码应如下所示：  
  
     [!code-csharp[ApplicationSettings.Create#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
     [!code-vb[ApplicationSettings.Create#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
3. 在你的应用程序中创建此包装类的实例。 该实例通常为主窗体的私有成员。 对类进行定义后，你需要将其绑定到属性；在这种情况下，是指绑定到你窗体的 <xref:System.Windows.Forms.Form.BackColor%2A> 属性。 可以在窗体的事件处理程序中完成此项 `Load` 。  
  
     [!code-csharp[ApplicationSettings.Create#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#2)]
     [!code-vb[ApplicationSettings.Create#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#2)]  
  
4. 如果你在运行时提供了一种更改设置的方法，则关闭窗体时需要将用户的当前设置保存到磁盘，否则将丢失这些更改。  
  
     [!code-csharp[ApplicationSettings.Create#3](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#3)]
     [!code-vb[ApplicationSettings.Create#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#3)]  
  
     现在，你已成功创建了一个新的应用程序设置并将其绑定到了指定的属性中。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  

 默认的设置提供程序 <xref:System.Configuration.LocalFileSettingsProvider> 会将配置文件的信息视为纯文本处理。 这将限制由当前用户由的操作系统提供的文件访问安全性的安全。 因此，必须谨慎处理配置文件中存储的信息。 例如，应用程序设置一种常见的用法就是，存储指向应用程序数据存储的连接字符串。 但是，出于安全考虑，此类字符串不应包括密码。 有关连接字符串的详细信息，请参阅 <xref:System.Configuration.SpecialSetting>。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Configuration.SpecialSettingAttribute>
- <xref:System.Configuration.LocalFileSettingsProvider>
- [应用程序设置概述](application-settings-overview.md)
- [如何：验证应用程序设置](how-to-validate-application-settings.md)
