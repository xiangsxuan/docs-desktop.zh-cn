---
title: 如何：为拖动的 GridView 列标题创建样式
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
ms.openlocfilehash: dbcdd38e0397b8e637aff962420a2959f33203df
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973559"
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a><span data-ttu-id="e9b52-102">如何：为拖动的 GridView 列标题创建样式</span><span class="sxs-lookup"><span data-stu-id="e9b52-102">How to: Create a Style for a Dragged GridView Column Header</span></span>
<span data-ttu-id="e9b52-103">此示例演示如何更改 <xref:System.Windows.Controls.GridViewColumnHeader> 用户更改列位置时所拖动的的外观。</span><span class="sxs-lookup"><span data-stu-id="e9b52-103">This example shows how to change the appearance of a dragged <xref:System.Windows.Controls.GridViewColumnHeader> when the user changes the position of a column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9b52-104">示例</span><span class="sxs-lookup"><span data-stu-id="e9b52-104">Example</span></span>  
 <span data-ttu-id="e9b52-105">当您将一个列标题拖到用于其查看模式的中的另一个位置时 <xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.GridView> ，该列将移动到新位置。</span><span class="sxs-lookup"><span data-stu-id="e9b52-105">When you drag a column header to another location in a <xref:System.Windows.Controls.ListView> that uses <xref:System.Windows.Controls.GridView> for its view mode, the column moves to the new position.</span></span> <span data-ttu-id="e9b52-106">在拖动列标题时，除了原始标题外，还会显示标头的浮动副本。</span><span class="sxs-lookup"><span data-stu-id="e9b52-106">While you are dragging the column header, a floating copy of the header appears in addition to the original header.</span></span> <span data-ttu-id="e9b52-107">中的列标题由 <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.GridViewColumnHeader> 对象表示。</span><span class="sxs-lookup"><span data-stu-id="e9b52-107">A column header in a <xref:System.Windows.Controls.GridView> is represented by a <xref:System.Windows.Controls.GridViewColumnHeader> object.</span></span>  
  
 <span data-ttu-id="e9b52-108">若要自定义浮动和原始标头的外观，可以设置 <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> 以修改 <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style> 。</span><span class="sxs-lookup"><span data-stu-id="e9b52-108">To customize the appearance of both the floating and original headers, you can set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to modify the <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>.</span></span> <span data-ttu-id="e9b52-109"><xref:System.Windows.Controls.ControlTemplate.Triggers%2A>当 <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> 属性值为 `true` ，且 <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> 属性值为时，将应用这些属性 <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating> 。</span><span class="sxs-lookup"><span data-stu-id="e9b52-109">These <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> are applied when the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value is `true` and the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property value is <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="e9b52-110">当用户按下鼠标按钮并在鼠标悬停在上时将其停留在上时 <xref:System.Windows.Controls.GridViewColumnHeader> ， <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> 属性值将更改为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="e9b52-110">When the user presses the mouse button and holds it down while the mouse pauses on the <xref:System.Windows.Controls.GridViewColumnHeader>, the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value changes to `true`.</span></span> <span data-ttu-id="e9b52-111">同样，当用户开始拖动操作时，属性将 <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> 更改为 <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating> 。</span><span class="sxs-lookup"><span data-stu-id="e9b52-111">Likewise, when the user begins the drag operation, the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property changes to <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="e9b52-112">下面的示例演示如何设置 <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> ，以便 <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.Background%2A> 在用户将列拖动到新位置时更改原始标题和浮点数的颜色。</span><span class="sxs-lookup"><span data-stu-id="e9b52-112">The following example shows how to set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to change the <xref:System.Windows.Controls.Control.Foreground%2A> and <xref:System.Windows.Controls.Control.Background%2A> colors of the original and floating headers when the user drags a column to a new position.</span></span>  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a><span data-ttu-id="e9b52-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9b52-113">See also</span></span>

- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="e9b52-114">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="e9b52-114">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="e9b52-115">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="e9b52-115">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="e9b52-116">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="e9b52-116">GridView Overview</span></span>](gridview-overview.md)
