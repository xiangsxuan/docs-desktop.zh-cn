---
title: 如何：使用 ThicknessConverter 对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: 7420824ad939012d12f61ecbb72f2d00ce483e8b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971810"
---
# <a name="how-to-use-a-thicknessconverter-object"></a><span data-ttu-id="6264c-102">如何：使用 ThicknessConverter 对象</span><span class="sxs-lookup"><span data-stu-id="6264c-102">How to: Use a ThicknessConverter Object</span></span>

## <a name="example"></a><span data-ttu-id="6264c-103">示例</span><span class="sxs-lookup"><span data-stu-id="6264c-103">Example</span></span>  

 <span data-ttu-id="6264c-104">此示例演示如何创建实例 <xref:System.Windows.ThicknessConverter> ，并使用它来更改边框的粗细。</span><span class="sxs-lookup"><span data-stu-id="6264c-104">This example shows how to create an instance of <xref:System.Windows.ThicknessConverter> and use it to change the thickness of a border.</span></span>  
  
 <span data-ttu-id="6264c-105">该示例定义了一个名为的自定义方法 `changeThickness` ; 此方法首先将中定义的的内容转换为的 <xref:System.Windows.Controls.ListBoxItem> 实例，然后将 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] <xref:System.Windows.Thickness> 内容转换为 <xref:System.String> 。</span><span class="sxs-lookup"><span data-stu-id="6264c-105">The example defines a custom method called `changeThickness`; this method first converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Windows.Thickness>, and later converts the content into a <xref:System.String>.</span></span> <span data-ttu-id="6264c-106">此方法将传递 <xref:System.Windows.Controls.ListBoxItem> 到一个 <xref:System.Windows.ThicknessConverter> 对象，该对象将 <xref:System.Windows.Controls.ContentControl.Content%2A> 的转换 <xref:System.Windows.Controls.ListBoxItem> 为的实例 <xref:System.Windows.Thickness> 。</span><span class="sxs-lookup"><span data-stu-id="6264c-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.ThicknessConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.Thickness>.</span></span> <span data-ttu-id="6264c-107">然后，将此值作为的属性的值传递回 <xref:System.Windows.Controls.Border.BorderThickness%2A> <xref:System.Windows.Controls.Border> 。</span><span class="sxs-lookup"><span data-stu-id="6264c-107">This value is then passed back as the value of the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of the <xref:System.Windows.Controls.Border>.</span></span>  
  
 <span data-ttu-id="6264c-108">此示例不运行。</span><span class="sxs-lookup"><span data-stu-id="6264c-108">This example does not run.</span></span>  
  
 [!code-csharp[ThicknessConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6264c-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6264c-109">See also</span></span>

- <xref:System.Windows.Thickness>
- <xref:System.Windows.ThicknessConverter>
- <xref:System.Windows.Controls.Border>
- <span data-ttu-id="6264c-110">[如何：更改 Margin 属性](/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="6264c-110">[How to: Change the Margin Property](/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))</span></span>
- <span data-ttu-id="6264c-111">[如何：将 ListBoxItem 转换为新数据类型](/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="6264c-111">[How to: Convert a ListBoxItem to a new Data Type](/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))</span></span>
- [<span data-ttu-id="6264c-112">面板概述</span><span class="sxs-lookup"><span data-stu-id="6264c-112">Panels Overview</span></span>](../controls/panels-overview.md)
