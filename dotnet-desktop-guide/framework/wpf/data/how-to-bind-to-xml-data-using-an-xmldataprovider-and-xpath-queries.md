---
title: 如何：使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据
ms.date: 03/30/2017
helpviewer_keywords:
- XmlDataProvider [WPF], binding to XML data
- data binding [WPF], binding to XML data using XmlDataProvider queries
- binding [WPF], to XML data using XmlDataProvider queries
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
ms.openlocfilehash: c32905e567058710514097136d39c8471df2c237
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664089"
---
# <a name="how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries"></a><span data-ttu-id="4ba28-102">如何：使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据</span><span class="sxs-lookup"><span data-stu-id="4ba28-102">How to: Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>
<span data-ttu-id="4ba28-103">此示例演示如何使用绑定到 XML 数据 <xref:System.Windows.Data.XmlDataProvider> 。</span><span class="sxs-lookup"><span data-stu-id="4ba28-103">This example shows how to bind to XML data using an <xref:System.Windows.Data.XmlDataProvider>.</span></span>  
  
 <span data-ttu-id="4ba28-104">利用 <xref:System.Windows.Data.XmlDataProvider> ，可以通过应用程序中的数据绑定访问的基础数据可以是 XML 节点的任意树。</span><span class="sxs-lookup"><span data-stu-id="4ba28-104">With an <xref:System.Windows.Data.XmlDataProvider>, the underlying data that can be accessed through data binding in your application can be any tree of XML nodes.</span></span> <span data-ttu-id="4ba28-105">换句话说，是一 <xref:System.Windows.Data.XmlDataProvider> 种将任何 XML 节点树作为绑定源的简便方法。</span><span class="sxs-lookup"><span data-stu-id="4ba28-105">In other words, an <xref:System.Windows.Data.XmlDataProvider> provides a convenient way to use any tree of XML nodes as a binding source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ba28-106">示例</span><span class="sxs-lookup"><span data-stu-id="4ba28-106">Example</span></span>  
 <span data-ttu-id="4ba28-107">在下面的示例中，数据直接嵌入到部分的 XML *数据岛* 中 <xref:System.Windows.FrameworkElement.Resources%2A> 。</span><span class="sxs-lookup"><span data-stu-id="4ba28-107">In the following example, the data is embedded directly as an XML *data island* within the <xref:System.Windows.FrameworkElement.Resources%2A> section.</span></span> <span data-ttu-id="4ba28-108">XML 数据岛必须包装在标记中， `<x:XData>` 并且始终有一个根节点，这是此示例中的 *清单* 。</span><span class="sxs-lookup"><span data-stu-id="4ba28-108">An XML data island must be wrapped in `<x:XData>` tags and always have a single root node, which is *Inventory* in this example.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ba28-109">XML 数据的根节点具有将 XML 命名空间设置为空字符串的 **xmlns** 属性。</span><span class="sxs-lookup"><span data-stu-id="4ba28-109">The root node of the XML data has an **xmlns** attribute that sets the XML namespace to an empty string.</span></span> <span data-ttu-id="4ba28-110">将 XPath 查询应用到 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 页中内联的数据岛时，需要此属性。</span><span class="sxs-lookup"><span data-stu-id="4ba28-110">This is a requirement for applying XPath queries to a data island that is inline within the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="4ba28-111">在此内联情况下， [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 和数据岛继承 <xref:System.Windows> 命名空间。</span><span class="sxs-lookup"><span data-stu-id="4ba28-111">In this inline case, the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], and thus the data island, inherits the <xref:System.Windows> namespace.</span></span> <span data-ttu-id="4ba28-112">因此，你需要将命名空间设置为空，以使 XPath 查询不受 <xref:System.Windows> 命名空间的限定，这会 misdirect 查询。</span><span class="sxs-lookup"><span data-stu-id="4ba28-112">Because of this, you need to set the namespace blank to keep XPath queries from being qualified by the <xref:System.Windows> namespace, which would misdirect the queries.</span></span>  
  
 [!code-xaml[XMLDataSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="4ba28-113">如此示例中所示，若要使用属性语法创建相同的绑定声明，必须对特殊字符进行正确转义。</span><span class="sxs-lookup"><span data-stu-id="4ba28-113">As shown in this example, to create the same binding declaration in attribute syntax you must escape the special characters properly.</span></span> <span data-ttu-id="4ba28-114">有关详细信息，请参阅 [XML 字符实体和 XAML](/dotnet/desktop-wpf/xaml-services/xml-character-entities)。</span><span class="sxs-lookup"><span data-stu-id="4ba28-114">For more information, see [XML Character Entities and XAML](/dotnet/desktop-wpf/xaml-services/xml-character-entities).</span></span>  
  
 <span data-ttu-id="4ba28-115"><xref:System.Windows.Controls.ListBox>运行此示例时，将显示以下各项。</span><span class="sxs-lookup"><span data-stu-id="4ba28-115">The <xref:System.Windows.Controls.ListBox> will show the following items when this example is run.</span></span> <span data-ttu-id="4ba28-116">这些项为 *Books* 下所有元素的 *Title*，其中 *Stock* 值为“*out*”，*Number* 值为 3 或者大于或等于 8。</span><span class="sxs-lookup"><span data-stu-id="4ba28-116">These are the *Title* s of all of the elements under *Books* with either a *Stock* value of "*out*" or a *Number* value of 3 or greater than or equals to 8.</span></span> <span data-ttu-id="4ba28-117">请注意，不会返回任何 *CD* 项，因为在 <xref:System.Windows.Data.XmlDataProvider.XPath%2A> 上设置的值 <xref:System.Windows.Data.XmlDataProvider> 指示只应公开 *图书* 元素， (实质上是设置筛选器) 。</span><span class="sxs-lookup"><span data-stu-id="4ba28-117">Notice that no *CD* items are returned because the <xref:System.Windows.Data.XmlDataProvider.XPath%2A> value set on the <xref:System.Windows.Data.XmlDataProvider> indicates that only the *Books* elements should be exposed (essentially setting a filter).</span></span>  
  
 ![显示四本书标题的 XPath 示例的屏幕截图。](./media/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries/xpath-example-listbox-details.png)  
  
 <span data-ttu-id="4ba28-119">在此示例中，将显示书籍标题，因为 <xref:System.Windows.Data.Binding.XPath%2A> 中的 <xref:System.Windows.Controls.TextBlock> 绑定的将 <xref:System.Windows.DataTemplate> 设置为 "*Title*"。</span><span class="sxs-lookup"><span data-stu-id="4ba28-119">In this example, the book titles are displayed because the <xref:System.Windows.Data.Binding.XPath%2A> of the <xref:System.Windows.Controls.TextBlock> binding in the <xref:System.Windows.DataTemplate> is set to "*Title*".</span></span> <span data-ttu-id="4ba28-120">如果要显示特性的值（如 *ISBN*），请将该值设置 <xref:System.Windows.Data.Binding.XPath%2A> 为 " `@ISBN` "。</span><span class="sxs-lookup"><span data-stu-id="4ba28-120">If you want to display the value of an attribute, such as the *ISBN*, you would set that <xref:System.Windows.Data.Binding.XPath%2A> value to "`@ISBN`".</span></span>  
  
 <span data-ttu-id="4ba28-121">[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 中的 **XPath** 属性使用 XmlNode.SelectNodes 方法处理。</span><span class="sxs-lookup"><span data-stu-id="4ba28-121">The **XPath** properties in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] are handled by the XmlNode.SelectNodes method.</span></span> <span data-ttu-id="4ba28-122">可以修改 **XPath** 查询以获取不同的结果。</span><span class="sxs-lookup"><span data-stu-id="4ba28-122">You can modify the **XPath** queries to get different results.</span></span> <span data-ttu-id="4ba28-123">下面是 <xref:System.Windows.Data.Binding.XPath%2A> 上一示例中绑定的查询的一些示例 <xref:System.Windows.Controls.ListBox> ：</span><span class="sxs-lookup"><span data-stu-id="4ba28-123">Here are some examples for the <xref:System.Windows.Data.Binding.XPath%2A> query on the bound <xref:System.Windows.Controls.ListBox> from the previous example:</span></span>  
  
- <span data-ttu-id="4ba28-124">`XPath="Book[1]"` 将返回第一个 Book 元素（“XML in Action”）。</span><span class="sxs-lookup"><span data-stu-id="4ba28-124">`XPath="Book[1]"` will return the first book element ("XML in Action").</span></span> <span data-ttu-id="4ba28-125">请注意，**XPath** 索引从 1 而不是从 0 开始。</span><span class="sxs-lookup"><span data-stu-id="4ba28-125">Note that **XPath** indexes are based on 1, not 0.</span></span>  
  
- <span data-ttu-id="4ba28-126">`XPath="Book[@*]"` 将返回带有任意属性的所有 Book 元素。</span><span class="sxs-lookup"><span data-stu-id="4ba28-126">`XPath="Book[@*]"` will return all book elements with any attributes.</span></span>  
  
- <span data-ttu-id="4ba28-127">`XPath="Book[last()-1]"` 将返回第二个至最后一个 Book 元素（“Introducing Microsoft .NET”）。</span><span class="sxs-lookup"><span data-stu-id="4ba28-127">`XPath="Book[last()-1]"` will return the second to last book element ("Introducing Microsoft .NET").</span></span>  
  
- <span data-ttu-id="4ba28-128">`XPath="*[position()>3]"` 将返回除前 3 个元素之外的所有 Book 元素。</span><span class="sxs-lookup"><span data-stu-id="4ba28-128">`XPath="*[position()>3]"` will return all of the book elements except for the first 3.</span></span>  
  
 <span data-ttu-id="4ba28-129">运行 **XPath** 查询时，将返回 <xref:System.Xml.XmlNode> 或 XmlNodes 的列表。</span><span class="sxs-lookup"><span data-stu-id="4ba28-129">When you run an **XPath** query, it returns an <xref:System.Xml.XmlNode> or a list of XmlNodes.</span></span> <span data-ttu-id="4ba28-130"><xref:System.Xml.XmlNode> 是公共语言运行时 (CLR) 对象，这意味着你可以使用 <xref:System.Windows.Data.Binding.Path%2A> 属性绑定到公共语言运行时 (clr) 属性。</span><span class="sxs-lookup"><span data-stu-id="4ba28-130"><xref:System.Xml.XmlNode> is a common language runtime (CLR) object, which means you can use the <xref:System.Windows.Data.Binding.Path%2A> property to bind to the common language runtime (CLR) properties.</span></span> <span data-ttu-id="4ba28-131">再以上述示例为例。</span><span class="sxs-lookup"><span data-stu-id="4ba28-131">Consider the previous example again.</span></span> <span data-ttu-id="4ba28-132">如果该示例的其余部分保持不变，并将 <xref:System.Windows.Controls.TextBlock> 绑定更改为以下内容，则会在中看到返回的 XmlNodes 的名称 <xref:System.Windows.Controls.ListBox> 。</span><span class="sxs-lookup"><span data-stu-id="4ba28-132">If the rest of the example stays the same and you change the <xref:System.Windows.Controls.TextBlock> binding to the following, you will see the names of the returned XmlNodes in the <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="4ba28-133">在此情况下，所有返回节点的名称为“*Book*”。</span><span class="sxs-lookup"><span data-stu-id="4ba28-133">In this case, the name of all the returned nodes is "*Book*".</span></span>  
  
 [!code-xaml[XmlDataSourceVariation#XmlNodePath](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 <span data-ttu-id="4ba28-134">在某些应用程序中，将 XML 作为数据岛嵌入到页面的源中 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 可能不太方便，因为在编译时必须知道数据的确切内容。</span><span class="sxs-lookup"><span data-stu-id="4ba28-134">In some applications, embedding the XML as a data island within the source of the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] page can be inconvenient because the exact content of the data must be known at compile time.</span></span> <span data-ttu-id="4ba28-135">因此，还支持从外部 XML 文件获取数据，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="4ba28-135">Therefore, obtaining the data from an external XML file is also supported, as in the following example:</span></span>  
  
 [!code-xaml[XMLDataSource2#XmlFileExample](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 <span data-ttu-id="4ba28-136">如果 XML 数据位于远程 XML 文件中，则可以通过为属性分配相应的 URL 来定义对数据的访问权限，如下所示 <xref:System.Windows.Data.XmlDataProvider.Source%2A> ：</span><span class="sxs-lookup"><span data-stu-id="4ba28-136">If the XML data resides in a remote XML file, you would define access to the data by assigning an appropriate URL to the <xref:System.Windows.Data.XmlDataProvider.Source%2A> attribute as follows:</span></span>  
  
```xml  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ba28-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ba28-137">See also</span></span>

- <xref:System.Windows.Data.ObjectDataProvider>
- [<span data-ttu-id="4ba28-138">绑定到 XDocument、XElement 或 LINQ for XML 查询结果</span><span class="sxs-lookup"><span data-stu-id="4ba28-138">Bind to XDocument, XElement, or LINQ for XML Query Results</span></span>](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)
- [<span data-ttu-id="4ba28-139">将 Master-Detail 模式用于分层 XML 数据</span><span class="sxs-lookup"><span data-stu-id="4ba28-139">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [<span data-ttu-id="4ba28-140">绑定源概述</span><span class="sxs-lookup"><span data-stu-id="4ba28-140">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="4ba28-141">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="4ba28-141">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="4ba28-142">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="4ba28-142">How-to Topics</span></span>](data-binding-how-to-topics.md)
