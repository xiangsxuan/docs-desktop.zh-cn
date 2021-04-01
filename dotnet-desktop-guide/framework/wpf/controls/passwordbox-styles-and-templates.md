---
title: PasswordBox 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
ms.openlocfilehash: aecd625a052f097aeb2b8cb73743fd4b47df89e1
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970465"
---
# <a name="passwordbox-styles-and-templates"></a>PasswordBox 样式和模板

本主题描述控件的样式和模板 <xref:System.Windows.Controls.PasswordBox> 。 您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。 有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。

## <a name="passwordbox-parts"></a>PasswordBox 部件

下表列出了控件的已命名部件 <xref:System.Windows.Controls.PasswordBox> 。

|组成部分|类型|描述|
|-|-|-|
|PART_ContentHost|<xref:System.Windows.FrameworkElement>|一个可包含的可视元素 <xref:System.Windows.FrameworkElement> 。 的文本 <xref:System.Windows.Controls.PasswordBox> 显示在此元素中。|

## <a name="passwordbox-states"></a>PasswordBox 状态

下表列出了控件的可视状态 <xref:System.Windows.Controls.PasswordBox> 。

|VisualState 名称|VisualStateGroup 名称|描述|
|-|-|-|
|普通|CommonStates|默认状态。|
|MouseOver|CommonStates|鼠标指针悬停在控件上方。|
|已禁用|CommonStates|已禁用控件。|
|已设定焦点|FocusStates|控件有焦点。|
|失去焦点|FocusStates|控件没有焦点。|
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。|
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。|
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。|

## <a name="passwordbox-controltemplate-example"></a>PasswordBox System.windows.controls.controltemplate> 示例

下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.PasswordBox> 。

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

上一示例使用了一个或多个以下资源。

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Control 样式和模板](control-styles-and-templates.md)
- [控件自定义](control-customization.md)
- [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [创建控件模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
