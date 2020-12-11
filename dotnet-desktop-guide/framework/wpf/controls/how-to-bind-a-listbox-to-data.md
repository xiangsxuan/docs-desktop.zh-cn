---
title: 如何：将 ListBox 绑定到数据
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 4dea53a524247d18628b3e7e7b2c06906dced53d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973998"
---
# <a name="how-to-bind-a-listbox-to-data"></a>如何：将 ListBox 绑定到数据
应用程序开发人员可以创建 <xref:System.Windows.Controls.ListBox> 控件，而无需单独指定每个控件的内容 <xref:System.Windows.Controls.ListBoxItem> 。 您可以使用数据绑定将数据绑定到各个项。  
  
 下面的示例演示如何创建一个 <xref:System.Windows.Controls.ListBox> ，它 <xref:System.Windows.Controls.ListBoxItem> 通过数据绑定将元素填充到称为 *颜色* 的数据源。 在这种情况下，无需使用 <xref:System.Windows.Controls.ListBoxItem> 标记来指定每个项的内容。  
  
## <a name="example"></a>示例  
 [!code-xaml[ListBoxEvent#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.Controls.ListBoxItem>
- [控件](../advanced/optimizing-performance-controls.md)
