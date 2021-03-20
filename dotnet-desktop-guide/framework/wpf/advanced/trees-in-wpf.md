---
title: Trees
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- logical tree [WPF]
- element tree [WPF]
- visual tree [WPF]
ms.assetid: e83f25e5-d66b-4fc7-92d2-50130c9a6649
ms.openlocfilehash: 5375b5893c826f3eeeedf8e290dfef269a142e4a
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664686"
---
# <a name="trees-in-wpf"></a>WPF 中的树

在许多技术中，元素和组件都按树结构的形式组织。在这种结构中，开发人员可以直接操作树中的对象节点来影响应用程序的绘制或行为。 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 也使用了若干树结构形式来定义程序元素之间的关系。 多数情况下，在概念层面考虑对象树形式时，WPF 开发人员会用代码创建应用程序，或用 XAML 定义应用程序的组成部分，但他们会调用具体的 API 或使用特定的标记来执行此操作，而不是像在 XML DOM 中那样，使用某些常规对象树操作 API。 WPF 公开了两个帮助器类，它们提供树比喻视图 <xref:System.Windows.LogicalTreeHelper> 和 <xref:System.Windows.Media.VisualTreeHelper> 。 WPF 文档中还使用了“可视化树”和“逻辑树”两个术语，它们有助于理解某些关键 WPF 功能的行为。 本主题定义了可视化树和逻辑树表示的内容，讨论了此类树如何与整体对象树概念相关，并介绍了 <xref:System.Windows.LogicalTreeHelper> 和 <xref:System.Windows.Media.VisualTreeHelper> 。  

<a name="element_tree"></a>

## <a name="trees-in-wpf"></a>WPF 中的树  

 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 中，最完整的树结构是对象树。 如果在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中定义一个应用程序页，然后加载 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]，将根据标记中元素之间的嵌套关系来创建树结构。 如果使用代码定义应用程序或应用程序的一部分，则将根据为属性（属性实现给定对象的内容模型）分配属性值的方式来创建树结构。 在 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 中，完整的对象树可通过两种方式进行概念化并报告给其公共 API：作为逻辑树和作为可视化树。 逻辑树与可视化树之间的区别不一定重要，但在某些 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 子系统中它们偶尔可能会导致问题，并影响你对标记或代码的选择。  
  
 尽管你并不会总是直接操作逻辑树或可视化树，但理解它们之间的关系有助于你从技术角度了解 WPF。 若要理解 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 中属性继承和事件路由的工作原理，将 WPF 视为某种树形式也相当重要。  
  
> [!NOTE]
> 因为对象树更像是概念，而不像是实际 API，所以还可以将此概念视为对象图。 实际上，在运行时，对象之间的某些关系不能由树形式表示。 尽管如此，树形式的相关性还是很强，尤其是对于 XAML 定义的 UI。因此，大多数 WPF 文档在引用这个常见概念时，仍使用术语“对象树”。  
  
<a name="logical_tree"></a>

## <a name="the-logical-tree"></a>逻辑树  

 在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 中，通过为支持 UI 元素的对象设置属性，可以向这些 UI 元素添加内容。 例如， <xref:System.Windows.Controls.ListBox> 通过操作属性来向控件添加项 <xref:System.Windows.Controls.ItemsControl.Items%2A> 。 通过执行此操作，您要将项放入作为 <xref:System.Windows.Controls.ItemCollection> <xref:System.Windows.Controls.ItemsControl.Items%2A> 属性值的中。 同样，若要将对象添加到 <xref:System.Windows.Controls.DockPanel> 中，可以操作其 <xref:System.Windows.Controls.Panel.Children%2A> 属性值。 此处，你要将对象添加到中 <xref:System.Windows.Controls.UIElementCollection> 。 有关代码示例，请参阅 [如何：动态添加元素](/previous-versions/dotnet/netframework-4.0/ms752374(v=vs.100))。  
  
 在中， [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 当你将中的列表项放入 <xref:System.Windows.Controls.ListBox> 或控件或中的其他 UI 元素时 <xref:System.Windows.Controls.DockPanel> ，你也可以 <xref:System.Windows.Controls.ItemsControl.Items%2A> <xref:System.Windows.Controls.Panel.Children%2A> 显式或隐式使用和属性，如下面的示例中所示。  
  
 [!code-xaml[TreeOvwsSupport#AllCode](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeOvwsSupport/CS/page1.xaml#allcode)]  
  
 如果此 XAML 是作为文档对象模型下的 XML 进行处理，且已包含作为隐式项禁止注释的标记（可能是合法的），生成的 XML DOM 树已包含 `<ListBox.Items>` 的元素以及其他隐式项。 但是，读取标记和写入对象时，XAML 不会这样处理，生成的对象图不包含 `ListBox.Items`。 但它具有一个 <xref:System.Windows.Controls.ListBox> 名为的属性，该属性 `Items` 包含 <xref:System.Windows.Controls.ItemCollection> ，并且在 <xref:System.Windows.Controls.ItemCollection> 处理 XAML 时已初始化但为空 <xref:System.Windows.Controls.ListBox> 。 然后，将作为的内容的每个子对象元素 <xref:System.Windows.Controls.ListBox> 添加到中的， <xref:System.Windows.Controls.ItemCollection> 由分析器调用添加到 `ItemCollection.Add` 。 此示例将 XAML 处理成对象树，目前这似乎表明所创建的对象树基本上是逻辑树。  
  
 但是，逻辑树并不是应用程序 UI 在运行时存在的整个对象图，即使已分解 XAML 隐式语法项也是如此。这种情况的主要原因是视觉对象和模板。 例如，请考虑 <xref:System.Windows.Controls.Button> 。 逻辑树报告 <xref:System.Windows.Controls.Button> 对象及其字符串 `Content` 。 但在运行时对象树中，此按钮还有更多内容。 特别是，按钮只在屏幕上显示，因为应用了特定的 <xref:System.Windows.Controls.Button> 控件模板。 <xref:System.Windows.Controls.Border>即使在运行时查看逻辑树，在运行时，也不会在逻辑树中报告来自已应用模板的视觉对象 (如) 的视觉对象的模板定义的模板，即使在运行时要查看逻辑树 (如从可见 UI 处理输入事件，然后读取逻辑树) 。 若要查找模板视觉对象，需要改为检查可视化树。  
  
 有关 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 语法如何映射到所创建的对象图，以及 XAML 中隐式语法的详细信息，请参阅 [XAML 语法详述](xaml-syntax-in-detail.md)或 [XAML 概述 (WPF)](/dotnet/desktop-wpf/fundamentals/xaml)。  
  
<a name="tree_property_inheritance_event_routing"></a>

### <a name="the-purpose-of-the-logical-tree"></a>逻辑树用途  

 借助逻辑树，内容模型可以方便地循环访问其可能的子对象，从而实现扩展。 此外，逻辑树还为某些通知提供框架，例如在加载逻辑树中的所有对象时。 基本上，逻辑树是框架级别的近似运行时对象图（排除了视觉对象），但其足以用于对你自己的运行时应用程序组合执行多种查询操作。  
  
 此外，通过在初始请求对象上的集合的逻辑树中向上查找 <xref:System.Windows.FrameworkElement.Resources%2A> ，然后继续运行逻辑树并检查每个 <xref:System.Windows.FrameworkElement> (或 <xref:System.Windows.FrameworkContentElement>) 对于 `Resources` 包含 <xref:System.Windows.ResourceDictionary> （可能包含该密钥）的另一个值，可以解析静态和动态资源引用。 当同时存在逻辑树和可视化树时，将使用逻辑树进行资源查找。 有关资源字典和查找的详细信息，请参见 [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)。  
  
<a name="composition"></a>

### <a name="composition-of-the-logical-tree"></a>逻辑树的构成  

 逻辑树在 WPF 框架级别定义，这意味着，与逻辑树操作最相关的 WPF 基元素是 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement> 。 然而，如您所看到的实际使用的 <xref:System.Windows.LogicalTreeHelper> 是 API，逻辑树有时会包含不是或的节点 <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> 。 例如，逻辑树报告的 <xref:System.Windows.Controls.TextBlock.Text%2A> 值 <xref:System.Windows.Controls.TextBlock> ，它是一个字符串。  
  
<a name="override_logical_tree"></a>

### <a name="overriding-the-logical-tree"></a>替代逻辑树  

 高级控件作者可以通过重写几个 Api 来重写逻辑树，这些 Api 定义了常规对象或内容模型在逻辑树中添加或删除对象的方式。 有关如何替代逻辑树的示例，请参阅[替代逻辑树](how-to-override-the-logical-tree.md)。  
  
<a name="pvi"></a>

### <a name="property-value-inheritance"></a>属性值继承  

 属性值继承通过混合树操作。 实际的元数据（包含 <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A> 启用属性继承的属性）是 WPF 框架级别的 <xref:System.Windows.FrameworkPropertyMetadata> 类。 因此，持有原始值的父对象和继承该值的子对象都必须为 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement> ，并且它们必须都是某个逻辑树的一部分。 但是，对于支持属性继承的现有 WPF 属性，属性值的继承可通过逻辑树中没有的中介对象永久存在。 这主要适用于以下情况：让模板元素使用在应用了模板的实例上设置的任何继承属性值，或者使用在更高级别的页级构成（因此在逻辑树中也位于更高位置）中设置的任何继承属性值。 为了使属性值的继承在这两种情况下保持一致，继承属性必须注册为附加属性。如果要定义具有属性继承行为的自定义依赖属性，则应采用这种模式。 无法通过帮助器类实用工具方法完全预测属性继承确切使用的树，即使在运行时也是如此。 有关详细信息，请参阅[属性值继承](property-value-inheritance.md)。  
  
<a name="two_trees"></a>

## <a name="the-visual-tree"></a>可视化树  

 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 中除了逻辑树的概念，还存在可视化树的概念。 可视化树描述了可视化对象的结构，由 <xref:System.Windows.Media.Visual> 基类表示。 为控件编写模板时，将定义或重新定义适用于该控件的可视化树。 对于出于性能和优化考虑需要对绘图进行较低级别控制的开发人员来说，他们也会对可视化树感兴趣。 在传统 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序编程中，可视化树的一个应用是：路由事件的事件路由大多遍历可视化树而非逻辑树。 路由事件行为的这种微妙之处可能不会很明显，除非你是控件作者。 通过可视化树对事件进行路由可使控件在可视化级别实现组合以处理事件或创建事件资源库。  
  
<a name="trees_content"></a>

## <a name="trees-content-elements-and-content-hosts"></a>树、内容元素和内容宿主  

 派生自)  (类的内容元素 <xref:System.Windows.ContentElement> 不是可视化树的一部分; 它们不是从继承的 <xref:System.Windows.Media.Visual> ，也不具有可视表示形式。 若要在 UI 中显示，必须在同时作为 <xref:System.Windows.ContentElement> <xref:System.Windows.Media.Visual> 和逻辑树参与者的内容主机中承载。 通常，此类对象为 <xref:System.Windows.FrameworkElement> 。 从概念上讲，内容宿主有些类似于内容的“浏览器”，它选择在该宿主控制的屏幕区域中显示内容的方式。 承载内容时，可以使内容成为通常与可视化树关联的某些树进程的参与者。 通常情况下， <xref:System.Windows.FrameworkElement> 主机类包括实现代码，该代码 <xref:System.Windows.ContentElement> 通过 content 逻辑树的子节点将所有宿主添加到事件路由，即使寄宿内容不是真正的可视化树的一部分。 这是必需的，以便 <xref:System.Windows.ContentElement> 可以将路由的路由事件作为路由到自身之外的任何元素的源。  
  
<a name="tree_traversal"></a>

## <a name="tree-traversal"></a>树遍历  

 <xref:System.Windows.LogicalTreeHelper>类 <xref:System.Windows.LogicalTreeHelper.GetChildren%2A> <xref:System.Windows.LogicalTreeHelper.GetParent%2A> <xref:System.Windows.LogicalTreeHelper.FindLogicalNode%2A> 为逻辑树遍历提供、和方法。 在大多数情况下，不需要遍历现有控件的逻辑树，因为这些控件几乎总是将其逻辑子元素公开为一个专用集合属性，这种属性支持集合访问，如 `Add`、索引器等等。 树遍历主要是一种方案，控件作者可以选择不从预期的控件模式派生 <xref:System.Windows.Controls.ItemsControl> ，如或 <xref:System.Windows.Controls.Panel> 已定义集合属性的位置，以及要提供自己的集合属性支持的用户。  
  
 可视化树还支持 visual tree 遍历的帮助器类 <xref:System.Windows.Media.VisualTreeHelper> 。 可视化树不会通过特定于控件的属性方便地公开，因此， <xref:System.Windows.Media.VisualTreeHelper> 如果您的编程方案需要，则建议使用类遍历可视化树。 有关详细信息，请参阅 [WPF 图形呈现概述](../graphics-multimedia/wpf-graphics-rendering-overview.md)。  
  
> [!NOTE]
> 有时有必要检查所应用模板的可视化树。 执行此操作时应谨慎。 即使您正在遍历定义模板的控件的可视化树，控件的使用者也可以通过设置实例的属性来更改模板， <xref:System.Windows.Controls.Control.Template%2A> 甚至最终用户也可以通过更改系统主题来影响应用的模板。  
  
<a name="routes"></a>

## <a name="routes-for-routed-events-as-a-tree"></a>“树”形式路由事件的路由  

 如前所述，对于任何给定的路由事件，其路由都沿着一条预定的树路径进行，这棵树是可视化树和逻辑树表示形式的混合体。 事件路由可在树中向上或向下进行，具体取决于该事件是隧道路由事件还是浮升路由事件。 事件路由概念没有直接支持的帮助器类（此类可用于独立于引发实际路由的事件，遍历事件）。 有一个表示路由的类 <xref:System.Windows.EventRoute> ，但该类的方法通常仅供内部使用。  
  
<a name="resourcesandtrees"></a>

## <a name="resource-dictionaries-and-trees"></a>资源字典和树  

 对页中定义的所有 `Resources` 进行资源字典查找时，基本上遍历逻辑树。 逻辑树之外的对象可以引用键控资源，但资源查找顺序将从该对象与逻辑树的连接点开始。 在 WPF 中，只有逻辑树节点可以具有 `Resources` 包含的属性 <xref:System.Windows.ResourceDictionary> ，因此，在从查找用于加密资源的可视化树方面没有任何好处 <xref:System.Windows.ResourceDictionary> 。  
  
 但是，资源查找也可以超出直接逻辑树。 对于应用程序标记，资源查找可向前继续进行到应用程序级资源字典，然后再到作为静态属性或键进行引用的主题支持和系统值。 如果资源引用是动态的，则主题本身也可以引用主题逻辑树之外的系统值。 有关资源字典和查找逻辑的详细信息，请参阅 [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)。  
  
## <a name="see-also"></a>请参阅

- [输入概述](input-overview.md)
- [WPF 图形呈现疑难解答](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [路由事件概述](routed-events-overview.md)
- [不在对象树中的对象元素的初始化](initialization-for-object-elements-not-in-an-object-tree.md)
- [WPF 体系结构](wpf-architecture.md)
