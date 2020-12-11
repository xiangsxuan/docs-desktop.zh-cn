---
title: 用 MonthCalendar 控件以粗体显示特定日期
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], displaying dates in bold
- examples [Windows Forms], calendar controls
- GetDayBold event
- MonthCalendar control [Windows Forms], dates displayed in bold
ms.assetid: 8b20db5b-8118-4825-90e8-2c45c186ac7d
ms.openlocfilehash: 377eb76f562fff20aae2136ddb7130516d2d76f7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971552"
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a>如何：使用 Windows 窗体 MonthCalendar 控件以粗体显示特定日期
Windows 窗体 <xref:System.Windows.Forms.MonthCalendar> 控件可以将以粗体显示的日期显示为 "单数" 或 "重复"。 您可以这样做，以突出特殊日期，如假日和周末。  
  
 这三个属性控制此功能。 此 <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> 属性包含一个日期。 <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>属性包含每年以粗体显示的日期。 <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A>属性包含以粗体显示的日期。 其中每个属性都包含一个 <xref:System.DateTime> 对象数组。 若要在这些列表之一中添加或删除日期，必须添加或删除 <xref:System.DateTime> 对象。  
  
### <a name="to-make-a-date-appear-in-bold-type"></a>使日期显示为粗体  
  
1. 创建 <xref:System.DateTime> 对象。  
  
    ```vb  
    Dim myVacation1 As Date = New DateTime(2001, 6, 10)  
    Dim myVacation2 As Date = New DateTime(2001, 6, 17)  
    ```  
  
    ```csharp  
    DateTime myVacation1 = new DateTime(2001, 6, 10);  
    DateTime myVacation2 = new DateTime(2001, 6, 17);  
    ```  
  
    ```cpp  
    DateTime myVacation1 = DateTime(2001, 6, 10);  
    DateTime myVacation2 = DateTime(2001, 6, 17);  
    ```  
  
2. 通过调用 <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A> 控件的、或方法，使单个日期为粗体 <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A> <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> <xref:System.Windows.Forms.MonthCalendar> 。  
  
    ```vb  
    MonthCalendar1.AddBoldedDate(myVacation1)  
    MonthCalendar1.AddBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.AddBoldedDate(myVacation1);  
    monthCalendar1.AddBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->AddBoldedDate(myVacation1);  
    monthCalendar1->AddBoldedDate(myVacation2);  
    ```  
  
     –或者–  
  
     通过创建对象的数组 <xref:System.DateTime> 并将其分配给某个属性，使一组日期全部为粗体。  
  
    ```vb  
    Dim VacationDates As DateTime() = {myVacation1, myVacation2}  
    MonthCalendar1.BoldedDates = VacationDates  
    ```  
  
    ```csharp  
    DateTime[] VacationDates = {myVacation1, myVacation2};  
    monthCalendar1.BoldedDates = VacationDates;  
    ```  
  
    ```cpp  
    Array<DateTime>^ VacationDates = {myVacation1, myVacation2};  
    monthCalendar1->BoldedDates = VacationDates;  
    ```  
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a>使日期显示为常规字体  
  
1. 通过调用 <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A> 、或方法，使单个以粗体显示的日期显示为常规字体 <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A> <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> 。  
  
    ```vb  
    MonthCalendar1.RemoveBoldedDate(myVacation1)  
    MonthCalendar1.RemoveBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveBoldedDate(myVacation1);  
    monthCalendar1.RemoveBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveBoldedDate(myVacation1);  
    monthCalendar1->RemoveBoldedDate(myVacation2);  
    ```  
  
     –或者–  
  
     通过调用 <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A> 、或方法，从三个列表的一个列表中移除所有粗体日期 <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A> <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> 。  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2. 通过调用方法来更新字体的外观 <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> 。  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a>另请参阅

- [MonthCalendar 控件](monthcalendar-control-windows-forms.md)
- [如何：在 Windows 窗体 MonthCalendar 控件中选择日期范围](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [如何：更改 Windows 窗体 MonthCalendar 控件的外观](how-to-change-monthcalendar-control-appearance.md)
- [如何：在 Windows 窗体 MonthCalendar 控件中显示多个月份](display-more-than-one-month-wf-monthcalendar-control.md)
