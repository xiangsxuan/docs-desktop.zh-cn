---
title: 如何：创建绑定控件并设置显示数据的格式
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: e1448e0dcb80a7ac7ab0199b14957bddec27c133
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970266"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a>如何：创建绑定控件并设置显示数据的格式

使用 Windows 窗体数据绑定，可以通过使用 " **格式设置和高级绑定** " 对话框来设置数据绑定控件中显示的数据的格式。

## <a name="to-bind-a-control-and-format-the-displayed-data"></a>绑定控件并设置显示的数据的格式

1. 连接到数据源。 有关详细信息，请参阅 [连接到数据源](/dotnet/framework/data/adonet/connecting-to-a-data-source)。

2. 在 Visual Studio 中，选择窗体上的控件，然后打开 " **属性** " 窗口。

3. 展开 " **(** databinding") 属性，然后在 " **(高级)** " 框中，单击 "Visual Studio ( ( 中省略号按钮 ) 省略号按钮属性窗口"， ![ ](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png) 以显示 " **格式设置和高级绑定** " 对话框，该对话框具有该控件的完整属性列表。

4. 选择要绑定的属性，然后选择 " **绑定** " 箭头。

     此时将显示可用数据源的列表。

5. 展开要绑定到的数据源，直到找到所需的单个数据元素。

     例如，如果你正在绑定到数据集表中的列值，请展开该数据集的名称，然后展开表名以显示列名。

6. 选择要绑定到的元素的名称。

7. 在 " **格式类型** " 框中，选择要应用于控件中显示的数据的格式。

     在任何情况下，如果数据源包含 <xref:System.DBNull>，都可以指定控件中显示的值。 否则，选项会略有不同，具体取决于你选择的格式类型。 下表显示了格式类型和选项。

    |格式类型|格式选项|
    |-----------------|-----------------------|
    |无格式|无选项。|
    |Numeric|使用 " **小数位数** " up-down 控件指定小数位数。|
    |货币|使用 " **小数位数** " up-down 控件指定小数位数。|
    |DateTime|通过选择 " **类型** 选择" 框中的一个项来选择显示日期和时间的方式。|
    |科学记数|使用 " **小数位数** " up-down 控件指定小数位数。|
    |自定义|指定一个自定义格式字符串用法。<br /><br /> 有关详细信息，请参阅[类型格式设置](/dotnet/standard/base-types/formatting-types)。 **注意：**  不保证自定义格式字符串在数据源和绑定控件之间成功往返。 请改为处理该绑定的 <xref:System.Windows.Forms.Binding.Parse> 或 <xref:System.Windows.Forms.Binding.Format> 事件，并在事件处理代码中应用自定义格式设置。|

8. 选择 **"确定"** 以关闭 " **格式设置和高级绑定** " 对话框并返回到属性窗口。

## <a name="see-also"></a>另请参阅

- [如何：在 Windows 窗体上创建简单绑定控件](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [Windows 窗体中的用户输入验证](user-input-validation-in-windows-forms.md)
- [Windows 窗体数据绑定](windows-forms-data-binding.md)
