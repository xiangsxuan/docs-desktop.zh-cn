---
title: 如何：获取和设置主应用程序窗口
description: 按照以下示例获取并设置 Windows Presentation Foundation (WPF) 应用程序内的主应用程序窗口。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows objects [WPF], setting
- setting windows objects [WPF]
- windows objects [WPF], getting
- getting windows objects [WPF]
ms.assetid: ec902bc4-4a59-46f5-8ec1-963b46789356
ms.openlocfilehash: 9bb5bce9b90482796acd8c62e77dc8bd9a850eeb
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973892"
---
# <a name="how-to-get-and-set-the-main-application-window"></a>如何：获取和设置主应用程序窗口
此示例演示如何获取和设置主应用程序窗口。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Window>Windows Presentation Foundation (WPF) 应用程序中实例化的第一个实例将由 <xref:System.Windows.Application> 主应用程序窗口自动设置。 首先 <xref:System.Windows.Window> 要实例化的窗口很可能是指定为启动统一资源标识符 (URI) 的窗口 (参阅 <xref:System.Windows.Application.StartupUri%2A>) 。  
  
 第一种情况 <xref:System.Windows.Window> 也可以使用代码来实例化。 例如，在应用程序启动过程中打开一个窗口，如下所示：  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 有时，第一个实例化 <xref:System.Windows.Window> 实际上并不是主应用程序窗口（例如，初始屏幕）。 在这种情况下，可以使用标记指定主应用程序窗口，如下所示：  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 无论是自动还是手动指定主窗口，都可以使用以下代码获取主窗口 <xref:System.Windows.Application.MainWindow%2A> ，如下所示：  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
