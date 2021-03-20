---
title: 存储墨迹
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ISF (Ink Serialized Format)
- storing ink [WPF]
- ink [WPF], storing
- retrieving ink [WPF]
- Ink Serialized Format (ISF)
ms.assetid: a3f6d16b-d682-4680-9965-907332b4d2b8
ms.openlocfilehash: 36d68ce423e493b5cb69c9cf2de7ce9de3d66c0c
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664647"
---
# <a name="storing-ink"></a><span data-ttu-id="e32f3-102">存储墨迹</span><span class="sxs-lookup"><span data-stu-id="e32f3-102">Storing Ink</span></span>
<span data-ttu-id="e32f3-103"><xref:System.Windows.Ink.StrokeCollection.Save%2A>方法支持将墨迹存储为墨迹序列化格式 (ISF) 。</span><span class="sxs-lookup"><span data-stu-id="e32f3-103">The <xref:System.Windows.Ink.StrokeCollection.Save%2A> methods provide support for storing ink as Ink Serialized Format (ISF).</span></span> <span data-ttu-id="e32f3-104">类的构造函数为 <xref:System.Windows.Ink.StrokeCollection> 读取墨迹数据提供支持。</span><span class="sxs-lookup"><span data-stu-id="e32f3-104">Constructors for the <xref:System.Windows.Ink.StrokeCollection> class provide support for reading ink data.</span></span>  
  
## <a name="ink-storage-and-retrieval"></a><span data-ttu-id="e32f3-105">墨迹存储和检索</span><span class="sxs-lookup"><span data-stu-id="e32f3-105">Ink Storage and Retrieval</span></span>  
 <span data-ttu-id="e32f3-106">本部分讨论如何在平台中存储和检索墨迹 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="e32f3-106">This section discusses how to store and retrieve ink in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] platform.</span></span>  
  
 <span data-ttu-id="e32f3-107">下面的示例实现了一个按钮单击事件处理程序，该处理程序向用户显示 "文件保存" 对话框，并将墨迹从 <xref:System.Windows.Controls.InkCanvas> out 保存到文件。</span><span class="sxs-lookup"><span data-stu-id="e32f3-107">The following example implements a button-click event handler that presents the user with a File Save dialog box and saves the ink from an <xref:System.Windows.Controls.InkCanvas> out to a file.</span></span>  
  
 [!code-csharp[DigitalInkTopics#12](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 <span data-ttu-id="e32f3-108">下面的示例实现一个按钮单击事件处理程序，该处理程序向用户显示一个 "文件打开" 对话框，并将文件中的墨迹读取到 <xref:System.Windows.Controls.InkCanvas> 元素中。</span><span class="sxs-lookup"><span data-stu-id="e32f3-108">The following example implements a button-click event handler that presents the user with a File Open dialog box and reads ink from the file into an <xref:System.Windows.Controls.InkCanvas> element.</span></span>  
  
 [!code-csharp[DigitalInkTopics#13](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="e32f3-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="e32f3-109">See also</span></span>

- <xref:System.Windows.Controls.InkCanvas>
- [<span data-ttu-id="e32f3-110">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="e32f3-110">Windows Presentation Foundation</span></span>](../index.md)
