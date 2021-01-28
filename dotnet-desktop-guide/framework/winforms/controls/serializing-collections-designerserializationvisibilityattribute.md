---
title: 演练：使用 DesignerSerializationVisibilityAttribute 序列化标准类型的集合
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
ms.openlocfilehash: f4fb9c6e7c48a1c6671b14ba05a63dc61195105a
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957612"
---
# <a name="walkthrough-serialize-collections-of-standard-types"></a><span data-ttu-id="ed13a-102">演练：序列化标准类型的集合</span><span class="sxs-lookup"><span data-stu-id="ed13a-102">Walkthrough: Serialize collections of standard types</span></span>

<span data-ttu-id="ed13a-103">自定义控件有时会将集合公开为属性。</span><span class="sxs-lookup"><span data-stu-id="ed13a-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="ed13a-104">本演练演示如何使用 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> 类来控制在设计时如何序列化集合。</span><span class="sxs-lookup"><span data-stu-id="ed13a-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="ed13a-105"><xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>将值应用于集合属性可确保对属性进行序列化。</span><span class="sxs-lookup"><span data-stu-id="ed13a-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>

<span data-ttu-id="ed13a-106">若要将本主题中的代码复制为单个列表，请参阅 [如何：使用 DesignerSerializationVisibilityAttribute 序列化标准类型的集合](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="ed13a-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ed13a-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="ed13a-107">Prerequisites</span></span>

<span data-ttu-id="ed13a-108">若要完成本演练，必须具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="ed13a-108">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-a-control-with-a-serializable-collection"></a><span data-ttu-id="ed13a-109">使用可序列化集合创建控件</span><span class="sxs-lookup"><span data-stu-id="ed13a-109">Create a control with a serializable collection</span></span>

<span data-ttu-id="ed13a-110">第一步是创建一个控件，该控件将可序列化集合作为属性。</span><span class="sxs-lookup"><span data-stu-id="ed13a-110">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="ed13a-111">您可以使用 " **集合编辑器**" 编辑此集合的内容，您可以从 " **属性** " 窗口访问此集合。</span><span class="sxs-lookup"><span data-stu-id="ed13a-111">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>

1. <span data-ttu-id="ed13a-112">在 Visual Studio 中，创建一个 Windows 控件库项目，并将其命名为 **SerializationDemoControlLib**。</span><span class="sxs-lookup"><span data-stu-id="ed13a-112">In Visual Studio, create a Windows Control Library project, and name it **SerializationDemoControlLib**.</span></span>

2. <span data-ttu-id="ed13a-113">将 `UserControl1` 重命名为 `SerializationDemoControl`。</span><span class="sxs-lookup"><span data-stu-id="ed13a-113">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="ed13a-114">有关详细信息，请参阅 [重命名代码符号重构](/visualstudio/ide/reference/rename)。</span><span class="sxs-lookup"><span data-stu-id="ed13a-114">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

3. <span data-ttu-id="ed13a-115">在 " **属性** " 窗口中，将属性的值设置 <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> 为 **10**。</span><span class="sxs-lookup"><span data-stu-id="ed13a-115">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to **10**.</span></span>

4. <span data-ttu-id="ed13a-116">将 <xref:System.Windows.Forms.TextBox> 控件放置在中 `SerializationDemoControl` 。</span><span class="sxs-lookup"><span data-stu-id="ed13a-116">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>

5. <span data-ttu-id="ed13a-117">选择 <xref:System.Windows.Forms.TextBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="ed13a-117">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="ed13a-118">在 " **属性** " 窗口中，设置以下属性。</span><span class="sxs-lookup"><span data-stu-id="ed13a-118">In the **Properties** window, set the following properties.</span></span>

    |<span data-ttu-id="ed13a-119">properties</span><span class="sxs-lookup"><span data-stu-id="ed13a-119">Property</span></span>|<span data-ttu-id="ed13a-120">更改为</span><span class="sxs-lookup"><span data-stu-id="ed13a-120">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="ed13a-121">**多行**</span><span class="sxs-lookup"><span data-stu-id="ed13a-121">**Multiline**</span></span>|`true`|
    |<span data-ttu-id="ed13a-122">**靠接**</span><span class="sxs-lookup"><span data-stu-id="ed13a-122">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|
    |<span data-ttu-id="ed13a-123">**ScrollBars**</span><span class="sxs-lookup"><span data-stu-id="ed13a-123">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |<span data-ttu-id="ed13a-124">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="ed13a-124">**ReadOnly**</span></span>|`true`|

6. <span data-ttu-id="ed13a-125">在 **代码编辑器** 中，声明中名为的字符串数组字段 `stringsValue` `SerializationDemoControl` 。</span><span class="sxs-lookup"><span data-stu-id="ed13a-125">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. <span data-ttu-id="ed13a-126">定义 `Strings` 上的属性 `SerializationDemoControl` 。</span><span class="sxs-lookup"><span data-stu-id="ed13a-126">Define the `Strings` property on the `SerializationDemoControl`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ed13a-127"><xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>该值用于启用集合的序列化。</span><span class="sxs-lookup"><span data-stu-id="ed13a-127">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. <span data-ttu-id="ed13a-128">按 **F5** 生成项目并在 " **UserControl 测试容器**" 中运行控件。</span><span class="sxs-lookup"><span data-stu-id="ed13a-128">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

9. <span data-ttu-id="ed13a-129">查找 <xref:System.Windows.Forms.PropertyGrid> **UserControl 测试容器** 的中的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="ed13a-129">Find the **Strings** property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="ed13a-130">选择 " **字符串** " 属性，然后在 ![ "Visual Studio) " 按钮的属性窗口中选择省略号按钮 ( ( ... ) ， ](./media/visual-studio-ellipsis-button.png) 以打开 " **字符串集合编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="ed13a-130">Select the **Strings** property, then select the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to open the **String Collection Editor**.</span></span>

10. <span data-ttu-id="ed13a-131">在 **字符串集合编辑器** 中输入几个字符串。</span><span class="sxs-lookup"><span data-stu-id="ed13a-131">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="ed13a-132">通过在每个字符串的结尾按 **enter** 键来分隔它们。</span><span class="sxs-lookup"><span data-stu-id="ed13a-132">Separate them by pressing the **Enter** key at the end of each string.</span></span> <span data-ttu-id="ed13a-133">输入完字符串后，请单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="ed13a-133">Click **OK** when you are finished entering strings.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ed13a-134">你键入的字符串将显示在 <xref:System.Windows.Forms.TextBox> 的中 `SerializationDemoControl` 。</span><span class="sxs-lookup"><span data-stu-id="ed13a-134">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

## <a name="serialize-a-collection-property"></a><span data-ttu-id="ed13a-135">序列化集合属性</span><span class="sxs-lookup"><span data-stu-id="ed13a-135">Serialize a collection property</span></span>

<span data-ttu-id="ed13a-136">若要测试控件的序列化行为，请将其放在窗体上，并使用 **集合编辑器** 更改集合的内容。</span><span class="sxs-lookup"><span data-stu-id="ed13a-136">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="ed13a-137">可以通过查看 **Windows 窗体设计器** 向其发出代码的特定设计器文件来查看序列化的集合状态。</span><span class="sxs-lookup"><span data-stu-id="ed13a-137">You can see the serialized collection state by looking at a special designer file into which the **Windows Forms Designer** emits code.</span></span>

1. <span data-ttu-id="ed13a-138">向解决方案中添加一个 Windows 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="ed13a-138">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="ed13a-139">将项目命名为 `SerializationDemoControlTest`。</span><span class="sxs-lookup"><span data-stu-id="ed13a-139">Name the project `SerializationDemoControlTest`.</span></span>

2. <span data-ttu-id="ed13a-140">在 " **工具箱**" 中，找到名为 " **SerializationDemoControlLib 组件**" 的选项卡。</span><span class="sxs-lookup"><span data-stu-id="ed13a-140">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="ed13a-141">在此选项卡中，你将找到 `SerializationDemoControl` 。</span><span class="sxs-lookup"><span data-stu-id="ed13a-141">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="ed13a-142">有关详细信息，请参阅[演练：使用自定义组件自动填充工具箱](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)。</span><span class="sxs-lookup"><span data-stu-id="ed13a-142">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

3. <span data-ttu-id="ed13a-143">将放置 `SerializationDemoControl` 在窗体上。</span><span class="sxs-lookup"><span data-stu-id="ed13a-143">Place a `SerializationDemoControl` on your form.</span></span>

4. <span data-ttu-id="ed13a-144">`Strings`在 "**属性**" 窗口中找到属性。</span><span class="sxs-lookup"><span data-stu-id="ed13a-144">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="ed13a-145">单击 " `Strings` 属性"，然后单击 " ![ Visual Studio 属性窗口中的省略号按钮 (省略号按钮 (" ) "。 ](./media/visual-studio-ellipsis-button.png)) " 按钮，以打开 " **字符串集合编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="ed13a-145">Click the `Strings` property, then click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **String Collection Editor**.</span></span>

5. <span data-ttu-id="ed13a-146">在 **字符串集合编辑器** 中键入多个字符串。</span><span class="sxs-lookup"><span data-stu-id="ed13a-146">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="ed13a-147">在每个字符串的末尾按 **enter** 分隔它们。</span><span class="sxs-lookup"><span data-stu-id="ed13a-147">Separate them by pressing **Enter** at the end of each string.</span></span> <span data-ttu-id="ed13a-148">输入完字符串后，请单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="ed13a-148">Click **OK** when you are finished entering strings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ed13a-149">你键入的字符串将显示在 <xref:System.Windows.Forms.TextBox> 的中 `SerializationDemoControl` 。</span><span class="sxs-lookup"><span data-stu-id="ed13a-149">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

6. <span data-ttu-id="ed13a-150">在“解决方案资源管理器”中，单击“显示所有文件”按钮。</span><span class="sxs-lookup"><span data-stu-id="ed13a-150">In **Solution Explorer**, click the **Show All Files** button.</span></span>

7. <span data-ttu-id="ed13a-151">打开 " **Form1** " 节点。</span><span class="sxs-lookup"><span data-stu-id="ed13a-151">Open the **Form1** node.</span></span> <span data-ttu-id="ed13a-152">下面是一个名为 **Form1.Designer.cs 或** 的 **文件。**</span><span class="sxs-lookup"><span data-stu-id="ed13a-152">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="ed13a-153">这是 **Windows 窗体设计器** 发出代码的文件，表示窗体的设计时状态及其子控件。</span><span class="sxs-lookup"><span data-stu-id="ed13a-153">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="ed13a-154">在 **代码编辑器** 中打开此文件。</span><span class="sxs-lookup"><span data-stu-id="ed13a-154">Open this file in the **Code Editor**.</span></span>

8. <span data-ttu-id="ed13a-155">打开名为 " **Windows 窗体设计器生成的代码** " 的区域，找到标记为 " **serializationDemoControl1**" 的部分。</span><span class="sxs-lookup"><span data-stu-id="ed13a-155">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="ed13a-156">此标签下面是表示控件的已序列化状态的代码。</span><span class="sxs-lookup"><span data-stu-id="ed13a-156">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="ed13a-157">在步骤5中键入的字符串将显示在对属性的赋值中 `Strings` 。</span><span class="sxs-lookup"><span data-stu-id="ed13a-157">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="ed13a-158">下面的 c # 和 Visual Basic 中的代码示例将显示类似于键入字符串 "red"、"橙色" 和 "黄色" 的代码。</span><span class="sxs-lookup"><span data-stu-id="ed13a-158">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

9. <span data-ttu-id="ed13a-159">在 **代码编辑器** 中，将属性的值更改 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> `Strings` 为 <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden> 。</span><span class="sxs-lookup"><span data-stu-id="ed13a-159">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

10. <span data-ttu-id="ed13a-160">重新生成解决方案，并重复步骤3和4。</span><span class="sxs-lookup"><span data-stu-id="ed13a-160">Rebuild the solution and repeat steps 3 and 4.</span></span>

> [!NOTE]
> <span data-ttu-id="ed13a-161">在这种情况下， **Windows 窗体设计器** 不发出对属性的赋值 `Strings` 。</span><span class="sxs-lookup"><span data-stu-id="ed13a-161">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ed13a-162">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ed13a-162">Next steps</span></span>

<span data-ttu-id="ed13a-163">一旦知道如何序列化标准类型的集合，请考虑将自定义控件更深入地集成到设计时环境中。</span><span class="sxs-lookup"><span data-stu-id="ed13a-163">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="ed13a-164">以下主题介绍如何增强自定义控件的设计时集成：</span><span class="sxs-lookup"><span data-stu-id="ed13a-164">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>

- <span data-ttu-id="ed13a-165">[设计时体系结构](/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ed13a-165">[Design-Time Architecture](/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span></span>

- [<span data-ttu-id="ed13a-166">Windows 窗体控件中的特性</span><span class="sxs-lookup"><span data-stu-id="ed13a-166">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)

- <span data-ttu-id="ed13a-167">[设计器序列化概述](/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ed13a-167">[Designer Serialization Overview](/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>

- [<span data-ttu-id="ed13a-168">演练：创建利用 Visual Studio Design-Time 功能的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="ed13a-168">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a><span data-ttu-id="ed13a-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed13a-169">See also</span></span>

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- [<span data-ttu-id="ed13a-170">演练：使用自定义组件自动填充工具箱</span><span class="sxs-lookup"><span data-stu-id="ed13a-170">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
