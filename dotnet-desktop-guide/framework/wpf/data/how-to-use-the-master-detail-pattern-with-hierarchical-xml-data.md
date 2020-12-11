---
title: 如何：对分层 XML 数据使用主-从模式
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 0fe42d57fcaf4acee09340fdb3f5df73d7291566
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972085"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="01770-102">如何：对分层 XML 数据使用主-从模式</span><span class="sxs-lookup"><span data-stu-id="01770-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="01770-103">此示例演示如何用 XML 数据实现主-从方案。</span><span class="sxs-lookup"><span data-stu-id="01770-103">This example shows how to implement the master-detail scenario with XML data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01770-104">示例</span><span class="sxs-lookup"><span data-stu-id="01770-104">Example</span></span>  
 <span data-ttu-id="01770-105">此示例是 [将 Master-Detail 模式与分层数据结合使用](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)中所述的示例的 XML 数据版本。</span><span class="sxs-lookup"><span data-stu-id="01770-105">This example is the XML data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="01770-106">在此示例中，数据来自该文件 `League.xml` 。</span><span class="sxs-lookup"><span data-stu-id="01770-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="01770-107">请注意第三个 <xref:System.Windows.Controls.ListBox> 控件如何 <xref:System.Windows.Controls.ListBox> 通过绑定到其属性来跟踪第二个选定内容的更改 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> 。</span><span class="sxs-lookup"><span data-stu-id="01770-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="01770-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01770-108">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="01770-109">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="01770-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
