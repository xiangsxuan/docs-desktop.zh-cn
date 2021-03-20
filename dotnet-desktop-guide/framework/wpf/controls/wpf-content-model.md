---
title: 内容模型
ms.date: 03/30/2017
helpviewer_keywords:
- UIElement class [WPF], displaying content
- content model [WPF], controls
- controls [WPF], displaying text
- content display [WPF], controls
- controls [WPF], formatting text
- displaying content [WPF]
- arbitrary content classes [WPF], content model
- ContentControl class [WPF], displaying content
ms.assetid: 214da5ef-547a-4cf8-9b07-4aa8a0e52cdd
ms.openlocfilehash: 193e465fe14eb5e21f4a855f056600f907bfccbc
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667347"
---
# <a name="wpf-content-model"></a><span data-ttu-id="119c3-102">WPF 内容模型</span><span class="sxs-lookup"><span data-stu-id="119c3-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="119c3-103">是一个演示平台，提供了许多控件和类似控件的类型，主要用于显示不同类型的内容。</span><span class="sxs-lookup"><span data-stu-id="119c3-103">is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="119c3-104">若要确定所要使用的控件或要从其派生的控件，应该了解特定控件可以最佳效果显示的对象类型。</span><span class="sxs-lookup"><span data-stu-id="119c3-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="119c3-105">本主题概述了适用于 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件和类似控件的类型的内容模型。</span><span class="sxs-lookup"><span data-stu-id="119c3-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="119c3-106">内容模型描述可在控件中使用的内容。</span><span class="sxs-lookup"><span data-stu-id="119c3-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="119c3-107">本主题还列出了每个内容模型的内容属性。</span><span class="sxs-lookup"><span data-stu-id="119c3-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="119c3-108">内容属性是一种用于存储对象内容的属性。</span><span class="sxs-lookup"><span data-stu-id="119c3-108">A content property is a property that is used to store the content of the object.</span></span>  

<a name="classes_that_contain_arbitrary_content"></a>
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="119c3-109">包含任意内容的类</span><span class="sxs-lookup"><span data-stu-id="119c3-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="119c3-110">某些控件可以包含任何类型的对象，例如字符串、 <xref:System.DateTime> 对象或作为 <xref:System.Windows.UIElement> 附加项的容器的。</span><span class="sxs-lookup"><span data-stu-id="119c3-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="119c3-111">例如， <xref:System.Windows.Controls.Button> 可以包含图像和某些文本; 或 <xref:System.Windows.Controls.CheckBox> 可以包含的值 <xref:System.DateTime.Now%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="119c3-112">有四个可包含任意内容的类。</span><span class="sxs-lookup"><span data-stu-id="119c3-112">has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="119c3-113">下表列出了从继承的类 <xref:System.Windows.Controls.Control> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="119c3-114">包含任意内容的类</span><span class="sxs-lookup"><span data-stu-id="119c3-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="119c3-115">内容</span><span class="sxs-lookup"><span data-stu-id="119c3-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="119c3-116">一个任意对象。</span><span class="sxs-lookup"><span data-stu-id="119c3-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="119c3-117">一个标头和一个项（两者都是任意对象）。</span><span class="sxs-lookup"><span data-stu-id="119c3-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="119c3-118">一个任意对象集合。</span><span class="sxs-lookup"><span data-stu-id="119c3-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="119c3-119">一个标头和一个项集合（全部都是任意对象）。</span><span class="sxs-lookup"><span data-stu-id="119c3-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="119c3-120">继承自这些类的控件可以包含相同类型的内容，并可以采用相同方式处理该内容。</span><span class="sxs-lookup"><span data-stu-id="119c3-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="119c3-121">下图显示了一个来自每个包含图像和文本的内容模型的控件：</span><span class="sxs-lookup"><span data-stu-id="119c3-121">The following illustration shows one control from each content model that contains an image and some text:</span></span>  
  
 ![显示四个不同控件的屏幕截图，每个内容模型一个。](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="119c3-123">包含一个任意对象的控件</span><span class="sxs-lookup"><span data-stu-id="119c3-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="119c3-124"><xref:System.Windows.Controls.ContentControl>类包含一段任意内容。</span><span class="sxs-lookup"><span data-stu-id="119c3-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="119c3-125">它的内容属性为 <xref:System.Windows.Controls.ContentControl.Content%2A> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="119c3-126">以下控件从继承 <xref:System.Windows.Controls.ContentControl> 并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="119c3-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Button>  
  
- <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
- <xref:System.Windows.Controls.CheckBox>  
  
- <xref:System.Windows.Controls.ComboBoxItem>  
  
- <xref:System.Windows.Controls.ContentControl>  
  
- <xref:System.Windows.Controls.Frame>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GroupItem>  
  
- <xref:System.Windows.Controls.Label>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Navigation.NavigationWindow>  
  
- <xref:System.Windows.Controls.RadioButton>  
  
- <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
- <xref:System.Windows.Controls.ScrollViewer>  
  
- <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
- <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
- <xref:System.Windows.Controls.ToolTip>  
  
- <xref:System.Windows.Controls.UserControl>  
  
- <xref:System.Windows.Window>  
  
 <span data-ttu-id="119c3-127">下图显示了四个按钮 <xref:System.Windows.Controls.ContentControl.Content%2A> ，其设置为字符串、 <xref:System.DateTime> 对象、和， <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.Controls.Panel> 其中包含 <xref:System.Windows.Shapes.Ellipse> 和 <xref:System.Windows.Controls.TextBlock> ：</span><span class="sxs-lookup"><span data-stu-id="119c3-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>:</span></span>  
  
 ![显示具有不同内容类型的四个按钮的屏幕截图。](./media/wpf-content-model/control-content-model-buttons.png)  
  
 <span data-ttu-id="119c3-129">有关如何设置属性的示例 <xref:System.Windows.Controls.ContentControl.Content%2A> ，请参见 <xref:System.Windows.Controls.ContentControl> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-129">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="119c3-130">包含一个标头和一个任意对象的控件</span><span class="sxs-lookup"><span data-stu-id="119c3-130">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="119c3-131"><xref:System.Windows.Controls.HeaderedContentControl>类从继承 <xref:System.Windows.Controls.ContentControl> ，并显示带有标题的内容。</span><span class="sxs-lookup"><span data-stu-id="119c3-131">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="119c3-132">它从中继承 content 属性， <xref:System.Windows.Controls.ContentControl.Content%2A> <xref:System.Windows.Controls.ContentControl> 并定义类型为的 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 属性 <xref:System.Object> ; 因此，两者都可以是任意对象。</span><span class="sxs-lookup"><span data-stu-id="119c3-132">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="119c3-133">以下控件从继承 <xref:System.Windows.Controls.HeaderedContentControl> 并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="119c3-133">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="119c3-134">下图显示了两个 <xref:System.Windows.Controls.TabItem> 对象。</span><span class="sxs-lookup"><span data-stu-id="119c3-134">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="119c3-135">第一个 <xref:System.Windows.Controls.TabItem> 具有 <xref:System.Windows.UIElement> 对象作为 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 和 <xref:System.Windows.Controls.ContentControl.Content%2A> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-135">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="119c3-136">将 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 设置为 <xref:System.Windows.Controls.StackPanel> ，其中包含 <xref:System.Windows.Shapes.Ellipse> 和 <xref:System.Windows.Controls.TextBlock> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-136">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="119c3-137">将 <xref:System.Windows.Controls.ContentControl.Content%2A> 设置为 <xref:System.Windows.Controls.StackPanel> ，其中包含 <xref:System.Windows.Controls.TextBlock> 和 <xref:System.Windows.Controls.Label> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-137">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="119c3-138">第二个在 <xref:System.Windows.Controls.TabItem> 的和中有一个字符串 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.ContentControl.Content%2A> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-138">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 ![在标头属性中使用不同类型的 TabControl。](./media/wpf-content-model/control-content-model-tab.png)  
  
 <span data-ttu-id="119c3-140">有关如何创建对象的示例 <xref:System.Windows.Controls.TabItem> ，请参阅 <xref:System.Windows.Controls.HeaderedContentControl> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-140">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="119c3-141">包含一个任意对象集合的控件</span><span class="sxs-lookup"><span data-stu-id="119c3-141">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="119c3-142"><xref:System.Windows.Controls.ItemsControl>类从继承， <xref:System.Windows.Controls.Control> 并且可以包含多个项，例如字符串、对象或其他元素。</span><span class="sxs-lookup"><span data-stu-id="119c3-142">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="119c3-143">它的内容属性为 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 和 <xref:System.Windows.Controls.ItemsControl.Items%2A> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-143">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="119c3-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 通常用于填充 <xref:System.Windows.Controls.ItemsControl> 数据集合。</span><span class="sxs-lookup"><span data-stu-id="119c3-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="119c3-145">如果你不希望使用集合来填充 <xref:System.Windows.Controls.ItemsControl> ，则可以通过使用属性添加项 <xref:System.Windows.Controls.ItemsControl.Items%2A> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-145">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="119c3-146">以下控件从继承 <xref:System.Windows.Controls.ItemsControl> 并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="119c3-146">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Menu>  
  
- <xref:System.Windows.Controls.Primitives.MenuBase>  
  
- <xref:System.Windows.Controls.ContextMenu>  
  
- <xref:System.Windows.Controls.ComboBox>  
  
- <xref:System.Windows.Controls.ItemsControl>  
  
- <xref:System.Windows.Controls.ListBox>  
  
- <xref:System.Windows.Controls.ListView>  
  
- <xref:System.Windows.Controls.TabControl>  
  
- <xref:System.Windows.Controls.TreeView>  
  
- <xref:System.Windows.Controls.Primitives.Selector>  
  
- <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 <span data-ttu-id="119c3-147">下图显示了一个 <xref:System.Windows.Controls.ListBox> 包含以下类型的项的：</span><span class="sxs-lookup"><span data-stu-id="119c3-147">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
- <span data-ttu-id="119c3-148">一个字符串。</span><span class="sxs-lookup"><span data-stu-id="119c3-148">A string.</span></span>  
  
- <span data-ttu-id="119c3-149"><xref:System.DateTime> 对象。</span><span class="sxs-lookup"><span data-stu-id="119c3-149">A <xref:System.DateTime> object.</span></span>  
  
- <span data-ttu-id="119c3-150"><xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="119c3-150">A <xref:System.Windows.UIElement>.</span></span>  
  
- <span data-ttu-id="119c3-151">一个 <xref:System.Windows.Controls.Panel> ，它包含一个 <xref:System.Windows.Shapes.Ellipse> 和一个 <xref:System.Windows.Controls.TextBlock> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-151">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 ![显示具有四种内容类型的列表框的屏幕截图。](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="119c3-153">包含一个标头和一个任意对象集合的控件</span><span class="sxs-lookup"><span data-stu-id="119c3-153">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="119c3-154"><xref:System.Windows.Controls.HeaderedItemsControl>类从继承， <xref:System.Windows.Controls.ItemsControl> 并且可以包含多个项，例如字符串、对象或其他元素以及标头。</span><span class="sxs-lookup"><span data-stu-id="119c3-154">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="119c3-155">它继承 <xref:System.Windows.Controls.ItemsControl> 内容属性、 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 和 <xref:System.Windows.Controls.ItemsControl.Items%2A> ，并定义 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 可以为任意对象的属性。</span><span class="sxs-lookup"><span data-stu-id="119c3-155">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="119c3-156">以下控件从继承 <xref:System.Windows.Controls.HeaderedItemsControl> 并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="119c3-156">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="119c3-157">包含一个 UIElement 对象集合的类</span><span class="sxs-lookup"><span data-stu-id="119c3-157">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="119c3-158"><xref:System.Windows.Controls.Panel>类定位和排列子 <xref:System.Windows.UIElement> 对象。</span><span class="sxs-lookup"><span data-stu-id="119c3-158">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="119c3-159">它的内容属性为 <xref:System.Windows.Controls.Panel.Children%2A> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-159">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="119c3-160">下面的类从类继承 <xref:System.Windows.Controls.Panel> ，并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="119c3-160">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Canvas>  
  
- <xref:System.Windows.Controls.DockPanel>  
  
- <xref:System.Windows.Controls.Grid>  
  
- <xref:System.Windows.Controls.Primitives.TabPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
- <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
- <xref:System.Windows.Controls.StackPanel>  
  
- <xref:System.Windows.Controls.VirtualizingPanel>  
  
- <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
- <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="119c3-161">有关详细信息，请参阅[面板概述](panels-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="119c3-161">For more information, see [Panels Overview](panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="119c3-162">影响 UIElement 外观的类</span><span class="sxs-lookup"><span data-stu-id="119c3-162">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="119c3-163"><xref:System.Windows.Controls.Decorator>类将视觉效果应用于或围绕单个子级 <xref:System.Windows.UIElement> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-163">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="119c3-164">它的内容属性为 <xref:System.Windows.Controls.Decorator.Child%2A> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-164">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="119c3-165">以下类从继承 <xref:System.Windows.Controls.Decorator> 并使用其内容模型：</span><span class="sxs-lookup"><span data-stu-id="119c3-165">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="119c3-166">下图显示了一个 <xref:System.Windows.Controls.TextBox> 具有 (修饰的，其中) <xref:System.Windows.Controls.Border> 围绕它的。</span><span class="sxs-lookup"><span data-stu-id="119c3-166">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="119c3-167">![具有黑色边框的 TextBox](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="119c3-167">![TextBox with black border](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="119c3-168">具有边框的 TextBlock</span><span class="sxs-lookup"><span data-stu-id="119c3-168">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="119c3-169">提供 UIElement 相关视觉反馈的类</span><span class="sxs-lookup"><span data-stu-id="119c3-169">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="119c3-170"><xref:System.Windows.Documents.Adorner>类向用户提供视觉提示。</span><span class="sxs-lookup"><span data-stu-id="119c3-170">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="119c3-171">例如，使用 <xref:System.Windows.Documents.Adorner> 向元素添加功能句柄，或提供有关控件的状态信息。</span><span class="sxs-lookup"><span data-stu-id="119c3-171">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="119c3-172"><xref:System.Windows.Documents.Adorner>类提供一个框架，以便您可以创建自己的装饰器。</span><span class="sxs-lookup"><span data-stu-id="119c3-172">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="119c3-173">不会提供任何实现的装饰器。</span><span class="sxs-lookup"><span data-stu-id="119c3-173">does not provide any implemented adorners.</span></span> <span data-ttu-id="119c3-174">有关详细信息，请参阅[装饰器概述](adorners-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="119c3-174">For more information, see [Adorners Overview](adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="119c3-175">可让用户输入文本的类</span><span class="sxs-lookup"><span data-stu-id="119c3-175">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="119c3-176">WPF 提供了三个可让用户输入文本的主要控件。</span><span class="sxs-lookup"><span data-stu-id="119c3-176">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="119c3-177">每个控件都以不同方式显示文本。</span><span class="sxs-lookup"><span data-stu-id="119c3-177">Each control displays the text differently.</span></span> <span data-ttu-id="119c3-178">下表列出了这三个与文本相关的控件、显示文本时的功能以及包含控件文本的属性。</span><span class="sxs-lookup"><span data-stu-id="119c3-178">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="119c3-179">控制</span><span class="sxs-lookup"><span data-stu-id="119c3-179">Control</span></span>|<span data-ttu-id="119c3-180">文本显示方式</span><span class="sxs-lookup"><span data-stu-id="119c3-180">Text is displayed as</span></span>|<span data-ttu-id="119c3-181">内容属性</span><span class="sxs-lookup"><span data-stu-id="119c3-181">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="119c3-182">纯文本</span><span class="sxs-lookup"><span data-stu-id="119c3-182">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="119c3-183">带格式文本</span><span class="sxs-lookup"><span data-stu-id="119c3-183">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="119c3-184">隐藏文本（字符已屏蔽）</span><span class="sxs-lookup"><span data-stu-id="119c3-184">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>
## <a name="classes-that-display-your-text"></a><span data-ttu-id="119c3-185">显示文本的类</span><span class="sxs-lookup"><span data-stu-id="119c3-185">Classes That Display Your Text</span></span>  
 <span data-ttu-id="119c3-186">某些类可用于显示纯文本或带格式文本。</span><span class="sxs-lookup"><span data-stu-id="119c3-186">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="119c3-187">您可以使用 <xref:System.Windows.Controls.TextBlock> 来显示少量文本。</span><span class="sxs-lookup"><span data-stu-id="119c3-187">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="119c3-188">如果要显示大量文本，请使用 <xref:System.Windows.Controls.FlowDocumentReader> 、 <xref:System.Windows.Controls.FlowDocumentPageViewer> 或 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 控件。</span><span class="sxs-lookup"><span data-stu-id="119c3-188">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="119c3-189"><xref:System.Windows.Controls.TextBlock>具有两个内容属性： <xref:System.Windows.Controls.TextBlock.Text%2A> 和 <xref:System.Windows.Controls.TextBlock.Inlines%2A> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-189">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="119c3-190">如果要显示使用一致格式的文本，则该 <xref:System.Windows.Controls.TextBlock.Text%2A> 属性通常是最佳选择。</span><span class="sxs-lookup"><span data-stu-id="119c3-190">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="119c3-191">如果计划在整个文本中使用不同的格式，请使用 <xref:System.Windows.Controls.TextBlock.Inlines%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="119c3-191">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="119c3-192"><xref:System.Windows.Controls.TextBlock.Inlines%2A>属性是对象的集合 <xref:System.Windows.Documents.Inline> ，这些对象指定如何设置文本格式。</span><span class="sxs-lookup"><span data-stu-id="119c3-192">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="119c3-193">下表列出了 <xref:System.Windows.Controls.FlowDocumentReader> 、和类的 content 属性 <xref:System.Windows.Controls.FlowDocumentPageViewer> <xref:System.Windows.Controls.FlowDocumentScrollViewer> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-193">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="119c3-194">控制</span><span class="sxs-lookup"><span data-stu-id="119c3-194">Control</span></span>|<span data-ttu-id="119c3-195">内容属性</span><span class="sxs-lookup"><span data-stu-id="119c3-195">Content property</span></span>|<span data-ttu-id="119c3-196">内容属性类型</span><span class="sxs-lookup"><span data-stu-id="119c3-196">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="119c3-197">文档</span><span class="sxs-lookup"><span data-stu-id="119c3-197">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="119c3-198">文档</span><span class="sxs-lookup"><span data-stu-id="119c3-198">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="119c3-199">文档</span><span class="sxs-lookup"><span data-stu-id="119c3-199">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="119c3-200"><xref:System.Windows.Documents.FlowDocument>实现 <xref:System.Windows.Documents.IDocumentPaginatorSource> 接口; 因此，所有这三个类都可以采用 <xref:System.Windows.Documents.FlowDocument> 作为内容。</span><span class="sxs-lookup"><span data-stu-id="119c3-200">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>
## <a name="classes-that-format-your-text"></a><span data-ttu-id="119c3-201">设置文本格式的类</span><span class="sxs-lookup"><span data-stu-id="119c3-201">Classes That Format Your Text</span></span>  
 <span data-ttu-id="119c3-202"><xref:System.Windows.Documents.TextElement> 及其相关类允许您设置文本格式。</span><span class="sxs-lookup"><span data-stu-id="119c3-202"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="119c3-203"><xref:System.Windows.Documents.TextElement> 对象包含和设置和对象中的文本 <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Documents.FlowDocument> 。</span><span class="sxs-lookup"><span data-stu-id="119c3-203"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="119c3-204">对象的两个主要类型 <xref:System.Windows.Documents.TextElement> 是 <xref:System.Windows.Documents.Block> 元素和 <xref:System.Windows.Documents.Inline> 元素。</span><span class="sxs-lookup"><span data-stu-id="119c3-204">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="119c3-205"><xref:System.Windows.Documents.Block>元素表示文本块，如段落或列表。</span><span class="sxs-lookup"><span data-stu-id="119c3-205">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="119c3-206"><xref:System.Windows.Documents.Inline>元素表示块中的部分文本。</span><span class="sxs-lookup"><span data-stu-id="119c3-206">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="119c3-207">许多 <xref:System.Windows.Documents.Inline> 类指定其应用到的文本的格式设置。</span><span class="sxs-lookup"><span data-stu-id="119c3-207">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="119c3-208">每个 <xref:System.Windows.Documents.TextElement> 都有其自己的内容模型。</span><span class="sxs-lookup"><span data-stu-id="119c3-208">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="119c3-209">有关详细信息，请参阅 [TextElement 内容模型概述](../advanced/textelement-content-model-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="119c3-209">For more information, see the [TextElement Content Model Overview](../advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="119c3-210">请参阅</span><span class="sxs-lookup"><span data-stu-id="119c3-210">See also</span></span>

- [<span data-ttu-id="119c3-211">高级</span><span class="sxs-lookup"><span data-stu-id="119c3-211">Advanced</span></span>](../advanced/index.md)
