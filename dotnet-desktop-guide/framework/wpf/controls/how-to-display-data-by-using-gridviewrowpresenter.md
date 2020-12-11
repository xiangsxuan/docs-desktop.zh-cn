---
title: 如何：使用 GridViewRowPresenter 来显示数据
ms.date: 03/30/2017
helpviewer_keywords:
- displaying data with GridViewRowPresenter [WPF]
- GridViewRowPresenter [WPF]
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
ms.openlocfilehash: 0e471df3ab6fd10417fc58ece4cdb8ff1c457c95
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973715"
---
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a><span data-ttu-id="b8a0c-102">如何：使用 GridViewRowPresenter 来显示数据</span><span class="sxs-lookup"><span data-stu-id="b8a0c-102">How to: Display Data by Using GridViewRowPresenter</span></span>
<span data-ttu-id="b8a0c-103">此示例演示如何使用 <xref:System.Windows.Controls.GridViewRowPresenter> 和 <xref:System.Windows.Controls.GridViewHeaderRowPresenter> 对象在列中显示数据。</span><span class="sxs-lookup"><span data-stu-id="b8a0c-103">This example shows how to use the <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects to display data in columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8a0c-104">示例</span><span class="sxs-lookup"><span data-stu-id="b8a0c-104">Example</span></span>  
 <span data-ttu-id="b8a0c-105">下面的示例演示如何 <xref:System.Windows.Controls.GridViewColumnCollection> <xref:System.DateTime.DayOfWeek%2A> <xref:System.DateTime.Year%2A> <xref:System.DateTime> 使用 <xref:System.Windows.Controls.GridViewRowPresenter> 和 <xref:System.Windows.Controls.GridViewHeaderRowPresenter> 对象来指定显示对象的和的。</span><span class="sxs-lookup"><span data-stu-id="b8a0c-105">The following example shows how to specify a <xref:System.Windows.Controls.GridViewColumnCollection> that displays the <xref:System.DateTime.DayOfWeek%2A> and <xref:System.DateTime.Year%2A> of a <xref:System.DateTime> object by using <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects.</span></span> <span data-ttu-id="b8a0c-106">该示例还 <xref:System.Windows.Style> 为的定义了 <xref:System.Windows.Controls.GridViewColumn.Header%2A> <xref:System.Windows.Controls.GridViewColumn> 。</span><span class="sxs-lookup"><span data-stu-id="b8a0c-106">The example also defines a <xref:System.Windows.Style> for the <xref:System.Windows.Controls.GridViewColumn.Header%2A> of a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a><span data-ttu-id="b8a0c-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8a0c-107">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewColumnCollection>
- [<span data-ttu-id="b8a0c-108">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="b8a0c-108">GridView Overview</span></span>](gridview-overview.md)
