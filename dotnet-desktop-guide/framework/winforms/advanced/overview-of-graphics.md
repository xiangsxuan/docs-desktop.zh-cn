---
title: 图形概述
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: e2cc534c32c24f3ac13248bd16b177205e480820
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970800"
---
# <a name="overview-of-graphics"></a><span data-ttu-id="6b5ee-102">图形概述</span><span class="sxs-lookup"><span data-stu-id="6b5ee-102">Overview of Graphics</span></span>
<span data-ttu-id="6b5ee-103">GDI + 是一种应用程序编程接口， (API) 构成 Microsoft Windows 操作系统的子系统。</span><span class="sxs-lookup"><span data-stu-id="6b5ee-103">GDI+ is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> <span data-ttu-id="6b5ee-104">GDI + 负责在屏幕和打印机上显示信息。</span><span class="sxs-lookup"><span data-stu-id="6b5ee-104">GDI+ is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="6b5ee-105">顾名思义，GDI + 是 GDI 的后续版本，图形设备接口包含在 Windows 的早期版本中。</span><span class="sxs-lookup"><span data-stu-id="6b5ee-105">As its name suggests, GDI+ is the successor to GDI, the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="6b5ee-106">托管类接口</span><span class="sxs-lookup"><span data-stu-id="6b5ee-106">Managed Class Interface</span></span>  
 <span data-ttu-id="6b5ee-107">GDI + API 通过作为托管代码部署的一组类公开。</span><span class="sxs-lookup"><span data-stu-id="6b5ee-107">The GDI+ API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="6b5ee-108">这组类称为 GDI + 的 *托管类接口* 。</span><span class="sxs-lookup"><span data-stu-id="6b5ee-108">This set of classes is called the *managed class interface* to GDI+.</span></span> <span data-ttu-id="6b5ee-109">以下命名空间构成托管类接口：</span><span class="sxs-lookup"><span data-stu-id="6b5ee-109">The following namespaces make up the managed class interface:</span></span>  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="6b5ee-110">使用图形设备接口（如 GDI +），可以在屏幕或打印机上显示信息，而不必担心特定显示设备的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6b5ee-110">With a Graphics Device Interface, such as GDI+, you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="6b5ee-111">程序员调用 GDI + 类提供的方法。</span><span class="sxs-lookup"><span data-stu-id="6b5ee-111">The programmer makes calls to methods provided by GDI+ classes.</span></span> <span data-ttu-id="6b5ee-112">这些方法，反过来，对特定的设备驱动程序进行适当的调用。</span><span class="sxs-lookup"><span data-stu-id="6b5ee-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> <span data-ttu-id="6b5ee-113">GDI + 将应用程序与图形硬件隔离开来。</span><span class="sxs-lookup"><span data-stu-id="6b5ee-113">GDI+ insulates the application from the graphics hardware.</span></span> <span data-ttu-id="6b5ee-114">正是这种隔离使程序员能够创建独立于设备的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6b5ee-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b5ee-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b5ee-115">See also</span></span>

- [<span data-ttu-id="6b5ee-116">图形概述</span><span class="sxs-lookup"><span data-stu-id="6b5ee-116">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
