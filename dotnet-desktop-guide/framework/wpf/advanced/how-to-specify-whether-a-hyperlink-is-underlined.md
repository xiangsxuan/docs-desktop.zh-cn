---
title: 如何：指定是否为超链接添加下划线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
ms.openlocfilehash: 5718912e24a0697f209669b0ab4e7f4df1765ed3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970593"
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a>如何：指定是否为超链接添加下划线
<xref:System.Windows.Documents.Hyperlink>对象是一个内联级别的流内容元素，它允许您在流内容中承载超链接。 默认情况下， <xref:System.Windows.Documents.Hyperlink> 使用 <xref:System.Windows.TextDecoration> 对象显示下划线。 <xref:System.Windows.TextDecoration> 实例化对象的性能可能会很高，尤其是在有多个对象的情况下 <xref:System.Windows.Documents.Hyperlink> 。 如果您广泛使用了 <xref:System.Windows.Documents.Hyperlink> 元素，则可能需要考虑仅在触发事件（例如事件）时显示下划线 <xref:System.Windows.ContentElement.MouseEnter> 。  
  
 在下面的示例中，"我的 MSN" 链接的下划线是动态的，也就是说，它仅在触发事件时才会出现 <xref:System.Windows.ContentElement.MouseEnter> 。  
  
  ![显示 TextDecoration 的超链接](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)  

## <a name="example"></a>示例  
 以下标记示例显示了 <xref:System.Windows.Documents.Hyperlink> 使用和不带下划线定义的：  
  
 [!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 下面的代码示例演示如何为事件创建下划线 <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.ContentElement.MouseEnter> ，并在事件上删除它 <xref:System.Windows.ContentElement.MouseLeave> 。  
  
 [!code-csharp[Performance#PerformanceSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [优化 WPF 应用程序性能](optimizing-wpf-application-performance.md)
- [创建文本修饰](how-to-create-a-text-decoration.md)
