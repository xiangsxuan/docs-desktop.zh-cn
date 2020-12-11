---
title: MonthCalendar 控件概述
ms.date: 03/30/2017
f1_keywords:
- MonthCalendar
helpviewer_keywords:
- calendars [Windows Forms], Windows Forms controls
- calendar controls [Windows Forms], Windows Forms
- MonthCalendar control [Windows Forms], setting the first day of the week
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
ms.openlocfilehash: a9b56164339d03b380a564b21855f6d94ec06af5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972607"
---
# <a name="monthcalendar-control-overview-windows-forms"></a>MonthCalendar 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.MonthCalendar> 控件提供了一个直观的图形界面，用户可在其中查看和设置日期信息。 该控件将显示一个日历：一个包含月份的编号日期的网格，按一周中的日期排列，并突出显示选定的日期范围。 可以通过单击月份标题两侧的箭头按钮来选择其他月份。 与类似的控件不同的是 <xref:System.Windows.Forms.DateTimePicker> ，您可以选择此控件的多个日期。 有关控件的详细信息 <xref:System.Windows.Forms.DateTimePicker> ，请参阅 [DateTimePicker 控件](datetimepicker-control-windows-forms.md)。  
  
## <a name="configuring-the-monthcalendar-control"></a>配置 MonthCalendar 控件  
 <xref:System.Windows.Forms.MonthCalendar>控件的外观是高度可配置的。 默认情况下，今天的日期显示为带圆圈，并在网格底部注明。 可以通过将 <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> 和 <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> 属性设置为来更改此功能 `false` 。 还可以通过将属性设置为，将周数添加到日历 <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> `true` 。 通过设置 <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> 属性，可以水平和垂直显示多个月份。 默认情况下，星期日显示为一周的第一天，但可以使用属性指定任何日期 <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A> 。  
  
 还可以通过将 <xref:System.DateTime> 对象添加到 <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> 、 <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> 和属性，将特定日期设置为以粗体显示的每年、每年或每月一次 <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> 。 有关详细信息，请参阅 [如何：用 Windows 窗体 MonthCalendar 控件以粗体显示特定日期](display-specific-days-in-bold-with-wf-monthcalendar-control.md)。  
  
 控件的键属性 <xref:System.Windows.Forms.MonthCalendar> 是 <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> 在控件中选择的日期范围。 <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>该值不能超过可以选择的最大天数，在属性中设置 <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A> 。 用户可选择的最早和最晚日期由 <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> 和属性确定 <xref:System.Windows.Forms.MonthCalendar.MinDate%2A> 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.MonthCalendar>
- [MonthCalendar 控件](monthcalendar-control-windows-forms.md)
