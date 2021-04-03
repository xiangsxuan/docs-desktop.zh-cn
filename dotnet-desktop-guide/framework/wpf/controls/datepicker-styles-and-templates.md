---
title: DatePicker 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], DatePicker
- DatePicker [WPF], styles and templates
- templates [WPF], DatePicker
- parts [WPF], DatePicker
- styles [WPF], DatePicker
- states [WPF], DatePicker
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
ms.openlocfilehash: c6663ae3f7f4eefc61c1a07d968ea300a485e157
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973377"
---
# <a name="datepicker-styles-and-templates"></a>DatePicker 样式和模板
本主题描述控件的样式和模板 <xref:System.Windows.Controls.DatePicker> 。 您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。 有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。  
  
## <a name="datepicker-parts"></a>DatePicker 部件  
 下表列出了控件的已命名部件 <xref:System.Windows.Controls.DatePicker> 。  
  
|组成部分|类型|说明|  
|-|-|-|  
|PART_Root|<xref:System.Windows.Controls.Grid>|控件的根。|  
|PART_Button|<xref:System.Windows.Controls.Button>|用于打开和关闭的按钮 <xref:System.Windows.Controls.Calendar> 。|  
|PART_TextBox|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|允许您输入日期的文本框。|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|控件的弹出窗口 <xref:System.Windows.Controls.DatePicker> 。|  
  
## <a name="datepicker-states"></a>DatePicker 状态  
 下表列出了控件的可视状态 <xref:System.Windows.Controls.DatePicker> 。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|普通|CommonStates|默认状态。|  
|已禁用|CommonStates|<xref:System.Windows.Controls.DatePicker>已禁用。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。|  
  
## <a name="datepickertextbox-parts"></a>DatePickerTextBox 部件  
 下表列出了控件的已命名部件 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 。  
  
|组成部分|类型|说明|  
|-|-|-|  
|PART_Watermark|<xref:System.Windows.Controls.ContentControl>|包含中的初始文本的元素 <xref:System.Windows.Controls.DatePicker> 。|  
|PART_ContentElement|<xref:System.Windows.FrameworkElement>|一个可包含的可视元素 <xref:System.Windows.FrameworkElement> 。 的文本 <xref:System.Windows.Controls.TextBox> 显示在此元素中。|  
  
## <a name="datepickertextbox-states"></a>DatePickerTextBox 状态  
 下表列出了控件的可视状态 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|普通|CommonStates|默认状态。|  
|已禁用|CommonStates|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>已禁用。|  
|MouseOver|CommonStates|鼠标指针置于上 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 。|  
|ReadOnly|CommonStates|用户不能更改中的文本 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 。|  
|已设定焦点|FocusStates|控件有焦点。|  
|失去焦点|FocusStates|控件没有焦点。|  
|打水印|WatermarkStates|控件显示其初始文本。  <xref:System.Windows.Controls.Primitives.DatePickerTextBox>当用户未输入文本或选择日期时，处于状态。|  
|Unwatermarked|WatermarkStates|用户已将文本输入到 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 中，或在中选择了一个日期 <xref:System.Windows.Controls.DatePicker> 。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性为 `true` ，并且控件具有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性为 `true` ，并且该控件没有焦点。|  
  
## <a name="datepicker-controltemplate-example"></a>DatePicker System.windows.controls.controltemplate> 示例  
 下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.DatePicker> 。  
  
 [!code-xaml[ControlTemplateExamples#DatePicker](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
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
