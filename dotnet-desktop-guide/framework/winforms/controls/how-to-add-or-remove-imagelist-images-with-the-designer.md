---
title: 如何：使用设计器添加或移除 ImageList 图像
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: cdc7b563a0ee4f8779b99b4e9a6786e78f8d500f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971909"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="ebd7d-102">如何：使用设计器添加或移除 ImageList 图像</span><span class="sxs-lookup"><span data-stu-id="ebd7d-102">How to: Add or Remove ImageList Images with the Designer</span></span>

<span data-ttu-id="ebd7d-103">可以 <xref:System.Windows.Forms.ImageList> 通过多种不同方式向组件添加图像。</span><span class="sxs-lookup"><span data-stu-id="ebd7d-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="ebd7d-104">你可以通过使用与关联的智能标记来非常快速地添加图像 <xref:System.Windows.Forms.ImageList> ，或者，如果你在上设置多个其他属性 <xref:System.Windows.Forms.ImageList> ，则可以更方便地使用属性窗口添加图像。</span><span class="sxs-lookup"><span data-stu-id="ebd7d-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="ebd7d-105">你还可以通过使用代码来添加映像。</span><span class="sxs-lookup"><span data-stu-id="ebd7d-105">You can also add images by using code.</span></span> <span data-ttu-id="ebd7d-106">有关如何添加包含代码的图像的详细信息，请参阅 [如何：在 Windows 窗体 ImageList 组件中添加或删除图像](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)。</span><span class="sxs-lookup"><span data-stu-id="ebd7d-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="ebd7d-107">通常，在 <xref:System.Windows.Forms.ImageList> 组件与控件关联之前，使用图像填充组件，但这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="ebd7d-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="ebd7d-108">使用属性窗口添加或删除映像</span><span class="sxs-lookup"><span data-stu-id="ebd7d-108">To add or remove images by using the Properties window</span></span>

1. <span data-ttu-id="ebd7d-109">选择 <xref:System.Windows.Forms.ImageList> 组件，或将其添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="ebd7d-109">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="ebd7d-110">在属性窗口中，单击省略号按钮 (![ Visual Studio 属性窗口中的省略号按钮 ( ") "。在 ](./media/visual-studio-ellipsis-button.png) 属性旁) 。 <xref:System.Windows.Forms.ImageList.Images%2A></span><span class="sxs-lookup"><span data-stu-id="ebd7d-110">In the Properties window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>

3. <span data-ttu-id="ebd7d-111">在 **图像集合编辑器** 中，单击 " **添加** " 或 " **删除** " 以添加或删除列表中的映像。</span><span class="sxs-lookup"><span data-stu-id="ebd7d-111">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>

### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="ebd7d-112">使用智能标记添加或删除图像</span><span class="sxs-lookup"><span data-stu-id="ebd7d-112">To add or remove images using the smart tag</span></span>

1. <span data-ttu-id="ebd7d-113">选择 <xref:System.Windows.Forms.ImageList> 组件，或将其添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="ebd7d-113">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="ebd7d-114">单击设计器操作标志符号 (</span><span class="sxs-lookup"><span data-stu-id="ebd7d-114">Click the designer actions glyph (</span></span>![小号黑色箭头](./media/designer-actions-glyph.gif)<span data-ttu-id="ebd7d-116">)</span><span class="sxs-lookup"><span data-stu-id="ebd7d-116">)</span></span>

3. <span data-ttu-id="ebd7d-117">在 " **ImageList 任务** " 对话框中，选择 " **选择图像**"。</span><span class="sxs-lookup"><span data-stu-id="ebd7d-117">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>

4. <span data-ttu-id="ebd7d-118">在 **图像集合编辑器** 中，单击 " **添加** " 或 " **删除** " 以添加或删除列表中的映像。</span><span class="sxs-lookup"><span data-stu-id="ebd7d-118">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="ebd7d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebd7d-119">See also</span></span>

- [<span data-ttu-id="ebd7d-120">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="ebd7d-120">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="ebd7d-121">演练：使用设计操作执行常规任务</span><span class="sxs-lookup"><span data-stu-id="ebd7d-121">Walkthrough: Perform common tasks using designer actions</span></span>](perform-common-tasks-design-actions.md)
- [<span data-ttu-id="ebd7d-122">ImageList 组件</span><span class="sxs-lookup"><span data-stu-id="ebd7d-122">ImageList Component</span></span>](imagelist-component-windows-forms.md)
