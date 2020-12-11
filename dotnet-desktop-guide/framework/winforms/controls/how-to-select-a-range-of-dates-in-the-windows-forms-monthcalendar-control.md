---
title: 在 MonthCalendar 控件中选择日期范围
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- dates [Windows Forms], selecting range in calendar controls
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], selecting date range
- MonthCalendar control [Windows Forms], selecting date range
ms.assetid: 95d9ab95-b0f8-4c19-9f63-b5cd4593a5d0
ms.openlocfilehash: bda96af21a8f86a54d5c0fe0204546b980076d26
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971133"
---
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a>如何：在 Windows 窗体 MonthCalendar 控件中选择日期范围
Windows 窗体控件的一项重要功能 <xref:System.Windows.Forms.MonthCalendar> 是用户可以选择日期范围。 此功能优于控件的日期选择功能 <xref:System.Windows.Forms.DateTimePicker> ，只允许用户选择单个日期/时间值。 您可以使用控件的属性来设置日期范围或获取由用户设置的选择范围 <xref:System.Windows.Forms.MonthCalendar> 。 下面的代码示例演示如何设置选择范围。  
  
### <a name="to-select-a-range-of-dates"></a>选择日期范围  
  
1. 创建 <xref:System.DateTime> 表示范围中第一个和最后一个日期的对象。  
  
    ```vb  
    Dim projectStart As Date = New DateTime(2001, 2, 13)  
    Dim projectEnd As Date = New DateTime(2001, 2, 28)  
    ```  
  
    ```csharp  
    DateTime projectStart = new DateTime(2001, 2, 13);  
    DateTime projectEnd = new DateTime(2001, 2, 28);  
    ```  
  
    ```cpp  
    DateTime projectStart = DateTime(2001, 2, 13);  
    DateTime projectEnd = DateTime(2001, 2, 28);  
    ```  
  
2. 设置 <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> 属性。  
  
    ```vb  
    MonthCalendar1.SelectionRange = New SelectionRange(projectStart, projectEnd)  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionRange = new SelectionRange(projectStart, projectEnd);  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionRange = gcnew  
       SelectionRange(projectStart, projectEnd);  
    ```  
  
     –或者–  
  
     设置 <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> 和 <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> 属性。  
  
    ```vb  
    MonthCalendar1.SelectionStart = projectStart  
    MonthCalendar1.SelectionEnd = projectEnd  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionStart = projectStart;  
    monthCalendar1.SelectionEnd = projectEnd;  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionStart = projectStart;  
    monthCalendar1->SelectionEnd = projectEnd;  
    ```  
  
## <a name="see-also"></a>另请参阅

- [MonthCalendar 控件](monthcalendar-control-windows-forms.md)
- [如何：更改 Windows 窗体 MonthCalendar 控件的外观](how-to-change-monthcalendar-control-appearance.md)
- [如何：使用 Windows 窗体 MonthCalendar 控件以粗体显示特定日期](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [如何：在 Windows 窗体 MonthCalendar 控件中显示多个月份](display-more-than-one-month-wf-monthcalendar-control.md)
