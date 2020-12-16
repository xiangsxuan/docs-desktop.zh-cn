---
title: 将控件添加到窗体
description: 了解如何在适用于 .NET 的 Windows 窗体中将控件添加到窗体
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.openlocfilehash: 44a20f135eb0f1503a6e5204a33aa8dca092123f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941967"
---
# <a name="add-a-control-windows-forms-net"></a><span data-ttu-id="4af96-103">添加控件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="4af96-103">Add a control (Windows Forms .NET)</span></span>

<span data-ttu-id="4af96-104">大多数窗体的设计方法如下：向窗体表面添加控件，以定义用户界面 (UI)。</span><span class="sxs-lookup"><span data-stu-id="4af96-104">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="4af96-105">控件是窗体上的组件，用于显示信息或接受用户输入。</span><span class="sxs-lookup"><span data-stu-id="4af96-105">A *control* is a component on a form used to display information or accept user input.</span></span><!-- TODO For more information about controls, see [Forms overview](..\forms\overview.md). -->

<span data-ttu-id="4af96-106">将控件添加到窗体的主要方法是使用 Visual Studio 设计器，但你也可以在运行时使用代码来管理窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="4af96-106">The primary way a control is added to a form is through the Visual Studio Designer, but you can also manage the controls on a form at run time through code.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="add-with-designer"></a><span data-ttu-id="4af96-107">使用设计器添加</span><span class="sxs-lookup"><span data-stu-id="4af96-107">Add with Designer</span></span>

<span data-ttu-id="4af96-108">Visual Studio 使用窗体设计器设计窗体。</span><span class="sxs-lookup"><span data-stu-id="4af96-108">Visual Studio uses the Forms Designer to design forms.</span></span> <span data-ttu-id="4af96-109">“控件”窗格列出了应用可使用的所有控件。</span><span class="sxs-lookup"><span data-stu-id="4af96-109">There is a Controls pane which lists all the controls available to your app.</span></span> <span data-ttu-id="4af96-110">可以通过两种方式从窗格中添加控件：</span><span class="sxs-lookup"><span data-stu-id="4af96-110">You can add controls from the pane in two ways:</span></span>

### <a name="add-the-control-by-double-clicking"></a><span data-ttu-id="4af96-111">通过双击添加控件</span><span class="sxs-lookup"><span data-stu-id="4af96-111">Add the control by double-clicking</span></span>

<span data-ttu-id="4af96-112">双击控件时，它将自动添加到当前打开的具有默认设置的窗体中。</span><span class="sxs-lookup"><span data-stu-id="4af96-112">When a control is double-clicked, it is automatically added to the current open form with default settings.</span></span>

:::image type="content" source="media/how-to-add-to-a-form/toolbox-double-click.gif" alt-text="双击适用于 .NET Windows 窗体的 Visual Studio 的工具箱中的控件":::

### <a name="add-the-control-by-drawing"></a><span data-ttu-id="4af96-114">通过拖动添加控件</span><span class="sxs-lookup"><span data-stu-id="4af96-114">Add the control by drawing</span></span>

<span data-ttu-id="4af96-115">通过单击选择控件。</span><span class="sxs-lookup"><span data-stu-id="4af96-115">Select the control by clicking on it.</span></span> <span data-ttu-id="4af96-116">在窗体中，拖选一个区域。</span><span class="sxs-lookup"><span data-stu-id="4af96-116">In your form, drag-select a region.</span></span> <span data-ttu-id="4af96-117">放置控件以适应所选区域的大小。</span><span class="sxs-lookup"><span data-stu-id="4af96-117">The control will be placed to fit the size of the region you selected.</span></span>

:::image type="content" source="media/how-to-add-to-a-form/toolbox-drag-draw.gif" alt-text="拖选和拖放适用于 .NET Windows 窗体的 Visual Studio 的工具箱中的控件":::

## <a name="add-with-code"></a><span data-ttu-id="4af96-119">使用代码添加</span><span class="sxs-lookup"><span data-stu-id="4af96-119">Add with code</span></span>

<span data-ttu-id="4af96-120">可以创建控件，然后在运行时使用窗体的 <xref:System.Windows.Forms.Control.Controls%2A> 集合将其添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="4af96-120">Controls can be created and then added to a form at run time with the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span> <span data-ttu-id="4af96-121">还可以使用此集合将控件从窗体中删除。</span><span class="sxs-lookup"><span data-stu-id="4af96-121">This collection can also be used to remove controls from a form.</span></span>

<span data-ttu-id="4af96-122">以下代码添加并放置了两个控件，即 [Label](xref:System.Windows.Forms.Label) 和 [TextBox](xref:System.Windows.Forms.TextBox)：</span><span class="sxs-lookup"><span data-stu-id="4af96-122">The following code adds and positions two controls, a [Label](xref:System.Windows.Forms.Label) and a [TextBox](xref:System.Windows.Forms.TextBox):</span></span>

:::code language="csharp" source="snippets/how-to-add-to-a-form/cs/Form1.cs" id="CreateControl":::

:::code language="vb" source="snippets/how-to-add-to-a-form/vb/Form1.vb" id="CreateControl":::

## <a name="see-also"></a><span data-ttu-id="4af96-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4af96-123">See also</span></span>

- [<span data-ttu-id="4af96-124">如何：设置 Windows 窗体控件所显示的文本</span><span class="sxs-lookup"><span data-stu-id="4af96-124">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-display-text.md)
- [<span data-ttu-id="4af96-125">如何：向控件添加访问键快捷方式</span><span class="sxs-lookup"><span data-stu-id="4af96-125">How to: Add an access key shortcut to a control</span></span>](how-to-create-access-keys.md)
- <xref:System.Windows.Forms.Label>
- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.Button>
