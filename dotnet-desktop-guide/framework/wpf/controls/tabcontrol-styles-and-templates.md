---
title: TabControl 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TabControl
- TabControl [WPF], styles and templates [WPF]
- parts [WPF], TabControl
- styles [WPF], TabControl
- states [WPF], TabControl
- templates [WPF], TabControl
ms.assetid: f6b19a30-f10e-4fa1-96ce-f17a54092ab6
ms.openlocfilehash: 254a68e2bc130446e0c3c7273f2cd750aad3c9c2
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970452"
---
# <a name="tabcontrol-styles-and-templates"></a>TabControl 样式和模板
本主题描述控件的样式和模板 <xref:System.Windows.Controls.TabControl> 。 您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。 有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。  
  
## <a name="tabcontrol-parts"></a>TabControl 部件  
 下表列出了控件的已命名部件 <xref:System.Windows.Controls.TabControl> 。  
  
|组成部分|类型|说明|  
|-|-|-|  
|PART_SelectedContentHost|<xref:System.Windows.Controls.ContentPresenter>|显示当前所选内容的对象 <xref:System.Windows.Controls.TabItem> 。|  
  
 为创建时 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.TabControl> ，模板可能包含 <xref:System.Windows.Controls.ItemsPresenter> 内的 <xref:System.Windows.Controls.ScrollViewer> 。  (<xref:System.Windows.Controls.ItemsPresenter> 显示中的每一项，则在 <xref:System.Windows.Controls.TabControl> <xref:System.Windows.Controls.ScrollViewer> 控件内启用滚动) 。  如果不 <xref:System.Windows.Controls.ItemsPresenter> 是的直接子级 <xref:System.Windows.Controls.ScrollViewer> ，则必须指定 <xref:System.Windows.Controls.ItemsPresenter> 名称 `ItemsPresenter` 。  
  
## <a name="tabcontrol-states"></a>TabControl 状态  
 下表列出了控件的可视状态 <xref:System.Windows.Controls.TabControl> 。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|----------------------|---------------------------|-----------------|  
|普通|CommonStates|默认状态。|  
|已禁用|CommonStates|已禁用控件。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。|  
  
## <a name="tabitem-parts"></a>TabItem 部件  
 <xref:System.Windows.Controls.TabItem>控件没有任何命名部分。  
  
## <a name="tabitem-states"></a>TabItem 状态  
 下表列出了控件的可视状态 <xref:System.Windows.Controls.TabItem> 。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|----------------------|---------------------------|-----------------|  
|普通|CommonStates|默认状态。|  
|MouseOver|CommonStates|鼠标指针悬停在控件上方。|  
|已禁用|CommonStates|已禁用控件。|  
|已设定焦点|FocusStates|控件有焦点。|  
|失去焦点|FocusStates|控件没有焦点。|  
|选定|SelectionStates|已选择控件。|  
|未选定|SelectionStates|未选择控件。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。|  
  
## <a name="tabcontrol-controltemplate-example"></a>TabControl System.windows.controls.controltemplate> 示例  
 下面的示例演示如何为 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.TabControl> 和 <xref:System.Windows.Controls.TabItem> 控件定义。  
  
 [!code-xaml[ControlTemplateExamples#TabControl](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tabcontrol.xaml#tabcontrol)]  
  
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
