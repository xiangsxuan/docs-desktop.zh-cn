---
title: 图像处理概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- metadata [WPF], images
- displaying images [WPF]
- Imaging API [WPF]
- image metadata [WPF]
- converting images [WPF]
- encoding image formats [WPF]
- format decoding for images [WPF]
- painting with images [WPF]
- stretching images [WPF]
- images [WPF], about imaging
- format encoding for images [WPF]
- cropping images [WPF]
- decoding image formats [WPF]
- rotating images [WPF]
ms.assetid: 72aad87a-e6f3-4937-94cd-a18b7766e990
ms.openlocfilehash: 3b1e330802a485857e24fd68a7686c238495261c
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668482"
---
# <a name="imaging-overview"></a><span data-ttu-id="f533f-102">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="f533f-102">Imaging Overview</span></span>

<span data-ttu-id="f533f-103">本主题介绍 Microsoft Windows Presentation Foundation 映像组件。</span><span class="sxs-lookup"><span data-stu-id="f533f-103">This topic provides an introduction to the Microsoft Windows Presentation Foundation Imaging Component.</span></span> <span data-ttu-id="f533f-104">WPF 映像使开发人员能够显示、转换和格式化图像。</span><span class="sxs-lookup"><span data-stu-id="f533f-104">WPF Imaging enables developers to display, transform, and format images.</span></span>  

## <a name="wpf-imaging-component"></a><span data-ttu-id="f533f-105">WPF 图像处理组件</span><span class="sxs-lookup"><span data-stu-id="f533f-105">WPF Imaging Component</span></span>  

 <span data-ttu-id="f533f-106">WPF 映像为 Microsoft Windows 中的映像功能提供了重大的改进。</span><span class="sxs-lookup"><span data-stu-id="f533f-106">WPF Imaging provides significant enhancements in imaging capabilities within Microsoft Windows.</span></span> <span data-ttu-id="f533f-107">映像功能（如显示位图或在公共控件上使用图像）先前依赖于 Microsoft Windows 图形设备接口 (GDI) 或 Microsoft Windows GDI + 库。</span><span class="sxs-lookup"><span data-stu-id="f533f-107">Imaging capabilities, such as displaying a bitmap or using an image on a common control were previously reliant upon the Microsoft Windows Graphics Device Interface (GDI) or Microsoft Windows GDI+ libraries.</span></span> <span data-ttu-id="f533f-108">这些 API 提供基线映像功能，但缺乏功能，如支持编解码器扩展性和高保真图像支持。</span><span class="sxs-lookup"><span data-stu-id="f533f-108">These API provide baseline imaging functionality, but lack features such as support for codec extensibility and high fidelity image support.</span></span> <span data-ttu-id="f533f-109">WPF 映像旨在克服 GDI 和 GDI + 的缺点，并提供一组新的 API，用于在应用程序中显示和使用图像。</span><span class="sxs-lookup"><span data-stu-id="f533f-109">WPF Imaging is designed to overcome the shortcomings of GDI and GDI+ and provide a new set of API to display and use images within your applications.</span></span>  
  
 <span data-ttu-id="f533f-110">可通过两种方式访问 WPF 图像处理 API、托管组件和非托管组件。</span><span class="sxs-lookup"><span data-stu-id="f533f-110">There are two ways to access the WPF Imaging API, a managed component and an unmanaged component.</span></span> <span data-ttu-id="f533f-111">非托管组件提供以下功能。</span><span class="sxs-lookup"><span data-stu-id="f533f-111">The unmanaged component provides the following features.</span></span>  
  
- <span data-ttu-id="f533f-112">适用于新的或专用图像格式的扩展性模型。</span><span class="sxs-lookup"><span data-stu-id="f533f-112">Extensibility model for new or proprietary image formats.</span></span>  
  
- <span data-ttu-id="f533f-113">改进了本机映像格式的性能和安全性，包括位图 (BMP) 、联合图像专家组 (JPEG) 、可移植网络图形 (PNG) 、标记图像文件格式 (TIFF) 、Microsoft Windows Media 照片、图形交换格式 (GIF) 和图标 ( .ico) 。</span><span class="sxs-lookup"><span data-stu-id="f533f-113">Improved performance and security on native image formats including bitmap (BMP), Joint Photographics Experts Group (JPEG), Portable Network Graphics (PNG), Tagged Image File Format (TIFF), Microsoft Windows Media Photo, Graphics Interchange Format (GIF), and icon (.ico).</span></span>  
  
- <span data-ttu-id="f533f-114">高位深图像数据最多保留 8 位/通道（32 位/像素）。</span><span class="sxs-lookup"><span data-stu-id="f533f-114">Preservation of high bit-depth image data up to 8 bits per channel (32 bits per pixel).</span></span>  
  
- <span data-ttu-id="f533f-115">非破坏性图像缩放、剪切和旋转。</span><span class="sxs-lookup"><span data-stu-id="f533f-115">Nondestructive image scaling, cropping, and rotations.</span></span>  
  
- <span data-ttu-id="f533f-116">简化的颜色管理。</span><span class="sxs-lookup"><span data-stu-id="f533f-116">Simplified color management.</span></span>  
  
- <span data-ttu-id="f533f-117">对文件内的专用元数据的支持。</span><span class="sxs-lookup"><span data-stu-id="f533f-117">Support for in-file, proprietary metadata.</span></span>  
  
- <span data-ttu-id="f533f-118">托管组件利用非托管的基础结构来提供图像与其他 WPF 功能（如 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 、动画和图形）的无缝集成。</span><span class="sxs-lookup"><span data-stu-id="f533f-118">The managed component utilizes the unmanaged infrastructure to provide seamless integration of images with other WPF features such as [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], animation, and graphics.</span></span> <span data-ttu-id="f533f-119">托管组件还受益于 Windows Presentation Foundation (WPF) 映像编解码器扩展性模型，该模型可在 WPF 应用程序中自动识别新的图像格式。</span><span class="sxs-lookup"><span data-stu-id="f533f-119">The managed component also benefits from the Windows Presentation Foundation (WPF) imaging codec extensibility model which enables automatic recognition of new image formats in WPF applications.</span></span>  
  
 <span data-ttu-id="f533f-120"><xref:System.Windows.Media.Imaging?displayProperty=nameWithType>虽然多个重要类型（如和）驻留在命名空间中 <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.ImageDrawing> <xref:System.Windows.Media?displayProperty=nameWithType> 并 <xref:System.Windows.Controls.Image> 驻留在 <xref:System.Windows.Controls?displayProperty=nameWithType> 命名空间中，但大多数托管 WPF 映像 API 位于命名空间中。</span><span class="sxs-lookup"><span data-stu-id="f533f-120">The majority of the managed WPF Imaging API reside in the <xref:System.Windows.Media.Imaging?displayProperty=nameWithType> namespace, though several important types, such as <xref:System.Windows.Media.ImageBrush> and <xref:System.Windows.Media.ImageDrawing> reside in the <xref:System.Windows.Media?displayProperty=nameWithType> namespace and <xref:System.Windows.Controls.Image> resides in the <xref:System.Windows.Controls?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="f533f-121">本主题提供有关托管组件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="f533f-121">This topic provides additional information about the managed component.</span></span> <span data-ttu-id="f533f-122">有关非托管 API 的详细信息，请参阅 [非托管 WPF 图像处理组件](/windows/desktop/wic/-wic-lh) 文档。</span><span class="sxs-lookup"><span data-stu-id="f533f-122">For more information on the unmanaged API see the [Unmanaged WPF Imaging Component](/windows/desktop/wic/-wic-lh) documentation.</span></span>  
  
<a name="_imageformats"></a>

## <a name="wpf-image-formats"></a><span data-ttu-id="f533f-123">WPF 图像格式</span><span class="sxs-lookup"><span data-stu-id="f533f-123">WPF Image Formats</span></span>  

 <span data-ttu-id="f533f-124">编解码器用于对特定媒体格式进行解码或编码。</span><span class="sxs-lookup"><span data-stu-id="f533f-124">A codec is used to decode or encode a specific media format.</span></span> <span data-ttu-id="f533f-125">WPF 映像包含用于 BMP、JPEG、PNG、TIFF、Windows Media 照片、GIF 和图标图像格式的编解码器。</span><span class="sxs-lookup"><span data-stu-id="f533f-125">WPF Imaging includes a codec  for BMP, JPEG, PNG, TIFF, Windows Media Photo, GIF, and ICON image formats.</span></span> <span data-ttu-id="f533f-126">利用上述每个编解码器，应用程序可以对其各自的图像格式进行解码（ICON 除外）和编码。</span><span class="sxs-lookup"><span data-stu-id="f533f-126">Each of these codecs enable applications to decode and, with the exception of ICON, encode their respective image formats.</span></span>  
  
 <span data-ttu-id="f533f-127"><xref:System.Windows.Media.Imaging.BitmapSource> 是用于对图像进行解码和编码的重要类。</span><span class="sxs-lookup"><span data-stu-id="f533f-127"><xref:System.Windows.Media.Imaging.BitmapSource> is an important class used in the decoding and encoding of images.</span></span> <span data-ttu-id="f533f-128">它是 WPF 图像处理管道的基本构建基块，表示特定大小和分辨率的单个恒定像素集。</span><span class="sxs-lookup"><span data-stu-id="f533f-128">It is the basic building block of the WPF Imaging pipeline and represents a single, constant set of pixels at a certain size and resolution.</span></span> <span data-ttu-id="f533f-129"><xref:System.Windows.Media.Imaging.BitmapSource>可以是多个框架图像的单个帧，也可以是在上执行的转换的结果 <xref:System.Windows.Media.Imaging.BitmapSource> 。</span><span class="sxs-lookup"><span data-stu-id="f533f-129">A <xref:System.Windows.Media.Imaging.BitmapSource> can be an individual frame of a multiple frame image, or it can be the result of a transform performed on a <xref:System.Windows.Media.Imaging.BitmapSource>.</span></span> <span data-ttu-id="f533f-130">它是 WPF 映像（如）中使用的许多主类的父级 <xref:System.Windows.Media.Imaging.BitmapFrame> 。</span><span class="sxs-lookup"><span data-stu-id="f533f-130">It is the parent of many of the primary classes used in WPF imaging such as <xref:System.Windows.Media.Imaging.BitmapFrame>.</span></span>  
  
 <span data-ttu-id="f533f-131"><xref:System.Windows.Media.Imaging.BitmapFrame>用于存储图像格式的实际位图数据。</span><span class="sxs-lookup"><span data-stu-id="f533f-131">A <xref:System.Windows.Media.Imaging.BitmapFrame> is used to store the actual bitmap data of an image format.</span></span> <span data-ttu-id="f533f-132">许多图像格式仅支持单个 <xref:System.Windows.Media.Imaging.BitmapFrame> ，但 GIF 和 TIFF 等格式支持每个图像多个帧。</span><span class="sxs-lookup"><span data-stu-id="f533f-132">Many image formats only support a single <xref:System.Windows.Media.Imaging.BitmapFrame>, although formats such as GIF and TIFF support multiple frames per image.</span></span> <span data-ttu-id="f533f-133">帧由解码器用作输入数据，并传递到编码器以创建图像文件。</span><span class="sxs-lookup"><span data-stu-id="f533f-133">Frames are used by decoders as input data and are passed to encoders to create image files.</span></span>  
  
 <span data-ttu-id="f533f-134">下面的示例演示如何 <xref:System.Windows.Media.Imaging.BitmapFrame> 从创建 <xref:System.Windows.Media.Imaging.BitmapSource> ，然后将其添加到 TIFF 映像。</span><span class="sxs-lookup"><span data-stu-id="f533f-134">The following example demonstrates how a <xref:System.Windows.Media.Imaging.BitmapFrame> is created from a <xref:System.Windows.Media.Imaging.BitmapSource> and then added to a TIFF image.</span></span>  
  
 [!code-csharp[BitmapFrameExample#10](~/samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a><span data-ttu-id="f533f-135">图像格式解码</span><span class="sxs-lookup"><span data-stu-id="f533f-135">Image Format Decoding</span></span>  

 <span data-ttu-id="f533f-136">图像解码是指将某种图像格式转换为可以由系统使用的图像数据。</span><span class="sxs-lookup"><span data-stu-id="f533f-136">Image decoding is the translation of an image format to image data that can be used by the system.</span></span> <span data-ttu-id="f533f-137">然后，此图像数据可以用于显示、处理或编码为其他格式。</span><span class="sxs-lookup"><span data-stu-id="f533f-137">The image data can then be used to display, process, or encode to a different format.</span></span> <span data-ttu-id="f533f-138">根据图像格式选择解码器。</span><span class="sxs-lookup"><span data-stu-id="f533f-138">Decoder selection is based on the image format.</span></span> <span data-ttu-id="f533f-139">自动选择编解码器，除非指定了特定解码器。</span><span class="sxs-lookup"><span data-stu-id="f533f-139">Codec selection is automatic unless a specific decoder is specified.</span></span> <span data-ttu-id="f533f-140">[在 WPF 中显示图像](#_displayingimages)一节中的示例演示了自动解码。</span><span class="sxs-lookup"><span data-stu-id="f533f-140">The examples in the [Displaying Images in WPF](#_displayingimages) section demonstrate automatic decoding.</span></span> <span data-ttu-id="f533f-141">使用非托管 WPF 映像接口开发并向系统注册的自定义格式解码器将自动参与解码器选择。</span><span class="sxs-lookup"><span data-stu-id="f533f-141">Custom format decoders developed using the unmanaged WPF Imaging interfaces and registered with the system automatically participate in decoder selection.</span></span> <span data-ttu-id="f533f-142">这允许在 WPF 应用程序中自动显示自定义格式。</span><span class="sxs-lookup"><span data-stu-id="f533f-142">This allows custom formats to be displayed automatically in WPF applications.</span></span>  
  
 <span data-ttu-id="f533f-143">下面的示例演示如何使用位图解码器来解码 BMP 格式的图像。</span><span class="sxs-lookup"><span data-stu-id="f533f-143">The following example demonstrates the use of a bitmap decoder to decode a BMP format image.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### <a name="image-format-encoding"></a><span data-ttu-id="f533f-144">图像格式编码</span><span class="sxs-lookup"><span data-stu-id="f533f-144">Image Format Encoding</span></span>  

 <span data-ttu-id="f533f-145">图像编码是指将图像数据转换为特定的图像格式。</span><span class="sxs-lookup"><span data-stu-id="f533f-145">Image encoding is the translation of image data to a specific image format.</span></span> <span data-ttu-id="f533f-146">然后，已编码的图像数据可以用于创建新的图像文件。</span><span class="sxs-lookup"><span data-stu-id="f533f-146">The encoded image data can then be used to create new image files.</span></span> <span data-ttu-id="f533f-147">WPF 映像提供上述每个图像格式的编码器。</span><span class="sxs-lookup"><span data-stu-id="f533f-147">WPF Imaging provides encoders for each of the image formats described above.</span></span>  
  
 <span data-ttu-id="f533f-148">以下示例演示使用编码器保存一个新创建的位图图像。</span><span class="sxs-lookup"><span data-stu-id="f533f-148">The following example demonstrates the use of an encoder to save a newly created bitmap image.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>

## <a name="displaying-images-in-wpf"></a><span data-ttu-id="f533f-149">在 WPF 中显示图像</span><span class="sxs-lookup"><span data-stu-id="f533f-149">Displaying Images in WPF</span></span>  

 <span data-ttu-id="f533f-150">有多种方法可在 Windows Presentation Foundation (WPF) 应用程序中显示图像。</span><span class="sxs-lookup"><span data-stu-id="f533f-150">There are several ways to display an image in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="f533f-151">图像可以使用 <xref:System.Windows.Controls.Image> 控件显示，使用在视觉对象上绘制， <xref:System.Windows.Media.ImageBrush> 或使用绘制 <xref:System.Windows.Media.ImageDrawing> 。</span><span class="sxs-lookup"><span data-stu-id="f533f-151">Images can be displayed using an <xref:System.Windows.Controls.Image> control, painted on a visual using an <xref:System.Windows.Media.ImageBrush>, or drawn using an <xref:System.Windows.Media.ImageDrawing>.</span></span>  
  
### <a name="using-the-image-control"></a><span data-ttu-id="f533f-152">使用 Image 控件</span><span class="sxs-lookup"><span data-stu-id="f533f-152">Using the Image Control</span></span>  

 <span data-ttu-id="f533f-153"><xref:System.Windows.Controls.Image> 是框架元素，是在应用程序中显示图像的主要方式。</span><span class="sxs-lookup"><span data-stu-id="f533f-153"><xref:System.Windows.Controls.Image> is a framework element and the primary way to display images in applications.</span></span> <span data-ttu-id="f533f-154">在中 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ， <xref:System.Windows.Controls.Image> 可以通过两种方式使用：属性语法或属性语法。</span><span class="sxs-lookup"><span data-stu-id="f533f-154">In [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], <xref:System.Windows.Controls.Image> can be used in two ways; attribute syntax or property syntax.</span></span> <span data-ttu-id="f533f-155">以下示例演示如何使用特性语法或属性标记语法来呈现宽度为 200 像素的图像。</span><span class="sxs-lookup"><span data-stu-id="f533f-155">The following example shows how to render an image 200 pixels wide using both attribute syntax and property tag syntax.</span></span> <span data-ttu-id="f533f-156">有关特性语法和属性语法的详细信息，请参阅[依赖属性概述](../advanced/dependency-properties-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f533f-156">For more information on attribute syntax and property syntax, see [Dependency Properties Overview](../advanced/dependency-properties-overview.md).</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 <span data-ttu-id="f533f-157">许多示例使用 <xref:System.Windows.Media.Imaging.BitmapImage> 对象来引用映像文件。</span><span class="sxs-lookup"><span data-stu-id="f533f-157">Many of the examples use a <xref:System.Windows.Media.Imaging.BitmapImage> object to reference an image file.</span></span> <span data-ttu-id="f533f-158"><xref:System.Windows.Media.Imaging.BitmapImage> 是一种专用化的 <xref:System.Windows.Media.Imaging.BitmapSource> ，它针对加载进行了优化 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ，并且是一种将图像显示为控件的简单方法 <xref:System.Windows.Controls.Image.Source%2A> <xref:System.Windows.Controls.Image> 。</span><span class="sxs-lookup"><span data-stu-id="f533f-158"><xref:System.Windows.Media.Imaging.BitmapImage> is a specialized <xref:System.Windows.Media.Imaging.BitmapSource> that is optimized for [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] loading and is an easy way to display images as the <xref:System.Windows.Controls.Image.Source%2A> of an <xref:System.Windows.Controls.Image> control.</span></span>  
  
 <span data-ttu-id="f533f-159">以下示例演示如何使用代码呈现宽度为 200 像素的图像。</span><span class="sxs-lookup"><span data-stu-id="f533f-159">The following example shows how to render an image 200 pixels wide using code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f533f-160"><xref:System.Windows.Media.Imaging.BitmapImage> 实现 <xref:System.ComponentModel.ISupportInitialize> 接口，以优化多个属性的初始化。</span><span class="sxs-lookup"><span data-stu-id="f533f-160"><xref:System.Windows.Media.Imaging.BitmapImage> implements the <xref:System.ComponentModel.ISupportInitialize> interface to optimize initialization on multiple properties.</span></span> <span data-ttu-id="f533f-161">只能在对象初始化过程中进行属性更改。</span><span class="sxs-lookup"><span data-stu-id="f533f-161">Property changes can only occur during object initialization.</span></span> <span data-ttu-id="f533f-162">调用 <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> 以发送初始化已开始的信号，并 <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> 通知初始化已完成。</span><span class="sxs-lookup"><span data-stu-id="f533f-162">Call <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> to signal that initialization has begun and <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> to signal that initialization has completed.</span></span> <span data-ttu-id="f533f-163">初始化后，将忽略所做的属性更改。</span><span class="sxs-lookup"><span data-stu-id="f533f-163">Once initialized, property changes are ignored.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a><span data-ttu-id="f533f-164">旋转、转换和剪切图像</span><span class="sxs-lookup"><span data-stu-id="f533f-164">Rotating, Converting, and Cropping Images</span></span>  

 <span data-ttu-id="f533f-165">WPF 使用户能够通过使用 <xref:System.Windows.Media.Imaging.BitmapImage> 或的其他 <xref:System.Windows.Media.Imaging.BitmapSource> 对象（如或）来转换图像 <xref:System.Windows.Media.Imaging.CroppedBitmap> <xref:System.Windows.Media.Imaging.FormatConvertedBitmap> 。</span><span class="sxs-lookup"><span data-stu-id="f533f-165">WPF enables users to transform images by using properties of <xref:System.Windows.Media.Imaging.BitmapImage> or by using additional <xref:System.Windows.Media.Imaging.BitmapSource> objects such as <xref:System.Windows.Media.Imaging.CroppedBitmap> or <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>.</span></span> <span data-ttu-id="f533f-166">上述图像转换可以缩放或旋转图像、更改图像的像素格式或剪切图像。</span><span class="sxs-lookup"><span data-stu-id="f533f-166">These image transformations can scale or rotate an image, change the pixel format of an image, or crop an image.</span></span>  
  
 <span data-ttu-id="f533f-167">使用的属性执行图像旋转 <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> <xref:System.Windows.Media.Imaging.BitmapImage> 。</span><span class="sxs-lookup"><span data-stu-id="f533f-167">Image rotations are performed using the <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> property of <xref:System.Windows.Media.Imaging.BitmapImage>.</span></span> <span data-ttu-id="f533f-168">只能以 90 度为增量进行旋转。</span><span class="sxs-lookup"><span data-stu-id="f533f-168">Rotations can only be done in 90 degree increments.</span></span> <span data-ttu-id="f533f-169">在以下示例中，图像旋转了 90 度。</span><span class="sxs-lookup"><span data-stu-id="f533f-169">In the following example, an image is rotated 90 degrees.</span></span>  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 <span data-ttu-id="f533f-170">将图像转换为其他像素格式（如灰度）使用完成 <xref:System.Windows.Media.Imaging.FormatConvertedBitmap> 。</span><span class="sxs-lookup"><span data-stu-id="f533f-170">Converting an image to a different pixel format such as grayscale is done using <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>.</span></span> <span data-ttu-id="f533f-171">在下面的示例中，将图像转换为 <xref:System.Windows.Media.PixelFormats.Gray4%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f533f-171">In the following examples, an image is converted to <xref:System.Windows.Media.PixelFormats.Gray4%2A>.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 <span data-ttu-id="f533f-172">若要裁剪图像， <xref:System.Windows.UIElement.Clip%2A> <xref:System.Windows.Controls.Image> 可以使用或的属性 <xref:System.Windows.Media.Imaging.CroppedBitmap> 。</span><span class="sxs-lookup"><span data-stu-id="f533f-172">To crop an image, either the <xref:System.Windows.UIElement.Clip%2A> property of <xref:System.Windows.Controls.Image> or <xref:System.Windows.Media.Imaging.CroppedBitmap> can be used.</span></span> <span data-ttu-id="f533f-173">通常，如果只想显示部分图像，则 <xref:System.Windows.UIElement.Clip%2A> 应使用。</span><span class="sxs-lookup"><span data-stu-id="f533f-173">Typically, if you just want to display a portion of an image, <xref:System.Windows.UIElement.Clip%2A> should be used.</span></span> <span data-ttu-id="f533f-174">如果需要编码并保存裁剪后的图像，则 <xref:System.Windows.Media.Imaging.CroppedBitmap> 应使用。</span><span class="sxs-lookup"><span data-stu-id="f533f-174">If you need to encode and save a cropped image, the <xref:System.Windows.Media.Imaging.CroppedBitmap> should be used.</span></span> <span data-ttu-id="f533f-175">在下面的示例中，使用剪辑属性裁剪图像 <xref:System.Windows.Media.EllipseGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="f533f-175">In the following example, an image is cropped using the Clip property using an <xref:System.Windows.Media.EllipseGeometry>.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a><span data-ttu-id="f533f-176">拉伸图像</span><span class="sxs-lookup"><span data-stu-id="f533f-176">Stretching Images</span></span>  

 <span data-ttu-id="f533f-177"><xref:System.Windows.Controls.Image.Stretch%2A>属性控制如何拉伸图像以填充其容器。</span><span class="sxs-lookup"><span data-stu-id="f533f-177">The <xref:System.Windows.Controls.Image.Stretch%2A> property controls how an image is stretched to fill its container.</span></span> <span data-ttu-id="f533f-178"><xref:System.Windows.Controls.Image.Stretch%2A>属性接受由枚举定义的下列值 <xref:System.Windows.Media.Stretch> ：</span><span class="sxs-lookup"><span data-stu-id="f533f-178">The <xref:System.Windows.Controls.Image.Stretch%2A> property accepts the following values, defined by the <xref:System.Windows.Media.Stretch> enumeration:</span></span>  
  
- <span data-ttu-id="f533f-179"><xref:System.Windows.Media.Stretch.None>：不拉伸图像来填充输出区域。</span><span class="sxs-lookup"><span data-stu-id="f533f-179"><xref:System.Windows.Media.Stretch.None>: The image is not stretched to fill the output area.</span></span> <span data-ttu-id="f533f-180">如果图像比输出区域大，将图像绘制到输出区域，剪裁掉无法容纳的内容。</span><span class="sxs-lookup"><span data-stu-id="f533f-180">If the image is larger than the output area, the image is drawn to the output area, clipping what does not fit.</span></span>  
  
- <span data-ttu-id="f533f-181"><xref:System.Windows.Media.Stretch.Fill>：缩放图像以适合输出区域。</span><span class="sxs-lookup"><span data-stu-id="f533f-181"><xref:System.Windows.Media.Stretch.Fill>: The image is scaled to fit the output area.</span></span> <span data-ttu-id="f533f-182">由于图像的高度和宽度独立进行缩放，因此图像的原始纵横比可能不会保留。</span><span class="sxs-lookup"><span data-stu-id="f533f-182">Because the image height and width are scaled independently, the original aspect ratio of the image might not be preserved.</span></span> <span data-ttu-id="f533f-183">也就是说，为了完全填充输出容器，图像可能会扭曲。</span><span class="sxs-lookup"><span data-stu-id="f533f-183">That is, the image might be warped in order to completely fill the output container.</span></span>  
  
- <span data-ttu-id="f533f-184"><xref:System.Windows.Media.Stretch.Uniform>：缩放图像，使其完全适合输出区域。</span><span class="sxs-lookup"><span data-stu-id="f533f-184"><xref:System.Windows.Media.Stretch.Uniform>: The image is scaled so that it fits completely within the output area.</span></span> <span data-ttu-id="f533f-185">图像的纵横比会保留。</span><span class="sxs-lookup"><span data-stu-id="f533f-185">The image's aspect ratio is preserved.</span></span>  
  
- <span data-ttu-id="f533f-186"><xref:System.Windows.Media.Stretch.UniformToFill>：缩放图像，使其完全填充输出区域，同时保留图像的原始纵横比。</span><span class="sxs-lookup"><span data-stu-id="f533f-186"><xref:System.Windows.Media.Stretch.UniformToFill>: The image is scaled so that it completely fills the output area while preserving the image's original aspect ratio.</span></span>  
  
 <span data-ttu-id="f533f-187">下面的示例将每个可用枚举应用于 <xref:System.Windows.Media.Stretch> <xref:System.Windows.Controls.Image> 。</span><span class="sxs-lookup"><span data-stu-id="f533f-187">The following example applies each of the available <xref:System.Windows.Media.Stretch> enumerations to an <xref:System.Windows.Controls.Image>.</span></span>  
  
 <span data-ttu-id="f533f-188">下图显示了该示例的输出，并演示了 <xref:System.Windows.Controls.Image.Stretch%2A> 应用于图像时不同设置的影响。</span><span class="sxs-lookup"><span data-stu-id="f533f-188">The following image shows the output from the example and demonstrates the affect the different <xref:System.Windows.Controls.Image.Stretch%2A> settings have when applied to an image.</span></span>  
  
 <span data-ttu-id="f533f-189">![不同的 TileBrush 拉伸设置](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")</span><span class="sxs-lookup"><span data-stu-id="f533f-189">![Different TileBrush Stretch settings](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")</span></span>  
<span data-ttu-id="f533f-190">不同的拉伸设置</span><span class="sxs-lookup"><span data-stu-id="f533f-190">Different stretch settings</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a><span data-ttu-id="f533f-191">使用图像进行绘制</span><span class="sxs-lookup"><span data-stu-id="f533f-191">Painting with Images</span></span>  

 <span data-ttu-id="f533f-192">通过使用绘制，还可以在应用程序中显示图像 <xref:System.Windows.Media.Brush> 。</span><span class="sxs-lookup"><span data-stu-id="f533f-192">Images can also be displayed in an application by painting with a <xref:System.Windows.Media.Brush>.</span></span> <span data-ttu-id="f533f-193">借助画笔，可以利用任意内容（从简单的纯色到复杂的图案和图像集）绘制 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 对象。</span><span class="sxs-lookup"><span data-stu-id="f533f-193">Brushes enable you to paint [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] objects with anything from simple, solid colors to complex sets of patterns and images.</span></span> <span data-ttu-id="f533f-194">若要使用图像进行绘制，请使用 <xref:System.Windows.Media.ImageBrush> 。</span><span class="sxs-lookup"><span data-stu-id="f533f-194">To paint with images, use an <xref:System.Windows.Media.ImageBrush>.</span></span> <span data-ttu-id="f533f-195"><xref:System.Windows.Media.ImageBrush>是将 <xref:System.Windows.Media.TileBrush> 其内容定义为位图图像的类型。</span><span class="sxs-lookup"><span data-stu-id="f533f-195">An <xref:System.Windows.Media.ImageBrush> is a type of <xref:System.Windows.Media.TileBrush> that defines its content as a bitmap image.</span></span> <span data-ttu-id="f533f-196"><xref:System.Windows.Media.ImageBrush>显示单个图像，由其 <xref:System.Windows.Media.ImageBrush.ImageSource%2A> 属性指定。</span><span class="sxs-lookup"><span data-stu-id="f533f-196">An <xref:System.Windows.Media.ImageBrush> displays a single image, which is specified by its <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property.</span></span> <span data-ttu-id="f533f-197">可以控制图像的拉伸、对齐和平铺方式，从而防止失真并生成图案和其他效果。</span><span class="sxs-lookup"><span data-stu-id="f533f-197">You can control how the image is stretched, aligned, and tiled, enabling you to prevent distortion and produce patterns and other effects.</span></span> <span data-ttu-id="f533f-198">下图显示了可使用实现的一些效果 <xref:System.Windows.Media.ImageBrush> 。</span><span class="sxs-lookup"><span data-stu-id="f533f-198">The following illustration shows some effects that can be achieved with an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 <span data-ttu-id="f533f-199">![ImageBrush 输出示例](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")</span><span class="sxs-lookup"><span data-stu-id="f533f-199">![ImageBrush output examples](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")</span></span>  
<span data-ttu-id="f533f-200">图像画笔可以填充形状、控件、文本等</span><span class="sxs-lookup"><span data-stu-id="f533f-200">Image brushes can fill shapes, controls, text, and more</span></span>  
  
 <span data-ttu-id="f533f-201">下面的示例演示如何使用图像绘制按钮的背景 <xref:System.Windows.Media.ImageBrush> 。</span><span class="sxs-lookup"><span data-stu-id="f533f-201">The following example demonstrates how to paint the background of a button with an image using an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 [!code-xaml[UsingImageBrush#4](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 <span data-ttu-id="f533f-202">有关和绘制图像的其他信息， <xref:System.Windows.Media.ImageBrush> 请参阅 [通过图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)。</span><span class="sxs-lookup"><span data-stu-id="f533f-202">For additional information about <xref:System.Windows.Media.ImageBrush> and painting images see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
<a name="_metadata"></a>

## <a name="image-metadata"></a><span data-ttu-id="f533f-203">图像元数据</span><span class="sxs-lookup"><span data-stu-id="f533f-203">Image Metadata</span></span>  

 <span data-ttu-id="f533f-204">某些图像文件包含用于描述文件的内容或特征的元数据。</span><span class="sxs-lookup"><span data-stu-id="f533f-204">Some image files contain metadata that describes the content or the characteristics of the file.</span></span> <span data-ttu-id="f533f-205">例如，大多数数数字相机创建的图像中包含用于捕获该图像的照相机品牌和型号的元数据。</span><span class="sxs-lookup"><span data-stu-id="f533f-205">For example, most digital cameras create images that contain metadata about the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="f533f-206">每个图像格式处理元数据的方式不同，但 WPF 映像为每种支持的图像格式的元数据提供了一种统一的方式。</span><span class="sxs-lookup"><span data-stu-id="f533f-206">Each image format handles metadata differently but WPF Imaging provides a uniform way of storing and retrieving metadata for each supported image format.</span></span>  
  
 <span data-ttu-id="f533f-207">通过对象的属性提供对元数据的访问 <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> <xref:System.Windows.Media.Imaging.BitmapSource> 。</span><span class="sxs-lookup"><span data-stu-id="f533f-207">Access to metadata is provided through the <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> property of a <xref:System.Windows.Media.Imaging.BitmapSource> object.</span></span> <span data-ttu-id="f533f-208"><xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> 返回一个 <xref:System.Windows.Media.Imaging.BitmapMetadata> 对象，该对象包含图像所包含的所有元数据。</span><span class="sxs-lookup"><span data-stu-id="f533f-208"><xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> returns a <xref:System.Windows.Media.Imaging.BitmapMetadata> object that includes all the metadata contained by the image.</span></span> <span data-ttu-id="f533f-209">此数据可以位于一个元数据架构中或位于不同架构的组合中。</span><span class="sxs-lookup"><span data-stu-id="f533f-209">This data may be in one metadata schema or a combination of different schemes.</span></span> <span data-ttu-id="f533f-210">WPF 映像支持以下图像元数据架构：可交换 image file (Exif) ，文本 (PNG 文本数据) ，图像文件目录 (IFD) ，国际新闻电信委员会 (IPTC) ，以及可扩展的元数据平台 (XMP) 。</span><span class="sxs-lookup"><span data-stu-id="f533f-210">WPF Imaging supports the following image metadata schemas: Exchangeable image file (Exif), tEXt (PNG Textual Data), image file directory (IFD), International Press Telecommunications Council (IPTC), and Extensible Metadata Platform (XMP).</span></span>  
  
 <span data-ttu-id="f533f-211">为了简化读取元数据的过程， <xref:System.Windows.Media.Imaging.BitmapMetadata> 提供了多个可以轻松访问的命名属性，如 <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A> 、 <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A> 和 <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f533f-211">In order to simplify the process of reading metadata, <xref:System.Windows.Media.Imaging.BitmapMetadata> provides several named properties that can be easily accessed such as <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>, <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A>, and <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>.</span></span> <span data-ttu-id="f533f-212">许多命名属性还可以用于编写元数据。</span><span class="sxs-lookup"><span data-stu-id="f533f-212">Many of these named properties can also be used to write metadata.</span></span> <span data-ttu-id="f533f-213">元数据查询读取器提供对读取元数据的其他支持。</span><span class="sxs-lookup"><span data-stu-id="f533f-213">Additional support for reading metadata is provided by the metadata query reader.</span></span> <span data-ttu-id="f533f-214"><xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A>方法用于检索元数据查询读取器，方法是提供一个字符串查询，如 *"/app1/exif/"*。</span><span class="sxs-lookup"><span data-stu-id="f533f-214">The <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> method is used to retrieve a metadata query reader by providing a string query such as *"/app1/exif/"*.</span></span> <span data-ttu-id="f533f-215">在下面的示例中， <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> 用于获取存储在 *"/Text/Description"* 位置中的文本。</span><span class="sxs-lookup"><span data-stu-id="f533f-215">In the following example, <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> is used to obtain the text stored in the *"/Text/Description"* location.</span></span>  
  
 [!code-cpp[BitmapMetadata#GetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 <span data-ttu-id="f533f-216">若要编写元数据，请使用元数据查询编写器。</span><span class="sxs-lookup"><span data-stu-id="f533f-216">To write metadata, a metadata query writer is used.</span></span> <span data-ttu-id="f533f-217"><xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> 获取查询编写器并设置所需的值。</span><span class="sxs-lookup"><span data-stu-id="f533f-217"><xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> obtains the query writer and sets the desired value.</span></span> <span data-ttu-id="f533f-218">在下面的示例中， <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> 用于写入 *"/Text/Description"* 位置中存储的文本。</span><span class="sxs-lookup"><span data-stu-id="f533f-218">In the following example, <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> is used to write the text stored in the *"/Text/Description"* location.</span></span>  
  
 [!code-cpp[BitmapMetadata#SetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>

## <a name="codec-extensibility"></a><span data-ttu-id="f533f-219">编解码器扩展性</span><span class="sxs-lookup"><span data-stu-id="f533f-219">Codec Extensibility</span></span>  

 <span data-ttu-id="f533f-220">WPF 映像的核心功能是用于新映像编解码器的扩展性模型。</span><span class="sxs-lookup"><span data-stu-id="f533f-220">A core feature of WPF Imaging is the extensibility model for new image codecs.</span></span> <span data-ttu-id="f533f-221">这些非托管接口使编解码器开发人员能够将编解码器与 WPF 集成，因此，WPF 应用程序可以自动使用新的图像格式。</span><span class="sxs-lookup"><span data-stu-id="f533f-221">These unmanaged interfaces enable codec developers to integrate codecs with WPF so new image formats can automatically be used by WPF applications.</span></span>  
  
 <span data-ttu-id="f533f-222">有关扩展性 API 的示例，请参阅 [Win32 示例编解码器](https://github.com/microsoft/WPF-Samples/tree/master/Graphics/AITCodec)。</span><span class="sxs-lookup"><span data-stu-id="f533f-222">For a sample of the extensibility API, see the [Win32 Sample Codec](https://github.com/microsoft/WPF-Samples/tree/master/Graphics/AITCodec).</span></span> <span data-ttu-id="f533f-223">此示例演示如何为自定义图像格式创建解码器和编码器。</span><span class="sxs-lookup"><span data-stu-id="f533f-223">This sample demonstrates how to create a decoder and encoder for a custom image format.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f533f-224">编解码器必须进行数字签名，系统才能够识别它。</span><span class="sxs-lookup"><span data-stu-id="f533f-224">The codec must be digitally signed for the system to recognize it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f533f-225">请参阅</span><span class="sxs-lookup"><span data-stu-id="f533f-225">See also</span></span>

- <xref:System.Windows.Media.Imaging.BitmapSource>
- <xref:System.Windows.Media.Imaging.BitmapImage>
- <xref:System.Windows.Controls.Image>
- <xref:System.Windows.Media.Imaging.BitmapMetadata>
- [<span data-ttu-id="f533f-226">二维图形和图像处理</span><span class="sxs-lookup"><span data-stu-id="f533f-226">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="f533f-227">Win32 示例编解码器</span><span class="sxs-lookup"><span data-stu-id="f533f-227">Win32 Sample Codec</span></span>](https://github.com/microsoft/WPF-Samples/tree/master/Graphics/AITCodec)
