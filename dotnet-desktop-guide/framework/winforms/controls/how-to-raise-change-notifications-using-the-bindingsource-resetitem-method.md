---
title: 如何：使用 BindingSource ResetItem 方法引发更改通知
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- change notifications [Windows Forms], raising
- data binding [Windows Forms], change notifications
- BindingSource component [Windows Forms], raising change notifications with
- data sources [Windows Forms], detecting changes
- change notifications
ms.assetid: ab8b4096-37ff-4e30-aabc-de79a2f2e972
ms.openlocfilehash: 39beb5c7162fb01a51360330216687c158ff433c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971141"
---
# <a name="how-to-raise-change-notifications-using-the-bindingsource-resetitem-method"></a>如何：使用 BindingSource ResetItem 方法引发更改通知
当对项进行更改、添加或删除时，控件的一些数据源不会引发更改通知。 使用 <xref:System.Windows.Forms.BindingSource> 组件，可以绑定到此类数据源并从代码引发更改通知。  
  
## <a name="example"></a>示例  
 此窗体演示了使用 <xref:System.Windows.Forms.BindingSource> 组件将列表绑定到 <xref:System.Windows.Forms.DataGridView> 控件。 该列表不会引发更改通知，因此当更改列表中的项时，会调用 <xref:System.Windows.Forms.BindingSource> 上的 <xref:System.Windows.Forms.BindingSource.ResetItem%2A> 方法。 .  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [BindingSource 组件](bindingsource-component.md)
- [如何：将 Windows 窗体控件绑定到类型](how-to-bind-a-windows-forms-control-to-a-type.md)
