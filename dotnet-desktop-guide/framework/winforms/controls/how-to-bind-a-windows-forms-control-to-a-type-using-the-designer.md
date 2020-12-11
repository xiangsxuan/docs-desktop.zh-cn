---
title: 使用设计器将控件绑定到类型
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: 2257489e123ceeea819ad3538952db51b726c7e5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971254"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a>如何：使用设计器将 Windows 窗体控件绑定到类型

在生成与数据交互的控件时，有时需要将控件绑定到类型而非对象。 当数据可能不可用，但仍然希望数据绑定控件显示类型的公共接口中的信息时，通常需要在设计时将控件绑定到类型。 下面的过程演示如何创建一个 <xref:System.Windows.Forms.BindingSource> 绑定到类型的新，然后将该类型的一个属性绑定到的 <xref:System.Windows.Forms.TextBox.Text%2A> 属性 <xref:System.Windows.Forms.TextBox> 。

### <a name="to-bind-the-bindingsource-to-a-type"></a>将 BindingSource 绑定到类型

1. 创建 Windows 窗体 **项目 ("**  >  **新建**  >  **项目**" "  >  **Visual c #** " 或 " **Visual Basic**  >  **经典桌面**  >  **Windows 窗体应用程序**) "。

2. 在 " **设计** " 视图中，将 <xref:System.Windows.Forms.BindingSource> 组件拖到窗体上。

3. 在 " **属性** " 窗口中，单击属性的箭头 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 。

4. 在“DataSource UI 类型编辑器”中，单击“添加项目数据源”。

5. 在“选择数据源类型”页上，选择“对象”，并单击“下一步”。

6. 选择要绑定到的类型：

    - 如果要绑定到的类型位于当前项目，或者包含该类型的程序集已经作为引用添加，请展开节点以找到所需类型，然后选择它。

      \- 或 -

    - 如果要绑定到的类型位于另一个程序集中，当前不在引用列表中，请单击 " **添加引用**"，然后单击 " **项目** " 选项卡。选择包含所需业务对象的项目，然后单击 **"确定"**。 此项目将显示在程序集列表中，因此可以展开节点以查找所需类型，然后选择它。

      > [!NOTE]
      > 如果要绑定到框架或 Microsoft 程序集中的类型，请清除“隐藏以 Microsoft 或 System 开头的程序集”复选框。

7. 单击“下一步”  ，然后单击“完成”  。

### <a name="to-bind-the-control-to-the-bindingsource"></a>将控件绑定到 BindingSource

1. 在窗体上添加一个 <xref:System.Windows.Forms.TextBox> 控件。

2. 在“属性”窗口中，展开“(DataBindings)”节点。

3. 单击属性旁边的箭头 <xref:System.Windows.Forms.TextBox.Text%2A> 。

4. 在 " **数据源 UI 类型编辑器**" 中，展开 <xref:System.Windows.Forms.BindingSource> 之前添加的节点，并选择要绑定到的属性的绑定类型的属性 <xref:System.Windows.Forms.TextBox.Text%2A> <xref:System.Windows.Forms.TextBox> 。

## <a name="see-also"></a>另请参阅

- [BindingSource 组件](bindingsource-component.md)
- [如何：将 Windows 窗体控件绑定到类型](how-to-bind-a-windows-forms-control-to-a-type.md)
- [在 Visual Studio 中将控件绑定到数据](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
