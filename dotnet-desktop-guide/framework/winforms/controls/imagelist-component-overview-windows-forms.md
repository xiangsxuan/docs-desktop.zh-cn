---
title: ImageList 组件概述
ms.date: 03/30/2017
f1_keywords:
- ImageList
helpviewer_keywords:
- collection controls [Windows Forms], images
- icon list control
- ImageList component [Windows Forms], about ImageList component
ms.assetid: 7e25d89b-5633-40c1-afc3-82e0e301ffa2
ms.openlocfilehash: b46204375cb046d637f4c9e1d888f37d10ea1f57
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972641"
---
# <a name="imagelist-component-overview-windows-forms"></a><span data-ttu-id="74a7c-102">ImageList 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="74a7c-102">ImageList Component Overview (Windows Forms)</span></span>

<span data-ttu-id="74a7c-103">Windows 窗体 <xref:System.Windows.Forms.ImageList> 组件用于存储图像，此图像之后可由控件显示。</span><span class="sxs-lookup"><span data-stu-id="74a7c-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is used to store images, which can then be displayed by controls.</span></span> <span data-ttu-id="74a7c-104">借助图像列表，你可为图像的单个一致目录编写代码。</span><span class="sxs-lookup"><span data-stu-id="74a7c-104">An image list allows you to write code for a single, consistent catalog of images.</span></span> <span data-ttu-id="74a7c-105">例如，只需更改按钮的 <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> 或 <xref:System.Windows.Forms.ButtonBase.ImageKey%2A> 属性，即可旋转 <xref:System.Windows.Forms.Button> 控件显示的图像。</span><span class="sxs-lookup"><span data-stu-id="74a7c-105">For example, you can rotate images displayed by a <xref:System.Windows.Forms.Button> control simply by changing the button's <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> or <xref:System.Windows.Forms.ButtonBase.ImageKey%2A> property.</span></span> <span data-ttu-id="74a7c-106">还可将相同图像列表与多个控件关联。</span><span class="sxs-lookup"><span data-stu-id="74a7c-106">You can also associate the same image list with multiple controls.</span></span> <span data-ttu-id="74a7c-107">例如，如果同时使用 <xref:System.Windows.Forms.ListView> 控件和 <xref:System.Windows.Forms.TreeView> 控件来显示相同的文件列表，更改文件在图像列表中的图标将导致新图标显示在这两个视图中。</span><span class="sxs-lookup"><span data-stu-id="74a7c-107">For example, if you are using both a <xref:System.Windows.Forms.ListView> control and a <xref:System.Windows.Forms.TreeView> control to display the same list of files, changing a file's icon in the image list will cause the new icon to appear in both views.</span></span>

## <a name="using-imagelist-with-controls"></a><span data-ttu-id="74a7c-108">将 ImageList 与控件一起使用</span><span class="sxs-lookup"><span data-stu-id="74a7c-108">Using ImageList with Controls</span></span>

<span data-ttu-id="74a7c-109">可将图像列表与任何具有 `ImageList` 属性的控件一同使用，如果与 <xref:System.Windows.Forms.ListView> 控件一同使用，则此控件要具有 <xref:System.Windows.Forms.ListView.SmallImageList%2A> 和 <xref:System.Windows.Forms.ListView.LargeImageList%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="74a7c-109">You can use an image list with any control that has an `ImageList` property — or in the case of the <xref:System.Windows.Forms.ListView> control, <xref:System.Windows.Forms.ListView.SmallImageList%2A> and <xref:System.Windows.Forms.ListView.LargeImageList%2A> properties.</span></span> <span data-ttu-id="74a7c-110">可与图像列表关联的控件包括：<xref:System.Windows.Forms.ListView>、<xref:System.Windows.Forms.TreeView>、<xref:System.Windows.Forms.ToolBar>、<xref:System.Windows.Forms.TabControl>、<xref:System.Windows.Forms.Button><xref:System.Windows.Forms.CheckBox>、<xref:System.Windows.Forms.RadioButton> 和 <xref:System.Windows.Forms.Label> 控件。</span><span class="sxs-lookup"><span data-stu-id="74a7c-110">The controls that can be associated with an image list include: the <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ToolBar>, <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton>, and <xref:System.Windows.Forms.Label> controls.</span></span> <span data-ttu-id="74a7c-111">若要将图像列表与控件关联，请将控件的 `ImageList` 属性设置为 <xref:System.Windows.Forms.ImageList> 组件的名称。</span><span class="sxs-lookup"><span data-stu-id="74a7c-111">To associate the image list with a control, set the control's `ImageList` property to the name of the <xref:System.Windows.Forms.ImageList> component.</span></span>

## <a name="key-properties"></a><span data-ttu-id="74a7c-112">键属性</span><span class="sxs-lookup"><span data-stu-id="74a7c-112">Key Properties</span></span>

<span data-ttu-id="74a7c-113"><xref:System.Windows.Forms.ImageList> 组件的键属性是 <xref:System.Windows.Forms.ImageList.Images%2A>，其中包含关联控件使用的图片。</span><span class="sxs-lookup"><span data-stu-id="74a7c-113">The key property of the <xref:System.Windows.Forms.ImageList> component is <xref:System.Windows.Forms.ImageList.Images%2A>, which contains the pictures to be used by the associated control.</span></span> <span data-ttu-id="74a7c-114">可通过相应的索引值或键访问每张单独的图像。</span><span class="sxs-lookup"><span data-stu-id="74a7c-114">Each individual image can be accessed by its index value or by its key.</span></span> <span data-ttu-id="74a7c-115"><xref:System.Windows.Forms.ImageList.ColorDepth%2A> 属性确定图像呈现的颜色数。</span><span class="sxs-lookup"><span data-stu-id="74a7c-115">The <xref:System.Windows.Forms.ImageList.ColorDepth%2A> property determines the number of colors that the images are rendered with.</span></span> <span data-ttu-id="74a7c-116">由 <xref:System.Windows.Forms.ImageList.ImageSize%2A> 属性设置后，图像将以相同大小显示。</span><span class="sxs-lookup"><span data-stu-id="74a7c-116">The images will all be displayed at the same size, set by the <xref:System.Windows.Forms.ImageList.ImageSize%2A> property.</span></span> <span data-ttu-id="74a7c-117">较大的图像将调整为合适大小。</span><span class="sxs-lookup"><span data-stu-id="74a7c-117">Images that are larger will be scaled to fit.</span></span>

## <a name="see-also"></a><span data-ttu-id="74a7c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74a7c-118">See also</span></span>

- <xref:System.Windows.Forms.ImageList>
- [<span data-ttu-id="74a7c-119">如何：使用 Windows 窗体 ImageList 组件添加或移除图像</span><span class="sxs-lookup"><span data-stu-id="74a7c-119">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
