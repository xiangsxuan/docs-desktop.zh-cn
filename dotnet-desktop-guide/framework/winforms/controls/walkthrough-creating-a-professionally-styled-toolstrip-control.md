---
title: 演练：创建具有专业样式的 ToolStrip 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
ms.openlocfilehash: 3fd9175f47f9f1b35743dc69b462227fdfafe55d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972867"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="fd728-102">演练：创建具有专业样式的 ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="fd728-102">Walkthrough: Creating a Professionally Styled ToolStrip Control</span></span>

<span data-ttu-id="fd728-103">可以 <xref:System.Windows.Forms.ToolStrip> 通过编写自己的从类型派生的类，为应用程序的控件指定专业外观和行为 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 。</span><span class="sxs-lookup"><span data-stu-id="fd728-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>

<span data-ttu-id="fd728-104">本演练演示如何使用 <xref:System.Windows.Forms.ToolStrip> 控件来创建与 Microsoft® Outlook®提供的 **导航窗格** 类似的复合控件。</span><span class="sxs-lookup"><span data-stu-id="fd728-104">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that resembles the **Navigation Pane** provided by Microsoft® Outlook®.</span></span> <span data-ttu-id="fd728-105">此演练演示了下列任务：</span><span class="sxs-lookup"><span data-stu-id="fd728-105">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="fd728-106">创建 Windows 控件库项目。</span><span class="sxs-lookup"><span data-stu-id="fd728-106">Creating a Windows Control Library project.</span></span>

- <span data-ttu-id="fd728-107">设计 System.windows.forms.toolstrip.stackview 控件。</span><span class="sxs-lookup"><span data-stu-id="fd728-107">Designing the StackView Control.</span></span>

- <span data-ttu-id="fd728-108">实现自定义呈现器。</span><span class="sxs-lookup"><span data-stu-id="fd728-108">Implementing a Custom Renderer.</span></span>

<span data-ttu-id="fd728-109">完成后，将拥有一个可重复使用的自定义客户端控件，该控件具有专业外观 Microsoft Office® XP 控件。</span><span class="sxs-lookup"><span data-stu-id="fd728-109">When you are finished, you will have a reusable custom client control with the professional appearance of a Microsoft Office® XP control.</span></span>

<span data-ttu-id="fd728-110">若要将本主题中的代码复制为单个列表，请参阅 [如何：创建具有专业样式的 ToolStrip 控件](how-to-create-a-professionally-styled-toolstrip-control.md)。</span><span class="sxs-lookup"><span data-stu-id="fd728-110">To copy the code in this topic as a single listing, see [How to: Create a Professionally Styled ToolStrip Control](how-to-create-a-professionally-styled-toolstrip-control.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fd728-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="fd728-111">Prerequisites</span></span>

<span data-ttu-id="fd728-112">需要 Visual Studio 才能完成此演练。</span><span class="sxs-lookup"><span data-stu-id="fd728-112">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="fd728-113">创建控件库项目</span><span class="sxs-lookup"><span data-stu-id="fd728-113">Create the control library project</span></span>

1. <span data-ttu-id="fd728-114">在 Visual Studio 中，创建一个名为的新 Windows 控件库项目 `StackViewLibrary` 。</span><span class="sxs-lookup"><span data-stu-id="fd728-114">In Visual Studio, create a new Windows Control Library project named `StackViewLibrary`.</span></span>

2. <span data-ttu-id="fd728-115">在 **解决方案资源管理器** 中，通过删除名为 "UserControl1.cs" 或 "UserControl1" 的源文件来删除项目的默认控件，具体取决于你选择的语言。</span><span class="sxs-lookup"><span data-stu-id="fd728-115">In **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>

     <span data-ttu-id="fd728-116">有关详细信息，请参阅 [如何：删除、删除和排除项](/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="fd728-116">For more information, see [How to: Remove, Delete, and Exclude Items](/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

3. <span data-ttu-id="fd728-117">向 <xref:System.Windows.Forms.UserControl> **StackViewLibrary** 项目添加一个新项。</span><span class="sxs-lookup"><span data-stu-id="fd728-117">Add a new <xref:System.Windows.Forms.UserControl> item to the **StackViewLibrary** project.</span></span> <span data-ttu-id="fd728-118">为新的源文件指定基名称 `StackView` 。</span><span class="sxs-lookup"><span data-stu-id="fd728-118">Give the new source file a base name of `StackView`.</span></span>

## <a name="design-the-stackview-control"></a><span data-ttu-id="fd728-119">设计 System.windows.forms.toolstrip.stackview 控件</span><span class="sxs-lookup"><span data-stu-id="fd728-119">Design the StackView control</span></span>

<span data-ttu-id="fd728-120">`StackView`控件是具有一个子控件的复合控件 <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="fd728-120">The `StackView` control is a composite control with one child <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="fd728-121">有关复合控件的详细信息，请参阅 [各种自定义控件](varieties-of-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="fd728-121">For more information about composite controls, see [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>

1. <span data-ttu-id="fd728-122">从 " **工具箱**" 中，将 <xref:System.Windows.Forms.ToolStrip> 控件拖动到设计图面。</span><span class="sxs-lookup"><span data-stu-id="fd728-122">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStrip> control to the design surface.</span></span>

2. <span data-ttu-id="fd728-123">在 " **属性** " 窗口中， <xref:System.Windows.Forms.ToolStrip> 根据下表设置控件的属性。</span><span class="sxs-lookup"><span data-stu-id="fd728-123">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStrip> control's properties according to the following table.</span></span>

    |<span data-ttu-id="fd728-124">属性</span><span class="sxs-lookup"><span data-stu-id="fd728-124">Property</span></span>|<span data-ttu-id="fd728-125">值</span><span class="sxs-lookup"><span data-stu-id="fd728-125">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="fd728-126">名称</span><span class="sxs-lookup"><span data-stu-id="fd728-126">Name</span></span>|`stackStrip`|
    |<span data-ttu-id="fd728-127">CanOverflow</span><span class="sxs-lookup"><span data-stu-id="fd728-127">CanOverflow</span></span>|`false`|
    |<span data-ttu-id="fd728-128">程序坞</span><span class="sxs-lookup"><span data-stu-id="fd728-128">Dock</span></span>|<xref:System.Windows.Forms.DockStyle.Bottom>|
    |<span data-ttu-id="fd728-129">字体</span><span class="sxs-lookup"><span data-stu-id="fd728-129">Font</span></span>|`Tahoma, 10pt, style=Bold`|
    |<span data-ttu-id="fd728-130">GripStyle</span><span class="sxs-lookup"><span data-stu-id="fd728-130">GripStyle</span></span>|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|
    |<span data-ttu-id="fd728-131">LayoutStyle</span><span class="sxs-lookup"><span data-stu-id="fd728-131">LayoutStyle</span></span>|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|
    |<span data-ttu-id="fd728-132">填充</span><span class="sxs-lookup"><span data-stu-id="fd728-132">Padding</span></span>|`0, 7, 0, 0`|
    |<span data-ttu-id="fd728-133">RenderMode</span><span class="sxs-lookup"><span data-stu-id="fd728-133">RenderMode</span></span>|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|

3. <span data-ttu-id="fd728-134">在 Windows 窗体设计器中，单击 <xref:System.Windows.Forms.ToolStrip> 控件的 " **添加** " 按钮，并将添加 <xref:System.Windows.Forms.ToolStripButton> 到 `stackStrip` 控件。</span><span class="sxs-lookup"><span data-stu-id="fd728-134">In the Windows Forms Designer, click the <xref:System.Windows.Forms.ToolStrip> control's **Add** button and add a <xref:System.Windows.Forms.ToolStripButton> to the `stackStrip` control.</span></span>

4. <span data-ttu-id="fd728-135">在 " **属性** " 窗口中， <xref:System.Windows.Forms.ToolStripButton> 根据下表设置控件的属性。</span><span class="sxs-lookup"><span data-stu-id="fd728-135">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStripButton> control's properties according to the following table.</span></span>

    |<span data-ttu-id="fd728-136">属性</span><span class="sxs-lookup"><span data-stu-id="fd728-136">Property</span></span>|<span data-ttu-id="fd728-137">值</span><span class="sxs-lookup"><span data-stu-id="fd728-137">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="fd728-138">名称</span><span class="sxs-lookup"><span data-stu-id="fd728-138">Name</span></span>|`mailStackButton`|
    |<span data-ttu-id="fd728-139">CheckOnClick</span><span class="sxs-lookup"><span data-stu-id="fd728-139">CheckOnClick</span></span>|<span data-ttu-id="fd728-140">true</span><span class="sxs-lookup"><span data-stu-id="fd728-140">true</span></span>|
    |<span data-ttu-id="fd728-141">CheckState</span><span class="sxs-lookup"><span data-stu-id="fd728-141">CheckState</span></span>|<xref:System.Windows.Forms.CheckState.Checked>|
    |<span data-ttu-id="fd728-142">System.windows.forms.toolstripitem.displaystyle</span><span class="sxs-lookup"><span data-stu-id="fd728-142">DisplayStyle</span></span>|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|
    |<span data-ttu-id="fd728-143">ImageAlign</span><span class="sxs-lookup"><span data-stu-id="fd728-143">ImageAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|
    |<span data-ttu-id="fd728-144">ImageScaling</span><span class="sxs-lookup"><span data-stu-id="fd728-144">ImageScaling</span></span>|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|
    |<span data-ttu-id="fd728-145">ImageTransparentColor</span><span class="sxs-lookup"><span data-stu-id="fd728-145">ImageTransparentColor</span></span>|`238, 238, 238`|
    |<span data-ttu-id="fd728-146">Margin</span><span class="sxs-lookup"><span data-stu-id="fd728-146">Margin</span></span>|`0, 0, 0, 0`|
    |<span data-ttu-id="fd728-147">填充</span><span class="sxs-lookup"><span data-stu-id="fd728-147">Padding</span></span>|`3, 3, 3, 3`|
    |<span data-ttu-id="fd728-148">文本</span><span class="sxs-lookup"><span data-stu-id="fd728-148">Text</span></span>|<span data-ttu-id="fd728-149">**信**</span><span class="sxs-lookup"><span data-stu-id="fd728-149">**Mail**</span></span>|
    |<span data-ttu-id="fd728-150">TextAlign</span><span class="sxs-lookup"><span data-stu-id="fd728-150">TextAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|

5. <span data-ttu-id="fd728-151">对其他三个控件重复步骤 7 <xref:System.Windows.Forms.ToolStripButton> 。</span><span class="sxs-lookup"><span data-stu-id="fd728-151">Repeat step 7 for three more <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>

     <span data-ttu-id="fd728-152">将控件命名为 `calendarStackButton` 、 `contactsStackButton` 和 `tasksStackButton` 。</span><span class="sxs-lookup"><span data-stu-id="fd728-152">Name the controls `calendarStackButton`, `contactsStackButton`, and `tasksStackButton`.</span></span> <span data-ttu-id="fd728-153">分别将属性的值设置 <xref:System.Windows.Forms.Control.Text%2A> 为 " **日历**"、" **联系人**" 和 " **任务**"。</span><span class="sxs-lookup"><span data-stu-id="fd728-153">Set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to **Calendar**, **Contacts**, and **Tasks**, respectively.</span></span>

## <a name="handle-events"></a><span data-ttu-id="fd728-154">处理事件</span><span class="sxs-lookup"><span data-stu-id="fd728-154">Handle events</span></span>

<span data-ttu-id="fd728-155">为了使控件正常运行，两个事件很重要 `StackView` 。</span><span class="sxs-lookup"><span data-stu-id="fd728-155">Two events are important to make the `StackView` control behave correctly.</span></span> <span data-ttu-id="fd728-156">处理 <xref:System.Windows.Forms.UserControl.Load> 事件以正确定位控件。</span><span class="sxs-lookup"><span data-stu-id="fd728-156">Handle the <xref:System.Windows.Forms.UserControl.Load> event to position the control correctly.</span></span> <span data-ttu-id="fd728-157">处理 <xref:System.Windows.Forms.ToolStripItem.Click> 每个的事件 <xref:System.Windows.Forms.ToolStripButton> ，以使 `StackView` 控件状态行为与控件相似 <xref:System.Windows.Forms.RadioButton> 。</span><span class="sxs-lookup"><span data-stu-id="fd728-157">Handle the <xref:System.Windows.Forms.ToolStripItem.Click> event for each <xref:System.Windows.Forms.ToolStripButton> to give the `StackView` control state behavior similar to the <xref:System.Windows.Forms.RadioButton> control.</span></span>

1. <span data-ttu-id="fd728-158">在 Windows 窗体设计器中，选择 `StackView` 控件。</span><span class="sxs-lookup"><span data-stu-id="fd728-158">In the Windows Forms Designer, select the `StackView` control.</span></span>

2. <span data-ttu-id="fd728-159">在“属性”窗口中，单击“事件”。</span><span class="sxs-lookup"><span data-stu-id="fd728-159">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="fd728-160">双击 Load 事件以生成 `StackView_Load` 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="fd728-160">Double-click the Load event to generate the `StackView_Load` event handler.</span></span>

4. <span data-ttu-id="fd728-161">在 `StackView_Load` 事件处理程序中，复制并粘贴以下代码。</span><span class="sxs-lookup"><span data-stu-id="fd728-161">In the `StackView_Load` event handler, copy and paste the following code.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]

5. <span data-ttu-id="fd728-162">在 Windows 窗体设计器中，选择 `mailStackButton` 控件。</span><span class="sxs-lookup"><span data-stu-id="fd728-162">In the Windows Forms Designer, select the `mailStackButton` control.</span></span>

6. <span data-ttu-id="fd728-163">在“属性”窗口中，单击“事件”。</span><span class="sxs-lookup"><span data-stu-id="fd728-163">In the **Properties** window, click **Events**.</span></span>

7. <span data-ttu-id="fd728-164">双击 "Click" 事件。</span><span class="sxs-lookup"><span data-stu-id="fd728-164">Double-click the Click event.</span></span>

     <span data-ttu-id="fd728-165">Windows 窗体设计器生成 `mailStackButton_Click` 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="fd728-165">The Windows Forms Designer generates the `mailStackButton_Click` event handler.</span></span>

8. <span data-ttu-id="fd728-166">将 `mailStackButton_Click` 事件处理程序重命名为 `stackButton_Click` 。</span><span class="sxs-lookup"><span data-stu-id="fd728-166">Rename the `mailStackButton_Click` event handler to `stackButton_Click`.</span></span>

     <span data-ttu-id="fd728-167">有关详细信息，请参阅 [重命名代码符号重构](/visualstudio/ide/reference/rename)。</span><span class="sxs-lookup"><span data-stu-id="fd728-167">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

9. <span data-ttu-id="fd728-168">将以下代码插入到 `stackButton_Click` 事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="fd728-168">Insert the following code into the `stackButton_Click` event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]

10. <span data-ttu-id="fd728-169">在 Windows 窗体设计器中，选择 `calendarStackButton` 控件。</span><span class="sxs-lookup"><span data-stu-id="fd728-169">In the Windows Forms Designer, select the `calendarStackButton` control.</span></span>

11. <span data-ttu-id="fd728-170">在 " **属性** " 窗口中，将 Click 事件设置为 `stackButton_Click` 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="fd728-170">In the **Properties** window, set the Click event to the `stackButton_Click` event handler.</span></span>

12. <span data-ttu-id="fd728-171">对和控件重复步骤10和 `contactsStackButton` 11 `tasksStackButton` 。</span><span class="sxs-lookup"><span data-stu-id="fd728-171">Repeat steps 10 and 11 for the `contactsStackButton` and `tasksStackButton` controls.</span></span>

## <a name="define-icons"></a><span data-ttu-id="fd728-172">定义图标</span><span class="sxs-lookup"><span data-stu-id="fd728-172">Define icons</span></span>

<span data-ttu-id="fd728-173">每个 `StackView` 按钮都有一个关联的图标。</span><span class="sxs-lookup"><span data-stu-id="fd728-173">Each `StackView` button has an associated icon.</span></span> <span data-ttu-id="fd728-174">为方便起见，每个图标都表示为 Base64 编码的字符串，该字符串在从其创建之前进行反序列化 <xref:System.Drawing.Bitmap> 。</span><span class="sxs-lookup"><span data-stu-id="fd728-174">For convenience, each icon is represented as a Base64-encoded string, which is deserialized before a <xref:System.Drawing.Bitmap> is created from it.</span></span> <span data-ttu-id="fd728-175">在生产环境中，将位图数据存储为资源，并在 Windows 窗体设计器中显示图标。</span><span class="sxs-lookup"><span data-stu-id="fd728-175">In a production environment, you store bitmap data as a resource, and your icons appear in the Windows Forms Designer.</span></span> <span data-ttu-id="fd728-176">有关详细信息，请参阅 [如何：将背景图像添加到 Windows 窗体](/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="fd728-176">For more information, see [How to: Add Background Images to Windows Forms](/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span></span>

1. <span data-ttu-id="fd728-177">在代码编辑器中，将以下代码插入到 `StackView` 类定义中。</span><span class="sxs-lookup"><span data-stu-id="fd728-177">In the Code Editor, insert the following code into the `StackView` class definition.</span></span> <span data-ttu-id="fd728-178">此代码初始化图标的位图 <xref:System.Windows.Forms.ToolStripButton> 。</span><span class="sxs-lookup"><span data-stu-id="fd728-178">This code initializes the bitmaps for the <xref:System.Windows.Forms.ToolStripButton> icons.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]

2. <span data-ttu-id="fd728-179">`InitializeImages`在类构造函数中添加对方法的调用 `StackView` 。</span><span class="sxs-lookup"><span data-stu-id="fd728-179">Add a call to the `InitializeImages` method in the `StackView` class constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="implement-a-custom-renderer"></a><span data-ttu-id="fd728-180">实现自定义呈现器</span><span class="sxs-lookup"><span data-stu-id="fd728-180">Implement a custom renderer</span></span>

<span data-ttu-id="fd728-181">您可以自定义控件的大多数元素 `StackView` ，实现从类派生的类 <xref:System.Windows.Forms.ToolStripRenderer> 。</span><span class="sxs-lookup"><span data-stu-id="fd728-181">You can customize most elements of the `StackView` control my implementing a class that derives from the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="fd728-182">在此过程中，您将实现一个 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 类，该类自定义手柄并绘制控件的渐变背景 <xref:System.Windows.Forms.ToolStripButton> 。</span><span class="sxs-lookup"><span data-stu-id="fd728-182">In this procedure, you will implement a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class that customizes the grip and draws gradient backgrounds for the <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>

1. <span data-ttu-id="fd728-183">将以下代码插入 `StackView` 控件定义。</span><span class="sxs-lookup"><span data-stu-id="fd728-183">Insert the following code into the `StackView` control definition.</span></span>

     <span data-ttu-id="fd728-184">这是类的定义 `StackRenderer` ，它将重写 <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip> 、 <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder> 和 <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> 方法以生成自定义外观。</span><span class="sxs-lookup"><span data-stu-id="fd728-184">This is the definition for the `StackRenderer` class, which overrides the <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, and <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> methods to produce a custom appearance.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]

2. <span data-ttu-id="fd728-185">在 `StackView` 控件的构造函数中，创建类的新实例， `StackRenderer` 并将此实例分配给 `stackStrip` 控件的 <xref:System.Windows.Forms.ToolStrip.Renderer%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="fd728-185">In the `StackView` control's constructor, create a new instance of the `StackRenderer` class and assign this instance to the `stackStrip` control's <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="test-the-stackview-control"></a><span data-ttu-id="fd728-186">测试 System.windows.forms.toolstrip.stackview 控件</span><span class="sxs-lookup"><span data-stu-id="fd728-186">Test the StackView control</span></span>

<span data-ttu-id="fd728-187">`StackView`控件派生自 <xref:System.Windows.Forms.UserControl> 类。</span><span class="sxs-lookup"><span data-stu-id="fd728-187">The `StackView` control derives from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="fd728-188">因此，可以用 **UserControl 测试容器** 测试控件。</span><span class="sxs-lookup"><span data-stu-id="fd728-188">Therefore, you can test the control with the **UserControl Test Container**.</span></span> <span data-ttu-id="fd728-189">有关详细信息，请参阅 [如何：测试 UserControl 的 Run-Time 行为](how-to-test-the-run-time-behavior-of-a-usercontrol.md)。</span><span class="sxs-lookup"><span data-stu-id="fd728-189">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

1. <span data-ttu-id="fd728-190">按 **F5** 生成项目并启动 " **UserControl 测试容器**"。</span><span class="sxs-lookup"><span data-stu-id="fd728-190">Press **F5** to build the project and start the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="fd728-191">将指针移到控件的按钮上 `StackView` ，然后单击按钮以查看其所选状态的外观。</span><span class="sxs-lookup"><span data-stu-id="fd728-191">Move the pointer over the buttons of the `StackView` control, and then click a button to see the appearance of its selected state.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fd728-192">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fd728-192">Next steps</span></span>

<span data-ttu-id="fd728-193">在本演练中，您已创建了一个可重用的自定义客户端控件，并具有 Office XP 控件的专业外观。</span><span class="sxs-lookup"><span data-stu-id="fd728-193">In this walkthrough, you have created a reusable custom client control with the professional appearance of an Office XP control.</span></span> <span data-ttu-id="fd728-194">可以将 <xref:System.Windows.Forms.ToolStrip> 控件系列用于许多其他用途：</span><span class="sxs-lookup"><span data-stu-id="fd728-194">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="fd728-195">为控件创建快捷菜单 <xref:System.Windows.Forms.ContextMenuStrip> 。</span><span class="sxs-lookup"><span data-stu-id="fd728-195">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="fd728-196">有关详细信息，请参阅 [ContextMenu 组件概述](contextmenu-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="fd728-196">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="fd728-197">使用自动填充的标准菜单创建窗体。</span><span class="sxs-lookup"><span data-stu-id="fd728-197">Create a form with an automatically populated standard menu.</span></span> <span data-ttu-id="fd728-198">有关详细信息，请参阅 [演练：向窗体提供标准菜单项](walkthrough-providing-standard-menu-items-to-a-form.md)。</span><span class="sxs-lookup"><span data-stu-id="fd728-198">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="fd728-199">使用停靠控件 (MDI) 窗体创建多文档界面 <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="fd728-199">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="fd728-200">有关详细信息，请参阅 [如何：创建具有菜单合并和 ToolStrip 控件的 MDI 窗体](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="fd728-200">For more information, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fd728-201">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd728-201">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="fd728-202">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="fd728-202">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="fd728-203">如何：向窗体提供标准菜单项</span><span class="sxs-lookup"><span data-stu-id="fd728-203">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
