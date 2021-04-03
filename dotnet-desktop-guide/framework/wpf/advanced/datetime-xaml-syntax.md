---
title: DateTime XAML 语法
ms.date: 03/30/2017
helpviewer_keywords:
- DateTime XAML syntax [WPF], strings for
- DateTime XAML syntax [WPF], where used
- short date format [WPF], DateTime
- DateTime XAML syntax [WPF]
- DateTime XAML text [WPF]
- DateTime XAML syntax [WPF], format strings for
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
ms.openlocfilehash: dc7291f09c44f8a0b616bf38c1c90eb92ec906e6
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971944"
---
# <a name="datetime-xaml-syntax"></a>DateTime XAML 语法
某些控件（例如 <xref:System.Windows.Controls.Calendar> 和 <xref:System.Windows.Controls.DatePicker> ）具有使用该类型的属性 <xref:System.DateTime> 。 虽然通常会在运行时在代码隐藏中指定这些控件的初始日期或时间，但可以在 XAML 中指定初始日期或时间。 WPF XAML 分析器 <xref:System.DateTime> 使用内置的 XAML 文本语法来处理值分析。 本主题介绍 <xref:System.DateTime> XAML 文本语法的具体信息。  

<a name="where_datetime_xaml_syntax_is_used"></a>
## <a name="when-to-use-datetime-xaml-syntax"></a>DateTime XAML 语法的使用场合  
 无需经常对 XAML 中的日期进行设置，而且设置也可能并不合适。 例如，可以使用 <xref:System.DateTime.Now%2A?displayProperty=nameWithType> 属性在运行时初始化日期，也可以基于用户输入在代码隐藏中执行日历的所有日期调整。 但是，在某些情况下，你可能想要 <xref:System.Windows.Controls.Calendar> <xref:System.Windows.Controls.DatePicker> 在和控件模板中对日期进行硬编码。 <xref:System.DateTime>XAML 语法必须用于这些方案。  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>DateTime XAML 语法是本机行为  
 <xref:System.DateTime> 是在 CLR 的基类库中定义的类。 由于基类库如何与 CLR 的其余部分相关，因此不能应用于 <xref:System.ComponentModel.TypeConverterAttribute> 类并使用类型转换器来处理 XAML 中的字符串，并将其转换为 <xref:System.DateTime> 运行时对象模型中的字符串。 没有提供转换行为的 `DateTimeConverter` 类；本主题中描述的转换行为源于 WPF XAML 分析器。  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>
## <a name="format-strings-for-datetime-xaml-syntax"></a>DateTime XAML 语法的格式字符串  
 您可以 <xref:System.DateTime> 使用格式字符串指定的格式。 格式字符串会规范可用于创建值的文本语法。 <xref:System.DateTime> 现有 WPF 控件的值通常仅使用的日期组成部分 <xref:System.DateTime> ，而不是时间部分。  
  
 <xref:System.DateTime>在 XAML 中指定时，可以将任何格式字符串互换使用。  
  
 还可以使用未在本主题中专门显示的格式和格式字符串。 从技术上说， <xref:System.DateTime> WPF xaml 分析器指定然后分析的任何值的 XAML 都使用对的内部调用 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> ，因此，你可以使用接受的任何字符串 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> 作为 XAML 输入。 有关详细信息，请参阅 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>。  
  
> [!IMPORTANT]
> DateTime XAML 语法始终使用 `en-us` 作为 <xref:System.Globalization.CultureInfo> 其本机转换的。 这不受 <xref:System.Windows.FrameworkElement.Language%2A> xaml 中的值或 `xml:lang` 值影响，因为 xaml 特性级类型转换在没有该上下文的情况下起作用。 出于区域性差异的原因，请不要尝试插入此处所示的格式字符串，例如，日期和月份的显示顺序。 此处所示的格式字符串是在分析 XAML 时（不考虑其他区域性设置）使用的确切格式字符串。  
  
 以下各节介绍一些常用 <xref:System.DateTime> 格式字符串。  
  
### <a name="short-date-pattern-d"></a>短日期模式（“d”）  
 下面演示了 XAML 中的的短日期格式 <xref:System.DateTime> ：  
  
 `M/d/YYYY`  
  
 这是最简单的形式，可指定 WPF 控件一般使用的所有必要信息，并且不受针对时间部分的偶然时区偏移的影响，因此比其他格式更适用。  
  
 例如，若要指定日期 2010 年 6 月 1 日，可使用以下字符串：  
  
 `3/1/2010`  
  
 有关详细信息，请参阅 <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>。  
  
### <a name="sortable-datetime-pattern-s"></a>可排序 DateTime 模式（“s”）  
 下面演示了 XAML 中的可排序 <xref:System.DateTime> 模式：  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 例如，若要指定日期 2010 年 6 月 1 日，可使用以下字符串（时间部分全部输入为 0）：  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>RFC1123 模式（“r”）  
 RFC1123 模式很有用，因为它可以是来自其他日期生成器的字符串输入，这些字符生成器出于区域性固定原因同样使用 RFC1123 模式。 下面演示了 <xref:System.DateTime> XAML 中的 RFC1123 模式：  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 例如，若要指定日期 2010 年 6 月 1 日，可使用以下字符串（时间部分全部输入为 0）：  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>其他格式和模式  
 如前文所述， <xref:System.DateTime> 可将 XAML 中的指定为可作为输入的任意字符串 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> 。 这包括 (示例) 的其他形式化格式 <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A> ，以及不是作为特定形式规范化的格式 <xref:System.Globalization.DateTimeFormatInfo> 。 例如，窗体 `YYYY/mm/dd` 可作为的输入 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> 。 本主题并没有试图介绍所有可能有效的格式，而是推荐将短日期模式作为一种标准做法。  
  
## <a name="see-also"></a>另请参阅

- [XAML 概述 (WPF)](/dotnet/desktop-wpf/fundamentals/xaml)
