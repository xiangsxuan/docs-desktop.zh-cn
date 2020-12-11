---
title: GDI+ 中的图元文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: df54289722cf12bad840722c6eafdaa43279a5dc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970802"
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="4dc4c-102">GDI+ 中的图元文件</span><span class="sxs-lookup"><span data-stu-id="4dc4c-102">Metafiles in GDI+</span></span>
<span data-ttu-id="4dc4c-103">GDI + 提供 <xref:System.Drawing.Imaging.Metafile> 类，以便可以记录和显示图元文件。</span><span class="sxs-lookup"><span data-stu-id="4dc4c-103">GDI+ provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="4dc4c-104">图元文件（也称为矢量图像）是存储为一系列绘图命令和设置的图像。</span><span class="sxs-lookup"><span data-stu-id="4dc4c-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="4dc4c-105">在对象中记录的命令和设置 <xref:System.Drawing.Imaging.Metafile> 可以存储在内存中，也可以保存到文件或流中。</span><span class="sxs-lookup"><span data-stu-id="4dc4c-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="4dc4c-106">图元文件格式</span><span class="sxs-lookup"><span data-stu-id="4dc4c-106">Metafile Formats</span></span>  
 <span data-ttu-id="4dc4c-107">GDI + 可以显示存储为以下格式的图元文件：</span><span class="sxs-lookup"><span data-stu-id="4dc4c-107">GDI+ can display metafiles that have been stored in the following formats:</span></span>  
  
- <span data-ttu-id="4dc4c-108">Windows 图元文件 (WMF) </span><span class="sxs-lookup"><span data-stu-id="4dc4c-108">Windows Metafile (WMF)</span></span>  
  
- <span data-ttu-id="4dc4c-109">增强型图元文件 (EMF)</span><span class="sxs-lookup"><span data-stu-id="4dc4c-109">Enhanced Metafile (EMF)</span></span>  
  
- <span data-ttu-id="4dc4c-110">EMF +</span><span class="sxs-lookup"><span data-stu-id="4dc4c-110">EMF+</span></span>  
  
 <span data-ttu-id="4dc4c-111">GDI + 可以记录 EMF 和 EMF + 格式的图元文件，但不能以 WMF 格式记录。</span><span class="sxs-lookup"><span data-stu-id="4dc4c-111">GDI+ can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="4dc4c-112">EMF + 是 EMF 的扩展，它允许存储 GDI + 记录。</span><span class="sxs-lookup"><span data-stu-id="4dc4c-112">EMF+ is an extension to EMF that allows GDI+ records to be stored.</span></span> <span data-ttu-id="4dc4c-113">EMF + 格式有两种变体：仅限 EMF + 和 EMF + 双重。</span><span class="sxs-lookup"><span data-stu-id="4dc4c-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="4dc4c-114">仅限 EMF + 只包含 GDI + 记录的图元文件。</span><span class="sxs-lookup"><span data-stu-id="4dc4c-114">EMF+ Only metafiles contain only GDI+ records.</span></span> <span data-ttu-id="4dc4c-115">此类元文件可通过 GDI + 显示，但不能由 GDI 显示。</span><span class="sxs-lookup"><span data-stu-id="4dc4c-115">Such metafiles can be displayed by GDI+ but not by GDI.</span></span> <span data-ttu-id="4dc4c-116">EMF + 双图元文件包含 GDI + 和 GDI 记录。</span><span class="sxs-lookup"><span data-stu-id="4dc4c-116">EMF+ Dual metafiles contain GDI+ and GDI records.</span></span> <span data-ttu-id="4dc4c-117">EMF + 双重图元文件中的每个 GDI + 记录都与备用的 GDI 记录配对。</span><span class="sxs-lookup"><span data-stu-id="4dc4c-117">Each GDI+ record in an EMF+ Dual metafile is paired with an alternate GDI record.</span></span> <span data-ttu-id="4dc4c-118">此类元文件可通过 GDI + 或 GDI 来显示。</span><span class="sxs-lookup"><span data-stu-id="4dc4c-118">Such metafiles can be displayed by GDI+ or by GDI.</span></span>  
  
 <span data-ttu-id="4dc4c-119">下面的示例显示之前保存为文件的图元文件。</span><span class="sxs-lookup"><span data-stu-id="4dc4c-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="4dc4c-120">图元文件的左上角显示 (100，100) 。</span><span class="sxs-lookup"><span data-stu-id="4dc4c-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="4dc4c-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4dc4c-121">See also</span></span>

- [<span data-ttu-id="4dc4c-122">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="4dc4c-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
