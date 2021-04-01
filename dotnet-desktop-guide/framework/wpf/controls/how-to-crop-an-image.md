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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973721"
---
# <a name="how-to-crop-an-image"></a>如何：裁剪图像

此示例演示如何使用裁剪图像 <xref:System.Windows.Media.Imaging.CroppedBitmap> 。  
  
 <xref:System.Windows.Media.Imaging.CroppedBitmap> 主要在编码要保存到文件的图像的裁剪版本时使用。 若要为显示目的裁剪图像，请参阅 [如何：创建剪辑区域](/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90)) 主题。  
  
## <a name="example"></a>示例  

 下面的 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 示例定义了下面的示例中使用的资源。  
  
 [!code-xaml[imageelementexample#CroppedXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 下面的示例使用 <xref:System.Windows.Media.Imaging.CroppedBitmap> 作为其源创建一个图像。  
  
 [!code-xaml[imageelementexample#CroppedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <xref:System.Windows.Media.Imaging.CroppedBitmap>还可以用作另一个的源 <xref:System.Windows.Media.Imaging.CroppedBitmap> ，链接裁剪。 请注意， <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> 使用相对于源裁剪位图的值，而不使用初始图像的值。  
  
 [!code-xaml[imageelementexample#CroppedXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a>请参阅

- [如何：创建剪辑区域](/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90))
