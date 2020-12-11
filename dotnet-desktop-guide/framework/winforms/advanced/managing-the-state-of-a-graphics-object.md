---
title: 管理 Graphics 对象的状态
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
ms.openlocfilehash: d1e7e6eac775ca779fb68605adcc9bc2b9915e49
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971377"
---
# <a name="managing-the-state-of-a-graphics-object"></a><span data-ttu-id="f1697-102">管理 Graphics 对象的状态</span><span class="sxs-lookup"><span data-stu-id="f1697-102">Managing the State of a Graphics Object</span></span>
<span data-ttu-id="f1697-103"><xref:System.Drawing.Graphics>类是 GDI + 的核心。</span><span class="sxs-lookup"><span data-stu-id="f1697-103">The <xref:System.Drawing.Graphics> class is at the heart of GDI+.</span></span> <span data-ttu-id="f1697-104">若要绘制任何内容，可以获取 <xref:System.Drawing.Graphics> 对象，设置其属性，并调用其方法 <xref:System.Drawing.Graphics.DrawLine%2A> 、 <xref:System.Drawing.Graphics.DrawImage%2A> 、和， <xref:System.Drawing.Graphics.DrawString%2A> 如) 。</span><span class="sxs-lookup"><span data-stu-id="f1697-104">To draw anything, you obtain a <xref:System.Drawing.Graphics> object, set its properties, and call its methods <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, and the like).</span></span>  
  
 <span data-ttu-id="f1697-105">下面的示例调用 <xref:System.Drawing.Graphics.DrawRectangle%2A> 对象的方法 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="f1697-105">The following example calls the <xref:System.Drawing.Graphics.DrawRectangle%2A> method of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="f1697-106">传递给方法的第一个参数 <xref:System.Drawing.Graphics.DrawRectangle%2A> 是 <xref:System.Drawing.Pen> 对象。</span><span class="sxs-lookup"><span data-stu-id="f1697-106">The first argument passed to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method is a <xref:System.Drawing.Pen> object.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a><span data-ttu-id="f1697-107">图形状态</span><span class="sxs-lookup"><span data-stu-id="f1697-107">Graphics State</span></span>  
 <span data-ttu-id="f1697-108"><xref:System.Drawing.Graphics>对象不仅仅提供绘图方法，如 <xref:System.Drawing.Graphics.DrawLine%2A> 和 <xref:System.Drawing.Graphics.DrawRectangle%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f1697-108">A <xref:System.Drawing.Graphics> object does more than provide drawing methods, such as <xref:System.Drawing.Graphics.DrawLine%2A> and <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span></span> <span data-ttu-id="f1697-109"><xref:System.Drawing.Graphics>对象还维持了图形状态，可分为以下几类：</span><span class="sxs-lookup"><span data-stu-id="f1697-109">A <xref:System.Drawing.Graphics> object also maintains graphics state, which can be divided into the following categories:</span></span>  
  
- <span data-ttu-id="f1697-110">质量设置</span><span class="sxs-lookup"><span data-stu-id="f1697-110">Quality settings</span></span>  
  
- <span data-ttu-id="f1697-111">转换</span><span class="sxs-lookup"><span data-stu-id="f1697-111">Transformations</span></span>  
  
- <span data-ttu-id="f1697-112">剪辑区域</span><span class="sxs-lookup"><span data-stu-id="f1697-112">Clipping region</span></span>  
  
### <a name="quality-settings"></a><span data-ttu-id="f1697-113">质量设置</span><span class="sxs-lookup"><span data-stu-id="f1697-113">Quality Settings</span></span>  
 <span data-ttu-id="f1697-114"><xref:System.Drawing.Graphics>对象具有多个属性，这些属性影响绘制的项的质量。</span><span class="sxs-lookup"><span data-stu-id="f1697-114">A <xref:System.Drawing.Graphics> object has several properties that influence the quality of the items that are drawn.</span></span> <span data-ttu-id="f1697-115">例如， <xref:System.Drawing.Graphics.TextRenderingHint%2A> 如果将任何) 应用于文本，可以将属性设置为指定消除锯齿的类型 (。</span><span class="sxs-lookup"><span data-stu-id="f1697-115">For example, you can set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property to specify the type of antialiasing (if any) applied to text.</span></span> <span data-ttu-id="f1697-116">影响质量的其他属性包括 <xref:System.Drawing.Graphics.SmoothingMode%2A> 、 <xref:System.Drawing.Graphics.CompositingMode%2A> 、 <xref:System.Drawing.Graphics.CompositingQuality%2A> 和 <xref:System.Drawing.Graphics.InterpolationMode%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f1697-116">Other properties that influence quality are <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, and <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span></span>  
  
 <span data-ttu-id="f1697-117">下面的示例绘制两个椭圆，其中一个平滑模式设置为， <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> 一个设置为平滑模式 <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed> ：</span><span class="sxs-lookup"><span data-stu-id="f1697-117">The following example draws two ellipses, one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> and one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a><span data-ttu-id="f1697-118">转换</span><span class="sxs-lookup"><span data-stu-id="f1697-118">Transformations</span></span>  
 <span data-ttu-id="f1697-119"><xref:System.Drawing.Graphics>对象维护 (世界和页面) 的两个转换，这些转换应用于该对象绘制的所有项 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="f1697-119">A <xref:System.Drawing.Graphics> object maintains two transformations (world and page) that are applied to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="f1697-120">任何仿射转换都可以存储在世界变换中。</span><span class="sxs-lookup"><span data-stu-id="f1697-120">Any affine transformation can be stored in the world transformation.</span></span> <span data-ttu-id="f1697-121">仿射转换包括缩放、旋转、反射、倾斜和平移。</span><span class="sxs-lookup"><span data-stu-id="f1697-121">Affine transformations include scaling, rotating, reflecting, skewing, and translating.</span></span> <span data-ttu-id="f1697-122">页面转换可用于缩放和更改单位 (例如，将像素改为英寸) 。</span><span class="sxs-lookup"><span data-stu-id="f1697-122">The page transformation can be used for scaling and for changing units (for example, pixels to inches).</span></span> <span data-ttu-id="f1697-123">有关详细信息，请参阅 [坐标系统和转换](coordinate-systems-and-transformations.md)。</span><span class="sxs-lookup"><span data-stu-id="f1697-123">For more information, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
 <span data-ttu-id="f1697-124">下面的示例设置对象的世界转换和页转换 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="f1697-124">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="f1697-125">世界变换设置为30度旋转。</span><span class="sxs-lookup"><span data-stu-id="f1697-125">The world transformation is set to a 30-degree rotation.</span></span> <span data-ttu-id="f1697-126">设置页转换，以便将传递给第二个的坐标 <xref:System.Drawing.Graphics.DrawEllipse%2A> 视为毫米而不是像素。</span><span class="sxs-lookup"><span data-stu-id="f1697-126">The page transformation is set so that the coordinates passed to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> will be treated as millimeters instead of pixels.</span></span> <span data-ttu-id="f1697-127">此代码对方法进行两次相同的调用 <xref:System.Drawing.Graphics.DrawEllipse%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f1697-127">The code makes two identical calls to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="f1697-128">世界转换应用于第一次 <xref:System.Drawing.Graphics.DrawEllipse%2A> 调用， (世界和页面) 的转换都应用于第二次 <xref:System.Drawing.Graphics.DrawEllipse%2A> 调用。</span><span class="sxs-lookup"><span data-stu-id="f1697-128">The world transformation is applied to the first <xref:System.Drawing.Graphics.DrawEllipse%2A> call, and both transformations (world and page) are applied to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> call.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 <span data-ttu-id="f1697-129">下图显示了这两个椭圆。</span><span class="sxs-lookup"><span data-stu-id="f1697-129">The following illustration shows the two ellipses.</span></span> <span data-ttu-id="f1697-130">请注意，30度的旋转大约是 (工作区左上角的坐标系统的原点) ，而不是椭圆的中心。</span><span class="sxs-lookup"><span data-stu-id="f1697-130">Note that the 30-degree rotation is about the origin of the coordinate system (upper-left corner of the client area), not about the centers of the ellipses.</span></span> <span data-ttu-id="f1697-131">另请注意，对于第一个椭圆，笔宽度1表示1个像素，第二个椭圆为1毫米。</span><span class="sxs-lookup"><span data-stu-id="f1697-131">Also note that the pen width of 1 means 1 pixel for the first ellipse and 1 millimeter for the second ellipse.</span></span>  
  
 ![显示两个椭圆的插图：旋转和笔宽度。](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a><span data-ttu-id="f1697-133">剪辑区域</span><span class="sxs-lookup"><span data-stu-id="f1697-133">Clipping Region</span></span>  
 <span data-ttu-id="f1697-134"><xref:System.Drawing.Graphics>对象维护一个适用于该对象绘制的所有项的剪辑区域 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="f1697-134">A <xref:System.Drawing.Graphics> object maintains a clipping region that applies to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="f1697-135">可以通过调用方法设置剪辑区域 <xref:System.Drawing.Graphics.SetClip%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f1697-135">You can set the clipping region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
 <span data-ttu-id="f1697-136">下面的示例通过构造两个矩形的并集来创建一个加号区域。</span><span class="sxs-lookup"><span data-stu-id="f1697-136">The following example creates a plus-shaped region by forming the union of two rectangles.</span></span> <span data-ttu-id="f1697-137">该区域被指定为对象的剪辑区域 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="f1697-137">That region is designated as the clipping region of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="f1697-138">然后，该代码将绘制两个限制为剪辑区域内部的行。</span><span class="sxs-lookup"><span data-stu-id="f1697-138">Then the code draws two lines that are restricted to the interior of the clipping region.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 <span data-ttu-id="f1697-139">下图显示了剪切的行：</span><span class="sxs-lookup"><span data-stu-id="f1697-139">The following illustration shows the clipped lines:</span></span>  
  
 ![显示受限制的剪辑区域的关系图。](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a><span data-ttu-id="f1697-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1697-141">See also</span></span>

- [<span data-ttu-id="f1697-142">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="f1697-142">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="f1697-143">使用嵌套的 Graphics 容器</span><span class="sxs-lookup"><span data-stu-id="f1697-143">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)
