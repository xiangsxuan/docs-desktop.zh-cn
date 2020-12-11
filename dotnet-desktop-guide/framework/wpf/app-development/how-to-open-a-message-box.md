---
title: 如何：打开消息框
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: bd2c4dce78e46163eb4628cb3aab829fc0173edf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973321"
---
# <a name="how-to-open-a-message-box"></a><span data-ttu-id="883eb-102">如何：打开消息框</span><span class="sxs-lookup"><span data-stu-id="883eb-102">How to: Open a Message Box</span></span>
<span data-ttu-id="883eb-103">此示例演示如何打开消息框。</span><span class="sxs-lookup"><span data-stu-id="883eb-103">This example shows how to open a message box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="883eb-104">示例</span><span class="sxs-lookup"><span data-stu-id="883eb-104">Example</span></span>  
 <span data-ttu-id="883eb-105">消息框是用于向用户显示信息的预制模式对话框。</span><span class="sxs-lookup"><span data-stu-id="883eb-105">A message box is a prefabricated modal dialog box for displaying information to users.</span></span> <span data-ttu-id="883eb-106">通过调用类的静态方法打开一个消息框 <xref:System.Windows.MessageBox.Show%2A> <xref:System.Windows.MessageBox> 。</span><span class="sxs-lookup"><span data-stu-id="883eb-106">A message box is opened by calling the static <xref:System.Windows.MessageBox.Show%2A> method of the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="883eb-107"><xref:System.Windows.MessageBox.Show%2A>调用时，将使用字符串参数来传递消息。</span><span class="sxs-lookup"><span data-stu-id="883eb-107">When <xref:System.Windows.MessageBox.Show%2A> is called, the message is passed using a string parameter.</span></span> <span data-ttu-id="883eb-108">的多个重载 <xref:System.Windows.MessageBox.Show%2A> 允许您配置消息框的显示方式 (参阅 <xref:System.Windows.MessageBox>) 。</span><span class="sxs-lookup"><span data-stu-id="883eb-108">Several overloads of <xref:System.Windows.MessageBox.Show%2A> allow you to configure how a message box will appear (see <xref:System.Windows.MessageBox>).</span></span>  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a><span data-ttu-id="883eb-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="883eb-109">See also</span></span>

- [<span data-ttu-id="883eb-110">MessageBox 示例</span><span class="sxs-lookup"><span data-stu-id="883eb-110">MessageBox Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)