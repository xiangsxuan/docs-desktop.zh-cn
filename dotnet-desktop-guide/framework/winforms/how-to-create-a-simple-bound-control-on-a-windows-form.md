---
title: 如何：在 Windows 窗体上创建简单绑定控件
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: bb7554831ab3698333850b71c42a5343ceb7d682
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970264"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a>如何：在 Windows 窗体上创建简单绑定控件

使用 *简单绑定*，可以在控件中显示单个数据元素，例如数据集表中的列值。 可以简单地将控件的任何属性绑定到数据值。

## <a name="to-simple-bind-a-control"></a>简单-绑定控件

1. 连接到数据源。 有关详细信息，请参阅 [连接到数据源](/dotnet/framework/data/adonet/connecting-to-a-data-source)。

2. 在 Visual Studio 中，选择窗体上的控件并显示 " **属性** " 窗口。

3. 展开 " **(databinding)** " 属性。

     最常绑定的属性将显示在 **(databinding)** 属性下。 例如，在大多数控件中， **Text** 属性是最常绑定的。

4. 如果要绑定的属性不是某个常用的绑定属性，请单击 **省略号** 按钮 (![ Visual Studio 属性窗口中的省略号按钮 ( ... ) 。 ](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)) 在 " **(高级)** " 框中显示 " **格式设置和高级绑定** " 对话框，其中包含该控件的属性的完整列表。

5. 选择要绑定的属性，然后单击 " **绑定**" 下的下拉箭头。

     此时将显示可用数据源的列表。

6. 展开要绑定到的数据源，直到找到所需的单个数据元素。 例如，如果你正在绑定到数据集表中的列值，请展开该数据集的名称，然后展开表名以显示列名。

7. 单击要绑定到的元素的名称。

8. 如果使用的是 " **格式设置和高级绑定** " 对话框，请单击 **"确定"** 以返回到 " **属性** " 窗口。

9. 如果要绑定控件的其他属性，请重复步骤3到步骤7。

    > [!NOTE]
    > 由于简单绑定控件只显示单个数据元素，因此在 Windows 窗体中包含具有简单绑定控件的导航逻辑非常典型。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Binding>
- [Windows 窗体数据绑定](windows-forms-data-binding.md)
- [数据绑定和 Windows 窗体](data-binding-and-windows-forms.md)
