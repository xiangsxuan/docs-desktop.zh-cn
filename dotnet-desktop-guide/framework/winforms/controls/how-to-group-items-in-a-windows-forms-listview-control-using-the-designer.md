---
title: 使用设计器在 ListView 控件中对项进行分组
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 935d8d75517e1028e686ca229f6ada656f58b01e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972020"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>如何：使用设计器对 Windows 窗体 ListView 控件中的项进行分组

控件的分组功能 <xref:System.Windows.Forms.ListView> 使你能够以组的形式显示相关项集。 这些组按包含组标题的水平组标头在屏幕上进行分隔。 你可以使用 <xref:System.Windows.Forms.ListView> 组，通过按字母顺序、日期或任何其他逻辑分组对项进行分组来更轻松地导航大型列表。 下图显示了一些分组项：

![数字分为奇数甚至是组。](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含控件的窗体 <xref:System.Windows.Forms.ListView> 。 有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

若要启用分组，必须先 <xref:System.Windows.Forms.ListViewGroup> 在设计器中或以编程方式创建一个或多个对象。 定义组后，可以为其分配项。

## <a name="to-add-or-remove-groups-in-the-designer"></a>在设计器中添加或删除组

1. 在 "**属性**" 窗口中，**单击省略号按钮 (省略号** ![ 按钮 ( ") " 属性窗口中的 "Visual) Studio"。 ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.ListView.Groups%2A>

     此时将显示 " **ListViewGroup 集合编辑器** "。

2. 若要添加组，请单击 " **添加** " 按钮。 然后，可以设置新组的属性，如 <xref:System.Windows.Forms.ListViewGroup.Header%2A> 和 <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> 属性。 若要删除某个组，请选择该组，然后单击 " **删除** " 按钮。

## <a name="to-assign-items-to-groups-in-the-designer"></a>在设计器中向组分配项

1. 在 "**属性**" 窗口中，**单击省略号按钮 (省略号** ![ 按钮 ( ") " 属性窗口中的 "Visual) Studio"。 ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.ListView.Items%2A>

     此时将显示 " **ListViewItem 集合编辑器** "。

2. 若要添加新项，请单击 " **添加** " 按钮。 然后，可以设置新项的属性，如 <xref:System.Windows.Forms.ListViewItem.Text%2A> 和 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 属性。

3. 选择该 <xref:System.Windows.Forms.ListViewItem.Group%2A> 属性，然后从下拉列表中选择一个组。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView 控件](listview-control-windows-forms.md)
- [ListView 控件概述](listview-control-overview-windows-forms.md)
- [如何：使用 Windows 窗体 ListView 控件添加和移除项](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
