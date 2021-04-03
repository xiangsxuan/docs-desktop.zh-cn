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
# <a name="datepicker"></a><span data-ttu-id="1e92f-102">DatePicker</span><span class="sxs-lookup"><span data-stu-id="1e92f-102">DatePicker</span></span>
<span data-ttu-id="1e92f-103"><xref:System.Windows.Controls.DatePicker>控件允许用户通过在文本字段中键入日期或使用下拉控件来选择日期 <xref:System.Windows.Controls.Calendar> 。</span><span class="sxs-lookup"><span data-stu-id="1e92f-103">The <xref:System.Windows.Controls.DatePicker> control allows the user to select a date by either typing it into a text field or by using a drop-down <xref:System.Windows.Controls.Calendar> control.</span></span>  
  
 <span data-ttu-id="1e92f-104">下图显示了 <xref:System.Windows.Controls.DatePicker> 。</span><span class="sxs-lookup"><span data-stu-id="1e92f-104">The following illustration shows a <xref:System.Windows.Controls.DatePicker>.</span></span>  
  
 <span data-ttu-id="1e92f-105">![DatePicker 控件](./media/ndp-datepicker.png "NDP_DatePicker")</span><span class="sxs-lookup"><span data-stu-id="1e92f-105">![DatePicker control](./media/ndp-datepicker.png "NDP_DatePicker")</span></span>  
<span data-ttu-id="1e92f-106">DatePicker 控件</span><span class="sxs-lookup"><span data-stu-id="1e92f-106">DatePicker Control</span></span>  
  
 <span data-ttu-id="1e92f-107"><xref:System.Windows.Controls.DatePicker>控件的许多属性是管理其内置的 <xref:System.Windows.Controls.Calendar> ，并且与中的等效属性的功能相同 <xref:System.Windows.Controls.Calendar> 。</span><span class="sxs-lookup"><span data-stu-id="1e92f-107">Many of a <xref:System.Windows.Controls.DatePicker> control's properties are for managing its built-in <xref:System.Windows.Controls.Calendar>, and function identically to the equivalent property in <xref:System.Windows.Controls.Calendar>.</span></span> <span data-ttu-id="1e92f-108">特别是，、、、、 <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType> 、 <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType> 和属性的 <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> 功能与其对应项的作用相同 <xref:System.Windows.Controls.Calendar> 。</span><span class="sxs-lookup"><span data-stu-id="1e92f-108">In particular, the <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, and <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> properties function identically to their <xref:System.Windows.Controls.Calendar> counterparts.</span></span> <span data-ttu-id="1e92f-109">有关详细信息，请参阅 <xref:System.Windows.Controls.Calendar>。</span><span class="sxs-lookup"><span data-stu-id="1e92f-109">For more information, see <xref:System.Windows.Controls.Calendar>.</span></span>  
  
 <span data-ttu-id="1e92f-110">用户可以直接在文本字段中键入日期，以设置 <xref:System.Windows.Controls.DatePicker.Text%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="1e92f-110">Users can type a date directly into a text field, which sets the <xref:System.Windows.Controls.DatePicker.Text%2A> property.</span></span> <span data-ttu-id="1e92f-111">如果 <xref:System.Windows.Controls.DatePicker> 无法将输入的字符串转换为有效的日期，则 <xref:System.Windows.Controls.DatePicker.DateValidationError> 会引发事件。</span><span class="sxs-lookup"><span data-stu-id="1e92f-111">If the <xref:System.Windows.Controls.DatePicker> cannot convert the entered string to a valid date, the <xref:System.Windows.Controls.DatePicker.DateValidationError> event will be raised.</span></span> <span data-ttu-id="1e92f-112">默认情况下，这会引发异常，但的事件处理程序 <xref:System.Windows.Controls.DatePicker.DateValidationError> 可以将 <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> 属性设置为 `false` ，并防止引发异常。</span><span class="sxs-lookup"><span data-stu-id="1e92f-112">By default, this causes an exception, but an event handler for <xref:System.Windows.Controls.DatePicker.DateValidationError> can set the <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> property to `false` and prevent an exception from being raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e92f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e92f-113">See also</span></span>

- [<span data-ttu-id="1e92f-114">控件</span><span class="sxs-lookup"><span data-stu-id="1e92f-114">Controls</span></span>](index.md)
- [<span data-ttu-id="1e92f-115">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="1e92f-115">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
