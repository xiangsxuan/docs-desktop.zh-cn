---
title: 使用 BindingNavigator 控件浏览数据集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- datasets [Windows Forms], moving through
- BindingNavigator control [Windows Forms], moving through datasets
- examples [Windows Forms], BindingNavigator control
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
ms.openlocfilehash: 8f023521ab78f6a0bf44b2c6afcbf618eb745ad9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972606"
---
# <a name="how-to-move-through-a-dataset-with-the-windows-forms-bindingnavigator-control"></a>如何：使用 Windows 窗体 BindingNavigator 控件浏览数据集

生成数据驱动的应用程序时，经常需要向用户显示数据集合。 <xref:System.Windows.Forms.BindingNavigator> 控件与 <xref:System.Windows.Forms.BindingSource> 组件一起为滚动集合并按顺序显示其中的项提供方便的可扩展解决方案。  
  
## <a name="example"></a>示例  

 下面的代码示例演示如何使用 <xref:System.Windows.Forms.BindingNavigator> 控件来浏览数据。 集合包含在 <xref:System.Data.DataView> 中，后者使用 <xref:System.Windows.Forms.BindingSource> 组件绑定到 <xref:System.Windows.Forms.TextBox> 控件。  
  
> [!NOTE]
> 将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。 若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。 有关详细信息，请参阅 [保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)。  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  

 此示例需要：  
  
- 对 System、System.Data、System.Drawing、System.Windows.Forms 和 System.Xml 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [BindingNavigator 控件](bindingnavigator-control-windows-forms.md)
- [BindingSource 组件](bindingsource-component.md)
- [如何：将 Windows 窗体控件绑定到类型](how-to-bind-a-windows-forms-control-to-a-type.md)
