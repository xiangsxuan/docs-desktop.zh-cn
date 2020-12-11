---
title: 在控件中应用特性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: f12b430d787b4b974e12902b2c17d3a35a09e468
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971262"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>如何：应用 Windows 窗体控件中的特性

若要开发正确与设计环境进行交互并在运行时正确执行的组件和控件，需要正确地将特性应用于类和成员。  
  
## <a name="example"></a>示例  

 下面的代码示例演示如何在自定义控件上使用多个特性。 控件说明了简单的日志记录功能。 当控件绑定到数据源时，它将在控件中显示数据源发送的值 <xref:System.Windows.Forms.DataGridView> 。 如果某个值超出了由属性指定的值 `Threshold` ， `ThresholdExceeded` 则会引发事件。  
  
 `AttributesDemoControl`使用类记录值 `LogEntry` 。 `LogEntry`类是一个模板类，这意味着它将在它所记录的类型中进行参数化。 例如，如果 `AttributesDemoControl` 是日志记录值类型 `float` ， `LogEntry` 则按如下方式声明并使用每个实例。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> 由于 `LogEntry` 是由任意类型参数化的，因此它必须使用反射来对参数类型进行操作。 要使阈值功能正常工作，参数类型 `T` 必须实现 <xref:System.IComparable> 接口。  
  
 托管查询性能计数器的窗体会 `AttributesDemoControl` 定期执行。 每个值都打包为 `LogEntry` 适当类型的，并添加到窗体的中 <xref:System.Windows.Forms.BindingSource> 。 `AttributesDemoControl`通过数据绑定接收值并在控件中显示值 <xref:System.Windows.Forms.DataGridView> 。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 第一个代码示例是 `AttributesDemoControl` 实现。 第二个代码示例演示使用的窗体 `AttributesDemoControl` 。  
  
## <a name="class-level-attributes"></a>类级属性  

 某些属性应用于类级别。 下面的代码示例演示通常应用于 Windows 窗体控件的特性。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>TypeConverter 特性  

 <xref:System.ComponentModel.TypeConverterAttribute> 是另一种常用的类级属性。 下面的代码示例演示如何使用 `LogEntry` 类。 此示例还演示类型的的实现 <xref:System.ComponentModel.TypeConverter> ，该 `LogEntry` 类型名为 `LogEntryTypeConverter` 。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>成员级特性  

 某些属性应用于成员级别。 下面的代码示例演示一些通常应用于 Windows 窗体控件的属性的属性。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>AmbientValue 特性  

 下面的示例演示 <xref:System.ComponentModel.AmbientValueAttribute> 并显示支持与设计环境交互的代码。 这种交互称为 " *环境*"。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>数据绑定属性  

 下面的示例演示如何实现复杂数据绑定。 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>前面所示的类级别指定了用于 `DataSource` 数据绑定的和 `DataMember` 属性。 <xref:System.ComponentModel.AttributeProviderAttribute>指定属性将绑定到的类型 `DataSource` 。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>编译代码  
  
- 承载的窗体 `AttributesDemoControl` 需要引用 `AttributesDemoControl` 程序集才能生成。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [使用 .NET Framework 开发自定义 Windows 窗体控件](developing-custom-windows-forms-controls.md)
- [Windows 窗体控件中的特性](attributes-in-windows-forms-controls.md)
- [如何：使用 DesignerSerializationVisibilityAttribute 序列化标准类型的集合](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
