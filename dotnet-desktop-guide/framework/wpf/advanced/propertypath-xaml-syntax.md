---
title: PropertyPath XAML 语法
ms.date: 03/30/2017
helpviewer_keywords:
- PropertyPath object [WPF]
- XAML [WPF], PropertyPath object
ms.assetid: 0e3cdf07-abe6-460a-a9af-3764b4fd707f
ms.openlocfilehash: 6e7a38926415ff9298ae4441e948d3ec1d9f4751
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667091"
---
# <a name="propertypath-xaml-syntax"></a><span data-ttu-id="b62c5-102">PropertyPath XAML 语法</span><span class="sxs-lookup"><span data-stu-id="b62c5-102">PropertyPath XAML Syntax</span></span>

<span data-ttu-id="b62c5-103"><xref:System.Windows.PropertyPath>对象支持使用复杂的内联 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 语法来设置采用 <xref:System.Windows.PropertyPath> 类型作为其值的各种属性。</span><span class="sxs-lookup"><span data-stu-id="b62c5-103">The <xref:System.Windows.PropertyPath> object supports a complex inline [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] syntax for setting various properties that take the <xref:System.Windows.PropertyPath> type as their value.</span></span> <span data-ttu-id="b62c5-104">本主题将 <xref:System.Windows.PropertyPath> 语法记录为应用于绑定和动画语法。</span><span class="sxs-lookup"><span data-stu-id="b62c5-104">This topic documents the <xref:System.Windows.PropertyPath> syntax as applied to binding and animation syntaxes.</span></span>

<a name="where"></a>

## <a name="where-propertypath-is-used"></a><span data-ttu-id="b62c5-105">PropertyPath 的使用情景</span><span class="sxs-lookup"><span data-stu-id="b62c5-105">Where PropertyPath Is Used</span></span>

<span data-ttu-id="b62c5-106"><xref:System.Windows.PropertyPath> 是在若干功能中使用的公共对象 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-106"><xref:System.Windows.PropertyPath> is a common object that is used in several [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] features.</span></span> <span data-ttu-id="b62c5-107">尽管使用共同 <xref:System.Windows.PropertyPath> 传达属性路径信息，但用作类型的每个功能区域的用法 <xref:System.Windows.PropertyPath> 各不相同。</span><span class="sxs-lookup"><span data-stu-id="b62c5-107">Despite using the common <xref:System.Windows.PropertyPath> to convey property path information, the usages for each feature area where <xref:System.Windows.PropertyPath> is used as a type vary.</span></span> <span data-ttu-id="b62c5-108">因此，基于每个功能来讨论语法更为可行。</span><span class="sxs-lookup"><span data-stu-id="b62c5-108">Therefore, it is more practical to document the syntaxes on a per-feature basis.</span></span>

<span data-ttu-id="b62c5-109">主要 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 使用 <xref:System.Windows.PropertyPath> 来描述对象模型路径，以便遍历对象数据源的属性，以及描述目标动画的目标路径。</span><span class="sxs-lookup"><span data-stu-id="b62c5-109">Primarily, [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] uses <xref:System.Windows.PropertyPath> to describe object-model paths for traversing the properties of an object data source, and to describe the target path for targeted animations.</span></span>

<span data-ttu-id="b62c5-110">某些样式和模板属性（如） <xref:System.Windows.Setter.Property%2A?displayProperty=nameWithType> 采用表面上类似的限定属性名称 <xref:System.Windows.PropertyPath> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-110">Some style and template properties such as <xref:System.Windows.Setter.Property%2A?displayProperty=nameWithType> take a qualified property name that superficially resembles a <xref:System.Windows.PropertyPath>.</span></span> <span data-ttu-id="b62c5-111">但这并不是真正的， <xref:System.Windows.PropertyPath> 而是限定的 *所有者。* 由 WPF 处理器启用的属性字符串格式用法 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 与的类型转换器一起 <xref:System.Windows.DependencyProperty> 使用。</span><span class="sxs-lookup"><span data-stu-id="b62c5-111">But this is not a true <xref:System.Windows.PropertyPath>; instead it is a qualified *owner.property* string format usage that is enabled by the WPF [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processor in combination with the type converter for <xref:System.Windows.DependencyProperty>.</span></span>

<a name="databinding_s"></a>

## <a name="propertypath-for-objects-in-data-binding"></a><span data-ttu-id="b62c5-112">数据绑定中对象的 PropertyPath</span><span class="sxs-lookup"><span data-stu-id="b62c5-112">PropertyPath for Objects in Data Binding</span></span>

<span data-ttu-id="b62c5-113">数据绑定是 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 功能，借此可以绑定到任意依赖属性的目标值。</span><span class="sxs-lookup"><span data-stu-id="b62c5-113">Data binding is a [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] feature whereby you can bind to the target value of any dependency property.</span></span> <span data-ttu-id="b62c5-114">但是，此类数据绑定的源不需要是依赖属性；可以是适用数据提供程序能识别的任意属性类型。</span><span class="sxs-lookup"><span data-stu-id="b62c5-114">However, the source of such a data binding need not be a dependency property; it can be any property type that is recognized by the applicable data provider.</span></span> <span data-ttu-id="b62c5-115">属性路径特别用于 <xref:System.Windows.Data.ObjectDataProvider> ，后者用于从公共语言运行时 (CLR) 对象及其属性获取绑定源。</span><span class="sxs-lookup"><span data-stu-id="b62c5-115">Property paths are particularly used for the <xref:System.Windows.Data.ObjectDataProvider>, which is used for obtaining binding sources from common language runtime (CLR) objects and their properties.</span></span>

<span data-ttu-id="b62c5-116">请注意，数据绑定到 XML 不使用 <xref:System.Windows.PropertyPath> ，因为它不 <xref:System.Windows.Data.Binding.Path%2A> 在中使用 <xref:System.Windows.Data.Binding> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-116">Note that data binding to XML does not use <xref:System.Windows.PropertyPath>, because it does not use <xref:System.Windows.Data.Binding.Path%2A> in the <xref:System.Windows.Data.Binding>.</span></span> <span data-ttu-id="b62c5-117">相反，您可以使用 <xref:System.Windows.Data.Binding.XPath%2A> 并将有效的 XPath 语法指定到 XML 文档对象模型 (DOM) 数据。</span><span class="sxs-lookup"><span data-stu-id="b62c5-117">Instead, you use <xref:System.Windows.Data.Binding.XPath%2A> and specify valid XPath syntax into the XML Document Object Model (DOM) of the data.</span></span> <span data-ttu-id="b62c5-118"><xref:System.Windows.Data.Binding.XPath%2A> 还将指定为字符串，但此处未提供说明。请参阅 [使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="b62c5-118"><xref:System.Windows.Data.Binding.XPath%2A> is also specified as a string, but is not documented here; see [Bind to XML Data Using an XMLDataProvider and XPath Queries](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span>

<span data-ttu-id="b62c5-119">理解数据绑定中的属性路径的关键是将绑定到单个属性值设置为目标，或者改为绑定到采用列表或集合的目标属性。</span><span class="sxs-lookup"><span data-stu-id="b62c5-119">A key to understanding property paths in data binding is that you can target the binding to an individual property value, or you can instead bind to target properties that take lists or collections.</span></span> <span data-ttu-id="b62c5-120">如果要绑定集合，例如绑定 <xref:System.Windows.Controls.ListBox> 将根据集合中的数据项数展开的，则属性路径应引用集合对象，而不是单个集合项。</span><span class="sxs-lookup"><span data-stu-id="b62c5-120">If you are binding collections, for instance binding a <xref:System.Windows.Controls.ListBox> that will expand depending on how many data items are in the collection, then your property path should reference the collection object, not individual collection items.</span></span> <span data-ttu-id="b62c5-121">数据绑定引擎会自动将用作数据源的集合与绑定目标的类型匹配，从而导致行为，如 <xref:System.Windows.Controls.ListBox> 使用 items 数组填充。</span><span class="sxs-lookup"><span data-stu-id="b62c5-121">The data binding engine will match the collection used as the data source to the type of the binding target automatically, resulting in behavior such as populating a <xref:System.Windows.Controls.ListBox> with an items array.</span></span>

<a name="singlecurrent"></a>

### <a name="single-property-on-the-immediate-object-as-data-context"></a><span data-ttu-id="b62c5-122">直接对象上作为数据上下文的单个属性</span><span class="sxs-lookup"><span data-stu-id="b62c5-122">Single Property on the Immediate Object as Data Context</span></span>

```xml
<Binding Path="propertyName" ... />
```

<span data-ttu-id="b62c5-123">*propertyName* 必须解析为当前使用中的属性的名称 <xref:System.Windows.FrameworkElement.DataContext%2A> <xref:System.Windows.Data.Binding.Path%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-123">*propertyName* must resolve to be the name of a property that is in the current <xref:System.Windows.FrameworkElement.DataContext%2A> for a <xref:System.Windows.Data.Binding.Path%2A> usage.</span></span> <span data-ttu-id="b62c5-124">如果绑定更新源，则属性必须是可读取/写入的，并且源对象必须可变。</span><span class="sxs-lookup"><span data-stu-id="b62c5-124">If your binding updates the source, that property must be read/write and the source object must be mutable.</span></span>

<a name="singleindex"></a>

### <a name="single-indexer-on-the-immediate-object-as-data-context"></a><span data-ttu-id="b62c5-125">直接对象上作为数据上下文的单个索引器</span><span class="sxs-lookup"><span data-stu-id="b62c5-125">Single Indexer on the Immediate Object as Data Context</span></span>

```xml
<Binding Path="[key]" ... />
```

<span data-ttu-id="b62c5-126">`key` 必须是字典或哈希表的类型化索引，或者是数组的整数索引。</span><span class="sxs-lookup"><span data-stu-id="b62c5-126">`key` must be either the typed index to a dictionary or hash table, or the integer index of an array.</span></span> <span data-ttu-id="b62c5-127">此外，键值必须是可直接绑定到所应用属性的类型。</span><span class="sxs-lookup"><span data-stu-id="b62c5-127">Also, the value of the key must be a type that is directly bindable to the property where it is applied.</span></span> <span data-ttu-id="b62c5-128">例如，可以通过这种方式使用包含字符串键和字符串值的哈希表来绑定到的文本 <xref:System.Windows.Controls.TextBox> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-128">For instance, a hash table that contains string keys and string values can be used this way to bind to Text for a <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="b62c5-129">或者，如果键指向集合或子索引，则可使用此语法绑定到目标集合属性。</span><span class="sxs-lookup"><span data-stu-id="b62c5-129">Or, if the key points to a collection or subindex, you could use this syntax to bind to a target collection property.</span></span> <span data-ttu-id="b62c5-130">否则，需要通过 `<Binding Path="[key].propertyName" .../>` 等语法来引用特定属性。</span><span class="sxs-lookup"><span data-stu-id="b62c5-130">Otherwise, you need to reference a specific property, through a syntax such as `<Binding Path="[key].propertyName" .../>`.</span></span>

<span data-ttu-id="b62c5-131">如有必要，可以指定索引的类型。</span><span class="sxs-lookup"><span data-stu-id="b62c5-131">You can specify the type of the index if necessary.</span></span> <span data-ttu-id="b62c5-132">有关索引属性路径的这一方面的详细信息，请参阅 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-132">For details on this aspect of an indexed property path, see <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.</span></span>

<a name="multipleindirect"></a>

### <a name="multiple-property-indirect-property-targeting"></a><span data-ttu-id="b62c5-133">多个属性（间接属性目标设置）</span><span class="sxs-lookup"><span data-stu-id="b62c5-133">Multiple Property (Indirect Property Targeting)</span></span>

```xml
<Binding Path="propertyName.propertyName2" ... />
```

<span data-ttu-id="b62c5-134">`propertyName` 必须解析为当前的属性的名称 <xref:System.Windows.FrameworkElement.DataContext%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-134">`propertyName` must resolve to be the name of a property that is the current <xref:System.Windows.FrameworkElement.DataContext%2A>.</span></span> <span data-ttu-id="b62c5-135">路径属性 `propertyName` 和 `propertyName2` 可以是关系中的任意属性，其中 `propertyName2` 是存在于类型中的值为 `propertyName` 的属性。</span><span class="sxs-lookup"><span data-stu-id="b62c5-135">The path properties `propertyName` and `propertyName2` can be any properties that exist in a relationship, where `propertyName2` is a property that exists on the type that is the value of `propertyName`.</span></span>

<a name="singleattached"></a>

### <a name="single-property-attached-or-otherwise-type-qualified"></a><span data-ttu-id="b62c5-136">附加的或类型限定的单个属性</span><span class="sxs-lookup"><span data-stu-id="b62c5-136">Single Property, Attached or Otherwise Type-Qualified</span></span>

```xml
<object property="(ownerType.propertyName)" ... />
```

<span data-ttu-id="b62c5-137">圆括号指示中的此属性 <xref:System.Windows.PropertyPath> 应使用部分限定构造。</span><span class="sxs-lookup"><span data-stu-id="b62c5-137">The parentheses indicate that this property in a <xref:System.Windows.PropertyPath> should be constructed using a partial qualification.</span></span> <span data-ttu-id="b62c5-138">它可以使用 XML 命名空间来查找具有适当映射的类型。</span><span class="sxs-lookup"><span data-stu-id="b62c5-138">It can use an XML namespace to find the type with an appropriate mapping.</span></span> <span data-ttu-id="b62c5-139">`ownerType` [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器有权访问的搜索类型，通过 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 每个程序集中的声明。</span><span class="sxs-lookup"><span data-stu-id="b62c5-139">The `ownerType` searches types that a [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processor has access to, through the <xref:System.Windows.Markup.XmlnsDefinitionAttribute> declarations in each assembly.</span></span> <span data-ttu-id="b62c5-140">大部分应用程序都具有映射到 `http://schemas.microsoft.com/winfx/2006/xaml/presentation` 命名空间的默认 XML 命名空间，因此通常仅有自定义类型或该命名空间之外的类型才需要前缀。</span><span class="sxs-lookup"><span data-stu-id="b62c5-140">Most applications have the default XML namespace mapped to the `http://schemas.microsoft.com/winfx/2006/xaml/presentation` namespace, so a prefix is usually only necessary for custom types or types otherwise outside that namespace.</span></span>  <span data-ttu-id="b62c5-141">`propertyName` 必须解析为 `ownerType` 中存在的属性名称。</span><span class="sxs-lookup"><span data-stu-id="b62c5-141">`propertyName` must resolve to be the name of a property existing on the `ownerType`.</span></span> <span data-ttu-id="b62c5-142">此语法一般用于以下任一情况：</span><span class="sxs-lookup"><span data-stu-id="b62c5-142">This syntax is generally used for one of the following cases:</span></span>

- <span data-ttu-id="b62c5-143">路径是在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中的样式或模板（该样式或模板没有指定的目标类型）中指定的。</span><span class="sxs-lookup"><span data-stu-id="b62c5-143">The path is specified in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] that is in a style or template that does not have a specified Target Type.</span></span> <span data-ttu-id="b62c5-144">除此之外，限定用法一般无效，因为在非样式、非模板情况下，属性存在于实例中，而不是类型中。</span><span class="sxs-lookup"><span data-stu-id="b62c5-144">A qualified usage is generally not valid for cases other than this, because in non-style, non-template cases, the property exists on an instance, not a type.</span></span>

- <span data-ttu-id="b62c5-145">属性为附加属性。</span><span class="sxs-lookup"><span data-stu-id="b62c5-145">The property is an attached property.</span></span>

- <span data-ttu-id="b62c5-146">要绑定到静态属性中。</span><span class="sxs-lookup"><span data-stu-id="b62c5-146">You are binding to a static property.</span></span>

<span data-ttu-id="b62c5-147">要用作情节提要目标，指定为的属性 `propertyName` 必须是 <xref:System.Windows.DependencyProperty> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-147">For use as storyboard target, the property specified as `propertyName` must be a <xref:System.Windows.DependencyProperty>.</span></span>

<a name="sourcetraversal"></a>

### <a name="source-traversal-binding-to-hierarchies-of-collections"></a><span data-ttu-id="b62c5-148">源遍历（绑定到集合的层次结构）</span><span class="sxs-lookup"><span data-stu-id="b62c5-148">Source Traversal (Binding to Hierarchies of Collections)</span></span>

```xml
<object Path="propertyName/propertyNameX" ... />
```

<span data-ttu-id="b62c5-149">此语法中的 / 用于在分层数据源对象中导航，并且支持使用连续的 / 字符分多个步骤导航层次结构。</span><span class="sxs-lookup"><span data-stu-id="b62c5-149">The / in this syntax is used to navigate within a hierarchical data source object, and multiple steps into the hierarchy with successive / characters are supported.</span></span> <span data-ttu-id="b62c5-150">源遍历说明了当前记录指针位置，该位置是通过将数据与其视图的 UI 同步而确定的。</span><span class="sxs-lookup"><span data-stu-id="b62c5-150">The source traversal accounts for the current record pointer position, which is determined by synchronizing the data with the UI of its view.</span></span> <span data-ttu-id="b62c5-151">有关与分层数据源对象绑定的详细信息，以及数据绑定中当前记录指针的概念，请参阅[对分层数据使用主-从模式](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)或[数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)。</span><span class="sxs-lookup"><span data-stu-id="b62c5-151">For details on binding with hierarchical data source objects, and the concept of current record pointer in data binding, see [Use the Master-Detail Pattern with Hierarchical Data](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) or [Data Binding Overview](/dotnet/desktop-wpf/data/data-binding-overview).</span></span>

> [!NOTE]
> <span data-ttu-id="b62c5-152">在表面上，此语法类似于 XPath。</span><span class="sxs-lookup"><span data-stu-id="b62c5-152">Superficially, this syntax resembles XPath.</span></span> <span data-ttu-id="b62c5-153">用于绑定到 XML 数据源的真正的 XPath 表达式不用作 <xref:System.Windows.Data.Binding.Path%2A> 值，应改为用于互斥 <xref:System.Windows.Data.Binding.XPath%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="b62c5-153">A true XPath expression for binding to an XML data source is not used as a <xref:System.Windows.Data.Binding.Path%2A> value and should instead be used for the mutually exclusive <xref:System.Windows.Data.Binding.XPath%2A> property.</span></span>

### <a name="collection-views"></a><span data-ttu-id="b62c5-154">集合视图</span><span class="sxs-lookup"><span data-stu-id="b62c5-154">Collection Views</span></span>

<span data-ttu-id="b62c5-155">若要引用一个已命名的集合视图，请使用哈希字符 (`#`) 为集合视图名称添加前缀。</span><span class="sxs-lookup"><span data-stu-id="b62c5-155">To reference a named collection view, prefix the collection view name with the hash character (`#`).</span></span>

### <a name="current-record-pointer"></a><span data-ttu-id="b62c5-156">当前记录指针</span><span class="sxs-lookup"><span data-stu-id="b62c5-156">Current Record Pointer</span></span>

<span data-ttu-id="b62c5-157">若要引用集合视图的当前记录指针或引用主从数据绑定方案，请启用带正斜杠 (`/`) 的路径字符串。</span><span class="sxs-lookup"><span data-stu-id="b62c5-157">To reference the current record pointer for a collection view or master detail data binding scenario, start the path string with a forward slash (`/`).</span></span> <span data-ttu-id="b62c5-158">从当前记录指针开始遍历任何超出正斜杠的路径。</span><span class="sxs-lookup"><span data-stu-id="b62c5-158">Any path past the forward slash is traversed starting from the current record pointer.</span></span>

### <a name="multiple-indexers"></a><span data-ttu-id="b62c5-159">多个索引器</span><span class="sxs-lookup"><span data-stu-id="b62c5-159">Multiple Indexers</span></span>

```xaml
<object Path="[index1,index2...]" ... />
```

<span data-ttu-id="b62c5-160">或</span><span class="sxs-lookup"><span data-stu-id="b62c5-160">or</span></span>

```xaml
<object Path="propertyName[index,index2...]" ... />
```

<span data-ttu-id="b62c5-161">如果给定的对象支持多个索引器，则可以按顺序指定这些索引器，类似于数组引用语法。</span><span class="sxs-lookup"><span data-stu-id="b62c5-161">If a given object supports multiple indexers, those indexers can be specified in order, similar to an array referencing syntax.</span></span> <span data-ttu-id="b62c5-162">上述对象可以是当前上下文，也可以是包含多个索引对象的属性的值。</span><span class="sxs-lookup"><span data-stu-id="b62c5-162">The object in question can be either the current context or the value of a property that contains a multiple index object.</span></span>

<span data-ttu-id="b62c5-163">默认情况下，通过使用基础对象的特性来类型化索引器值。</span><span class="sxs-lookup"><span data-stu-id="b62c5-163">By default, the indexer values are typed by using the characteristics of the underlying object.</span></span> <span data-ttu-id="b62c5-164">如有必要，可以指定索引的类型。</span><span class="sxs-lookup"><span data-stu-id="b62c5-164">You can specify the type of the index if necessary.</span></span> <span data-ttu-id="b62c5-165">有关键入索引器的详细信息，请参阅 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-165">For details on typing the indexers, see <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.</span></span>

<a name="mixing"></a>

### <a name="mixing-syntaxes"></a><span data-ttu-id="b62c5-166">混合语法</span><span class="sxs-lookup"><span data-stu-id="b62c5-166">Mixing Syntaxes</span></span>

<span data-ttu-id="b62c5-167">上述每条语法都可以独立使用。</span><span class="sxs-lookup"><span data-stu-id="b62c5-167">Each of the syntaxes shown above can be interspersed.</span></span> <span data-ttu-id="b62c5-168">例如，下面是一个示例，该示例创建一个属性路径，该属性指向 `ColorGrid` 包含对象像素网格数组的属性的特定 x、y 的颜色路径 <xref:System.Windows.Media.SolidColorBrush> ：</span><span class="sxs-lookup"><span data-stu-id="b62c5-168">For instance, the following is an example that creates a property path to the color at a particular x,y of a `ColorGrid` property that contains a pixel grid array of <xref:System.Windows.Media.SolidColorBrush> objects:</span></span>

```xml
<Rectangle Fill="{Binding ColorGrid[20,30].SolidColorBrushResult}" ... />
```

### <a name="escapes-for-property-path-strings"></a><span data-ttu-id="b62c5-169">属性路径字符串的转义</span><span class="sxs-lookup"><span data-stu-id="b62c5-169">Escapes for Property Path Strings</span></span>

<span data-ttu-id="b62c5-170">对于某些业务对象，你可能会遇到这样的情况：属性路径字符串需要转义序列以进行正确分析。</span><span class="sxs-lookup"><span data-stu-id="b62c5-170">For certain business objects, you might encounter a case where the property path string requires an escape sequence in order to parse correctly.</span></span> <span data-ttu-id="b62c5-171">因为大多数此类字符在常用于定义业务对象的语言方面具有类似的命名交互问题，因此转义需要非常少见。</span><span class="sxs-lookup"><span data-stu-id="b62c5-171">The need to escape should be rare, because many of these characters have similar naming-interaction issues in languages that would typically be used to define the business object.</span></span>

- <span data-ttu-id="b62c5-172">在索引器 ([ ]) 内部，脱字符号 (^) 用于对下一个字符进行转义。</span><span class="sxs-lookup"><span data-stu-id="b62c5-172">Inside indexers ([ ]), the caret character (^) escapes the next character.</span></span>

- <span data-ttu-id="b62c5-173">必须（使用 XML 实体）对 XML 语言定义专用的某些字符进行转义。</span><span class="sxs-lookup"><span data-stu-id="b62c5-173">You must escape (using XML entities) certain characters that are special to the XML language definition.</span></span> <span data-ttu-id="b62c5-174">使用 `&` 对字符“&”进行转义。</span><span class="sxs-lookup"><span data-stu-id="b62c5-174">Use `&` to escape the character "&".</span></span> <span data-ttu-id="b62c5-175">使用 `>` 对结束标记“>”进行转义。</span><span class="sxs-lookup"><span data-stu-id="b62c5-175">Use `>` to escape the end tag ">".</span></span>

- <span data-ttu-id="b62c5-176">必须（使用反斜杠 `\`）对特定于 WPF XAML 分析程序行为的字符进行转义，以处理标记扩展。</span><span class="sxs-lookup"><span data-stu-id="b62c5-176">You must escape (using backslash `\`) characters that are special to the WPF XAML parser behavior for processing a markup extension.</span></span>

  - <span data-ttu-id="b62c5-177">反斜杠 (`\`) 本身是转义字符。</span><span class="sxs-lookup"><span data-stu-id="b62c5-177">Backslash (`\`) is the escape character itself.</span></span>

  - <span data-ttu-id="b62c5-178">等号 (`=`) 将属性名与属性值分隔开。</span><span class="sxs-lookup"><span data-stu-id="b62c5-178">The equal sign (`=`) separates property name from property value.</span></span>

  - <span data-ttu-id="b62c5-179">逗号 (`,`) 用于分隔属性。</span><span class="sxs-lookup"><span data-stu-id="b62c5-179">Comma (`,`) separates properties.</span></span>

  - <span data-ttu-id="b62c5-180">右大括号 (`}`) 是标记扩展的结尾。</span><span class="sxs-lookup"><span data-stu-id="b62c5-180">The right curly brace (`}`) is the end of a markup extension.</span></span>

> [!NOTE]
> <span data-ttu-id="b62c5-181">从技术上讲，这些转义符还适用于情节提要属性路径，但通常会遍历适用于现有 WPF 对象的对象模型，转义应该是不必要的。</span><span class="sxs-lookup"><span data-stu-id="b62c5-181">Technically, these escapes work for a storyboard property path also, but you are usually traversing object models for existing WPF objects, and escaping should be unnecessary.</span></span>

<a name="databinding_sa"></a>

## <a name="propertypath-for-animation-targets"></a><span data-ttu-id="b62c5-182">动画目标的 PropertyPath</span><span class="sxs-lookup"><span data-stu-id="b62c5-182">PropertyPath for Animation Targets</span></span>

<span data-ttu-id="b62c5-183">动画的目标属性必须是采用或基元类型的依赖项属性 <xref:System.Windows.Freezable> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-183">The target property of an animation must be a dependency property that takes either a <xref:System.Windows.Freezable> or a primitive type.</span></span> <span data-ttu-id="b62c5-184">但是，类型中的目标属性和最终动画属性可以存在于不同的对象中。</span><span class="sxs-lookup"><span data-stu-id="b62c5-184">However, the targeted property on a type and the eventual animated property can exist on different objects.</span></span> <span data-ttu-id="b62c5-185">对于动画，属性路径用于通过遍历属性值中的对象-属性关系，定义命名动画目标对象的属性和预期目标动画属性之间的连接。</span><span class="sxs-lookup"><span data-stu-id="b62c5-185">For animations, a property path is used to define the connection between the named animation target object's property and the intended target animation property, by traversing object-property relationships in the property values.</span></span>

<a name="general"></a>

### <a name="general-object-property-considerations-for-animations"></a><span data-ttu-id="b62c5-186">动画的一般对象-属性注意事项</span><span class="sxs-lookup"><span data-stu-id="b62c5-186">General Object-Property Considerations for Animations</span></span>

<span data-ttu-id="b62c5-187">有关一般动画概念的详细信息，请参阅[情节提要概述](../graphics-multimedia/storyboards-overview.md)和[动画概述](../graphics-multimedia/animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b62c5-187">For more information on animation concepts in general, see [Storyboards Overview](../graphics-multimedia/storyboards-overview.md) and [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>

<span data-ttu-id="b62c5-188">要进行动画处理的值类型或属性必须是 <xref:System.Windows.Freezable> 类型或基元类型。</span><span class="sxs-lookup"><span data-stu-id="b62c5-188">The value type or the property being animated must be either a <xref:System.Windows.Freezable> type or a primitive.</span></span> <span data-ttu-id="b62c5-189">启动路径的属性必须解析为在指定类型上存在的依赖属性的名称 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-189">The property that starts the path must resolve to be the name of a dependency property that exists on the specified <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> type.</span></span>

<span data-ttu-id="b62c5-190">若要支持克隆以对已冻结的进行动画处理 <xref:System.Windows.Freezable> ，由指定的对象 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 必须是 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement> 派生类。</span><span class="sxs-lookup"><span data-stu-id="b62c5-190">In order to support cloning for animating a <xref:System.Windows.Freezable> that is already frozen, the object specified by <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> must be a <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement> derived class.</span></span>

<a name="singlestepanim"></a>

### <a name="single-property-on-the-target-object"></a><span data-ttu-id="b62c5-191">目标对象上的单个属性</span><span class="sxs-lookup"><span data-stu-id="b62c5-191">Single Property on the Target Object</span></span>

```xml
<animation Storyboard.TargetProperty="propertyName" ... />
```

<span data-ttu-id="b62c5-192">`propertyName` 必须解析为在指定类型上存在的依赖属性的名称 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-192">`propertyName` must resolve to be the name of a dependency property that exists on the specified <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> type.</span></span>

<a name="indirectanim"></a>

### <a name="indirect-property-targeting"></a><span data-ttu-id="b62c5-193">间接属性目标设定</span><span class="sxs-lookup"><span data-stu-id="b62c5-193">Indirect Property Targeting</span></span>

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2" ... />
```

<span data-ttu-id="b62c5-194">`propertyName` 必须是在 <xref:System.Windows.Freezable> 指定类型上存在的值类型或基元类型的属性 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-194">`propertyName` must be a property that is either a <xref:System.Windows.Freezable> value type or a primitive, which exists on the specified <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> type.</span></span>

<span data-ttu-id="b62c5-195">`propertyName2` 必须为依赖属性的名称，该属性存在于作为 `propertyName` 值的对象中。</span><span class="sxs-lookup"><span data-stu-id="b62c5-195">`propertyName2` must be the name of a dependency property that exists on the object that is the value of `propertyName`.</span></span> <span data-ttu-id="b62c5-196">换言之， `propertyName2` 必须作为类型的依赖属性存在于中 `propertyName` <xref:System.Windows.DependencyProperty.PropertyType%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-196">In other words, `propertyName2` must exist as a dependency property on the type that is the `propertyName` <xref:System.Windows.DependencyProperty.PropertyType%2A>.</span></span>

<span data-ttu-id="b62c5-197">因为应用了样式和模板，所以间接设定动画的目标是必要的。</span><span class="sxs-lookup"><span data-stu-id="b62c5-197">Indirect targeting of animations is necessary because of applied styles and templates.</span></span> <span data-ttu-id="b62c5-198">若要以动画为目标，需要 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 在目标对象上，并且该名称是由 [x：Name](/dotnet/desktop-wpf/xaml-services/xname-directive) 或创建的 <xref:System.Windows.FrameworkElement.Name%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-198">In order to target an animation, you need a <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> on a target object, and that name is established by [x:Name](/dotnet/desktop-wpf/xaml-services/xname-directive) or <xref:System.Windows.FrameworkElement.Name%2A>.</span></span> <span data-ttu-id="b62c5-199">虽然模板和样式元素也可以有名称，但这些名称仅在样式和模板的命名范围内有效。</span><span class="sxs-lookup"><span data-stu-id="b62c5-199">Although template and style elements also can have names, those names are only valid within the namescope of the style and template.</span></span> <span data-ttu-id="b62c5-200">（如果模板和样式与应用程序标记共享命名范围，则名称不唯一。</span><span class="sxs-lookup"><span data-stu-id="b62c5-200">(If templates and styles did share namescopes with application markup, names couldn't be unique.</span></span> <span data-ttu-id="b62c5-201">样式和模板按字面方式在实例之间共享，并将保持重复的名称 ) 。因此，如果你可能想要对其进行动画处理的元素的单个属性来自样式或模板，则需要从样式模板中的命名元素实例开始，然后以样式或模板可视化树为目标，以到达要进行动画处理的属性。</span><span class="sxs-lookup"><span data-stu-id="b62c5-201">The styles and templates are literally shared between instances and would perpetuate duplicate names.) Thus, if the individual properties of an element that you might wish to animate came from a style or template, you need to start with a named element instance that is not from a style template, and then target into the style or template visual tree to arrive at the property you wish to animate.</span></span>

<span data-ttu-id="b62c5-202">例如，的 <xref:System.Windows.Controls.Panel.Background%2A> 属性 <xref:System.Windows.Controls.Panel> 是完整的 <xref:System.Windows.Media.Brush> (实际上是 <xref:System.Windows.Media.SolidColorBrush> 来自主题模板) 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-202">For instance, the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Panel> is a complete <xref:System.Windows.Media.Brush> (actually a <xref:System.Windows.Media.SolidColorBrush>) that came from a theme template.</span></span> <span data-ttu-id="b62c5-203">若要完全进行动画处理 <xref:System.Windows.Media.Brush> ，需要 BrushAnimation 的每个) 类型都有一个 (， <xref:System.Windows.Media.Brush> 并且没有此类类型。</span><span class="sxs-lookup"><span data-stu-id="b62c5-203">To animate a <xref:System.Windows.Media.Brush> completely, there would need to be a BrushAnimation (probably one for every <xref:System.Windows.Media.Brush> type) and there is no such type.</span></span> <span data-ttu-id="b62c5-204">若要对画笔进行动画处理，请改为对特定类型的属性进行动画处理 <xref:System.Windows.Media.Brush> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-204">To animate a Brush, you instead animate properties of a particular <xref:System.Windows.Media.Brush> type.</span></span> <span data-ttu-id="b62c5-205">你需要从获取，以 <xref:System.Windows.Media.SolidColorBrush> <xref:System.Windows.Media.SolidColorBrush.Color%2A> 应用 <xref:System.Windows.Media.Animation.ColorAnimation> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-205">You need to get from <xref:System.Windows.Media.SolidColorBrush> to its <xref:System.Windows.Media.SolidColorBrush.Color%2A> to apply a <xref:System.Windows.Media.Animation.ColorAnimation> there.</span></span> <span data-ttu-id="b62c5-206">本示例的属性路径是 `Background.Color`。</span><span class="sxs-lookup"><span data-stu-id="b62c5-206">The property path for this example would be `Background.Color`.</span></span>

<a name="attachedanim"></a>

### <a name="attached-properties"></a><span data-ttu-id="b62c5-207">附加属性</span><span class="sxs-lookup"><span data-stu-id="b62c5-207">Attached Properties</span></span>

```xml
<animation Storyboard.TargetProperty="(ownerType.propertyName)" ... />
```

<span data-ttu-id="b62c5-208">圆括号指示中的此属性 <xref:System.Windows.PropertyPath> 应使用部分限定构造。</span><span class="sxs-lookup"><span data-stu-id="b62c5-208">The parentheses indicate that this property in a <xref:System.Windows.PropertyPath> should be constructed using a partial qualification.</span></span> <span data-ttu-id="b62c5-209">可以使用 XML 命名空间来查找类型。</span><span class="sxs-lookup"><span data-stu-id="b62c5-209">It can use an XML namespace to find the type.</span></span> <span data-ttu-id="b62c5-210">`ownerType` [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器有权访问的搜索类型，通过 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 每个程序集中的声明。</span><span class="sxs-lookup"><span data-stu-id="b62c5-210">The `ownerType` searches types that a [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processor has access to, through the <xref:System.Windows.Markup.XmlnsDefinitionAttribute> declarations in each assembly.</span></span> <span data-ttu-id="b62c5-211">大部分应用程序都具有映射到 `http://schemas.microsoft.com/winfx/2006/xaml/presentation` 命名空间的默认 XML 命名空间，因此通常仅有自定义类型或该命名空间之外的类型才需要前缀。</span><span class="sxs-lookup"><span data-stu-id="b62c5-211">Most applications have the default XML namespace mapped to the `http://schemas.microsoft.com/winfx/2006/xaml/presentation` namespace, so a prefix is usually only necessary for custom types or types otherwise outside that namespace.</span></span> <span data-ttu-id="b62c5-212">`propertyName` 必须解析为 `ownerType` 中存在的属性名称。</span><span class="sxs-lookup"><span data-stu-id="b62c5-212">`propertyName` must resolve to be the name of a property existing on the `ownerType`.</span></span> <span data-ttu-id="b62c5-213">指定为的属性 `propertyName` 必须是 <xref:System.Windows.DependencyProperty> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-213">The property specified as `propertyName` must be a <xref:System.Windows.DependencyProperty>.</span></span> <span data-ttu-id="b62c5-214">（所有 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 附加属性都实现为依赖属性，因此该问题仅与自定义附加属性相关。）</span><span class="sxs-lookup"><span data-stu-id="b62c5-214">(All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] attached properties are implemented as dependency properties, so this issue is only of concern for custom attached properties.)</span></span>

<a name="indexanim"></a>

### <a name="indexers"></a><span data-ttu-id="b62c5-215">索引器</span><span class="sxs-lookup"><span data-stu-id="b62c5-215">Indexers</span></span>

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2[index].propertyName3" ... />
```

<span data-ttu-id="b62c5-216">大多数依赖属性或 <xref:System.Windows.Freezable> 类型不支持索引器。</span><span class="sxs-lookup"><span data-stu-id="b62c5-216">Most dependency properties or <xref:System.Windows.Freezable> types do not support an indexer.</span></span> <span data-ttu-id="b62c5-217">因此，动画路径中唯一使用索引器的地方是在用于启动命名目标上的链的属性与最终动画属性之间的中间位置。</span><span class="sxs-lookup"><span data-stu-id="b62c5-217">Therefore, the only usage for an indexer in an animation path is at an intermediate position between the property that starts the chain on the named target and the eventual animated property.</span></span> <span data-ttu-id="b62c5-218">在提供的语法中，为 `propertyName2`。</span><span class="sxs-lookup"><span data-stu-id="b62c5-218">In the provided syntax, that is `propertyName2`.</span></span> <span data-ttu-id="b62c5-219">例如，如果中间属性为中的集合（如），则可能需要使用索引器 <xref:System.Windows.Media.TransformGroup> `RenderTransform.Children[1].Angle` 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-219">For instance, an indexer usage might be necessary if the intermediate property is a collection such as <xref:System.Windows.Media.TransformGroup>, in a property path such as `RenderTransform.Children[1].Angle`.</span></span>

<a name="ppincode"></a>

## <a name="propertypath-in-code"></a><span data-ttu-id="b62c5-220">代码中的 PropertyPath</span><span class="sxs-lookup"><span data-stu-id="b62c5-220">PropertyPath in Code</span></span>

<span data-ttu-id="b62c5-221">的 <xref:System.Windows.PropertyPath> <xref:System.Windows.PropertyPath> "参考" 主题中介绍了的代码用法，其中包括如何构造 <xref:System.Windows.PropertyPath> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-221">Code usage for <xref:System.Windows.PropertyPath>, including how to construct a <xref:System.Windows.PropertyPath>, is documented in the reference topic for <xref:System.Windows.PropertyPath>.</span></span>

<span data-ttu-id="b62c5-222">通常， <xref:System.Windows.PropertyPath> 旨在使用两个不同的构造函数，一个用于绑定使用情况和最简单的动画用法，一个用于复杂动画用法。</span><span class="sxs-lookup"><span data-stu-id="b62c5-222">In general, <xref:System.Windows.PropertyPath> is designed to use two different constructors, one for the binding usages and simplest animation usages, and one for the complex animation usages.</span></span> <span data-ttu-id="b62c5-223">将 <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> 签名用于绑定用法，其中对象是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="b62c5-223">Use the <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> signature for binding usages, where the object is a string.</span></span> <span data-ttu-id="b62c5-224">将 <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> 签名用于单步动画路径，其中对象是 <xref:System.Windows.DependencyProperty> 。</span><span class="sxs-lookup"><span data-stu-id="b62c5-224">Use the <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> signature for one-step animation paths, where the object is a <xref:System.Windows.DependencyProperty>.</span></span> <span data-ttu-id="b62c5-225">将 <xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29> 签名用于复杂动画。</span><span class="sxs-lookup"><span data-stu-id="b62c5-225">Use the <xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29> signature for complex animations.</span></span> <span data-ttu-id="b62c5-226">后一种构造函数使用第一个参数的令牌字符串，以及在该令牌字符串中填充位置的对象的数组，以定义属性路径关系。</span><span class="sxs-lookup"><span data-stu-id="b62c5-226">This latter constructor uses a token string for the first parameter and an array of objects that fill positions in the token string to define a property path relationship.</span></span>

## <a name="see-also"></a><span data-ttu-id="b62c5-227">请参阅</span><span class="sxs-lookup"><span data-stu-id="b62c5-227">See also</span></span>

- <xref:System.Windows.PropertyPath>
- [<span data-ttu-id="b62c5-228">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="b62c5-228">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="b62c5-229">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="b62c5-229">Storyboards Overview</span></span>](../graphics-multimedia/storyboards-overview.md)
