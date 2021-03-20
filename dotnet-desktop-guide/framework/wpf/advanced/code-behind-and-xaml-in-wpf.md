---
title: Code-Behind 和 XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: cb4dbe3d730574fc6ff500802ad31cde7edc7171
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666155"
---
# <a name="code-behind-and-xaml-in-wpf"></a>WPF 中的代码隐藏和 XAML
<a name="introduction"></a> 代码隐藏是一项术语，用于描述在对 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 页进行标记编译时与标记定义的对象联接的代码。 本主题介绍代码隐藏的要求，以及中代码的替代内联代码机制 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。  
  
 本主题包含以下各节：  
  
- [必备条件](#Prerequisites)  
  
- [代码隐藏和 XAML 语言](#codebehind_and_the_xaml_language)  
  
- [WPF 中的代码隐藏、事件处理程序和分部类要求](#Code_behind__Event_Handler__and_Partial_Class)  
  
- [x：Code](#x_Code)  
  
- [内联代码限制](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>
## <a name="prerequisites"></a>必备条件  
 本主题假定您已阅读 [XAML 概述 (WPF) ](/dotnet/desktop-wpf/fundamentals/xaml) ，并对 CLR 和面向对象的编程有一些基本知识。  
  
<a name="codebehind_and_the_xaml_language"></a>
## <a name="code-behind-and-the-xaml-language"></a>Code-Behind 和 XAML 语言  
 XAML 语言包含语言级功能，使您可以将代码文件与标记文件相关联。 具体而言，XAML 语言将定义语言功能 [X：Class 指令](/dotnet/desktop-wpf/xaml-services/xclass-directive)、 [X:Subclass 指令](/dotnet/desktop-wpf/xaml-services/xsubclass-directive)和 [x:ClassModifier 指令](/dotnet/desktop-wpf/xaml-services/xclassmodifier-directive)。 应确切地说明代码的生成方式以及如何集成标记和代码，这并不是 XAML 语言指定内容的一部分。 它留给了框架（如 WPF）来确定如何集成代码，如何在应用程序和编程模型中使用 XAML，以及生成操作或支持所有这些操作所需的其他支持。  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>WPF 中的代码隐藏、事件处理程序和分部类要求  
  
- 分部类必须派生自根元素支持的类型。  
  
- 请注意，在标记编译生成操作的默认行为下，可以在代码隐藏端的分部类定义中保留派生空白。 已编译的结果将假定页根的后备类型为分部类的基础，即使未指定也是如此。 但是，依赖于此行为并不是最佳做法。  
  
- 在代码隐藏中编写的事件处理程序必须是实例方法，并且不能是静态方法。 这些方法必须由标识的 CLR 命名空间中的分部类定义 `x:Class` 。 不能将事件处理程序的名称限定为指示 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器在不同的类范围内查找事件布线的事件处理程序。  
  
- 处理程序必须匹配后备类型系统中相应事件的委托。  
  
- 对于 Microsoft Visual Basic 语言，你可以使用特定于语言的 `Handles` 关键字在处理程序声明中将处理程序与实例和事件关联，而不是使用中的特性附加处理程序 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。 但是，这种方法确实存在一些限制，因为 `Handles` 关键字不能支持事件系统的所有特定功能 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，如某些路由事件方案或附加事件。 有关详细信息，请参阅 [Visual Basic 和 WPF 事件处理](visual-basic-and-wpf-event-handling.md)。  
  
<a name="x_Code"></a>
## <a name="xcode"></a>x：Code  
 [x:Code](/dotnet/desktop-wpf/xaml-services/xcode-intrinsic-xaml-type) 是在中定义的指令元素 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。 `x:Code`指令元素可以包含内联编程代码。 以内联方式定义的代码可以与 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 同一页上的进行交互。 下面的示例演示内联 c # 代码。 请注意，代码位于元素内部， `x:Code` 并且代码必须使用 `<CDATA[` ... `]]>` 来转义 XML 的内容，以便 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器 (解释 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 架构或 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 架构) 不会尝试将内容按原义解释为 xml。  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>
## <a name="inline-code-limitations"></a>内联代码限制  
 应考虑避免或限制使用内联代码。 就体系结构和编码理念而言，维护标记和代码隐藏之间的分离使设计人员和开发人员角色更加独特。 在更多的技术级别上，你为内联代码编写的代码可能会很难编写，因为你始终会写入 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 生成的分部类，并且只能使用默认的 XML 命名空间映射。 由于不能添加 `using` 语句，因此必须完全限定你所做的多个 API 调用。 默认 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 映射包括程序集中存在的大多数但不是所有的 CLR 命名空间 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ; 必须完全限定对其他 CLR 命名空间中包含的类型和成员的调用。 你还不能在内联代码中定义除分部类之外的任何内容，并且引用的所有用户代码实体都必须作为生成的分部类中的成员或变量存在。 其他特定于语言的编程功能（如宏或 `#ifdef` 针对全局变量或生成变量）也不可用。 有关详细信息，请参阅 [X:Code 内部 XAML 类型](/dotnet/desktop-wpf/xaml-services/xcode-intrinsic-xaml-type)。  
  
## <a name="see-also"></a>请参阅

- [XAML 概述 (WPF)](/dotnet/desktop-wpf/fundamentals/xaml)
- [x:Code 内部 XAML 类型](/dotnet/desktop-wpf/xaml-services/xcode-intrinsic-xaml-type)
- [生成 WPF 应用程序](../app-development/building-a-wpf-application-wpf.md)
- [XAML 语法详述](xaml-syntax-in-detail.md)
