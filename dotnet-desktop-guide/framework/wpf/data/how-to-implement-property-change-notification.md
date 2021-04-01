---
title: 如何：实现属性更改通知
description: 启用属性，以便在 (WPF) Windows Presentation Foundation 中的属性值更改时自动通知绑定源。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
ms.openlocfilehash: f3cf3fe211e852fccaa605623820ebbde7e62917
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973599"
---
# <a name="how-to-implement-property-change-notification"></a>如何：实现属性更改通知
若要支持 <xref:System.Windows.Data.BindingMode.OneWay> 或 <xref:System.Windows.Data.BindingMode.TwoWay> 绑定以使绑定目标属性能够自动反映绑定源的动态更改 (例如，若要在用户编辑窗体时自动更新预览窗格) ，你的类需要提供适当的属性更改通知。 此示例演示如何创建实现的类 <xref:System.ComponentModel.INotifyPropertyChanged> 。  
  
## <a name="example"></a>示例  
 若要实现 <xref:System.ComponentModel.INotifyPropertyChanged> ，需要声明 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 事件并创建 `OnPropertyChanged` 方法。 然后，对于每个需要更改通知的属性，只要进行了更新，就可以调用 `OnPropertyChanged`。  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 若要查看如何 `Person` 使用类来支持绑定的示例 <xref:System.Windows.Data.BindingMode.TwoWay> ，请参阅 [控制文本框文本更新源的时间](how-to-control-when-the-textbox-text-updates-the-source.md)。  
  
## <a name="see-also"></a>请参阅

- [绑定源概述](binding-sources-overview.md)
- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [操作指南主题](data-binding-how-to-topics.md)
