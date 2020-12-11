---
title: 如何：绑定到 XDocument、XElement 或 LINQ for XML 查询结果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
ms.openlocfilehash: 070f67f30613d4522a48e08fd1c208fbe5887525
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973237"
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a><span data-ttu-id="961f5-102">如何：绑定到 XDocument、XElement 或 LINQ for XML 查询结果</span><span class="sxs-lookup"><span data-stu-id="961f5-102">How to: Bind to XDocument, XElement, or LINQ for XML Query Results</span></span>

<span data-ttu-id="961f5-103">此示例演示如何使用将 XML 数据绑定到 <xref:System.Windows.Controls.ItemsControl> <xref:System.Xml.Linq.XDocument> 。</span><span class="sxs-lookup"><span data-stu-id="961f5-103">This example demonstrates how to bind XML data to an <xref:System.Windows.Controls.ItemsControl> using <xref:System.Xml.Linq.XDocument>.</span></span>

## <a name="example"></a><span data-ttu-id="961f5-104">示例</span><span class="sxs-lookup"><span data-stu-id="961f5-104">Example</span></span>

<span data-ttu-id="961f5-105">下面的 XAML 代码定义 <xref:System.Windows.Controls.ItemsControl> ，并在 `Planet` XML 命名空间中包含类型数据的数据模板 `http://planetsNS` 。</span><span class="sxs-lookup"><span data-stu-id="961f5-105">The following XAML code defines an <xref:System.Windows.Controls.ItemsControl> and includes a data template for data of type `Planet` in the `http://planetsNS` XML namespace.</span></span> <span data-ttu-id="961f5-106">占用命名空间的 XML 数据类型必须包含相应的命名空间（用大括号括起来），并且如果它出现在 XAML 标记扩展可能出现的位置，则还必须在相应命名空间前加上大括号转义序列。</span><span class="sxs-lookup"><span data-stu-id="961f5-106">An XML data type that occupies a namespace must include the namespace in braces, and if it appears where a XAML markup extension could appear, it must precede the namespace with a brace escape sequence.</span></span> <span data-ttu-id="961f5-107">此代码绑定到与类的和方法相对应的动态属性 <xref:System.Xml.Linq.XContainer.Element%2A> <xref:System.Xml.Linq.XElement.Attribute%2A> <xref:System.Xml.Linq.XElement> 。</span><span class="sxs-lookup"><span data-stu-id="961f5-107">This code binds to dynamic properties that correspond to the <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> methods of the <xref:System.Xml.Linq.XElement> class.</span></span> <span data-ttu-id="961f5-108">借助动态属性，XAML 可以绑定到共享方法名称的动态属性。</span><span class="sxs-lookup"><span data-stu-id="961f5-108">Dynamic properties enable XAML to bind to dynamic properties that share the names of methods.</span></span> <span data-ttu-id="961f5-109">若要了解详细信息，请参阅 [LINQ to XML 动态属性](linq-to-xml-dynamic-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="961f5-109">To learn more, see [LINQ to XML dynamic properties](linq-to-xml-dynamic-properties.md).</span></span> <span data-ttu-id="961f5-110">请注意 XML 的默认命名空间声明为何不适用于特性名。</span><span class="sxs-lookup"><span data-stu-id="961f5-110">Notice how the default namespace declaration for the XML does not apply to attribute names.</span></span>

[!code-xaml[XLinqExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]
[!code-xaml[XLinqExample#ItemsControl](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]

<span data-ttu-id="961f5-111">下面的 c # 代码调用 <xref:System.Xml.Linq.XDocument.Load%2A> 并将堆栈面板数据上下文设置为 `SolarSystemPlanets` `http://planetsNS` XML 命名空间中名为的元素的所有子元素。</span><span class="sxs-lookup"><span data-stu-id="961f5-111">The following C# code calls <xref:System.Xml.Linq.XDocument.Load%2A> and sets the stack panel data context to all subelements of the element named `SolarSystemPlanets` in the `http://planetsNS` XML namespace.</span></span>

[!code-csharp[XLinqExample#LoadDCFromFile](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
[!code-vb[XLinqExample#LoadDCFromFile](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]

<span data-ttu-id="961f5-112">可以使用将 XML 数据存储为 XAML 资源 <xref:System.Windows.Data.ObjectDataProvider> 。</span><span class="sxs-lookup"><span data-stu-id="961f5-112">XML data can be stored as a XAML resource using <xref:System.Windows.Data.ObjectDataProvider>.</span></span> <span data-ttu-id="961f5-113">有关完整示例，请参阅[l2dbform.xaml。](l2dbform-xaml-source-code.md)</span><span class="sxs-lookup"><span data-stu-id="961f5-113">For a complete example, see  [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span> <span data-ttu-id="961f5-114">下面的示例演示代码如何将数据上下文设置为对象资源。</span><span class="sxs-lookup"><span data-stu-id="961f5-114">The following sample shows how code can set the data context to an object resource.</span></span>

[!code-csharp[XLinqExample#LoadDCFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
[!code-vb[XLinqExample#LoadDCFromXAML](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]

<span data-ttu-id="961f5-115">动态的属性，它映射到 <xref:System.Xml.Linq.XContainer.Element%2A> 并 <xref:System.Xml.Linq.XElement.Attribute%2A> 在 XAML 中提供灵活性。</span><span class="sxs-lookup"><span data-stu-id="961f5-115">The dynamic properties that map to <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> provide flexibility within XAML.</span></span> <span data-ttu-id="961f5-116">代码还可以绑定到 LINQ for XML 查询的结果。</span><span class="sxs-lookup"><span data-stu-id="961f5-116">Your code can also bind to the results of a LINQ for XML query.</span></span> <span data-ttu-id="961f5-117">此示例绑定到按元素值排序的查询结果。</span><span class="sxs-lookup"><span data-stu-id="961f5-117">This example binds to query results ordered by an element value.</span></span>

[!code-csharp[XLinqExample#BindToResults](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
[!code-vb[XLinqExample#BindToResults](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]

## <a name="see-also"></a><span data-ttu-id="961f5-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="961f5-118">See also</span></span>

- [<span data-ttu-id="961f5-119">绑定源概述</span><span class="sxs-lookup"><span data-stu-id="961f5-119">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="961f5-120">使用 LINQ to XML 进行 WPF 数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="961f5-120">WPF Data Binding with LINQ to XML Overview</span></span>](wpf-data-binding-with-linq-to-xml-overview.md)
- [<span data-ttu-id="961f5-121">使用 LINQ to XML 示例进行 WPF 数据绑定</span><span class="sxs-lookup"><span data-stu-id="961f5-121">WPF Data Binding Using LINQ to XML Example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="961f5-122">LINQ to XML 动态属性</span><span class="sxs-lookup"><span data-stu-id="961f5-122">LINQ to XML Dynamic Properties</span></span>](linq-to-xml-dynamic-properties.md)
