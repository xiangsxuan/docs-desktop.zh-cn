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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973321"
---
# <a name="how-to-open-a-message-box"></a>如何：打开消息框
此示例演示如何打开消息框。  
  
## <a name="example"></a>示例  
 消息框是用于向用户显示信息的预制模式对话框。 通过调用类的静态方法打开一个消息框 <xref:System.Windows.MessageBox.Show%2A> <xref:System.Windows.MessageBox> 。 <xref:System.Windows.MessageBox.Show%2A>调用时，将使用字符串参数来传递消息。 的多个重载 <xref:System.Windows.MessageBox.Show%2A> 允许您配置消息框的显示方式 (参阅 <xref:System.Windows.MessageBox>) 。  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>另请参阅

- [MessageBox 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)
