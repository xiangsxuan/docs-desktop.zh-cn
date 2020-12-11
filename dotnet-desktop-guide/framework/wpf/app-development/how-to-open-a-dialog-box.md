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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972865"
---
# <a name="how-to-open-a-dialog-box"></a>如何：打开对话框
此示例演示如何打开对话框。  
  
## <a name="example"></a>示例  
 对话框是通过实例化并调用方法打开的窗口 <xref:System.Windows.Window> <xref:System.Windows.Window.ShowDialog%2A> 。 <xref:System.Windows.Window.ShowDialog%2A> 打开一个窗口，不返回，直到新对话框关闭为止。 这种类型的窗口也称为 *模式* 窗口，用于限制用户输入。  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 调用 <xref:System.Windows.Window.ShowDialog%2A> 需要权限以在没有限制的情况下使用所有窗口和用户输入事件。  
  
## <a name="see-also"></a>另请参阅

- [返回对话框结果](how-to-return-a-dialog-box-result.md)
