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
# <a name="how-to-open-a-window"></a>如何：打开窗口
此示例演示如何打开窗口。  
  
## <a name="example"></a>示例  
 窗口通过实例化 <xref:System.Windows.Window> 并调用 <xref:System.Windows.Window.Show%2A> 方法打开。 <xref:System.Windows.Window.Show%2A> 打开窗口并立即返回，而不等待新窗口关闭。 这种类型的窗口也称为 *无模式* 窗口，并不限制用户输入。  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 实例化 <xref:System.Windows.Window> 需要权限才能调用安全的本机方法 (参阅 <xref:System.Windows.Window.%23ctor%2A>) 。
