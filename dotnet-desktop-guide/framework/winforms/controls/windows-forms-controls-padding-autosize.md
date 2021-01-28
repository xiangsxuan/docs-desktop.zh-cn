---
title: 用填充、边距和 AutoSize 属性对控件进行布局
ms.date: 03/30/2017
f1_keywords:
- Margin.Bottom
- Margin.Left
- Margin.Top
- Margin.All
- Margin.Right
helpviewer_keywords:
- Margin property [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], layout
- AutoSize property [Windows Forms], walkthroughs
- Padding property [Windows Forms], walkthroughs
- layout [Windows Forms], margins and padding
- Windows Forms, layout
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
ms.openlocfilehash: 84b1a5d20d273bb9dee6e7f97cf8bd569e5e97ab
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957573"
---
# <a name="walkthrough-lay-out-controls-with-padding-margins-and-the-autosize-property"></a><span data-ttu-id="5dbe1-102">演练：按填充、边距和 AutoSize 属性对控件进行布局</span><span class="sxs-lookup"><span data-stu-id="5dbe1-102">Walkthrough: Lay out controls with padding, margins, and the AutoSize property</span></span>

<span data-ttu-id="5dbe1-103">在窗体上精确地放置控件对于许多应用程序而言是高优先级。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="5dbe1-104">Visual Studio 中的 **Windows 窗体设计器** 提供了许多布局工具来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-104">The **Windows Forms Designer** in Visual Studio gives you many layout tools to accomplish this.</span></span> <span data-ttu-id="5dbe1-105">其中三个最重要的 <xref:System.Windows.Forms.Control.Margin%2A> 属性是、 <xref:System.Windows.Forms.Control.Padding%2A> 和 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性，它们存在于所有 Windows 窗体控件中。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-105">Three of the most important are the <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>, and <xref:System.Windows.Forms.Control.AutoSize%2A> properties, which are present on all Windows Forms controls.</span></span>

<span data-ttu-id="5dbe1-106"><xref:System.Windows.Forms.Control.Margin%2A> 属性定义控件周围的空间，该空间使其他控件与该控件的边框保持指定的距离。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-106">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>

<span data-ttu-id="5dbe1-107"><xref:System.Windows.Forms.Control.Padding%2A> 属性定义控件内部的空间，该空间使控件的内容（例如，其 <xref:System.Windows.Forms.Control.Text%2A> 属性的值）与该控件的边框保持指定的距离。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-107">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>

<span data-ttu-id="5dbe1-108">下图显示控件上的 <xref:System.Windows.Forms.Control.Padding%2A> 和 <xref:System.Windows.Forms.Control.Margin%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-108">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>

![Windows 窗体控件的填充和边距](./media/vs-winformpadmargin.gif)

<span data-ttu-id="5dbe1-110"><xref:System.Windows.Forms.Control.AutoSize%2A>属性告知控件自动调整其内容的大小。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-110">The <xref:System.Windows.Forms.Control.AutoSize%2A> property tells a control to automatically size itself to its contents.</span></span> <span data-ttu-id="5dbe1-111">它不会将其大小调整为小于其原始属性的值 <xref:System.Windows.Forms.Control.Size%2A> ，并且将会考虑其属性的值 <xref:System.Windows.Forms.Control.Padding%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-111">It will not resize itself to be smaller than the value of its original <xref:System.Windows.Forms.Control.Size%2A> property, and it will account for the value of its <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5dbe1-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="5dbe1-112">Prerequisites</span></span>

<span data-ttu-id="5dbe1-113">需要 Visual Studio 才能完成此演练。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-113">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="5dbe1-114">创建项目</span><span class="sxs-lookup"><span data-stu-id="5dbe1-114">Create the project</span></span>

1. <span data-ttu-id="5dbe1-115">在 Visual Studio 中，创建一个名为的 **Windows 应用程序** 项目 `LayoutExample` 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-115">In Visual Studio, create a **Windows Application** project called `LayoutExample`.</span></span>

2. <span data-ttu-id="5dbe1-116">在 **Windows 窗体设计器** 中选择窗体。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-116">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="set-margins-for-controls"></a><span data-ttu-id="5dbe1-117">设置控件的边距</span><span class="sxs-lookup"><span data-stu-id="5dbe1-117">Set margins for controls</span></span>

<span data-ttu-id="5dbe1-118">您可以使用属性设置控件之间的默认距离 <xref:System.Windows.Forms.Control.Margin%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-118">You can set the default distance between your controls using the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span> <span data-ttu-id="5dbe1-119">当您将控件向右移动到另一个控件时，将看到显示两个控件的边距的对齐线。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-119">When you move a control close enough to another control, you will see a snapline that shows the margins for the two controls.</span></span> <span data-ttu-id="5dbe1-120">您要移动的控件也将与边距定义的距离对齐。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-120">The control you are moving will also snap to the distance defined by the margins.</span></span>

### <a name="arrange-controls-on-your-form-using-the-margin-property"></a><span data-ttu-id="5dbe1-121">使用 Margin 属性排列窗体上的控件</span><span class="sxs-lookup"><span data-stu-id="5dbe1-121">Arrange controls on your form using the Margin property</span></span>

1. <span data-ttu-id="5dbe1-122">将两个 <xref:System.Windows.Forms.Button> 控件从 **工具箱** 拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-122">Drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="5dbe1-123">选择其中一个 <xref:System.Windows.Forms.Button> 控件，并将其移动到另一个控件，直到它们接近。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-123">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other, until they are almost touching.</span></span>

   <span data-ttu-id="5dbe1-124">观察它们之间出现的对齐线。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-124">Observe the snapline that appears between them.</span></span> <span data-ttu-id="5dbe1-125">此距离是两个控件值的总和 <xref:System.Windows.Forms.Control.Margin%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-125">This distance is the sum of the two controls' <xref:System.Windows.Forms.Control.Margin%2A> values.</span></span> <span data-ttu-id="5dbe1-126">正在移动的控件将对齐到此距离。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-126">The control you are moving snaps to this distance.</span></span> <span data-ttu-id="5dbe1-127">有关详细信息，请参阅 [演练：使用对齐线排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-127">For details, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

3. <span data-ttu-id="5dbe1-128">通过在 <xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Control.Margin%2A> " **属性** " 窗口中展开条目并将 <xref:System.Windows.Forms.Padding.All%2A> 属性设置为 **20**，可更改其中一个控件的属性。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-128">Change the <xref:System.Windows.Forms.Control.Margin%2A> property of one of the controls by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **20**.</span></span>

4. <span data-ttu-id="5dbe1-129">选择其中一个 <xref:System.Windows.Forms.Button> 控件，并将其移动到另一个控件。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-129">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other.</span></span>

   <span data-ttu-id="5dbe1-130">定义边距值的和的对齐线会更长，并使控件与其他控件对齐。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-130">The snapline defining the sum of the margin values is longer and that the control snaps to a greater distance from the other control.</span></span>

5. <span data-ttu-id="5dbe1-131">通过在 <xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Control.Margin%2A> " **属性** " 窗口中展开条目并将 <xref:System.Windows.Forms.Padding.Top%2A> 属性设置为 **5** 来更改所选控件的属性。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-131">Change the <xref:System.Windows.Forms.Control.Margin%2A> property of the selected control by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.Top%2A> property to **5**.</span></span>

6. <span data-ttu-id="5dbe1-132">将所选控件移动到另一个控件的下方，并观察对齐线是否更短。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-132">Move the selected control below the other control and observe that the snapline is shorter.</span></span> <span data-ttu-id="5dbe1-133">将所选控件移动到另一个控件的左侧，并观察对齐线是否保留步骤4中观测到的值。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-133">Move the selected control to the left of the other control and observe that the snapline retains the value observed in step 4.</span></span>

7. <span data-ttu-id="5dbe1-134">可以将属性的每个方面分别设置 <xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Padding.Left%2A> <xref:System.Windows.Forms.Padding.Top%2A> 为不同的值，也可以将 <xref:System.Windows.Forms.Padding.Right%2A> <xref:System.Windows.Forms.Padding.Bottom%2A> 其设置为与属性相同的值 <xref:System.Windows.Forms.Padding.All%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-134">You can set each of the aspects of the <xref:System.Windows.Forms.Control.Margin%2A> property, <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>, to different values, or you can set them all to the same value with the <xref:System.Windows.Forms.Padding.All%2A> property.</span></span>

## <a name="set-padding-for-controls"></a><span data-ttu-id="5dbe1-135">为控件设置填充</span><span class="sxs-lookup"><span data-stu-id="5dbe1-135">Set padding for controls</span></span>

<span data-ttu-id="5dbe1-136">若要实现应用程序所需的精确布局，控件通常会包含子控件。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-136">To achieve the precise layout required for your application, your controls will often contain child controls.</span></span> <span data-ttu-id="5dbe1-137">若要指定子控件边框到父控件边框的邻近性，请结合使用父控件的 <xref:System.Windows.Forms.Control.Padding%2A> 属性和子控件的 <xref:System.Windows.Forms.Control.Margin%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-137">When you want to specify the proximity of the child control's border to the parent control's border, use the parent control's <xref:System.Windows.Forms.Control.Padding%2A> property in conjunction with the child control's <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span> <span data-ttu-id="5dbe1-138"><xref:System.Windows.Forms.Control.Padding%2A>属性还可用于控制控件内容的邻近性 (例如，将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Text%2A> 属性) 到其边框。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-138">The <xref:System.Windows.Forms.Control.Padding%2A> property is also used to control the proximity of a control's content (for example, a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property) to its borders.</span></span>

### <a name="arrange-controls-on-your-form-using-padding"></a><span data-ttu-id="5dbe1-139">使用填充排列窗体上的控件</span><span class="sxs-lookup"><span data-stu-id="5dbe1-139">Arrange controls on your form using padding</span></span>

1. <span data-ttu-id="5dbe1-140">从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-140">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="5dbe1-141">将控件的属性值更改 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.AutoSize%2A> 为 **true**。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-141">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

3. <span data-ttu-id="5dbe1-142"><xref:System.Windows.Forms.Control.Padding%2A>通过 <xref:System.Windows.Forms.Control.Padding%2A> 在 "**属性**" 窗口中展开条目并将 <xref:System.Windows.Forms.Padding.All%2A> 属性设置为 **5** 来更改属性。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-142">Change the <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **5**.</span></span>

   <span data-ttu-id="5dbe1-143">控件将展开以为新的填充提供空间。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-143">The control expands to provide room for the new padding.</span></span>

4. <span data-ttu-id="5dbe1-144">从 <xref:System.Windows.Forms.GroupBox> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-144">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="5dbe1-145">将 <xref:System.Windows.Forms.Button> 控件从 " **工具箱** " 拖放到 <xref:System.Windows.Forms.GroupBox> 控件中。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-145">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="5dbe1-146">定位 <xref:System.Windows.Forms.Button> 控件，使其与控件的右下角齐平 <xref:System.Windows.Forms.GroupBox> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-146">Position the <xref:System.Windows.Forms.Button> control so it is flush with the lower-right corner of the <xref:System.Windows.Forms.GroupBox> control.</span></span>

   <span data-ttu-id="5dbe1-147">观察控件在控件 <xref:System.Windows.Forms.Button> 接近控件的下边框和右边框时显示的对齐线 <xref:System.Windows.Forms.GroupBox> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-147">Observe the snaplines that appear as the <xref:System.Windows.Forms.Button> control approaches the bottom and right borders of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="5dbe1-148">这些对齐线与 <xref:System.Windows.Forms.Control.Margin%2A> 的属性相对应 <xref:System.Windows.Forms.Button> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-148">These snaplines correspond to the <xref:System.Windows.Forms.Control.Margin%2A> property of the <xref:System.Windows.Forms.Button>.</span></span>

5. <span data-ttu-id="5dbe1-149"><xref:System.Windows.Forms.GroupBox> <xref:System.Windows.Forms.Control.Padding%2A> 通过 <xref:System.Windows.Forms.Control.Padding%2A> 在 "**属性**" 窗口中展开条目并将 <xref:System.Windows.Forms.Padding.All%2A> 属性设置为 **20**，可更改控件的属性。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-149">Change the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **20**.</span></span>

6. <span data-ttu-id="5dbe1-150">选择 <xref:System.Windows.Forms.Button> 控件内的控件 <xref:System.Windows.Forms.GroupBox> ，并将其移动到的中心 <xref:System.Windows.Forms.GroupBox> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-150">Select the <xref:System.Windows.Forms.Button> control within the <xref:System.Windows.Forms.GroupBox> control and move it toward the center of the <xref:System.Windows.Forms.GroupBox>.</span></span>

   <span data-ttu-id="5dbe1-151">对齐线的显示距离控件边框更远 <xref:System.Windows.Forms.GroupBox> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-151">The snaplines appear at a greater distance from the borders of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="5dbe1-152">此距离是 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Margin%2A> 属性和 <xref:System.Windows.Forms.GroupBox> 控件的属性的总和 <xref:System.Windows.Forms.Control.Padding%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-152">This distance is the sum of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Margin%2A> property and the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>

## <a name="size-controls-automatically"></a><span data-ttu-id="5dbe1-153">自动调整控件大小</span><span class="sxs-lookup"><span data-stu-id="5dbe1-153">Size controls automatically</span></span>

<span data-ttu-id="5dbe1-154">在某些应用程序中，控件的大小在运行时与设计时的大小不相同。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-154">In some applications, the size of a control will not be the same at run time as it was at design time.</span></span> <span data-ttu-id="5dbe1-155"><xref:System.Windows.Forms.Button>例如，可以从数据库中获取控件的文本，并且该文本的长度事先未知。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-155">The text of a <xref:System.Windows.Forms.Button> control, for example, may be taken from a database, and its length are not known in advance.</span></span>

<span data-ttu-id="5dbe1-156">当 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性设置为时 `true` ，控件将自行调整其内容大小。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-156">When the <xref:System.Windows.Forms.Control.AutoSize%2A> property is set to `true`, the control will size itself to its content.</span></span> <span data-ttu-id="5dbe1-157">有关详细信息，请参阅 [AutoSize 属性概述](autosize-property-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-157">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

### <a name="arrange-controls-on-your-form-using-the-autosize-property"></a><span data-ttu-id="5dbe1-158">使用 AutoSize 属性排列窗体上的控件</span><span class="sxs-lookup"><span data-stu-id="5dbe1-158">Arrange controls on your form using the AutoSize property</span></span>

1. <span data-ttu-id="5dbe1-159">从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-159">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="5dbe1-160">将控件的属性值更改 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.AutoSize%2A> 为 **true**。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-160">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

3. <span data-ttu-id="5dbe1-161">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Text%2A> 属性更改为 **此按钮的 Text 属性的长字符串**。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-161">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to **This button has a long string for its Text property**.</span></span>

   <span data-ttu-id="5dbe1-162">提交更改时， <xref:System.Windows.Forms.Button> 控件会自行调整大小以适应新文本。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-162">When you commit the change, the <xref:System.Windows.Forms.Button> control resizes itself to fit the new text.</span></span>

4. <span data-ttu-id="5dbe1-163">将另一个 <xref:System.Windows.Forms.Button> 控件从 **工具箱** 拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-163">Drag another <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

5. <span data-ttu-id="5dbe1-164">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Text%2A> 属性更改为 "**此按钮的文本属性具有长字符串。**"</span><span class="sxs-lookup"><span data-stu-id="5dbe1-164">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property.**"</span></span>

   <span data-ttu-id="5dbe1-165">提交更改时， <xref:System.Windows.Forms.Button> 控件不会调整其自身的大小，而是由控件的右边缘剪切文本。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-165">When you commit the change, the <xref:System.Windows.Forms.Button> control does not resize itself, and the text is clipped by the right edge of the control.</span></span>

6. <span data-ttu-id="5dbe1-166"><xref:System.Windows.Forms.Control.Padding%2A>通过 <xref:System.Windows.Forms.Control.Padding%2A> 在 "**属性**" 窗口中展开条目并将 <xref:System.Windows.Forms.Padding.All%2A> 属性设置为 **5** 来更改属性。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-166">Change the <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **5**.</span></span>

   <span data-ttu-id="5dbe1-167">控件内部的文本在所有四个边都被剪切。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-167">The text in the control's interior is clipped on all four sides.</span></span>

7. <span data-ttu-id="5dbe1-168">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性更改为 **true**。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-168">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

   <span data-ttu-id="5dbe1-169"><xref:System.Windows.Forms.Button>控件调整自身大小以包含整个字符串。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-169">The <xref:System.Windows.Forms.Button> control resizes itself to encompass the entire string.</span></span> <span data-ttu-id="5dbe1-170">此外，还会围绕文本添加填充，从而导致 <xref:System.Windows.Forms.Button> 控件在四个方向上都展开。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-170">Also, padding has been added around the text, causing the <xref:System.Windows.Forms.Button> control to expand in all four directions.</span></span>

8. <span data-ttu-id="5dbe1-171">从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-171">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="5dbe1-172">将其放置在窗体右下角附近。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-172">Position it near the lower-right corner of the form.</span></span>

9. <span data-ttu-id="5dbe1-173">将控件的属性值更改 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.AutoSize%2A> 为 **true**。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-173">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

10. <span data-ttu-id="5dbe1-174">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性设置为 <xref:System.Windows.Forms.AnchorStyles.Right> ， <xref:System.Windows.Forms.AnchorStyles.Bottom> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-174">Set the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>.</span></span>

11. <span data-ttu-id="5dbe1-175">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Text%2A> 属性更改为 "**此按钮的文本属性具有长字符串。**"</span><span class="sxs-lookup"><span data-stu-id="5dbe1-175">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property.**"</span></span>

   <span data-ttu-id="5dbe1-176">当你提交更改时， <xref:System.Windows.Forms.Button> 控件会向左调整控件的大小。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-176">When you commit the change, the <xref:System.Windows.Forms.Button> control resizes itself toward the left.</span></span> <span data-ttu-id="5dbe1-177">通常，自动调整大小会使控件在其属性设置的方向上增加 <xref:System.Windows.Forms.Control.Anchor%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-177">In general, automatic sizing will increase the size of a control in the direction opposite its <xref:System.Windows.Forms.Control.Anchor%2A> property setting.</span></span>

## <a name="autosize-and-autosizemode-properties"></a><span data-ttu-id="5dbe1-178">AutoSize 和 AutoSizeMode 属性</span><span class="sxs-lookup"><span data-stu-id="5dbe1-178">AutoSize and AutoSizeMode properties</span></span>

 <span data-ttu-id="5dbe1-179">某些控件支持 `AutoSizeMode` 属性，这使你可以更精细地控制控件的自动调整大小行为。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-179">Some controls support the `AutoSizeMode` property, which gives you more fine-grained control over the automatic sizing behavior of a control.</span></span>

### <a name="use-the-autosizemode-property"></a><span data-ttu-id="5dbe1-180">使用 AutoSizeMode 属性</span><span class="sxs-lookup"><span data-stu-id="5dbe1-180">Use the AutoSizeMode property</span></span>

1. <span data-ttu-id="5dbe1-181">从 <xref:System.Windows.Forms.Panel> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-181">Drag a <xref:System.Windows.Forms.Panel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="5dbe1-182">将控件的属性的值设置 <xref:System.Windows.Forms.Panel> <xref:System.Windows.Forms.Control.AutoSize%2A> 为 **true**。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-182">Set the value of the <xref:System.Windows.Forms.Panel> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

3. <span data-ttu-id="5dbe1-183">将 <xref:System.Windows.Forms.Button> 控件从 " **工具箱** " 拖放到 <xref:System.Windows.Forms.Panel> 控件中。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-183">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.Panel> control.</span></span>

4. <span data-ttu-id="5dbe1-184">将控件放置在 <xref:System.Windows.Forms.Button> 控件的右下角附近 <xref:System.Windows.Forms.Panel> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-184">Place the <xref:System.Windows.Forms.Button> control near the lower-right corner of the <xref:System.Windows.Forms.Panel> control.</span></span>

5. <span data-ttu-id="5dbe1-185">选择 <xref:System.Windows.Forms.Panel> 控件并抓住右下的大小调整控点。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-185">Select the <xref:System.Windows.Forms.Panel> control and grab the lower-right sizing handle.</span></span> <span data-ttu-id="5dbe1-186">将控件的大小调整 <xref:System.Windows.Forms.Panel> 为更大、更小。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-186">Resize the <xref:System.Windows.Forms.Panel> control to be larger and smaller.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5dbe1-187">您可以随意调整 <xref:System.Windows.Forms.Panel> 控件大小，但不能将其大小调整为小于 <xref:System.Windows.Forms.Button> 控件右下角的位置。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-187">You can freely resize the <xref:System.Windows.Forms.Panel> control, but you cannot size it smaller than the position of the <xref:System.Windows.Forms.Button> control's lower-right corner.</span></span> <span data-ttu-id="5dbe1-188">此行为由属性的默认值指定，即 `AutoSizeMode` <xref:System.Windows.Forms.AutoSizeMode.GrowOnly> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-188">This behavior is specified by the default value of the `AutoSizeMode` property, which is <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>.</span></span>

6. <span data-ttu-id="5dbe1-189">将控件的属性的值设置 <xref:System.Windows.Forms.Panel> `AutoSizeMode` 为 <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-189">Set the value of the <xref:System.Windows.Forms.Panel> control's `AutoSizeMode` property to <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>.</span></span>

   <span data-ttu-id="5dbe1-190"><xref:System.Windows.Forms.Panel>控件自行调整大小以包围 <xref:System.Windows.Forms.Button> 控件。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-190">The <xref:System.Windows.Forms.Panel> control sizes itself to surround the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="5dbe1-191">无法调整控件的大小 <xref:System.Windows.Forms.Panel> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-191">You cannot resize the <xref:System.Windows.Forms.Panel> control.</span></span>

7. <span data-ttu-id="5dbe1-192">将控件拖动到 <xref:System.Windows.Forms.Button> 控件的左上角 <xref:System.Windows.Forms.Panel> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-192">Drag the <xref:System.Windows.Forms.Button> control toward the upper-left corner of the <xref:System.Windows.Forms.Panel> control.</span></span>

   <span data-ttu-id="5dbe1-193"><xref:System.Windows.Forms.Panel>控件的大小调整为 <xref:System.Windows.Forms.Button> 控件的新位置。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-193">The <xref:System.Windows.Forms.Panel> control resizes to the <xref:System.Windows.Forms.Button> control's new position.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5dbe1-194">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5dbe1-194">Next steps</span></span>

<span data-ttu-id="5dbe1-195">在 Windows 窗体应用程序中排列控件还有很多其他布局功能。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-195">There are many other layout features for arranging controls in your Windows Forms applications.</span></span> <span data-ttu-id="5dbe1-196">下面是可以尝试的一些组合：</span><span class="sxs-lookup"><span data-stu-id="5dbe1-196">Here are some combinations you might try:</span></span>

- <span data-ttu-id="5dbe1-197">使用控件生成窗体 <xref:System.Windows.Forms.TableLayoutPanel> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-197">Build a form using a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="5dbe1-198">有关详细信息，请参阅 [演练：使用 TableLayoutPanel 排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-198">For details, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span> <span data-ttu-id="5dbe1-199">尝试更改控件的属性的值以及其子 <xref:System.Windows.Forms.TableLayoutPanel> <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.Control.Margin%2A> 控件的属性。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-199">Try changing the values of the <xref:System.Windows.Forms.TableLayoutPanel> control's <xref:System.Windows.Forms.Control.Padding%2A> property, as well as the <xref:System.Windows.Forms.Control.Margin%2A> property on its child controls.</span></span>

- <span data-ttu-id="5dbe1-200">使用控件尝试相同的试验 <xref:System.Windows.Forms.FlowLayoutPanel> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-200">Try the same experiment using a <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span> <span data-ttu-id="5dbe1-201">有关详细信息，请参阅 [演练：使用 FlowLayoutPanel 排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-201">For details, see [Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span></span>

- <span data-ttu-id="5dbe1-202">尝试在控件中停靠子控件 <xref:System.Windows.Forms.Panel> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-202">Experiment with docking child controls in a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="5dbe1-203"><xref:System.Windows.Forms.Control.Padding%2A>属性是对属性的更通用的实现 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> ，您可以通过在控件中放置一个子控件 <xref:System.Windows.Forms.Panel> 并将子控件的 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为来自行满足这种情况 <xref:System.Windows.Forms.DockStyle.Fill> 。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-203">The <xref:System.Windows.Forms.Control.Padding%2A> property is a more general realization of the <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> property, and you can satisfy yourself that this is the case by putting a child control in a <xref:System.Windows.Forms.Panel> control and setting the child control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="5dbe1-204">将 <xref:System.Windows.Forms.Panel> 控件的 <xref:System.Windows.Forms.Control.Padding%2A> 属性设置为不同的值并记下该效果。</span><span class="sxs-lookup"><span data-stu-id="5dbe1-204">Set the <xref:System.Windows.Forms.Panel> control's <xref:System.Windows.Forms.Control.Padding%2A> property to various values and note the effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="5dbe1-205">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5dbe1-205">See also</span></span>

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [<span data-ttu-id="5dbe1-206">AutoSize 属性概述</span><span class="sxs-lookup"><span data-stu-id="5dbe1-206">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="5dbe1-207">演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="5dbe1-207">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="5dbe1-208">演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="5dbe1-208">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="5dbe1-209">演练：使用对齐线在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="5dbe1-209">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
