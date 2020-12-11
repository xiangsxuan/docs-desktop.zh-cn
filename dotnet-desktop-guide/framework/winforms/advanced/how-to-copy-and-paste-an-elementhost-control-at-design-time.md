---
title: 如何：在设计时复制并粘贴 ElementHost 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: bde599dd8f2f592e9cd361c37572da240f710e2f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970330"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a><span data-ttu-id="21193-102">如何：复制和粘贴 ElementHost 控件</span><span class="sxs-lookup"><span data-stu-id="21193-102">How to: Copy and paste an ElementHost control</span></span>

<span data-ttu-id="21193-103">此过程演示如何在 Visual Studio 中的 Windows 窗体上复制 Windows Presentation Foundation (WPF) 控件。</span><span class="sxs-lookup"><span data-stu-id="21193-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form in Visual Studio.</span></span>

1. <span data-ttu-id="21193-104">在 Visual Studio 中，将一个新的 WPF 添加 <xref:System.Windows.Controls.UserControl> 到 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="21193-104">In Visual Studio, add a new WPF <xref:System.Windows.Controls.UserControl> to a Windows Forms project.</span></span> <span data-ttu-id="21193-105">使用控件类型的默认名称，`UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="21193-105">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="21193-106">有关详细信息，请参阅 [演练：在设计时在 Windows 窗体上创建新的 WPF 内容](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="21193-106">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="21193-107">在 " **属性** " 窗口中，将的和属性的值设置 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> `UserControl1` 为 **200**。</span><span class="sxs-lookup"><span data-stu-id="21193-107">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to **200**.</span></span>

3. <span data-ttu-id="21193-108">将属性的值设置 <xref:System.Windows.Controls.Control.Background%2A> 为 **蓝色**。</span><span class="sxs-lookup"><span data-stu-id="21193-108">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

4. <span data-ttu-id="21193-109">生成项目。</span><span class="sxs-lookup"><span data-stu-id="21193-109">Build the project.</span></span>

5. <span data-ttu-id="21193-110">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="21193-110">Open `Form1` in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="21193-111">从 " **工具箱**" 中，将的实例拖 `UserControl1` 到窗体上。</span><span class="sxs-lookup"><span data-stu-id="21193-111">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>

   <span data-ttu-id="21193-112">`UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="21193-112">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

7. <span data-ttu-id="21193-113">`elementHost1`选中此选项后，按 **Ctrl** + **C** 将其复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="21193-113">With `elementHost1` selected, press **Ctrl**+**C** to copy it to the clipboard.</span></span>

8. <span data-ttu-id="21193-114">按 **Ctrl** + **V** 将复制的控件粘贴到窗体上。</span><span class="sxs-lookup"><span data-stu-id="21193-114">Press **Ctrl**+**V** to paste the copied control onto the form.</span></span>

   <span data-ttu-id="21193-115"><xref:System.Windows.Forms.Integration.ElementHost> `elementHost2` 在窗体上创建一个名为的新控件。</span><span class="sxs-lookup"><span data-stu-id="21193-115">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>

## <a name="see-also"></a><span data-ttu-id="21193-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21193-116">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="21193-117">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="21193-117">Migration and Interoperability</span></span>](/dotnet/framework/wpf/advanced/migration-and-interoperability)
- [<span data-ttu-id="21193-118">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="21193-118">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="21193-119">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="21193-119">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
