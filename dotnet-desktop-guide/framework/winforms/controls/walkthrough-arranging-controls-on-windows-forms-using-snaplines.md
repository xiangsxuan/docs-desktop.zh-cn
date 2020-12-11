---
title: 使用对齐线排列控件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 0b68a70b55cbf03d480fd388a637a4caf78b6eaa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972853"
---
# <a name="walkthrough-arrange-controls-on-windows-forms-using-snaplines"></a><span data-ttu-id="8a2b1-102">演练：使用对齐线排列 Windows 窗体上的控件</span><span class="sxs-lookup"><span data-stu-id="8a2b1-102">Walkthrough: Arrange controls on Windows Forms using snaplines</span></span>

<span data-ttu-id="8a2b1-103">在窗体上精确地放置控件对于许多应用程序而言是高优先级。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="8a2b1-104">Windows 窗体设计器提供了许多布局工具来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-104">The Windows Forms Designer gives you many layout tools to accomplish this.</span></span> <span data-ttu-id="8a2b1-105">最重要的一项是 <xref:System.Windows.Forms.Design.Behavior.SnapLine> 功能。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-105">One of the most important is the <xref:System.Windows.Forms.Design.Behavior.SnapLine> feature.</span></span>

<span data-ttu-id="8a2b1-106">对齐线可精确显示控件与其他控件的对齐位置。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-106">Snaplines show you precisely where to line up controls with other controls.</span></span> <span data-ttu-id="8a2b1-107">它们还显示了建议的距离，如 [Windows 用户界面准则](/windows/win32/uxguide/guidelines)所指定。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-107">They also show you the recommended distances for margins between controls, as specified by the [Windows User Interface guidelines](/windows/win32/uxguide/guidelines).</span></span>

<span data-ttu-id="8a2b1-108">利用对齐线，你可以轻松地对齐控件，以获得清晰、专业的外观和行为 (外观) 。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-108">Snaplines make it easy to align your controls, for crisp, professional appearance and behavior (look and feel).</span></span>

## <a name="create-the-project"></a><span data-ttu-id="8a2b1-109">创建项目</span><span class="sxs-lookup"><span data-stu-id="8a2b1-109">Create the project</span></span>

1. <span data-ttu-id="8a2b1-110">在 Visual Studio 中，创建一个名为 "SnaplineExample" 的基于 Windows 的应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-110">In Visual Studio, create a Windows-based application project called "SnaplineExample".</span></span>

2. <span data-ttu-id="8a2b1-111">在“窗体设计器”中选择窗体。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-111">Select the form in the Forms Designer.</span></span>

## <a name="space-and-align-controls"></a><span data-ttu-id="8a2b1-112">间距和对齐控件</span><span class="sxs-lookup"><span data-stu-id="8a2b1-112">Space and align controls</span></span>

<span data-ttu-id="8a2b1-113">"对齐线" 为您显示窗体上控件的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-113">Snaplines give you an accurate and intuitive way to align controls on your form.</span></span> <span data-ttu-id="8a2b1-114">当您将选定控件或控件移动到与另一个控件或控件集对齐的位置时，它们将显示。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-114">They appear when you are moving a selected control or controls near a position that would align with another control or set of controls.</span></span> <span data-ttu-id="8a2b1-115">在将其移到其他控件之后，你的选择将 "对齐" 到建议的位置。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-115">Your selection will "snap" to the suggested position as you move it past the other controls.</span></span>

### <a name="to-arrange-controls-using-snaplines"></a><span data-ttu-id="8a2b1-116">使用对齐线排列控件</span><span class="sxs-lookup"><span data-stu-id="8a2b1-116">To arrange controls using snaplines</span></span>

1. <span data-ttu-id="8a2b1-117">从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-117">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="8a2b1-118">将 <xref:System.Windows.Forms.Button> 控件移动到窗体的右下角。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-118">Move the <xref:System.Windows.Forms.Button> control to the lower-right corner of the form.</span></span> <span data-ttu-id="8a2b1-119">请注意，当 <xref:System.Windows.Forms.Button> 控件接近窗体的下边框和右边框时显示的对齐线。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-119">Note the snaplines that appear as the <xref:System.Windows.Forms.Button> control approaches the bottom and right borders of the form.</span></span> <span data-ttu-id="8a2b1-120">这些对齐线显示控件边框与窗体边框之间的建议距离。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-120">These snaplines display the recommended distance between the borders of the control and the form.</span></span>

3. <span data-ttu-id="8a2b1-121"><xref:System.Windows.Forms.Button>围绕窗体的边框移动控件，并注意对齐线出现的位置。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-121">Move the <xref:System.Windows.Forms.Button> control around the borders of the form and note where the snaplines appear.</span></span> <span data-ttu-id="8a2b1-122">完成后，将控件移动到 <xref:System.Windows.Forms.Button> 窗体中心附近。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-122">When you are finished, move the <xref:System.Windows.Forms.Button> control near the center of the form.</span></span>

4. <span data-ttu-id="8a2b1-123">将另一个 <xref:System.Windows.Forms.Button> 控件从 **工具箱** 拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-123">Drag another <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

5. <span data-ttu-id="8a2b1-124">移动第二个 <xref:System.Windows.Forms.Button> 控件，直到它接近第一个控件。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-124">Move the second <xref:System.Windows.Forms.Button> control until it is nearly level with the first.</span></span> <span data-ttu-id="8a2b1-125">请注意，在这两个按钮的文本基线上出现的对齐线，并注意您正在移动的控件将对齐到与其他控件完全相同的位置。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-125">Note the snapline that appears at the text baseline of both buttons, and note that the control you are moving snaps to a position that is exactly level with the other control.</span></span>

6. <span data-ttu-id="8a2b1-126">移动第二个 <xref:System.Windows.Forms.Button> 控件，直到它直接位于第一个控件的上方。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-126">Move the second <xref:System.Windows.Forms.Button> control until it is positioned directly above the first.</span></span> <span data-ttu-id="8a2b1-127">请注意在这两个按钮的左右边缘上出现的对齐线，并注意您正在移动的控件将对齐到与其他控件完全对齐的位置。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-127">Note the snaplines that appear along the left and right edges of both buttons, and note that the control you are moving snaps to a position that is exactly aligned with the other control.</span></span>

7. <span data-ttu-id="8a2b1-128">选择其中一个 <xref:System.Windows.Forms.Button> 控件，并将其移动到另一个控件，直到它们接近。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-128">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other, until they are almost touching.</span></span> <span data-ttu-id="8a2b1-129">请注意它们之间出现的对齐线。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-129">Note the snapline that appears between them.</span></span> <span data-ttu-id="8a2b1-130">此距离是控件边框之间建议的距离。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-130">This distance is the recommended distance between the borders of the controls.</span></span> <span data-ttu-id="8a2b1-131">另请注意，正在移动的控件将对齐到此位置。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-131">Also note that the control you are moving snaps to this position.</span></span>

8. <span data-ttu-id="8a2b1-132">将两个 <xref:System.Windows.Forms.Panel> 控件从 **工具箱** 拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-132">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto your form.</span></span>

9. <span data-ttu-id="8a2b1-133">移动其中一个 <xref:System.Windows.Forms.Panel> 控件，直到它接近于第一个控件。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-133">Move one of the <xref:System.Windows.Forms.Panel> controls until it is nearly level with the first.</span></span> <span data-ttu-id="8a2b1-134">请注意沿两个控件的上边缘和下边缘显示的对齐线，并注意您正在移动的控件对齐到与其他控件完全相同的位置。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-134">Note the snaplines that appear along the top and bottom edges of both controls, and note that the control you are moving snaps to a position that is exactly level with the other control.</span></span>

## <a name="align-to-form-and-container-margins"></a><span data-ttu-id="8a2b1-135">对齐窗体和容器边距</span><span class="sxs-lookup"><span data-stu-id="8a2b1-135">Align to form and container margins</span></span>

<span data-ttu-id="8a2b1-136">对齐线有助于以一致的方式将控件与窗体和容器边距对齐。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-136">Snaplines help you to align your controls to form and container margins in a consistent manner.</span></span>

1. <span data-ttu-id="8a2b1-137">选择其中一个 <xref:System.Windows.Forms.Button> 控件，并将其移动到窗体的右边框，直到出现对齐线。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-137">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the right border of the form until a snapline appears.</span></span> <span data-ttu-id="8a2b1-138">对齐线与右边框的距离是控件的 <xref:System.Windows.Forms.Control.Margin%2A> 属性和窗体的 <xref:System.Windows.Forms.Control.Padding%2A> 属性值之和。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-138">The snapline's distance from the right border is the sum of the control's <xref:System.Windows.Forms.Control.Margin%2A> property and the form's <xref:System.Windows.Forms.Control.Padding%2A> property values.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8a2b1-139">如果窗体的 <xref:System.Windows.Forms.Control.Padding%2A> 属性设置为0，0，0，0，则 Windows 窗体设计器为窗体提供一个阴影 <xref:System.Windows.Forms.Control.Padding%2A> 值9、9、9、9。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-139">If the form's <xref:System.Windows.Forms.Control.Padding%2A> property is set to 0,0,0,0, the Windows Forms Designer gives the form a shadowed <xref:System.Windows.Forms.Control.Padding%2A> value of 9,9,9,9.</span></span> <span data-ttu-id="8a2b1-140">若要重写此行为，请指定0、0、0、0以外的值。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-140">To override this behavior, assign a value other than 0,0,0,0.</span></span>

2. <span data-ttu-id="8a2b1-141"><xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Margin%2A> 通过 <xref:System.Windows.Forms.Control.Margin%2A> 在 "**属性**" 窗口中展开条目并将属性设置为0，可更改控件的属性的值 <xref:System.Windows.Forms.Padding.All%2A> 。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-141">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Margin%2A> property by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 0.</span></span> <span data-ttu-id="8a2b1-142">有关详细信息，请参阅 [演练：通过填充、边距和 AutoSize 属性排放 Windows 窗体控件](windows-forms-controls-padding-autosize.md)。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-142">For details, see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](windows-forms-controls-padding-autosize.md).</span></span>

3. <span data-ttu-id="8a2b1-143">将 <xref:System.Windows.Forms.Button> 控件移动到窗体的右边框附近，直到出现对齐线。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-143">Move the <xref:System.Windows.Forms.Button> control close to the right border of the form until a snapline appears.</span></span> <span data-ttu-id="8a2b1-144">此距离现在由窗体的属性的值提供 <xref:System.Windows.Forms.Control.Padding%2A> 。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-144">This distance is now given by the value of the form's <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>

4. <span data-ttu-id="8a2b1-145">从 <xref:System.Windows.Forms.GroupBox> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-145">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span>

5. <span data-ttu-id="8a2b1-146"><xref:System.Windows.Forms.GroupBox> <xref:System.Windows.Forms.Control.Padding%2A> 通过 <xref:System.Windows.Forms.Control.Padding%2A> 在 "**属性**" 窗口中展开条目并将属性设置为10，来更改控件的属性的值 <xref:System.Windows.Forms.Padding.All%2A> 。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-146">Change the value of the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 10.</span></span>

6. <span data-ttu-id="8a2b1-147">将 <xref:System.Windows.Forms.Button> 控件从 " **工具箱** " 拖放到 <xref:System.Windows.Forms.GroupBox> 控件中。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-147">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span>

7. <span data-ttu-id="8a2b1-148">将 <xref:System.Windows.Forms.Button> 控件移动到控件的右边框附近， <xref:System.Windows.Forms.GroupBox> 直到出现对齐线。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-148">Move the <xref:System.Windows.Forms.Button> control close to the right border of the <xref:System.Windows.Forms.GroupBox> control until a snapline appears.</span></span> <span data-ttu-id="8a2b1-149">移动 <xref:System.Windows.Forms.Button> 控件内的控件 <xref:System.Windows.Forms.GroupBox> ，并注意对齐线出现的位置。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-149">Move the <xref:System.Windows.Forms.Button> control within the <xref:System.Windows.Forms.GroupBox> control and note where the snaplines appear.</span></span>

## <a name="align-to-grouped-controls"></a><span data-ttu-id="8a2b1-150">对齐到分组控件</span><span class="sxs-lookup"><span data-stu-id="8a2b1-150">Align to grouped controls</span></span>

<span data-ttu-id="8a2b1-151">您可以使用对齐线对齐控件中的分组控件和控件 <xref:System.Windows.Forms.GroupBox> 。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-151">You can use snaplines to align grouped controls as well as controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span>

1. <span data-ttu-id="8a2b1-152">选择窗体上的两个控件。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-152">Select two of the controls on your form.</span></span> <span data-ttu-id="8a2b1-153">移动所选内容，并记下所选内容与其他控件之间出现的对齐线。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-153">Move the selection around and note the snaplines that appear between your selection and the other controls.</span></span>

2. <span data-ttu-id="8a2b1-154">从 <xref:System.Windows.Forms.GroupBox> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-154">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span>

3. <span data-ttu-id="8a2b1-155">将 <xref:System.Windows.Forms.Button> 控件从 " **工具箱** " 拖放到 <xref:System.Windows.Forms.GroupBox> 控件中。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-155">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span>

4. <span data-ttu-id="8a2b1-156">选择其中一个 <xref:System.Windows.Forms.Button> 控件，并在控件上移动它 <xref:System.Windows.Forms.GroupBox> 。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-156">Select one of the <xref:System.Windows.Forms.Button> controls and move it around the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="8a2b1-157">请注意控件边缘上出现的对齐线 <xref:System.Windows.Forms.GroupBox> 。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-157">Note the snaplines that appear at the edges of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="8a2b1-158">另请注意控件所包含控件边缘上出现的对齐线 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.GroupBox> 。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-158">Also note the snaplines that appear at the edges of the <xref:System.Windows.Forms.Button> control that is contained by the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="8a2b1-159">容器控件的子级控件也支持对齐线。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-159">Controls that are children of a container control also support snaplines.</span></span>

## <a name="use-snaplines-to-place-a-control-by-outlining-its-size"></a><span data-ttu-id="8a2b1-160">通过勾画控件大小来使用对齐线放置控件</span><span class="sxs-lookup"><span data-stu-id="8a2b1-160">Use snaplines to place a control by outlining its size</span></span>

1. <span data-ttu-id="8a2b1-161">在“工具箱” 中，单击 <xref:System.Windows.Forms.Button> 控件图标。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-161">In the **Toolbox**, click the <xref:System.Windows.Forms.Button> control icon.</span></span> <span data-ttu-id="8a2b1-162">请勿将其拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-162">Do not drag it onto the form.</span></span>

2. <span data-ttu-id="8a2b1-163">将鼠标指针移动到窗体的设计图面上。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-163">Move the mouse pointer over the form's design surface.</span></span> <span data-ttu-id="8a2b1-164">请注意，指针会更改为十字形，同时会附上 <xref:System.Windows.Forms.Button> 控件图标。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-164">Note that the pointer changes to a crosshair with the <xref:System.Windows.Forms.Button> control icon attached.</span></span> <span data-ttu-id="8a2b1-165">另请注意为控件建议对齐位置的对齐线 <xref:System.Windows.Forms.Button> 。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-165">Also note the snaplines that appear to suggest aligned positions for the <xref:System.Windows.Forms.Button> control.</span></span>

3. <span data-ttu-id="8a2b1-166">单击并按住鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-166">Click and hold the mouse button.</span></span>

4. <span data-ttu-id="8a2b1-167">在窗体上拖动鼠标指针。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-167">Drag the mouse pointer around the form.</span></span> <span data-ttu-id="8a2b1-168">请注意，会绘制一个轮廓，指示控件的位置和大小。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-168">Note that an outline is drawn, indicating the position and the size of the control.</span></span>

5. <span data-ttu-id="8a2b1-169">拖动指针，直到它与窗体上的另一个控件对齐。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-169">Drag the pointer until it aligns with another control on the form.</span></span> <span data-ttu-id="8a2b1-170">请注意，将显示一条对齐线以指示对齐方式。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-170">Note that a snapline appears to indicate alignment.</span></span>

6. <span data-ttu-id="8a2b1-171">释放鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-171">Release the mouse button.</span></span> <span data-ttu-id="8a2b1-172">控件在由轮廓指示的位置和大小创建。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-172">The control is created at the position and size indicated by the outline.</span></span>

## <a name="use-snaplines-when-dragging-a-control-from-the-toolbox"></a><span data-ttu-id="8a2b1-173">从工具箱拖动控件时使用对齐线</span><span class="sxs-lookup"><span data-stu-id="8a2b1-173">Use snaplines when dragging a control from the Toolbox</span></span>

1. <span data-ttu-id="8a2b1-174">将 <xref:System.Windows.Forms.Button> 控件从 " **工具箱** " 拖到窗体上，但不释放鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-174">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form, but do not release the mouse button.</span></span>

2. <span data-ttu-id="8a2b1-175">将鼠标指针移动到窗体的设计图面上。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-175">Move the mouse pointer over the form's design surface.</span></span> <span data-ttu-id="8a2b1-176">请注意，指针会更改以指示 <xref:System.Windows.Forms.Button> 将创建新控件的位置。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-176">Note that the pointer changes to indicate the position at which the new <xref:System.Windows.Forms.Button> control will be created.</span></span>

3. <span data-ttu-id="8a2b1-177">在窗体上拖动鼠标指针。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-177">Drag the mouse pointer around the form.</span></span> <span data-ttu-id="8a2b1-178">请注意显示的对齐线，用于建议控件的对齐位置 <xref:System.Windows.Forms.Button> 。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-178">Note the snaplines that appear to suggest aligned positions for the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="8a2b1-179">查找与其他控件对齐的位置。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-179">Find a position that is aligned with other controls.</span></span>

4. <span data-ttu-id="8a2b1-180">释放鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-180">Release the mouse button.</span></span> <span data-ttu-id="8a2b1-181">控件将在对齐线指示的位置创建。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-181">The control is created at the position indicated by the snaplines.</span></span>

## <a name="resize-a-control-using-snaplines"></a><span data-ttu-id="8a2b1-182">使用对齐线调整控件大小</span><span class="sxs-lookup"><span data-stu-id="8a2b1-182">Resize a control using snaplines</span></span>

1. <span data-ttu-id="8a2b1-183">从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-183">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="8a2b1-184">通过获取 <xref:System.Windows.Forms.Button> 一个角大小调整控点并拖动来调整控件的大小。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-184">Resize the <xref:System.Windows.Forms.Button> control by grabbing one of the corner sizing handles and dragging.</span></span> <span data-ttu-id="8a2b1-185">有关详细信息，请参阅 [如何：在 Windows 窗体上调整控件的大小](how-to-resize-controls-on-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-185">For details, see [How to: Resize Controls on Windows Forms](how-to-resize-controls-on-windows-forms.md).</span></span>

3. <span data-ttu-id="8a2b1-186">拖动调整大小控点，直到其中一个 <xref:System.Windows.Forms.Button> 控件的边框与另一个控件对齐。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-186">Drag the sizing handle until one of the <xref:System.Windows.Forms.Button> control's borders is aligned with another control.</span></span> <span data-ttu-id="8a2b1-187">请注意，会显示对齐线。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-187">Note that a snapline appears.</span></span> <span data-ttu-id="8a2b1-188">另请注意，大小调整控点与对齐线指示的位置对齐。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-188">Also note that the sizing handle snaps to the position indicated by the snapline.</span></span>

4. <span data-ttu-id="8a2b1-189"><xref:System.Windows.Forms.Button>按不同方向调整控件大小，并将大小调整控点与不同控件对齐。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-189">Resize the <xref:System.Windows.Forms.Button> control in different directions and align the sizing handle to different controls.</span></span> <span data-ttu-id="8a2b1-190">请注意对齐线如何出现在各种方向上以指示对齐方式。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-190">Note how the snaplines appear in various orientations to indicate alignment.</span></span>

## <a name="align-a-label-to-a-controls-text"></a><span data-ttu-id="8a2b1-191">将标签与控件的文本对齐</span><span class="sxs-lookup"><span data-stu-id="8a2b1-191">Align a label to a control's text</span></span>

1. <span data-ttu-id="8a2b1-192">从 <xref:System.Windows.Forms.TextBox> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-192">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="8a2b1-193">将 <xref:System.Windows.Forms.TextBox> 控件放到窗体上时，单击智能标记标志符号，然后选择 " **将文本设置为 textBox1** " 选项。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-193">When you drop the <xref:System.Windows.Forms.TextBox> control onto the form, click the smart-tag glyph and select the **Set text to textBox1** option.</span></span> <span data-ttu-id="8a2b1-194">有关详细信息，请参阅 [演练：使用设计器操作执行常见任务](perform-common-tasks-design-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-194">For details, see [Walkthrough: Perform common tasks using designer actions](perform-common-tasks-design-actions.md).</span></span>

2. <span data-ttu-id="8a2b1-195">从 <xref:System.Windows.Forms.Label> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-195">Drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto your form.</span></span>

3. <span data-ttu-id="8a2b1-196">将 <xref:System.Windows.Forms.Label> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性值更改为 `true`。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-196">Change the value of the <xref:System.Windows.Forms.Label> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="8a2b1-197">请注意，控件的边框会调整以适应显示文本。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-197">Note that the control's borders are adjusted to fit the display text.</span></span>

4. <span data-ttu-id="8a2b1-198">将 <xref:System.Windows.Forms.Label> 控件移动到控件的左侧 <xref:System.Windows.Forms.TextBox> ，使其与控件的下边缘对齐 <xref:System.Windows.Forms.TextBox> 。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-198">Move the <xref:System.Windows.Forms.Label> control to the left of the <xref:System.Windows.Forms.TextBox> control, so it is aligned with the bottom edge of the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="8a2b1-199">请注意在两个控件的下边缘显示的对齐线。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-199">Note the snapline that appears along the bottom edges of the two controls.</span></span>

5. <span data-ttu-id="8a2b1-200"><xref:System.Windows.Forms.Label>稍微向上移动控件，直到 <xref:System.Windows.Forms.Label> 文本和 <xref:System.Windows.Forms.TextBox> 文本对齐。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-200">Move the <xref:System.Windows.Forms.Label> control slightly upward, until the <xref:System.Windows.Forms.Label> text and the <xref:System.Windows.Forms.TextBox> text are aligned.</span></span> <span data-ttu-id="8a2b1-201">请注意显示的样式不同的对齐线，指示两个控件的文本字段对齐的时间。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-201">Note the differently styled snapline that appears, indicating when the text fields of both controls are aligned.</span></span>

## <a name="use-snaplines-with-keyboard-navigation"></a><span data-ttu-id="8a2b1-202">通过键盘导航使用对齐线</span><span class="sxs-lookup"><span data-stu-id="8a2b1-202">Use snaplines with keyboard navigation</span></span>

1. <span data-ttu-id="8a2b1-203">从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-203">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="8a2b1-204">将其放在窗体的左上角。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-204">Place it in the upper-left corner of the form.</span></span>

2. <span data-ttu-id="8a2b1-205">按 **Ctrl** + **向下** 键。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-205">Press **Ctrl**+**down arrow**.</span></span> <span data-ttu-id="8a2b1-206">请注意，控件向下移动到第一个可用的水平对齐位置。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-206">Note that the control moves down the form to the first available horizontal alignment position.</span></span>

3. <span data-ttu-id="8a2b1-207">按 **Ctrl** + **向下键**，直到控件到达窗体的底部。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-207">Press **Ctrl**+**down arrow** until the control reaches the bottom of the form.</span></span> <span data-ttu-id="8a2b1-208">请注意，它在窗体中向下移动时所占据的位置。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-208">Note the positions it occupies as it moves down the form.</span></span>

4. <span data-ttu-id="8a2b1-209">按 **Ctrl** + **向右箭头**。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-209">Press **Ctrl**+**right arrow**.</span></span> <span data-ttu-id="8a2b1-210">请注意，控件在窗体上移动到第一个可用的垂直对齐位置。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-210">Note that the control moves across the form to the first available vertical alignment position.</span></span>

5. <span data-ttu-id="8a2b1-211">按 **Ctrl** + **向右箭头** 直到控件到达窗体的一侧。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-211">Press **Ctrl**+**right arrow** until the control reaches the side of the form.</span></span> <span data-ttu-id="8a2b1-212">请注意，它在窗体中移动时所占据的位置。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-212">Note the positions it occupies as it moves across the form.</span></span>

6. <span data-ttu-id="8a2b1-213">使用箭头键的组合在窗体周围移动控件。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-213">Move the control around the form with a combination of arrow keys.</span></span> <span data-ttu-id="8a2b1-214">请注意控件占据的位置以及伴随控件的对齐线。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-214">Note the positions the control occupies and the snaplines that accompany them.</span></span>

7. <span data-ttu-id="8a2b1-215">按 **Shift** + **箭头键** 可按 <xref:System.Windows.Forms.Button> 一个像素的增量调整控件的大小。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-215">Press **Shift**+**arrow keys** to resize the <xref:System.Windows.Forms.Button> control by increments of one pixel.</span></span>

8. <span data-ttu-id="8a2b1-216">按 **Ctrl** + **Shift** + **箭头键** 可 <xref:System.Windows.Forms.Button> 在对齐线增量中调整控件的大小。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-216">Press **Ctrl**+**Shift**+**arrow keys** to resize the <xref:System.Windows.Forms.Button> control in snapline increments.</span></span>

## <a name="selectively-disable-snaplines"></a><span data-ttu-id="8a2b1-217">有选择地禁用对齐线</span><span class="sxs-lookup"><span data-stu-id="8a2b1-217">Selectively disable snaplines</span></span>

1. <span data-ttu-id="8a2b1-218">从 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-218">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="8a2b1-219">在“工具箱” <xref:System.Windows.Forms.Button>**中，双击** 控件图标。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-219">Double-click the <xref:System.Windows.Forms.Button> control icon in the **Toolbox**.</span></span> <span data-ttu-id="8a2b1-220">请注意，新的按钮控件出现在 <xref:System.Windows.Forms.TableLayoutPanel> 控件的第一个单元格中。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-220">Note that a new button control appears in the <xref:System.Windows.Forms.TableLayoutPanel> control's first cell.</span></span>

3. <span data-ttu-id="8a2b1-221">再次双击 <xref:System.Windows.Forms.Button> **工具箱** 中的控件图标。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-221">Double-click the <xref:System.Windows.Forms.Button> control icon in the **Toolbox** twice more.</span></span> <span data-ttu-id="8a2b1-222">这会在控件中保留一个空单元 <xref:System.Windows.Forms.TableLayoutPanel> 。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-222">This leaves one empty cell in the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="8a2b1-223">将 <xref:System.Windows.Forms.Button> 控件从 " **工具箱** " 拖到控件的空单元中 <xref:System.Windows.Forms.TableLayoutPanel> 。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-223">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the empty cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="8a2b1-224">请注意，不会显示对齐线。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-224">Note that no snaplines appear.</span></span>

5. <span data-ttu-id="8a2b1-225">将 <xref:System.Windows.Forms.Button> 控件拖出 <xref:System.Windows.Forms.TableLayoutPanel> 控件，并将其移动到 <xref:System.Windows.Forms.TableLayoutPanel> 控件上。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-225">Drag the <xref:System.Windows.Forms.Button> control out of the <xref:System.Windows.Forms.TableLayoutPanel> control and move it around the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="8a2b1-226">请注意，对齐线将再次出现。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-226">Note that snaplines appear again.</span></span>

## <a name="disable-snaplines"></a><span data-ttu-id="8a2b1-227">禁用对齐线</span><span class="sxs-lookup"><span data-stu-id="8a2b1-227">Disable snaplines</span></span>

<span data-ttu-id="8a2b1-228">按 **Alt** 键，同时在窗体中移动控件。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-228">Press the **Alt** key and while moving a control around the form.</span></span>

<span data-ttu-id="8a2b1-229">不会出现对齐线，并且控件不会对齐任何可能的对齐位置。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-229">No snaplines appear and the control does not snap to any potential alignment positions.</span></span>

### <a name="to-disable-snaplines-in-the-design-environment"></a><span data-ttu-id="8a2b1-230">禁用设计环境中的对齐线</span><span class="sxs-lookup"><span data-stu-id="8a2b1-230">To disable snaplines in the design environment</span></span>

1. <span data-ttu-id="8a2b1-231">从 " **工具** " 菜单中，打开 " **选项** " 对话框。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-231">From the **Tools** menu, open the **Options** dialog box.</span></span> <span data-ttu-id="8a2b1-232">选择 **Windows 窗体设计器**。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-232">Select **Windows Forms Designer**.</span></span>

2. <span data-ttu-id="8a2b1-233">选择 " **常规** " 节点。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-233">Select the **General** node.</span></span> <span data-ttu-id="8a2b1-234">在 " **布局模式** " 部分中，将所选内容从 **对齐线** 更改为 " **对齐**"。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-234">In the **Layout Mode** section, change the selection from **SnapLines** to **SnapToGrid**.</span></span>

3. <span data-ttu-id="8a2b1-235">选择 **"确定"** 以应用设置。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-235">Select **OK** to apply the setting.</span></span>

4. <span data-ttu-id="8a2b1-236">选择窗体上的控件，并将其移动到其他控件上。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-236">Select a control on your form and move it around the other controls.</span></span> <span data-ttu-id="8a2b1-237">请注意，不会显示对齐线。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-237">Note that snaplines do not appear.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8a2b1-238">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8a2b1-238">Next steps</span></span>

<span data-ttu-id="8a2b1-239">对齐线提供了在窗体上对齐控件的直观方式。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-239">Snaplines offer an intuitive means of aligning controls on your form.</span></span> <span data-ttu-id="8a2b1-240">建议了解的其他内容包括：</span><span class="sxs-lookup"><span data-stu-id="8a2b1-240">Suggestions for more exploration include:</span></span>

- <span data-ttu-id="8a2b1-241">尝试将 <xref:System.Windows.Forms.GroupBox> 控件嵌套在另一个 <xref:System.Windows.Forms.GroupBox> 控件中。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-241">Try nesting a <xref:System.Windows.Forms.GroupBox> control within another <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="8a2b1-242">将 <xref:System.Windows.Forms.Button> 控件置于子控件内，并将其放在 <xref:System.Windows.Forms.GroupBox> 父 <xref:System.Windows.Forms.GroupBox> 控件中。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-242">Place a <xref:System.Windows.Forms.Button> control within the child <xref:System.Windows.Forms.GroupBox> control, and another within the parent <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="8a2b1-243">移动 <xref:System.Windows.Forms.Button> 控件以查看对齐线跨容器边界的方式。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-243">Move the <xref:System.Windows.Forms.Button> controls around to see how the snaplines cross container boundaries.</span></span>

- <span data-ttu-id="8a2b1-244">创建列 <xref:System.Windows.Forms.TextBox> 控件和相应的 <xref:System.Windows.Forms.Label> 控件列。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-244">Create a column of <xref:System.Windows.Forms.TextBox> controls and a corresponding column of <xref:System.Windows.Forms.Label> controls.</span></span> <span data-ttu-id="8a2b1-245">将控件的属性值设置 <xref:System.Windows.Forms.Label> <xref:System.Windows.Forms.Control.AutoSize%2A> 为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-245">Set the value of the <xref:System.Windows.Forms.Label> controls' <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="8a2b1-246">使用对齐线移动 <xref:System.Windows.Forms.Label> 控件，使其显示的文本与控件中的文本对齐 <xref:System.Windows.Forms.TextBox> 。</span><span class="sxs-lookup"><span data-stu-id="8a2b1-246">Use snaplines to move the <xref:System.Windows.Forms.Label> controls so their displayed text is aligned with the text in the <xref:System.Windows.Forms.TextBox> controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a2b1-247">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a2b1-247">See also</span></span>

- <xref:System.Windows.Forms.Design.Behavior.SnapLine>
- [<span data-ttu-id="8a2b1-248">演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="8a2b1-248">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="8a2b1-249">演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="8a2b1-249">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="8a2b1-250">演练：使用 Padding、Margins 和 AutoSize 属性对 Windows 窗体控件进行布局</span><span class="sxs-lookup"><span data-stu-id="8a2b1-250">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
