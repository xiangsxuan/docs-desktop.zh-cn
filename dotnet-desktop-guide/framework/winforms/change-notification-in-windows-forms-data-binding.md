---
title: 数据绑定中的更改通知
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, data binding
- Windows Forms, adding change notification for data binding
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
ms.openlocfilehash: 2dffea46bf0db54d28ef55e507767d88bd29ebc2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971343"
---
# <a name="change-notification-in-windows-forms-data-binding"></a>Windows 窗体数据绑定中的更改通知
Windows 窗体数据绑定的最重要的概念之一是 *更改通知*。 若要确保数据源和绑定控件始终具有最新的数据，必须为数据绑定添加更改通知。 具体来说，您需要确保绑定控件收到对其数据源所做的更改的通知，并通知数据源对控件的绑定属性所做的更改。  
  
 有不同类型的更改通知，具体取决于数据绑定的种类：  
  
- 简单绑定，其中单个控件属性绑定到对象的单个实例。  
  
- 基于列表的绑定，它可以包含绑定到列表中某一项的属性或绑定到对象列表的控件属性的单个控件属性。  
  
 此外，如果您要创建要用于数据绑定的 Windows 窗体控件，则必须将 *PropertyName* changed 模式应用于控件，以便将对控件的绑定属性所做的更改传播到数据源。  
  
## <a name="change-notification-for-simple-binding"></a>简单绑定的更改通知  
 对于简单绑定，当绑定属性的值发生更改时，业务对象必须提供更改通知。 为此，可以为业务对象的每个属性公开属性 *名称* changed 事件，并将业务对象绑定到控件， <xref:System.Windows.Forms.BindingSource> 或者使用你的业务对象实现接口的首选方法 <xref:System.ComponentModel.INotifyPropertyChanged> ，并在 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 属性的值更改时引发事件。 有关详细信息，请参阅 [如何：实现 INotifyPropertyChanged 接口](how-to-implement-the-inotifypropertychanged-interface.md)。 使用实现接口的对象时 <xref:System.ComponentModel.INotifyPropertyChanged> ，无需使用将 <xref:System.Windows.Forms.BindingSource> 对象绑定到控件，但 <xref:System.Windows.Forms.BindingSource> 建议使用。  
  
## <a name="change-notification-for-list-based-binding"></a>List-Based 绑定的更改通知  
 Windows 窗体依赖于绑定列表来提供属性更改 (列表项属性值更改) 和列表更改 (项被删除或添加到列表) 绑定控件。 因此，用于数据绑定的列表必须实现 <xref:System.ComponentModel.IBindingList> ，这将提供两种类型的更改通知。 <xref:System.ComponentModel.BindingList%601>是的泛型实现 <xref:System.ComponentModel.IBindingList> ，设计用于 Windows 窗体数据绑定。 你可以创建一个 <xref:System.ComponentModel.BindingList%601> ，它包含实现的业务对象类型， <xref:System.ComponentModel.INotifyPropertyChanged> 并且该列表会将事件自动转换 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 为 <xref:System.ComponentModel.IBindingList.ListChanged> 事件。 如果绑定列表不是 <xref:System.ComponentModel.IBindingList> ，则必须使用组件将对象列表绑定到 Windows 窗体控件 <xref:System.Windows.Forms.BindingSource> 。 该 <xref:System.Windows.Forms.BindingSource> 组件将提供与的属性到列表的转换 <xref:System.ComponentModel.BindingList%601> 。 有关详细信息，请参阅 [如何：使用 BindingSource 和 INotifyPropertyChanged 接口引发更改通知](./controls/raise-change-notifications--bindingsource.md)。  
  
## <a name="change-notification-for-custom-controls"></a>自定义控件的更改通知  
 最后，从控件端，您必须为每个设计为绑定到数据的属性公开一个 *PropertyName* changed 事件。 然后，对控件属性所做的更改将传播到绑定数据源。 有关详细信息，请参阅 [如何：应用 PropertyNameChanged 模式](how-to-apply-the-propertynamechanged-pattern.md)  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.ComponentModel.INotifyPropertyChanged>
- <xref:System.ComponentModel.BindingList%601>
- [Windows 窗体数据绑定](windows-forms-data-binding.md)
- [Windows 窗体支持的数据源](data-sources-supported-by-windows-forms.md)
- [数据绑定和 Windows 窗体](data-binding-and-windows-forms.md)
