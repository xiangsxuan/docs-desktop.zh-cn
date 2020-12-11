---
title: 使用设计器将控件绑定到 BindingSource 组件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: ec4e556e855a2c86dc280e1c386e9dabc2319c57
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971320"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a>如何：使用设计器将 Windows 窗体控件与 BindingSource 组件进行绑定

将控件添加到窗体并确定应用程序的用户界面后，可以将控件绑定到数据源，以便在运行时，用户可以更改和保存与应用程序相关的数据。

 使用 <xref:System.Windows.Forms.BindingSource> 控件作为窗体上的控件与数据源之间的桥梁，可以很容易地在 Windows 窗体中绑定控件或一系列控件。

 窗体上的一个或多个控件可以绑定到数据;在下面的过程中， <xref:System.Windows.Forms.TextBox> 控件绑定到数据源。

 若要完成该过程，假设您将绑定到从数据库派生的数据源。 有关从其他数据存储创建数据源的详细信息，请参阅 [添加新数据源](/visualstudio/data-tools/add-new-data-sources)。

## <a name="to-bind-a-control-at-design-time"></a>在设计时绑定控件

1. 将 <xref:System.Windows.Forms.TextBox> 控件拖动到窗体上。

2. 在 " **属性** " 窗口中：

    1. 展开 **(databinding)** "节点。

    2. 单击属性旁边的箭头 <xref:System.Windows.Forms.TextBox.Text%2A> 。

         " **数据源** UI 类型编辑器" 随即打开。

         如果以前已经为项目或窗体配置了数据源，则将显示该数据源。

3. 单击“添加项目数据源”以连接到数据并创建一个数据源。

4. 在“数据源配置向导”欢迎页上，单击“下一步”。

5. 在 " **选择数据源类型** " 页上，选择 " **数据库**"。

6. 在 " **选择你的数据连接** " 页上，从可用连接的列表中选择一个数据连接。 如果所需的数据连接不可用，请选择 " **新建连接** " 以创建新的数据连接。

7. 选择 **"是，保存连接"，** 将连接字符串保存到应用程序配置文件中。

8. 选择要放置到应用程序中的数据库对象。 在这种情况下，请在表中选择要显示的字段 <xref:System.Windows.Forms.TextBox> 。

9. 如果愿意，可以替换默认的数据集名称。

10. 单击“完成”。

11. 在 " **属性** " 窗口中，再次单击属性旁边的箭头 <xref:System.Windows.Forms.TextBox.Text%2A> 。 在 " **数据源** UI 类型编辑器" 中，选择要绑定到的字段的名称 <xref:System.Windows.Forms.TextBox> 。

     数据 **源** UI 类型编辑器将关闭，并将 <xref:System.Windows.Forms.BindingSource> 特定于该数据连接的表适配器添加到窗体中。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [添加新数据源](/visualstudio/data-tools/add-new-data-sources)
- [“数据源”窗口](/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))
