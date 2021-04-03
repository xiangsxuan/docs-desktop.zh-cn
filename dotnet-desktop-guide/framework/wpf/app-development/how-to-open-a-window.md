---
title: 如何：打开窗口
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows [WPF], opening
- opening windows [WPF]
ms.assetid: 6b91b2bb-fda7-491d-a72e-139dd630a5b0
ms.openlocfilehash: 9ce7ffb3f46dd869fda7893745b531bd02d18ee1
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973864"
---
# <a name="how-to-open-a-window"></a><span data-ttu-id="f596a-102">如何：打开窗口</span><span class="sxs-lookup"><span data-stu-id="f596a-102">How to: Open a Window</span></span>
<span data-ttu-id="f596a-103">此示例演示如何打开窗口。</span><span class="sxs-lookup"><span data-stu-id="f596a-103">This example shows how to open a window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f596a-104">示例</span><span class="sxs-lookup"><span data-stu-id="f596a-104">Example</span></span>  
 <span data-ttu-id="f596a-105">窗口通过实例化 <xref:System.Windows.Window> 并调用 <xref:System.Windows.Window.Show%2A> 方法打开。</span><span class="sxs-lookup"><span data-stu-id="f596a-105">A window is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.Show%2A> method.</span></span> <span data-ttu-id="f596a-106"><xref:System.Windows.Window.Show%2A> 打开窗口并立即返回，而不等待新窗口关闭。</span><span class="sxs-lookup"><span data-stu-id="f596a-106"><xref:System.Windows.Window.Show%2A> opens a window and returns immediately without waiting for the new window to close.</span></span> <span data-ttu-id="f596a-107">这种类型的窗口也称为 *无模式* 窗口，并不限制用户输入。</span><span class="sxs-lookup"><span data-stu-id="f596a-107">This type of window is also known as a *modeless* window, and doesn't restrict user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="f596a-108">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="f596a-108">.NET Framework Security</span></span>  
 <span data-ttu-id="f596a-109">实例化 <xref:System.Windows.Window> 需要权限才能调用安全的本机方法 (参阅 <xref:System.Windows.Window.%23ctor%2A>) 。</span><span class="sxs-lookup"><span data-stu-id="f596a-109">Instantiating <xref:System.Windows.Window> requires permission to call unsafe native methods (see <xref:System.Windows.Window.%23ctor%2A>).</span></span>
