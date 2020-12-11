---
title: 如何：向墨迹数据添加自定义数据
ms.date: 03/30/2017
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
ms.openlocfilehash: 7c59a205df5358daec101339cc6a308c8e38a9d6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972472"
---
# <a name="how-to-add-custom-data-to-ink-data"></a><span data-ttu-id="8d986-102">如何：向墨迹数据添加自定义数据</span><span class="sxs-lookup"><span data-stu-id="8d986-102">How to: Add Custom Data to Ink Data</span></span>
<span data-ttu-id="8d986-103">可以将自定义数据添加到墨迹，当墨迹以墨迹序列化格式保存 (ISF) 时，这些数据将被保存。</span><span class="sxs-lookup"><span data-stu-id="8d986-103">You can add custom data to ink that will be saved when the ink is saved as ink serialized format (ISF).</span></span>  <span data-ttu-id="8d986-104">您可以将自定义数据保存到 <xref:System.Windows.Ink.DrawingAttributes> 、 <xref:System.Windows.Ink.StrokeCollection> 或 <xref:System.Windows.Ink.Stroke> 。</span><span class="sxs-lookup"><span data-stu-id="8d986-104">You can save the custom data to the <xref:System.Windows.Ink.DrawingAttributes>, the <xref:System.Windows.Ink.StrokeCollection>, or the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="8d986-105">如果能够将自定义数据保存到三个对象，则可以决定保存数据的最佳位置。</span><span class="sxs-lookup"><span data-stu-id="8d986-105">Being able to save custom data on three objects gives you the ability to decide the best place to save the data.</span></span>  <span data-ttu-id="8d986-106">这三个类都使用类似的方法来存储和访问自定义数据。</span><span class="sxs-lookup"><span data-stu-id="8d986-106">All three classes use similar methods to store and access custom data.</span></span>  
  
 <span data-ttu-id="8d986-107">只能将以下类型保存为自定义数据：</span><span class="sxs-lookup"><span data-stu-id="8d986-107">Only the following types can be saved as custom data:</span></span>  
  
- <xref:System.Boolean>  
  
- <span data-ttu-id="8d986-108"><xref:System.Boolean>[]</span><span class="sxs-lookup"><span data-stu-id="8d986-108"><xref:System.Boolean>[]</span></span>  
  
- <xref:System.Byte>  
  
- <span data-ttu-id="8d986-109"><xref:System.Byte>[]</span><span class="sxs-lookup"><span data-stu-id="8d986-109"><xref:System.Byte>[]</span></span>  
  
- <xref:System.Char>  
  
- <span data-ttu-id="8d986-110"><xref:System.Char>[]</span><span class="sxs-lookup"><span data-stu-id="8d986-110"><xref:System.Char>[]</span></span>  
  
- <xref:System.DateTime>  
  
- <span data-ttu-id="8d986-111"><xref:System.DateTime>[]</span><span class="sxs-lookup"><span data-stu-id="8d986-111"><xref:System.DateTime>[]</span></span>  
  
- <xref:System.Decimal>  
  
- <span data-ttu-id="8d986-112"><xref:System.Decimal>[]</span><span class="sxs-lookup"><span data-stu-id="8d986-112"><xref:System.Decimal>[]</span></span>  
  
- <xref:System.Double>  
  
- <span data-ttu-id="8d986-113"><xref:System.Double>[]</span><span class="sxs-lookup"><span data-stu-id="8d986-113"><xref:System.Double>[]</span></span>  
  
- <xref:System.Int16>  
  
- <span data-ttu-id="8d986-114"><xref:System.Int16>[]</span><span class="sxs-lookup"><span data-stu-id="8d986-114"><xref:System.Int16>[]</span></span>  
  
- <xref:System.Int32>  
  
- <span data-ttu-id="8d986-115"><xref:System.Int32>[]</span><span class="sxs-lookup"><span data-stu-id="8d986-115"><xref:System.Int32>[]</span></span>  
  
- <xref:System.Int64>  
  
- <span data-ttu-id="8d986-116"><xref:System.Int64>[]</span><span class="sxs-lookup"><span data-stu-id="8d986-116"><xref:System.Int64>[]</span></span>  
  
- <xref:System.Single>  
  
- <span data-ttu-id="8d986-117"><xref:System.Single>[]</span><span class="sxs-lookup"><span data-stu-id="8d986-117"><xref:System.Single>[]</span></span>  
  
- <xref:System.String>  
  
- <xref:System.UInt16>  
  
- <span data-ttu-id="8d986-118"><xref:System.UInt16>[]</span><span class="sxs-lookup"><span data-stu-id="8d986-118"><xref:System.UInt16>[]</span></span>  
  
- <xref:System.UInt32>  
  
- <span data-ttu-id="8d986-119"><xref:System.UInt32>[]</span><span class="sxs-lookup"><span data-stu-id="8d986-119"><xref:System.UInt32>[]</span></span>  
  
- <xref:System.UInt64>  
  
- <span data-ttu-id="8d986-120"><xref:System.UInt64>[]</span><span class="sxs-lookup"><span data-stu-id="8d986-120"><xref:System.UInt64>[]</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d986-121">示例</span><span class="sxs-lookup"><span data-stu-id="8d986-121">Example</span></span>  
 <span data-ttu-id="8d986-122">下面的示例演示如何在中添加和检索自定义数据 <xref:System.Windows.Ink.StrokeCollection> 。</span><span class="sxs-lookup"><span data-stu-id="8d986-122">The following example demonstrates how to add and retrieve custom data from a <xref:System.Windows.Ink.StrokeCollection>.</span></span>  
  
 [!code-csharp[HowToAddCustomDataToInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 <span data-ttu-id="8d986-123">下面的示例创建一个显示 <xref:System.Windows.Controls.InkCanvas> 和两个按钮的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8d986-123">The following example creates an application that displays an <xref:System.Windows.Controls.InkCanvas> and two buttons.</span></span>  <span data-ttu-id="8d986-124">按钮允许两个 `switchAuthor` 不同作者使用两个笔。</span><span class="sxs-lookup"><span data-stu-id="8d986-124">The button, `switchAuthor`, enables two pens to be used by two different authors.</span></span>  <span data-ttu-id="8d986-125">按钮 `changePenColors` 根据作者更改上每个笔划的颜色 <xref:System.Windows.Controls.InkCanvas> 。</span><span class="sxs-lookup"><span data-stu-id="8d986-125">The button `changePenColors` changes the color of each stroke on the <xref:System.Windows.Controls.InkCanvas> according to the author.</span></span>  <span data-ttu-id="8d986-126">应用程序定义了两个 <xref:System.Windows.Ink.DrawingAttributes> 对象，并向每个对象添加了一个自定义属性，该属性指示绘制了哪个作者 <xref:System.Windows.Ink.Stroke> 。</span><span class="sxs-lookup"><span data-stu-id="8d986-126">The application defines two <xref:System.Windows.Ink.DrawingAttributes> objects and adds a custom property to each one that indicates which author drew the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="8d986-127">用户单击时 `changePenColors` ，应用程序会根据自定义属性的值更改笔划的外观。</span><span class="sxs-lookup"><span data-stu-id="8d986-127">When the user clicks `changePenColors`, the application changes the appearance of the stroke according to the value of the custom property.</span></span>  
  
 [!code-xaml[HowToAddCustomDataToInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
