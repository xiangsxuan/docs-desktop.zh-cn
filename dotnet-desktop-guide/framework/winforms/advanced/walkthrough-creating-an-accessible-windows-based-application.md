---
title: 演练：创建基于 Windows 的可访问应用程序
ms.date: 03/30/2017
helpviewer_keywords:
- accessibility [Windows Forms], Windows applications
- Windows applications [Windows Forms], accessibility
- applications [Windows Forms], accessibility
dev_langs:
- csharp
- vb
ms.assetid: 654c7f2f-1586-480b-9f12-9d9b8f5cc32b
ms.openlocfilehash: 63d328c1dae9eb18be0631a0007a92ad10461afb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971576"
---
# <a name="walkthrough-creating-an-accessible-windows-based-application"></a><span data-ttu-id="2e988-102">演练：创建基于 Windows 的可访问应用程序</span><span class="sxs-lookup"><span data-stu-id="2e988-102">Walkthrough: Creating an Accessible Windows-based Application</span></span>

<span data-ttu-id="2e988-103">创建具有辅助功能的应用程序具有重要的商业意义。</span><span class="sxs-lookup"><span data-stu-id="2e988-103">Creating an accessible application has important business implications.</span></span> <span data-ttu-id="2e988-104">很多政府都有针对软件购买的辅助功能法规。</span><span class="sxs-lookup"><span data-stu-id="2e988-104">Many governments have accessibility regulations for software purchase.</span></span> <span data-ttu-id="2e988-105">Certified for Windows 徽标包括辅助功能需求。</span><span class="sxs-lookup"><span data-stu-id="2e988-105">The Certified for Windows logo includes accessibility requirements.</span></span> <span data-ttu-id="2e988-106">据估计，仅美国就有 3 千万居民（其中很多为潜在客户）受到软件辅助功能的影响。</span><span class="sxs-lookup"><span data-stu-id="2e988-106">An estimated 30 million residents of the U.S. alone, many of them potential customers, are affected by the accessibility of software.</span></span>

<span data-ttu-id="2e988-107">此演练将针对 Certified for Windows 徽标的 5 项辅助功能需求。</span><span class="sxs-lookup"><span data-stu-id="2e988-107">This walkthrough will address the five accessibility requirements for the Certified for Windows logo.</span></span> <span data-ttu-id="2e988-108">根据这些要求，具有辅助功能的应用程序将：</span><span class="sxs-lookup"><span data-stu-id="2e988-108">According to these requirements, an accessible application will:</span></span>

- <span data-ttu-id="2e988-109">支持控件面板大小、颜色、字体和输入设置。</span><span class="sxs-lookup"><span data-stu-id="2e988-109">Support Control Panel size, color, font, and input settings.</span></span> <span data-ttu-id="2e988-110">当用户更改控件面板设置时，菜单栏、标题栏、边框和状态栏都将调整大小。</span><span class="sxs-lookup"><span data-stu-id="2e988-110">The menu bar, title bar, borders, and status bar will all resize themselves when the user changes the control panel settings.</span></span> <span data-ttu-id="2e988-111">此应用程序中不需要对控件或代码进行任何其他更改。</span><span class="sxs-lookup"><span data-stu-id="2e988-111">No additional changes to the controls or code are required in this application.</span></span>

- <span data-ttu-id="2e988-112">支持高对比度模式。</span><span class="sxs-lookup"><span data-stu-id="2e988-112">Support High Contrast mode.</span></span>

- <span data-ttu-id="2e988-113">提供对所有功能的已记录的键盘访问。</span><span class="sxs-lookup"><span data-stu-id="2e988-113">Provide documented keyboard access to all features.</span></span>

- <span data-ttu-id="2e988-114">以可视方式和以编程方式公开键盘焦点的位置。</span><span class="sxs-lookup"><span data-stu-id="2e988-114">Expose location of the keyboard focus visually and programmatically.</span></span>

- <span data-ttu-id="2e988-115">避免仅靠声音传达重要信息。</span><span class="sxs-lookup"><span data-stu-id="2e988-115">Avoid conveying important information by sound alone.</span></span>

<span data-ttu-id="2e988-116">有关详细信息，请参阅[用于设计支持辅助功能的应用程序的资源](/visualstudio/ide/reference/resources-for-designing-accessible-applications)。</span><span class="sxs-lookup"><span data-stu-id="2e988-116">For more information, see [Resources for Designing Accessible Applications](/visualstudio/ide/reference/resources-for-designing-accessible-applications).</span></span>

<span data-ttu-id="2e988-117">有关支持不同键盘布局的信息，请参阅[开发全球通用应用程序的最佳做法](/dotnet/standard/globalization-localization/best-practices-for-developing-world-ready-apps)。</span><span class="sxs-lookup"><span data-stu-id="2e988-117">For information on supporting varying keyboard layouts, see [Best Practices for Developing World-Ready Applications](/dotnet/standard/globalization-localization/best-practices-for-developing-world-ready-apps).</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="2e988-118">创建项目</span><span class="sxs-lookup"><span data-stu-id="2e988-118">Creating the Project</span></span>

<span data-ttu-id="2e988-119">此演练为一个可接受比萨订单的应用程序创建用户界面。</span><span class="sxs-lookup"><span data-stu-id="2e988-119">This walkthrough creates the user interface for an application that takes pizza orders.</span></span> <span data-ttu-id="2e988-120">它包含以下内容：一个用于输入客户名称的 <xref:System.Windows.Forms.TextBox>一个用于选择比萨大小的 <xref:System.Windows.Forms.RadioButton> 组，一个用于选择浇头的 <xref:System.Windows.Forms.CheckedListBox>分别标记为“订购”和“取消”的两个 Button 控件，以及一个具有“退出”命令的“菜单”。</span><span class="sxs-lookup"><span data-stu-id="2e988-120">It consists of a <xref:System.Windows.Forms.TextBox> for the customer's name, a <xref:System.Windows.Forms.RadioButton> group to select the pizza size, a <xref:System.Windows.Forms.CheckedListBox> for selecting the toppings, two Button controls labeled Order and Cancel, and a Menu with an Exit command.</span></span>

<span data-ttu-id="2e988-121">用户输入客户名称、比萨大小和想要的浇头。</span><span class="sxs-lookup"><span data-stu-id="2e988-121">The user enters the customer's name, the size of the pizza, and the toppings desired.</span></span> <span data-ttu-id="2e988-122">当用户单击“订购”按钮时，将在消息框中显示订单一览表及其价格，然后将控件清除并为下个订单做好准备。</span><span class="sxs-lookup"><span data-stu-id="2e988-122">When the user clicks the Order button, a summary of the order and its cost are displayed in a message box and the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="2e988-123">当用户单击“取消”按钮时，将控件清除并为下个订单做好准备。</span><span class="sxs-lookup"><span data-stu-id="2e988-123">When the user clicks the Cancel button, the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="2e988-124">当用户单击“退出”菜单项时，程序关闭。</span><span class="sxs-lookup"><span data-stu-id="2e988-124">When the user clicks the Exit menu item, the program closes.</span></span>

<span data-ttu-id="2e988-125">本演练的重点不是零售订单系统的代码，而是用户界面的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="2e988-125">The emphasis of this walkthrough is not the code for a retail order system, but the accessibility of the user interface.</span></span> <span data-ttu-id="2e988-126">本演练说明几个常用控件（包括按钮、单选按钮、文本框和标签）的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="2e988-126">The walkthrough demonstrates the accessibility features of several frequently used controls, including buttons, radio buttons, text boxes, and labels.</span></span>

#### <a name="to-begin-making-the-application"></a><span data-ttu-id="2e988-127">开始生成应用程序</span><span class="sxs-lookup"><span data-stu-id="2e988-127">To begin making the application</span></span>

- <span data-ttu-id="2e988-128">在 Visual Basic 或 Visual c # 中创建新的 Windows 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2e988-128">Create a new Windows Application in Visual Basic or Visual C#.</span></span> <span data-ttu-id="2e988-129">将项目命名为 **PizzaOrder**。</span><span class="sxs-lookup"><span data-stu-id="2e988-129">Name the project **PizzaOrder**.</span></span> <span data-ttu-id="2e988-130">有关详细信息，请参阅 [创建新解决方案和项目](/visualstudio/ide/creating-solutions-and-projects)。</span><span class="sxs-lookup"><span data-stu-id="2e988-130">For details, see [Creating New Solutions and Projects](/visualstudio/ide/creating-solutions-and-projects).</span></span>

## <a name="adding-the-controls-to-the-form"></a><span data-ttu-id="2e988-131">将控件添加到窗体</span><span class="sxs-lookup"><span data-stu-id="2e988-131">Adding the Controls to the Form</span></span>

<span data-ttu-id="2e988-132">将控件添加到窗体时，请牢记以下指南以生成具有辅助功能的应用程序：</span><span class="sxs-lookup"><span data-stu-id="2e988-132">When adding the controls to a form, keep in mind the following guidelines to make an accessible application:</span></span>

- <span data-ttu-id="2e988-133">设置 <xref:System.Windows.Forms.Control.AccessibleDescription%2A> 和 <xref:System.Windows.Forms.Control.AccessibleName%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="2e988-133">Set the <xref:System.Windows.Forms.Control.AccessibleDescription%2A> and <xref:System.Windows.Forms.Control.AccessibleName%2A> properties.</span></span> <span data-ttu-id="2e988-134">在此示例中，<xref:System.Windows.Forms.Control.AccessibleRole%2A> 的默认设置已经足够。</span><span class="sxs-lookup"><span data-stu-id="2e988-134">In this example, the Default setting for the <xref:System.Windows.Forms.Control.AccessibleRole%2A> is sufficient.</span></span> <span data-ttu-id="2e988-135">有关辅助功能属性的详细信息，请参阅[为 Windows 窗体上的控件提供辅助功能信息](../controls/providing-accessibility-information-for-controls-on-a-windows-form.md)。</span><span class="sxs-lookup"><span data-stu-id="2e988-135">For more information on the accessibility properties, see [Providing Accessibility Information for Controls on a Windows Form](../controls/providing-accessibility-information-for-controls-on-a-windows-form.md).</span></span>

- <span data-ttu-id="2e988-136">将字体大小设置为 10 号或更大。</span><span class="sxs-lookup"><span data-stu-id="2e988-136">Set the font size to 10 points or larger.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2e988-137">如果在启动时将窗体的字体大小设置为 10，则随后添加到窗体的所有控件的字体大小均为 10。</span><span class="sxs-lookup"><span data-stu-id="2e988-137">If you set the font size of the form to 10 when you start, then all controls subsequently added to the form will have a font size of 10.</span></span>

- <span data-ttu-id="2e988-138">确保任何描述 TextBox 控件的 Label 控件均按 Tab 顺序紧排在相应的 TextBox 控件之前。</span><span class="sxs-lookup"><span data-stu-id="2e988-138">Make sure any Label control that describes a TextBox control immediately precedes the TextBox control in the tab order.</span></span>

- <span data-ttu-id="2e988-139">使用 "&" 字符将访问键添加到 <xref:System.Windows.Forms.Control.Text%2A> 用户可能想要导航到的任何控件的属性。</span><span class="sxs-lookup"><span data-stu-id="2e988-139">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of any control the user may want to navigate to.</span></span>

- <span data-ttu-id="2e988-140">使用 "&" 字符将访问键添加到 <xref:System.Windows.Forms.Control.Text%2A> 用户可能想要导航到的控件之前的标签属性。</span><span class="sxs-lookup"><span data-stu-id="2e988-140">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of the label that precedes a control that the user may want to navigate to.</span></span> <span data-ttu-id="2e988-141">将标签的 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 属性设置为 `true`，以便在用户按下访问键时将焦点设置到按 Tab 键顺序的下一控件。</span><span class="sxs-lookup"><span data-stu-id="2e988-141">Set the labels' <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`, so that the focus is set to the next control in the tab order when the user presses the access key.</span></span>

- <span data-ttu-id="2e988-142">将访问键添加到所有菜单项。</span><span class="sxs-lookup"><span data-stu-id="2e988-142">Add access keys to all menu items.</span></span>

#### <a name="to-make-your-windows-application-accessible"></a><span data-ttu-id="2e988-143">使 Windows 应用程序具有辅助功能</span><span class="sxs-lookup"><span data-stu-id="2e988-143">To make your Windows Application accessible</span></span>

- <span data-ttu-id="2e988-144">将控件添加到窗体并如下所述设置属性。</span><span class="sxs-lookup"><span data-stu-id="2e988-144">Add the controls to the form and set the properties as described below.</span></span> <span data-ttu-id="2e988-145">有关如何在窗体上排列控件的模型，请查看表结尾处的图片。</span><span class="sxs-lookup"><span data-stu-id="2e988-145">See the picture at the end of the table for a model of how to arrange the controls on the form.</span></span>

   |<span data-ttu-id="2e988-146">Object</span><span class="sxs-lookup"><span data-stu-id="2e988-146">Object</span></span>|<span data-ttu-id="2e988-147">属性</span><span class="sxs-lookup"><span data-stu-id="2e988-147">Property</span></span>|<span data-ttu-id="2e988-148">值</span><span class="sxs-lookup"><span data-stu-id="2e988-148">Value</span></span>|
   |------------|--------------|-----------|
   |<span data-ttu-id="2e988-149">Form1</span><span class="sxs-lookup"><span data-stu-id="2e988-149">Form1</span></span>|<span data-ttu-id="2e988-150">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="2e988-150">AccessibleDescription</span></span>|<span data-ttu-id="2e988-151">订购窗体</span><span class="sxs-lookup"><span data-stu-id="2e988-151">Order form</span></span>|
   ||<span data-ttu-id="2e988-152">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="2e988-152">AccessibleName</span></span>|<span data-ttu-id="2e988-153">订购窗体</span><span class="sxs-lookup"><span data-stu-id="2e988-153">Order form</span></span>|
   ||<span data-ttu-id="2e988-154">字号</span><span class="sxs-lookup"><span data-stu-id="2e988-154">Font Size</span></span>|<span data-ttu-id="2e988-155">10</span><span class="sxs-lookup"><span data-stu-id="2e988-155">10</span></span>|
   ||<span data-ttu-id="2e988-156">文本</span><span class="sxs-lookup"><span data-stu-id="2e988-156">Text</span></span>|<span data-ttu-id="2e988-157">比萨饼订购窗体</span><span class="sxs-lookup"><span data-stu-id="2e988-157">Pizza Order Form</span></span>|
   |<span data-ttu-id="2e988-158">PictureBox</span><span class="sxs-lookup"><span data-stu-id="2e988-158">PictureBox</span></span>|<span data-ttu-id="2e988-159">名称</span><span class="sxs-lookup"><span data-stu-id="2e988-159">Name</span></span>|<span data-ttu-id="2e988-160">徽标</span><span class="sxs-lookup"><span data-stu-id="2e988-160">logo</span></span>|
   ||<span data-ttu-id="2e988-161">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="2e988-161">AccessibleDescription</span></span>|<span data-ttu-id="2e988-162">一片比萨饼</span><span class="sxs-lookup"><span data-stu-id="2e988-162">A slice of pizza</span></span>|
   ||<span data-ttu-id="2e988-163">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="2e988-163">AccessibleName</span></span>|<span data-ttu-id="2e988-164">公司徽标</span><span class="sxs-lookup"><span data-stu-id="2e988-164">Company logo</span></span>|
   ||<span data-ttu-id="2e988-165">图像</span><span class="sxs-lookup"><span data-stu-id="2e988-165">Image</span></span>|<span data-ttu-id="2e988-166">任何图标或位图</span><span class="sxs-lookup"><span data-stu-id="2e988-166">Any icon or bitmap</span></span>|
   |<span data-ttu-id="2e988-167">Label</span><span class="sxs-lookup"><span data-stu-id="2e988-167">Label</span></span>|<span data-ttu-id="2e988-168">名称</span><span class="sxs-lookup"><span data-stu-id="2e988-168">Name</span></span>|<span data-ttu-id="2e988-169">companyLabel</span><span class="sxs-lookup"><span data-stu-id="2e988-169">companyLabel</span></span>|
   ||<span data-ttu-id="2e988-170">文本</span><span class="sxs-lookup"><span data-stu-id="2e988-170">Text</span></span>|<span data-ttu-id="2e988-171">美味比萨</span><span class="sxs-lookup"><span data-stu-id="2e988-171">Good Pizza</span></span>|
   ||<span data-ttu-id="2e988-172">TabIndex</span><span class="sxs-lookup"><span data-stu-id="2e988-172">TabIndex</span></span>|<span data-ttu-id="2e988-173">1</span><span class="sxs-lookup"><span data-stu-id="2e988-173">1</span></span>|
   ||<span data-ttu-id="2e988-174">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="2e988-174">AccessibleDescription</span></span>|<span data-ttu-id="2e988-175">公司名称</span><span class="sxs-lookup"><span data-stu-id="2e988-175">Company name</span></span>|
   ||<span data-ttu-id="2e988-176">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="2e988-176">AccessibleName</span></span>|<span data-ttu-id="2e988-177">公司名称</span><span class="sxs-lookup"><span data-stu-id="2e988-177">Company name</span></span>|
   ||<span data-ttu-id="2e988-178">背景色</span><span class="sxs-lookup"><span data-stu-id="2e988-178">Backcolor</span></span>|<span data-ttu-id="2e988-179">蓝色</span><span class="sxs-lookup"><span data-stu-id="2e988-179">Blue</span></span>|
   ||<span data-ttu-id="2e988-180">前景色</span><span class="sxs-lookup"><span data-stu-id="2e988-180">Forecolor</span></span>|<span data-ttu-id="2e988-181">Yellow</span><span class="sxs-lookup"><span data-stu-id="2e988-181">Yellow</span></span>|
   ||<span data-ttu-id="2e988-182">字体大小</span><span class="sxs-lookup"><span data-stu-id="2e988-182">Font size</span></span>|<span data-ttu-id="2e988-183">18</span><span class="sxs-lookup"><span data-stu-id="2e988-183">18</span></span>|
   |<span data-ttu-id="2e988-184">Label</span><span class="sxs-lookup"><span data-stu-id="2e988-184">Label</span></span>|<span data-ttu-id="2e988-185">名称</span><span class="sxs-lookup"><span data-stu-id="2e988-185">Name</span></span>|<span data-ttu-id="2e988-186">customerLabel</span><span class="sxs-lookup"><span data-stu-id="2e988-186">customerLabel</span></span>|
   ||<span data-ttu-id="2e988-187">文本</span><span class="sxs-lookup"><span data-stu-id="2e988-187">Text</span></span>|<span data-ttu-id="2e988-188">名称(&N)</span><span class="sxs-lookup"><span data-stu-id="2e988-188">&Name</span></span>|
   ||<span data-ttu-id="2e988-189">TabIndex</span><span class="sxs-lookup"><span data-stu-id="2e988-189">TabIndex</span></span>|<span data-ttu-id="2e988-190">2</span><span class="sxs-lookup"><span data-stu-id="2e988-190">2</span></span>|
   ||<span data-ttu-id="2e988-191">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="2e988-191">AccessibleDescription</span></span>|<span data-ttu-id="2e988-192">客户名称标签</span><span class="sxs-lookup"><span data-stu-id="2e988-192">Customer name label</span></span>|
   ||<span data-ttu-id="2e988-193">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="2e988-193">AccessibleName</span></span>|<span data-ttu-id="2e988-194">客户名称标签</span><span class="sxs-lookup"><span data-stu-id="2e988-194">Customer name label</span></span>|
   ||<span data-ttu-id="2e988-195">UseMnemonic</span><span class="sxs-lookup"><span data-stu-id="2e988-195">UseMnemonic</span></span>|<span data-ttu-id="2e988-196">正确</span><span class="sxs-lookup"><span data-stu-id="2e988-196">True</span></span>|
   |<span data-ttu-id="2e988-197">TextBox</span><span class="sxs-lookup"><span data-stu-id="2e988-197">TextBox</span></span>|<span data-ttu-id="2e988-198">名称</span><span class="sxs-lookup"><span data-stu-id="2e988-198">Name</span></span>|<span data-ttu-id="2e988-199">customerName</span><span class="sxs-lookup"><span data-stu-id="2e988-199">customerName</span></span>|
   ||<span data-ttu-id="2e988-200">文本</span><span class="sxs-lookup"><span data-stu-id="2e988-200">Text</span></span>|<span data-ttu-id="2e988-201">（无）</span><span class="sxs-lookup"><span data-stu-id="2e988-201">(none)</span></span>|
   ||<span data-ttu-id="2e988-202">TabIndex</span><span class="sxs-lookup"><span data-stu-id="2e988-202">TabIndex</span></span>|<span data-ttu-id="2e988-203">3</span><span class="sxs-lookup"><span data-stu-id="2e988-203">3</span></span>|
   ||<span data-ttu-id="2e988-204">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="2e988-204">AccessibleDescription</span></span>|<span data-ttu-id="2e988-205">客户名称</span><span class="sxs-lookup"><span data-stu-id="2e988-205">Customer name</span></span>|
   ||<span data-ttu-id="2e988-206">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="2e988-206">AccessibleName</span></span>|<span data-ttu-id="2e988-207">客户名称</span><span class="sxs-lookup"><span data-stu-id="2e988-207">Customer name</span></span>|
   |<span data-ttu-id="2e988-208">GroupBox</span><span class="sxs-lookup"><span data-stu-id="2e988-208">GroupBox</span></span>|<span data-ttu-id="2e988-209">名称</span><span class="sxs-lookup"><span data-stu-id="2e988-209">Name</span></span>|<span data-ttu-id="2e988-210">sizeOptions</span><span class="sxs-lookup"><span data-stu-id="2e988-210">sizeOptions</span></span>|
   ||<span data-ttu-id="2e988-211">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="2e988-211">AccessibleDescription</span></span>|<span data-ttu-id="2e988-212">比萨大小选项</span><span class="sxs-lookup"><span data-stu-id="2e988-212">Pizza size options</span></span>|
   ||<span data-ttu-id="2e988-213">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="2e988-213">AccessibleName</span></span>|<span data-ttu-id="2e988-214">比萨大小选项</span><span class="sxs-lookup"><span data-stu-id="2e988-214">Pizza size options</span></span>|
   ||<span data-ttu-id="2e988-215">文本</span><span class="sxs-lookup"><span data-stu-id="2e988-215">Text</span></span>|<span data-ttu-id="2e988-216">比萨大小</span><span class="sxs-lookup"><span data-stu-id="2e988-216">Pizza size</span></span>|
   ||<span data-ttu-id="2e988-217">TabIndex</span><span class="sxs-lookup"><span data-stu-id="2e988-217">TabIndex</span></span>|<span data-ttu-id="2e988-218">4</span><span class="sxs-lookup"><span data-stu-id="2e988-218">4</span></span>|
   |<span data-ttu-id="2e988-219">RadioButton</span><span class="sxs-lookup"><span data-stu-id="2e988-219">RadioButton</span></span>|<span data-ttu-id="2e988-220">名称</span><span class="sxs-lookup"><span data-stu-id="2e988-220">Name</span></span>|<span data-ttu-id="2e988-221">smallPizza</span><span class="sxs-lookup"><span data-stu-id="2e988-221">smallPizza</span></span>|
   ||<span data-ttu-id="2e988-222">文本</span><span class="sxs-lookup"><span data-stu-id="2e988-222">Text</span></span>|<span data-ttu-id="2e988-223">小号 $6.00 (&S)</span><span class="sxs-lookup"><span data-stu-id="2e988-223">&Small $6.00</span></span>|
   ||<span data-ttu-id="2e988-224">已选中</span><span class="sxs-lookup"><span data-stu-id="2e988-224">Checked</span></span>|<span data-ttu-id="2e988-225">正确</span><span class="sxs-lookup"><span data-stu-id="2e988-225">True</span></span>|
   ||<span data-ttu-id="2e988-226">TabIndex</span><span class="sxs-lookup"><span data-stu-id="2e988-226">TabIndex</span></span>|<span data-ttu-id="2e988-227">0</span><span class="sxs-lookup"><span data-stu-id="2e988-227">0</span></span>|
   ||<span data-ttu-id="2e988-228">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="2e988-228">AccessibleDescription</span></span>|<span data-ttu-id="2e988-229">小号比萨</span><span class="sxs-lookup"><span data-stu-id="2e988-229">Small pizza</span></span>|
   ||<span data-ttu-id="2e988-230">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="2e988-230">AccessibleName</span></span>|<span data-ttu-id="2e988-231">小号比萨</span><span class="sxs-lookup"><span data-stu-id="2e988-231">Small pizza</span></span>|
   |<span data-ttu-id="2e988-232">RadioButton</span><span class="sxs-lookup"><span data-stu-id="2e988-232">RadioButton</span></span>|<span data-ttu-id="2e988-233">名称</span><span class="sxs-lookup"><span data-stu-id="2e988-233">Name</span></span>|<span data-ttu-id="2e988-234">largePizza</span><span class="sxs-lookup"><span data-stu-id="2e988-234">largePizza</span></span>|
   ||<span data-ttu-id="2e988-235">文本</span><span class="sxs-lookup"><span data-stu-id="2e988-235">Text</span></span>|<span data-ttu-id="2e988-236">大号 $10.00 (&L)</span><span class="sxs-lookup"><span data-stu-id="2e988-236">&Large $10.00</span></span>|
   ||<span data-ttu-id="2e988-237">TabIndex</span><span class="sxs-lookup"><span data-stu-id="2e988-237">TabIndex</span></span>|<span data-ttu-id="2e988-238">1</span><span class="sxs-lookup"><span data-stu-id="2e988-238">1</span></span>|
   ||<span data-ttu-id="2e988-239">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="2e988-239">AccessibleDescription</span></span>|<span data-ttu-id="2e988-240">大号披萨</span><span class="sxs-lookup"><span data-stu-id="2e988-240">Large pizza</span></span>|
   ||<span data-ttu-id="2e988-241">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="2e988-241">AccessibleName</span></span>|<span data-ttu-id="2e988-242">大号披萨</span><span class="sxs-lookup"><span data-stu-id="2e988-242">Large pizza</span></span>|
   |<span data-ttu-id="2e988-243">Label</span><span class="sxs-lookup"><span data-stu-id="2e988-243">Label</span></span>|<span data-ttu-id="2e988-244">名称</span><span class="sxs-lookup"><span data-stu-id="2e988-244">Name</span></span>|<span data-ttu-id="2e988-245">toppingsLabel</span><span class="sxs-lookup"><span data-stu-id="2e988-245">toppingsLabel</span></span>|
   ||<span data-ttu-id="2e988-246">文本</span><span class="sxs-lookup"><span data-stu-id="2e988-246">Text</span></span>|<span data-ttu-id="2e988-247">浇头(每个$0.75)(&T)</span><span class="sxs-lookup"><span data-stu-id="2e988-247">&Toppings ($0.75 each)</span></span>|
   ||<span data-ttu-id="2e988-248">TabIndex</span><span class="sxs-lookup"><span data-stu-id="2e988-248">TabIndex</span></span>|<span data-ttu-id="2e988-249">5</span><span class="sxs-lookup"><span data-stu-id="2e988-249">5</span></span>|
   ||<span data-ttu-id="2e988-250">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="2e988-250">AccessibleDescription</span></span>|<span data-ttu-id="2e988-251">浇头标签</span><span class="sxs-lookup"><span data-stu-id="2e988-251">Toppings label</span></span>|
   ||<span data-ttu-id="2e988-252">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="2e988-252">AccessibleName</span></span>|<span data-ttu-id="2e988-253">浇头标签</span><span class="sxs-lookup"><span data-stu-id="2e988-253">Toppings label</span></span>|
   ||<span data-ttu-id="2e988-254">UseMnemonic</span><span class="sxs-lookup"><span data-stu-id="2e988-254">UseMnemonic</span></span>|<span data-ttu-id="2e988-255">正确</span><span class="sxs-lookup"><span data-stu-id="2e988-255">True</span></span>|
   |<span data-ttu-id="2e988-256">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="2e988-256">CheckedListBox</span></span>|<span data-ttu-id="2e988-257">名称</span><span class="sxs-lookup"><span data-stu-id="2e988-257">Name</span></span>|<span data-ttu-id="2e988-258">浇头</span><span class="sxs-lookup"><span data-stu-id="2e988-258">toppings</span></span>|
   ||<span data-ttu-id="2e988-259">TabIndex</span><span class="sxs-lookup"><span data-stu-id="2e988-259">TabIndex</span></span>|<span data-ttu-id="2e988-260">6</span><span class="sxs-lookup"><span data-stu-id="2e988-260">6</span></span>|
   ||<span data-ttu-id="2e988-261">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="2e988-261">AccessibleDescription</span></span>|<span data-ttu-id="2e988-262">可用浇头</span><span class="sxs-lookup"><span data-stu-id="2e988-262">Available toppings</span></span>|
   ||<span data-ttu-id="2e988-263">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="2e988-263">AccessibleName</span></span>|<span data-ttu-id="2e988-264">可用浇头</span><span class="sxs-lookup"><span data-stu-id="2e988-264">Available toppings</span></span>|
   ||<span data-ttu-id="2e988-265">项目</span><span class="sxs-lookup"><span data-stu-id="2e988-265">Items</span></span>|<span data-ttu-id="2e988-266">意大利辣肠、香肠、蘑菇</span><span class="sxs-lookup"><span data-stu-id="2e988-266">Pepperoni, Sausage, Mushrooms</span></span>|
   |<span data-ttu-id="2e988-267">Button</span><span class="sxs-lookup"><span data-stu-id="2e988-267">Button</span></span>|<span data-ttu-id="2e988-268">名称</span><span class="sxs-lookup"><span data-stu-id="2e988-268">Name</span></span>|<span data-ttu-id="2e988-269">顺序</span><span class="sxs-lookup"><span data-stu-id="2e988-269">order</span></span>|
   ||<span data-ttu-id="2e988-270">文本</span><span class="sxs-lookup"><span data-stu-id="2e988-270">Text</span></span>|<span data-ttu-id="2e988-271">顺序(&O)</span><span class="sxs-lookup"><span data-stu-id="2e988-271">&Order</span></span>|
   ||<span data-ttu-id="2e988-272">TabIndex</span><span class="sxs-lookup"><span data-stu-id="2e988-272">TabIndex</span></span>|<span data-ttu-id="2e988-273">7</span><span class="sxs-lookup"><span data-stu-id="2e988-273">7</span></span>|
   ||<span data-ttu-id="2e988-274">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="2e988-274">AccessibleDescription</span></span>|<span data-ttu-id="2e988-275">订单合计</span><span class="sxs-lookup"><span data-stu-id="2e988-275">Total the order</span></span>|
   ||<span data-ttu-id="2e988-276">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="2e988-276">AccessibleName</span></span>|<span data-ttu-id="2e988-277">总订单</span><span class="sxs-lookup"><span data-stu-id="2e988-277">Total order</span></span>|
   |<span data-ttu-id="2e988-278">Button</span><span class="sxs-lookup"><span data-stu-id="2e988-278">Button</span></span>|<span data-ttu-id="2e988-279">名称</span><span class="sxs-lookup"><span data-stu-id="2e988-279">Name</span></span>|<span data-ttu-id="2e988-280">cancel</span><span class="sxs-lookup"><span data-stu-id="2e988-280">cancel</span></span>|
   ||<span data-ttu-id="2e988-281">文本</span><span class="sxs-lookup"><span data-stu-id="2e988-281">Text</span></span>|<span data-ttu-id="2e988-282">取消(&C)</span><span class="sxs-lookup"><span data-stu-id="2e988-282">&Cancel</span></span>|
   ||<span data-ttu-id="2e988-283">TabIndex</span><span class="sxs-lookup"><span data-stu-id="2e988-283">TabIndex</span></span>|<span data-ttu-id="2e988-284">8</span><span class="sxs-lookup"><span data-stu-id="2e988-284">8</span></span>|
   ||<span data-ttu-id="2e988-285">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="2e988-285">AccessibleDescription</span></span>|<span data-ttu-id="2e988-286">取消订单</span><span class="sxs-lookup"><span data-stu-id="2e988-286">Cancel the order</span></span>|
   ||<span data-ttu-id="2e988-287">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="2e988-287">AccessibleName</span></span>|<span data-ttu-id="2e988-288">取消订单</span><span class="sxs-lookup"><span data-stu-id="2e988-288">Cancel order</span></span>|
   |<span data-ttu-id="2e988-289">MainMenu</span><span class="sxs-lookup"><span data-stu-id="2e988-289">MainMenu</span></span>|<span data-ttu-id="2e988-290">名称</span><span class="sxs-lookup"><span data-stu-id="2e988-290">Name</span></span>|<span data-ttu-id="2e988-291">theMainMenu</span><span class="sxs-lookup"><span data-stu-id="2e988-291">theMainMenu</span></span>|
   |<span data-ttu-id="2e988-292">MenuItem</span><span class="sxs-lookup"><span data-stu-id="2e988-292">MenuItem</span></span>|<span data-ttu-id="2e988-293">名称</span><span class="sxs-lookup"><span data-stu-id="2e988-293">Name</span></span>|<span data-ttu-id="2e988-294">fileCommands</span><span class="sxs-lookup"><span data-stu-id="2e988-294">fileCommands</span></span>|
   ||<span data-ttu-id="2e988-295">文本</span><span class="sxs-lookup"><span data-stu-id="2e988-295">Text</span></span>|<span data-ttu-id="2e988-296">文件(&F)</span><span class="sxs-lookup"><span data-stu-id="2e988-296">&File</span></span>|
   |<span data-ttu-id="2e988-297">MenuItem</span><span class="sxs-lookup"><span data-stu-id="2e988-297">MenuItem</span></span>|<span data-ttu-id="2e988-298">名称</span><span class="sxs-lookup"><span data-stu-id="2e988-298">Name</span></span>|<span data-ttu-id="2e988-299">exitApp</span><span class="sxs-lookup"><span data-stu-id="2e988-299">exitApp</span></span>|
   ||<span data-ttu-id="2e988-300">文本</span><span class="sxs-lookup"><span data-stu-id="2e988-300">Text</span></span>|<span data-ttu-id="2e988-301">退出(&X)</span><span class="sxs-lookup"><span data-stu-id="2e988-301">E&xit</span></span>|

   <span data-ttu-id="2e988-302">您的窗体将如下图所示：</span><span class="sxs-lookup"><span data-stu-id="2e988-302">Your form will look something like the following image:</span></span>

   !["比萨饼订单" 窗体具有 "名称" 文本框，"大小" 和 "浇头" 选项。](./media/walkthrough-creating-an-accessible-windows-based-application/visual-basic-pizza-order-form.gif)

## <a name="supporting-high-contrast-mode"></a><span data-ttu-id="2e988-304">支持高对比度模式</span><span class="sxs-lookup"><span data-stu-id="2e988-304">Supporting High Contrast Mode</span></span>

<span data-ttu-id="2e988-305">高对比度模式是一种 Windows 系统设置，它通过使用有益于视力受损用户的对比颜色和字体大小提高可读性。</span><span class="sxs-lookup"><span data-stu-id="2e988-305">High Contrast mode is a Windows system setting that improves readability by using contrasting colors and font sizes that are beneficial for visually impaired users.</span></span> <span data-ttu-id="2e988-306"><xref:System.Windows.Forms.SystemInformation.HighContrast%2A>提供属性以确定是否设置了高对比度模式。</span><span class="sxs-lookup"><span data-stu-id="2e988-306">The <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> property is provided to determine whether the High Contrast mode is set.</span></span>

<span data-ttu-id="2e988-307">如果 SystemInformation.HighContrast 为`true`，则应用程序应：</span><span class="sxs-lookup"><span data-stu-id="2e988-307">If SystemInformation.HighContrast is `true`, the application should:</span></span>

- <span data-ttu-id="2e988-308">显示使用系统配色方案的所有用户界面元素</span><span class="sxs-lookup"><span data-stu-id="2e988-308">Display all user interface elements using the system color scheme</span></span>

- <span data-ttu-id="2e988-309">通过可视提示或声音传递任何通过颜色传递的信息。</span><span class="sxs-lookup"><span data-stu-id="2e988-309">Convey by visual cues or sound any information that is conveyed through color.</span></span> <span data-ttu-id="2e988-310">例如，如果特定列表项使用红色字体突出显示，则还可为字体加粗，以便用户得到突出显示项的非颜色提示。</span><span class="sxs-lookup"><span data-stu-id="2e988-310">For example, if particular list items are highlighted by using a red font, you could also add bold to the font, so that the user has a non-color cue that the items are highlighted.</span></span>

- <span data-ttu-id="2e988-311">忽略文本之后的任何图像或图案</span><span class="sxs-lookup"><span data-stu-id="2e988-311">Omit any images or patterns behind text</span></span>

<span data-ttu-id="2e988-312">应用程序应在启动时检查 <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> 的设置，并响应系统事件 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>。</span><span class="sxs-lookup"><span data-stu-id="2e988-312">The application should check the setting of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> when the application starts and respond to the system event <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span></span> <span data-ttu-id="2e988-313">每当 <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> 的值更改时，都会引发 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 事件。</span><span class="sxs-lookup"><span data-stu-id="2e988-313">The <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event is raised whenever the value of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> changes.</span></span>

<span data-ttu-id="2e988-314">在本应用程序中，未使用系统颜色设置的唯一元素是 `lblCompanyName`。</span><span class="sxs-lookup"><span data-stu-id="2e988-314">In our application, the only element that is not using the system settings for color is `lblCompanyName`.</span></span> <span data-ttu-id="2e988-315"><xref:System.Drawing.SystemColors>类用于将标签的颜色设置更改为用户选择的系统颜色。</span><span class="sxs-lookup"><span data-stu-id="2e988-315">The <xref:System.Drawing.SystemColors> class is used to change the color settings of the label to the user-selected system colors.</span></span>

#### <a name="to-enable-high-contrast-mode-in-an-effective-way"></a><span data-ttu-id="2e988-316">有效地启用高对比度模式</span><span class="sxs-lookup"><span data-stu-id="2e988-316">To enable High Contrast mode in an effective way</span></span>

1. <span data-ttu-id="2e988-317">创建一种方法将标签颜色设置为系统颜色。</span><span class="sxs-lookup"><span data-stu-id="2e988-317">Create a method to set the colors of the label to the system colors.</span></span>

    ```vb
    Private Sub SetColorScheme()
        If SystemInformation.HighContrast Then
            companyLabel.BackColor = SystemColors.Window
            companyLabel.ForeColor = SystemColors.WindowText
        Else
            companyLabel.BackColor = Color.Blue
            companyLabel.ForeColor = Color.Yellow
        End If
    End Sub
    ```

    ```csharp
    private void SetColorScheme()
    {
        if (SystemInformation.HighContrast)
        {
            companyLabel.BackColor = SystemColors.Window;
            companyLabel.ForeColor = SystemColors.WindowText;
        }
        else
        {
            companyLabel.BackColor = Color.Blue;
            companyLabel.ForeColor = Color.Yellow;
        }
    }
    ```

2. <span data-ttu-id="2e988-318">在窗体构造函数（Visual Basic 中为 `Public Sub New()`，Visual C# 中为 `public Form1()`）调用 `SetColorScheme` 过程。</span><span class="sxs-lookup"><span data-stu-id="2e988-318">Call the `SetColorScheme` procedure in the form constructor (`Public Sub New()` in Visual Basic and `public Form1()` in Visual C#).</span></span> <span data-ttu-id="2e988-319">若要访问 Visual Basic 中的构造函数，需要展开标记了“Windows 窗体设计器生成的代码”的区域。</span><span class="sxs-lookup"><span data-stu-id="2e988-319">To access the constructor in Visual Basic, you will need to expand the region labeled **Windows Form Designer generated code**.</span></span>

    ```vb
    Public Sub New()
        MyBase.New()
        InitializeComponent()
        SetColorScheme()
    End Sub
    ```

    ```csharp
    public Form1()
    {
        InitializeComponent();
        SetColorScheme();
    }
    ```

3. <span data-ttu-id="2e988-320">使用适当签名创建事件过程，以响应 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 事件。</span><span class="sxs-lookup"><span data-stu-id="2e988-320">Create an event procedure, with the appropriate signature, to respond to the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event.</span></span>

    ```vb
    Protected Sub UserPreferenceChanged(sender As Object, _
    e As Microsoft.Win32.UserPreferenceChangedEventArgs)
        SetColorScheme()
    End Sub
    ```

    ```csharp
    public void UserPreferenceChanged(object sender,
    Microsoft.Win32.UserPreferenceChangedEventArgs e)
    {
        SetColorScheme();
    }
    ```

4. <span data-ttu-id="2e988-321">在调用 `InitializeComponents` 后将代码添加到窗体构造函数，以便将事件过程挂钩到系统事件。</span><span class="sxs-lookup"><span data-stu-id="2e988-321">Add code to the form constructor, after the call to `InitializeComponents`, to hook up the event procedure to the system event.</span></span> <span data-ttu-id="2e988-322">此方法调用 `SetColorScheme` 过程。</span><span class="sxs-lookup"><span data-stu-id="2e988-322">This method calls the `SetColorScheme` procedure.</span></span>

    ```vb
    Public Sub New()
        MyBase.New()
        InitializeComponent()
        SetColorScheme()
        AddHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _
           AddressOf Me.UserPreferenceChanged
    End Sub
    ```

    ```csharp
    public Form1()
    {
        InitializeComponent();
        SetColorScheme();
        Microsoft.Win32.SystemEvents.UserPreferenceChanged
           += new Microsoft.Win32.UserPreferenceChangedEventHandler(
           this.UserPreferenceChanged);
    }
    ```

5. <span data-ttu-id="2e988-323">在调用基类的 <xref:System.Windows.Forms.Control.Dispose%2A> 方法之前将代码添加到窗体 <xref:System.Windows.Forms.Control.Dispose%2A> 方法，以便在应用程序关闭时释放事件。</span><span class="sxs-lookup"><span data-stu-id="2e988-323">Add code to the form <xref:System.Windows.Forms.Control.Dispose%2A> method, before the call to the <xref:System.Windows.Forms.Control.Dispose%2A> method of the base class, to release the event when the application closes.</span></span> <span data-ttu-id="2e988-324">若要访问 Visual Basic 中的 <xref:System.Windows.Forms.Control.Dispose%2A> 方法，需要展开标记为“Windows 窗体设计器生成的代码”区域。</span><span class="sxs-lookup"><span data-stu-id="2e988-324">To access the <xref:System.Windows.Forms.Control.Dispose%2A> method in Visual Basic, you will need to expand the region labeled Windows Form Designer generated code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e988-325">系统事件代码运行独立于主应用程序的线程。</span><span class="sxs-lookup"><span data-stu-id="2e988-325">The system event code runs a thread separate from the main application.</span></span> <span data-ttu-id="2e988-326">如果不释放事件，挂钩到事件的代码在程序关闭后仍将运行。</span><span class="sxs-lookup"><span data-stu-id="2e988-326">If you do not release the event, the code that you hook up to the event will run even after the program is closed.</span></span>

    ```vb
    Protected Overloads Overrides Sub Dispose(ByVal disposing As Boolean)
        If disposing AndAlso components IsNot Nothing Then
            components.Dispose()
        End If
        RemoveHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _
           AddressOf Me.UserPreferenceChanged
        MyBase.Dispose(disposing)
    End Sub
    ```

    ```csharp
    protected override void Dispose(bool disposing)
    {
        if(disposing && components != null)
        {
            components.Dispose();
        }
        Microsoft.Win32.SystemEvents.UserPreferenceChanged
           -= new Microsoft.Win32.UserPreferenceChangedEventHandler(
           this.UserPreferenceChanged);
        base.Dispose( disposing );
    }
    ```

6. <span data-ttu-id="2e988-327">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="2e988-327">Press F5 to run the application.</span></span>

## <a name="conveying-important-information-by-means-other-than-sound"></a><span data-ttu-id="2e988-328">通过非声音方式传达重要信息</span><span class="sxs-lookup"><span data-stu-id="2e988-328">Conveying Important Information by Means Other Than Sound</span></span>

<span data-ttu-id="2e988-329">在此应用程序中，没有信息是仅靠声音传达的。</span><span class="sxs-lookup"><span data-stu-id="2e988-329">In this application, no information is conveyed by sound alone.</span></span> <span data-ttu-id="2e988-330">如果在应用程序中使用声音，则还应通过其他一些方式提供信息。</span><span class="sxs-lookup"><span data-stu-id="2e988-330">If you use sound in your application, then you should supply the information by some other means as well.</span></span>

#### <a name="to-supply-information-by-some-other-means-than-sound"></a><span data-ttu-id="2e988-331">以声音以外的其他方式提供信息</span><span class="sxs-lookup"><span data-stu-id="2e988-331">To supply information by some other means than sound</span></span>

1. <span data-ttu-id="2e988-332">使用 Windows API 函数 FlashWindow 使标题栏闪烁。</span><span class="sxs-lookup"><span data-stu-id="2e988-332">Make the title bar flash by using the Windows API function FlashWindow.</span></span> <span data-ttu-id="2e988-333">有关如何调用 Windows API 函数的示例，请参阅[演练：调用 Windows API](/dotnet/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis)。</span><span class="sxs-lookup"><span data-stu-id="2e988-333">For an example of how to call Windows API functions, see [Walkthrough: Calling Windows APIs](/dotnet/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis).</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e988-334">用户可能已启用 Windows SoundSentry 服务，它也会在系统声音通过计算机内置扬声器播放时使窗口闪烁。</span><span class="sxs-lookup"><span data-stu-id="2e988-334">The user may have the Windows SoundSentry service enabled, which will also cause the window to flash when the system sounds are played through the computer's built-in speaker.</span></span>

2. <span data-ttu-id="2e988-335">在非模式窗口中显示重要信息，以便用户可以响应它。</span><span class="sxs-lookup"><span data-stu-id="2e988-335">Display the important information in a non-modal window so that the user may respond to it.</span></span>

3. <span data-ttu-id="2e988-336">显示一个获取键盘焦点消息框。</span><span class="sxs-lookup"><span data-stu-id="2e988-336">Display a message box that acquires the keyboard focus.</span></span> <span data-ttu-id="2e988-337">在用户可能键入时避免使用此方法。</span><span class="sxs-lookup"><span data-stu-id="2e988-337">Avoid this method when the user may be typing.</span></span>

4. <span data-ttu-id="2e988-338">在任务栏的状态通知区域中显示一个状态指示器。</span><span class="sxs-lookup"><span data-stu-id="2e988-338">Display a status indicator in the status notification area of the taskbar.</span></span> <span data-ttu-id="2e988-339">有关详细信息，请参阅[使用 Windows 窗体 NotifyIcon 组件向任务栏添加应用程序图标](../controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)。</span><span class="sxs-lookup"><span data-stu-id="2e988-339">For details, see [Adding Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](../controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>

## <a name="testing-the-application"></a><span data-ttu-id="2e988-340">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="2e988-340">Testing the Application</span></span>

<span data-ttu-id="2e988-341">在部署应用程序之前，应测试已实现的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="2e988-341">Before deploying the application, you should test the accessibility features that you have implemented.</span></span>

#### <a name="to-test-accessibility-features"></a><span data-ttu-id="2e988-342">测试辅助功能</span><span class="sxs-lookup"><span data-stu-id="2e988-342">To test accessibility features</span></span>

1. <span data-ttu-id="2e988-343">若要测试键盘访问，请拔下鼠标，并仅使用键盘导航每个功能的用户界面。</span><span class="sxs-lookup"><span data-stu-id="2e988-343">To test keyboard access, unplug the mouse and navigate the user interface for each feature using only the keyboard.</span></span> <span data-ttu-id="2e988-344">确保只使用键盘即可执行所有任务。</span><span class="sxs-lookup"><span data-stu-id="2e988-344">Ensure that all tasks may be performed using the keyboard only.</span></span>

2. <span data-ttu-id="2e988-345">若要测试高对比度的支持，请在控制面板中选择“辅助功能选项”图标。</span><span class="sxs-lookup"><span data-stu-id="2e988-345">To test support of High Contrast, choose the Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="2e988-346">单击“显示”选项卡并选择“使用高对比度”复选框。</span><span class="sxs-lookup"><span data-stu-id="2e988-346">Click the Display tab and select the Use High Contrast check box.</span></span> <span data-ttu-id="2e988-347">导航到所有用户界面元素以确保会反映颜色和字体更改。</span><span class="sxs-lookup"><span data-stu-id="2e988-347">Navigate through all user interface elements to ensure that the color and font changes are reflected.</span></span> <span data-ttu-id="2e988-348">此外，确保忽略文本后面绘制的图像或图案。</span><span class="sxs-lookup"><span data-stu-id="2e988-348">Also, ensure that images or patterns drawn behind text are omitted.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e988-349">Windows NT 4 的控制面板中没有“辅助功能选项”图标。</span><span class="sxs-lookup"><span data-stu-id="2e988-349">Windows NT 4 does not have an Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="2e988-350">因此，更改 SystemInformation.HighContrast 设置的此过程不适用于 Windows NT 4。</span><span class="sxs-lookup"><span data-stu-id="2e988-350">Thus, this procedure for changing the SystemInformation.HighContrast setting does not work in Windows NT 4.</span></span>

3. <span data-ttu-id="2e988-351">其他工具也用于测试应用程序的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="2e988-351">Other tools are readily available for testing the accessibility of an application.</span></span>

4. <span data-ttu-id="2e988-352">若要测试公开键盘焦点，请运行放大镜。</span><span class="sxs-lookup"><span data-stu-id="2e988-352">To test exposing the keyboard focus, run Magnifier.</span></span> <span data-ttu-id="2e988-353">（若要打开它，请单击“开始”菜单，依次指向“程序”、“附件”和“辅助功能”，然后单击“放大镜”）。</span><span class="sxs-lookup"><span data-stu-id="2e988-353">(To open it, click the **Start** menu, point to **Programs**, point to **Accessories**, point to **Accessibility**, and then click **Magnifier**).</span></span> <span data-ttu-id="2e988-354">使用键盘 Tab 键和鼠标导航用户界面。</span><span class="sxs-lookup"><span data-stu-id="2e988-354">Navigate the user interface using both keyboard tabbing and the mouse.</span></span> <span data-ttu-id="2e988-355">确保在“放大镜”中正确跟踪所有导航。</span><span class="sxs-lookup"><span data-stu-id="2e988-355">Ensure that all navigation is tracked properly in **Magnifier**.</span></span>

5. <span data-ttu-id="2e988-356">若要测试公开屏幕元素，请运行检查并使用鼠标和 Tab 键选中每个元素。</span><span class="sxs-lookup"><span data-stu-id="2e988-356">To test exposing screen elements, run Inspect, and use both the mouse and the TAB key to reach each element.</span></span> <span data-ttu-id="2e988-357">确保“检查”窗口中名称、状态、角色、位置和值字段中显示的信息对于 UI 中每个对象的用户都有意义。</span><span class="sxs-lookup"><span data-stu-id="2e988-357">Ensure that the information presented in the Name, State, Role, Location, and Value fields of the Inspect window is meaningful to the user for each object in the UI.</span></span>
