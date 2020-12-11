---
title: 调整控件大小
ms.date: 03/30/2017
f1_keywords:
- Size.Height
- Size.Width
helpviewer_keywords:
- controls [Windows Forms], resizing
- size [Windows Forms], controls
- Windows Forms controls, size
ms.assetid: d2dba441-a8c0-4705-b8e8-2e5d86d6e7ec
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 771de6e3962df241357307b0af7682eb45283892
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970536"
---
# <a name="how-to-resize-controls-on-windows-forms"></a><span data-ttu-id="50f19-102">如何：在 Windows 窗体上调整控件的大小</span><span class="sxs-lookup"><span data-stu-id="50f19-102">How to: Resize controls on Windows Forms</span></span>

<span data-ttu-id="50f19-103">可以调整各个控件的大小，还可以调整相同或不同类型的多个控件，例如 <xref:System.Windows.Forms.Button> 和 <xref:System.Windows.Forms.GroupBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="50f19-103">You can resize individual controls, and you can resize multiple controls of the same or different kind, such as <xref:System.Windows.Forms.Button> and <xref:System.Windows.Forms.GroupBox> controls.</span></span>

## <a name="to-resize-a-control"></a><span data-ttu-id="50f19-104">调整控件的大小</span><span class="sxs-lookup"><span data-stu-id="50f19-104">To resize a control</span></span>

<span data-ttu-id="50f19-105">在 Visual Studio 中，选择要调整大小的控件，并拖动8个大小调整控点中的一个。</span><span class="sxs-lookup"><span data-stu-id="50f19-105">In Visual Studio, select the control to be resized and drag one of the eight sizing handles.</span></span>

> [!NOTE]
> <span data-ttu-id="50f19-106">选择控件，然后按住 **Shift** 键并按 **箭头** 键，一次一个像素地调整控件大小。</span><span class="sxs-lookup"><span data-stu-id="50f19-106">Select the control and press the **arrow** keys while holding down the **Shift** key to resize the control one pixel at a time.</span></span> <span data-ttu-id="50f19-107">按住 **Shift** 和 **Ctrl** 键的同时按 **下箭头** 键或 **右箭头** 键，以大幅度调整控件大小。</span><span class="sxs-lookup"><span data-stu-id="50f19-107">Press the **down arrow** or **right arrow** keys while holding down the **Shift** and **Ctrl** keys to resize the control in large increments.</span></span>

## <a name="to-resize-multiple-controls-on-a-form"></a><span data-ttu-id="50f19-108">调整窗体上多个控件的大小</span><span class="sxs-lookup"><span data-stu-id="50f19-108">To resize multiple controls on a form</span></span>

1. <span data-ttu-id="50f19-109">在 Visual Studio 中，按住 **Ctrl** 或 **Shift** 键并选择要调整大小的控件。</span><span class="sxs-lookup"><span data-stu-id="50f19-109">In Visual Studio, hold down the **Ctrl** or **Shift** key and select the controls you want to resize.</span></span> <span data-ttu-id="50f19-110">您选择的第一个控件的大小用于其他控件。</span><span class="sxs-lookup"><span data-stu-id="50f19-110">The size of the first control you select is used for the other controls.</span></span>

2. <span data-ttu-id="50f19-111">在 " **格式** " 菜单上，选择 " **使大小相同**"，然后选择四个选项之一。</span><span class="sxs-lookup"><span data-stu-id="50f19-111">On the **Format** menu, choose **Make Same Size**, and select one of the four options.</span></span> <span data-ttu-id="50f19-112">前三个命令更改控件的尺寸，以匹配第一个选定的控件。</span><span class="sxs-lookup"><span data-stu-id="50f19-112">The first three commands change the dimensions of the controls to match the first-selected control.</span></span>

## <a name="see-also"></a><span data-ttu-id="50f19-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50f19-113">See also</span></span>

- [<span data-ttu-id="50f19-114">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="50f19-114">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="50f19-115">标记单个 Windows 窗体控件并提供它们的快捷方式</span><span class="sxs-lookup"><span data-stu-id="50f19-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="50f19-116">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="50f19-116">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="50f19-117">根据功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="50f19-117">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="50f19-118">[如何：使用设计器调整 Windows 窗体的大小](/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="50f19-118">[How to: Resize Windows Forms Using the Designer](/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100))</span></span>
