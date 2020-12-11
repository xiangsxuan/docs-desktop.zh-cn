---
title: 为 Windows 窗体选择 WPF 控件
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c1532206b467c523ffd8e4cf4f85c168a4aad80b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971360"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="5db06-102">演练：在设计时在 Windows 窗体上分配 WPF 内容</span><span class="sxs-lookup"><span data-stu-id="5db06-102">Walkthrough: Assign WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="5db06-103">本文介绍如何选择要在窗体上显示的 Windows Presentation Foundation (WPF) 控件类型。</span><span class="sxs-lookup"><span data-stu-id="5db06-103">This article show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="5db06-104">您可以选择项目中包括的任何 WPF 控件类型。</span><span class="sxs-lookup"><span data-stu-id="5db06-104">You can select any WPF control types that are included in your project.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5db06-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="5db06-105">Prerequisites</span></span>

<span data-ttu-id="5db06-106">若要完成本演练，必须具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="5db06-106">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="5db06-107">创建项目</span><span class="sxs-lookup"><span data-stu-id="5db06-107">Create the project</span></span>

<span data-ttu-id="5db06-108">打开 Visual Studio，并在名为的 Visual Basic 或 Visual c # 中创建新的 Windows 窗体应用程序项目 `SelectingWpfContent` 。</span><span class="sxs-lookup"><span data-stu-id="5db06-108">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="5db06-109">承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="5db06-109">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="5db06-110">创建 WPF 控件类型</span><span class="sxs-lookup"><span data-stu-id="5db06-110">Create the WPF control types</span></span>

<span data-ttu-id="5db06-111">将 WPF 控件类型添加到项目后，可将其托管到不同的 <xref:System.Windows.Forms.Integration.ElementHost> 控件。</span><span class="sxs-lookup"><span data-stu-id="5db06-111">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>

1. <span data-ttu-id="5db06-112">将新的 WPF <xref:System.Windows.Controls.UserControl> 项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="5db06-112">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="5db06-113">使用控件类型的默认名称，`UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="5db06-113">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="5db06-114">有关详细信息，请参阅 [演练：在设计时在 Windows 窗体上创建新的 WPF 内容](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="5db06-114">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="5db06-115">在设计视图中，请确保已选中 `UserControl1`。</span><span class="sxs-lookup"><span data-stu-id="5db06-115">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="5db06-116">在 " **属性** " 窗口中，将和属性的值设置 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> 为 **200**。</span><span class="sxs-lookup"><span data-stu-id="5db06-116">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="5db06-117">向添加一个 <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 控件 <xref:System.Windows.Controls.UserControl> ，并将该属性的值设置 <xref:System.Windows.Controls.TextBox.Text%2A> 为 " **托管内容**"。</span><span class="sxs-lookup"><span data-stu-id="5db06-117">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

5. <span data-ttu-id="5db06-118">将第二个 WPF <xref:System.Windows.Controls.UserControl> 添加到项目。</span><span class="sxs-lookup"><span data-stu-id="5db06-118">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="5db06-119">使用控件类型的默认名称，`UserControl2.xaml`。</span><span class="sxs-lookup"><span data-stu-id="5db06-119">Use the default name for the control type, `UserControl2.xaml`.</span></span>

6. <span data-ttu-id="5db06-120">在 " **属性** " 窗口中，将和属性的值设置 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> 为 **200**。</span><span class="sxs-lookup"><span data-stu-id="5db06-120">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

7. <span data-ttu-id="5db06-121">向添加一个 <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 控件 <xref:System.Windows.Controls.UserControl> ，并将该属性的值设置 <xref:System.Windows.Controls.TextBox.Text%2A> 为 " **托管内容 2**"。</span><span class="sxs-lookup"><span data-stu-id="5db06-121">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5db06-122">一般情况下，你应承载更复杂的 WPF 内容。</span><span class="sxs-lookup"><span data-stu-id="5db06-122">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="5db06-123">此处，<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 控件仅为了便于说明。</span><span class="sxs-lookup"><span data-stu-id="5db06-123">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

8. <span data-ttu-id="5db06-124">生成项目。</span><span class="sxs-lookup"><span data-stu-id="5db06-124">Build the project.</span></span>

## <a name="select-wpf-controls"></a><span data-ttu-id="5db06-125">选择 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="5db06-125">Select WPF controls</span></span>

<span data-ttu-id="5db06-126">可将不同的 WPF 内容分配到 <xref:System.Windows.Forms.Integration.ElementHost> 控件，该控件现已承载内容。</span><span class="sxs-lookup"><span data-stu-id="5db06-126">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>

1. <span data-ttu-id="5db06-127">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="5db06-127">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="5db06-128">在 " **工具箱**" 中，双击在 `UserControl1` `UserControl1` 窗体上创建的实例。</span><span class="sxs-lookup"><span data-stu-id="5db06-128">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="5db06-129">`UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="5db06-129">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

3. <span data-ttu-id="5db06-130">在的智能标记面板中 `elementHost1` ，打开 " **选择承载的内容** " 下拉列表。</span><span class="sxs-lookup"><span data-stu-id="5db06-130">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>

4. <span data-ttu-id="5db06-131">从下拉列表框中选择 " **UserControl2** "。</span><span class="sxs-lookup"><span data-stu-id="5db06-131">Select **UserControl2** from the drop-down list box.</span></span>

   <span data-ttu-id="5db06-132">`elementHost1` 控件现承载 `UserControl2` 类型的实例。</span><span class="sxs-lookup"><span data-stu-id="5db06-132">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>

5. <span data-ttu-id="5db06-133">在 " **属性** " 窗口中，确认 " <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 属性" 设置为 " **UserControl2**"。</span><span class="sxs-lookup"><span data-stu-id="5db06-133">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>

6. <span data-ttu-id="5db06-134">从 " **工具箱**" 的 " **WPF 互操作性** " 组中，将 <xref:System.Windows.Forms.Integration.ElementHost> 控件拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="5db06-134">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>

   <span data-ttu-id="5db06-135">新控件的默认名称是 `elementHost2`。</span><span class="sxs-lookup"><span data-stu-id="5db06-135">The default name for the new control is `elementHost2`.</span></span>

7. <span data-ttu-id="5db06-136">在的智能标记面板中 `elementHost2` ，打开 " **选择承载的内容** " 下拉列表。</span><span class="sxs-lookup"><span data-stu-id="5db06-136">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>

8. <span data-ttu-id="5db06-137">从下拉列表中选择 " **UserControl1** "。</span><span class="sxs-lookup"><span data-stu-id="5db06-137">Select **UserControl1** from the drop-down list.</span></span>

9. <span data-ttu-id="5db06-138">`elementHost2` 控件现承载 `UserControl1` 类型的实例。</span><span class="sxs-lookup"><span data-stu-id="5db06-138">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>

## <a name="see-also"></a><span data-ttu-id="5db06-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5db06-139">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="5db06-140">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="5db06-140">Migration and Interoperability</span></span>](/dotnet/framework/wpf/advanced/migration-and-interoperability)
- [<span data-ttu-id="5db06-141">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="5db06-141">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="5db06-142">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="5db06-142">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
