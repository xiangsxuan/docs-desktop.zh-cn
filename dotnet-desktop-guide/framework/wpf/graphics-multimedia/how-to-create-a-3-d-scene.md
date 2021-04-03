---
title: 如何：创建三维场景
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3D
- 3D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 36453894e06e7b59f339c21713449140c17f6851
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973526"
---
# <a name="how-to-create-a-3d-scene"></a><span data-ttu-id="54b72-102">如何：创建三维场景</span><span class="sxs-lookup"><span data-stu-id="54b72-102">How to: Create a 3D Scene</span></span>
<span data-ttu-id="54b72-103">此示例演示如何创建一个三维对象，使其看起来像一张旋转的纸张。</span><span class="sxs-lookup"><span data-stu-id="54b72-103">This example shows how to create a 3D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="54b72-104"><xref:System.Windows.Controls.Viewport3D>和以下组件一起用于创建这个简单的三维场景：</span><span class="sxs-lookup"><span data-stu-id="54b72-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3D scene:</span></span>  
  
- <span data-ttu-id="54b72-105">照相机是使用创建的 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 。</span><span class="sxs-lookup"><span data-stu-id="54b72-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="54b72-106">照相机指定三维场景的哪部分是可查看的。</span><span class="sxs-lookup"><span data-stu-id="54b72-106">The camera specifies what part of the 3D scene is viewable.</span></span>  
  
- <span data-ttu-id="54b72-107">将创建一个网格，以使用的属性指定 (纸) 的3D 对象的形状 <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> <xref:System.Windows.Media.Media3D.GeometryModel3D> 。</span><span class="sxs-lookup"><span data-stu-id="54b72-107">A mesh is created to specify the shape of 3D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
- <span data-ttu-id="54b72-108">在此示例中使用的属性指定要在对象的表面上显示的材料 (线性渐变) <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> <xref:System.Windows.Media.Media3D.GeometryModel3D> 。</span><span class="sxs-lookup"><span data-stu-id="54b72-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
- <span data-ttu-id="54b72-109">将创建一个用来照射对象的光源 <xref:System.Windows.Media.Media3D.DirectionalLight> 。</span><span class="sxs-lookup"><span data-stu-id="54b72-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54b72-110">示例</span><span class="sxs-lookup"><span data-stu-id="54b72-110">Example</span></span>  
 <span data-ttu-id="54b72-111">下面的代码演示如何在 XAML 中创建三维场景。</span><span class="sxs-lookup"><span data-stu-id="54b72-111">The code below shows how to create a 3D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="54b72-112">示例</span><span class="sxs-lookup"><span data-stu-id="54b72-112">Example</span></span>  
 <span data-ttu-id="54b72-113">下面的代码演示如何在程序代码中创建相同的三维场景。</span><span class="sxs-lookup"><span data-stu-id="54b72-113">The code below shows how to create the same 3D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="54b72-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54b72-114">See also</span></span>

- [<span data-ttu-id="54b72-115">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="54b72-115">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
