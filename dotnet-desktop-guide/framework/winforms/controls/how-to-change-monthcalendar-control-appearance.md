---
title: 更改 MonthCalendar 控件的外观
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: ded9059ede4ad03f637c0e697b880c41a9a8ba32
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971890"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a>如何：更改 Windows 窗体 MonthCalendar 控件的外观
Windows 窗体 <xref:System.Windows.Forms.MonthCalendar> 控件允许您通过多种方式自定义日历的外观。 例如，可以设置配色方案，并选择显示或隐藏周数和当前日期。  
  
### <a name="to-change-the-month-calendars-color-scheme"></a>更改月历的配色方案  
  
- 设置属性，如 <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> 、 <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> 和 <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> 。 <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>属性还确定一周中各天的字体颜色。 <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>属性确定在显示月份之前和之后的日期的颜色。  
  
    ```vb  
    MonthCalendar1.TitleBackColor = System.Drawing.Color.Blue  
    MonthCalendar1.TrailingForeColor = System.Drawing.Color.Red  
    MonthCalendar1.TitleForeColor = System.Drawing.Color.Yellow  
    ```  
  
    ```csharp  
    monthCalendar1.TitleBackColor = System.Drawing.Color.Blue;  
    monthCalendar1.TrailingForeColor = System.Drawing.Color.Red;  
    monthCalendar1.TitleForeColor = System.Drawing.Color.Yellow;  
    ```  
  
    ```cpp  
    monthCalendar1->TitleBackColor = System::Drawing::Color::Blue;  
    monthCalendar1->TrailingForeColor = System::Drawing::Color::Red;  
    monthCalendar1->TitleForeColor = System::Drawing::Color::Yellow;  
    ```  
  
    > [!NOTE]
    > 从 Windows Vista 开始，根据主题，设置某些属性可能不会更改日历的外观。 例如，如果将 Windows 设置为使用 Aero 主题，则设置、、 <xref:System.Windows.Forms.MonthCalendar.BackColor%2A> <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> 或 <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> 属性不起作用。 这是因为，日历的更新版本呈现为在运行时从当前操作系统主题派生的外观。 如果要使用这些属性并启用日历的早期版本，则可以禁用应用程序的视觉样式。 禁用视觉样式可能会影响应用程序中其他控件的外观和行为。 若要禁用 Visual Basic 中的视觉样式，请打开项目设计器并取消选中 " **启用 XP 视觉样式** " 复选框。 若要在 c # 中禁用视觉样式，请打开 Program.cs 并注释掉 `Application.EnableVisualStyles();` 。 有关视觉样式的详细信息，请参阅 [启用视觉样式](/windows/desktop/controls/cookbook-overview)。  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a>显示控件底部的当前日期  
  
- 将 <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> 属性设置为 `true`。 下面的示例在双击窗体时在显示和省略今天的日期之间切换。  
  
    ```vb  
    Private Sub Form1_DoubleClick(ByVal sender As Object, _  
    ByVal e As System.EventArgs) Handles MyBase.DoubleClick  
       ' Toggle between True and False.  
       MonthCalendar1.ShowToday = Not MonthCalendar1.ShowToday  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_DoubleClick(object sender, System.EventArgs e)  
    {  
       // Toggle between True and False.  
       monthCalendar1.ShowToday = !monthCalendar1.ShowToday;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void Form1_DoubleClick(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // Toggle between True and False.  
          monthCalendar1->ShowToday = !monthCalendar1->ShowToday;  
       }  
    ```  
  
      (Visual c # 中，Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a>显示周数  
  
- 将 <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> 属性设置为 `true`。 可以在代码中或在属性窗口中设置此属性。  
  
     周数将显示在一周的第一天的左侧。  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a>另请参阅

- [MonthCalendar 控件](monthcalendar-control-windows-forms.md)
- [如何：在 Windows 窗体 MonthCalendar 控件中选择日期范围](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [如何：使用 Windows 窗体 MonthCalendar 控件以粗体显示特定日期](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [如何：在 Windows 窗体 MonthCalendar 控件中显示多个月份](display-more-than-one-month-wf-monthcalendar-control.md)
