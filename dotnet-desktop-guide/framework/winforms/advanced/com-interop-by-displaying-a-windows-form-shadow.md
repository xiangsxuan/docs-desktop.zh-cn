---
title: 如何：通过使用 ShowDialog 方法显示 Windows 窗体来支持 COM 互操作
ms.date: 03/30/2017
helpviewer_keywords:
- COM [Windows Forms]
- Windows Forms, unmanaged
- COM interop [Windows Forms], calling methods
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: 87aac8ad-3c04-43b3-9b0c-d0b00df9ee74
ms.openlocfilehash: a4b86616fab5603e08fe9efa1213edaa633deeb9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970354"
---
# <a name="how-to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>如何：通过使用 ShowDialog 方法显示 Windows 窗体来支持 COM 互操作

可以通过在 .NET Framework 消息循环上显示 Windows 窗体来解决组件对象模型 (COM) 互操作性问题，该循环是使用 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> 方法创建的。  
  
 若要使窗体在 COM 客户端应用程序中正确工作，必须在 Windows 窗体消息循环上运行该窗体。 若要执行此操作，请使用以下方法之一：  
  
- 使用 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 方法显示 Windows 窗体；  
  
- 在单独的线程上显示每个 Windows 窗体。 有关详细信息，请参阅 [How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)。  
  
## <a name="procedure"></a>过程  

 使用 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 方法可能是在 .NET Framework 消息循环上显示窗体的最简单方法，因为在所有方法中，它都要求最少的代码来实现。  
  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 方法挂起非托管应用程序的消息循环，并将窗体显示为对话框。 由于宿主应用程序的消息循环已挂起，因此该 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 方法会创建一个新的 .NET Framework 消息循环来处理窗体的消息。  
  
 使用 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 方法的缺点是窗体将作为模式对话框打开。 Windows 窗体打开时，此行为将阻止调用应用程序中的任何用户界面 (UI)。 当用户退出该窗体时，.NET Framework 的消息循环将关闭，并且之前的应用程序的消息循环将开始再次运行。  
  
 可以在 Windows 窗体中创建具有显示窗体方法的类库，然后为 COM 互操作生成类库。 可以从 Visual Basic 6.0 或 Microsoft 基础类 (MFC) 中使用此 DLL 文件，在这两种环境中，都可以调用 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 方法来显示窗体。  
  
#### <a name="to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>通过使用 ShowDialog 方法显示 Windows 窗体来支持 COM 互操作  
  
- 将对方法的所有调用替换为对 <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> .NET Framework 组件中的方法的调用。  
  
## <a name="see-also"></a>请参阅

- [向 COM 公开 .NET Framework 组件](/dotnet/framework/interop/exposing-dotnet-components-to-co)
- [如何：通过在每个 Windows 窗体各自的线程上显示此 Windows 窗体来支持 COM 互操作](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)
- [Windows 窗体和非托管应用程序](windows-forms-and-unmanaged-applications.md)
