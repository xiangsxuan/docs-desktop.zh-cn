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
# <a name="how-to-specify-the-direction-of-the-binding"></a>如何：指定绑定的方向

本示例演示如何指定绑定是仅更新绑定目标（目标）属性或绑定源（源）属性，还是同时更新目标属性和源属性。  
  
## <a name="example"></a>示例  
 使用 <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> 属性可以指定绑定的方向。 下面是绑定更新的可用选项：  
  
- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> 每当目标属性或源属性更改时，更新目标属性或属性。  
  
- <xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> 仅当源属性更改时才更新目标属性。  
  
- <xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> 仅当应用程序启动或发生更改时才更新目标属性 <xref:System.Windows.FrameworkElement.DataContext%2A> 。  
  
- <xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> 在目标属性更改时更新源属性。  
  
- <xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> 导致 <xref:System.Windows.Data.Binding.Mode%2A> 使用目标属性的默认值。  
  
 有关详细信息，请参见 <xref:System.Windows.Data.BindingMode> 枚举。  
  
 下面的示例演示如何设置 <xref:System.Windows.Data.Binding.Mode%2A> 属性。  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 若要检测源更改（适用于 <xref:System.Windows.Data.BindingMode.OneWay> 和 <xref:System.Windows.Data.BindingMode.TwoWay> 绑定），则源必须实现合适的属性更改通知机制，例如 <xref:System.ComponentModel.INotifyPropertyChanged>。 有关实现的示例，请参阅 [实现属性更改通知](how-to-implement-property-change-notification.md) <xref:System.ComponentModel.INotifyPropertyChanged> 。  
  
 对于 <xref:System.Windows.Data.BindingMode.TwoWay> 或 <xref:System.Windows.Data.BindingMode.OneWayToSource> 绑定，可以通过设置属性来控制源更新的时间 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 。 有关详细信息，请参阅<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Data.Binding>
- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [操作指南主题](data-binding-how-to-topics.md)
