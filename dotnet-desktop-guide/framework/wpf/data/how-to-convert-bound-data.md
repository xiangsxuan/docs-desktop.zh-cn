---
title: 如何：转换绑定的数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
ms.openlocfilehash: 981994426afd173fa8560d3ee24c6cf24c0c24aa
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973087"
---
# <a name="how-to-convert-bound-data"></a>如何：转换绑定的数据
此示例演示如何将转换应用于绑定中使用的数据。  
  
 若要在绑定期间转换数据，您必须创建一个实现接口的类 <xref:System.Windows.Data.IValueConverter> ，其中包括 <xref:System.Windows.Data.IValueConverter.Convert%2A> 和 <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> 方法。  
  
## <a name="example"></a>示例  
 下面的示例演示如何实现日期转换器，该转换器转换传入的 date 值，以便只显示年份、月份和日期。 实现接口时 <xref:System.Windows.Data.IValueConverter> ，最好使用特性修饰实现，以便向 <xref:System.Windows.Data.ValueConversionAttribute> 开发工具指示转换中涉及的数据类型，如以下示例中所示：  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 创建转换器后，可以将其作为资源添加到 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 文件中。 在下面的示例中， *src* 映射到在其中定义了 *DateConverter* 的命名空间。  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 最后，可以使用以下语法在绑定中使用转换器。 在下面的示例中，的文本内容 <xref:System.Windows.Controls.TextBlock> 绑定到开始 *日期*，这是外部数据源的属性。  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 上述示例中引用的样式资源在资源部分中定义，而不会显示在本主题中。  
  
## <a name="see-also"></a>另请参阅

- [实现绑定验证](how-to-implement-binding-validation.md)
- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [操作指南主题](data-binding-how-to-topics.md)
