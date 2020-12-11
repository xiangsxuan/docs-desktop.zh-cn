---
title: 如何：使用 Modifiers 和 GenerateMember 属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
ms.openlocfilehash: 3fbaaae53aa60f6356c3a8daa0513de86ef2dacb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971389"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a>如何：使用 Modifiers 和 GenerateMember 属性

在 Windows 窗体中放置组件时，设计环境会提供两个属性： `GenerateMember` 和 `Modifiers` 。 `GenerateMember`属性指定 Windows 窗体设计器为组件生成成员变量的时间。 `Modifiers`属性是分配给该成员变量的访问修饰符。 如果属性的值 `GenerateMember` 为，则 `false` 属性的值 `Modifiers` 不起作用。

## <a name="specify-whether-a-component-is-a-member-of-the-form"></a>指定组件是否为窗体的成员

1. 在 Visual Studio 的 "Windows 窗体设计器中，打开窗体。

2. 打开 " **工具箱**"，然后在窗体上放置三个 <xref:System.Windows.Forms.Button> 控件。

3. `GenerateMember` `Modifiers` 根据下表设置每个控件的和属性 <xref:System.Windows.Forms.Button> 。

    |按钮名称|GenerateMember 值|修饰符值|
    |-----------------|--------------------------|---------------------|
    |`button1`|`true`|`private`|
    |`button2`|`true`|`protected`|
    |`button3`|`false`|没有变化|

4. 生成解决方案。

5. 在“解决方案资源管理器”中，单击“显示所有文件”按钮。

6. 打开 " **form1** " 节点，并在 **代码编辑器** 中打开 "Form1.Designer.cs **" 或 "**  " 文件。 此文件包含 Windows 窗体设计器发出的代码。

7. 找到三个按钮的声明。 下面的代码示例演示了和属性指定的 `GenerateMember` 差异 `Modifiers` 。

     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]

     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]

> [!NOTE]
> 默认情况下，Windows 窗体设计器将 `private` `Friend` Visual Basic) 修饰符中的 (分配给容器控件，如 <xref:System.Windows.Forms.Panel> 。 如果你的基础 <xref:System.Windows.Forms.UserControl> 或 <xref:System.Windows.Forms.Form> 具有容器控件，它将不接受继承的控件和窗体中的新子级。 解决方法是将基容器控件的修饰符更改为 `protected` 或 `public` 。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Button>
- [Windows 窗体可视化继承](windows-forms-visual-inheritance.md)
- [演练：演示可视化继承](walkthrough-demonstrating-visual-inheritance.md)
- [如何：继承 Windows 窗体](how-to-inherit-windows-forms.md)
