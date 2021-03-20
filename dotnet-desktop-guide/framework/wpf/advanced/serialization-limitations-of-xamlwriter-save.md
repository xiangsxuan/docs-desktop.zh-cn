---
title: XamlWriter.Save 的序列化限制
ms.date: 03/30/2017
helpviewer_keywords:
- XamlWriter.Save [WPF], serialization limitations of
- limitations of XamlWriter.Save
- serialization limitations of XamlWriter.Save
ms.assetid: f86acc91-2b67-4039-8555-505734491d36
ms.openlocfilehash: ea1a71da5618d20d4c656ae05dda0c3a1be92cd2
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664933"
---
# <a name="serialization-limitations-of-xamlwritersave"></a>XamlWriter.Save 的序列化限制
API <xref:System.Windows.Markup.XamlWriter.Save%2A> 可用于将应用程序的内容序列化为 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 文件。 但是，对于所序列化的内容有一些显著限制。 本主题对这些限制和某些一般注意事项进行了介绍。  

<a name="Run_Time__Not_Design_Time_Representation"></a>
## <a name="run-time-not-design-time-representation"></a>运行时、非设计时表示形式  
 通过调用序列化的内容的基本原理是， <xref:System.Windows.Markup.XamlWriter.Save%2A> 在运行时，结果将是要序列化的对象的表示形式。 在将加载为内存中对象时，原始文件的多个设计时属性 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 可能已经优化或丢失 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，并且在您调用序列化时不会保留 <xref:System.Windows.Markup.XamlWriter.Save%2A> 。 序列化的结果是应用程序的结构化逻辑树的有效表示形式，但并不一定是生成该树的原始 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 的有效表示形式。 这些问题使得在 <xref:System.Windows.Markup.XamlWriter.Save%2A> 广泛的设计图面中使用序列化变得极其困难 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。  
  
<a name="Serialization_is_Self_Contained"></a>
## <a name="serialization-is-self-contained"></a>序列化是自包含的  
 的序列化输出 <xref:System.Windows.Markup.XamlWriter.Save%2A> 是自包含的; 序列化的所有内容都包含在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 单个页面中，其中包含单个根元素，没有 uri 以外的外部引用。 例如，如果页面从应用程序资源引用了资源，则这些资源看上去如同正在进行序列化的页面的一个组件。  
  
<a name="Extension_References_are_Dereferenced"></a>
## <a name="extension-references-are-dereferenced"></a>取消引用扩展引用  
 由各种标记扩展格式（如 `StaticResource` 或 `Binding`）对对象进行的公共引用将会由序列化进程取消引用。 在应用程序运行时创建内存中对象时，这些对象已被取消引用，并且逻辑不 <xref:System.Windows.Markup.XamlWriter.Save%2A> 会重新访问原始对象 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 来还原此类对序列化输出的引用。 这样可能会将任何数据绑定的或资源获得的值冻结为运行时表示形式最后使用的值，并且只能有限地或间接地区别这样的值与任何其他在本地设置的值。 图像作为对象存在于对象中，而不是作为原始源引用进行序列化，从而丢失最初引用的任何文件名或 URI。 即使是在同一页面内声明的资源，也会序列化到引用点内，而不是保留为资源集合的键。  
  
<a name="Event_Handling_is_Not_Preserved"></a>
## <a name="event-handling-is-not-preserved"></a>不保留事件处理  
 当对通过 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 添加的事件处理程序进行序列化后，不会保留这些事件处理程序。 不具有代码隐藏功能（并且也不具有相关的 x:Code 机制）的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 无法对运行时过程逻辑进行序列化。 因为序列化是自包含的且限于逻辑树，所以不存在用于存储事件处理程序的设施。 因此，会从输出 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中删除事件处理程序特性（特性本身和用于命名处理程序的字符串值）。  
  
<a name="Realistic_Scenarios_for_Use_of_XAMLWriter_Save"></a>
## <a name="realistic-scenarios-for-use-of-xamlwritersave"></a>XAMLWriter.Save 实用方案  
 虽然此处列出的限制相当重要，但仍有几个适用于序列化的合适方案 <xref:System.Windows.Markup.XamlWriter.Save%2A> 。  
  
- 向量或图形输出：所呈现的区域的输出可用于在重新加载时重新生成相同的向量或图形。  
  
- 格式文本和流文档：输出中会保留文本以及文本内的所有元素格式和元素所含内容。 这对类似于剪贴板功能的机制可能非常有用。  
  
- 保留业务对象数据：如果已将数据存储在自定义元素（例如 XML 数据）中，只要业务对象遵循基本 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 规则（如为按引用属性值提供自定义构造函数和转换），就可以通过序列化来永久保留这些业务对象。
