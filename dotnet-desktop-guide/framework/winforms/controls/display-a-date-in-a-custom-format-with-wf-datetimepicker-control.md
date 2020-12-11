---
title: 使用 DateTimePicker 控件以自定义格式显示日期
description: 了解如何使用 Windows 窗体 DateTimePicker 控件设置控件中日期和时间的显示格式。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
ms.openlocfilehash: 773070136e4fd43ab1bf510ebcaf6b0aa6a7ba8a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970070"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="cbc99-103">如何：使用 Windows 窗体 DateTimePicker 控件以自定义格式显示日期</span><span class="sxs-lookup"><span data-stu-id="cbc99-103">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="cbc99-104">Windows 窗体 <xref:System.Windows.Forms.DateTimePicker> 控件使您可以灵活地设置控件中日期和时间的显示格式。</span><span class="sxs-lookup"><span data-stu-id="cbc99-104">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="cbc99-105"><xref:System.Windows.Forms.DateTimePicker.Format%2A>属性允许您从中列出的预定义格式中进行选择 <xref:System.Windows.Forms.DateTimePickerFormat> 。</span><span class="sxs-lookup"><span data-stu-id="cbc99-105">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="cbc99-106">如果这些都不能满足您的需要，则可以使用中列出的格式字符来创建自己的格式样式 <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> 。</span><span class="sxs-lookup"><span data-stu-id="cbc99-106">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="cbc99-107">显示自定义格式</span><span class="sxs-lookup"><span data-stu-id="cbc99-107">To display a custom format</span></span>  
  
1. <span data-ttu-id="cbc99-108">将 <xref:System.Windows.Forms.DateTimePicker.Format%2A> 属性设置为 `DateTimePickerFormat.Custom`。</span><span class="sxs-lookup"><span data-stu-id="cbc99-108">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2. <span data-ttu-id="cbc99-109">将 <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> 属性设置为格式字符串。</span><span class="sxs-lookup"><span data-stu-id="cbc99-109">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
    ```vb  
    DateTimePicker1.Format = DateTimePickerFormat.Custom  
    ' Display the date as "Mon 27 Feb 2012".  
    DateTimePicker1.CustomFormat = "ddd dd MMM yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.Format = DateTimePickerFormat.Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1.CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->Format = DateTimePickerFormat::Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1->CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="cbc99-110">向格式化值添加文本</span><span class="sxs-lookup"><span data-stu-id="cbc99-110">To add text to the formatted value</span></span>  
  
1. <span data-ttu-id="cbc99-111">使用单引号将不是格式字符（如 "M"）或分隔符（如 "："）的任何字符括起来。</span><span class="sxs-lookup"><span data-stu-id="cbc99-111">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="cbc99-112">例如，下面的格式字符串将显示英语 (美国) 区域性中的 "今天为：05:30:31 星期五，2012" 格式的当前日期。</span><span class="sxs-lookup"><span data-stu-id="cbc99-112">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
    ```vb  
    DateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->CustomFormat =  
       "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
     <span data-ttu-id="cbc99-113">根据区域性设置的不同，不包含在单引号中的任何字符都可以更改。</span><span class="sxs-lookup"><span data-stu-id="cbc99-113">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="cbc99-114">例如，上面的格式字符串将以英语 (美国) 区域性显示当前日期，格式为 "今日为：05:30:31 星期五，2012"。</span><span class="sxs-lookup"><span data-stu-id="cbc99-114">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="cbc99-115">请注意，第一个冒号括在单引号中，因为它不应作为 "hh： mm： ss" 中的分隔字符。</span><span class="sxs-lookup"><span data-stu-id="cbc99-115">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="cbc99-116">在另一种区域性中，该格式可能显示为 "今天是：05.30.31 星期五02： 2012"。</span><span class="sxs-lookup"><span data-stu-id="cbc99-116">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc99-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cbc99-117">See also</span></span>

- [<span data-ttu-id="cbc99-118">DateTimePicker 控件</span><span class="sxs-lookup"><span data-stu-id="cbc99-118">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
- [<span data-ttu-id="cbc99-119">如何：使用 Windows 窗体 DateTimePicker 控件设置和返回日期</span><span class="sxs-lookup"><span data-stu-id="cbc99-119">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
