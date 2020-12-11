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
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a><span data-ttu-id="23ef1-102">如何：更改 Windows 窗体 MonthCalendar 控件的外观</span><span class="sxs-lookup"><span data-stu-id="23ef1-102">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>
<span data-ttu-id="23ef1-103">Windows 窗体 <xref:System.Windows.Forms.MonthCalendar> 控件允许您通过多种方式自定义日历的外观。</span><span class="sxs-lookup"><span data-stu-id="23ef1-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control allows you to customize the calendar's appearance in many ways.</span></span> <span data-ttu-id="23ef1-104">例如，可以设置配色方案，并选择显示或隐藏周数和当前日期。</span><span class="sxs-lookup"><span data-stu-id="23ef1-104">For example, you can set the color scheme and choose to display or hide week numbers and the current date.</span></span>  
  
### <a name="to-change-the-month-calendars-color-scheme"></a><span data-ttu-id="23ef1-105">更改月历的配色方案</span><span class="sxs-lookup"><span data-stu-id="23ef1-105">To change the month calendar's color scheme</span></span>  
  
- <span data-ttu-id="23ef1-106">设置属性，如 <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> 、 <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> 和 <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> 。</span><span class="sxs-lookup"><span data-stu-id="23ef1-106">Set properties such as <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> and <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span></span> <span data-ttu-id="23ef1-107"><xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>属性还确定一周中各天的字体颜色。</span><span class="sxs-lookup"><span data-stu-id="23ef1-107">The <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> property also determines the font color for the days of the week.</span></span> <span data-ttu-id="23ef1-108"><xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>属性确定在显示月份之前和之后的日期的颜色。</span><span class="sxs-lookup"><span data-stu-id="23ef1-108">The <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> property determines the color of the dates that precede and follow the displayed month or months.</span></span>  
  
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
    > <span data-ttu-id="23ef1-109">从 Windows Vista 开始，根据主题，设置某些属性可能不会更改日历的外观。</span><span class="sxs-lookup"><span data-stu-id="23ef1-109">Starting with Windows Vista and depending on the theme, setting some properties might not change the appearance of the calendar.</span></span> <span data-ttu-id="23ef1-110">例如，如果将 Windows 设置为使用 Aero 主题，则设置、、 <xref:System.Windows.Forms.MonthCalendar.BackColor%2A> <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> 或 <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> 属性不起作用。</span><span class="sxs-lookup"><span data-stu-id="23ef1-110">For example, if Windows is set to use the Aero theme, setting the <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, or <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> properties has no effect.</span></span> <span data-ttu-id="23ef1-111">这是因为，日历的更新版本呈现为在运行时从当前操作系统主题派生的外观。</span><span class="sxs-lookup"><span data-stu-id="23ef1-111">This is because an updated version of the calendar is rendered with an appearance that is derived at run time from the current operating system theme.</span></span> <span data-ttu-id="23ef1-112">如果要使用这些属性并启用日历的早期版本，则可以禁用应用程序的视觉样式。</span><span class="sxs-lookup"><span data-stu-id="23ef1-112">If you want to use these properties and enable the earlier version of the calendar, you can disable visual styles for your application.</span></span> <span data-ttu-id="23ef1-113">禁用视觉样式可能会影响应用程序中其他控件的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="23ef1-113">Disabling visual styles might affect the appearance and behavior of other controls in your application.</span></span> <span data-ttu-id="23ef1-114">若要禁用 Visual Basic 中的视觉样式，请打开项目设计器并取消选中 " **启用 XP 视觉样式** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="23ef1-114">To disable visual styles in Visual Basic, open the Project Designer and uncheck the **Enable XP visual styles** check box.</span></span> <span data-ttu-id="23ef1-115">若要在 c # 中禁用视觉样式，请打开 Program.cs 并注释掉 `Application.EnableVisualStyles();` 。</span><span class="sxs-lookup"><span data-stu-id="23ef1-115">To disable visual styles in C#, open Program.cs and comment out `Application.EnableVisualStyles();`.</span></span> <span data-ttu-id="23ef1-116">有关视觉样式的详细信息，请参阅 [启用视觉样式](/windows/desktop/controls/cookbook-overview)。</span><span class="sxs-lookup"><span data-stu-id="23ef1-116">For more information about visual styles, see [Enabling Visual Styles](/windows/desktop/controls/cookbook-overview).</span></span>  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a><span data-ttu-id="23ef1-117">显示控件底部的当前日期</span><span class="sxs-lookup"><span data-stu-id="23ef1-117">To display the current date at the bottom of the control</span></span>  
  
- <span data-ttu-id="23ef1-118">将 <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="23ef1-118">Set the <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> property to `true`.</span></span> <span data-ttu-id="23ef1-119">下面的示例在双击窗体时在显示和省略今天的日期之间切换。</span><span class="sxs-lookup"><span data-stu-id="23ef1-119">The example below toggles between displaying and omitting today's date when the form is double-clicked.</span></span>  
  
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
  
     <span data-ttu-id="23ef1-120"> (Visual c # 中，Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="23ef1-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a><span data-ttu-id="23ef1-121">显示周数</span><span class="sxs-lookup"><span data-stu-id="23ef1-121">To display week numbers</span></span>  
  
- <span data-ttu-id="23ef1-122">将 <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="23ef1-122">Set the <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> property to `true`.</span></span> <span data-ttu-id="23ef1-123">可以在代码中或在属性窗口中设置此属性。</span><span class="sxs-lookup"><span data-stu-id="23ef1-123">You can set this property either in code or in the Properties window.</span></span>  
  
     <span data-ttu-id="23ef1-124">周数将显示在一周的第一天的左侧。</span><span class="sxs-lookup"><span data-stu-id="23ef1-124">Week numbers appear in a separate column to the left of the first day of the week.</span></span>  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="23ef1-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23ef1-125">See also</span></span>

- [<span data-ttu-id="23ef1-126">MonthCalendar 控件</span><span class="sxs-lookup"><span data-stu-id="23ef1-126">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="23ef1-127">如何：在 Windows 窗体 MonthCalendar 控件中选择日期范围</span><span class="sxs-lookup"><span data-stu-id="23ef1-127">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="23ef1-128">如何：使用 Windows 窗体 MonthCalendar 控件以粗体显示特定日期</span><span class="sxs-lookup"><span data-stu-id="23ef1-128">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="23ef1-129">如何：在 Windows 窗体 MonthCalendar 控件中显示多个月份</span><span class="sxs-lookup"><span data-stu-id="23ef1-129">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
