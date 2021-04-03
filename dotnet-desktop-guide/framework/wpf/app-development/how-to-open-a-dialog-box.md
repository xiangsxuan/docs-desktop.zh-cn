---
title: 如何：打开对话框
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
ms.openlocfilehash: 70ac31285dd22244b4bd6ad0d188d182eb6e6264
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972865"
---
# <a name="how-to-open-a-dialog-box"></a><span data-ttu-id="83690-102">如何：打开对话框</span><span class="sxs-lookup"><span data-stu-id="83690-102">How to: Open a Dialog Box</span></span>
<span data-ttu-id="83690-103">此示例演示如何打开对话框。</span><span class="sxs-lookup"><span data-stu-id="83690-103">This example shows how to open a dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83690-104">示例</span><span class="sxs-lookup"><span data-stu-id="83690-104">Example</span></span>  
 <span data-ttu-id="83690-105">对话框是通过实例化并调用方法打开的窗口 <xref:System.Windows.Window> <xref:System.Windows.Window.ShowDialog%2A> 。</span><span class="sxs-lookup"><span data-stu-id="83690-105">A dialog box is a window that is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span> <span data-ttu-id="83690-106"><xref:System.Windows.Window.ShowDialog%2A> 打开一个窗口，不返回，直到新对话框关闭为止。</span><span class="sxs-lookup"><span data-stu-id="83690-106"><xref:System.Windows.Window.ShowDialog%2A> opens a window and doesn't return until the new dialog box has been closed.</span></span> <span data-ttu-id="83690-107">这种类型的窗口也称为 *模式* 窗口，用于限制用户输入。</span><span class="sxs-lookup"><span data-stu-id="83690-107">This type of window is also known as a *modal* window, and restricts user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="83690-108">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="83690-108">.NET Framework Security</span></span>  
 <span data-ttu-id="83690-109">调用 <xref:System.Windows.Window.ShowDialog%2A> 需要权限以在没有限制的情况下使用所有窗口和用户输入事件。</span><span class="sxs-lookup"><span data-stu-id="83690-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83690-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83690-110">See also</span></span>

- [<span data-ttu-id="83690-111">返回对话框结果</span><span class="sxs-lookup"><span data-stu-id="83690-111">Return a Dialog Box Result</span></span>](how-to-return-a-dialog-box-result.md)
