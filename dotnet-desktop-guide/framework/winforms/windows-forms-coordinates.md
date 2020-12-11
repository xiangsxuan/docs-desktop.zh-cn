---
title: 坐标
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: c95888f31bfc867e9c028d53072ab3d710256708
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970513"
---
# <a name="windows-forms-coordinates"></a><span data-ttu-id="24edc-102">Windows 窗体坐标</span><span class="sxs-lookup"><span data-stu-id="24edc-102">Windows Forms Coordinates</span></span>
<span data-ttu-id="24edc-103">Windows 窗体的坐标系统基于设备坐标，在 Windows 窗体中绘制时的基本度量单位是 (通常为设备单位，像素) 。</span><span class="sxs-lookup"><span data-stu-id="24edc-103">The coordinate system for a Windows Form is based on device coordinates, and the basic unit of measure when drawing in Windows Forms is the device unit (typically, the pixel).</span></span> <span data-ttu-id="24edc-104">屏幕上的点按 x 和 y 坐标对进行说明，其中 x 坐标向右递增，y 坐标从上到下递增。</span><span class="sxs-lookup"><span data-stu-id="24edc-104">Points on the screen are described by x- and y-coordinate pairs, with the x-coordinates increasing to the right and the y-coordinates increasing from top to bottom.</span></span> <span data-ttu-id="24edc-105">根据您指定的是屏幕坐标还是工作区坐标，原点相对于屏幕的位置会有所不同。</span><span class="sxs-lookup"><span data-stu-id="24edc-105">The location of the origin, relative to the screen, will vary depending on whether you are specifying screen or client coordinates.</span></span>  
  
## <a name="screen-coordinates"></a><span data-ttu-id="24edc-106">屏幕坐标</span><span class="sxs-lookup"><span data-stu-id="24edc-106">Screen Coordinates</span></span>  
 <span data-ttu-id="24edc-107">Windows 窗体应用程序以屏幕坐标的形式指定窗口在屏幕上的位置。</span><span class="sxs-lookup"><span data-stu-id="24edc-107">A Windows Forms application specifies the position of a window on the screen in screen coordinates.</span></span> <span data-ttu-id="24edc-108">对于屏幕坐标，原点是屏幕的左上角。</span><span class="sxs-lookup"><span data-stu-id="24edc-108">For screen coordinates, the origin is the upper-left corner of the screen.</span></span> <span data-ttu-id="24edc-109">窗口的完整位置通常由一个结构描述，该 <xref:System.Drawing.Rectangle> 结构包含定义窗口的左上角和右下角的两个点的屏幕坐标。</span><span class="sxs-lookup"><span data-stu-id="24edc-109">The full position of a window is often described by a <xref:System.Drawing.Rectangle> structure containing the screen coordinates of two points that define the upper-left and lower-right corners of the window.</span></span>  
  
## <a name="client-coordinates"></a><span data-ttu-id="24edc-110">工作区坐标</span><span class="sxs-lookup"><span data-stu-id="24edc-110">Client Coordinates</span></span>  
 <span data-ttu-id="24edc-111">Windows 窗体应用程序使用客户端坐标指定窗体或控件中点的位置。</span><span class="sxs-lookup"><span data-stu-id="24edc-111">A Windows Forms application specifies the position of points in a form or control using client coordinates.</span></span> <span data-ttu-id="24edc-112">工作区坐标原点是控件或窗体工作区的左上角。</span><span class="sxs-lookup"><span data-stu-id="24edc-112">The origin for client coordinates is the upper-left corner of the client area of the control or form.</span></span> <span data-ttu-id="24edc-113">客户端坐标可确保应用程序在窗体或控件中绘制时可以使用一致的坐标值，而不管窗体或控件在屏幕上的位置。</span><span class="sxs-lookup"><span data-stu-id="24edc-113">Client coordinates ensure that an application can use consistent coordinate values while drawing in a form or control, regardless of the position of the form or control on the screen.</span></span>  
  
 <span data-ttu-id="24edc-114">工作区的维度也由 <xref:System.Drawing.Rectangle> 包含区域的工作区坐标的结构描述。</span><span class="sxs-lookup"><span data-stu-id="24edc-114">The dimensions of the client area are also described by a <xref:System.Drawing.Rectangle> structure that contains client coordinates for the area.</span></span> <span data-ttu-id="24edc-115">在所有情况下，矩形的左上角坐标都包含在工作区中，同时排除右下坐标。</span><span class="sxs-lookup"><span data-stu-id="24edc-115">In all cases, the upper-left coordinate of the rectangle is included in the client area, while the lower-right coordinate is excluded.</span></span> <span data-ttu-id="24edc-116">图形操作不包括工作区的右边缘和下边缘。</span><span class="sxs-lookup"><span data-stu-id="24edc-116">Graphics operations do not include the right and lower edges of a client area.</span></span> <span data-ttu-id="24edc-117">例如， <xref:System.Drawing.Graphics.FillRectangle%2A> 方法将填充指定矩形的右边缘和下边缘，但不包括这些边缘。</span><span class="sxs-lookup"><span data-stu-id="24edc-117">For example the <xref:System.Drawing.Graphics.FillRectangle%2A> method will fill up to the right and lower edge of the specified rectangle, but will not include these edges.</span></span>  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a><span data-ttu-id="24edc-118">从一种坐标类型映射到另一种坐标</span><span class="sxs-lookup"><span data-stu-id="24edc-118">Mapping From One Type of Coordinate to Another</span></span>  
 <span data-ttu-id="24edc-119">有时，可能需要从屏幕坐标映射到工作区坐标。</span><span class="sxs-lookup"><span data-stu-id="24edc-119">Occasionally, you may need to map from screen coordinates to client coordinates.</span></span> <span data-ttu-id="24edc-120">通过使用 <xref:System.Windows.Forms.Control.PointToClient%2A> 类中提供的和方法，可以轻松实现此目的 <xref:System.Windows.Forms.Control.PointToScreen%2A> <xref:System.Windows.Forms.Control> 。</span><span class="sxs-lookup"><span data-stu-id="24edc-120">You can easily accomplish this by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available in the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="24edc-121">例如，的 <xref:System.Windows.Forms.Control.MousePosition%2A> 属性 <xref:System.Windows.Forms.Control> 以屏幕坐标的形式报告，但你可能希望将其转换为工作区坐标。</span><span class="sxs-lookup"><span data-stu-id="24edc-121">For example, the <xref:System.Windows.Forms.Control.MousePosition%2A> property of <xref:System.Windows.Forms.Control> is reported in screen coordinates, but you may want to convert these to client coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24edc-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24edc-122">See also</span></span>

- <xref:System.Windows.Forms.Control.PointToClient%2A>
- <xref:System.Windows.Forms.Control.PointToScreen%2A>
