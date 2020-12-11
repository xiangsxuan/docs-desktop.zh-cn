---
title: 全局变换和局部变换
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- matrices [Windows Forms], using transformations
- transformations [Windows Forms], global
- transformations [Windows Forms], local
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
ms.openlocfilehash: f62efb31e95b0797272997fadbc28459579a0de0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970810"
---
# <a name="global-and-local-transformations"></a><span data-ttu-id="28aa9-102">全局变换和局部变换</span><span class="sxs-lookup"><span data-stu-id="28aa9-102">Global and Local Transformations</span></span>
<span data-ttu-id="28aa9-103">全局转换是应用于给定对象绘制的每个项的转换 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="28aa9-103">A global transformation is a transformation that applies to every item drawn by a given <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="28aa9-104">与此相反，本地转换是应用于要绘制的特定项的转换。</span><span class="sxs-lookup"><span data-stu-id="28aa9-104">In contrast, a local transformation is a transformation that applies to a specific item to be drawn.</span></span>  
  
## <a name="global-transformations"></a><span data-ttu-id="28aa9-105">全局转换</span><span class="sxs-lookup"><span data-stu-id="28aa9-105">Global Transformations</span></span>  
 <span data-ttu-id="28aa9-106">若要创建全局转换，请构造 <xref:System.Drawing.Graphics> 对象，然后操作其 <xref:System.Drawing.Graphics.Transform%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="28aa9-106">To create a global transformation, construct a <xref:System.Drawing.Graphics> object, and then manipulate its <xref:System.Drawing.Graphics.Transform%2A> property.</span></span> <span data-ttu-id="28aa9-107"><xref:System.Drawing.Graphics.Transform%2A>属性是一个 <xref:System.Drawing.Drawing2D.Matrix> 对象，因此它可以保存任何仿射转换序列。</span><span class="sxs-lookup"><span data-stu-id="28aa9-107">The <xref:System.Drawing.Graphics.Transform%2A> property is a <xref:System.Drawing.Drawing2D.Matrix> object, so it can hold any sequence of affine transformations.</span></span> <span data-ttu-id="28aa9-108">存储在属性中的转换 <xref:System.Drawing.Graphics.Transform%2A> 称为 "世界转换"。</span><span class="sxs-lookup"><span data-stu-id="28aa9-108">The transformation stored in the <xref:System.Drawing.Graphics.Transform%2A> property is called the world transformation.</span></span> <span data-ttu-id="28aa9-109"><xref:System.Drawing.Graphics>类提供若干用于构建复合世界转换的方法： <xref:System.Drawing.Graphics.MultiplyTransform%2A> 、 <xref:System.Drawing.Graphics.RotateTransform%2A> 、 <xref:System.Drawing.Graphics.ScaleTransform%2A> 和 <xref:System.Drawing.Graphics.TranslateTransform%2A> 。</span><span class="sxs-lookup"><span data-stu-id="28aa9-109">The <xref:System.Drawing.Graphics> class provides several methods for building up a composite world transformation: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A>, and <xref:System.Drawing.Graphics.TranslateTransform%2A>.</span></span> <span data-ttu-id="28aa9-110">下面的示例将一个椭圆绘制两次：在创建世界变换之前和之后。</span><span class="sxs-lookup"><span data-stu-id="28aa9-110">The following example draws an ellipse twice: once before creating a world transformation and once after.</span></span> <span data-ttu-id="28aa9-111">变换首先在 y 方向上按比例为0.5，然后在 x 方向上平移50个单位，然后旋转30度。</span><span class="sxs-lookup"><span data-stu-id="28aa9-111">The transformation first scales by a factor of 0.5 in the y direction, then translates 50 units in the x direction, and then rotates 30 degrees.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 <span data-ttu-id="28aa9-112">下图显示了转换中涉及的矩阵。</span><span class="sxs-lookup"><span data-stu-id="28aa9-112">The following illustration shows the matrices involved in the transformation.</span></span>  
  
 <span data-ttu-id="28aa9-113">![转换](./media/aboutgdip05-art14.gif "AboutGdip05_art14")</span><span class="sxs-lookup"><span data-stu-id="28aa9-113">![Transformations](./media/aboutgdip05-art14.gif "AboutGdip05_art14")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="28aa9-114">在前面的示例中，椭圆围绕坐标系统的原点旋转，后者位于工作区的左上角。</span><span class="sxs-lookup"><span data-stu-id="28aa9-114">In the preceding example, the ellipse is rotated about the origin of the coordinate system, which is at the upper-left corner of the client area.</span></span> <span data-ttu-id="28aa9-115">这产生的结果与围绕椭圆中心旋转椭圆的结果不同。</span><span class="sxs-lookup"><span data-stu-id="28aa9-115">This produces a different result than rotating the ellipse about its own center.</span></span>  
  
## <a name="local-transformations"></a><span data-ttu-id="28aa9-116">本地转换</span><span class="sxs-lookup"><span data-stu-id="28aa9-116">Local Transformations</span></span>  
 <span data-ttu-id="28aa9-117">局部转换应用于要绘制的特定项。</span><span class="sxs-lookup"><span data-stu-id="28aa9-117">A local transformation applies to a specific item to be drawn.</span></span> <span data-ttu-id="28aa9-118">例如， <xref:System.Drawing.Drawing2D.GraphicsPath> 对象具有一个可 <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> 用于转换该路径的数据点的方法。</span><span class="sxs-lookup"><span data-stu-id="28aa9-118">For example, a <xref:System.Drawing.Drawing2D.GraphicsPath> object has a <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> method that allows you to transform the data points of that path.</span></span> <span data-ttu-id="28aa9-119">下面的示例绘制一个没有转换的矩形和一个带有旋转转换的路径。</span><span class="sxs-lookup"><span data-stu-id="28aa9-119">The following example draws a rectangle with no transformation and a path with a rotation transformation.</span></span> <span data-ttu-id="28aa9-120"> (假设没有世界转换。 ) </span><span class="sxs-lookup"><span data-stu-id="28aa9-120">(Assume that there is no world transformation.)</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 <span data-ttu-id="28aa9-121">可以结合使用世界转换和局部转换来实现各种结果。</span><span class="sxs-lookup"><span data-stu-id="28aa9-121">You can combine the world transformation with local transformations to achieve a variety of results.</span></span> <span data-ttu-id="28aa9-122">例如，您可以使用世界变换来修改坐标系统，使用局部转换来旋转和缩放在新坐标系统上绘制的对象。</span><span class="sxs-lookup"><span data-stu-id="28aa9-122">For example, you can use the world transformation to revise the coordinate system and use local transformations to rotate and scale objects drawn on the new coordinate system.</span></span>  
  
 <span data-ttu-id="28aa9-123">假设您想要一个坐标系统，该系统的原点为200像素，距工作区的左边缘和工作区顶部150像素。</span><span class="sxs-lookup"><span data-stu-id="28aa9-123">Suppose you want a coordinate system that has its origin 200 pixels from the left edge of the client area and 150 pixels from the top of the client area.</span></span> <span data-ttu-id="28aa9-124">而且，假设您希望度量单位为像素，而 x 轴指向右侧，y 轴指向上方，则为。</span><span class="sxs-lookup"><span data-stu-id="28aa9-124">Furthermore, assume that you want the unit of measure to be the pixel, with the x-axis pointing to the right and the y-axis pointing up.</span></span> <span data-ttu-id="28aa9-125">默认坐标系统的 y 轴向下移动，因此您需要在水平轴上执行反射。</span><span class="sxs-lookup"><span data-stu-id="28aa9-125">The default coordinate system has the y-axis pointing down, so you need to perform a reflection across the horizontal axis.</span></span> <span data-ttu-id="28aa9-126">下图显示了此类反射的矩阵。</span><span class="sxs-lookup"><span data-stu-id="28aa9-126">The following illustration shows the matrix of such a reflection.</span></span>  
  
 <span data-ttu-id="28aa9-127">![转换](./media/aboutgdip05-art15.gif "AboutGdip05_art15")</span><span class="sxs-lookup"><span data-stu-id="28aa9-127">![Transformations](./media/aboutgdip05-art15.gif "AboutGdip05_art15")</span></span>  
  
 <span data-ttu-id="28aa9-128">接下来，假设你需要向右和150个单位执行平移200单元。</span><span class="sxs-lookup"><span data-stu-id="28aa9-128">Next, assume you need to perform a translation 200 units to the right and 150 units down.</span></span>  
  
 <span data-ttu-id="28aa9-129">下面的示例通过设置对象的世界变换来确定刚刚介绍的坐标系统 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="28aa9-129">The following example establishes the coordinate system just described by setting the world transformation of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 <span data-ttu-id="28aa9-130">下面的代码 (放置在前面示例的末尾) 创建一个路径，该路径包含一个矩形，该矩形的左上角位于新坐标系统的原点。</span><span class="sxs-lookup"><span data-stu-id="28aa9-130">The following code (placed at the end of the preceding example) creates a path that consists of a single rectangle with its lower-left corner at the origin of the new coordinate system.</span></span> <span data-ttu-id="28aa9-131">该矩形只填充一次，不使用本地转换，一次则使用本地转换。</span><span class="sxs-lookup"><span data-stu-id="28aa9-131">The rectangle is filled once with no local transformation and once with a local transformation.</span></span> <span data-ttu-id="28aa9-132">局部转换由2的水平缩放，后跟30度的旋转。</span><span class="sxs-lookup"><span data-stu-id="28aa9-132">The local transformation consists of a horizontal scaling by a factor of 2 followed by a 30-degree rotation.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 <span data-ttu-id="28aa9-133">下图显示了新的坐标系统和两个矩形。</span><span class="sxs-lookup"><span data-stu-id="28aa9-133">The following illustration shows the new coordinate system and the two rectangles.</span></span>  
  
 <span data-ttu-id="28aa9-134">![转换](./media/aboutgdip05-art16.gif "AboutGdip05_art16")</span><span class="sxs-lookup"><span data-stu-id="28aa9-134">![Transformations](./media/aboutgdip05-art16.gif "AboutGdip05_art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28aa9-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28aa9-135">See also</span></span>

- [<span data-ttu-id="28aa9-136">坐标系和坐标转换</span><span class="sxs-lookup"><span data-stu-id="28aa9-136">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="28aa9-137">在托管 GDI+ 中使用变换</span><span class="sxs-lookup"><span data-stu-id="28aa9-137">Using Transformations in Managed GDI+</span></span>](using-transformations-in-managed-gdi.md)
