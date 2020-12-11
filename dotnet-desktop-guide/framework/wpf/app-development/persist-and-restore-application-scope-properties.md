---
title: 如何：跨应用程序会话保持和还原应用程序范围的属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application-scope properties [WPF], persisting
- persisting application-scope properties [WPF]
- properties [WPF], persisting
- restoring application-scope properties [WPF]
- properties [WPF], restoring
- application-scope properties [WPF], restoring
ms.assetid: 55d5904a-f444-4eb5-abd3-6bc74dd14226
ms.openlocfilehash: d9c2dda2745e7528902b6b1c4f46d17264d1a8d8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973290"
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a>如何：跨应用程序会话保持和还原应用程序范围的属性
此示例演示如何在应用程序关闭时保留应用程序范围的属性，以及如何在下次启动应用程序时还原应用程序范围的属性。  
  
## <a name="example"></a>示例  
 应用程序将应用程序范围的属性保存到，并从独立存储中还原它们。 独立存储是受保护的存储区域，应用程序可以安全地使用该存储区域，而无需文件访问权限。  *App.xaml* 文件将 `App_Startup` 方法定义为事件的处理程序 <xref:System.Windows.Application.Startup?displayProperty=nameWithType> ，并将方法定义为 `App_Exit` 事件的处理程序 <xref:System.Windows.Application.Exit?displayProperty=nameWithType> ，如第一个示例中突出显示的行所示。 第二个示例显示了 *App.xaml.cs* 和 *app.config* 文件的一部分，这些文件重点介绍了方法的代码 `App_Startup` ，该方法可还原应用程序范围的属性和方法，该方法 `App_Exit` 可保存应用程序范围的属性。

 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=14-45)]
