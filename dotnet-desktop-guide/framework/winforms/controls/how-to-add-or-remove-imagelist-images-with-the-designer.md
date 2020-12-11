---
title: 如何：使用设计器添加或移除 ImageList 图像
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: cdc7b563a0ee4f8779b99b4e9a6786e78f8d500f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971909"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a>如何：使用设计器添加或移除 ImageList 图像

可以 <xref:System.Windows.Forms.ImageList> 通过多种不同方式向组件添加图像。 你可以通过使用与关联的智能标记来非常快速地添加图像 <xref:System.Windows.Forms.ImageList> ，或者，如果你在上设置多个其他属性 <xref:System.Windows.Forms.ImageList> ，则可以更方便地使用属性窗口添加图像。 你还可以通过使用代码来添加映像。 有关如何添加包含代码的图像的详细信息，请参阅 [如何：在 Windows 窗体 ImageList 组件中添加或删除图像](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)。 通常，在 <xref:System.Windows.Forms.ImageList> 组件与控件关联之前，使用图像填充组件，但这不是必需的。

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a>使用属性窗口添加或删除映像

1. 选择 <xref:System.Windows.Forms.ImageList> 组件，或将其添加到窗体。

2. 在属性窗口中，单击省略号按钮 (![ Visual Studio 属性窗口中的省略号按钮 ( ") "。在 ](./media/visual-studio-ellipsis-button.png) 属性旁) 。 <xref:System.Windows.Forms.ImageList.Images%2A>

3. 在 **图像集合编辑器** 中，单击 " **添加** " 或 " **删除** " 以添加或删除列表中的映像。

### <a name="to-add-or-remove-images-using-the-smart-tag"></a>使用智能标记添加或删除图像

1. 选择 <xref:System.Windows.Forms.ImageList> 组件，或将其添加到窗体。

2. 单击设计器操作标志符号 (![小号黑色箭头](./media/designer-actions-glyph.gif))

3. 在 " **ImageList 任务** " 对话框中，选择 " **选择图像**"。

4. 在 **图像集合编辑器** 中，单击 " **添加** " 或 " **删除** " 以添加或删除列表中的映像。

## <a name="see-also"></a>另请参阅

- [图像、位图和图元文件](../advanced/images-bitmaps-and-metafiles.md)
- [演练：使用设计操作执行常规任务](perform-common-tasks-design-actions.md)
- [ImageList 组件](imagelist-component-windows-forms.md)
