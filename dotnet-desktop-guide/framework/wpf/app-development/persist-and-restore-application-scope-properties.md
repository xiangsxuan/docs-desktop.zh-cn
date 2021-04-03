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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973290"
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a><span data-ttu-id="11fef-102">如何：跨应用程序会话保持和还原应用程序范围的属性</span><span class="sxs-lookup"><span data-stu-id="11fef-102">How to: Persist and Restore Application-Scope Properties Across Application Sessions</span></span>
<span data-ttu-id="11fef-103">此示例演示如何在应用程序关闭时保留应用程序范围的属性，以及如何在下次启动应用程序时还原应用程序范围的属性。</span><span class="sxs-lookup"><span data-stu-id="11fef-103">This example shows how to persist application-scope properties when an application shuts down, and how to restore application-scope properties when an application is next launch.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11fef-104">示例</span><span class="sxs-lookup"><span data-stu-id="11fef-104">Example</span></span>  
 <span data-ttu-id="11fef-105">应用程序将应用程序范围的属性保存到，并从独立存储中还原它们。</span><span class="sxs-lookup"><span data-stu-id="11fef-105">The application persists application-scope properties to, and restores them from, isolated storage.</span></span> <span data-ttu-id="11fef-106">独立存储是受保护的存储区域，应用程序可以安全地使用该存储区域，而无需文件访问权限。</span><span class="sxs-lookup"><span data-stu-id="11fef-106">Isolated storage is a protected storage area that can safely be used by applications without file access permission.</span></span>  <span data-ttu-id="11fef-107">*App.xaml* 文件将 `App_Startup` 方法定义为事件的处理程序 <xref:System.Windows.Application.Startup?displayProperty=nameWithType> ，并将方法定义为 `App_Exit` 事件的处理程序 <xref:System.Windows.Application.Exit?displayProperty=nameWithType> ，如第一个示例中突出显示的行所示。</span><span class="sxs-lookup"><span data-stu-id="11fef-107">The *App.xaml* file defines the `App_Startup` method as the handler for the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event, and the `App_Exit` method as the handler for the  <xref:System.Windows.Application.Exit?displayProperty=nameWithType> event, as shown in the highlighted lines of the first example.</span></span> <span data-ttu-id="11fef-108">第二个示例显示 *应用* 程序的一部分，其中突出显示了方法的代码， *这些文件将* `App_Startup` 还原应用程序范围的属性和 `App_Exit` 方法，这将保存应用程序范围的属性。</span><span class="sxs-lookup"><span data-stu-id="11fef-108">The second example shows a portion of the *App.xaml.cs* and *App.xaml.vb* files that highlights the code for the `App_Startup` method, which restores application-scope properties, and the `App_Exit` method, which saves application-scope properties.</span></span>

 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=14-45)]
