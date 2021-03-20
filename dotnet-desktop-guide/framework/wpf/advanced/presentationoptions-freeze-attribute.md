---
title: PresentationOptions:Freeze 特性
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: d4cd4b727338fdb3e6c6e4872c25b323aebe144e
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667143"
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="16a2a-102">PresentationOptions:Freeze 特性</span><span class="sxs-lookup"><span data-stu-id="16a2a-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="16a2a-103">将 <xref:System.Windows.Freezable.IsFrozen%2A> 包含元素的状态设置为 `true` <xref:System.Windows.Freezable> 。</span><span class="sxs-lookup"><span data-stu-id="16a2a-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="16a2a-104">如果未指定属性，则的默认行为是 <xref:System.Windows.Freezable> `PresentationOptions:Freeze` <xref:System.Windows.Freezable.IsFrozen%2A> `false` 在加载时，并且依赖于 <xref:System.Windows.Freezable> 运行时的常规行为。</span><span class="sxs-lookup"><span data-stu-id="16a2a-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="16a2a-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="16a2a-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="16a2a-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="16a2a-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="16a2a-107">XML 命名空间前缀，可以是每个 XML 1.0 规范的任何有效的前缀字符串。</span><span class="sxs-lookup"><span data-stu-id="16a2a-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="16a2a-108">`PresentationOptions`在本文档中，前缀用于标识目的。</span><span class="sxs-lookup"><span data-stu-id="16a2a-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="16a2a-109">一个实例化的任何派生类的元素 <xref:System.Windows.Freezable> 。</span><span class="sxs-lookup"><span data-stu-id="16a2a-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16a2a-110">备注</span><span class="sxs-lookup"><span data-stu-id="16a2a-110">Remarks</span></span>  
 <span data-ttu-id="16a2a-111">`Freeze`特性是在 XML 命名空间中定义的唯一特性或其他编程元素 `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` 。</span><span class="sxs-lookup"><span data-stu-id="16a2a-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="16a2a-112">`Freeze`此特殊命名空间中存在属性，因此可将其指定为可忽略，并使用[mc：可忽略属性](mc-ignorable-attribute.md)作为根元素声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="16a2a-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="16a2a-113">`Freeze`必须能够被忽略的原因是，并非所有 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器实现都能够 <xref:System.Windows.Freezable> 在加载时冻结; 此功能不是规范的组成部分 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="16a2a-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="16a2a-114">处理属性的功能 `Freeze` 专门内置于 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 已编译应用程序的处理器。</span><span class="sxs-lookup"><span data-stu-id="16a2a-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="16a2a-115">任何类都不支持该特性，且特性语法不可扩展或可修改。</span><span class="sxs-lookup"><span data-stu-id="16a2a-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="16a2a-116">如果要实现自己的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器，可以选择在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 加载时并行处理元素上的属性时，并行处理处理器的冻结行为 `Freeze` <xref:System.Windows.Freezable> 。</span><span class="sxs-lookup"><span data-stu-id="16a2a-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="16a2a-117">`Freeze`除 `true` (不区分大小写) 以外的其他属性值会生成加载时错误。</span><span class="sxs-lookup"><span data-stu-id="16a2a-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="16a2a-118"> (将 `Freeze` 属性指定为 `false` 不是错误，但已是默认值，则将设置为 `false` 不会) 。</span><span class="sxs-lookup"><span data-stu-id="16a2a-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16a2a-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="16a2a-119">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="16a2a-120">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="16a2a-120">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="16a2a-121">mc:Ignorable 特性</span><span class="sxs-lookup"><span data-stu-id="16a2a-121">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
