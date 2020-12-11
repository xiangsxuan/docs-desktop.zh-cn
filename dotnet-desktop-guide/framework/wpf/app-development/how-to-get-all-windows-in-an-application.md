---
title: 如何：获取应用程序中的所有窗口
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
ms.openlocfilehash: 34316f0c6f81b960a8e00131a30b9a237b9ca938
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973865"
---
# <a name="how-to-get-all-windows-in-an-application"></a><span data-ttu-id="d01de-102">如何：获取应用程序中的所有窗口</span><span class="sxs-lookup"><span data-stu-id="d01de-102">How to: Get all Windows in an Application</span></span>
<span data-ttu-id="d01de-103">此示例演示如何获取 <xref:System.Windows.Window> 应用程序中的所有对象。</span><span class="sxs-lookup"><span data-stu-id="d01de-103">This example shows how to get all <xref:System.Windows.Window> objects in an application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d01de-104">示例</span><span class="sxs-lookup"><span data-stu-id="d01de-104">Example</span></span>  
 <span data-ttu-id="d01de-105">每个实例化 <xref:System.Windows.Window> 对象（无论是否可见）都将自动添加到由管理 <xref:System.Windows.Application> 并从公开的窗口引用集合 <xref:System.Windows.Application.Windows%2A> 。</span><span class="sxs-lookup"><span data-stu-id="d01de-105">Every instantiated <xref:System.Windows.Window> object, whether visible or not, is automatically added to a collection of window references that is managed by <xref:System.Windows.Application>, and exposed from <xref:System.Windows.Application.Windows%2A>.</span></span>  
  
 <span data-ttu-id="d01de-106">可以 <xref:System.Windows.Application.Windows%2A> 使用以下代码枚举以获取所有实例化的窗口：</span><span class="sxs-lookup"><span data-stu-id="d01de-106">You can enumerate <xref:System.Windows.Application.Windows%2A> to get all instantiated windows using the following code:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
