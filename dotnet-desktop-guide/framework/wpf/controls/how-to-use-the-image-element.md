---
title: 如何：使用 Image 元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Image
- Image control [WPF]
- rendering images [WPF]
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
ms.openlocfilehash: e267aec4d8a1632f77d756bd94d077efcbb2e10c
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972990"
---
# <a name="how-to-use-the-image-element"></a><span data-ttu-id="33fb5-102">如何：使用 Image 元素</span><span class="sxs-lookup"><span data-stu-id="33fb5-102">How to: Use the Image Element</span></span>
<span data-ttu-id="33fb5-103">此示例演示如何使用元素在应用程序中包括图像 <xref:System.Windows.Controls.Image> 。</span><span class="sxs-lookup"><span data-stu-id="33fb5-103">This example shows how to include images in an application by using the <xref:System.Windows.Controls.Image> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33fb5-104">示例</span><span class="sxs-lookup"><span data-stu-id="33fb5-104">Example</span></span>  
 <span data-ttu-id="33fb5-105">下面的示例演示如何呈现宽为 200 像素的图像。</span><span class="sxs-lookup"><span data-stu-id="33fb5-105">The following example shows how to render an image 200 pixels wide.</span></span> <span data-ttu-id="33fb5-106">在此 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 示例中，同时使用特性语法和属性标记语法来定义图像。</span><span class="sxs-lookup"><span data-stu-id="33fb5-106">In this [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] example, both attribute syntax and property tag syntax are used to define the image.</span></span> <span data-ttu-id="33fb5-107">有关特性语法和属性语法的详细信息，请参阅[依赖属性概述](../advanced/dependency-properties-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="33fb5-107">For more information on attribute syntax and property syntax, see [Dependency Properties Overview](../advanced/dependency-properties-overview.md).</span></span> <span data-ttu-id="33fb5-108"><xref:System.Windows.Media.Imaging.BitmapImage>用于定义图像的源数据，并为属性标记语法示例显式定义了。</span><span class="sxs-lookup"><span data-stu-id="33fb5-108">A <xref:System.Windows.Media.Imaging.BitmapImage> is used to define the image's source data and is explicitly defined for the property tag syntax example.</span></span> <span data-ttu-id="33fb5-109">此外，的将 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> 设置为与 <xref:System.Windows.Media.Imaging.BitmapImage> 的相同宽度 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Controls.Image> 。</span><span class="sxs-lookup"><span data-stu-id="33fb5-109">In addition, the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> of the <xref:System.Windows.Media.Imaging.BitmapImage> is set to the same width as the <xref:System.Windows.FrameworkElement.Width%2A> of the <xref:System.Windows.Controls.Image>.</span></span> <span data-ttu-id="33fb5-110">这样做是为了确保呈现图像所使用的内存量最小。</span><span class="sxs-lookup"><span data-stu-id="33fb5-110">This is done to ensure that the minimum amount of memory is used rendering the image.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33fb5-111">通常，如果要指定呈现的图像的大小，请仅指定 <xref:System.Windows.FrameworkElement.Width%2A> 或， <xref:System.Windows.FrameworkElement.Height%2A> 而不是两者。</span><span class="sxs-lookup"><span data-stu-id="33fb5-111">In general, if you want to specify the size of a rendered image, specify only the <xref:System.Windows.FrameworkElement.Width%2A> or the <xref:System.Windows.FrameworkElement.Height%2A> but not both.</span></span> <span data-ttu-id="33fb5-112">如果仅指定一个，则会保持图像的纵横比。</span><span class="sxs-lookup"><span data-stu-id="33fb5-112">If you only specify one, the image's aspect ratio is preserved.</span></span> <span data-ttu-id="33fb5-113">否则，图像可能会出现意外的拉伸或扭曲。</span><span class="sxs-lookup"><span data-stu-id="33fb5-113">Otherwise, the image may unexpectedly appear stretched or warped.</span></span> <span data-ttu-id="33fb5-114">若要控制图像的拉伸行为，请使用 <xref:System.Windows.Controls.Image.Stretch%2A> 和 <xref:System.Windows.Controls.Image.StretchDirection%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="33fb5-114">To control the image's stretching behavior, use the <xref:System.Windows.Controls.Image.Stretch%2A> and <xref:System.Windows.Controls.Image.StretchDirection%2A> properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33fb5-115">当使用或指定映像的大小时 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> ，还应将 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> 或设置 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> 为相同的大小。</span><span class="sxs-lookup"><span data-stu-id="33fb5-115">When you specify the size of an image with either <xref:System.Windows.FrameworkElement.Width%2A> or <xref:System.Windows.FrameworkElement.Height%2A>, you should also set either <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> or <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> to the same respective size.</span></span>  
  
 <span data-ttu-id="33fb5-116"><xref:System.Windows.Controls.Image.Stretch%2A>属性确定如何拉伸图像源以填充图像元素。</span><span class="sxs-lookup"><span data-stu-id="33fb5-116">The <xref:System.Windows.Controls.Image.Stretch%2A> property determines how the image source is stretched to fill the image element.</span></span> <span data-ttu-id="33fb5-117">有关详细信息，请参见 <xref:System.Windows.Media.Stretch> 枚举。</span><span class="sxs-lookup"><span data-stu-id="33fb5-117">For more information, see the <xref:System.Windows.Media.Stretch> enumeration.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="33fb5-118">示例</span><span class="sxs-lookup"><span data-stu-id="33fb5-118">Example</span></span>  
 <span data-ttu-id="33fb5-119">以下示例演示如何使用代码呈现宽度为 200 像素的图像。</span><span class="sxs-lookup"><span data-stu-id="33fb5-119">The following example shows how to render an image 200 pixels wide using code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33fb5-120">设置 <xref:System.Windows.Media.Imaging.BitmapImage> 属性必须在 <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> 和块中完成 <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> 。</span><span class="sxs-lookup"><span data-stu-id="33fb5-120">Setting <xref:System.Windows.Media.Imaging.BitmapImage> properties must be done within a <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> and <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> block.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="33fb5-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="33fb5-121">See also</span></span>

- [<span data-ttu-id="33fb5-122">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="33fb5-122">Imaging Overview</span></span>](../graphics-multimedia/imaging-overview.md)
