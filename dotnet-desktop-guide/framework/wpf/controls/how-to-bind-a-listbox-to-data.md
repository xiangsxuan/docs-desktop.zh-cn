---
title: 如何：将 ListBox 绑定到数据
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 4dea53a524247d18628b3e7e7b2c06906dced53d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973998"
---
# <a name="how-to-bind-a-listbox-to-data"></a><span data-ttu-id="448b6-102">如何：将 ListBox 绑定到数据</span><span class="sxs-lookup"><span data-stu-id="448b6-102">How to: Bind a ListBox to Data</span></span>
<span data-ttu-id="448b6-103">应用程序开发人员可以创建 <xref:System.Windows.Controls.ListBox> 控件，而无需单独指定每个控件的内容 <xref:System.Windows.Controls.ListBoxItem> 。</span><span class="sxs-lookup"><span data-stu-id="448b6-103">An application developer can create <xref:System.Windows.Controls.ListBox> controls without specifying the contents of each <xref:System.Windows.Controls.ListBoxItem> separately.</span></span> <span data-ttu-id="448b6-104">您可以使用数据绑定将数据绑定到各个项。</span><span class="sxs-lookup"><span data-stu-id="448b6-104">You can use data binding to bind data to the individual items.</span></span>  
  
 <span data-ttu-id="448b6-105">下面的示例演示如何创建一个 <xref:System.Windows.Controls.ListBox> ，它 <xref:System.Windows.Controls.ListBoxItem> 通过数据绑定将元素填充到称为 *颜色* 的数据源。</span><span class="sxs-lookup"><span data-stu-id="448b6-105">The following example shows how to create a <xref:System.Windows.Controls.ListBox> that populates the <xref:System.Windows.Controls.ListBoxItem> elements by data binding to a data source called *Colors*.</span></span> <span data-ttu-id="448b6-106">在这种情况下，无需使用 <xref:System.Windows.Controls.ListBoxItem> 标记来指定每个项的内容。</span><span class="sxs-lookup"><span data-stu-id="448b6-106">In this case it is not necessary to use <xref:System.Windows.Controls.ListBoxItem> tags to specify the content of each item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="448b6-107">示例</span><span class="sxs-lookup"><span data-stu-id="448b6-107">Example</span></span>  
 [!code-xaml[ListBoxEvent#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="448b6-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="448b6-108">See also</span></span>

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.Controls.ListBoxItem>
- [<span data-ttu-id="448b6-109">控件</span><span class="sxs-lookup"><span data-stu-id="448b6-109">Controls</span></span>](../advanced/optimizing-performance-controls.md)
