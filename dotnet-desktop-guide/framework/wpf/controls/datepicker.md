---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: 4e4b536aca768872a0729a9b34a5dc1cc17e04fb
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973375"
---
# <a name="datepicker"></a>DatePicker
<xref:System.Windows.Controls.DatePicker>控件允许用户通过在文本字段中键入日期或使用下拉控件来选择日期 <xref:System.Windows.Controls.Calendar> 。  
  
 下图显示了 <xref:System.Windows.Controls.DatePicker> 。  
  
 ![DatePicker 控件](./media/ndp-datepicker.png "NDP_DatePicker")  
DatePicker 控件  
  
 <xref:System.Windows.Controls.DatePicker>控件的许多属性是管理其内置的 <xref:System.Windows.Controls.Calendar> ，并且与中的等效属性的功能相同 <xref:System.Windows.Controls.Calendar> 。 特别是，、、、、 <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType> 、 <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType> 和属性的 <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> 功能与其对应项的作用相同 <xref:System.Windows.Controls.Calendar> 。 有关详细信息，请参阅 <xref:System.Windows.Controls.Calendar>。  
  
 用户可以直接在文本字段中键入日期，以设置 <xref:System.Windows.Controls.DatePicker.Text%2A> 属性。 如果 <xref:System.Windows.Controls.DatePicker> 无法将输入的字符串转换为有效的日期，则 <xref:System.Windows.Controls.DatePicker.DateValidationError> 会引发事件。 默认情况下，这会引发异常，但的事件处理程序 <xref:System.Windows.Controls.DatePicker.DateValidationError> 可以将 <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> 属性设置为 `false` ，并防止引发异常。  
  
## <a name="see-also"></a>请参阅

- [控件](index.md)
- [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
