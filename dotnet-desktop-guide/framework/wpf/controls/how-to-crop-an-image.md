---
title: 如何：裁剪图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
ms.openlocfilehash: 09a8dd01dec8bf93be627520b1c4700263427411
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973721"
---
# <a name="how-to-crop-an-image"></a><span data-ttu-id="3a3da-102">如何：裁剪图像</span><span class="sxs-lookup"><span data-stu-id="3a3da-102">How to: Crop an Image</span></span>

<span data-ttu-id="3a3da-103">此示例演示如何使用裁剪图像 <xref:System.Windows.Media.Imaging.CroppedBitmap> 。</span><span class="sxs-lookup"><span data-stu-id="3a3da-103">This example shows how to crop an image using <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span></span>  
  
 <span data-ttu-id="3a3da-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> 主要在编码要保存到文件的图像的裁剪版本时使用。</span><span class="sxs-lookup"><span data-stu-id="3a3da-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> is primarily used when encoding a cropped version of an image to save out to a file.</span></span> <span data-ttu-id="3a3da-105">若要为显示目的裁剪图像，请参阅 [如何：创建剪辑区域](/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90)) 主题。</span><span class="sxs-lookup"><span data-stu-id="3a3da-105">To crop an image for display purposes see the [How to: Create a Clip Region](/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90)) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a3da-106">示例</span><span class="sxs-lookup"><span data-stu-id="3a3da-106">Example</span></span>  

 <span data-ttu-id="3a3da-107">下面的 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 示例定义了下面的示例中使用的资源。</span><span class="sxs-lookup"><span data-stu-id="3a3da-107">The following [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] defines resources used within the samples below.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 <span data-ttu-id="3a3da-108">下面的示例使用 <xref:System.Windows.Media.Imaging.CroppedBitmap> 作为其源创建一个图像。</span><span class="sxs-lookup"><span data-stu-id="3a3da-108">The following example creates an image using a <xref:System.Windows.Media.Imaging.CroppedBitmap> as its source.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <span data-ttu-id="3a3da-109"><xref:System.Windows.Media.Imaging.CroppedBitmap>还可以用作另一个的源 <xref:System.Windows.Media.Imaging.CroppedBitmap> ，链接裁剪。</span><span class="sxs-lookup"><span data-stu-id="3a3da-109">The <xref:System.Windows.Media.Imaging.CroppedBitmap> can also be used as the source of another <xref:System.Windows.Media.Imaging.CroppedBitmap>, chaining the cropping.</span></span> <span data-ttu-id="3a3da-110">请注意， <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> 使用相对于源裁剪位图的值，而不使用初始图像的值。</span><span class="sxs-lookup"><span data-stu-id="3a3da-110">Note that the <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> uses values that are relative to the source cropped bitmap and not the initial image.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a><span data-ttu-id="3a3da-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a3da-111">See also</span></span>

- <span data-ttu-id="3a3da-112">[如何：创建剪辑区域](/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="3a3da-112">[How to: Create a Clip Region](/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90))</span></span>
