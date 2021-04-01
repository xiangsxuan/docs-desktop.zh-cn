---
title: ToggleButton 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: 2c5aee58878ea6199c07ee201882fd3ded97bdee
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972884"
---
# <a name="togglebutton-styles-and-templates"></a>ToggleButton 样式和模板

本主题描述控件的样式和模板 <xref:System.Windows.Controls.Primitives.ToggleButton> 。 您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。 有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。

## <a name="togglebutton-parts"></a>切换按钮部件

<xref:System.Windows.Controls.Primitives.ToggleButton>控件没有任何命名部分。

## <a name="togglebutton-states"></a>切换按钮状态

下表列出了控件的可视状态 <xref:System.Windows.Controls.Primitives.ToggleButton> 。

|VisualState 名称|VisualStateGroup 名称|描述|
|-|-|-|
|普通|CommonStates|默认状态。|
|MouseOver|CommonStates|鼠标指针悬停在控件上方。|
|已按下|CommonStates|已按下控件。|
|已禁用|CommonStates|已禁用控件。|
|已设定焦点|FocusStates|控件有焦点。|
|失去焦点|FocusStates|控件没有焦点。|
|已选中|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `true`。|
|未选中|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `false`。|
|尚|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> 为 `true` 且 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `null`。|
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。|
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性为 `true` ，并且控件具有焦点。|
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性为 `true` ，并且该控件没有焦点。|

> [!NOTE]
> 如果控件模板中不存在不确定的视觉对象状态，则将使用未选中的视觉对象状态作为默认视觉对象状态。

## <a name="togglebutton-controltemplate-example"></a>切换按钮 System.windows.controls.controltemplate> 示例

下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Primitives.ToggleButton> 。

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

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
