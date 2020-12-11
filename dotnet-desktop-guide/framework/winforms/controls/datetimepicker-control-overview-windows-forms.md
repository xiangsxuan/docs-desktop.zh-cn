---
title: DateTimePicker 控件概述
ms.date: 03/30/2017
f1_keywords:
- DateTimePicker
helpviewer_keywords:
- DateTimePicker control [Windows Forms], about
- date and time picker controls
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
ms.openlocfilehash: 63271dd91116c1f68d426f3ed5aa710644ded928
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970113"
---
# <a name="datetimepicker-control-overview-windows-forms"></a>DateTimePicker 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.DateTimePicker> 控件允许用户从日期或时间列表中选择单个项。 用于表示日期时，它显示在两个部分：一个下拉列表，其中包含以文本表示的日期，当您单击列表旁边的向下箭头时，将显示网格。 网格看起来像 <xref:System.Windows.Forms.MonthCalendar> 控件，可用于选择多个日期。 有关控件的详细信息 <xref:System.Windows.Forms.MonthCalendar> ，请参阅 [MonthCalendar 控件概述](monthcalendar-control-overview-windows-forms.md)。  
  
## <a name="key-properties"></a>键属性  
 如果希望将 <xref:System.Windows.Forms.DateTimePicker> 显示为用于选取或编辑时间的控件而不是日期，请将 <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> 属性设置为 `true` ，并将 <xref:System.Windows.Forms.DateTimePicker.Format%2A> 属性设置为 <xref:System.Windows.Forms.DateTimePickerFormat.Time> 。 有关详细信息，请参阅 [如何：在 DateTimePicker 控件中显示时间](how-to-display-time-with-the-datetimepicker-control.md)。  
  
 当 <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> 属性设置为时，将在 `true` 控件中的所选日期旁显示复选框。 选中此复选框后，可以更新所选的日期时间值。 如果复选框为空，则该值显示为 "不可用"。  
  
 控件的 <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> 和 <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> 属性确定日期和时间范围。 <xref:System.Windows.Forms.DateTimePicker.Value%2A>属性包含控件设置为的当前日期和时间。 有关详细信息，请参阅 [如何：用 Windows 窗体 DateTimePicker 控件设置和返回日期](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)。 这些值可以使用四种格式显示，由 <xref:System.Windows.Forms.DateTimePicker.Format%2A> 属性设置： <xref:System.Windows.Forms.DateTimePickerFormat.Long> 、 <xref:System.Windows.Forms.DateTimePickerFormat.Short> 、 <xref:System.Windows.Forms.DateTimePickerFormat.Time> 或 <xref:System.Windows.Forms.DateTimePickerFormat.Custom> 。 如果选择了自定义格式，则必须将 <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> 属性设置为相应的字符串。 有关详细信息，请参阅 [如何：使用 Windows 窗体 DateTimePicker 控件以自定义格式显示日期](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)。  
  
## <a name="see-also"></a>另请参阅

- [如何：使用 Windows 窗体 DateTimePicker 控件以自定义格式显示日期](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
- [如何：使用 Windows 窗体 DateTimePicker 控件设置和返回日期](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
