---
title: 如何：使用 CheckBox 创建 ListViewItem
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
ms.openlocfilehash: b09d5ad11b0961febf524cec1e19cb1e59832e44
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973723"
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a><span data-ttu-id="2f03f-102">如何：使用 CheckBox 创建 ListViewItem</span><span class="sxs-lookup"><span data-stu-id="2f03f-102">How to: Create ListViewItems with a CheckBox</span></span>
<span data-ttu-id="2f03f-103">此示例演示如何 <xref:System.Windows.Controls.CheckBox> 在使用的控件中显示一列控件 <xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.GridView> 。</span><span class="sxs-lookup"><span data-stu-id="2f03f-103">This example shows how to display a column of <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f03f-104">示例</span><span class="sxs-lookup"><span data-stu-id="2f03f-104">Example</span></span>  
 <span data-ttu-id="2f03f-105">若要创建包含中的 <xref:System.Windows.Controls.CheckBox> 控件的列 <xref:System.Windows.Controls.ListView> ，请创建一个 <xref:System.Windows.DataTemplate> 包含的 <xref:System.Windows.Controls.CheckBox> 。</span><span class="sxs-lookup"><span data-stu-id="2f03f-105">To create a column that contains <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView>, create a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="2f03f-106">然后将 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> 的设置 <xref:System.Windows.Controls.GridViewColumn> 为 <xref:System.Windows.DataTemplate> 。</span><span class="sxs-lookup"><span data-stu-id="2f03f-106">Then set the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> of a <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 <span data-ttu-id="2f03f-107">下面的示例演示一个 <xref:System.Windows.DataTemplate> 包含的 <xref:System.Windows.Controls.CheckBox> 。</span><span class="sxs-lookup"><span data-stu-id="2f03f-107">The following example shows a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="2f03f-108">该示例将 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 的属性绑定 <xref:System.Windows.Controls.CheckBox> 到 <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> 包含它的的属性值 <xref:System.Windows.Controls.ListViewItem> 。</span><span class="sxs-lookup"><span data-stu-id="2f03f-108">The example binds the <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> property of the <xref:System.Windows.Controls.CheckBox> to the <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> property value of the <xref:System.Windows.Controls.ListViewItem> that contains it.</span></span> <span data-ttu-id="2f03f-109">因此，在 <xref:System.Windows.Controls.ListViewItem> 选择包含的时 <xref:System.Windows.Controls.CheckBox> ，将 <xref:System.Windows.Controls.CheckBox> 选中。</span><span class="sxs-lookup"><span data-stu-id="2f03f-109">Therefore, when the <xref:System.Windows.Controls.ListViewItem> that contains the <xref:System.Windows.Controls.CheckBox> is selected, the <xref:System.Windows.Controls.CheckBox> is checked.</span></span>  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 <span data-ttu-id="2f03f-110">下面的示例演示如何创建一个 <xref:System.Windows.Controls.CheckBox> 控件列。</span><span class="sxs-lookup"><span data-stu-id="2f03f-110">The following example shows how to create a column of <xref:System.Windows.Controls.CheckBox> controls.</span></span> <span data-ttu-id="2f03f-111">为了使列成为，此示例将 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> 的属性设置 <xref:System.Windows.Controls.GridViewColumn> 为 <xref:System.Windows.DataTemplate> 。</span><span class="sxs-lookup"><span data-stu-id="2f03f-111">To make the column, the example sets the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> property of the <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a><span data-ttu-id="2f03f-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f03f-112">See also</span></span>

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="2f03f-113">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="2f03f-113">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="2f03f-114">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="2f03f-114">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="2f03f-115">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="2f03f-115">GridView Overview</span></span>](gridview-overview.md)
