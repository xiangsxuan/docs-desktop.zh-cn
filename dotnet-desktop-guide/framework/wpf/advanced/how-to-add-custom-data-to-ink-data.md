---
title: 如何：向墨迹数据添加自定义数据
ms.date: 03/30/2017
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
ms.openlocfilehash: 7c59a205df5358daec101339cc6a308c8e38a9d6
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972472"
---
# <a name="how-to-add-custom-data-to-ink-data"></a>如何：向墨迹数据添加自定义数据
可以将自定义数据添加到墨迹，当墨迹以墨迹序列化格式保存 (ISF) 时，这些数据将被保存。  您可以将自定义数据保存到 <xref:System.Windows.Ink.DrawingAttributes> 、 <xref:System.Windows.Ink.StrokeCollection> 或 <xref:System.Windows.Ink.Stroke> 。  如果能够将自定义数据保存到三个对象，则可以决定保存数据的最佳位置。  这三个类都使用类似的方法来存储和访问自定义数据。  
  
 只能将以下类型保存为自定义数据：  
  
- <xref:System.Boolean>  
  
- <xref:System.Boolean>[]  
  
- <xref:System.Byte>  
  
- <xref:System.Byte>[]  
  
- <xref:System.Char>  
  
- <xref:System.Char>[]  
  
- <xref:System.DateTime>  
  
- <xref:System.DateTime>[]  
  
- <xref:System.Decimal>  
  
- <xref:System.Decimal>[]  
  
- <xref:System.Double>  
  
- <xref:System.Double>[]  
  
- <xref:System.Int16>  
  
- <xref:System.Int16>[]  
  
- <xref:System.Int32>  
  
- <xref:System.Int32>[]  
  
- <xref:System.Int64>  
  
- <xref:System.Int64>[]  
  
- <xref:System.Single>  
  
- <xref:System.Single>[]  
  
- <xref:System.String>  
  
- <xref:System.UInt16>  
  
- <xref:System.UInt16>[]  
  
- <xref:System.UInt32>  
  
- <xref:System.UInt32>[]  
  
- <xref:System.UInt64>  
  
- <xref:System.UInt64>[]  
  
## <a name="example"></a>示例  
 下面的示例演示如何在中添加和检索自定义数据 <xref:System.Windows.Ink.StrokeCollection> 。  
  
 [!code-csharp[HowToAddCustomDataToInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 下面的示例创建一个显示 <xref:System.Windows.Controls.InkCanvas> 和两个按钮的应用程序。  按钮允许两个 `switchAuthor` 不同作者使用两个笔。  按钮 `changePenColors` 根据作者更改上每个笔划的颜色 <xref:System.Windows.Controls.InkCanvas> 。  应用程序定义了两个 <xref:System.Windows.Ink.DrawingAttributes> 对象，并向每个对象添加了一个自定义属性，该属性指示绘制了哪个作者 <xref:System.Windows.Ink.Stroke> 。  用户单击时 `changePenColors` ，应用程序会根据自定义属性的值更改笔划的外观。  
  
 [!code-xaml[HowToAddCustomDataToInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
