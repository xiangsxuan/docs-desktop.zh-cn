---
title: 使用 Glyphs 绘制文本
ms.date: 03/30/2017
helpviewer_keywords:
- text [WPF], drawing with Glyphs objects
- Glyphs objects [WPF], drawing text
- typography [WPF], Glyphs objects
ms.assetid: 587ab17e-a419-4ad5-b6da-8933a8e83d97
ms.openlocfilehash: f8f111dc3148ebcd43bb11f80b357db9234322ae
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666051"
---
# <a name="draw-text-using-glyphs"></a><span data-ttu-id="56452-102">使用 Glyphs 绘制文本</span><span class="sxs-lookup"><span data-stu-id="56452-102">Draw Text Using Glyphs</span></span>
<span data-ttu-id="56452-103">本主题说明如何使用低级别 <xref:System.Windows.Documents.Glyphs> 对象在中显示文本 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="56452-103">This topic explains how to use the low-level <xref:System.Windows.Documents.Glyphs> object to display text in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="56452-104">示例</span><span class="sxs-lookup"><span data-stu-id="56452-104">Example</span></span>  
 <span data-ttu-id="56452-105">下面的示例演示如何 <xref:System.Windows.Documents.Glyphs> 在中定义对象的属性 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="56452-105">The following examples show how to define properties for a <xref:System.Windows.Documents.Glyphs> object in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="56452-106"><xref:System.Windows.Documents.Glyphs>对象表示中的的输出 <xref:System.Windows.Media.GlyphRun> [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="56452-106">The <xref:System.Windows.Documents.Glyphs> object represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="56452-107">示例假定本地计算机上的 C:\WINDOWS\Fonts 文件夹中安装了 Arial、Courier New 和 Times New Roman 字体。</span><span class="sxs-lookup"><span data-stu-id="56452-107">The examples assume that the Arial, Courier New, and Times New Roman fonts are installed in the C:\WINDOWS\Fonts folder on the local computer.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="56452-108">此示例演示如何 <xref:System.Windows.Documents.Glyphs> 在中定义对象的其他属性 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="56452-108">This example shows how to define other properties of <xref:System.Windows.Documents.Glyphs> objects in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="56452-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="56452-109">See also</span></span>

- [<span data-ttu-id="56452-110">WPF 中的版式</span><span class="sxs-lookup"><span data-stu-id="56452-110">Typography in WPF</span></span>](typography-in-wpf.md)
