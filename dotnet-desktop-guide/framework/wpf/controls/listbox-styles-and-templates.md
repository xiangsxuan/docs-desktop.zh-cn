---
title: ListBox 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ListBox
- templates [WPF], ListBox
- states [WPF], ListBox
- ControlTemplate [WPF], ListBox
- parts [WPF], ListBox
- ListBox [WPF], styles and templates
ms.assetid: fc5764cb-c27b-495b-88d4-d969a8213ccb
ms.openlocfilehash: d97977de37924219f5b492a8659f2d55676ec2c4
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970592"
---
# <a name="listbox-styles-and-templates"></a>ListBox 样式和模板
本主题描述控件的样式和模板 <xref:System.Windows.Controls.ListBox> 。 您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。 有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。  
  
## <a name="listbox-parts"></a>ListBox 部件  
 <xref:System.Windows.Controls.ListBox>控件没有任何命名部分。  
  
 为创建时 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.ListBox> ，模板可能包含 <xref:System.Windows.Controls.ItemsPresenter> 内的 <xref:System.Windows.Controls.ScrollViewer> 。  (<xref:System.Windows.Controls.ItemsPresenter> 显示中的每一项，则在 <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.ScrollViewer> 控件内启用滚动) 。  如果不 <xref:System.Windows.Controls.ItemsPresenter> 是的直接子级 <xref:System.Windows.Controls.ScrollViewer> ，则必须指定 <xref:System.Windows.Controls.ItemsPresenter> 名称 `ItemsPresenter` 。  
  
## <a name="listbox-states"></a>ListBox 状态  
 下表列出了控件的可视状态 <xref:System.Windows.Controls.ListBox> 。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|有效|ValidationStates|控件有效。|  
|InvalidFocused|ValidationStates|控件无效，但具有焦点。|  
|InvalidUnfocused|ValidationStates|控件无效，并且没有焦点。|  
  
## <a name="listboxitem-parts"></a>ListBoxItem 部件  
 <xref:System.Windows.Controls.ListBoxItem>控件没有任何命名部分。  
  
## <a name="listboxitem-states"></a>ListBoxItem 状态  
 下表列出了控件的可视状态 <xref:System.Windows.Controls.ListBox> 。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|普通|CommonStates|默认状态。|  
|MouseOver|CommonStates|鼠标指针悬停在控件上方。|  
|已禁用|CommonStates|该项已禁用。|  
|已设定焦点|FocusStates|该项有焦点。|  
|失去焦点|FocusStates|该项没有焦点。|  
|未选定|SelectionStates|未选定该项。|  
|选定|SelectionStates|该项当前已选定。|  
|SelectedUnfocused|SelectionStates|该项已选定，但没有焦点。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。|  
  
## <a name="listbox-controltemplate-example"></a>ListBox ControlTemplate 示例  
 下面的示例演示如何为 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.ListBox> 和 <xref:System.Windows.Controls.ListBoxItem> 控件定义。  
  
 [!code-xaml[ControlTemplateExamples#ListBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listbox.xaml#listbox)]  
  
 上一示例使用了一个或多个以下资源。  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Control 样式和模板](control-styles-and-templates.md)
- [控件自定义](control-customization.md)
- [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [创建控件模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
