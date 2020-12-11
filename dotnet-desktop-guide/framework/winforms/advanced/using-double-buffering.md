---
title: 使用双缓冲
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: 5b22336221c7bdda3c9dd7adf23308a2b0bad450
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970775"
---
# <a name="using-double-buffering"></a><span data-ttu-id="f4a15-102">使用双缓冲</span><span class="sxs-lookup"><span data-stu-id="f4a15-102">Using Double Buffering</span></span>
<span data-ttu-id="f4a15-103">您可以使用双缓冲图形来减少应用程序中包含复杂绘制操作的闪烁。</span><span class="sxs-lookup"><span data-stu-id="f4a15-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="f4a15-104">.NET Framework 包含对双缓冲的内置支持，或者你可以手动管理和呈现图形。</span><span class="sxs-lookup"><span data-stu-id="f4a15-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f4a15-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="f4a15-105">In This Section</span></span>  
 [<span data-ttu-id="f4a15-106">双缓冲图形</span><span class="sxs-lookup"><span data-stu-id="f4a15-106">Double Buffered Graphics</span></span>](double-buffered-graphics.md)  
 <span data-ttu-id="f4a15-107">介绍双重缓冲概念并概述 .NET Framework 支持。</span><span class="sxs-lookup"><span data-stu-id="f4a15-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="f4a15-108">如何：通过对窗体和控件使用双缓冲来减少图形闪烁</span><span class="sxs-lookup"><span data-stu-id="f4a15-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="f4a15-109">演示如何使用 .NET Framework 中的默认双缓冲支持。</span><span class="sxs-lookup"><span data-stu-id="f4a15-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="f4a15-110">如何：手动管理缓冲的图形</span><span class="sxs-lookup"><span data-stu-id="f4a15-110">How to: Manually Manage Buffered Graphics</span></span>](how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="f4a15-111">演示如何管理应用程序中的双缓冲。</span><span class="sxs-lookup"><span data-stu-id="f4a15-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="f4a15-112">如何：手动呈现缓冲的图形</span><span class="sxs-lookup"><span data-stu-id="f4a15-112">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="f4a15-113">演示如何呈现双缓冲图形。</span><span class="sxs-lookup"><span data-stu-id="f4a15-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f4a15-114">参考</span><span class="sxs-lookup"><span data-stu-id="f4a15-114">Reference</span></span>  
 <span data-ttu-id="f4a15-115"><xref:System.Windows.Forms.Control.SetStyle%2A> 启用双缓冲的控制方法。</span><span class="sxs-lookup"><span data-stu-id="f4a15-115"><xref:System.Windows.Forms.Control.SetStyle%2A> Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="f4a15-116"><xref:System.Drawing.BufferedGraphicsContext> 提供用于创建图形缓冲区的方法。</span><span class="sxs-lookup"><span data-stu-id="f4a15-116"><xref:System.Drawing.BufferedGraphicsContext> Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="f4a15-117">提供对应用程序域的缓冲图形上下文的访问。</span><span class="sxs-lookup"><span data-stu-id="f4a15-117">Provides access to the buffered graphics context for a application domain.</span></span>
