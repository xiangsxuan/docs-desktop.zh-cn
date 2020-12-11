---
title: 通过 DateTimePicker 控件设置和返回日期
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- dates [Windows Forms], setting in DateTimePicker
- DateTimePicker control [Windows Forms], setting and returning dates
- examples [Windows Forms], DateTimePicker control
ms.assetid: a8a48d68-e4b5-426e-9764-51230fc9acd2
ms.openlocfilehash: f958097640316715b38828e72107ab5bdb9389aa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971130"
---
# <a name="how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="99a73-102">如何：使用 Windows 窗体 DateTimePicker 控件设置和返回日期</span><span class="sxs-lookup"><span data-stu-id="99a73-102">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="99a73-103">Windows 窗体 <xref:System.Windows.Forms.DateTimePicker> 控件中的当前所选日期或时间由 <xref:System.Windows.Forms.DateTimePicker.Value%2A> 属性确定。</span><span class="sxs-lookup"><span data-stu-id="99a73-103">The currently selected date or time in the Windows Forms <xref:System.Windows.Forms.DateTimePicker> control is determined by the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property.</span></span> <span data-ttu-id="99a73-104">可在显示控件前（例如，在设计时或在窗体的 <xref:System.Windows.Forms.Form.Load> 事件中）设置 <xref:System.Windows.Forms.DateTimePicker.Value%2A> 属性来确定控件中最初将选定的日期。</span><span class="sxs-lookup"><span data-stu-id="99a73-104">You can set the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property before the control is displayed (for example, at design time or in the form's <xref:System.Windows.Forms.Form.Load> event) to determine which date will be initially selected in the control.</span></span> <span data-ttu-id="99a73-105">默认情况下，该控件的 <xref:System.Windows.Forms.DateTimePicker.Value%2A> 设置为当前日期。</span><span class="sxs-lookup"><span data-stu-id="99a73-105">By default, the control's <xref:System.Windows.Forms.DateTimePicker.Value%2A> is set to the current date.</span></span> <span data-ttu-id="99a73-106">如果更改代码中控件的 <xref:System.Windows.Forms.DateTimePicker.Value%2A>，该控件将自动在窗体上更新以反映新设置。</span><span class="sxs-lookup"><span data-stu-id="99a73-106">If you change the control's <xref:System.Windows.Forms.DateTimePicker.Value%2A> in code, the control is automatically updated on the form to reflect the new setting.</span></span>  
  
 <span data-ttu-id="99a73-107"><xref:System.Windows.Forms.DateTimePicker.Value%2A> 属性返回 <xref:System.DateTime> 结构作为其值。</span><span class="sxs-lookup"><span data-stu-id="99a73-107">The <xref:System.Windows.Forms.DateTimePicker.Value%2A> property returns a <xref:System.DateTime> structure as its value.</span></span> <span data-ttu-id="99a73-108">存在几个 <xref:System.DateTime> 结构的属性，这些属性返回有关所显示日期的特定信息。</span><span class="sxs-lookup"><span data-stu-id="99a73-108">There are several properties of the <xref:System.DateTime> structure that return specific information about the displayed date.</span></span> <span data-ttu-id="99a73-109">这些属性仅可用于返回值；不要使用它们来设置值。</span><span class="sxs-lookup"><span data-stu-id="99a73-109">These properties can only be used to return a value; do not use them to set a value.</span></span>  
  
- <span data-ttu-id="99a73-110">对于日期值，<xref:System.DateTime.Month%2A>、<xref:System.DateTime.Day%2A> 和 <xref:System.DateTime.Year%2A> 属性为这些所选日期的时间单位返回整数值。</span><span class="sxs-lookup"><span data-stu-id="99a73-110">For date values, the <xref:System.DateTime.Month%2A>, <xref:System.DateTime.Day%2A>, and <xref:System.DateTime.Year%2A> properties return integer values for those time units of the selected date.</span></span> <span data-ttu-id="99a73-111"><xref:System.DateTime.DayOfWeek%2A> 属性返回的值指示所选的日期是星期几（<xref:System.DayOfWeek> 枚举中列出了可能的值）。</span><span class="sxs-lookup"><span data-stu-id="99a73-111">The <xref:System.DateTime.DayOfWeek%2A> property returns a value indicating the selected day of the week (possible values are listed in the <xref:System.DayOfWeek> enumeration).</span></span>  
  
- <span data-ttu-id="99a73-112">对于时间值，<xref:System.DateTime.Hour%2A>、<xref:System.DateTime.Minute%2A>、<xref:System.DateTime.Second%2A> 和 <xref:System.DateTime.Millisecond%2A> 属性为这些时间单位返回整数值。</span><span class="sxs-lookup"><span data-stu-id="99a73-112">For time values, the <xref:System.DateTime.Hour%2A>, <xref:System.DateTime.Minute%2A>, <xref:System.DateTime.Second%2A>, and <xref:System.DateTime.Millisecond%2A> properties return integer values for those time units.</span></span> <span data-ttu-id="99a73-113">若要配置控件以显示时间，请参阅 [如何：在 DateTimePicker 控件中显示时间](how-to-display-time-with-the-datetimepicker-control.md)。</span><span class="sxs-lookup"><span data-stu-id="99a73-113">To configure the control to display times, see [How to: Display Time with the DateTimePicker Control](how-to-display-time-with-the-datetimepicker-control.md).</span></span>  
  
### <a name="to-set-the-date-and-time-value-of-the-control"></a><span data-ttu-id="99a73-114">设置控件的日期和时间值</span><span class="sxs-lookup"><span data-stu-id="99a73-114">To set the date and time value of the control</span></span>  
  
- <span data-ttu-id="99a73-115">将 <xref:System.Windows.Forms.DateTimePicker.Value%2A> 属性设置为日期或时间值。</span><span class="sxs-lookup"><span data-stu-id="99a73-115">Set the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property to a date or time value.</span></span>  
  
    ```vb  
    DateTimePicker1.Value = New DateTime(2001, 10, 20)  
    ```  
  
    ```csharp  
    dateTimePicker1.Value = new DateTime(2001, 10, 20);  
    ```  
  
    ```cpp  
    dateTimePicker1->Value = DateTime(2001, 10, 20);  
    ```  
  
### <a name="to-return-the-date-and-time-value"></a><span data-ttu-id="99a73-116">返回日期和时间值</span><span class="sxs-lookup"><span data-stu-id="99a73-116">To return the date and time value</span></span>  
  
- <span data-ttu-id="99a73-117">调用 <xref:System.Windows.Forms.DateTimePicker.Text%2A> 属性以按照控件中设置的格式返回完整值，或调用 <xref:System.Windows.Forms.DateTimePicker.Value%2A> 属性的合适方法以返回值的一部分。</span><span class="sxs-lookup"><span data-stu-id="99a73-117">Call the <xref:System.Windows.Forms.DateTimePicker.Text%2A> property to return the entire value as formatted in the control, or call the appropriate method of the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property to return a part of the value.</span></span> <span data-ttu-id="99a73-118">使用 <xref:System.Windows.Forms.DateTimePicker.ToString%2A> 将信息转换为可向用户显示的字符串。</span><span class="sxs-lookup"><span data-stu-id="99a73-118">Use <xref:System.Windows.Forms.DateTimePicker.ToString%2A> to convert the information into a string that can be displayed to the user.</span></span>  
  
    ```vb  
    MessageBox.Show("The selected value is ", DateTimePicker1.Text)  
    MessageBox.Show("The day of the week is ",
       DateTimePicker1.Value.DayOfWeek.ToString)  
    MessageBox.Show("Millisecond is: ",
       DateTimePicker1.Value.Millisecond.ToString)  
    ```  
  
    ```csharp  
    MessageBox.Show ("The selected value is " +
       dateTimePicker1.Text);  
    MessageBox.Show ("The day of the week is " +
       dateTimePicker1.Value.DayOfWeek.ToString());  
    MessageBox.Show("Millisecond is: " +
       dateTimePicker1.Value.Millisecond.ToString());  
    ```  
  
    ```cpp  
    MessageBox::Show (String::Concat("The selected value is ",  
       dateTimePicker1->Text));  
    MessageBox::Show (String::Concat("The day of the week is ",  
       dateTimePicker1->Value.DayOfWeek.ToString()));  
    MessageBox::Show(String::Concat("Millisecond is: ",  
       dateTimePicker1->Value.Millisecond.ToString()));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="99a73-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99a73-119">See also</span></span>

- [<span data-ttu-id="99a73-120">DateTimePicker 控件</span><span class="sxs-lookup"><span data-stu-id="99a73-120">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
- [<span data-ttu-id="99a73-121">如何：使用 Windows 窗体 DateTimePicker 控件以自定义格式显示日期</span><span class="sxs-lookup"><span data-stu-id="99a73-121">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
