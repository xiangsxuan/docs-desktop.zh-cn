---
title: 在 Windows 窗体上承载 ActiveX 控件时的注意事项
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- ActiveX controls [Windows Forms], hosting
- Windows Forms, ActiveX controls
- Windows Forms, hosting ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
ms.openlocfilehash: d4d990bf904fbd8f89fa2a6f70117212a44d3932
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970189"
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a>在 Windows 窗体上承载 ActiveX 控件时的注意事项

尽管 Windows 窗体已经为承载 Windows 窗体控件而进行了优化，但仍可使用 ActiveX 控件。 规划使用 ActiveX 控件的应用程序时应谨记以下注意事项：  
  
- **安全性** - 公共语言运行时已在代码访问安全性方面得到了增强。 以 Windows 窗体为特色的应用程序在完全信任的环境中运行不会有任何问题；在不完全信任的环境中运行时，大部分功能也是可访问的。 Windows 窗体控件不用编译就可以在浏览器中承载。 然而，Windows 窗体上的 ActiveX 控件无法利用这些安全性增强功能。 运行 ActiveX 控件要求使用属性设置非托管代码权限 <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> 。 有关安全性和非托管代码权限的详细信息，请参阅 <xref:System.Security.Permissions.SecurityPermissionAttribute> 。  
  
- **总拥有成本** - 添加到 Windows 窗体的 ActiveX 控件将作为一个整体部署到该 Windows 窗体中，这会显著增加所创建文件的大小。 另外，在 Windows 窗体上使用 ActiveX 控件时需要写入注册表。 对用户的计算机来说，这比 Windows 窗体控件更具侵入性，因为后者不需要这样做。  
  
    > [!NOTE]
    > 使用 ActiveX 控件时需要使用 COM 互操作包装器。 有关详细信息，请参阅 [Visual Basic 和 Visual C# 中的 COM 互操作性](/dotnet/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications)。  
    > [!NOTE]
    > 如果 ActiveX 控件的成员名称与 .NET Framework 中定义的名称相匹配，则在创建派生类时，ActiveX 控件导入程序会在成员名称前加上 **Ctl** 前缀 <xref:System.Windows.Forms.AxHost> 。 例如，如果 ActiveX 控件有一个名为 " **Layout**" 的成员，则会在 AxHost 派生类中将其重命名为 **CtlLayout** ，因为 **Layout** 事件是在 .NET Framework 中定义的。  
  
## <a name="see-also"></a>另请参阅

- [如何：向 Windows 窗体添加 ActiveX 控件](how-to-add-activex-controls-to-windows-forms.md)
- [代码访问安全性](/dotnet/framework/misc/code-access-security)
- [不同语言和库中的控件和可编程对象的比较](/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [将控件放在 Windows 窗体上](putting-controls-on-windows-forms.md)
- [Windows 窗体控件](index.md)
