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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970593"
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a><span data-ttu-id="99b3e-102">如何：指定是否为超链接添加下划线</span><span class="sxs-lookup"><span data-stu-id="99b3e-102">How to: Specify Whether a Hyperlink is Underlined</span></span>
<span data-ttu-id="99b3e-103"><xref:System.Windows.Documents.Hyperlink>对象是一个内联级别的流内容元素，它允许您在流内容中承载超链接。</span><span class="sxs-lookup"><span data-stu-id="99b3e-103">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="99b3e-104">默认情况下， <xref:System.Windows.Documents.Hyperlink> 使用 <xref:System.Windows.TextDecoration> 对象显示下划线。</span><span class="sxs-lookup"><span data-stu-id="99b3e-104">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="99b3e-105"><xref:System.Windows.TextDecoration> 实例化对象的性能可能会很高，尤其是在有多个对象的情况下 <xref:System.Windows.Documents.Hyperlink> 。</span><span class="sxs-lookup"><span data-stu-id="99b3e-105"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="99b3e-106">如果您广泛使用了 <xref:System.Windows.Documents.Hyperlink> 元素，则可能需要考虑仅在触发事件（例如事件）时显示下划线 <xref:System.Windows.ContentElement.MouseEnter> 。</span><span class="sxs-lookup"><span data-stu-id="99b3e-106">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="99b3e-107">在下面的示例中，"我的 MSN" 链接的下划线是动态的，也就是说，它仅在触发事件时才会出现 <xref:System.Windows.ContentElement.MouseEnter> 。</span><span class="sxs-lookup"><span data-stu-id="99b3e-107">In the following example, the underline for the "My MSN" link is dynamic, that is, it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
  ![显示 TextDecoration 的超链接](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)  

## <a name="example"></a><span data-ttu-id="99b3e-109">示例</span><span class="sxs-lookup"><span data-stu-id="99b3e-109">Example</span></span>  
 <span data-ttu-id="99b3e-110">以下标记示例显示了 <xref:System.Windows.Documents.Hyperlink> 使用和不带下划线定义的：</span><span class="sxs-lookup"><span data-stu-id="99b3e-110">The following markup sample shows a <xref:System.Windows.Documents.Hyperlink> defined with and without an underline:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 <span data-ttu-id="99b3e-111">下面的代码示例演示如何为事件创建下划线 <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.ContentElement.MouseEnter> ，并在事件上删除它 <xref:System.Windows.ContentElement.MouseLeave> 。</span><span class="sxs-lookup"><span data-stu-id="99b3e-111">The following code sample shows how to create an underline for the <xref:System.Windows.Documents.Hyperlink> on the <xref:System.Windows.ContentElement.MouseEnter> event, and remove it on the <xref:System.Windows.ContentElement.MouseLeave> event.</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a><span data-ttu-id="99b3e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="99b3e-112">See also</span></span>

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="99b3e-113">优化 WPF 应用程序性能</span><span class="sxs-lookup"><span data-stu-id="99b3e-113">Optimizing WPF Application Performance</span></span>](optimizing-wpf-application-performance.md)
- [<span data-ttu-id="99b3e-114">创建文本修饰</span><span class="sxs-lookup"><span data-stu-id="99b3e-114">Create a Text Decoration</span></span>](how-to-create-a-text-decoration.md)
