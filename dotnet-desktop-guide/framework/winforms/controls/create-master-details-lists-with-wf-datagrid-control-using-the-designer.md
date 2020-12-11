---
title: 使用设计器通过 DataGrid 控件创建 Master-Details 列表
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: a60cecf4c4344ab5aca18f76a59223c02d58a062
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970164"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>如何：通过使用设计器使用 Windows 窗体 DataGrid 控件创建主/详细信息列表

> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。

 如果您 <xref:System.Data.DataSet> 包含一系列相关的表，则可以使用两个 <xref:System.Windows.Forms.DataGrid> 控件以主-详细信息格式显示数据。 将一个 <xref:System.Windows.Forms.DataGrid> 网格指定为主网格，并将第二个指定为详细信息网格。 当你在 "主列表" 中选择条目时，所有相关的子项都显示在 "详细信息" 列表中。 例如，如果您 <xref:System.Data.DataSet> 包含 customers 表和相关订单表，则您可以将 customers 表指定为主网格，将 Orders 表指定为详细信息网格。 从主网格中选择客户时，"订单" 表中与该客户关联的所有订单都将显示在 "详细信息" 网格中。

 下面的过程需要一个 **Windows 应用程序** 项目 (**文件**"  >  **新建**  >  **项目**" "  >  **Visual c #** " 或 " **Visual Basic**  >  **经典桌面**  >  **Windows 窗体应用程序**) "。

## <a name="to-create-a-master-details-list-in-the-designer"></a>在设计器中创建主-详细信息列表

1. 向窗体添加两个 <xref:System.Windows.Forms.DataGrid> 控件。 有关详细信息，请参阅 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。 在 Visual Studio 2005 中， <xref:System.Windows.Forms.DataGrid> 默认情况下控件不在 **工具箱** 中。 有关详细信息，请参阅 [如何：向工具箱添加项](/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))。

    > [!NOTE]
    > 以下步骤不适用于 Visual Studio 2005，后者使用 " **数据源** " 窗口进行设计时数据绑定。 有关详细信息，请参阅 [在 Visual Studio 中将控件绑定到数据](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) 和 [如何：在 Windows 窗体应用程序中显示相关数据](/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))。

2. 将两个或多个表从 **服务器资源管理器** 拖动到窗体。

3. 从 " **数据** " 菜单中，选择 " **生成数据集**"。

4. 使用 "XML 设计器" 设置表之间的关系。 有关详细信息，请参阅 MSDN 上的 "如何：在 XML 架构和数据集创建一对多关系"。

5. 通过从 "**文件**" 菜单中选择 "**全部保存**" 来保存关系。

6. 配置 <xref:System.Windows.Forms.DataGrid> 要指定主网格的控件，如下所示：

    1. <xref:System.Data.DataSet>从属性的下拉列表中选择 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 。

    2. 选择主表 (例如，从属性的下拉列表中选择 "Customers" ) <xref:System.Windows.Forms.DataGrid.DataMember%2A> 。

7. 配置 <xref:System.Windows.Forms.DataGrid> 要指定详细信息网格的控件，如下所示：

    1. <xref:System.Data.DataSet>从属性的下拉列表中选择 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 。

    2. 选择关系 (例如，从属性的下拉列表中选择 "CustOrd" ) 主表和详细信息表之间的 "" <xref:System.Windows.Forms.DataGrid.DataMember%2A> 。 若要查看关系，请通过单击下拉列表中的 "主表" 旁边的加号 () 符号，展开该节点 **+** 。

## <a name="see-also"></a>另请参阅

- [DataGrid 控件](datagrid-control-windows-forms.md)
- [DataGrid 控件概述](datagrid-control-overview-windows-forms.md)
- [如何：将 Windows 窗体 DataGrid 控件绑定到数据源](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [在 Visual Studio 中将控件绑定到数据](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
