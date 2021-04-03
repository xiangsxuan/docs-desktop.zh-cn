---
title: 如何：定义 GroupBox 模板
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: f04e4a7e3feb4bd7c5dac1b4127d48923fb7ea62
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973718"
---
# <a name="how-to-define-a-groupbox-template"></a><span data-ttu-id="902db-102">如何：定义 GroupBox 模板</span><span class="sxs-lookup"><span data-stu-id="902db-102">How to: Define a GroupBox Template</span></span>

<span data-ttu-id="902db-103">此示例演示如何为控件创建模板 <xref:System.Windows.Controls.GroupBox> 。</span><span class="sxs-lookup"><span data-stu-id="902db-103">This example shows how to create a template for a <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="902db-104">示例</span><span class="sxs-lookup"><span data-stu-id="902db-104">Example</span></span>  

 <span data-ttu-id="902db-105">下面的示例 <xref:System.Windows.Controls.GroupBox> 通过使用布局控件定义控件模板 <xref:System.Windows.Controls.Grid> 。</span><span class="sxs-lookup"><span data-stu-id="902db-105">The following example defines a <xref:System.Windows.Controls.GroupBox> control template by using a <xref:System.Windows.Controls.Grid> control for layout.</span></span> <span data-ttu-id="902db-106">模板使用 <xref:System.Windows.Controls.BorderGapMaskConverter> 来定义的边框， <xref:System.Windows.Controls.GroupBox> 以使边框不会遮盖 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 内容。</span><span class="sxs-lookup"><span data-stu-id="902db-106">The template uses a <xref:System.Windows.Controls.BorderGapMaskConverter> to define the border of the <xref:System.Windows.Controls.GroupBox> so that the border does not obscure the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> content.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a><span data-ttu-id="902db-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="902db-107">See also</span></span>

- <xref:System.Windows.Controls.GroupBox>
- <span data-ttu-id="902db-108">[如何：创建分组框](/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="902db-108">[How to: Create a GroupBox](/previous-versions/dotnet/netframework-3.5/ms748321(v=vs.90))</span></span>
