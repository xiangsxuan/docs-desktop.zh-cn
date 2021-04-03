---
title: 如何：枚举系统字体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], enumerating system fonts
- fonts [WPF], enumerating
- system fonts [WPF], enumerating
- enumerating [WPF], system fonts
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
ms.openlocfilehash: 7ea16afa12233ad5f8268ec048bed187f6081299
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973040"
---
# <a name="how-to-enumerate-system-fonts"></a><span data-ttu-id="2d97e-102">如何：枚举系统字体</span><span class="sxs-lookup"><span data-stu-id="2d97e-102">How to: Enumerate System Fonts</span></span>
## <a name="example"></a><span data-ttu-id="2d97e-103">示例</span><span class="sxs-lookup"><span data-stu-id="2d97e-103">Example</span></span>  
 <span data-ttu-id="2d97e-104">下面的示例演示如何枚举系统字体集合中的字体。</span><span class="sxs-lookup"><span data-stu-id="2d97e-104">The following example shows how to enumerate the fonts in the system font collection.</span></span> <span data-ttu-id="2d97e-105">中每个的字体系列 <xref:System.Windows.Media.FontFamily> 名称 <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> 作为项添加到组合框。</span><span class="sxs-lookup"><span data-stu-id="2d97e-105">The font family name of each <xref:System.Windows.Media.FontFamily> within <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> is added as an item to a combo box.</span></span>  
  
 [!code-csharp[TextOverview#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 <span data-ttu-id="2d97e-106">如果同一字体系列的多个版本驻留在同一目录中，则 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 字体枚举将返回最新版本的字体。</span><span class="sxs-lookup"><span data-stu-id="2d97e-106">If multiple versions of the same font family reside in the same directory, the [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] font enumeration returns the most recent version of the font.</span></span> <span data-ttu-id="2d97e-107">如果版本信息不提供解析，则返回具有最新时间戳的字体。</span><span class="sxs-lookup"><span data-stu-id="2d97e-107">If the version information does not provide resolution, the font with latest timestamp is returned.</span></span> <span data-ttu-id="2d97e-108">如果时间戳信息等效，则返回第一个按字母顺序排列的字体文件。</span><span class="sxs-lookup"><span data-stu-id="2d97e-108">If the timestamp information is equivalent, the font file that is first in alphabetical order is returned.</span></span>
