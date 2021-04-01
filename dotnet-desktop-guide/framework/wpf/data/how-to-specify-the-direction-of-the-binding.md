---
title: 如何：指定绑定的方向
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 6b3c6afde5e9fa1b778905b1a278bb295b6cbf11
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972087"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="d53d7-102">如何：指定绑定的方向</span><span class="sxs-lookup"><span data-stu-id="d53d7-102">How to: Specify the direction of the binding</span></span>

<span data-ttu-id="d53d7-103">本示例演示如何指定绑定是仅更新绑定目标（目标）属性或绑定源（源）属性，还是同时更新目标属性和源属性。</span><span class="sxs-lookup"><span data-stu-id="d53d7-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d53d7-104">示例</span><span class="sxs-lookup"><span data-stu-id="d53d7-104">Example</span></span>  
 <span data-ttu-id="d53d7-105">使用 <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> 属性可以指定绑定的方向。</span><span class="sxs-lookup"><span data-stu-id="d53d7-105">You use the <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> property to specify the direction of the binding.</span></span> <span data-ttu-id="d53d7-106">下面是绑定更新的可用选项：</span><span class="sxs-lookup"><span data-stu-id="d53d7-106">The following are the available options for binding updates:</span></span>  
  
- <span data-ttu-id="d53d7-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> 每当目标属性或源属性更改时，更新目标属性或属性。</span><span class="sxs-lookup"><span data-stu-id="d53d7-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
- <span data-ttu-id="d53d7-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> 仅当源属性更改时才更新目标属性。</span><span class="sxs-lookup"><span data-stu-id="d53d7-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> updates the target property only when the source property changes.</span></span>  
  
- <span data-ttu-id="d53d7-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> 仅当应用程序启动或发生更改时才更新目标属性 <xref:System.Windows.FrameworkElement.DataContext%2A> 。</span><span class="sxs-lookup"><span data-stu-id="d53d7-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
- <span data-ttu-id="d53d7-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> 在目标属性更改时更新源属性。</span><span class="sxs-lookup"><span data-stu-id="d53d7-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> updates the source property when the target property changes.</span></span>  
  
- <span data-ttu-id="d53d7-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> 导致 <xref:System.Windows.Data.Binding.Mode%2A> 使用目标属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="d53d7-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="d53d7-112">有关详细信息，请参见 <xref:System.Windows.Data.BindingMode> 枚举。</span><span class="sxs-lookup"><span data-stu-id="d53d7-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="d53d7-113">下面的示例演示如何设置 <xref:System.Windows.Data.Binding.Mode%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="d53d7-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="d53d7-114">若要检测源更改（适用于 <xref:System.Windows.Data.BindingMode.OneWay> 和 <xref:System.Windows.Data.BindingMode.TwoWay> 绑定），则源必须实现合适的属性更改通知机制，例如 <xref:System.ComponentModel.INotifyPropertyChanged>。</span><span class="sxs-lookup"><span data-stu-id="d53d7-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="d53d7-115">有关实现的示例，请参阅 [实现属性更改通知](how-to-implement-property-change-notification.md) <xref:System.ComponentModel.INotifyPropertyChanged> 。</span><span class="sxs-lookup"><span data-stu-id="d53d7-115">See [Implement Property Change Notification](how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="d53d7-116">对于 <xref:System.Windows.Data.BindingMode.TwoWay> 或 <xref:System.Windows.Data.BindingMode.OneWayToSource> 绑定，可以通过设置属性来控制源更新的时间 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 。</span><span class="sxs-lookup"><span data-stu-id="d53d7-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="d53d7-117">有关详细信息，请参阅<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>。</span><span class="sxs-lookup"><span data-stu-id="d53d7-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d53d7-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d53d7-118">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="d53d7-119">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="d53d7-119">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="d53d7-120">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="d53d7-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
