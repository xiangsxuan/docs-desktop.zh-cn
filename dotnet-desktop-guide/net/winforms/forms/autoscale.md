---
title: 自动窗体缩放
description: 介绍适用于 .NET 的 Windows 窗体如何缩放 UI。
ms.date: 10/26/2020
ms.topic: overview
helpviewer_keywords:
- scalability [Windows Forms], automatic in Windows Forms
- Windows Forms, automatic scaling
ms.openlocfilehash: c414575c83723dc1930a0bfe298534eee9aa48c8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942000"
---
# <a name="automatic-scaling-windows-forms-net"></a><span data-ttu-id="ee3b7-103">自动缩放（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="ee3b7-103">Automatic scaling (Windows Forms .NET)</span></span>

<span data-ttu-id="ee3b7-104">借助自动缩放功能，在某台计算机上以某种显示分辨率或字体设计的窗体及其控件可以在其他计算机上以不同的显示分辨率或字体适当显示。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-104">Automatic scaling enables a form and its controls, designed on one machine with a certain display resolution or font, to be displayed appropriately on another machine with a different display resolution or font.</span></span> <span data-ttu-id="ee3b7-105">它确保窗体及其控件将以智能方式调整大小，以便与本机 Windows 以及用户和其他开发人员的计算机上的其他应用程序保持一致。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-105">It assures that the form and its controls will intelligently resize to be consistent with native windows and other applications on both the users' and other developers' machines.</span></span> <span data-ttu-id="ee3b7-106">自动缩放和视觉样式使 Windows 窗体应用程序可以在与每个用户的计算机上的本机 Windows 应用程序比较时保持一致的外观和感觉。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-106">Automatic scaling and visual styles enable Windows Forms applications to maintain a consistent look-and-feel when compared to native Windows applications on each user's machine.</span></span>

<span data-ttu-id="ee3b7-107">大多数情况下，自动缩放可在 Windows 窗体中按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-107">For the most part, automatic scaling works as expected in Windows Forms.</span></span> <span data-ttu-id="ee3b7-108">但是，字体方案更改可能会产生问题。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-108">However, font scheme changes can be problematic.</span></span><!-- TODO For an example of how to resolve this, see [How to: Respond to Font Scheme Changes in a Windows Forms Application](how-to-respond-to-font-scheme-changes-in-a-windows-forms-application.md). -->

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="need-for-automatic-scaling"></a><span data-ttu-id="ee3b7-109">自动缩放的必要性</span><span class="sxs-lookup"><span data-stu-id="ee3b7-109">Need for automatic scaling</span></span>

<span data-ttu-id="ee3b7-110">若不进行自动缩放，在分辨率或字体更改时，为某个显示分辨率或字体设计的应用程序将显示太大或太小。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-110">Without automatic scaling, an application designed for one display resolution or font will either appear too small or too large when that resolution or font is changed.</span></span> <span data-ttu-id="ee3b7-111">例如，如果应用程序是使用 Tahoma 9 point 作为基准而设计的，则在系统字体为 Tahoma 12 point 的计算机上运行时，若不进行调整它将显示太小。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-111">For example, if the application is designed using Tahoma 9 point as a baseline, without adjustment it will appear too small if run on a machine where the system font is Tahoma 12 point.</span></span> <span data-ttu-id="ee3b7-112">与其他应用程序相比，呈现的文本元素（如标题、菜单、文本框内容等）要小一些。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-112">Text elements, such as titles, menus, text box contents, and so on will render smaller than other applications.</span></span> <span data-ttu-id="ee3b7-113">此外，包含文本的用户界面 (UI) 元素（如标题栏、菜单和很多控件）的大小均取决于所使用的字体。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-113">Furthermore, the size of user interface (UI) elements that contain text, such as the title bar, menus, and many controls are dependent on the font used.</span></span> <span data-ttu-id="ee3b7-114">在此示例中，这些元素的显示也相对小一些。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-114">In this example, these elements will also appear relatively smaller.</span></span>

<span data-ttu-id="ee3b7-115">如果应用程序是针对某种显示分辨率设计的，会发生类似情况。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-115">An analogous situation occurs when an application is designed for a certain display resolution.</span></span> <span data-ttu-id="ee3b7-116">最常见的显示分辨率为每英寸 96 点 (DPI)（即 100% 的显示比例），但支持 125%、150%、200%（分别等于 120、144 和 192 DPI）及以上的更高分辨率的显示器也越来越常见。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-116">The most common display resolution is 96 dots per inch (DPI), which equals 100% display scaling, but higher resolution displays supporting 125%, 150%, 200% (which respectively equal 120, 144 and 192 DPI) and above are becoming more common.</span></span> <span data-ttu-id="ee3b7-117">如果不进行调整，针对某个分辨率设计的应用程序（特别是基于图形的应用程序）在其他分辨率上运行时就会显示太大或太小。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-117">Without adjustment, an application, especially a graphics-based one, designed for one resolution will appear either too large or too small when run at another resolution.</span></span>

<span data-ttu-id="ee3b7-118">自动缩放力求解决这些问题，方法是更具相对字体大小或显示分辨率自动调整窗体及其子控件的大小。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-118">Automatic scaling seeks to address these problems by automatically resizing the form and its child controls according to the relative font size or display resolution.</span></span> <span data-ttu-id="ee3b7-119">Windows 操作系统支持使用一种名为对话框单位的相对度量单位的自动缩放对话框。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-119">The Windows operating system supports automatic scaling of dialog boxes using a relative unit of measurement called dialog units.</span></span> <span data-ttu-id="ee3b7-120">对话框单位基于系统字体，并且它与像素的关系可由 Win32 SDK 函数 `GetDialogBaseUnits` 确定。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-120">A dialog unit is based on the system font and its relationship to pixels can be determined though the Win32 SDK function `GetDialogBaseUnits`.</span></span> <span data-ttu-id="ee3b7-121">当用户更改 Windows 使用的主题时，所有对话框均自动进行相应调整。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-121">When a user changes the theme used by Windows, all dialog boxes are automatically adjusted accordingly.</span></span> <span data-ttu-id="ee3b7-122">此外，根据默认系统字体或显示分辨率，Windows 窗体支持自动缩放。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-122">In addition, Windows Forms supports automatic scaling either according to the default system font or the display resolution.</span></span> <span data-ttu-id="ee3b7-123">或者，可在应用程序中禁用自动缩放。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-123">Optionally, automatic scaling can be disabled in an application.</span></span>

> [!CAUTION]
> <span data-ttu-id="ee3b7-124">不支持任意混合的 DPI 和字体缩放模式。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-124">Arbitrary mixtures of DPI and font scaling modes are not supported.</span></span> <span data-ttu-id="ee3b7-125">虽然你可能成功使用某种模式（例如 DPI）缩放用户控件并以另一种模式（字体）将其放在窗体上，但混合使用一种模式下的基窗体和其他模式下的派生窗体时可能导致意外结果。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-125">Although you may scale a user control using one mode (for example, DPI) and place it on a form using another mode (Font) with no issues, but mixing a base form in one mode and a derived form in another can lead to unexpected results.</span></span>

## <a name="automatic-scaling-in-action"></a><span data-ttu-id="ee3b7-126">操作中的自动缩放</span><span class="sxs-lookup"><span data-stu-id="ee3b7-126">Automatic scaling in action</span></span>

<span data-ttu-id="ee3b7-127">Windows 窗体使用以下逻辑自动缩放窗体及其内容：</span><span class="sxs-lookup"><span data-stu-id="ee3b7-127">Windows Forms uses the following logic to automatically scale forms and their contents:</span></span>

01. <span data-ttu-id="ee3b7-128">在设计时，每个 <xref:System.Windows.Forms.ContainerControl> 分别在 <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> 和 <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> 中记录缩放模式及其当前的分辨率。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-128">At design time, each <xref:System.Windows.Forms.ContainerControl> records the scaling mode and it current resolution in the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> and <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>, respectively.</span></span>

01. <span data-ttu-id="ee3b7-129">在运行时，实际的分辨率存储在 <xref:System.Windows.Forms.ContainerControl.CurrentAutoScaleDimensions%2A> 属性中。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-129">At run time, the actual resolution is stored in the <xref:System.Windows.Forms.ContainerControl.CurrentAutoScaleDimensions%2A> property.</span></span> <span data-ttu-id="ee3b7-130"><xref:System.Windows.Forms.ContainerControl.AutoScaleFactor%2A> 属性动态计算运行时和设计时缩放分辨率之间的比率。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-130">The <xref:System.Windows.Forms.ContainerControl.AutoScaleFactor%2A> property dynamically calculates the ratio between the run-time and design-time scaling resolution.</span></span>

01. <span data-ttu-id="ee3b7-131">窗体加载时，如果 <xref:System.Windows.Forms.ContainerControl.CurrentAutoScaleDimensions%2A> 和 <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> 的值不同，则调用 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A> 方法来缩放控件及其子项。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-131">When the form loads, if the values of <xref:System.Windows.Forms.ContainerControl.CurrentAutoScaleDimensions%2A> and <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> are different, then the <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A> method is called to scale the control and its children.</span></span> <span data-ttu-id="ee3b7-132">此方法将挂起布局并调用 <xref:System.Windows.Forms.Control.Scale%2A> 方法来执行实际缩放。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-132">This method suspends layout and calls the <xref:System.Windows.Forms.Control.Scale%2A> method to perform the actual scaling.</span></span> <span data-ttu-id="ee3b7-133">随后将更新 <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> 的值以避免渐进式缩放。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-133">Afterwards, the value of <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> is updated to avoid progressive scaling.</span></span>

01. <span data-ttu-id="ee3b7-134">在以下情况下也可自动调用 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>：</span><span class="sxs-lookup"><span data-stu-id="ee3b7-134"><xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A> is also automatically invoked in the following situations:</span></span>

    - <span data-ttu-id="ee3b7-135">如果缩放模式为 <xref:System.Windows.Forms.AutoScaleMode.Font>，则响应 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 事件。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-135">In response to the <xref:System.Windows.Forms.Control.OnFontChanged%2A> event if the scaling mode is <xref:System.Windows.Forms.AutoScaleMode.Font>.</span></span>

    - <span data-ttu-id="ee3b7-136">当容器控件的布局继续执行并在 <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> 或 <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> 属性中检测到更改时。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-136">When the layout of the container control resumes and a change is detected in the <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> or <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> properties.</span></span>

    - <span data-ttu-id="ee3b7-137">如上所述，当父 <xref:System.Windows.Forms.ContainerControl> 正在缩放时。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-137">As implied above, when a parent <xref:System.Windows.Forms.ContainerControl> is being scaled.</span></span> <span data-ttu-id="ee3b7-138">每个容器控件负责使用自己的比例因子（而不是其父容器的比例因子）缩放其子控件。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-138">Each container control is responsible for scaling its children using its own scaling factors and not the one from its parent container.</span></span>

01. <span data-ttu-id="ee3b7-139">子控件可通过多种方式修改其缩放行为：</span><span class="sxs-lookup"><span data-stu-id="ee3b7-139">Child controls can modify their scaling behavior through several means:</span></span>

    - <span data-ttu-id="ee3b7-140">可重写 <xref:System.Windows.Forms.Control.ScaleChildren%2A> 属性以确定是否应缩放其子控件。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-140">The <xref:System.Windows.Forms.Control.ScaleChildren%2A> property can be overridden to determine if their child controls should be scaled or not.</span></span>

    - <span data-ttu-id="ee3b7-141">可重写 <xref:System.Windows.Forms.Control.GetScaledBounds%2A> 方法以调整控件缩放到的边界，但不是调整缩放逻辑。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-141">The <xref:System.Windows.Forms.Control.GetScaledBounds%2A> method can be overridden to adjust the bounds that the control is scaled to, but not the scaling logic.</span></span>

    - <span data-ttu-id="ee3b7-142">可重写 <xref:System.Windows.Forms.Control.ScaleControl%2A> 方法以更改当前控件的缩放逻辑。</span><span class="sxs-lookup"><span data-stu-id="ee3b7-142">The <xref:System.Windows.Forms.Control.ScaleControl%2A> method can be overridden to change the scaling logic for the current control.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee3b7-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee3b7-143">See also</span></span>

- <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>
- <xref:System.Windows.Forms.Control.Scale%2A>
- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>

<!-- TODO
- [Rendering Controls with Visual Styles](controls/rendering-controls-with-visual-styles.md)
- [How to: Improve Performance by Avoiding Automatic Scaling](advanced/how-to-improve-performance-by-avoiding-automatic-scaling.md)-->
