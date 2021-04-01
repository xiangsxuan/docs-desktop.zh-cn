---
title: 日历
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Calendar
- Calendar control [WPF]
ms.assetid: ee844e4a-eefe-48e2-bd0d-1d82cc5e960b
ms.openlocfilehash: c06cd34739dd25f717a5ea2cbc9803453558a400
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973264"
---
# <a name="calendar"></a>日历
使用日历，用户可以使用可视日历显示来选择日期。  
  
 <xref:System.Windows.Controls.Calendar>控件可以单独使用，也可以作为控件的下拉部分使用 <xref:System.Windows.Controls.DatePicker> 。 有关详细信息，请参阅 <xref:System.Windows.Controls.DatePicker>。  
  
 下图显示了两个 <xref:System.Windows.Controls.Calendar> 控件，一个具有选择和中断日期，另一个不包含。  
  
 ![日历控件](./media/ndp-calendarcontrols.png "NDP_CalendarControls")  
日历控件  
  
 下表提供了有关通常与相关联的任务的信息 <xref:System.Windows.Controls.Calendar> 。  
  
|任务|实现|  
|----------|--------------------|  
|指定不能选择的日期。|使用 <xref:System.Windows.Controls.Calendar.BlackoutDates%2A> 属性。|  
|使 <xref:System.Windows.Controls.Calendar> 显示月份、整年或十年。|将 <xref:System.Windows.Controls.Calendar.DisplayMode%2A> 属性设置为月份、年份或十年。|  
|指定用户是否可以选择日期、日期范围或多个日期范围。|使用 <xref:System.Windows.Controls.Calendar.SelectionMode%2A>。|  
|指定显示的日期范围 <xref:System.Windows.Controls.Calendar> 。|使用 <xref:System.Windows.Controls.Calendar.DisplayDateStart%2A> 和 <xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A> 属性。|  
|指定是否突出显示当前日期。|使用 <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> 属性。 默认情况下， <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> 为 `true` 。|  
|更改的大小 <xref:System.Windows.Controls.Calendar> 。|使用 <xref:System.Windows.Controls.Viewbox> 或将属性设置 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 为 <xref:System.Windows.Media.ScaleTransform> 。 请注意，如果您设置的 <xref:System.Windows.FrameworkElement.Width%2A> 和 <xref:System.Windows.FrameworkElement.Height%2A> 属性 <xref:System.Windows.Controls.Calendar> ，则实际日历不会更改其大小。|  
  
 <xref:System.Windows.Controls.Calendar>控件使用鼠标或键盘提供基本导航。 下表总结了键盘导航。  
  
|键组合|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>|操作|  
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|------------|  
|箭头|<xref:System.Windows.Controls.CalendarMode.Month>|<xref:System.Windows.Controls.Calendar.SelectedDate%2A>如果 <xref:System.Windows.Controls.Calendar.SelectionMode%2A> 属性未设置为，则更改属性 <xref:System.Windows.Controls.CalendarSelectionMode.None> 。|  
|箭头|<xref:System.Windows.Controls.CalendarMode.Year>|更改属性的月份 <xref:System.Windows.Controls.Calendar.DisplayDate%2A> 。 请注意，不 <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 会更改。|  
|箭头|<xref:System.Windows.Controls.CalendarMode.Decade>|更改的年份 <xref:System.Windows.Controls.Calendar.DisplayDate%2A> 。 请注意，不 <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 会更改。|  
|SHIFT + 箭头|<xref:System.Windows.Controls.CalendarMode.Month>|如果 <xref:System.Windows.Controls.Calendar.SelectionMode%2A> 未设置为 <xref:System.Windows.Controls.CalendarSelectionMode.SingleDate> 或 <xref:System.Windows.Controls.CalendarSelectionMode.None> ，则扩展选定日期的范围。|  
|Home|<xref:System.Windows.Controls.CalendarMode.Month>|将更改 <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 为当月的第一天。|  
|Home|<xref:System.Windows.Controls.CalendarMode.Year>|将的月份更改为一年中的 <xref:System.Windows.Controls.Calendar.DisplayDate%2A> 第一个月。 不 <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 会更改。|  
|Home|<xref:System.Windows.Controls.CalendarMode.Decade>|将的年更改 <xref:System.Windows.Controls.Calendar.DisplayDate%2A> 为十年的第一年。 不 <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 会更改。|  
|End|<xref:System.Windows.Controls.CalendarMode.Month>|将更改 <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 为当前月份的最后一天。|  
|End|<xref:System.Windows.Controls.CalendarMode.Year>|将中的月更改 <xref:System.Windows.Controls.Calendar.DisplayDate%2A> 为一年中的最后一个月。 不 <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 会更改。|  
|End|<xref:System.Windows.Controls.CalendarMode.Decade>|将的年更改 <xref:System.Windows.Controls.Calendar.DisplayDate%2A> 为十年的最后一年。 不 <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 会更改。|  
|CTRL + 向上箭头|任意|切换到下一个更大的 <xref:System.Windows.Controls.Calendar.DisplayMode%2A> 。 如果 <xref:System.Windows.Controls.Calendar.DisplayMode%2A> 已存在 <xref:System.Windows.Controls.CalendarMode.Decade> ，则不执行任何操作。|  
|CTRL + 向下箭头|任意|切换到下一个较小的 <xref:System.Windows.Controls.Calendar.DisplayMode%2A> 。 如果 <xref:System.Windows.Controls.Calendar.DisplayMode%2A> 已存在 <xref:System.Windows.Controls.CalendarMode.Month> ，则不执行任何操作。|  
|空格键或 ENTER|<xref:System.Windows.Controls.CalendarMode.Year> 或 <xref:System.Windows.Controls.CalendarMode.Decade>|切换 <xref:System.Windows.Controls.Calendar.DisplayMode%2A> 到 <xref:System.Windows.Controls.CalendarMode.Month> 或 <xref:System.Windows.Controls.CalendarMode.Year> 由重点项表示。|  
  
## <a name="see-also"></a>请参阅

- [控件](index.md)
- [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
