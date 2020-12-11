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
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="2e50f-102">如何：使用 Modifiers 和 GenerateMember 属性</span><span class="sxs-lookup"><span data-stu-id="2e50f-102">How to: Use the Modifiers and GenerateMember Properties</span></span>

<span data-ttu-id="2e50f-103">在 Windows 窗体中放置组件时，设计环境会提供两个属性： `GenerateMember` 和 `Modifiers` 。</span><span class="sxs-lookup"><span data-stu-id="2e50f-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="2e50f-104">`GenerateMember`属性指定 Windows 窗体设计器为组件生成成员变量的时间。</span><span class="sxs-lookup"><span data-stu-id="2e50f-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="2e50f-105">`Modifiers`属性是分配给该成员变量的访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="2e50f-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="2e50f-106">如果属性的值 `GenerateMember` 为，则 `false` 属性的值 `Modifiers` 不起作用。</span><span class="sxs-lookup"><span data-stu-id="2e50f-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>

## <a name="specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="2e50f-107">指定组件是否为窗体的成员</span><span class="sxs-lookup"><span data-stu-id="2e50f-107">Specify whether a component is a member of the form</span></span>

1. <span data-ttu-id="2e50f-108">在 Visual Studio 的 "Windows 窗体设计器中，打开窗体。</span><span class="sxs-lookup"><span data-stu-id="2e50f-108">In Visual Studio, in the Windows Forms Designer, open your form.</span></span>

2. <span data-ttu-id="2e50f-109">打开 " **工具箱**"，然后在窗体上放置三个 <xref:System.Windows.Forms.Button> 控件。</span><span class="sxs-lookup"><span data-stu-id="2e50f-109">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>

3. <span data-ttu-id="2e50f-110">`GenerateMember` `Modifiers` 根据下表设置每个控件的和属性 <xref:System.Windows.Forms.Button> 。</span><span class="sxs-lookup"><span data-stu-id="2e50f-110">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>

    |<span data-ttu-id="2e50f-111">按钮名称</span><span class="sxs-lookup"><span data-stu-id="2e50f-111">Button name</span></span>|<span data-ttu-id="2e50f-112">GenerateMember 值</span><span class="sxs-lookup"><span data-stu-id="2e50f-112">GenerateMember value</span></span>|<span data-ttu-id="2e50f-113">修饰符值</span><span class="sxs-lookup"><span data-stu-id="2e50f-113">Modifiers value</span></span>|
    |-----------------|--------------------------|---------------------|
    |`button1`|`true`|`private`|
    |`button2`|`true`|`protected`|
    |`button3`|`false`|<span data-ttu-id="2e50f-114">没有变化</span><span class="sxs-lookup"><span data-stu-id="2e50f-114">No change</span></span>|

4. <span data-ttu-id="2e50f-115">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="2e50f-115">Build the solution.</span></span>

5. <span data-ttu-id="2e50f-116">在“解决方案资源管理器”中，单击“显示所有文件”按钮。</span><span class="sxs-lookup"><span data-stu-id="2e50f-116">In **Solution Explorer**, click the **Show All Files** button.</span></span>

6. <span data-ttu-id="2e50f-117">打开 " **form1** " 节点，并在 **代码编辑器** 中打开 "Form1.Designer.cs **" 或 "**  " 文件。</span><span class="sxs-lookup"><span data-stu-id="2e50f-117">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="2e50f-118">此文件包含 Windows 窗体设计器发出的代码。</span><span class="sxs-lookup"><span data-stu-id="2e50f-118">This file contains the code emitted by the Windows Forms Designer.</span></span>

7. <span data-ttu-id="2e50f-119">找到三个按钮的声明。</span><span class="sxs-lookup"><span data-stu-id="2e50f-119">Find the declarations for the three buttons.</span></span> <span data-ttu-id="2e50f-120">下面的代码示例演示了和属性指定的 `GenerateMember` 差异 `Modifiers` 。</span><span class="sxs-lookup"><span data-stu-id="2e50f-120">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>

     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]

     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]

> [!NOTE]
> <span data-ttu-id="2e50f-121">默认情况下，Windows 窗体设计器将 `private` `Friend` Visual Basic) 修饰符中的 (分配给容器控件，如 <xref:System.Windows.Forms.Panel> 。</span><span class="sxs-lookup"><span data-stu-id="2e50f-121">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="2e50f-122">如果你的基础 <xref:System.Windows.Forms.UserControl> 或 <xref:System.Windows.Forms.Form> 具有容器控件，它将不接受继承的控件和窗体中的新子级。</span><span class="sxs-lookup"><span data-stu-id="2e50f-122">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="2e50f-123">解决方法是将基容器控件的修饰符更改为 `protected` 或 `public` 。</span><span class="sxs-lookup"><span data-stu-id="2e50f-123">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e50f-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e50f-124">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="2e50f-125">Windows 窗体可视化继承</span><span class="sxs-lookup"><span data-stu-id="2e50f-125">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="2e50f-126">演练：演示可视化继承</span><span class="sxs-lookup"><span data-stu-id="2e50f-126">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)
- [<span data-ttu-id="2e50f-127">如何：继承 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="2e50f-127">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
