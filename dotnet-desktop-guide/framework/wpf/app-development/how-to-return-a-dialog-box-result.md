---
title: 如何：返回对话框结果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: 5e3670006762bcd09634b29314ecf2d05b1a44da
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973866"
---
# <a name="how-to-return-a-dialog-box-result"></a>如何：返回对话框结果
此示例演示如何检索通过调用打开的窗口的对话框结果 <xref:System.Windows.Window.ShowDialog%2A> 。  
  
## <a name="example"></a>示例  
 在对话框关闭之前，应将其 <xref:System.Windows.Window.DialogResult%2A> 属性设置为 <xref:System.Nullable%601> <xref:System.Boolean> ，指示用户如何关闭对话框。 此值由返回， <xref:System.Windows.Window.ShowDialog%2A> 以允许客户端代码确定对话框的关闭方式，进而确定如何处理结果。  
  
> [!NOTE]
> <xref:System.Windows.Window.DialogResult%2A> 仅当通过调用打开了窗口时才能设置 <xref:System.Windows.Window.ShowDialog%2A> 。  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 调用 <xref:System.Windows.Window.ShowDialog%2A> 需要权限以在没有限制的情况下使用所有窗口和用户输入事件。
