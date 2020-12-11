---
title: 样式和模板
description: 了解 Windows Presentation Foundation 中的 XAML 资源 (WPF) .NET Framework。 了解与样式和主题相关的 XAML 资源类型。
author: adegeo
ms.author: adegeo
ms.date: 09/09/2019
ms.topic: overview
dev_langs:
- csharp
- vb
ms.openlocfilehash: 69418559fd76ec8d90860189125003a8dcaa8c74
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970456"
---
# <a name="styles-and-templates-in-wpf"></a><span data-ttu-id="d89b3-104">WPF 中的样式和模板</span><span class="sxs-lookup"><span data-stu-id="d89b3-104">Styles and templates in WPF</span></span>

<span data-ttu-id="d89b3-105">Windows Presentation Foundation (WPF) 样式设置和模板化是指一套功能，这套功能使开发者和设计者能够为其产品创建极具视觉表现力的效果和一致的外观。</span><span class="sxs-lookup"><span data-stu-id="d89b3-105">Windows Presentation Foundation (WPF) styling and templating refer to a suite of features that let developers and designers create visually compelling effects and a consistent appearance for their product.</span></span> <span data-ttu-id="d89b3-106">自定义应用的外观时，需要一个强大的样式设置和模板化模型，以便维护和共享应用内部和应用之间的外观。</span><span class="sxs-lookup"><span data-stu-id="d89b3-106">When customizing the appearance of an app, you want a strong styling and templating model that enables maintenance and sharing of appearance within and among apps.</span></span> <span data-ttu-id="d89b3-107">WPF 就提供了这样的模型。</span><span class="sxs-lookup"><span data-stu-id="d89b3-107">WPF provides that model.</span></span>

<span data-ttu-id="d89b3-108">WPF 样式设置模型的另一项功能是将呈现与逻辑分离。</span><span class="sxs-lookup"><span data-stu-id="d89b3-108">Another feature of the WPF styling model is the separation of presentation and logic.</span></span> <span data-ttu-id="d89b3-109">设计者可以仅使用 XAML 处理应用外观，与此同时开发者使用 C# 或 Visual Basic 处理编程逻辑。</span><span class="sxs-lookup"><span data-stu-id="d89b3-109">Designers can work on the appearance of an app by using only XAML at the same time that developers work on the programming logic by using C# or Visual Basic.</span></span>

<span data-ttu-id="d89b3-110">本概述侧重于应用的样式设置和模板化两方面，不讨论任何数据绑定概念。</span><span class="sxs-lookup"><span data-stu-id="d89b3-110">This overview focuses on the styling and templating aspects of the app and doesn't discuss any data-binding concepts.</span></span> <span data-ttu-id="d89b3-111">有关数据绑定的信息，请参阅[数据绑定概述](../data/data-binding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d89b3-111">For information about data binding, see [Data Binding Overview](../data/data-binding-overview.md).</span></span>

<span data-ttu-id="d89b3-112">了解资源很重要，正是这些资源使样式和模板能够重复使用。</span><span class="sxs-lookup"><span data-stu-id="d89b3-112">It's important to understand resources, which are what enable styles and templates to be reused.</span></span> <span data-ttu-id="d89b3-113">有关资源的详细信息，请参阅 [XAML 资源](../advanced/xaml-resources-define.md)。</span><span class="sxs-lookup"><span data-stu-id="d89b3-113">For more information about resources, see [XAML Resources](../advanced/xaml-resources-define.md).</span></span>

## <a name="sample"></a><span data-ttu-id="d89b3-114">示例</span><span class="sxs-lookup"><span data-stu-id="d89b3-114">Sample</span></span>

<span data-ttu-id="d89b3-115">本概述中提供的示例代码基于下图所示的[简单照片浏览应用程序](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="d89b3-115">The sample code provided in this overview is based on a [simple photo browsing application](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating) shown in the following illustration.</span></span>

<span data-ttu-id="d89b3-116">![带样式的 ListView](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")</span><span class="sxs-lookup"><span data-stu-id="d89b3-116">![Styled ListView](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")</span></span>

<span data-ttu-id="d89b3-117">此简单照片示例使用样式设置和模板化创建极具视觉表现力的用户体验。</span><span class="sxs-lookup"><span data-stu-id="d89b3-117">This simple photo sample uses styling and templating to create a visually compelling user experience.</span></span> <span data-ttu-id="d89b3-118">该示例具有两个 <xref:System.Windows.Controls.TextBlock> 元素和一个绑定到图像列表的 <xref:System.Windows.Controls.ListBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="d89b3-118">The sample has two <xref:System.Windows.Controls.TextBlock> elements and a <xref:System.Windows.Controls.ListBox> control that is bound to a list of images.</span></span>

<span data-ttu-id="d89b3-119">有关完整示例，请参阅[样式设置和模板化示例简介](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="d89b3-119">For the complete sample, see [Introduction to Styling and Templating Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="styles"></a><span data-ttu-id="d89b3-120">样式</span><span class="sxs-lookup"><span data-stu-id="d89b3-120">Styles</span></span>

<span data-ttu-id="d89b3-121">可以将 <xref:System.Windows.Style> 视为一种将一组属性值应用到多个元素的便捷方法。</span><span class="sxs-lookup"><span data-stu-id="d89b3-121">You can think of a <xref:System.Windows.Style> as a convenient way to apply a set of property values to multiple elements.</span></span> <span data-ttu-id="d89b3-122">可以对从 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement> 派生的任何元素（如 <xref:System.Windows.Window> 或 <xref:System.Windows.Controls.Button>）使用样式。</span><span class="sxs-lookup"><span data-stu-id="d89b3-122">You can use a style on any element that derives from <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement> such as a <xref:System.Windows.Window> or a <xref:System.Windows.Controls.Button>.</span></span>

<span data-ttu-id="d89b3-123">声明样式的最常见方法是在 XAML 文件的 `Resources` 部分中声明为资源。</span><span class="sxs-lookup"><span data-stu-id="d89b3-123">The most common way to declare a style is as a resource in the `Resources` section in a XAML file.</span></span> <span data-ttu-id="d89b3-124">样式是一种资源，因此它们遵从适用于所有资源的相同范围规则。</span><span class="sxs-lookup"><span data-stu-id="d89b3-124">Because styles are resources, they obey the same scoping rules that apply to all resources.</span></span> <span data-ttu-id="d89b3-125">简而言之，声明样式的位置会影响样式的应用范围。</span><span class="sxs-lookup"><span data-stu-id="d89b3-125">Put simply, where you declare a style affects where the style can be applied.</span></span> <span data-ttu-id="d89b3-126">例如，如果在应用定义 XAML 文件的根元素中声明样式，则该样式可以在应用中的任何位置使用。</span><span class="sxs-lookup"><span data-stu-id="d89b3-126">For example, if you declare the style in the root element of your app definition XAML file, the style can be used anywhere in your app.</span></span>

<span data-ttu-id="d89b3-127">例如，以下 XAML 代码为 `TextBlock` 声明了两个样式，一个自动应用于所有 `TextBlock` 元素，另一个则必须显式引用。</span><span class="sxs-lookup"><span data-stu-id="d89b3-127">For example, the following XAML code declares two styles for a `TextBlock`, one automatically applied to all `TextBlock` elements, and another that must be explicitly referenced.</span></span>

[!code-xaml[SnippetDefaultTextBlockStyleBasedOn](./snippets/styles-templates-overview/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

<span data-ttu-id="d89b3-128">下面举例说明了如何使用上面声明的样式。</span><span class="sxs-lookup"><span data-stu-id="d89b3-128">Here is an example of the styles declared above being used.</span></span>

[!code-xaml[SnippetTextBlocksExplicit](./snippets/styles-templates-overview/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

![带样式的 TextBlock](./media/styles-and-templates-overview/stylingintro-textblocks.png)

## <a name="controltemplates"></a><span data-ttu-id="d89b3-130">ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d89b3-130">ControlTemplates</span></span>

<span data-ttu-id="d89b3-131">在 WPF 中，控件的 <xref:System.Windows.Controls.ControlTemplate> 用于定义控件的外观。</span><span class="sxs-lookup"><span data-stu-id="d89b3-131">In WPF, the <xref:System.Windows.Controls.ControlTemplate> of a control defines the appearance of the control.</span></span> <span data-ttu-id="d89b3-132">可以通过定义新的 <xref:System.Windows.Controls.ControlTemplate> 并将其分配给控件来更改控件的结构和外观。</span><span class="sxs-lookup"><span data-stu-id="d89b3-132">You can change the structure and appearance of a control by defining a new <xref:System.Windows.Controls.ControlTemplate> and assigning it to a control.</span></span> <span data-ttu-id="d89b3-133">在许多情况下，模板提供了足够的灵活性，从而无需自行编写自定义控件。</span><span class="sxs-lookup"><span data-stu-id="d89b3-133">In many cases, templates give you enough flexibility so that you do not have to write your own custom controls.</span></span>

<span data-ttu-id="d89b3-134">每个控件都有一个分配给 [Control.Template](xref:System.Windows.Controls.Control.Template) 属性的默认模板。</span><span class="sxs-lookup"><span data-stu-id="d89b3-134">Each control has a default template assigned to the [Control.Template](xref:System.Windows.Controls.Control.Template) property.</span></span> <span data-ttu-id="d89b3-135">该模板将控件的视觉呈现与控件的功能关联起来。</span><span class="sxs-lookup"><span data-stu-id="d89b3-135">The template connects the visual presentation of the control with the control's capabilities.</span></span> <span data-ttu-id="d89b3-136">因为在 XAML 中定义了模板，所以无需编写任何代码即可更改控件的外观。</span><span class="sxs-lookup"><span data-stu-id="d89b3-136">Because you define a template in XAML, you can change the control's appearance without writing any code.</span></span> <span data-ttu-id="d89b3-137">每个模板都是为特定控件（例如 <xref:System.Windows.Controls.Button>）设计的。</span><span class="sxs-lookup"><span data-stu-id="d89b3-137">Each template is designed for a specific control, such as a <xref:System.Windows.Controls.Button>.</span></span>

<span data-ttu-id="d89b3-138">通常在 XAML 文件的 `Resources` 部分中将模板声明为资源。</span><span class="sxs-lookup"><span data-stu-id="d89b3-138">Commonly you declare a template as a resource on the `Resources` section of a XAML file.</span></span> <span data-ttu-id="d89b3-139">与所有资源一样，将应用范围规则。</span><span class="sxs-lookup"><span data-stu-id="d89b3-139">As with all resources, scoping rules apply.</span></span>

<span data-ttu-id="d89b3-140">控件模板比样式复杂得多。</span><span class="sxs-lookup"><span data-stu-id="d89b3-140">Control templates are a lot more involved than a style.</span></span> <span data-ttu-id="d89b3-141">这是因为控件模板重写了整个控件的视觉外观，而样式只是将属性更改应用于现有控件。</span><span class="sxs-lookup"><span data-stu-id="d89b3-141">This is because the control template rewrites the visual appearance of the entire control, while a style simply applies property changes to the existing control.</span></span> <span data-ttu-id="d89b3-142">但是，控件模板是通过设置 [Control.Template](xref:System.Windows.Controls.Control.Template) 属性来应用的，因此可以使用样式来定义或设置模板。</span><span class="sxs-lookup"><span data-stu-id="d89b3-142">However, since the template of a control is applied by setting the [Control.Template](xref:System.Windows.Controls.Control.Template) property, you can use a style to define or set a template.</span></span>

<span data-ttu-id="d89b3-143">设计器通常允许创建现有模板的副本并进行修改。</span><span class="sxs-lookup"><span data-stu-id="d89b3-143">Designers generally allow you to create a copy of an existing template and modify it.</span></span> <span data-ttu-id="d89b3-144">例如，在 Visual Studio WPF 设计器中，选择一个 `CheckBox` 控件，然后右键单击并选择“编辑模板” > “创建副本”   。</span><span class="sxs-lookup"><span data-stu-id="d89b3-144">For example, in the Visual Studio WPF designer, select a `CheckBox` control, and then right-click and select **Edit template** > **Create a copy**.</span></span> <span data-ttu-id="d89b3-145">此命令会生成一个 *用于定义模板的样式*。</span><span class="sxs-lookup"><span data-stu-id="d89b3-145">This command generates a *style that defines a template*.</span></span>

```xaml
<Style x:Key="CheckBoxStyle1" TargetType="{x:Type CheckBox}">
    <Setter Property="FocusVisualStyle" Value="{StaticResource FocusVisual1}"/>
    <Setter Property="Background" Value="{StaticResource OptionMark.Static.Background1}"/>
    <Setter Property="BorderBrush" Value="{StaticResource OptionMark.Static.Border1}"/>
    <Setter Property="Foreground" Value="{DynamicResource {x:Static SystemColors.ControlTextBrushKey}}"/>
    <Setter Property="BorderThickness" Value="1"/>
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="{x:Type CheckBox}">
                <Grid x:Name="templateRoot" Background="Transparent" SnapsToDevicePixels="True">
                    <Grid.ColumnDefinitions>
                        <ColumnDefinition Width="Auto"/>
                        <ColumnDefinition Width="*"/>
                    </Grid.ColumnDefinitions>
                    <Border x:Name="checkBoxBorder" Background="{TemplateBinding Background}" BorderThickness="{TemplateBinding BorderThickness}" BorderBrush="{TemplateBinding BorderBrush}" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="1" VerticalAlignment="{TemplateBinding VerticalContentAlignment}">
                        <Grid x:Name="markGrid">
                            <Path x:Name="optionMark" Data="F1 M 9.97498,1.22334L 4.6983,9.09834L 4.52164,9.09834L 0,5.19331L 1.27664,3.52165L 4.255,6.08833L 8.33331,1.52588e-005L 9.97498,1.22334 Z " Fill="{StaticResource OptionMark.Static.Glyph1}" Margin="1" Opacity="0" Stretch="None"/>
                            <Rectangle x:Name="indeterminateMark" Fill="{StaticResource OptionMark.Static.Glyph1}" Margin="2" Opacity="0"/>
                        </Grid>
                    </Border>
                    <ContentPresenter x:Name="contentPresenter" Grid.Column="1" Focusable="False" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" RecognizesAccessKey="True" SnapsToDevicePixels="{TemplateBinding SnapsToDevicePixels}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}"/>
                </Grid>
                <ControlTemplate.Triggers>
                    <Trigger Property="HasContent" Value="true">
                        <Setter Property="FocusVisualStyle" Value="{StaticResource OptionMarkFocusVisual1}"/>
                        <Setter Property="Padding" Value="4,-1,0,0"/>

... content removed to save space ...
```

<span data-ttu-id="d89b3-146">通过编辑模板副本可以很好地了解模板的工作原理。</span><span class="sxs-lookup"><span data-stu-id="d89b3-146">Editing a copy of a template is a great way to learn how templates work.</span></span> <span data-ttu-id="d89b3-147">与其新建一个空白模板，不如编辑副本并更改视觉呈现的某些方面来得简单。</span><span class="sxs-lookup"><span data-stu-id="d89b3-147">Instead of creating a new blank template, it's easier to edit a copy and change a few aspects of the visual presentation.</span></span>

<span data-ttu-id="d89b3-148">有关示例，请参阅[为控件创建模板](how-to-create-apply-template.md)。</span><span class="sxs-lookup"><span data-stu-id="d89b3-148">For an example, see [Create a template for a control](how-to-create-apply-template.md).</span></span>

### <a name="templatebinding"></a><span data-ttu-id="d89b3-149">TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="d89b3-149">TemplateBinding</span></span>

<span data-ttu-id="d89b3-150">你可能已经注意到，上一部分中定义的模板资源使用了 [TemplateBinding 标记扩展](../advanced/templatebinding-markup-extension.md)。</span><span class="sxs-lookup"><span data-stu-id="d89b3-150">You may have noticed that the template resource defined in the previous section uses the [TemplateBinding Markup Extension](../advanced/templatebinding-markup-extension.md).</span></span> <span data-ttu-id="d89b3-151">对于模板方案来说，`TemplateBinding` 是绑定的优化形式，类似于使用 `{Binding RelativeSource={RelativeSource TemplatedParent}}` 构造的绑定。</span><span class="sxs-lookup"><span data-stu-id="d89b3-151">A `TemplateBinding` is an optimized form of a binding for template scenarios, analogous to a binding constructed with `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="d89b3-152">`TemplateBinding` 可用于将模板的各个部分绑定到控件的各个属性。</span><span class="sxs-lookup"><span data-stu-id="d89b3-152">`TemplateBinding` is useful for binding parts of the template to properties of the control.</span></span> <span data-ttu-id="d89b3-153">例如，每个控件都有一个 <xref:System.Windows.Controls.Control.BorderThickness> 属性。</span><span class="sxs-lookup"><span data-stu-id="d89b3-153">For example, each control has a <xref:System.Windows.Controls.Control.BorderThickness> property.</span></span> <span data-ttu-id="d89b3-154">可使用 `TemplateBinding` 管理此控件设置影响模板中的哪个元素。</span><span class="sxs-lookup"><span data-stu-id="d89b3-154">Use a `TemplateBinding` to manage which element in the template is affected by this control setting.</span></span>

### <a name="contentcontrol-and-itemscontrol"></a><span data-ttu-id="d89b3-155">ContentControl 和 ItemsControl</span><span class="sxs-lookup"><span data-stu-id="d89b3-155">ContentControl and ItemsControl</span></span>

<span data-ttu-id="d89b3-156">如果在 <xref:System.Windows.Controls.ContentControl> 的 <xref:System.Windows.Controls.ControlTemplate> 中声明了 <xref:System.Windows.Controls.ContentPresenter>，<xref:System.Windows.Controls.ContentPresenter> 将自动绑定到 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 和 <xref:System.Windows.Controls.ContentControl.Content%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="d89b3-156">If a <xref:System.Windows.Controls.ContentPresenter> is declared in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Controls.ContentControl>, the <xref:System.Windows.Controls.ContentPresenter> will automatically bind to the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> and <xref:System.Windows.Controls.ContentControl.Content%2A> properties.</span></span> <span data-ttu-id="d89b3-157">同样，<xref:System.Windows.Controls.ItemsControl> 的 <xref:System.Windows.Controls.ControlTemplate> 中的 <xref:System.Windows.Controls.ItemsPresenter> 将自动绑定到 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 和 <xref:System.Windows.Controls.ItemsControl.Items%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="d89b3-157">Likewise, an <xref:System.Windows.Controls.ItemsPresenter> that is in the <xref:System.Windows.Controls.ControlTemplate> of an <xref:System.Windows.Controls.ItemsControl> will automatically bind to the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A> properties.</span></span>

## <a name="datatemplates"></a><span data-ttu-id="d89b3-158">DataTemplate</span><span class="sxs-lookup"><span data-stu-id="d89b3-158">DataTemplates</span></span>

<span data-ttu-id="d89b3-159">在此示例应用中，有一个绑定到照片列表的 <xref:System.Windows.Controls.ListBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="d89b3-159">In this sample app, there is a <xref:System.Windows.Controls.ListBox> control that is bound to a list of photos.</span></span>

[!code-xaml[ListBox](./snippets/styles-templates-overview/csharp/Window3.xaml#SnippetListBox)]

<span data-ttu-id="d89b3-160">此 <xref:System.Windows.Controls.ListBox> 当前如下所示。</span><span class="sxs-lookup"><span data-stu-id="d89b3-160">This <xref:System.Windows.Controls.ListBox> currently looks like the following.</span></span>

<span data-ttu-id="d89b3-161">![应用模板之前的 ListBox](./media/styles-and-templates-overview/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")</span><span class="sxs-lookup"><span data-stu-id="d89b3-161">![ListBox before applying template](./media/styles-and-templates-overview/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")</span></span>

<span data-ttu-id="d89b3-162">大多数控件都具有某些类型的内容，并且该内容通常来自要绑定到的数据。</span><span class="sxs-lookup"><span data-stu-id="d89b3-162">Most controls have some type of content, and that content often comes from data that you are binding to.</span></span> <span data-ttu-id="d89b3-163">在此示例中，数据是照片列表。</span><span class="sxs-lookup"><span data-stu-id="d89b3-163">In this sample, the data is the list of photos.</span></span> <span data-ttu-id="d89b3-164">在 WPF 中，使用 <xref:System.Windows.DataTemplate> 定义数据的视觉表示形式。</span><span class="sxs-lookup"><span data-stu-id="d89b3-164">In WPF, you use a <xref:System.Windows.DataTemplate> to define the visual representation of data.</span></span> <span data-ttu-id="d89b3-165">基本上，放入 <xref:System.Windows.DataTemplate> 的内容决定了数据在呈现的应用中的外观。</span><span class="sxs-lookup"><span data-stu-id="d89b3-165">Basically, what you put into a <xref:System.Windows.DataTemplate> determines what the data looks like in the rendered app.</span></span>

<span data-ttu-id="d89b3-166">在示例应用中，每个自定义 `Photo` 对象都有一个字符串类型的 `Source` 属性，用于指定图像的文件路径。</span><span class="sxs-lookup"><span data-stu-id="d89b3-166">In our sample app, each custom `Photo` object has a `Source` property of type string that specifies the file path of the image.</span></span> <span data-ttu-id="d89b3-167">当前，照片对象显示为文件路径。</span><span class="sxs-lookup"><span data-stu-id="d89b3-167">Currently, the photo objects appear as file paths.</span></span>

[!code-csharp[PhotoClass](./snippets/styles-templates-overview/csharp/Photo.cs#PhotoClass)]
[!code-vb[PhotoClass](./snippets/styles-templates-overview/vb/Photo.vb#PhotoClass)]

<span data-ttu-id="d89b3-168">若要使照片显示为图像，请将 <xref:System.Windows.DataTemplate> 创建为资源。</span><span class="sxs-lookup"><span data-stu-id="d89b3-168">For the photos to appear as images, you create a <xref:System.Windows.DataTemplate> as a resource.</span></span>

[!code-xaml[DataTemplate](./snippets/styles-templates-overview/csharp/Window4.xaml#SnippetDataTemplate)]

<span data-ttu-id="d89b3-169">请注意，<xref:System.Windows.DataTemplate.DataType%2A> 属性与 <xref:System.Windows.Style> 的 <xref:System.Windows.Style.TargetType%2A> 属性相似。</span><span class="sxs-lookup"><span data-stu-id="d89b3-169">Notice that the <xref:System.Windows.DataTemplate.DataType%2A> property is similar to the <xref:System.Windows.Style.TargetType%2A> property of the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="d89b3-170">如果 <xref:System.Windows.DataTemplate> 在 resources 部分中，则在将 <xref:System.Windows.DataTemplate.DataType%2A> 属性指定为某个类型并且省略 `x:Key` 时，只要该类型出现，就会应用 <xref:System.Windows.DataTemplate>。</span><span class="sxs-lookup"><span data-stu-id="d89b3-170">If your <xref:System.Windows.DataTemplate> is in the resources section, when you specify the <xref:System.Windows.DataTemplate.DataType%2A> property to a type and omit an `x:Key`, the <xref:System.Windows.DataTemplate> is applied whenever that type appears.</span></span> <span data-ttu-id="d89b3-171">始终可以选择为 <xref:System.Windows.DataTemplate> 分配 `x:Key`，然后将其设置为采用 <xref:System.Windows.DataTemplate> 类型的属性（例如 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 属性或 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 属性）的 `StaticResource`。</span><span class="sxs-lookup"><span data-stu-id="d89b3-171">You always have the option to assign the <xref:System.Windows.DataTemplate> with an `x:Key` and then set it as a `StaticResource` for properties that take <xref:System.Windows.DataTemplate> types, such as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> property or the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> property.</span></span>

<span data-ttu-id="d89b3-172">实质上，上述示例中的 <xref:System.Windows.DataTemplate> 定义每当存在 `Photo` 对象时，它都应显示为 <xref:System.Windows.Controls.Border> 内的 <xref:System.Windows.Controls.Image>。</span><span class="sxs-lookup"><span data-stu-id="d89b3-172">Essentially, the <xref:System.Windows.DataTemplate> in the above example defines that whenever there is a `Photo` object, it should appear as an <xref:System.Windows.Controls.Image> within a <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="d89b3-173">有了这个 <xref:System.Windows.DataTemplate>，我们的应用现在如下所示。</span><span class="sxs-lookup"><span data-stu-id="d89b3-173">With this <xref:System.Windows.DataTemplate>, our app now looks like this.</span></span>

<span data-ttu-id="d89b3-174">![照片图](./media/styles-and-templates-overview/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")</span><span class="sxs-lookup"><span data-stu-id="d89b3-174">![Photo image](./media/styles-and-templates-overview/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")</span></span>

<span data-ttu-id="d89b3-175">数据模板化模型提供其他功能。</span><span class="sxs-lookup"><span data-stu-id="d89b3-175">The data templating model provides other features.</span></span> <span data-ttu-id="d89b3-176">例如，如果要使用 <xref:System.Windows.Controls.HeaderedItemsControl> 类型（例如 <xref:System.Windows.Controls.Menu> 或 <xref:System.Windows.Controls.TreeView>）显示包含其他集合的集合数据，可以使用 <xref:System.Windows.HierarchicalDataTemplate>。</span><span class="sxs-lookup"><span data-stu-id="d89b3-176">For example, if you are displaying collection data that contains other collections using a <xref:System.Windows.Controls.HeaderedItemsControl> type such as a <xref:System.Windows.Controls.Menu> or a <xref:System.Windows.Controls.TreeView>, there is the <xref:System.Windows.HierarchicalDataTemplate>.</span></span> <span data-ttu-id="d89b3-177">另一个数据模板化功能是 <xref:System.Windows.Controls.DataTemplateSelector>，该功能允许基于自定义逻辑选择要使用的 <xref:System.Windows.DataTemplate>。</span><span class="sxs-lookup"><span data-stu-id="d89b3-177">Another data templating feature is the <xref:System.Windows.Controls.DataTemplateSelector>, which allows you to choose a <xref:System.Windows.DataTemplate> to use based on custom logic.</span></span> <span data-ttu-id="d89b3-178">有关详细信息，请参阅[数据模板化概述](../data/data-templating-overview.md)，该概述提供不同数据模板化功能的更多深入讨论。</span><span class="sxs-lookup"><span data-stu-id="d89b3-178">For more information, see [Data Templating Overview](../data/data-templating-overview.md), which provides a more in-depth discussion of the different data templating features.</span></span>

## <a name="triggers"></a><span data-ttu-id="d89b3-179">触发器</span><span class="sxs-lookup"><span data-stu-id="d89b3-179">Triggers</span></span>

<span data-ttu-id="d89b3-180">触发器在属性值发生更改或引发事件时设置属性或启动操作，例如动画。</span><span class="sxs-lookup"><span data-stu-id="d89b3-180">A trigger sets properties or starts actions, such as an animation, when a property value changes or when an event is raised.</span></span> <span data-ttu-id="d89b3-181"><xref:System.Windows.Style>、<xref:System.Windows.Controls.ControlTemplate> 和 <xref:System.Windows.DataTemplate> 都具有可包含一组触发器的 `Triggers` 属性。</span><span class="sxs-lookup"><span data-stu-id="d89b3-181"><xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, and <xref:System.Windows.DataTemplate> all have a `Triggers` property that can contain a set of triggers.</span></span> <span data-ttu-id="d89b3-182">触发器分为几种类型。</span><span class="sxs-lookup"><span data-stu-id="d89b3-182">There are several types of triggers.</span></span>

### <a name="propertytriggers"></a><span data-ttu-id="d89b3-183">PropertyTrigger</span><span class="sxs-lookup"><span data-stu-id="d89b3-183">PropertyTriggers</span></span>

<span data-ttu-id="d89b3-184">根据属性的值设置属性值或启动操作的 <xref:System.Windows.Trigger> 称为属性触发器。</span><span class="sxs-lookup"><span data-stu-id="d89b3-184">A <xref:System.Windows.Trigger> that sets property values or starts actions based on the value of a property is called a property trigger.</span></span>

<span data-ttu-id="d89b3-185">若要演示如何使用属性触发器，可以使每个 <xref:System.Windows.Controls.ListBoxItem> 在未选中时部分透明。</span><span class="sxs-lookup"><span data-stu-id="d89b3-185">To demonstrate how to use property triggers, you can make each <xref:System.Windows.Controls.ListBoxItem> partially transparent unless it is selected.</span></span> <span data-ttu-id="d89b3-186">以下样式将 <xref:System.Windows.Controls.ListBoxItem> 的 <xref:System.Windows.UIElement.Opacity%2A> 值设置为 `0.5`。</span><span class="sxs-lookup"><span data-stu-id="d89b3-186">The following style sets the <xref:System.Windows.UIElement.Opacity%2A> value of a <xref:System.Windows.Controls.ListBoxItem> to `0.5`.</span></span> <span data-ttu-id="d89b3-187">但是，当 <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> 属性为 `true` 时，<xref:System.Windows.UIElement.Opacity%2A> 设置为 `1.0`。</span><span class="sxs-lookup"><span data-stu-id="d89b3-187">When the <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> property is `true`, however, the <xref:System.Windows.UIElement.Opacity%2A> is set to `1.0`.</span></span>

[!code-xaml[PropertyTrigger](./snippets/styles-templates-overview/csharp/Window5.xaml#SnippetPropertyTrigger)]

<span data-ttu-id="d89b3-188">此示例使用 <xref:System.Windows.Trigger> 设置属性值，但请注意，<xref:System.Windows.Trigger> 类还有 <xref:System.Windows.TriggerBase.EnterActions%2A> 和 <xref:System.Windows.TriggerBase.ExitActions%2A> 属性，这些属性可使触发器执行操作。</span><span class="sxs-lookup"><span data-stu-id="d89b3-188">This example uses a <xref:System.Windows.Trigger> to set a property value, but note that the <xref:System.Windows.Trigger> class also has the <xref:System.Windows.TriggerBase.EnterActions%2A> and <xref:System.Windows.TriggerBase.ExitActions%2A> properties that enable a trigger to perform actions.</span></span>

<span data-ttu-id="d89b3-189">请注意，<xref:System.Windows.Controls.ListBoxItem> 的 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 属性设置为 `75`。</span><span class="sxs-lookup"><span data-stu-id="d89b3-189">Notice that the <xref:System.Windows.FrameworkElement.MaxHeight%2A> property of the <xref:System.Windows.Controls.ListBoxItem> is set to `75`.</span></span> <span data-ttu-id="d89b3-190">在下图中，第三项是选中的项。</span><span class="sxs-lookup"><span data-stu-id="d89b3-190">In the following illustration, the third item is the selected item.</span></span>

<span data-ttu-id="d89b3-191">![带样式的 ListView](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")</span><span class="sxs-lookup"><span data-stu-id="d89b3-191">![Styled ListView](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")</span></span>

### <a name="eventtriggers-and-storyboards"></a><span data-ttu-id="d89b3-192">EventTrigger 和情节提要</span><span class="sxs-lookup"><span data-stu-id="d89b3-192">EventTriggers and Storyboards</span></span>

<span data-ttu-id="d89b3-193">另一个触发器类型是 <xref:System.Windows.EventTrigger>，用于根据某个事件的发生启动一组操作。</span><span class="sxs-lookup"><span data-stu-id="d89b3-193">Another type of trigger is the <xref:System.Windows.EventTrigger>, which starts a set of actions based on the occurrence of an event.</span></span> <span data-ttu-id="d89b3-194">例如，以下 <xref:System.Windows.EventTrigger> 对象指定当鼠标指针进入 <xref:System.Windows.Controls.ListBoxItem> 时，<xref:System.Windows.FrameworkElement.MaxHeight%2A> 属性在 `0.2` 秒的时间内动画化为值 `90`。</span><span class="sxs-lookup"><span data-stu-id="d89b3-194">For example, the following <xref:System.Windows.EventTrigger> objects specify that when the mouse pointer enters the <xref:System.Windows.Controls.ListBoxItem>, the <xref:System.Windows.FrameworkElement.MaxHeight%2A> property animates to a value of `90` over a `0.2` second period.</span></span> <span data-ttu-id="d89b3-195">当鼠标离开该项时，属性在 `1` 秒的时间内返回到原始值。</span><span class="sxs-lookup"><span data-stu-id="d89b3-195">When the mouse moves away from the item, the property returns to the original value over a period of `1` second.</span></span> <span data-ttu-id="d89b3-196">请注意，不需要为 <xref:System.Windows.ContentElement.MouseLeave> 动画指定 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 值。</span><span class="sxs-lookup"><span data-stu-id="d89b3-196">Note how it is not necessary to specify a <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> value for the <xref:System.Windows.ContentElement.MouseLeave> animation.</span></span> <span data-ttu-id="d89b3-197">这是因为动画能够跟踪原始值。</span><span class="sxs-lookup"><span data-stu-id="d89b3-197">This is because the animation is able to keep track of the original value.</span></span>

[!code-xaml[StyleEventTriggers](./snippets/styles-templates-overview/csharp/Window6.xaml#SnippetStyleEventTriggers)]

<span data-ttu-id="d89b3-198">有关详细信息，请参阅[情节提要概述](../graphics-multimedia/storyboards-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d89b3-198">For more information, see the [Storyboards overview](../graphics-multimedia/storyboards-overview.md).</span></span>

<span data-ttu-id="d89b3-199">在下图中，鼠标指向第三项。</span><span class="sxs-lookup"><span data-stu-id="d89b3-199">In the following illustration, the mouse is pointing to the third item.</span></span>

<span data-ttu-id="d89b3-200">![样式设置示例屏幕截图](./media/styles-and-templates-overview/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span><span class="sxs-lookup"><span data-stu-id="d89b3-200">![Styling sample screenshot](./media/styles-and-templates-overview/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span></span>

### <a name="multitriggers-datatriggers-and-multidatatriggers"></a><span data-ttu-id="d89b3-201">MultiTrigger、DataTrigger 和 MultiDataTrigger</span><span class="sxs-lookup"><span data-stu-id="d89b3-201">MultiTriggers, DataTriggers, and MultiDataTriggers</span></span>

<span data-ttu-id="d89b3-202">除了 <xref:System.Windows.Trigger> 和 <xref:System.Windows.EventTrigger>，还有其他类型的触发器。</span><span class="sxs-lookup"><span data-stu-id="d89b3-202">In addition to <xref:System.Windows.Trigger> and <xref:System.Windows.EventTrigger>, there are other types of triggers.</span></span> <span data-ttu-id="d89b3-203"><xref:System.Windows.MultiTrigger> 允许基于多个条件设置属性值。</span><span class="sxs-lookup"><span data-stu-id="d89b3-203"><xref:System.Windows.MultiTrigger> allows you to set property values based on multiple conditions.</span></span> <span data-ttu-id="d89b3-204">当条件的属性为数据绑定时，使用 <xref:System.Windows.DataTrigger> 和 <xref:System.Windows.MultiDataTrigger>。</span><span class="sxs-lookup"><span data-stu-id="d89b3-204">You use <xref:System.Windows.DataTrigger> and <xref:System.Windows.MultiDataTrigger> when the property of your condition is data-bound.</span></span>

## <a name="visual-states"></a><span data-ttu-id="d89b3-205">视觉状态</span><span class="sxs-lookup"><span data-stu-id="d89b3-205">Visual States</span></span>

<span data-ttu-id="d89b3-206">控件始终处于特定的 **状态**。</span><span class="sxs-lookup"><span data-stu-id="d89b3-206">Controls are always in a specific **state**.</span></span> <span data-ttu-id="d89b3-207">例如，当鼠标在控件的表面上移动时，该控件被视为处于公用状态 `MouseOver`。</span><span class="sxs-lookup"><span data-stu-id="d89b3-207">For example, when the mouse moves over the surface of a control, the control is considered to be in a common state of `MouseOver`.</span></span> <span data-ttu-id="d89b3-208">没有特定状态的控件被视为处于公用 `Normal` 状态。</span><span class="sxs-lookup"><span data-stu-id="d89b3-208">A control without a specific state is considered to be in the common `Normal` state.</span></span> <span data-ttu-id="d89b3-209">状态分为多个组，前面提到的状态属于 `CommonStates` 状态组。</span><span class="sxs-lookup"><span data-stu-id="d89b3-209">States are broken into groups, and the previously mentioned states are part of the state group `CommonStates`.</span></span> <span data-ttu-id="d89b3-210">大多数控件都有两个状态组：`CommonStates` 和 `FocusStates`。</span><span class="sxs-lookup"><span data-stu-id="d89b3-210">Most controls have two state groups: `CommonStates` and `FocusStates`.</span></span> <span data-ttu-id="d89b3-211">在应用于控件的每个状态组中，控件始终处于每个组的一种状态，例如 `CommonStates.MouseOver` 和 `FocusStates.Unfocused`。</span><span class="sxs-lookup"><span data-stu-id="d89b3-211">Of each state group applied to a control, a control is always in one state of each group, such as `CommonStates.MouseOver` and `FocusStates.Unfocused`.</span></span> <span data-ttu-id="d89b3-212">但是，控件不能处于同一组中的两种不同状态，例如 `CommonStates.Normal` 和 `CommonStates.Disabled`。</span><span class="sxs-lookup"><span data-stu-id="d89b3-212">However, a control can't be in two different states within the same group, such as `CommonStates.Normal` and `CommonStates.Disabled`.</span></span> <span data-ttu-id="d89b3-213">下面是大多数控件可以识别和使用的状态表。</span><span class="sxs-lookup"><span data-stu-id="d89b3-213">Here is a table of states most controls recognize and use.</span></span>

| <span data-ttu-id="d89b3-214">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="d89b3-214">VisualState Name</span></span> | <span data-ttu-id="d89b3-215">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="d89b3-215">VisualStateGroup Name</span></span> | <span data-ttu-id="d89b3-216">描述</span><span class="sxs-lookup"><span data-stu-id="d89b3-216">Description</span></span> |
| ---------------- | --------------------- | ----------- |
| <span data-ttu-id="d89b3-217">普通</span><span class="sxs-lookup"><span data-stu-id="d89b3-217">Normal</span></span>           | <span data-ttu-id="d89b3-218">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d89b3-218">CommonStates</span></span>          | <span data-ttu-id="d89b3-219">默认状态。</span><span class="sxs-lookup"><span data-stu-id="d89b3-219">The default state.</span></span> |
| <span data-ttu-id="d89b3-220">MouseOver</span><span class="sxs-lookup"><span data-stu-id="d89b3-220">MouseOver</span></span>        | <span data-ttu-id="d89b3-221">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d89b3-221">CommonStates</span></span>          | <span data-ttu-id="d89b3-222">鼠标指针悬停在控件上方。</span><span class="sxs-lookup"><span data-stu-id="d89b3-222">The mouse pointer is positioned over the control.</span></span> |
| <span data-ttu-id="d89b3-223">已按下</span><span class="sxs-lookup"><span data-stu-id="d89b3-223">Pressed</span></span>          | <span data-ttu-id="d89b3-224">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d89b3-224">CommonStates</span></span>          | <span data-ttu-id="d89b3-225">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="d89b3-225">The control is pressed.</span></span> |
| <span data-ttu-id="d89b3-226">已禁用</span><span class="sxs-lookup"><span data-stu-id="d89b3-226">Disabled</span></span>         | <span data-ttu-id="d89b3-227">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d89b3-227">CommonStates</span></span>          | <span data-ttu-id="d89b3-228">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="d89b3-228">The control is disabled.</span></span> |
| <span data-ttu-id="d89b3-229">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="d89b3-229">Focused</span></span>          | <span data-ttu-id="d89b3-230">FocusStates</span><span class="sxs-lookup"><span data-stu-id="d89b3-230">FocusStates</span></span>           | <span data-ttu-id="d89b3-231">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="d89b3-231">The control has focus.</span></span> |
| <span data-ttu-id="d89b3-232">失去焦点</span><span class="sxs-lookup"><span data-stu-id="d89b3-232">Unfocused</span></span>        | <span data-ttu-id="d89b3-233">FocusStates</span><span class="sxs-lookup"><span data-stu-id="d89b3-233">FocusStates</span></span>           | <span data-ttu-id="d89b3-234">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="d89b3-234">The control does not have focus.</span></span> |

<span data-ttu-id="d89b3-235">通过在控件模板的根元素上定义 <xref:System.Windows.VisualStateManager?displayProperty=fullName>，可以在控件进入特定状态时触发动画。</span><span class="sxs-lookup"><span data-stu-id="d89b3-235">By defining a <xref:System.Windows.VisualStateManager?displayProperty=fullName> on the root element of a control template, you can trigger animations when a control enters a specific state.</span></span> <span data-ttu-id="d89b3-236">`VisualStateManager` 声明要监视的 <xref:System.Windows.VisualStateGroup> 和 <xref:System.Windows.VisualState> 的组合。</span><span class="sxs-lookup"><span data-stu-id="d89b3-236">The `VisualStateManager` declares which combinations of <xref:System.Windows.VisualStateGroup> and <xref:System.Windows.VisualState> to watch.</span></span> <span data-ttu-id="d89b3-237">当控件进入受监视状态时，将启动 `VisaulStateManager` 定义的动画。</span><span class="sxs-lookup"><span data-stu-id="d89b3-237">When the control enters a watched state, the animation defined by the `VisaulStateManager` is started.</span></span>

<span data-ttu-id="d89b3-238">例如，以下 XAML 代码监视 `CommonStates.MouseOver` 状态，以对名为 `backgroundElement` 的元素的填充颜色进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="d89b3-238">For example, the following XAML code watches the `CommonStates.MouseOver` state to animate the fill color of the element named `backgroundElement`.</span></span> <span data-ttu-id="d89b3-239">当控件恢复为 `CommonStates.Normal` 状态时，将还原名为 `backgroundElement` 的元素的填充颜色。</span><span class="sxs-lookup"><span data-stu-id="d89b3-239">When the control returns to the `CommonStates.Normal` state, the fill color of the element named `backgroundElement` is restored.</span></span>

```xaml
<ControlTemplate x:Key="roundbutton" TargetType="Button">
    <Grid>
        <VisualStateManager.VisualStateGroups>
            <VisualStateGroup Name="CommonStates">
                <VisualState Name="Normal">
                    <ColorAnimation Storyboard.TargetName="backgroundElement"
                                    Storyboard.TargetProperty="(Shape.Fill).(SolidColorBrush.Color)"
                                    To="{TemplateBinding Background}"
                                    Duration="0:0:0.3"/>
                </VisualState>
                <VisualState Name="MouseOver">
                    <ColorAnimation Storyboard.TargetName="backgroundElement"
                                    Storyboard.TargetProperty="(Shape.Fill).(SolidColorBrush.Color)"
                                    To="Yellow"
                                    Duration="0:0:0.3"/>
                </VisualState>
            </VisualStateGroup>
        </VisualStateManager.VisualStateGroups>

        ...
```

<span data-ttu-id="d89b3-240">有关情节提要的详细信息，请参阅[情节提要概述](../graphics-multimedia/storyboards-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d89b3-240">For more information about storyboards, see [Storyboards Overview](../graphics-multimedia/storyboards-overview.md).</span></span>

## <a name="shared-resources-and-themes"></a><span data-ttu-id="d89b3-241">共享资源和主题</span><span class="sxs-lookup"><span data-stu-id="d89b3-241">Shared resources and themes</span></span>

<span data-ttu-id="d89b3-242">典型的 WPF 应用可能具有多个 UI 资源，它们可应用于整个应用。</span><span class="sxs-lookup"><span data-stu-id="d89b3-242">A typical WPF app might have multiple UI resources that are applied throughout the app.</span></span> <span data-ttu-id="d89b3-243">这组资源统称为应用的主题。</span><span class="sxs-lookup"><span data-stu-id="d89b3-243">Collectively, this set of resources can be considered the theme for the app.</span></span> <span data-ttu-id="d89b3-244">WPF 支持使用封装为 <xref:System.Windows.ResourceDictionary> 类的资源字典将 UI 资源打包为主题。</span><span class="sxs-lookup"><span data-stu-id="d89b3-244">WPF provides support for packaging UI resources as a theme by using a resource dictionary that is encapsulated as the <xref:System.Windows.ResourceDictionary> class.</span></span>

<span data-ttu-id="d89b3-245">WPF 主题通过使用 WPF 公开的样式设置和模板化机制来定义，该机制用于自定义任何元素的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="d89b3-245">WPF themes are defined by using the styling and templating mechanism that WPF exposes for customizing the visuals of any element.</span></span>

<span data-ttu-id="d89b3-246">WPF 主题资源存储在嵌入的资源字典中。</span><span class="sxs-lookup"><span data-stu-id="d89b3-246">WPF theme resources are stored in embedded resource dictionaries.</span></span> <span data-ttu-id="d89b3-247">这些资源必须嵌入到已签名的程序集内，并且可以嵌入到与代码本身相同的程序集内或并行程序集内。</span><span class="sxs-lookup"><span data-stu-id="d89b3-247">These resource dictionaries must be embedded within a signed assembly, and can either be embedded in the same assembly as the code itself or in a side-by-side assembly.</span></span> <span data-ttu-id="d89b3-248">对于包含 WPF 控件的程序集 PresentationFramework.dll，主题资源位于一系列并行程序集内。</span><span class="sxs-lookup"><span data-stu-id="d89b3-248">For PresentationFramework.dll, the assembly that contains WPF controls, theme resources are in a series of side-by-side assemblies.</span></span>

<span data-ttu-id="d89b3-249">该主题成为在搜索元素样式时最后查看的位置。</span><span class="sxs-lookup"><span data-stu-id="d89b3-249">The theme becomes the last place to look when searching for the style of an element.</span></span> <span data-ttu-id="d89b3-250">通常，搜索先沿着元素树搜索适当的资源，然后在应用资源集合中查找，最后查询系统。</span><span class="sxs-lookup"><span data-stu-id="d89b3-250">Typically, the search will begin by walking up the element tree searching for an appropriate resource, then look in the app resource collection and finally query the system.</span></span> <span data-ttu-id="d89b3-251">这样一来，应用开发者便有机会在到达主题之前在树或应用级别上为任何对象重新定义样式。</span><span class="sxs-lookup"><span data-stu-id="d89b3-251">This gives app developers a chance to redefine the style for any object at the tree or app level before reaching the theme.</span></span>

<span data-ttu-id="d89b3-252">可以将资源字典定义为单独的文件，这些文件支持跨多个应用重复使用主题。</span><span class="sxs-lookup"><span data-stu-id="d89b3-252">You can define resource dictionaries as individual files that enable you to reuse a theme across multiple apps.</span></span> <span data-ttu-id="d89b3-253">还可以通过定义多个资源字典来创建可交换的主题，这些资源字典以不同的值提供相同类型的资源。</span><span class="sxs-lookup"><span data-stu-id="d89b3-253">You can also create swappable themes by defining multiple resource dictionaries that provide the same types of resources but with different values.</span></span> <span data-ttu-id="d89b3-254">在应用级别上重新定义这些样式或其他资源是设计应用外观的推荐方法。</span><span class="sxs-lookup"><span data-stu-id="d89b3-254">Redefining these styles or other resources at the app level is the recommended approach for skinning an app.</span></span>

<span data-ttu-id="d89b3-255">若要跨应用共享一组资源（包括样式和模板），可创建 XAML 文件，并定义包含对 `shared.xaml` 文件的引用的 <xref:System.Windows.ResourceDictionary>。</span><span class="sxs-lookup"><span data-stu-id="d89b3-255">To share a set of resources, including styles and templates, across apps, you can create a XAML file and define a <xref:System.Windows.ResourceDictionary> that includes reference to a `shared.xaml` file.</span></span>

```xaml
<ResourceDictionary.MergedDictionaries>
  <ResourceDictionary Source="Shared.xaml" />
</ResourceDictionary.MergedDictionaries>
```

<span data-ttu-id="d89b3-256">它是 `shared.xaml` 的共享，用于定义包含一组样式和画笔资源的 <xref:System.Windows.ResourceDictionary>，从而使应用中的控件具有一致的外观。</span><span class="sxs-lookup"><span data-stu-id="d89b3-256">It is the sharing of `shared.xaml`, which itself defines a <xref:System.Windows.ResourceDictionary> that contains a set of style and brush resources, that enables the controls in an app to have a consistent look.</span></span>

<span data-ttu-id="d89b3-257">有关详细信息，请参阅[合并资源字典](../advanced/merged-resource-dictionaries.md)。</span><span class="sxs-lookup"><span data-stu-id="d89b3-257">For more information, see [Merged resource dictionaries](../advanced/merged-resource-dictionaries.md).</span></span>

<span data-ttu-id="d89b3-258">如果要为自定义控件创建主题，请参阅 [控件创作概述](control-authoring-overview.md#defining-resources-at-the-theme-level)的 **在主题级别定义资源** 部分。</span><span class="sxs-lookup"><span data-stu-id="d89b3-258">If you are creating a theme for your custom control, see the **Defining resources at the theme level** section of the [Control authoring overview](control-authoring-overview.md#defining-resources-at-the-theme-level).</span></span>

## <a name="see-also"></a><span data-ttu-id="d89b3-259">请参阅</span><span class="sxs-lookup"><span data-stu-id="d89b3-259">See also</span></span>

- [<span data-ttu-id="d89b3-260">WPF 中的 Pack URI</span><span class="sxs-lookup"><span data-stu-id="d89b3-260">Pack URIs in WPF</span></span>](../app-development/pack-uris-in-wpf.md)
- [<span data-ttu-id="d89b3-261">如何：查找由 ControlTemplate 生成的元素</span><span class="sxs-lookup"><span data-stu-id="d89b3-261">How to: Find ControlTemplate-Generated Elements</span></span>](how-to-find-controltemplate-generated-elements.md)
- [<span data-ttu-id="d89b3-262">查找由 DataTemplate 生成的元素</span><span class="sxs-lookup"><span data-stu-id="d89b3-262">Find DataTemplate-Generated Elements</span></span>](../data/how-to-find-datatemplate-generated-elements.md)
