---
title: 演练：使用 Microsoft Expression Blend 创建按钮
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
- converting [WPF], shape to button
- Expression Blend [WPF Designer]
ms.assetid: ff5037c2-bba7-4cae-8abb-6475b686c48e
ms.openlocfilehash: bcf1c14980556caf7c08be03e12467c86ab3c6a1
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973946"
---
# <a name="walkthrough-create-a-button-by-using-microsoft-expression-blend"></a>演练：使用 Microsoft Expression Blend 创建按钮

本演练逐步介绍如何使用 Microsoft Expression Blend 创建 WPF 自定义按钮。

> [!IMPORTANT]
> Microsoft Expression Blend 的工作方式 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 是生成，然后将其编译为生成可执行程序。 如果你希望直接使用 XAML，则还有另一个演练，它使用 XAML 和 Visual Studio （而不是 Blend）创建与此应用程序相同的应用程序。 有关详细信息，请参阅 [使用 XAML 创建按钮](walkthrough-create-a-button-by-using-xaml.md) 。

下图显示了您将创建的自定义按钮。

![你将创建的自定义按钮](./media/custom-button-blend-intro.jpg)

## <a name="convert-a-shape-to-a-button"></a>将形状转换为按钮

在本演练的第一部分中，你将创建自定义按钮的自定义外观。 为此，首先要将矩形转换为按钮。 然后，将其他形状添加到按钮的模板中，从而创建一个更复杂的 "按钮" 按钮。 为什么不使用常规按钮启动并对其进行自定义？ 因为按钮具有不需要的内置功能，对于自定义按钮，从矩形开始更容易。

### <a name="to-create-a-new-project-in-expression-blend"></a>在 Expression Blend 中创建新项目

1. 开始 Expression Blend。  (单击 " **开始**"，指向 " **所有程序**"，指向 " **microsoft expression**"，然后单击 " **microsoft expression Blend**"。 ) 

2. 如果需要，最大化应用程序。

3. 在“文件”菜单上，单击“新建项目”。

4. 选择 **标准应用程序 ( .exe)**。

5. 为项目命名 `CustomButton` 并按 **"确定"**。

此时，您有一个空白 WPF 项目。 可以按 F5 运行该应用程序。 正如您所料，应用程序只包含一个空白窗口。 接下来，创建一个圆角矩形，并将其转换为按钮。

### <a name="to-convert-a-rectangle-to-a-button"></a>将矩形转换为按钮

1. **将窗口背景属性设置为黑色：** 选择窗口，单击 " **属性" 选项卡**，然后将 <xref:System.Windows.Controls.Control.Background%2A> 属性设置 `Black` 为。

    ![如何将按钮的背景设置为黑色](./media/custom-button-blend-changebackground.png)

2. **在窗口上的按钮大小约绘制一个矩形：** 选择左侧工具面板上的 "矩形" 工具，然后将该矩形拖到窗口上。

    ![如何绘制矩形](./media/custom-button-blend-drawrect.png)

3. 将 **矩形的角取整：** 拖动矩形的控制点或直接设置 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 和 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 属性。 将和的值 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 设置 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 为20。

    ![如何使矩形的角变为圆角](./media/custom-button-blend-roundcorners.png)

4. **将矩形更改为按钮：** 选择该矩形。 单击 " **工具** " 菜单上的 " **生成" 按钮**。

    ![如何使形状变为按钮](./media/custom-button-blend-makebutton.png)

5. **指定样式/模板的作用域：** 将显示如下所示的对话框。

    ![“创建样式资源”对话框](./media/custom-button-blend-makebutton2.gif)

    对于 **资源名称 (键)**，选择 " **应用到所有** 项"。  这会使生成的样式和按钮模板应用于所有作为按钮的对象。 对于 **中** 的 "定义"，选择 " **应用程序**"。 这会使生成的样式和按钮模板在整个应用程序中的作用域。 在这两个框中设置值时，按钮样式和模板应用于整个应用程序中的所有按钮，并且在应用程序中创建的任何按钮默认情况下都使用此模板。

## <a name="edit-the-button-template"></a>编辑按钮模板

现在，你已有一个已更改为按钮的矩形。 在本部分中，您将修改该按钮的模板，并进一步自定义其外观。

### <a name="to-edit-the-button-template-to-change-the-button-appearance"></a>编辑按钮模板以更改按钮外观

1. **进入编辑模板视图：** 若要进一步自定义按钮的外观，需要编辑按钮模板。 此模板是在将矩形转换为按钮时创建的。 若要编辑按钮模板，请右键单击该按钮，然后选择 " **编辑控件部件" (模板)** 然后单击 " **编辑模板**"。

    ![如何编辑模板](./media/custom-button-blend-edittemplate.jpg)

    请注意，在模板编辑器中，按钮现在分隔为 <xref:System.Windows.Shapes.Rectangle> 和 <xref:System.Windows.Controls.ContentPresenter> 。 <xref:System.Windows.Controls.ContentPresenter>用于在按钮内显示内容 (例如，字符串 "button" ) 。 矩形和都在 <xref:System.Windows.Controls.ContentPresenter> 内进行布局 <xref:System.Windows.Controls.Grid> 。

    ![用于展示矩形的组件](./media/custom-button-blend-templatepanel.png)

2. **更改模板组件的名称：** 右键单击模板清单中的矩形，将 <xref:System.Windows.Shapes.Rectangle> 名称从 "[rectangle]" 更改为 "outerRectangle"，并将 "[system.windows.controls.contentpresenter>]" 更改为 "myContentPresenter"。

    ![如何重命名模板的组件](./media/custom-button-blend-renamecomponents.png)

3. **更改矩形，使其在 (中为空，如环形) ：** 选择 **outerRectangle** 并将设置 <xref:System.Windows.Shapes.Shape.Fill%2A> 为 "透明"，并设置 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 为5。

    ![如何使矩形为空](./media/custom-button-blend-changerectproperties.png)

    然后，将设置 <xref:System.Windows.Shapes.Shape.Stroke%2A> 为模板的任何颜色。 为此，请单击 " **笔划**" 旁边的小白色框，选择 " **CustomExpression**"，然后在对话框中键入 "{TemplateBinding Background}"。

    ![如何设置和使用模板的颜色](./media/custom-button-blend-templatestroke.png)

4. **创建内部矩形：** 现在，请创建另一个矩形 (将其命名为 "innerRectangle" ) 并将其在 **outerRectangle** 内以对称的位置定位。 对于这种类型的工作，你可能想要进行缩放以使编辑区域中的按钮变大。

    > [!NOTE]
    > 例如，矩形的外观可能不同 (例如，它可能具有圆角) 。

    ![如何在一个矩形内创建另一个矩形](./media/custom-button-blend-innerrectangleproperties.png)

5. **将 System.windows.controls.contentpresenter> 移到顶部：** 此时，可能不会再看到文本 "Button"。 如果是这样，则这是因为 **innerRectangle** 位于 **myContentPresenter** 的顶层。 若要解决此问题，请将 **myContentPresenter** 拖到下面的 **innerRectangle**。 重定位矩形和 **myContentPresenter** ，使其看起来类似于下面的内容。

    > [!NOTE]
    > 此外，还可以通过右键单击 **myContentPresenter** 并按 " **发送前**" 将其定位在顶部。

    ![如何将一个按钮移到另一个按钮的上面](./media/custom-button-blend-innerrectangle2.png)

6. **更改 innerRectangle 的外观：** 将 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 、 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 和值设置 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 为20。 此外， <xref:System.Windows.Shapes.Shape.Fill%2A> 使用自定义表达式 "{TemplateBinding background}" 将设置为模板的背景 ) 并将其设置 <xref:System.Windows.Shapes.Shape.Stroke%2A> 为 "透明"。 请注意，和的 InnerRectangle 的设置与 OuterRectangle 的设置 <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Shape.Stroke%2A> 相反。  

    ![如何更改矩形的外观](./media/custom-button-blend-glassrectangleproperties1.png)

7. **在顶部添加玻璃层：** 自定义按钮外观的最后一项是在顶部添加玻璃层。 此玻璃层包含第三个矩形。 由于玻璃将覆盖整个按钮，因此，玻璃矩形在维度中类似于 **outerRectangle**。 因此，只需制作一份 **outerRectangle** 副本就能创建该矩形。 突出显示 **outerRectangle** ，并使用 Ctrl + C 和 Ctrl + V 制作副本。 将此新矩形命名为 "glassCube"。

8. **如有必要，重定位 glassCube：** 如果 **glassCube** 尚未定位，使其覆盖整个按钮，请将其拖动到位置。

9. **为 glassCube 指定一个与 outerRectangle 略有不同的形状：** 更改 **glassCube** 的属性。 首先将 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 和 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 属性更改为10，将更改 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 为2。

    ![glassCube 的外观设置](./media/custom-button-blend-glasscubeappearance.gif)

10. **使 glassCube 看起来像玻璃：**<xref:System.Windows.Shapes.Shape.Fill%2A>通过使用线性渐变（75% 不透明）将设置为 glassy 外观，在大约均匀间隔的时间段内，在白色和透明之间交替变化。 这是将梯度停止点设置为：

    - 梯度停止点1：白色，Alpha 值为75%

    - 梯度停止点2：透明

    - 梯度停止点3：白色，Alpha 值为75%

    - 梯度停止点4：透明

    - 梯度停止点5：白色，Alpha 值为75%

    - 梯度停止点6：透明

    这会创建一个 "波浪形" 玻璃外观。

    ![看起来像玻璃的矩形](./media/custom-button-blend-glassrectangleproperties2.png)

11. **隐藏玻璃层：** 现在，你已经了解了 glassy 层的外观，接下来请进入 "**属性" 面板** 的 "**外观" 窗格**，并将不透明度设置为0% 以隐藏它。 在前面的部分中，我们将使用属性触发器和事件来显示和操作玻璃层。

    ![如何隐藏玻璃矩形](./media/custom-button-glassrectangleproperties3.gif)

## <a name="customize-the-button-behavior"></a>自定义按钮行为

此时，您已通过编辑模板的模板对该按钮的显示进行了自定义，但该按钮不会对用户操作做出反应 (例如，通过鼠标悬停、接收焦点和单击操作来更改外观。 ) 接下来的两个过程演示如何在自定义按钮中生成类似的行为。 我们将从简单的属性触发器开始，然后添加事件触发器和动画。

### <a name="to-set-property-triggers"></a>设置属性触发器

1. **创建新的属性触发器：** 选择 **glassCube** 后，在 "**触发器**" 面板中单击 " **+ 属性**" (参阅下一步骤) 下图。 这将创建一个具有默认属性触发器的属性触发器。

2. **将 system.windows.uielement.ismouseover 用作触发器使用的属性：** 将属性更改为 <xref:System.Windows.UIElement.IsMouseOver%2A> 。 当 <xref:System.Windows.UIElement.IsMouseOver%2A> `true` 用户用鼠标) 指向按钮时，这会使属性触发器 (激活。

    ![如何在属性上设置触发器](./media/custom-button-blend-ismousedoverpropertytrigger.png)

3. **System.windows.uielement.ismouseover 触发 glassCube 的100% 的不透明度：** 请注意， **触发器记录位于** (参阅上图) 。 这意味着，在记录时对 **glassCube** 属性值所做的任何更改都将成为在为时进行的操作 <xref:System.Windows.UIElement.IsMouseOver%2A> `true` 。 录制时，将 <xref:System.Windows.UIElement.Opacity%2A> **glassCube** 的更改为100%。

    ![如何设置按钮的不透明度](./media/custom-button-blend-ismousedoverpropertytrigger2.gif)

    现在，您已创建了第一个属性触发器。 请注意，编辑器的 " **触发器" 面板** 已将 <xref:System.Windows.UIElement.Opacity%2A> 更改为100%。

    ![“触发器”面板](./media/custom-button-blend-propertytriggerinfo.png)

    按 F5 运行应用程序，并将鼠标指针移到按钮的上方和下方。 当鼠标悬停在按钮上并在指针离开时消失时，应会看到玻璃层。

4. **System.windows.uielement.ismouseover 触发器笔划值更改：** 让我们将其他一些操作与触发器相关联 <xref:System.Windows.UIElement.IsMouseOver%2A> 。 录制继续时，请将所选内容从 **glassCube** 切换到 **outerRectangle**。 然后，将 <xref:System.Windows.Shapes.Shape.Stroke%2A> **outerRectangle** 的设置为自定义表达式 "{DynamicResource {X:Static SystemColors. HighlightBrushKey}}"。 这会将设置 <xref:System.Windows.Shapes.Shape.Stroke%2A> 为按钮所使用的典型突出显示颜色。 当鼠标悬停在按钮上时，请按 F5 查看效果。

    ![如何将笔画设置为突出显示颜色](./media/custom-button-blend-ismousedoverpropertytrigger3.png)

5. **System.windows.uielement.ismouseover 触发模糊文本：** 让我们将另一个操作与 <xref:System.Windows.UIElement.IsMouseOver%2A> 属性触发器关联起来。 当玻璃出现在屏幕上时，使该按钮的内容看起来很模糊。 为此，我们可以将模糊应用 <xref:System.Windows.Media.Effects.BitmapEffect> 到 <xref:System.Windows.Controls.ContentPresenter> (**myContentPresenter**) 。

    ![如何使按钮内容变得模糊](./media/custom-button-blend-propertytriggerwithbitmapeffect.png)

    > [!NOTE]
    > 若要在执行搜索之前返回 " **属性" 面板** <xref:System.Windows.Media.Effects.BitmapEffect> ，请清除 **搜索框** 中的文本。

    此时，我们使用了具有多个相关操作的属性触发器来创建鼠标指针进入和离开按钮区域时的突出显示行为。 按钮的另一种典型行为是在 (单击) 时突出显示焦点。 可以通过为属性添加另一个属性触发器来添加此类行为 <xref:System.Windows.UIElement.IsFocused%2A> 。

6. **为 IsFocused 创建属性触发器：** 使用与相同的过程 <xref:System.Windows.UIElement.IsMouseOver%2A> (参阅本部分) 的第一步，为属性创建另一个属性触发器 <xref:System.Windows.UIElement.IsFocused%2A> 。 当 **触发器记录为 on** 时，将以下操作添加到触发器：

    - **glassCube** 获取 <xref:System.Windows.UIElement.Opacity%2A> 100% 的。

    - **outerRectangle** 获取 <xref:System.Windows.Shapes.Shape.Stroke%2A> 自定义表达式值 "{DynamicResource {X:Static SystemColors. HighlightBrushKey}}"。

作为本演练的最后一步，我们将向按钮添加动画。 这些动画将由事件（具体而言是 <xref:System.Windows.UIElement.MouseEnter> 和事件）触发 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 。

### <a name="to-use-event-triggers-and-animations-to-add-interactivity"></a>使用事件触发器和动画添加交互性

1. **创建 MouseEnter 事件触发器：** 添加新的事件触发器，并选择 <xref:System.Windows.UIElement.MouseEnter> 作为要在触发器中使用的事件。

     ![如何创建 MouseEnter 事件触发器](./media/custom-button-blend-mouseovereventtrigger.png)

2. **创建动画时间线：** 接下来，将动画时间线与 <xref:System.Windows.UIElement.MouseEnter> 事件关联。

    ![如何向事件添加动画时间线](./media/custom-button-blend-mouseovereventtrigger2.png)

    按 **"确定"** 创建新的时间线后，" **时间线" 面板** 将显示并在设计面板中显示 "时间线录制已打开"。 这意味着，可以在时间线中开始记录属性更改， () 对属性更改进行动画处理。

    > [!NOTE]
    > 可能需要调整窗口和/或面板的大小以查看显示。

    ![时间线面板](./media/custom-button-blend-mouseovereventtrigger3.png)

3. **创建关键帧：** 若要创建动画，请选择要进行动画处理的对象，在时间线上创建两个或更多关键帧，并为这些关键帧设置要在其中插入动画的属性值。 下图指导您创建关键帧。

    ![如何创建关键帧](./media/custom-button-blend-mouseovereventtrigger4.png)

4. **收缩此关键帧中的 glassCube：** 选择第二个关键帧后，使用 **大小转换** 将 **glassCube** 的大小缩小到其完整大小的90%。

    ![如何缩小按钮](./media/custom-button-blend-sizetransform.png)

    按 F5 运行该应用程序。 将鼠标指针移到按钮上。 请注意，玻璃层会在按钮上缩小。

5. **创建另一个事件触发器并将不同的动画与之关联：** 让我们再添加一个动画。 使用类似的过程来创建上一个事件触发器动画：

    1. 使用事件创建新的事件触发器 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 。

    2. 将新时间线与 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件关联。

        ![如何创建新的时间线](./media/custom-button-blend-clickeventtrigger1.png)

    3. 对于此时间线，请创建两个关键帧，一个为0.0 秒，第二个关键帧0.3 秒。

    4. 突出显示处于0.3 秒的关键帧后，将 **旋转变换角度** 设置为360度。

        ![如何创建旋转变换](./media/custom-button-blend-rotatetransform.gif)

    5. 按 F5 运行该应用程序。 单击按钮。 请注意，玻璃层会旋转。

## <a name="conclusion"></a>结束语

已完成自定义按钮。 使用应用于应用程序中所有按钮的按钮模板执行此操作。 如果你退出模板编辑模式 (参阅下图) 并创建更多按钮，你将看到它们的外观和行为类似于自定义按钮，而不像 "默认" 按钮。

![自定义按钮模板](./media/custom-button-blend-scopeup.gif)

![使用同一模板的多个按钮](./media/custom-button-blend-createmultiplebuttons.png)

按 F5 运行该应用程序。 单击按钮，并注意它们的行为方式如何。

请记住，在自定义模板时，可以将 <xref:System.Windows.Shapes.Shape.Fill%2A> **innerRectangle** 的属性和 <xref:System.Windows.Shapes.Shape.Stroke%2A> **outerRectangle** 属性设置为模板背景 ( {TemplateBinding background} ) 。 因此，在设置各个按钮的背景色时，设置的背景将用于各自的属性。 立即尝试更改背景。 在下图中，使用了不同的渐变。 因此，尽管模板对控件（如按钮）的整体自定义很有用，但仍可以修改具有模板的控件，使其看起来彼此不同。

![具有相同模板、但外观不同的按钮](./media/custom-button-blend-blendconclusion.jpg "custom_button_blend_BlendConclusion")

总之，在自定义按钮模板的过程中，已了解如何在 Microsoft Expression Blend 中执行以下操作：

- 自定义控件的外观。

- 设置属性触发器。 属性触发器非常有用，因为它们可在大多数对象（而不仅仅是控件）上使用。

- 设置事件触发器。 事件触发器非常有用，因为它们可在大多数对象（而不仅仅是控件）上使用。

- 创建动画。

- 其他：创建渐变、添加 BitmapEffects、使用转换，并设置对象的基本属性。

## <a name="see-also"></a>另请参阅

- [使用 XAML 创建按钮](walkthrough-create-a-button-by-using-xaml.md)
- [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [动画概述](../graphics-multimedia/animation-overview.md)
- [使用纯色和渐变进行绘制概述](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [位图效果概述](../graphics-multimedia/bitmap-effects-overview.md)
