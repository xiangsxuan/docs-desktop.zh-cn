---
title: 如何：为拖动的 GridView 列标题创建样式
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
ms.openlocfilehash: dbcdd38e0397b8e637aff962420a2959f33203df
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973559"
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a>如何：为拖动的 GridView 列标题创建样式
此示例演示如何更改 <xref:System.Windows.Controls.GridViewColumnHeader> 用户更改列位置时所拖动的的外观。  
  
## <a name="example"></a>示例  
 当您将一个列标题拖到用于其查看模式的中的另一个位置时 <xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.GridView> ，该列将移动到新位置。 在拖动列标题时，除了原始标题外，还会显示标头的浮动副本。 中的列标题由 <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.GridViewColumnHeader> 对象表示。  
  
 若要自定义浮动和原始标头的外观，可以设置 <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> 以修改 <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style> 。 <xref:System.Windows.Controls.ControlTemplate.Triggers%2A>当 <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> 属性值为 `true` ，且 <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> 属性值为时，将应用这些属性 <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating> 。  
  
 当用户按下鼠标按钮并在鼠标悬停在上时将其停留在上时 <xref:System.Windows.Controls.GridViewColumnHeader> ， <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> 属性值将更改为 `true` 。 同样，当用户开始拖动操作时，属性将 <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> 更改为 <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating> 。  
  
 下面的示例演示如何设置 <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> ，以便 <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.Background%2A> 在用户将列拖动到新位置时更改原始标题和浮点数的颜色。  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [操作指南主题](listview-how-to-topics.md)
- [ListView 概述](listview-overview.md)
- [GridView 概述](gridview-overview.md)
