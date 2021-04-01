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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973865"
---
# <a name="how-to-get-all-windows-in-an-application"></a>如何：获取应用程序中的所有窗口
此示例演示如何获取 <xref:System.Windows.Window> 应用程序中的所有对象。  
  
## <a name="example"></a>示例  
 每个实例化 <xref:System.Windows.Window> 对象（无论是否可见）都将自动添加到由管理 <xref:System.Windows.Application> 并从公开的窗口引用集合 <xref:System.Windows.Application.Windows%2A> 。  
  
 可以 <xref:System.Windows.Application.Windows%2A> 使用以下代码枚举以获取所有实例化的窗口：  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
