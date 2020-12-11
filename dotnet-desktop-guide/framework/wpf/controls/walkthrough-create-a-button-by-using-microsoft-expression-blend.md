---
title: 演练：使用 Microsoft Expression Blend 创建按钮
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
- converting [WPF], shape to button
- Expression Blend [WPF Designer]
ms.assetid: ff5037c2-bba7-4cae-8abb-6475b686c48e
ms.openlocfilehash: bcf1c14980556caf7c08be03e12467c86ab3c6a1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973946"
---
# <a name="walkthrough-create-a-button-by-using-microsoft-expression-blend"></a><span data-ttu-id="3b3cf-102">演练：使用 Microsoft Expression Blend 创建按钮</span><span class="sxs-lookup"><span data-stu-id="3b3cf-102">Walkthrough: Create a Button by Using Microsoft Expression Blend</span></span>

<span data-ttu-id="3b3cf-103">本演练逐步介绍如何使用 Microsoft Expression Blend 创建 WPF 自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-103">This walkthrough steps you through the process of creating a WPF customized button using Microsoft Expression Blend.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b3cf-104">Microsoft Expression Blend 的工作方式 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 是生成，然后将其编译为生成可执行程序。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-104">Microsoft Expression Blend works by generating [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] that is then compiled to make the executable program.</span></span> <span data-ttu-id="3b3cf-105">如果你希望直接使用 XAML，则还有另一个演练，它使用 XAML 和 Visual Studio （而不是 Blend）创建与此应用程序相同的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-105">If you would rather work with XAML directly, there is another walkthrough that creates the same application as this one using XAML with Visual Studio rather than Blend.</span></span> <span data-ttu-id="3b3cf-106">有关详细信息，请参阅 [使用 XAML 创建按钮](walkthrough-create-a-button-by-using-xaml.md) 。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-106">See [Create a Button by Using XAML](walkthrough-create-a-button-by-using-xaml.md) for more information.</span></span>

<span data-ttu-id="3b3cf-107">下图显示了您将创建的自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-107">The following illustration shows the customized button that you will create.</span></span>

![你将创建的自定义按钮](./media/custom-button-blend-intro.jpg)

## <a name="convert-a-shape-to-a-button"></a><span data-ttu-id="3b3cf-109">将形状转换为按钮</span><span class="sxs-lookup"><span data-stu-id="3b3cf-109">Convert a Shape to a Button</span></span>

<span data-ttu-id="3b3cf-110">在本演练的第一部分中，你将创建自定义按钮的自定义外观。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-110">In the first part of this walkthrough you create the custom look of the custom button.</span></span> <span data-ttu-id="3b3cf-111">为此，首先要将矩形转换为按钮。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-111">To do this, you first convert a rectangle to a button.</span></span> <span data-ttu-id="3b3cf-112">然后，将其他形状添加到按钮的模板中，从而创建一个更复杂的 "按钮" 按钮。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-112">You then add additional shapes to the template of the button, creating a more complex looking button.</span></span> <span data-ttu-id="3b3cf-113">为什么不使用常规按钮启动并对其进行自定义？</span><span class="sxs-lookup"><span data-stu-id="3b3cf-113">Why not start with a regular button and customize it?</span></span> <span data-ttu-id="3b3cf-114">因为按钮具有不需要的内置功能，对于自定义按钮，从矩形开始更容易。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-114">Because a button has built-in functionality that you do not need; for custom buttons, it is easier to start with a rectangle.</span></span>

### <a name="to-create-a-new-project-in-expression-blend"></a><span data-ttu-id="3b3cf-115">在 Expression Blend 中创建新项目</span><span class="sxs-lookup"><span data-stu-id="3b3cf-115">To create a new project in Expression Blend</span></span>

1. <span data-ttu-id="3b3cf-116">开始 Expression Blend。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-116">Start Expression Blend.</span></span> <span data-ttu-id="3b3cf-117"> (单击 " **开始**"，指向 " **所有程序**"，指向 " **microsoft expression**"，然后单击 " **microsoft expression Blend**"。 ) </span><span class="sxs-lookup"><span data-stu-id="3b3cf-117">(Click **Start**, point to **All Programs**, point to **Microsoft Expression**, and then click **Microsoft Expression Blend**.)</span></span>

2. <span data-ttu-id="3b3cf-118">如果需要，最大化应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-118">Maximize the application if needed.</span></span>

3. <span data-ttu-id="3b3cf-119">在“文件”菜单上，单击“新建项目”。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-119">On the **File** menu, click **New Project**.</span></span>

4. <span data-ttu-id="3b3cf-120">选择 **标准应用程序 ( .exe)**。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-120">Select **Standard Application (.exe)**.</span></span>

5. <span data-ttu-id="3b3cf-121">为项目命名 `CustomButton` 并按 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-121">Name the project `CustomButton` and press **OK**.</span></span>

<span data-ttu-id="3b3cf-122">此时，您有一个空白 WPF 项目。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-122">At this point you have a blank WPF project.</span></span> <span data-ttu-id="3b3cf-123">可以按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-123">You can press F5 to run the application.</span></span> <span data-ttu-id="3b3cf-124">正如您所料，应用程序只包含一个空白窗口。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-124">As you might expect, the application consists of only a blank window.</span></span> <span data-ttu-id="3b3cf-125">接下来，创建一个圆角矩形，并将其转换为按钮。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-125">Next, you create a rounded rectangle and convert it into a button.</span></span>

### <a name="to-convert-a-rectangle-to-a-button"></a><span data-ttu-id="3b3cf-126">将矩形转换为按钮</span><span class="sxs-lookup"><span data-stu-id="3b3cf-126">To convert a Rectangle to a Button</span></span>

1. <span data-ttu-id="3b3cf-127">**将窗口背景属性设置为黑色：** 选择窗口，单击 " **属性" 选项卡**，然后将 <xref:System.Windows.Controls.Control.Background%2A> 属性设置 `Black` 为。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-127">**Set the Window Background property to black:** Select the Window, click the **Properties Tab**, and set the <xref:System.Windows.Controls.Control.Background%2A> property to `Black`.</span></span>

    ![如何将按钮的背景设置为黑色](./media/custom-button-blend-changebackground.png)

2. <span data-ttu-id="3b3cf-129">**在窗口上的按钮大小约绘制一个矩形：** 选择左侧工具面板上的 "矩形" 工具，然后将该矩形拖到窗口上。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-129">**Draw a rectangle approximately the size of a button on the Window:** Select the rectangle tool on the left-hand tool panel and drag the rectangle onto the Window.</span></span>

    ![如何绘制矩形](./media/custom-button-blend-drawrect.png)

3. <span data-ttu-id="3b3cf-131">将 **矩形的角取整：** 拖动矩形的控制点或直接设置 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 和 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-131">**Round out the corners of the rectangle:** Either drag the control points of the rectangle or directly set the <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="3b3cf-132">将和的值 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 设置 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 为20。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-132">Set the values of <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> to 20.</span></span>

    ![如何使矩形的角变为圆角](./media/custom-button-blend-roundcorners.png)

4. <span data-ttu-id="3b3cf-134">**将矩形更改为按钮：** 选择该矩形。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-134">**Change the rectangle into a button:** Select the rectangle.</span></span> <span data-ttu-id="3b3cf-135">单击 " **工具** " 菜单上的 " **生成" 按钮**。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-135">On the **Tools** menu, click **Make Button**.</span></span>

    ![如何使形状变为按钮](./media/custom-button-blend-makebutton.png)

5. <span data-ttu-id="3b3cf-137">**指定样式/模板的作用域：** 将显示如下所示的对话框。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-137">**Specify the scope of the style/template:** A dialog box like the following appears.</span></span>

    ![“创建样式资源”对话框](./media/custom-button-blend-makebutton2.gif)

    <span data-ttu-id="3b3cf-139">对于 **资源名称 (键)**，选择 " **应用到所有** 项"。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-139">For **Resource name (Key)**, select **Apply to all**.</span></span>  <span data-ttu-id="3b3cf-140">这会使生成的样式和按钮模板应用于所有作为按钮的对象。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-140">This will make the resulting style and button template apply to all objects that are buttons.</span></span> <span data-ttu-id="3b3cf-141">对于 **中** 的 "定义"，选择 " **应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-141">For **Define in**, select **Application**.</span></span> <span data-ttu-id="3b3cf-142">这会使生成的样式和按钮模板在整个应用程序中的作用域。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-142">This will make the resulting style and button template have scope over the entire application.</span></span> <span data-ttu-id="3b3cf-143">在这两个框中设置值时，按钮样式和模板应用于整个应用程序中的所有按钮，并且在应用程序中创建的任何按钮默认情况下都使用此模板。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-143">When you set the values in these two boxes, the button style and template apply to all buttons within the entire application and any button you create in the application will, by default, use this template.</span></span>

## <a name="edit-the-button-template"></a><span data-ttu-id="3b3cf-144">编辑按钮模板</span><span class="sxs-lookup"><span data-stu-id="3b3cf-144">Edit the Button Template</span></span>

<span data-ttu-id="3b3cf-145">现在，你已有一个已更改为按钮的矩形。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-145">You now have a rectangle that has been changed to a button.</span></span> <span data-ttu-id="3b3cf-146">在本部分中，您将修改该按钮的模板，并进一步自定义其外观。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-146">In this section, you'll modify the template of the button and further customize how it looks.</span></span>

### <a name="to-edit-the-button-template-to-change-the-button-appearance"></a><span data-ttu-id="3b3cf-147">编辑按钮模板以更改按钮外观</span><span class="sxs-lookup"><span data-stu-id="3b3cf-147">To edit the button template to change the button appearance</span></span>

1. <span data-ttu-id="3b3cf-148">**进入编辑模板视图：** 若要进一步自定义按钮的外观，需要编辑按钮模板。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-148">**Go into edit template view:** To further customize the look of our button, we need to edit the button template.</span></span> <span data-ttu-id="3b3cf-149">此模板是在将矩形转换为按钮时创建的。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-149">This template was created when we converted the rectangle into a button.</span></span> <span data-ttu-id="3b3cf-150">若要编辑按钮模板，请右键单击该按钮，然后选择 " **编辑控件部件" (模板)** 然后单击 " **编辑模板**"。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-150">To edit the button template, right-click the button and select **Edit Control Parts (Template)** and then **Edit Template**.</span></span>

    ![如何编辑模板](./media/custom-button-blend-edittemplate.jpg)

    <span data-ttu-id="3b3cf-152">请注意，在模板编辑器中，按钮现在分隔为 <xref:System.Windows.Shapes.Rectangle> 和 <xref:System.Windows.Controls.ContentPresenter> 。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-152">In the template editor, notice that the button is now separated into a <xref:System.Windows.Shapes.Rectangle> and the <xref:System.Windows.Controls.ContentPresenter>.</span></span> <span data-ttu-id="3b3cf-153"><xref:System.Windows.Controls.ContentPresenter>用于在按钮内显示内容 (例如，字符串 "button" ) 。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-153">The <xref:System.Windows.Controls.ContentPresenter> is used to present content within the button (for example, the string "Button").</span></span> <span data-ttu-id="3b3cf-154">矩形和都在 <xref:System.Windows.Controls.ContentPresenter> 内进行布局 <xref:System.Windows.Controls.Grid> 。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-154">Both the rectangle and <xref:System.Windows.Controls.ContentPresenter> are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>

    ![用于展示矩形的组件](./media/custom-button-blend-templatepanel.png)

2. <span data-ttu-id="3b3cf-156">**更改模板组件的名称：** 右键单击模板清单中的矩形，将 <xref:System.Windows.Shapes.Rectangle> 名称从 "[rectangle]" 更改为 "outerRectangle"，并将 "[system.windows.controls.contentpresenter>]" 更改为 "myContentPresenter"。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-156">**Change the names of the template components:** Right-click the rectangle in the template inventory, change the <xref:System.Windows.Shapes.Rectangle> name from "[Rectangle]" to "outerRectangle", and change "[ContentPresenter]" to "myContentPresenter".</span></span>

    ![如何重命名模板的组件](./media/custom-button-blend-renamecomponents.png)

3. <span data-ttu-id="3b3cf-158">**更改矩形，使其在 (中为空，如环形) ：** 选择 **outerRectangle** 并将设置 <xref:System.Windows.Shapes.Shape.Fill%2A> 为 "透明"，并设置 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 为5。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-158">**Alter the rectangle so that it is empty inside (like a donut):** Select **outerRectangle** and set <xref:System.Windows.Shapes.Shape.Fill%2A> to "Transparent" and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> to 5.</span></span>

    ![如何使矩形为空](./media/custom-button-blend-changerectproperties.png)

    <span data-ttu-id="3b3cf-160">然后，将设置 <xref:System.Windows.Shapes.Shape.Stroke%2A> 为模板的任何颜色。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-160">Then set the <xref:System.Windows.Shapes.Shape.Stroke%2A> to the color of whatever the template will be.</span></span> <span data-ttu-id="3b3cf-161">为此，请单击 " **笔划**" 旁边的小白色框，选择 " **CustomExpression**"，然后在对话框中键入 "{TemplateBinding Background}"。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-161">To do this, click the small white box next to **Stroke**, select **CustomExpression**, and type "{TemplateBinding Background}" in the dialog box.</span></span>

    ![如何设置和使用模板的颜色](./media/custom-button-blend-templatestroke.png)

4. <span data-ttu-id="3b3cf-163">**创建内部矩形：** 现在，请创建另一个矩形 (将其命名为 "innerRectangle" ) 并将其在 **outerRectangle** 内以对称的位置定位。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-163">**Create an inner rectangle:** Now, create another rectangle (name it "innerRectangle") and position it symmetrically on the inside of **outerRectangle** .</span></span> <span data-ttu-id="3b3cf-164">对于这种类型的工作，你可能想要进行缩放以使编辑区域中的按钮变大。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-164">For this kind of work, you will probably want to zoom to make the button larger in the editing area.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3b3cf-165">例如，矩形的外观可能不同 (例如，它可能具有圆角) 。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-165">Your rectangle might look different than the one in the figure (for example, it might have rounded corners).</span></span>

    ![如何在一个矩形内创建另一个矩形](./media/custom-button-blend-innerrectangleproperties.png)

5. <span data-ttu-id="3b3cf-167">**将 System.windows.controls.contentpresenter> 移到顶部：** 此时，可能不会再看到文本 "Button"。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-167">**Move ContentPresenter to the top:** At this point, it is possible that the text "Button" will not be visible any longer.</span></span> <span data-ttu-id="3b3cf-168">如果是这样，则这是因为 **innerRectangle** 位于 **myContentPresenter** 的顶层。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-168">If this is so, this is because **innerRectangle** is on top of the **myContentPresenter**.</span></span> <span data-ttu-id="3b3cf-169">若要解决此问题，请将 **myContentPresenter** 拖到下面的 **innerRectangle**。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-169">To fix this, drag **myContentPresenter** below **innerRectangle**.</span></span> <span data-ttu-id="3b3cf-170">重定位矩形和 **myContentPresenter** ，使其看起来类似于下面的内容。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-170">Reposition rectangles and **myContentPresenter** to look similar to below.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3b3cf-171">此外，还可以通过右键单击 **myContentPresenter** 并按 " **发送前**" 将其定位在顶部。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-171">Alternatively, you can also position **myContentPresenter** on top by right-clicking it and pressing **Send Forward**.</span></span>

    ![如何将一个按钮移到另一个按钮的上面](./media/custom-button-blend-innerrectangle2.png)

6. <span data-ttu-id="3b3cf-173">**更改 innerRectangle 的外观：** 将 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 、 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 和值设置 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 为20。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-173">**Change the look of innerRectangle:** Set the <xref:System.Windows.Shapes.Rectangle.RadiusX%2A>, <xref:System.Windows.Shapes.Rectangle.RadiusY%2A>, and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> values to 20.</span></span> <span data-ttu-id="3b3cf-174">此外， <xref:System.Windows.Shapes.Shape.Fill%2A> 使用自定义表达式 "{TemplateBinding background}" 将设置为模板的背景 ) 并将其设置 <xref:System.Windows.Shapes.Shape.Stroke%2A> 为 "透明"。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-174">In addition, set the <xref:System.Windows.Shapes.Shape.Fill%2A> to the background of the template using the custom expression "{TemplateBinding Background}" ) and set <xref:System.Windows.Shapes.Shape.Stroke%2A> to "transparent".</span></span> <span data-ttu-id="3b3cf-175">请注意，和的 InnerRectangle 的设置与 OuterRectangle 的设置 <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Shape.Stroke%2A> 相反。  </span><span class="sxs-lookup"><span data-stu-id="3b3cf-175">Notice that the settings for the <xref:System.Windows.Shapes.Shape.Fill%2A> and <xref:System.Windows.Shapes.Shape.Stroke%2A> of **innerRectangle** are the opposite of those for **outerRectangle**.</span></span>

    ![如何更改矩形的外观](./media/custom-button-blend-glassrectangleproperties1.png)

7. <span data-ttu-id="3b3cf-177">**在顶部添加玻璃层：** 自定义按钮外观的最后一项是在顶部添加玻璃层。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-177">**Add a glass layer on top:** The final piece of customizing the look of the button is to add a glass layer on top.</span></span> <span data-ttu-id="3b3cf-178">此玻璃层包含第三个矩形。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-178">This glass layer consists of a third rectangle.</span></span> <span data-ttu-id="3b3cf-179">由于玻璃将覆盖整个按钮，因此，玻璃矩形在维度中类似于 **outerRectangle**。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-179">Because the glass will cover the entire button, the glass rectangle is similar in dimensions to the **outerRectangle**.</span></span> <span data-ttu-id="3b3cf-180">因此，只需制作一份 **outerRectangle** 副本就能创建该矩形。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-180">Therefore, create the rectangle by simply making a copy of the **outerRectangle**.</span></span> <span data-ttu-id="3b3cf-181">突出显示 **outerRectangle** ，并使用 Ctrl + C 和 Ctrl + V 制作副本。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-181">Highlight **outerRectangle** and use CTRL+C and CTRL+V to make a copy.</span></span> <span data-ttu-id="3b3cf-182">将此新矩形命名为 "glassCube"。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-182">Name this new rectangle "glassCube".</span></span>

8. <span data-ttu-id="3b3cf-183">**如有必要，重定位 glassCube：** 如果 **glassCube** 尚未定位，使其覆盖整个按钮，请将其拖动到位置。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-183">**Reposition glassCube if necessary:** If **glassCube** is not already positioned so that it covers the entire button, drag it into position.</span></span>

9. <span data-ttu-id="3b3cf-184">**为 glassCube 指定一个与 outerRectangle 略有不同的形状：** 更改 **glassCube** 的属性。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-184">**Give glassCube a slightly different shape than outerRectangle:** Change the properties of **glassCube**.</span></span> <span data-ttu-id="3b3cf-185">首先将 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 和 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 属性更改为10，将更改 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 为2。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-185">Start off by changing the <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties to 10 and the <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> to 2.</span></span>

    ![glassCube 的外观设置](./media/custom-button-blend-glasscubeappearance.gif)

10. <span data-ttu-id="3b3cf-187">**使 glassCube 看起来像玻璃：**<xref:System.Windows.Shapes.Shape.Fill%2A>通过使用线性渐变（75% 不透明）将设置为 glassy 外观，在大约均匀间隔的时间段内，在白色和透明之间交替变化。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-187">**Make glassCube look like glass:** Set the <xref:System.Windows.Shapes.Shape.Fill%2A> to a glassy look by  using a linear gradient that is 75% opaque and alternates between the color White and Transparent over 6 approximately evenly spaced intervals.</span></span> <span data-ttu-id="3b3cf-188">这是将梯度停止点设置为：</span><span class="sxs-lookup"><span data-stu-id="3b3cf-188">This is what to set the gradient stops to:</span></span>

    - <span data-ttu-id="3b3cf-189">梯度停止点1：白色，Alpha 值为75%</span><span class="sxs-lookup"><span data-stu-id="3b3cf-189">Gradient Stop 1: White with Alpha value of 75%</span></span>

    - <span data-ttu-id="3b3cf-190">梯度停止点2：透明</span><span class="sxs-lookup"><span data-stu-id="3b3cf-190">Gradient Stop 2: Transparent</span></span>

    - <span data-ttu-id="3b3cf-191">梯度停止点3：白色，Alpha 值为75%</span><span class="sxs-lookup"><span data-stu-id="3b3cf-191">Gradient Stop 3: White with Alpha value of 75%</span></span>

    - <span data-ttu-id="3b3cf-192">梯度停止点4：透明</span><span class="sxs-lookup"><span data-stu-id="3b3cf-192">Gradient Stop 4: Transparent</span></span>

    - <span data-ttu-id="3b3cf-193">梯度停止点5：白色，Alpha 值为75%</span><span class="sxs-lookup"><span data-stu-id="3b3cf-193">Gradient Stop 5: White with Alpha value of 75%</span></span>

    - <span data-ttu-id="3b3cf-194">梯度停止点6：透明</span><span class="sxs-lookup"><span data-stu-id="3b3cf-194">Gradient Stop 6: Transparent</span></span>

    <span data-ttu-id="3b3cf-195">这会创建一个 "波浪形" 玻璃外观。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-195">This creates a "wavy" glass look.</span></span>

    ![看起来像玻璃的矩形](./media/custom-button-blend-glassrectangleproperties2.png)

11. <span data-ttu-id="3b3cf-197">**隐藏玻璃层：** 现在，你已经了解了 glassy 层的外观，接下来请进入 "**属性" 面板** 的 "**外观" 窗格**，并将不透明度设置为0% 以隐藏它。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-197">**Hide the glass layer:** Now that you see what the glassy layer looks like, go into the **Appearance pane** of the **Properties panel** and set the Opacity to 0% to hide it.</span></span> <span data-ttu-id="3b3cf-198">在前面的部分中，我们将使用属性触发器和事件来显示和操作玻璃层。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-198">In the sections ahead, we'll use property triggers and events to show and manipulate the glass layer.</span></span>

    ![如何隐藏玻璃矩形](./media/custom-button-glassrectangleproperties3.gif)

## <a name="customize-the-button-behavior"></a><span data-ttu-id="3b3cf-200">自定义按钮行为</span><span class="sxs-lookup"><span data-stu-id="3b3cf-200">Customize the Button Behavior</span></span>

<span data-ttu-id="3b3cf-201">此时，您已通过编辑模板的模板对该按钮的显示进行了自定义，但该按钮不会对用户操作做出反应 (例如，通过鼠标悬停、接收焦点和单击操作来更改外观。 ) 接下来的两个过程演示如何在自定义按钮中生成类似的行为。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-201">At this point, you have customized the presentation of the button by editing its template, but the button does not react to user actions as typical buttons do (for example, changing appearance upon mouse-over, receiving focus, and clicking.) The next two procedures show how to build behaviors like these into the custom button.</span></span> <span data-ttu-id="3b3cf-202">我们将从简单的属性触发器开始，然后添加事件触发器和动画。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-202">We'll start with simple property triggers, and then add event triggers and animations.</span></span>

### <a name="to-set-property-triggers"></a><span data-ttu-id="3b3cf-203">设置属性触发器</span><span class="sxs-lookup"><span data-stu-id="3b3cf-203">To set property triggers</span></span>

1. <span data-ttu-id="3b3cf-204">**创建新的属性触发器：** 选择 **glassCube** 后，在 "**触发器**" 面板中单击 " **+ 属性**" (参阅下一步骤) 下图。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-204">**Create a new property trigger:** With **glassCube** selected, click **+ Property** in the **Triggers** panel (see the figure that follows the next step).</span></span> <span data-ttu-id="3b3cf-205">这将创建一个具有默认属性触发器的属性触发器。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-205">This creates a property trigger with a default property trigger.</span></span>

2. <span data-ttu-id="3b3cf-206">**将 system.windows.uielement.ismouseover 用作触发器使用的属性：** 将属性更改为 <xref:System.Windows.UIElement.IsMouseOver%2A> 。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-206">**Make IsMouseOver the property used by the trigger:** Change the property to <xref:System.Windows.UIElement.IsMouseOver%2A>.</span></span> <span data-ttu-id="3b3cf-207">当 <xref:System.Windows.UIElement.IsMouseOver%2A> `true` 用户用鼠标) 指向按钮时，这会使属性触发器 (激活。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-207">This makes the property trigger activate when the <xref:System.Windows.UIElement.IsMouseOver%2A> property is `true` (when the user points to the button with the mouse).</span></span>

    ![如何在属性上设置触发器](./media/custom-button-blend-ismousedoverpropertytrigger.png)

3. <span data-ttu-id="3b3cf-209">**System.windows.uielement.ismouseover 触发 glassCube 的100% 的不透明度：** 请注意， **触发器记录位于** (参阅上图) 。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-209">**IsMouseOver triggers opacity of 100% for glassCube:** Notice that the **Trigger recording is on** (see the preceding figure).</span></span> <span data-ttu-id="3b3cf-210">这意味着，在记录时对 **glassCube** 属性值所做的任何更改都将成为在为时进行的操作 <xref:System.Windows.UIElement.IsMouseOver%2A> `true` 。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-210">This means that any changes you make to the property values of **glassCube** while recording is on will become an action that takes place when <xref:System.Windows.UIElement.IsMouseOver%2A> is `true`.</span></span> <span data-ttu-id="3b3cf-211">录制时，将 <xref:System.Windows.UIElement.Opacity%2A> **glassCube** 的更改为100%。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-211">While recording, change the <xref:System.Windows.UIElement.Opacity%2A> of **glassCube** to 100%.</span></span>

    ![如何设置按钮的不透明度](./media/custom-button-blend-ismousedoverpropertytrigger2.gif)

    <span data-ttu-id="3b3cf-213">现在，您已创建了第一个属性触发器。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-213">You have now created your first property trigger.</span></span> <span data-ttu-id="3b3cf-214">请注意，编辑器的 " **触发器" 面板** 已将 <xref:System.Windows.UIElement.Opacity%2A> 更改为100%。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-214">Notice that the **Triggers panel** of the editor has recorded the <xref:System.Windows.UIElement.Opacity%2A> being changed to 100%.</span></span>

    ![“触发器”面板](./media/custom-button-blend-propertytriggerinfo.png)

    <span data-ttu-id="3b3cf-216">按 F5 运行应用程序，并将鼠标指针移到按钮的上方和下方。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-216">Press F5 to run the application, and move the mouse pointer over and off the button.</span></span> <span data-ttu-id="3b3cf-217">当鼠标悬停在按钮上并在指针离开时消失时，应会看到玻璃层。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-217">You should see the glass layer appear when you mouse-over the button and disappear when the pointer leaves.</span></span>

4. <span data-ttu-id="3b3cf-218">**System.windows.uielement.ismouseover 触发器笔划值更改：** 让我们将其他一些操作与触发器相关联 <xref:System.Windows.UIElement.IsMouseOver%2A> 。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-218">**IsMouseOver triggers stroke value change:** Let's associate some other actions with the <xref:System.Windows.UIElement.IsMouseOver%2A> trigger.</span></span> <span data-ttu-id="3b3cf-219">录制继续时，请将所选内容从 **glassCube** 切换到 **outerRectangle**。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-219">While recording continues, switch your selection from **glassCube** to **outerRectangle**.</span></span> <span data-ttu-id="3b3cf-220">然后，将 <xref:System.Windows.Shapes.Shape.Stroke%2A> **outerRectangle** 的设置为自定义表达式 "{DynamicResource {X:Static SystemColors. HighlightBrushKey}}"。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-220">Then set the <xref:System.Windows.Shapes.Shape.Stroke%2A> of **outerRectangle** to the custom expression of "{DynamicResource {x:Static SystemColors.HighlightBrushKey}}".</span></span> <span data-ttu-id="3b3cf-221">这会将设置 <xref:System.Windows.Shapes.Shape.Stroke%2A> 为按钮所使用的典型突出显示颜色。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-221">This sets the <xref:System.Windows.Shapes.Shape.Stroke%2A> to the typical highlight color used by buttons.</span></span> <span data-ttu-id="3b3cf-222">当鼠标悬停在按钮上时，请按 F5 查看效果。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-222">Press F5 to see the effect when you mouse over the button.</span></span>

    ![如何将笔画设置为突出显示颜色](./media/custom-button-blend-ismousedoverpropertytrigger3.png)

5. <span data-ttu-id="3b3cf-224">**System.windows.uielement.ismouseover 触发模糊文本：** 让我们将另一个操作与 <xref:System.Windows.UIElement.IsMouseOver%2A> 属性触发器关联起来。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-224">**IsMouseOver triggers blurry text:** Let's associate one more action to the <xref:System.Windows.UIElement.IsMouseOver%2A> property trigger.</span></span> <span data-ttu-id="3b3cf-225">当玻璃出现在屏幕上时，使该按钮的内容看起来很模糊。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-225">Make the content of the button appear a little blurry when the glass appears over it.</span></span> <span data-ttu-id="3b3cf-226">为此，我们可以将模糊应用 <xref:System.Windows.Media.Effects.BitmapEffect> 到 <xref:System.Windows.Controls.ContentPresenter> (**myContentPresenter**) 。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-226">To do this, we can apply a blur <xref:System.Windows.Media.Effects.BitmapEffect> to the <xref:System.Windows.Controls.ContentPresenter> (**myContentPresenter**).</span></span>

    ![如何使按钮内容变得模糊](./media/custom-button-blend-propertytriggerwithbitmapeffect.png)

    > [!NOTE]
    > <span data-ttu-id="3b3cf-228">若要在执行搜索之前返回 " **属性" 面板** <xref:System.Windows.Media.Effects.BitmapEffect> ，请清除 **搜索框** 中的文本。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-228">To return the **Properties panel** back to what it was before you did the search for <xref:System.Windows.Media.Effects.BitmapEffect>, clear the text from the **Search box**.</span></span>

    <span data-ttu-id="3b3cf-229">此时，我们使用了具有多个相关操作的属性触发器来创建鼠标指针进入和离开按钮区域时的突出显示行为。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-229">At this point, we have used a property trigger with several associated actions to create highlighting behavior for when the mouse pointer enters and leaves the button area.</span></span> <span data-ttu-id="3b3cf-230">按钮的另一种典型行为是在 (单击) 时突出显示焦点。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-230">Another typical behavior for a button is to highlight when it has focus (as after it is clicked).</span></span> <span data-ttu-id="3b3cf-231">可以通过为属性添加另一个属性触发器来添加此类行为 <xref:System.Windows.UIElement.IsFocused%2A> 。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-231">We can add such behavior by adding another property trigger for the <xref:System.Windows.UIElement.IsFocused%2A> property.</span></span>

6. <span data-ttu-id="3b3cf-232">**为 IsFocused 创建属性触发器：** 使用与相同的过程 <xref:System.Windows.UIElement.IsMouseOver%2A> (参阅本部分) 的第一步，为属性创建另一个属性触发器 <xref:System.Windows.UIElement.IsFocused%2A> 。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-232">**Create property trigger for IsFocused:** Using the same procedure as for <xref:System.Windows.UIElement.IsMouseOver%2A> (see the first step of this section), create another property trigger for the <xref:System.Windows.UIElement.IsFocused%2A> property.</span></span> <span data-ttu-id="3b3cf-233">当 **触发器记录为 on** 时，将以下操作添加到触发器：</span><span class="sxs-lookup"><span data-stu-id="3b3cf-233">While **Trigger recording is on**, add the following actions to the trigger:</span></span>

    - <span data-ttu-id="3b3cf-234">**glassCube** 获取 <xref:System.Windows.UIElement.Opacity%2A> 100% 的。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-234">**glassCube** gets an <xref:System.Windows.UIElement.Opacity%2A> of 100%.</span></span>

    - <span data-ttu-id="3b3cf-235">**outerRectangle** 获取 <xref:System.Windows.Shapes.Shape.Stroke%2A> 自定义表达式值 "{DynamicResource {X:Static SystemColors. HighlightBrushKey}}"。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-235">**outerRectangle** gets a <xref:System.Windows.Shapes.Shape.Stroke%2A> custom expression value of "{DynamicResource {x:Static SystemColors.HighlightBrushKey}}".</span></span>

<span data-ttu-id="3b3cf-236">作为本演练的最后一步，我们将向按钮添加动画。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-236">As the final step in this walkthrough, we will add animations to the button.</span></span> <span data-ttu-id="3b3cf-237">这些动画将由事件（具体而言是 <xref:System.Windows.UIElement.MouseEnter> 和事件）触发 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-237">These animations will be triggered by events—specifically, the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events.</span></span>

### <a name="to-use-event-triggers-and-animations-to-add-interactivity"></a><span data-ttu-id="3b3cf-238">使用事件触发器和动画添加交互性</span><span class="sxs-lookup"><span data-stu-id="3b3cf-238">To use event triggers and animations to add interactivity</span></span>

1. <span data-ttu-id="3b3cf-239">**创建 MouseEnter 事件触发器：** 添加新的事件触发器，并选择 <xref:System.Windows.UIElement.MouseEnter> 作为要在触发器中使用的事件。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-239">**Create a MouseEnter Event Trigger:** Add a new event trigger and select <xref:System.Windows.UIElement.MouseEnter> as the event to use in the trigger.</span></span>

     ![如何创建 MouseEnter 事件触发器](./media/custom-button-blend-mouseovereventtrigger.png)

2. <span data-ttu-id="3b3cf-241">**创建动画时间线：** 接下来，将动画时间线与 <xref:System.Windows.UIElement.MouseEnter> 事件关联。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-241">**Create an animation timeline:** Next, associate an animation timeline to the <xref:System.Windows.UIElement.MouseEnter> event.</span></span>

    ![如何向事件添加动画时间线](./media/custom-button-blend-mouseovereventtrigger2.png)

    <span data-ttu-id="3b3cf-243">按 **"确定"** 创建新的时间线后，" **时间线" 面板** 将显示并在设计面板中显示 "时间线录制已打开"。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-243">After you press **OK** to create a new timeline, a **Timeline Panel** appears and "Timeline recording is on" is visible in the design panel.</span></span> <span data-ttu-id="3b3cf-244">这意味着，可以在时间线中开始记录属性更改， () 对属性更改进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-244">This means we can start recording property changes in the timeline (animate property changes).</span></span>

    > [!NOTE]
    > <span data-ttu-id="3b3cf-245">可能需要调整窗口和/或面板的大小以查看显示。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-245">You may need to resize your window and/or panels to see the display.</span></span>

    ![时间线面板](./media/custom-button-blend-mouseovereventtrigger3.png)

3. <span data-ttu-id="3b3cf-247">**创建关键帧：** 若要创建动画，请选择要进行动画处理的对象，在时间线上创建两个或更多关键帧，并为这些关键帧设置要在其中插入动画的属性值。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-247">**Create a keyframe:** To create an animation, select the object you want to animate, create two or more keyframes on the timeline, and for those keyframes, set the property values you want the animation to interpolate between.</span></span> <span data-ttu-id="3b3cf-248">下图指导您创建关键帧。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-248">The following figure guides you through the creation of a keyframe.</span></span>

    ![如何创建关键帧](./media/custom-button-blend-mouseovereventtrigger4.png)

4. <span data-ttu-id="3b3cf-250">**收缩此关键帧中的 glassCube：** 选择第二个关键帧后，使用 **大小转换** 将 **glassCube** 的大小缩小到其完整大小的90%。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-250">**Shrink glassCube at this keyframe:** With the second keyframe selected, shrink the size of the **glassCube** to 90% of its full size using the **Size Transform**.</span></span>

    ![如何缩小按钮](./media/custom-button-blend-sizetransform.png)

    <span data-ttu-id="3b3cf-252">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-252">Press F5 to run the application.</span></span> <span data-ttu-id="3b3cf-253">将鼠标指针移到按钮上。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-253">Move the mouse pointer over the button.</span></span> <span data-ttu-id="3b3cf-254">请注意，玻璃层会在按钮上缩小。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-254">Notice that the glass layer shrinks on top of the button.</span></span>

5. <span data-ttu-id="3b3cf-255">**创建另一个事件触发器并将不同的动画与之关联：** 让我们再添加一个动画。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-255">**Create another Event Trigger and associate a different animation with it:** Let's add one more animation.</span></span> <span data-ttu-id="3b3cf-256">使用类似的过程来创建上一个事件触发器动画：</span><span class="sxs-lookup"><span data-stu-id="3b3cf-256">Use a similar procedure to what you used to create the previous event trigger animation:</span></span>

    1. <span data-ttu-id="3b3cf-257">使用事件创建新的事件触发器 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-257">Create a new event trigger using the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>

    2. <span data-ttu-id="3b3cf-258">将新时间线与 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件关联。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-258">Associate a new timeline with the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>

        ![如何创建新的时间线](./media/custom-button-blend-clickeventtrigger1.png)

    3. <span data-ttu-id="3b3cf-260">对于此时间线，请创建两个关键帧，一个为0.0 秒，第二个关键帧0.3 秒。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-260">For this timeline, create two keyframes, one at 0.0 seconds and the second one at 0.3 seconds.</span></span>

    4. <span data-ttu-id="3b3cf-261">突出显示处于0.3 秒的关键帧后，将 **旋转变换角度** 设置为360度。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-261">With the keyframe at 0.3 seconds highlighted, set the **Rotate Transform Angle** to 360 degrees.</span></span>

        ![如何创建旋转变换](./media/custom-button-blend-rotatetransform.gif)

    5. <span data-ttu-id="3b3cf-263">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-263">Press F5 to run the application.</span></span> <span data-ttu-id="3b3cf-264">单击按钮。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-264">Click the button.</span></span> <span data-ttu-id="3b3cf-265">请注意，玻璃层会旋转。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-265">Notice that the glass layer spins around.</span></span>

## <a name="conclusion"></a><span data-ttu-id="3b3cf-266">结论</span><span class="sxs-lookup"><span data-stu-id="3b3cf-266">Conclusion</span></span>

<span data-ttu-id="3b3cf-267">已完成自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-267">You have completed a customized button.</span></span> <span data-ttu-id="3b3cf-268">使用应用于应用程序中所有按钮的按钮模板执行此操作。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-268">You did this using a button template that was applied to all buttons in the application.</span></span> <span data-ttu-id="3b3cf-269">如果你退出模板编辑模式 (参阅下图) 并创建更多按钮，你将看到它们的外观和行为类似于自定义按钮，而不像 "默认" 按钮。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-269">If you leave the template editing mode (see the following figure) and create more buttons, you will see that they look and behave like your custom button rather than like the default button.</span></span>

![自定义按钮模板](./media/custom-button-blend-scopeup.gif)

![使用同一模板的多个按钮](./media/custom-button-blend-createmultiplebuttons.png)

<span data-ttu-id="3b3cf-272">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-272">Press F5 to run the application.</span></span> <span data-ttu-id="3b3cf-273">单击按钮，并注意它们的行为方式如何。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-273">Click the buttons and notice how they all behave the same.</span></span>

<span data-ttu-id="3b3cf-274">请记住，在自定义模板时，可以将 <xref:System.Windows.Shapes.Shape.Fill%2A> **innerRectangle** 的属性和 <xref:System.Windows.Shapes.Shape.Stroke%2A> **outerRectangle** 属性设置为模板背景 ( {TemplateBinding background} ) 。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-274">Remember that while you were customizing the template, you set the <xref:System.Windows.Shapes.Shape.Fill%2A> property of **innerRectangle** and the <xref:System.Windows.Shapes.Shape.Stroke%2A> property **outerRectangle** to the template background ({TemplateBinding Background}).</span></span> <span data-ttu-id="3b3cf-275">因此，在设置各个按钮的背景色时，设置的背景将用于各自的属性。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-275">Because of this, when you set the background color of the individual buttons, the background you set will be used for those respective properties.</span></span> <span data-ttu-id="3b3cf-276">立即尝试更改背景。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-276">Try changing the backgrounds now.</span></span> <span data-ttu-id="3b3cf-277">在下图中，使用了不同的渐变。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-277">In the following figure, different gradients are used.</span></span> <span data-ttu-id="3b3cf-278">因此，尽管模板对控件（如按钮）的整体自定义很有用，但仍可以修改具有模板的控件，使其看起来彼此不同。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-278">Therefore, although a template is useful for overall customization of controls like button, controls with templates can still be modified to look different from each other.</span></span>

<span data-ttu-id="3b3cf-279">![具有相同模板、但外观不同的按钮](./media/custom-button-blend-blendconclusion.jpg "custom_button_blend_BlendConclusion")</span><span class="sxs-lookup"><span data-stu-id="3b3cf-279">![Buttons with the same template that look diferent](./media/custom-button-blend-blendconclusion.jpg "custom_button_blend_BlendConclusion")</span></span>

<span data-ttu-id="3b3cf-280">总之，在自定义按钮模板的过程中，已了解如何在 Microsoft Expression Blend 中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3b3cf-280">In conclusion, in the process of customizing a button template you have learned how to do the following in Microsoft Expression Blend:</span></span>

- <span data-ttu-id="3b3cf-281">自定义控件的外观。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-281">Customize the look of a control.</span></span>

- <span data-ttu-id="3b3cf-282">设置属性触发器。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-282">Set property triggers.</span></span> <span data-ttu-id="3b3cf-283">属性触发器非常有用，因为它们可在大多数对象（而不仅仅是控件）上使用。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-283">Property triggers are very useful because they can be used on most objects, not just controls.</span></span>

- <span data-ttu-id="3b3cf-284">设置事件触发器。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-284">Set event triggers.</span></span> <span data-ttu-id="3b3cf-285">事件触发器非常有用，因为它们可在大多数对象（而不仅仅是控件）上使用。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-285">Event triggers are very useful because they can be used on most objects, not just controls.</span></span>

- <span data-ttu-id="3b3cf-286">创建动画。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-286">Create animations.</span></span>

- <span data-ttu-id="3b3cf-287">其他：创建渐变、添加 BitmapEffects、使用转换，并设置对象的基本属性。</span><span class="sxs-lookup"><span data-stu-id="3b3cf-287">Miscellaneous: create gradients, add BitmapEffects, use transforms, and set basic properties of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b3cf-288">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b3cf-288">See also</span></span>

- [<span data-ttu-id="3b3cf-289">使用 XAML 创建按钮</span><span class="sxs-lookup"><span data-stu-id="3b3cf-289">Create a Button by Using XAML</span></span>](walkthrough-create-a-button-by-using-xaml.md)
- [<span data-ttu-id="3b3cf-290">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="3b3cf-290">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="3b3cf-291">动画概述</span><span class="sxs-lookup"><span data-stu-id="3b3cf-291">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="3b3cf-292">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="3b3cf-292">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="3b3cf-293">位图效果概述</span><span class="sxs-lookup"><span data-stu-id="3b3cf-293">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
