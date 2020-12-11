---
title: L2DBForm.xaml 源代码
ms.date: 10/22/2019
ms.topic: sample
ms.openlocfilehash: 290b00e136f0c49e1b27d4fa1bca7321eebe936e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971797"
---
# <a name="l2dbformxaml-source-code"></a><span data-ttu-id="c81e5-102">L2DBForm.xaml 源代码</span><span class="sxs-lookup"><span data-stu-id="c81e5-102">L2DBForm.xaml source code</span></span>

<span data-ttu-id="c81e5-103">本页包含 [使用 LINQ to XML 示例的 WPF 数据绑定](linq-to-xml-data-binding-sample.md)的 XAML 源文件并对其进行说明。</span><span class="sxs-lookup"><span data-stu-id="c81e5-103">This page contains and describes the XAML source file for the [WPF data binding using LINQ to XML example](linq-to-xml-data-binding-sample.md).</span></span>

## <a name="overall-ui-structure"></a><span data-ttu-id="c81e5-104">总体 UI 结构</span><span class="sxs-lookup"><span data-stu-id="c81e5-104">Overall UI structure</span></span>

<span data-ttu-id="c81e5-105">与 WPF 项目一样，此文件包含一个父元素，该元素是一个 <xref:System.Windows.Window> 与 `L2XDBFrom` 命名空间中的派生类相关联的 XML 元素 `LinqToXmlDataBinding` 。</span><span class="sxs-lookup"><span data-stu-id="c81e5-105">As is typical for a WPF project, this file contains one parent element, a <xref:System.Windows.Window> XML element that's associated with the derived class `L2XDBFrom` in the `LinqToXmlDataBinding` namespace.</span></span>

<span data-ttu-id="c81e5-106">工作区包含在 <xref:System.Windows.Controls.StackPanel> 给定浅蓝色背景的中。</span><span class="sxs-lookup"><span data-stu-id="c81e5-106">The client area is contained within a <xref:System.Windows.Controls.StackPanel> that's given a light blue background.</span></span> <span data-ttu-id="c81e5-107">此面板包含四个 <xref:System.Windows.Controls.DockPanel> UI 区域，由 <xref:System.Windows.Controls.Separator> 条分隔。</span><span class="sxs-lookup"><span data-stu-id="c81e5-107">This panel contains four <xref:System.Windows.Controls.DockPanel> UI sections separated by <xref:System.Windows.Controls.Separator> bars.</span></span> <span data-ttu-id="c81e5-108">[此处](linq-to-xml-data-binding-sample.md#overview)介绍了这些部分的用途。</span><span class="sxs-lookup"><span data-stu-id="c81e5-108">The purpose of these sections is described [here](linq-to-xml-data-binding-sample.md#overview).</span></span>

<span data-ttu-id="c81e5-109">每个区域都包含一个标识该区域的标签。</span><span class="sxs-lookup"><span data-stu-id="c81e5-109">Each section contains a label that identifies it.</span></span> <span data-ttu-id="c81e5-110">在前两个区域中，此标签通过使用 <xref:System.Windows.FrameworkElement.LayoutTransform%2A>旋转 90 度。</span><span class="sxs-lookup"><span data-stu-id="c81e5-110">In the first two sections, this label is rotated 90 degrees through the use of a <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.</span></span> <span data-ttu-id="c81e5-111">本部分的其余部分包含对应于该区域用途的 UI 元素，例如，文本块、文本框和按钮。</span><span class="sxs-lookup"><span data-stu-id="c81e5-111">The rest of the section contains UI elements appropriate to the purpose of that section, for example, text blocks, text boxes, and buttons.</span></span> <span data-ttu-id="c81e5-112">有时使用子 <xref:System.Windows.Controls.StackPanel> 来对齐这些子控件。</span><span class="sxs-lookup"><span data-stu-id="c81e5-112">Sometimes a child <xref:System.Windows.Controls.StackPanel> is used to align these child controls.</span></span>

## <a name="window-resource-section"></a><span data-ttu-id="c81e5-113">窗口资源区域</span><span class="sxs-lookup"><span data-stu-id="c81e5-113">Window resource section</span></span>

<span data-ttu-id="c81e5-114">在第 9 行上的 `<Window.Resources>` 开始标记指示窗口资源区域的开始。</span><span class="sxs-lookup"><span data-stu-id="c81e5-114">The opening `<Window.Resources>` tag on line 9 indicates the start of the window resource section.</span></span> <span data-ttu-id="c81e5-115">它在第 35 行上以结束标记结束。</span><span class="sxs-lookup"><span data-stu-id="c81e5-115">It ends with the closing tag on line 35.</span></span>

<span data-ttu-id="c81e5-116">`<ObjectDataProvider>` 标记跨越第 11 至第 25 行，声明一个名为 <xref:System.Windows.Data.ObjectDataProvider>的 `LoadedBooks`，它使用 <xref:System.Xml.Linq.XElement> 作为源。</span><span class="sxs-lookup"><span data-stu-id="c81e5-116">The `<ObjectDataProvider>` tag, which spans lines 11 through 25, declares a <xref:System.Windows.Data.ObjectDataProvider>, named `LoadedBooks`, that uses an <xref:System.Xml.Linq.XElement> as the source.</span></span> <span data-ttu-id="c81e5-117">此 <xref:System.Xml.Linq.XElement> 是通过分析嵌入的 XML 文档（一个 `CDATA` 元素）来初始化的。</span><span class="sxs-lookup"><span data-stu-id="c81e5-117">The <xref:System.Xml.Linq.XElement> is initialized by parsing an embedded XML document (a `CDATA` element).</span></span> <span data-ttu-id="c81e5-118">请注意，在声明嵌入的 XML 文档以及分析该文档时将保留空白。</span><span class="sxs-lookup"><span data-stu-id="c81e5-118">Notice that white space is preserved when declaring the embedded XML document and also when it's parsed.</span></span> <span data-ttu-id="c81e5-119">之所以保留空格是因为用于显示原始 XML 的 <xref:System.Windows.Controls.TextBlock> 控件没有专门的 XML 格式化功能。</span><span class="sxs-lookup"><span data-stu-id="c81e5-119">White space is preserved because the <xref:System.Windows.Controls.TextBlock> control, which is used to display the raw XML, has no special XML formatting capabilities.</span></span>

<span data-ttu-id="c81e5-120">最后，第 28 行至第 34 行定义一个名为 <xref:System.Windows.DataTemplate> 的 `BookTemplate` 。</span><span class="sxs-lookup"><span data-stu-id="c81e5-120">Lastly, a <xref:System.Windows.DataTemplate> named `BookTemplate` is defined on lines 28 through 34.</span></span> <span data-ttu-id="c81e5-121">此模板将用于显示“Book List”（书籍列表）UI 区域中的条目。</span><span class="sxs-lookup"><span data-stu-id="c81e5-121">This template is used to display the entries in the **Book List** UI section.</span></span> <span data-ttu-id="c81e5-122">它使用数据绑定和 LINQ to XML 动态属性通过下面的赋值来检索书籍 ID 和书名：</span><span class="sxs-lookup"><span data-stu-id="c81e5-122">It uses data binding and LINQ to XML dynamic properties to retrieve the book ID and book name through the following assignments:</span></span>

```xaml
Text="{Binding Path=Attribute[id].Value}"Text="{Binding Path=Value}"
```

## <a name="data-binding-code"></a><span data-ttu-id="c81e5-123">数据绑定代码</span><span class="sxs-lookup"><span data-stu-id="c81e5-123">Data binding code</span></span>

<span data-ttu-id="c81e5-124">除 <xref:System.Windows.DataTemplate> 元素外，本文件中的许多其他位置也使用数据绑定。</span><span class="sxs-lookup"><span data-stu-id="c81e5-124">In addition to the <xref:System.Windows.DataTemplate> element, data binding is used in a number of other places in this file.</span></span>

<span data-ttu-id="c81e5-125">在第 38 行的 `<StackPanel>` 开始标记中，此面板的 <xref:System.Windows.FrameworkElement.DataContext%2A> 属性设置为 `LoadedBooks` 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="c81e5-125">In the opening `<StackPanel>` tag on line 38, the <xref:System.Windows.FrameworkElement.DataContext%2A> property of this panel is set to the `LoadedBooks` data provider.</span></span>

```xaml
DataContext="{Binding Source={StaticResource LoadedBooks}}
```

<span data-ttu-id="c81e5-126">设置数据上下文使名为 `tbRawXml` 的 <xref:System.Windows.Controls.TextBlock>（第 46 行）能够通过绑定到此数据提供程序的 `Xml` 属性来显示原始 XML：</span><span class="sxs-lookup"><span data-stu-id="c81e5-126">Setting the data context makes it possible (on line 46) for the <xref:System.Windows.Controls.TextBlock> named `tbRawXml` to display the raw XML by binding to this data provider's `Xml` property:</span></span>

```xaml
Text="{Binding Path=Xml}"
```

<span data-ttu-id="c81e5-127">从第 58 行至第 62 行，“Book List”（书籍列表） <xref:System.Windows.Controls.ListBox>**UI 区域中的** 将其显示项的模板设置为在窗口资源区域中定义的 `BookTemplate` ：</span><span class="sxs-lookup"><span data-stu-id="c81e5-127">The <xref:System.Windows.Controls.ListBox> in the **Book List** UI section, on lines 58 through 62, sets the template for its display items to the `BookTemplate` defined in the window resource section:</span></span>

```xaml
ItemTemplate ="{StaticResource BookTemplate}"
```

<span data-ttu-id="c81e5-128">然后，第 59 行至第 62 行将书籍的实际值绑定到此列表框：</span><span class="sxs-lookup"><span data-stu-id="c81e5-128">Then, on lines 59 through 62, the actual values of the books are bound to this list box:</span></span>

```xaml
<ListBox.ItemsSource>
    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
</ListBox.ItemsSource>
```

<span data-ttu-id="c81e5-129">在第三个 UI 区域 **“Edit Selected Book”（编辑所选书籍）** 中，首先将父 <xref:System.Windows.FrameworkElement.DataContext%2A> 的 <xref:System.Windows.Controls.StackPanel> 绑定到 **“Book List”（书籍列表）** UI 区域中的当前所选项（第 82 行）：</span><span class="sxs-lookup"><span data-stu-id="c81e5-129">The third UI section, **Edit Selected Book**, first binds the <xref:System.Windows.FrameworkElement.DataContext%2A> of the parent <xref:System.Windows.Controls.StackPanel> to the currently selected item in from the **Book List** UI section (line 82):</span></span>

```xaml
DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}"
```

<span data-ttu-id="c81e5-130">然后使用双向数据绑定，使书籍元素的当前值显示在此面板的两个文本框中并从中进行更新。</span><span class="sxs-lookup"><span data-stu-id="c81e5-130">It then uses two-way data binding, so that the current values of the book elements are displayed to, and updated from, the two text boxes in this panel.</span></span> <span data-ttu-id="c81e5-131">数据绑定到动态属性类似于在 `BookTemplate` 数据模板中使用数据绑定：</span><span class="sxs-lookup"><span data-stu-id="c81e5-131">Data binding to dynamic properties is similar to the data binding used in the `BookTemplate` data template:</span></span>

```xaml
Text="{Binding Path=Attribute[id].Value}"...Text="{Binding Path=Value}"
```

<span data-ttu-id="c81e5-132">最后一个 UI 区域“Add New Book”（新增书籍）不在其 XAML 代码中使用数据绑定。</span><span class="sxs-lookup"><span data-stu-id="c81e5-132">The last UI section, **Add New Book**, doesn't use data binding in its XAML code.</span></span> <span data-ttu-id="c81e5-133">数据绑定在 L2DBForm.xaml.cs 文件的事件处理代码中。</span><span class="sxs-lookup"><span data-stu-id="c81e5-133">Instead, data binding is in its event handling code in the file *L2DBForm.xaml.cs*.</span></span>

## <a name="example"></a><span data-ttu-id="c81e5-134">示例</span><span class="sxs-lookup"><span data-stu-id="c81e5-134">Example</span></span>

### <a name="description"></a><span data-ttu-id="c81e5-135">描述</span><span class="sxs-lookup"><span data-stu-id="c81e5-135">Description</span></span>

> [!NOTE]
> <span data-ttu-id="c81e5-136">建议您将下面的代码复制到代码编辑器（如 Visual Studio 中的 C# 源代码编辑器）中，以便更易于跟踪行号。</span><span class="sxs-lookup"><span data-stu-id="c81e5-136">We recommend that you copy the following code below into a code editor, such as the C# source code editor in Visual Studio, so that line numbers will be easier to track.</span></span>

### <a name="code"></a><span data-ttu-id="c81e5-137">代码</span><span class="sxs-lookup"><span data-stu-id="c81e5-137">Code</span></span>

```xml
<Window x:Class="LinqToXmlDataBinding.L2XDBForm"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:system="clr-namespace:System;assembly=mscorlib"
    xmlns:xlinq="clr-namespace:System.Xml.Linq;assembly=System.Xml.Linq"
    xmlns:local="clr-namespace:LinqToXmlDataBinding"
    Title="WPF Data Binding using LINQ-to-XML" Height="665" Width="500" ResizeMode="NoResize">

    <Window.Resources>
        <!-- Books provider and inline data -->
        <ObjectDataProvider x:Key="LoadedBooks" ObjectType="{x:Type xlinq:XElement}" MethodName="Parse">
            <ObjectDataProvider.MethodParameters>
                <system:String xml:space="preserve">
<![CDATA[
<books xmlns="http://www.mybooks.com">
  <book id="0">book zero</book>
  <book id="1">book one</book>
  <book id="2">book two</book>
  <book id="3">book three</book>
</books>
]]>
                </system:String>
                <xlinq:LoadOptions>PreserveWhitespace</xlinq:LoadOptions>
            </ObjectDataProvider.MethodParameters>
        </ObjectDataProvider>

        <!-- Template for use in Books List listbox. -->
        <DataTemplate x:Key="BookTemplate">
            <StackPanel Orientation="Horizontal">
                <TextBlock Margin="3" Text="{Binding Path=Attribute[id].Value}"/>
                <TextBlock Margin="3" Text="-"/>
                <TextBlock Margin="3" Text="{Binding Path=Value}"/>
            </StackPanel>
        </DataTemplate>
    </Window.Resources>

    <!-- Main visual content container -->
    <StackPanel Background="lightblue" DataContext="{Binding Source={StaticResource LoadedBooks}}">
        <!-- Raw XML display section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">XML
            <Label.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Label.LayoutTransform>
            </Label>
            <TextBlock Name="tbRawXml" Height="200" Background="LightGray" Text="{Binding Path=Xml}" TextTrimming="CharacterEllipsis" />
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- List box to display all books section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">Book List
                <Label.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Label.LayoutTransform>
            </Label>
            <ListBox Name="lbBooks" Height="200" Width="415" ItemTemplate ="{StaticResource BookTemplate}">
                <ListBox.ItemsSource>
                    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
                </ListBox.ItemsSource>
            </ListBox>
            <Button Margin="5" DockPanel.Dock="Right" Height="30" Width ="130" Content="Remove Selected Book" Click="OnRemoveBook">
            <Button.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Button.LayoutTransform>
            </Button>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Edit current selection section -->
        <DockPanel Margin="5">
            <TextBlock Margin="5" Height="30" Width="65" DockPanel.Dock="Right" Background="LightGray" TextWrapping="Wrap" TextAlignment="Center">
                    Changes are live!
                <TextBlock.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </TextBlock.LayoutTransform>
            </TextBlock>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Edit Selected Book</Label>
                <StackPanel Margin="1" DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="editAttributeTextBox" Width="410" Text="{Binding Path=Attribute[id].Value}">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book ID and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="editValueTextBox" Width="410" Text="{Binding Path=Value}" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book Value and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Add new book section -->
        <DockPanel Margin="5">
            <Button Margin="5" Height="30" DockPanel.Dock="Right" Click ="OnAddBook">Add Book
                <Button.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Button.LayoutTransform>
            </Button>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Add New Book</Label>
                <StackPanel Margin="1">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="tbAddID" Width="410">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="tbAddValue" Width="410" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="UltraBold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>
    </StackPanel>
</Window>
```

### <a name="comments"></a><span data-ttu-id="c81e5-138">注释</span><span class="sxs-lookup"><span data-stu-id="c81e5-138">Comments</span></span>

<span data-ttu-id="c81e5-139">有关与 WPF UI 元素相关联的事件处理程序的 C# 源代码，请参阅 [L2DBForm.xaml.cs 源代码](l2dbform-xaml-cs-source-code.md)。</span><span class="sxs-lookup"><span data-stu-id="c81e5-139">For the C# source code for the event handlers associated with the WPF UI elements, see [L2DBForm.xaml.cs source code](l2dbform-xaml-cs-source-code.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c81e5-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c81e5-140">See also</span></span>

- [<span data-ttu-id="c81e5-141">演练：LinqToXmlDataBinding 示例</span><span class="sxs-lookup"><span data-stu-id="c81e5-141">Walkthrough: LinqToXmlDataBinding example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="c81e5-142">L2DBForm.xaml.cs 源代码</span><span class="sxs-lookup"><span data-stu-id="c81e5-142">L2DBForm.xaml.cs source code</span></span>](l2dbform-xaml-cs-source-code.md)
