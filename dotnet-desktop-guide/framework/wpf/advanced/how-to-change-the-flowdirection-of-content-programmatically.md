---
title: 如何：以编程方式更改内容的 FlowDirection
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
ms.openlocfilehash: ec159ed0efce8b5514788331e8715a55e7a8a638
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972839"
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a>如何：以编程方式更改内容的 FlowDirection
此示例演示如何以编程方式更改的 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 属性 <xref:System.Windows.Controls.FlowDocumentReader> 。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.Button>将创建两个元素，每个元素表示可能的值之一 <xref:System.Windows.FlowDirection> 。 单击某个按钮后，关联的属性值将应用于指定的的内容 <xref:System.Windows.Controls.FlowDocumentReader> `tf1` 。  属性值还会写入一个名为 <xref:System.Windows.Controls.TextBlock> 的 `txt1` 。  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a>示例  
 与上面定义的按钮单击相关联的事件将在 c # 代码隐藏文件中进行处理。  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
