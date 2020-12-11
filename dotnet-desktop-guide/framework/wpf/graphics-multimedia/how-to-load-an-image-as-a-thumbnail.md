---
title: 如何：将图像作为缩略图加载
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
ms.openlocfilehash: a5b2f4b7de52203ded711e9e829886a5c25c6067
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972679"
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a><span data-ttu-id="79081-102">如何：将图像作为缩略图加载</span><span class="sxs-lookup"><span data-stu-id="79081-102">How to: Load an Image as a Thumbnail</span></span>
<span data-ttu-id="79081-103">下面的示例演示如何以 <xref:System.Windows.Controls.Image> 缩略图的形式加载以节省应用程序内存。</span><span class="sxs-lookup"><span data-stu-id="79081-103">The following examples show how to load an <xref:System.Windows.Controls.Image> as a thumbnail to conserve application memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79081-104">示例</span><span class="sxs-lookup"><span data-stu-id="79081-104">Example</span></span>  
 <span data-ttu-id="79081-105">下面的示例 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> 在中设置的属性 <xref:System.Windows.Media.Imaging.BitmapImage> [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 以减少加载图像所需的内存。</span><span class="sxs-lookup"><span data-stu-id="79081-105">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] to reduce the memory required to load the image.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="79081-106">示例</span><span class="sxs-lookup"><span data-stu-id="79081-106">Example</span></span>  
 <span data-ttu-id="79081-107">下面的示例 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> <xref:System.Windows.Media.Imaging.BitmapImage> 在代码中设置的属性以减少加载图像所需的内存。</span><span class="sxs-lookup"><span data-stu-id="79081-107">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in code to reduce the memory required to load the image.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="79081-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79081-108">See also</span></span>

- [<span data-ttu-id="79081-109">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="79081-109">Imaging Overview</span></span>](imaging-overview.md)
