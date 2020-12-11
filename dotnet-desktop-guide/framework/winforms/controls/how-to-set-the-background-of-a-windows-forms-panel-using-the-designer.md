---
title: 使用设计器设置面板的背景
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 8bdefba433632f7ba02f549a549c52c7aa56c2d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972668"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a><span data-ttu-id="f36a1-102">如何：使用设计器设置 Windows 窗体面板的背景</span><span class="sxs-lookup"><span data-stu-id="f36a1-102">How to: Set the background of a Windows Forms panel using the Designer</span></span>

<span data-ttu-id="f36a1-103">Windows 窗体 <xref:System.Windows.Forms.Panel> 控件可以同时显示背景色和背景图像。</span><span class="sxs-lookup"><span data-stu-id="f36a1-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="f36a1-104"><xref:System.Windows.Forms.Control.BackColor%2A>属性为面板中包含的控件（如标签和单选按钮）设置背景色。</span><span class="sxs-lookup"><span data-stu-id="f36a1-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for controls that are contained in the panel, such as labels and radio buttons.</span></span> <span data-ttu-id="f36a1-105">如果 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 未设置该属性，则所 <xref:System.Windows.Forms.Control.BackColor%2A> 选内容将填充所有面板。</span><span class="sxs-lookup"><span data-stu-id="f36a1-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill all of the panel.</span></span> <span data-ttu-id="f36a1-106">如果 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 设置了属性，则该图像将显示在面板中包含的控件后。</span><span class="sxs-lookup"><span data-stu-id="f36a1-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the controls that are contained in the panel.</span></span>

<span data-ttu-id="f36a1-107">下面的过程需要一个具有包含控件的窗体的 **Windows 应用程序** 项目 <xref:System.Windows.Forms.Panel> 。</span><span class="sxs-lookup"><span data-stu-id="f36a1-107">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="f36a1-108">有关如何在 Visual Studio 中设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="f36a1-108">For information about how to set up such a project in Visual Studio, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="set-the-background-in-the-windows-forms-designer"></a><span data-ttu-id="f36a1-109">在 Windows 窗体设计器中设置背景</span><span class="sxs-lookup"><span data-stu-id="f36a1-109">Set the background in the Windows Forms Designer</span></span>

1. <span data-ttu-id="f36a1-110">在 Visual Studio 中打开项目，然后选择 <xref:System.Windows.Forms.Panel> 控件。</span><span class="sxs-lookup"><span data-stu-id="f36a1-110">Open the project in Visual Studio and select the <xref:System.Windows.Forms.Panel> control.</span></span>

2. <span data-ttu-id="f36a1-111">在 " **属性** " 窗口中，单击属性旁边的箭头按钮， <xref:System.Windows.Forms.Control.BackColor%2A> 以显示带有三个选项卡的窗口。</span><span class="sxs-lookup"><span data-stu-id="f36a1-111">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackColor%2A> property to display a window with three tabs.</span></span>

3. <span data-ttu-id="f36a1-112">选择 " **自定义** " 选项卡以显示颜色调色板。</span><span class="sxs-lookup"><span data-stu-id="f36a1-112">Select the **Custom** tab to display a palette of colors.</span></span>

4. <span data-ttu-id="f36a1-113">选择 " **Web** " 或 " **系统** " 选项卡以显示颜色的预定义名称列表，然后选择一种颜色。</span><span class="sxs-lookup"><span data-stu-id="f36a1-113">Select the **Web** or **System** tab to display a list of predefined names for colors, and then select a color.</span></span>

5. <span data-ttu-id="f36a1-114">在 " **属性** " 窗口中，单击属性旁边的箭头按钮 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f36a1-114">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span>

6. <span data-ttu-id="f36a1-115">在 " **打开** " 对话框中，选择要显示的文件。</span><span class="sxs-lookup"><span data-stu-id="f36a1-115">In the **Open** dialog box, select the file that you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="f36a1-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f36a1-116">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="f36a1-117">面板控件</span><span class="sxs-lookup"><span data-stu-id="f36a1-117">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="f36a1-118">Panel 控件概述</span><span class="sxs-lookup"><span data-stu-id="f36a1-118">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="f36a1-119">如何：通过使用设计器使用 Windows 窗体 Panel 控件对控件进行分组</span><span class="sxs-lookup"><span data-stu-id="f36a1-119">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](group-controls-with-wf-panel-control-using-the-designer.md)
