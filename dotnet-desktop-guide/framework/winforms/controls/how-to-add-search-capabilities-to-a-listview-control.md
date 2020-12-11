---
title: 如何：向 ListView 控件添加搜索功能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
ms.openlocfilehash: d5d4dae55fc9f0613ab6535b2fe57e262d0ef141
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971782"
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a><span data-ttu-id="8c38a-102">如何：向 ListView 控件添加搜索功能</span><span class="sxs-lookup"><span data-stu-id="8c38a-102">How to: Add Search Capabilities to a ListView Control</span></span>
<span data-ttu-id="8c38a-103">在使用控件中的大型项列表时，经常 <xref:System.Windows.Forms.ListView> 需要为用户提供搜索功能。</span><span class="sxs-lookup"><span data-stu-id="8c38a-103">Oftentimes when working with a large list of items in a <xref:System.Windows.Forms.ListView> control, you want to offer search capabilities to the user.</span></span> <span data-ttu-id="8c38a-104"><xref:System.Windows.Forms.ListView>控件通过两种不同的方式提供此功能：文本匹配和位置搜索。</span><span class="sxs-lookup"><span data-stu-id="8c38a-104">The <xref:System.Windows.Forms.ListView> control offers this capability in two different ways: text matching and location searching.</span></span>  
  
 <span data-ttu-id="8c38a-105"><xref:System.Windows.Forms.ListView.FindItemWithText%2A>方法允许您在 <xref:System.Windows.Forms.ListView> 给定搜索字符串和可选起始和结束索引的 in 列表或详细信息视图中执行文本搜索。</span><span class="sxs-lookup"><span data-stu-id="8c38a-105">The <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method allows you to perform a text search on a <xref:System.Windows.Forms.ListView> in list or details view, given a search string and an optional starting and ending index.</span></span> <span data-ttu-id="8c38a-106">与此相反，在 <xref:System.Windows.Forms.ListView.FindNearestItem%2A> <xref:System.Windows.Forms.ListView> 给定一组 x 坐标和 y 坐标以及搜索方向的情况下，该方法允许您在中的图标或磁贴视图中查找项。</span><span class="sxs-lookup"><span data-stu-id="8c38a-106">In contrast, the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method allows you to find an item in a <xref:System.Windows.Forms.ListView> in icon or tile view, given a set of x- and y-coordinates and a direction to search.</span></span>  
  
### <a name="to-find-an-item-using-text"></a><span data-ttu-id="8c38a-107">使用文本查找项</span><span class="sxs-lookup"><span data-stu-id="8c38a-107">To find an item using text</span></span>  
  
1. <span data-ttu-id="8c38a-108">创建一个 <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.ListView.View%2A> 将属性设置为 <xref:System.Windows.Forms.View.Details> 或的 <xref:System.Windows.Forms.View.List> ，然后填充 <xref:System.Windows.Forms.ListView> with 项。</span><span class="sxs-lookup"><span data-stu-id="8c38a-108">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.ListView.View%2A> property set to <xref:System.Windows.Forms.View.Details> or <xref:System.Windows.Forms.View.List>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2. <span data-ttu-id="8c38a-109">调用 <xref:System.Windows.Forms.ListView.FindItemWithText%2A> 方法，传递要查找的项的文本。</span><span class="sxs-lookup"><span data-stu-id="8c38a-109">Call the <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method, passing the text of the item you would like to find.</span></span>  
  
3. <span data-ttu-id="8c38a-110">下面的代码示例演示如何创建一个基本的 <xref:System.Windows.Forms.ListView> ，使用项填充该项，并使用用户提供的文本输入查找列表中的项。</span><span class="sxs-lookup"><span data-stu-id="8c38a-110">The following code example demonstrates how to create a basic <xref:System.Windows.Forms.ListView>, populate it with items, and use text input from the user to find an item in the list.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a><span data-ttu-id="8c38a-111">使用 x 和 y 坐标查找项</span><span class="sxs-lookup"><span data-stu-id="8c38a-111">To find an item using x- and y-coordinates</span></span>  
  
1. <span data-ttu-id="8c38a-112">创建一个 <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.View> 将属性设置为 <xref:System.Windows.Forms.View.SmallIcon> 或的 <xref:System.Windows.Forms.View.LargeIcon> ，然后填充 <xref:System.Windows.Forms.ListView> with 项。</span><span class="sxs-lookup"><span data-stu-id="8c38a-112">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.View> property set to <xref:System.Windows.Forms.View.SmallIcon> or <xref:System.Windows.Forms.View.LargeIcon>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2. <span data-ttu-id="8c38a-113">调用 <xref:System.Windows.Forms.ListView.FindNearestItem%2A> 方法，传递所需的 x 坐标和 y 坐标以及想要搜索的方向。</span><span class="sxs-lookup"><span data-stu-id="8c38a-113">Call the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method, passing the desired x- and y-coordinates and the direction you would like to search.</span></span>  
  
3. <span data-ttu-id="8c38a-114">下面的代码示例演示如何创建一个基本的图标 <xref:System.Windows.Forms.ListView> ，将其填充到项，并捕获 <xref:System.Windows.Forms.Control.MouseDown> 事件以查找向上方向最近的项。</span><span class="sxs-lookup"><span data-stu-id="8c38a-114">The following code example demonstrates how to create a basic icon <xref:System.Windows.Forms.ListView>, populate it with items, and capture the <xref:System.Windows.Forms.Control.MouseDown> event to find the nearest item in the up direction.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="8c38a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c38a-115">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.FindItemWithText%2A>
- <xref:System.Windows.Forms.ListView.FindNearestItem%2A>
- [<span data-ttu-id="8c38a-116">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="8c38a-116">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="8c38a-117">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="8c38a-117">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="8c38a-118">如何：使用 Windows 窗体 ListView 控件添加和移除项</span><span class="sxs-lookup"><span data-stu-id="8c38a-118">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
