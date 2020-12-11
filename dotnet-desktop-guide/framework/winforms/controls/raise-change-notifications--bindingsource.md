---
title: 如何：使用 BindingSource 和 INotifyPropertyChanged 接口引发更改通知
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- change notifications [Windows Forms], raising
- BindingSource component [Windows Forms], and IPropertyChange
- data sources [Windows Forms], detecting changes
- examples [Windows Forms], BindingSource component
- change notifications
- INotifyPropertyChanged interface [Windows Forms], using with BindingSource
- BindingSource component [Windows Forms], examples
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
ms.openlocfilehash: cd8c3fba87fd5ab9acf9159fc1130ee28ed38497
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972868"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a>如何：使用 BindingSource 和 INotifyPropertyChanged 接口引发更改通知

<xref:System.Windows.Forms.BindingSource>当数据源中包含的类型实现时，该组件会自动检测数据源中的更改 <xref:System.ComponentModel.INotifyPropertyChanged> ，并在 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 属性值更改时引发事件。 此更改检测非常有用，因为在 <xref:System.Windows.Forms.BindingSource> 数据源值发生更改时，绑定到的控件会自动更新。  
  
> [!NOTE]
> 如果数据源实现 <xref:System.ComponentModel.INotifyPropertyChanged>，并且你正在执行异步操作，则不应更改后台线程上的数据源。 相反，应读取后台线程上的数据，并将数据合并到 UI 线程上的列表。  
  
## <a name="example"></a>示例  

 下面的代码示例演示了如何简单实现 <xref:System.ComponentModel.INotifyPropertyChanged> 接口。 它还演示了当将 <xref:System.Windows.Forms.BindingSource> 绑定到 <xref:System.ComponentModel.INotifyPropertyChanged> 类型的列表时，<xref:System.Windows.Forms.BindingSource> 如何将数据源更改自动传递到绑定控件。  
  
 如果使用 `CallerMemberName` 特性，则调用 `NotifyPropertyChanged` 方法不必将属性名称指定为字符串参数。 有关详细信息，请参阅 [) 的调用方信息 (c # ](/dotnet/csharp/language-reference/attributes/caller-information) 或 [调用方信息 (Visual Basic) ](/dotnet/visual-basic/programming-guide/concepts/caller-information)。  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  

 此示例需要：  
  
- 对系统、System.web、System.web 和 System.web 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.ComponentModel.INotifyPropertyChanged>
- [BindingSource 组件](bindingsource-component.md)
- [如何：使用 BindingSource ResetItem 方法引发更改通知](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
