---
title: Calendar 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Calendar
- templates [WPF], Calendar
- states [WPF], Calendar
- parts [WPF], Calendar
- Calendar [WPF], styles and templates
- ControlTemplate [WPF], Calendar
ms.assetid: f4fcf046-7a8f-41b8-b5a8-534b64e0345c
ms.openlocfilehash: 3639a6f012aae7e15bae0e765e46f92015273286
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973267"
---
# <a name="calendar-styles-and-templates"></a>Calendar 样式和模板
本主题描述控件的样式和模板 <xref:System.Windows.Controls.Calendar> 。 您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。 有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。  
  
## <a name="calendar-parts"></a>日历部件  
 下表列出了控件的已命名部件 <xref:System.Windows.Controls.Calendar> 。  
  
|组成部分|类型|描述|  
|-|-|-|  
|PART_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|上当前显示的月份或年份 <xref:System.Windows.Controls.Calendar> 。|  
|PART_Root|<xref:System.Windows.Controls.Panel>|包含的面板 <xref:System.Windows.Controls.Primitives.CalendarItem> 。|  
  
## <a name="calendar-states"></a>日历状态  
 下表列出了控件的可视状态 <xref:System.Windows.Controls.Calendar> 。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|----------------------|---------------------------|-----------------|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。|  
  
## <a name="calendaritem-parts"></a>CalendarItem 部件  
 下表列出了控件的已命名部件 <xref:System.Windows.Controls.Primitives.CalendarItem> 。  
  
|组成部分|类型|描述|  
|-|-|-|  
|PART_Root|<xref:System.Windows.FrameworkElement>|控件的根。|  
|PART_PreviousButton|<xref:System.Windows.Controls.Button>|单击此按钮将显示日历的上一页。|  
|PART_NextButton|<xref:System.Windows.Controls.Button>|用于显示单击日历下一页的按钮。|  
|PART_HeaderButton|<xref:System.Windows.Controls.Button>|用于在月模式、年份模式和十年模式间切换的按钮。|  
|PART_MonthView|<xref:System.Windows.Controls.Grid>|按月模式托管内容。|  
|PART_YearView|<xref:System.Windows.Controls.Grid>|在年或十年模式下托管内容。|  
|PART_DisabledVisual|<xref:System.Windows.FrameworkElement>|处于禁用状态的覆盖区。|  
|DayTitleTemplate|<xref:System.Windows.DataTemplate>|<xref:System.Windows.DataTemplate>描述视觉对象结构的。|  
  
## <a name="calendaritem-states"></a>CalendarItem 状态  
 下表列出了控件的可视状态 <xref:System.Windows.Controls.Primitives.CalendarItem> 。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|正常状态|CommonStates|默认状态。|  
|已禁用状态|CommonStates|当属性为时，日历的状态 <xref:System.Windows.UIElement.IsEnabled%2A> `false` 。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。|  
  
## <a name="calendardaybutton-parts"></a>CalendarDayButton 部件  
 <xref:System.Windows.Controls.Primitives.CalendarDayButton>控件没有任何命名部分。  
  
## <a name="calendardaybutton-states"></a>CalendarDayButton 状态  
 下表列出了控件的可视状态 <xref:System.Windows.Controls.Primitives.CalendarDayButton> 。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|普通|CommonStates|默认状态。|  
|已禁用|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarDayButton>已禁用。|  
|MouseOver|CommonStates|鼠标指针置于上 <xref:System.Windows.Controls.Primitives.CalendarDayButton> 。|  
|已按下|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarDayButton>已按下。|  
|选定|SelectionStates|该按钮处于选中状态。|  
|未选定|SelectionStates|未选择该按钮。|  
|CalendarButtonFocused|CalendarButtonFocusStates|按钮有焦点。|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|按钮没有焦点。|  
|已设定焦点|FocusStates|按钮有焦点。|  
|失去焦点|FocusStates|按钮没有焦点。|  
|活动|ActiveStates|该按钮处于活动状态。|  
|非活动|ActiveStates|该按钮处于非活动状态。|  
|RegularDay|DayStates|此按钮不表示 <xref:System.DateTime.Today%2A?displayProperty=nameWithType> 。|  
|今天|DayStates|按钮表示 <xref:System.DateTime.Today%2A?displayProperty=nameWithType> 。|  
|NormalDay|BlackoutDayStates|按钮表示可选择的日期。|  
|BlackoutDay|BlackoutDayStates|此按钮表示不能选择的日期。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。|  
  
## <a name="calendarbutton-parts"></a>CalendarButton 部件  
 <xref:System.Windows.Controls.Primitives.CalendarButton>控件没有任何命名部分。  
  
## <a name="calendarbutton-states"></a>CalendarButton 状态  
 下表列出了控件的可视状态 <xref:System.Windows.Controls.Primitives.CalendarButton> 。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|普通|CommonStates|默认状态。|  
|已禁用|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarButton>已禁用。|  
|MouseOver|CommonStates|鼠标指针置于上 <xref:System.Windows.Controls.Primitives.CalendarButton> 。|  
|已按下|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarButton>已按下。|  
|选定|SelectionStates|该按钮处于选中状态。|  
|未选定|SelectionStates|未选择该按钮。|  
|CalendarButtonFocused|CalendarButtonFocusStates|按钮有焦点。|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|按钮没有焦点。|  
|已设定焦点|FocusStates|按钮有焦点。|  
|失去焦点|FocusStates|按钮没有焦点。|  
|活动|ActiveStates|该按钮处于活动状态。|  
|非活动|ActiveStates|该按钮处于非活动状态。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。|  
  
## <a name="calendar-controltemplate-example"></a>Calendar System.windows.controls.controltemplate> 示例  
 下面的示例演示如何为 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Calendar> 控件和关联的类型定义。  
  
 [!code-xaml[ControlTemplateExamples#Calendar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
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
