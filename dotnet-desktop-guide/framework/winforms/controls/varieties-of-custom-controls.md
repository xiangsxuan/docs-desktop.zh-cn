---
title: 各种自定义控件
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- controls [Windows Forms], user controls
- controls [Windows Forms], types of
- composite controls [Windows Forms]
- extended controls [Windows Forms]
- controls [Windows Forms], extended
- user controls [Windows Forms]
- custom controls [Windows Forms]
- controls [Windows Forms], composite
ms.assetid: 3cea09e5-4344-4ccb-9858-b66ccac210ff
ms.openlocfilehash: e43b9a3fafd52c66681d4d6bbdd0e9bc39c6788a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973109"
---
# <a name="varieties-of-custom-controls"></a><span data-ttu-id="94525-102">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="94525-102">Varieties of Custom Controls</span></span>

<span data-ttu-id="94525-103">使用 .NET Framework 可以开发和实现新的控件。</span><span class="sxs-lookup"><span data-stu-id="94525-103">With the .NET Framework, you can develop and implement new controls.</span></span> <span data-ttu-id="94525-104">可以通过继承来扩展熟悉的用户控件和现有控件的功能。</span><span class="sxs-lookup"><span data-stu-id="94525-104">You can extend the functionality of the familiar user control as well as existing controls through inheritance.</span></span> <span data-ttu-id="94525-105">还可以编写自定义控件，这些控件执行自己的绘制。</span><span class="sxs-lookup"><span data-stu-id="94525-105">You can also write custom controls that perform their own painting.</span></span>  
  
 <span data-ttu-id="94525-106">确定创建何种类型的控件可能令人困惑。</span><span class="sxs-lookup"><span data-stu-id="94525-106">Deciding which kind of control to create can be confusing.</span></span> <span data-ttu-id="94525-107">本主题重点介绍各种可继承控件之间的差异，并提供有关如何为项目选择某种特定控件的信息。</span><span class="sxs-lookup"><span data-stu-id="94525-107">This topic highlights the differences among the various kinds of controls from which you can inherit, and provides you with information about how to choose a particular kind of control for your project.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94525-108">有关如何创作用于 Web 窗体的控件的信息，请参阅[开发自定义 ASP.NET 服务器控件](/previous-versions/aspnet/zt27tfhy(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="94525-108">For information about authoring a control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>  
  
## <a name="base-control-class"></a><span data-ttu-id="94525-109">基控件类</span><span class="sxs-lookup"><span data-stu-id="94525-109">Base Control Class</span></span>  

 <span data-ttu-id="94525-110"><xref:System.Windows.Forms.Control>类是 Windows 窗体控件的基类。</span><span class="sxs-lookup"><span data-stu-id="94525-110">The <xref:System.Windows.Forms.Control> class is the base class for Windows Forms controls.</span></span> <span data-ttu-id="94525-111">它提供了在 Windows 窗体应用程序中进行可视显示所需的基础结构。</span><span class="sxs-lookup"><span data-stu-id="94525-111">It provides the infrastructure required for visual display in Windows Forms applications.</span></span>  
  
 <span data-ttu-id="94525-112"><xref:System.Windows.Forms.Control>类执行以下任务以在 Windows 窗体应用程序中提供视觉显示：</span><span class="sxs-lookup"><span data-stu-id="94525-112">The <xref:System.Windows.Forms.Control> class performs the following tasks to provide visual display in Windows Forms applications:</span></span>  
  
- <span data-ttu-id="94525-113">公开窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="94525-113">Exposes a window handle.</span></span>  
  
- <span data-ttu-id="94525-114">管理消息路由。</span><span class="sxs-lookup"><span data-stu-id="94525-114">Manages message routing.</span></span>  
  
- <span data-ttu-id="94525-115">提供鼠标和键盘事件，以及许多其他用户界面事件。</span><span class="sxs-lookup"><span data-stu-id="94525-115">Provides mouse and keyboard events, and many other user interface events.</span></span>  
  
- <span data-ttu-id="94525-116">提供高级布局功能。</span><span class="sxs-lookup"><span data-stu-id="94525-116">Provides advanced layout features.</span></span>  
  
- <span data-ttu-id="94525-117">包含特定于可视显示的多个属性，如 <xref:System.Windows.Forms.Control.ForeColor%2A> 、、 <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.Control.Height%2A> 和 <xref:System.Windows.Forms.Control.Width%2A> 。</span><span class="sxs-lookup"><span data-stu-id="94525-117">Contains many properties specific to visual display, such as <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, and <xref:System.Windows.Forms.Control.Width%2A>.</span></span>  
  
- <span data-ttu-id="94525-118">为 Windows 窗体控件充当 Microsoft® ActiveX® 控件提供必需的安全性和线程支持。</span><span class="sxs-lookup"><span data-stu-id="94525-118">Provides the security and threading support necessary for a Windows Forms control to act as a Microsoft® ActiveX® control.</span></span>  
  
 <span data-ttu-id="94525-119">由于基类提供了大量基础结构，因此使开发自己的 Windows 窗体控件变得相对简单。</span><span class="sxs-lookup"><span data-stu-id="94525-119">Because so much of the infrastructure is provided by the base class, it is relatively easy to develop your own Windows Forms controls.</span></span>  
  
## <a name="kinds-of-controls"></a><span data-ttu-id="94525-120">控件种类</span><span class="sxs-lookup"><span data-stu-id="94525-120">Kinds of Controls</span></span>  

 <span data-ttu-id="94525-121">Windows 窗体支持三种用户定义的控件：复合、扩展和自定义。</span><span class="sxs-lookup"><span data-stu-id="94525-121">Windows Forms supports three kinds of user-defined controls: *composite*, *extended*, and *custom*.</span></span> <span data-ttu-id="94525-122">以下各节分别介绍各种控件，并就如何选择项目中使用的控件种类提供建议。</span><span class="sxs-lookup"><span data-stu-id="94525-122">The following sections describe each kind of control and give recommendations for choosing the kind to use in your projects.</span></span>  
  
### <a name="composite-controls"></a><span data-ttu-id="94525-123">复合控件</span><span class="sxs-lookup"><span data-stu-id="94525-123">Composite Controls</span></span>  

 <span data-ttu-id="94525-124">复合控件是封装在公共容器内的 Windows 窗体控件的集合。</span><span class="sxs-lookup"><span data-stu-id="94525-124">A composite control is a collection of Windows Forms controls encapsulated in a common container.</span></span> <span data-ttu-id="94525-125">这种控件有时称为用户控件。</span><span class="sxs-lookup"><span data-stu-id="94525-125">This kind of control is sometimes called a *user control*.</span></span> <span data-ttu-id="94525-126">其包含的控件称为构成控件。</span><span class="sxs-lookup"><span data-stu-id="94525-126">The contained controls are called *constituent controls*.</span></span>  
  
 <span data-ttu-id="94525-127">复合控件包含与每个包含的 Windows 窗体控件相关联的所有固有功能，允许选择性地公开和绑定它们的属性。</span><span class="sxs-lookup"><span data-stu-id="94525-127">A composite control holds all of the inherent functionality associated with each of the contained Windows Forms controls and enables you to selectively expose and bind their properties.</span></span> <span data-ttu-id="94525-128">复合控件还提供了大量的默认键盘处理功能，用户不需要进行任何额外的开发。</span><span class="sxs-lookup"><span data-stu-id="94525-128">A composite control also provides a great deal of default keyboard handling functionality with no extra development effort on your part.</span></span>  
  
 <span data-ttu-id="94525-129">例如，可以生成复合控件，以显示来自数据库的客户地址数据。</span><span class="sxs-lookup"><span data-stu-id="94525-129">For example, a composite control could be built to display customer address data from a database.</span></span> <span data-ttu-id="94525-130">此控件可能包括 <xref:System.Windows.Forms.DataGridView> 用于显示数据库字段的控件、 <xref:System.Windows.Forms.BindingSource> 用于处理与数据源的绑定的控件，以及 <xref:System.Windows.Forms.BindingNavigator> 用于移动记录的控件。</span><span class="sxs-lookup"><span data-stu-id="94525-130">This control could include a <xref:System.Windows.Forms.DataGridView> control to display the database fields, a <xref:System.Windows.Forms.BindingSource> to handle binding to a data source, and a <xref:System.Windows.Forms.BindingNavigator> control to move through the records.</span></span> <span data-ttu-id="94525-131">可以选择性地公开数据绑定属性，还可以将整个控件打包并在不同应用程序之间重复使用。</span><span class="sxs-lookup"><span data-stu-id="94525-131">You could selectively expose data binding properties, and you could package and reuse the entire control from application to application.</span></span> <span data-ttu-id="94525-132">有关这种复合控件的示例，请参阅[如何：应用 Windows 窗体控件中的特性](how-to-apply-attributes-in-windows-forms-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="94525-132">For an example of this kind of composite control, see [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="94525-133">若要创作复合控件，请从 <xref:System.Windows.Forms.UserControl> 类派生。</span><span class="sxs-lookup"><span data-stu-id="94525-133">To author a composite control, derive from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="94525-134"><xref:System.Windows.Forms.UserControl>基类为子控件提供了键盘路由，并使子控件可以作为组工作。</span><span class="sxs-lookup"><span data-stu-id="94525-134">The <xref:System.Windows.Forms.UserControl> base class provides keyboard routing for child controls and enables child controls to work as a group.</span></span> <span data-ttu-id="94525-135">有关详细信息，请参阅[开发复合 Windows 窗体控件](developing-a-composite-windows-forms-control.md)。</span><span class="sxs-lookup"><span data-stu-id="94525-135">For more information, see [Developing a Composite Windows Forms Control](developing-a-composite-windows-forms-control.md).</span></span>  
  
 <span data-ttu-id="94525-136">建议</span><span class="sxs-lookup"><span data-stu-id="94525-136">**Recommendation**</span></span>  
  
 <span data-ttu-id="94525-137">如果为以下情况，则从 <xref:System.Windows.Forms.UserControl> 类继承：</span><span class="sxs-lookup"><span data-stu-id="94525-137">Inherit from the <xref:System.Windows.Forms.UserControl> class if:</span></span>  
  
- <span data-ttu-id="94525-138">你想要将多个 Windows 窗体控件的功能组合到单个可重用单元。</span><span class="sxs-lookup"><span data-stu-id="94525-138">You want to combine the functionality of several Windows Forms controls into a single reusable unit.</span></span>  
  
### <a name="extended-controls"></a><span data-ttu-id="94525-139">扩展控件</span><span class="sxs-lookup"><span data-stu-id="94525-139">Extended Controls</span></span>  

 <span data-ttu-id="94525-140">你可以从任何现有的 Windows 窗体控件派生继承的控件。</span><span class="sxs-lookup"><span data-stu-id="94525-140">You can derive an inherited control from any existing Windows Forms control.</span></span> <span data-ttu-id="94525-141">使用此方法，你可以保留 Windows 窗体控件的所有固有功能，然后通过添加自定义属性、方法或其他功能来扩展该功能。</span><span class="sxs-lookup"><span data-stu-id="94525-141">With this approach, you can retain all of the inherent functionality of a Windows Forms control, and then extend that functionality by adding custom properties, methods, or other features.</span></span> <span data-ttu-id="94525-142">可以使用此选项重写基控件的绘制逻辑，然后通过更改该控件的外观来扩展其用户界面。</span><span class="sxs-lookup"><span data-stu-id="94525-142">With this option, you can override the base control's paint logic, and then extend its user interface by changing its appearance.</span></span>  
  
 <span data-ttu-id="94525-143">例如，你可以创建一个从控件派生的控件 <xref:System.Windows.Forms.Button> ，该控件跟踪用户已单击的次数。</span><span class="sxs-lookup"><span data-stu-id="94525-143">For example, you can create a control derived from the <xref:System.Windows.Forms.Button> control that tracks how many times a user has clicked it.</span></span>  
  
 <span data-ttu-id="94525-144">在某些控件中，还可以通过重写基类的方法，向控件的图形用户界面添加自定义外观 <xref:System.Windows.Forms.Control.OnPaint%2A> 。</span><span class="sxs-lookup"><span data-stu-id="94525-144">In some controls, you can also add a custom appearance to the graphical user interface of your control by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span> <span data-ttu-id="94525-145">对于跟踪单击的扩展按钮，你可以重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法以调用的基实现 <xref:System.Windows.Forms.Control.OnPaint%2A> ，然后在 <xref:System.Windows.Forms.Button> 控件的工作区的一个角落绘制单击计数。</span><span class="sxs-lookup"><span data-stu-id="94525-145">For an extended button that tracks clicks, you can override the <xref:System.Windows.Forms.Control.OnPaint%2A> method to call the base implementation of <xref:System.Windows.Forms.Control.OnPaint%2A>, and then draw the click count in one corner of the <xref:System.Windows.Forms.Button> control's client area.</span></span>  
  
 <span data-ttu-id="94525-146">建议</span><span class="sxs-lookup"><span data-stu-id="94525-146">**Recommendation**</span></span>  
  
 <span data-ttu-id="94525-147">如果为以下情况，则从 Windows 窗体控件继承：</span><span class="sxs-lookup"><span data-stu-id="94525-147">Inherit from a Windows Forms control if:</span></span>  
  
- <span data-ttu-id="94525-148">大部分所需功能与现有的 Windows 窗体控件相同。</span><span class="sxs-lookup"><span data-stu-id="94525-148">Most of the functionality you need is already identical to an existing Windows Forms control.</span></span>  
  
- <span data-ttu-id="94525-149">不需要自定义图形用户界面，或者想为现有控件设计一个新的图形用户界面。</span><span class="sxs-lookup"><span data-stu-id="94525-149">You do not need a custom graphical user interface, or you want to design a new graphical user interface for an existing control.</span></span>  
  
### <a name="custom-controls"></a><span data-ttu-id="94525-150">自定义控件</span><span class="sxs-lookup"><span data-stu-id="94525-150">Custom Controls</span></span>  

 <span data-ttu-id="94525-151">创建控件的另一种方法是从开始，通过从继承开始，从头开始创建一个控件 <xref:System.Windows.Forms.Control> 。</span><span class="sxs-lookup"><span data-stu-id="94525-151">Another way to create a control is to create one substantially from the beginning by inheriting from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="94525-152"><xref:System.Windows.Forms.Control>类提供控件所需的所有基本功能，包括鼠标和键盘处理事件，但不包括特定于控件的功能或图形界面。</span><span class="sxs-lookup"><span data-stu-id="94525-152">The <xref:System.Windows.Forms.Control> class provides all of the basic functionality required by controls, including mouse and keyboard handling events, but no control-specific functionality or graphical interface.</span></span>  
  
 <span data-ttu-id="94525-153">通过从类继承来创建控件 <xref:System.Windows.Forms.Control> 需要比从 <xref:System.Windows.Forms.UserControl> 或现有 Windows 窗体控件继承更多的想法和精力。</span><span class="sxs-lookup"><span data-stu-id="94525-153">Creating a control by inheriting from the <xref:System.Windows.Forms.Control> class requires much more thought and effort than inheriting from <xref:System.Windows.Forms.UserControl> or an existing Windows Forms control.</span></span> <span data-ttu-id="94525-154">由于用户还需执行大量的实现，因此，控件可以具有比复合控件或扩展控件更好的灵活性，而且可以使控件完全满足自己的需要。</span><span class="sxs-lookup"><span data-stu-id="94525-154">Because a great deal of implementation is left for you, your control can have greater flexibility than a composite or extended control, and you can tailor your control to suit your exact needs.</span></span>  
  
 <span data-ttu-id="94525-155">若要实现自定义控件，必须为 <xref:System.Windows.Forms.Control.OnPaint%2A> 控件的事件以及所需的任何特定于功能的代码编写代码。</span><span class="sxs-lookup"><span data-stu-id="94525-155">To implement a custom control, you must write code for the <xref:System.Windows.Forms.Control.OnPaint%2A> event of the control, as well as any feature-specific code you need.</span></span> <span data-ttu-id="94525-156">您还可以重写 <xref:System.Windows.Forms.Control.WndProc%2A> 方法并直接处理 windows 消息。</span><span class="sxs-lookup"><span data-stu-id="94525-156">You can also override the <xref:System.Windows.Forms.Control.WndProc%2A> method and handle windows messages directly.</span></span> <span data-ttu-id="94525-157">这是创建控件的最强大的方法，但若要有效地使用此技术，需熟悉 Microsoft Win32® API。</span><span class="sxs-lookup"><span data-stu-id="94525-157">This is the most powerful way to create a control, but to use this technique effectively, you need to be familiar with the Microsoft Win32® API.</span></span>  
  
 <span data-ttu-id="94525-158">时钟控件即是一个自定义控件，它复制模拟时钟的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="94525-158">An example of a custom control is a clock control that duplicates the appearance and behavior of an analog clock.</span></span> <span data-ttu-id="94525-159">调用自定义绘制是为了响应 <xref:System.Windows.Forms.Timer.Tick> 来自内部组件的事件 <xref:System.Windows.Forms.Timer> 。</span><span class="sxs-lookup"><span data-stu-id="94525-159">Custom painting is invoked to cause the hands of the clock to move in response to <xref:System.Windows.Forms.Timer.Tick> events from an internal <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="94525-160">有关详细信息，请参阅[如何：开发简单的 Windows 窗体控件](how-to-develop-a-simple-windows-forms-control.md)。</span><span class="sxs-lookup"><span data-stu-id="94525-160">For more information, see [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md).</span></span>  
  
 <span data-ttu-id="94525-161">建议</span><span class="sxs-lookup"><span data-stu-id="94525-161">**Recommendation**</span></span>  
  
 <span data-ttu-id="94525-162">如果为以下情况，则从 <xref:System.Windows.Forms.Control> 类继承：</span><span class="sxs-lookup"><span data-stu-id="94525-162">Inherit from the <xref:System.Windows.Forms.Control> class if:</span></span>  
  
- <span data-ttu-id="94525-163">你想要提供控件的自定义图形表示形式。</span><span class="sxs-lookup"><span data-stu-id="94525-163">You want to provide a custom graphical representation of your control.</span></span>  
  
- <span data-ttu-id="94525-164">你需要实现不能通过标准控件实现的自定义功能。</span><span class="sxs-lookup"><span data-stu-id="94525-164">You need to implement custom functionality that is not available through standard controls.</span></span>  
  
### <a name="activex-controls"></a><span data-ttu-id="94525-165">ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="94525-165">ActiveX Controls</span></span>  

 <span data-ttu-id="94525-166">尽管 Windows 窗体基础结构已为承载 Windows 窗体控件进行了优化，但仍可以使用 ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="94525-166">Although the Windows Forms infrastructure has been optimized to host Windows Forms controls, you can still use ActiveX controls.</span></span> <span data-ttu-id="94525-167">Visual Studio 中对此任务提供支持。</span><span class="sxs-lookup"><span data-stu-id="94525-167">There is support for this task in Visual Studio.</span></span> <span data-ttu-id="94525-168">有关详细信息，请参阅[如何：向 Windows 窗体添加 ActiveX 控件](how-to-add-activex-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="94525-168">For more information, see [How to: Add ActiveX Controls to Windows Forms](how-to-add-activex-controls-to-windows-forms.md).</span></span>  
  
### <a name="windowless-controls"></a><span data-ttu-id="94525-169">无窗口控件</span><span class="sxs-lookup"><span data-stu-id="94525-169">Windowless Controls</span></span>  

 <span data-ttu-id="94525-170">Microsoft Visual Basic® 6.0 和 ActiveX 技术支持无窗口控件。</span><span class="sxs-lookup"><span data-stu-id="94525-170">The Microsoft Visual Basic® 6.0and ActiveX technologies support *windowless* controls.</span></span> <span data-ttu-id="94525-171">Windows 窗体中不支持无窗口控件。</span><span class="sxs-lookup"><span data-stu-id="94525-171">Windowless controls are not supported in Windows Forms.</span></span>  
  
## <a name="custom-design-experience"></a><span data-ttu-id="94525-172">自定义设计体验</span><span class="sxs-lookup"><span data-stu-id="94525-172">Custom Design Experience</span></span>  

 <span data-ttu-id="94525-173">如果需要实现自定义设计时体验，可以创作自己的设计器。</span><span class="sxs-lookup"><span data-stu-id="94525-173">If you need to implement a custom design-time experience, you can author your own designer.</span></span> <span data-ttu-id="94525-174">对于复合控件，从或类派生自定义设计器类 <xref:System.Windows.Forms.Design.ParentControlDesigner> <xref:System.Windows.Forms.Design.DocumentDesigner> 。</span><span class="sxs-lookup"><span data-stu-id="94525-174">For composite controls, derive your custom designer class from the <xref:System.Windows.Forms.Design.ParentControlDesigner> or the <xref:System.Windows.Forms.Design.DocumentDesigner> classes.</span></span> <span data-ttu-id="94525-175">对于扩展控件和自定义控件，从类派生自定义设计器类 <xref:System.Windows.Forms.Design.ControlDesigner> 。</span><span class="sxs-lookup"><span data-stu-id="94525-175">For extended and custom controls, derive your custom designer class from the <xref:System.Windows.Forms.Design.ControlDesigner> class.</span></span>  
  
 <span data-ttu-id="94525-176">使用将 <xref:System.ComponentModel.DesignerAttribute> 控件与设计器关联。</span><span class="sxs-lookup"><span data-stu-id="94525-176">Use the <xref:System.ComponentModel.DesignerAttribute> to associate your control with your designer.</span></span> <span data-ttu-id="94525-177">有关详细信息，请参阅[扩展设计时支持](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))和[如何：创建利用设计时功能的 Windows 窗体控件](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="94525-177">For more information, see [Extending Design-Time Support](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)) and [How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94525-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94525-178">See also</span></span>

- [<span data-ttu-id="94525-179">使用 .NET Framework 开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="94525-179">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="94525-180">如何：开发简单的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="94525-180">How to: Develop a Simple Windows Forms Control</span></span>](how-to-develop-a-simple-windows-forms-control.md)
- [<span data-ttu-id="94525-181">开发复合 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="94525-181">Developing a Composite Windows Forms Control</span></span>](developing-a-composite-windows-forms-control.md)
- <span data-ttu-id="94525-182">[扩展设计时支持](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="94525-182">[Extending Design-Time Support](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>
- <span data-ttu-id="94525-183">[如何：创建利用设计时功能的 Windows 窗体控件](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="94525-183">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>
