---
title: 自定义控件的类型
description: 了解可在 .NET 的 Windows 窗体中创建的不同类型的自定义控件。
ms.date: 10/26/2020
ms.topic: overview
f1_keywords:
- UserControl
helpviewer_keywords:
- controls [Windows Forms], user controls
- controls [Windows Forms], types of
- composite controls [Windows Forms]
- extended controls [Windows Forms]
- controls [Windows Forms], extended
- user controls [Windows Forms]
- custom controls [Windows Forms]
- controls [Windows Forms], composite
ms.openlocfilehash: 25430adf6efbb4c1f323496ce46cdea5aa0bb95c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941960"
---
# <a name="types-of-custom-controls-windows-forms-net"></a><span data-ttu-id="2ef56-103">自定义控件的类型（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="2ef56-103">Types of custom controls (Windows Forms .NET)</span></span>

<span data-ttu-id="2ef56-104">可使用 Windows 窗体开发和实现新的控件。</span><span class="sxs-lookup"><span data-stu-id="2ef56-104">With Windows Forms, you can develop and implement new controls.</span></span> <span data-ttu-id="2ef56-105">可以创建新的用户控件，通过继承来修改现有控件，并编写可自行进行绘制的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="2ef56-105">You can create a new user control, modify existing controls through inheritance, and write a custom control that does its own painting.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="2ef56-106">确定创建何种类型的控件可能令人困惑。</span><span class="sxs-lookup"><span data-stu-id="2ef56-106">Deciding which kind of control to create can be confusing.</span></span> <span data-ttu-id="2ef56-107">本文重点介绍各种可继承控件之间的差异，并提供有关如何为项目选择某种特定控件的信息。</span><span class="sxs-lookup"><span data-stu-id="2ef56-107">This article highlights the differences among the various kinds of controls from which you can inherit, and provides you with information about how to choose a particular type of control for your project.</span></span>

<table>
<thead>
  <tr>
    <th><span data-ttu-id="2ef56-108">如果出现如下情况</span><span class="sxs-lookup"><span data-stu-id="2ef56-108">If ...</span></span></th>
    <th><span data-ttu-id="2ef56-109">创建以下内容</span><span class="sxs-lookup"><span data-stu-id="2ef56-109">Create a ...</span></span></th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>
        <ul>
            <li><span data-ttu-id="2ef56-110">你想要将多个 Windows 窗体控件的功能组合到单个可重用单元。</span><span class="sxs-lookup"><span data-stu-id="2ef56-110">You want to combine the functionality of several Windows Forms controls into a single reusable unit.</span></span></li>
        </ul>
    </td>
    <td><span data-ttu-id="2ef56-111"><a href="#composite-controls">复合控件</a>，方式是从 <a href="/dotnet/api/system.windows.forms.usercontrol">System.Windows.Forms.UserControl</a> 继承。</span><span class="sxs-lookup"><span data-stu-id="2ef56-111"><a href="#composite-controls">Composite control</a> by inheriting from <a href="/dotnet/api/system.windows.forms.usercontrol">System.Windows.Forms.UserControl</a>.</span></span></td>
  </tr>
  <tr>
    <td>
        <ul>
            <li><span data-ttu-id="2ef56-112">大部分所需功能与现有的 Windows 窗体控件相同。</span><span class="sxs-lookup"><span data-stu-id="2ef56-112">Most of the functionality you need is already identical to an existing Windows Forms control.</span></span></li>
            <li><span data-ttu-id="2ef56-113">你不需要自定义图形用户界面，或者想为现有控件设计一个新的图形用户界面。</span><span class="sxs-lookup"><span data-stu-id="2ef56-113">You don't need a custom graphical user interface, or you want to design a new graphical user interface for an existing control.</span></span></li>
        </ul>
    </td>
    <td><span data-ttu-id="2ef56-114"><a href="#extended-controls">扩展控件</a>，方式是从某一特定 Windows 窗体控件继承。</span><span class="sxs-lookup"><span data-stu-id="2ef56-114"><a href="#extended-controls">Extended control</a> by inheriting from a specific Windows Forms control.</span></span></td>
  </tr>
  <tr>
    <td>
        <ul>
            <li><span data-ttu-id="2ef56-115">你想要提供控件的自定义图形表示形式。</span><span class="sxs-lookup"><span data-stu-id="2ef56-115">You want to provide a custom graphical representation of your control.</span></span></li>
            <li><span data-ttu-id="2ef56-116">你需要实现不能通过标准控件实现的自定义功能。</span><span class="sxs-lookup"><span data-stu-id="2ef56-116">You need to implement custom functionality that isn't available through standard controls.</span></span></li>
        </ul>
    </td>
    <td><span data-ttu-id="2ef56-117"><a href="#custom-controls">自定义控件</a>，方式是从 <a href="/dotnet/api/system.windows.forms.control">System.Windows.Forms.Control</a> 继承。</span><span class="sxs-lookup"><span data-stu-id="2ef56-117"><a href="#custom-controls">Custom control</a> by inheriting from <a href="/dotnet/api/system.windows.forms.control">System.Windows.Forms.Control</a>.</span></span></td>
  </tr>
</tbody>
</table>

## <a name="base-control-class"></a><span data-ttu-id="2ef56-118">基控件类</span><span class="sxs-lookup"><span data-stu-id="2ef56-118">Base Control Class</span></span>

<span data-ttu-id="2ef56-119"><xref:System.Windows.Forms.Control> 类是 Windows 窗体控件的基类。</span><span class="sxs-lookup"><span data-stu-id="2ef56-119">The <xref:System.Windows.Forms.Control> class is the base class for Windows Forms controls.</span></span> <span data-ttu-id="2ef56-120">它提供了在 Windows 窗体应用程序中进行可视化显示所需的基础结构，并提供了以下功能：</span><span class="sxs-lookup"><span data-stu-id="2ef56-120">It provides the infrastructure required for visual display in Windows Forms applications and provides the following capabilities:</span></span>

- <span data-ttu-id="2ef56-121">公开窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="2ef56-121">Exposes a window handle.</span></span>
- <span data-ttu-id="2ef56-122">管理消息路由。</span><span class="sxs-lookup"><span data-stu-id="2ef56-122">Manages message routing.</span></span>
- <span data-ttu-id="2ef56-123">提供鼠标和键盘事件，以及许多其他用户界面事件。</span><span class="sxs-lookup"><span data-stu-id="2ef56-123">Provides mouse and keyboard events, and many other user interface events.</span></span>
- <span data-ttu-id="2ef56-124">提供高级布局功能。</span><span class="sxs-lookup"><span data-stu-id="2ef56-124">Provides advanced layout features.</span></span>
- <span data-ttu-id="2ef56-125">包含特定于可视化显示的多个属性，如 <xref:System.Windows.Forms.Control.ForeColor%2A>、<xref:System.Windows.Forms.Control.BackColor%2A>、<xref:System.Windows.Forms.Control.Height%2A> 和 <xref:System.Windows.Forms.Control.Width%2A>。</span><span class="sxs-lookup"><span data-stu-id="2ef56-125">Contains many properties specific to visual display, such as <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, and <xref:System.Windows.Forms.Control.Width%2A>.</span></span>
- <span data-ttu-id="2ef56-126">为 Windows 窗体控件充当 Microsoft® ActiveX® 控件提供必需的安全性和线程支持。</span><span class="sxs-lookup"><span data-stu-id="2ef56-126">Provides the security and threading support necessary for a Windows Forms control to act as a Microsoft® ActiveX® control.</span></span>

<span data-ttu-id="2ef56-127">由于基类提供了大量基础结构，因此开发你自己的 Windows 窗体控件相对比较简单。</span><span class="sxs-lookup"><span data-stu-id="2ef56-127">Because so much of the infrastructure is provided by the base class, it's relatively easy to develop your own Windows Forms controls.</span></span>

## <a name="composite-controls"></a><span data-ttu-id="2ef56-128">复合控件</span><span class="sxs-lookup"><span data-stu-id="2ef56-128">Composite Controls</span></span>

<span data-ttu-id="2ef56-129">复合控件是封装在公共容器内的 Windows 窗体控件的集合。</span><span class="sxs-lookup"><span data-stu-id="2ef56-129">A composite control is a collection of Windows Forms controls encapsulated in a common container.</span></span> <span data-ttu-id="2ef56-130">这种控件有时称为用户控件。</span><span class="sxs-lookup"><span data-stu-id="2ef56-130">This kind of control is sometimes called a *user control*.</span></span> <span data-ttu-id="2ef56-131">其包含的控件称为构成控件。</span><span class="sxs-lookup"><span data-stu-id="2ef56-131">The contained controls are called *constituent controls*.</span></span>

<span data-ttu-id="2ef56-132">复合控件包含与每个包含的 Windows 窗体控件相关联的所有固有功能，允许选择性地公开和绑定它们的属性。</span><span class="sxs-lookup"><span data-stu-id="2ef56-132">A composite control holds all of the inherent functionality associated with each of the contained Windows Forms controls and enables you to selectively expose and bind their properties.</span></span> <span data-ttu-id="2ef56-133">复合控件还提供了大量的默认键盘处理功能，用户不需要进行任何额外的开发。</span><span class="sxs-lookup"><span data-stu-id="2ef56-133">A composite control also provides a great deal of default keyboard handling functionality with no extra development effort on your part.</span></span>

<span data-ttu-id="2ef56-134">例如，可以生成复合控件，以显示来自数据库的客户地址数据。</span><span class="sxs-lookup"><span data-stu-id="2ef56-134">For example, a composite control could be built to display customer address data from a database.</span></span> <span data-ttu-id="2ef56-135">此控件将包括用于显示数据库字段的 <xref:System.Windows.Forms.DataGridView> 控件、用于处理到数据源的绑定的 <xref:System.Windows.Forms.BindingSource>，以及用于在记录之间移动的 <xref:System.Windows.Forms.BindingNavigator> 控件。</span><span class="sxs-lookup"><span data-stu-id="2ef56-135">This control would include a <xref:System.Windows.Forms.DataGridView> control to display the database fields, a <xref:System.Windows.Forms.BindingSource> to handle binding to a data source, and a <xref:System.Windows.Forms.BindingNavigator> control to move through the records.</span></span> <span data-ttu-id="2ef56-136">可以选择性地公开数据绑定属性，还可以将整个控件打包并在不同应用程序之间重复使用。</span><span class="sxs-lookup"><span data-stu-id="2ef56-136">You could selectively expose data binding properties, and you could package and reuse the entire control from application to application.</span></span><!-- TODO For an example of this kind of composite control, see [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).-->

<span data-ttu-id="2ef56-137">若要创作复合控件，请从 <xref:System.Windows.Forms.UserControl> 类派生。</span><span class="sxs-lookup"><span data-stu-id="2ef56-137">To author a composite control, derive from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="2ef56-138">基类 <xref:System.Windows.Forms.UserControl> 为子控件提供了键盘路由，并使子控件可以作为组进行工作。</span><span class="sxs-lookup"><span data-stu-id="2ef56-138">The <xref:System.Windows.Forms.UserControl> base class provides keyboard routing for child controls and enables child controls to work as a group.</span></span><!-- TODO For more information, see [Developing a Composite Windows Forms Control](developing-a-composite-windows-forms-control.md).-->

## <a name="extended-controls"></a><span data-ttu-id="2ef56-139">扩展控件</span><span class="sxs-lookup"><span data-stu-id="2ef56-139">Extended Controls</span></span>

<span data-ttu-id="2ef56-140">你可以从任何现有的 Windows 窗体控件派生继承的控件。</span><span class="sxs-lookup"><span data-stu-id="2ef56-140">You can derive an inherited control from any existing Windows Forms control.</span></span> <span data-ttu-id="2ef56-141">使用此方法，你可以保留 Windows 窗体控件的所有固有功能，然后通过添加自定义属性、方法或其他功能来扩展该功能。</span><span class="sxs-lookup"><span data-stu-id="2ef56-141">With this approach, you can keep all of the inherent functionality of a Windows Forms control, and then extend that functionality by adding custom properties, methods, or other features.</span></span> <span data-ttu-id="2ef56-142">可以使用此选项重写基控件的绘制逻辑，然后通过更改该控件的外观来扩展其用户界面。</span><span class="sxs-lookup"><span data-stu-id="2ef56-142">With this option, you can override the base control's paint logic, and then extend its user interface by changing its appearance.</span></span>

<span data-ttu-id="2ef56-143">例如，可以创建一个由 <xref:System.Windows.Forms.Button> 控件派生的控件，并用它来跟踪用户的单击次数。</span><span class="sxs-lookup"><span data-stu-id="2ef56-143">For example, you can create a control derived from the <xref:System.Windows.Forms.Button> control that tracks how many times a user has clicked it.</span></span>

<span data-ttu-id="2ef56-144">在某些控件中，也可以通过重写基类的 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法为控件的图形用户界面添加自定义外观。</span><span class="sxs-lookup"><span data-stu-id="2ef56-144">In some controls, you can also add a custom appearance to the graphical user interface of your control by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span> <span data-ttu-id="2ef56-145">对于跟踪单击次数的扩展按钮，可以重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法以调用 <xref:System.Windows.Forms.Control.OnPaint%2A> 的基实现，然后在 <xref:System.Windows.Forms.Button> 控件的工作区的一角绘制单击计数。</span><span class="sxs-lookup"><span data-stu-id="2ef56-145">For an extended button that tracks clicks, you can override the <xref:System.Windows.Forms.Control.OnPaint%2A> method to call the base implementation of <xref:System.Windows.Forms.Control.OnPaint%2A>, and then draw the click count in one corner of the <xref:System.Windows.Forms.Button> control's client area.</span></span>

## <a name="custom-controls"></a><span data-ttu-id="2ef56-146">自定义控件</span><span class="sxs-lookup"><span data-stu-id="2ef56-146">Custom Controls</span></span>

<span data-ttu-id="2ef56-147">创建控件的另一种方法是通过从 <xref:System.Windows.Forms.Control> 继承，从头开始充分创建一个控件。</span><span class="sxs-lookup"><span data-stu-id="2ef56-147">Another way to create a control is to create one substantially from the beginning by inheriting from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="2ef56-148"><xref:System.Windows.Forms.Control> 类提供控件所需的所有基本功能（包括鼠标和键盘处理事件），但不提供特定于控件的功能或图形界面。</span><span class="sxs-lookup"><span data-stu-id="2ef56-148">The <xref:System.Windows.Forms.Control> class provides all of the basic functionality required by controls, including mouse and keyboard handling events, but no control-specific functionality or graphical interface.</span></span>

<span data-ttu-id="2ef56-149">相比从 <xref:System.Windows.Forms.UserControl> 或现有 Windows 窗体控件继承来说，通过从 <xref:System.Windows.Forms.Control> 类继承来创建控件需要花费更多心思和精力。</span><span class="sxs-lookup"><span data-stu-id="2ef56-149">Creating a control by inheriting from the <xref:System.Windows.Forms.Control> class requires much more thought and effort than inheriting from <xref:System.Windows.Forms.UserControl> or an existing Windows Forms control.</span></span> <span data-ttu-id="2ef56-150">由于用户还需执行大量的实现，因此，控件可以具有比复合控件或扩展控件更好的灵活性，而且可以使控件完全满足自己的需要。</span><span class="sxs-lookup"><span data-stu-id="2ef56-150">Because a great deal of implementation is left for you, your control can have greater flexibility than a composite or extended control, and you can tailor your control to suit your exact needs.</span></span>

<span data-ttu-id="2ef56-151">若要实现自定义控件，必须编写该控件的 <xref:System.Windows.Forms.Control.OnPaint%2A> 事件的代码，以及所需的任何功能特定的代码。</span><span class="sxs-lookup"><span data-stu-id="2ef56-151">To implement a custom control, you must write code for the <xref:System.Windows.Forms.Control.OnPaint%2A> event of the control, as well as any feature-specific code you need.</span></span> <span data-ttu-id="2ef56-152">还可以重写 <xref:System.Windows.Forms.Control.WndProc%2A> 方法并直接处理窗口消息。</span><span class="sxs-lookup"><span data-stu-id="2ef56-152">You can also override the <xref:System.Windows.Forms.Control.WndProc%2A> method and handle windows messages directly.</span></span> <span data-ttu-id="2ef56-153">这是创建控件的最强大的方法，但若要有效地使用此技术，需熟悉 Microsoft Win32® API。</span><span class="sxs-lookup"><span data-stu-id="2ef56-153">This is the most powerful way to create a control, but to use this technique effectively, you need to be familiar with the Microsoft Win32® API.</span></span>

<span data-ttu-id="2ef56-154">时钟控件即是一个自定义控件，它复制模拟时钟的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="2ef56-154">An example of a custom control is a clock control that duplicates the appearance and behavior of an analog clock.</span></span> <span data-ttu-id="2ef56-155">调用自定义绘制来使指针移动，以响应来自内部 <xref:System.Windows.Forms.Timer> 组件的 <xref:System.Windows.Forms.Timer.Tick> 事件。</span><span class="sxs-lookup"><span data-stu-id="2ef56-155">Custom painting is invoked to cause the hands of the clock to move in response to <xref:System.Windows.Forms.Timer.Tick> events from an internal <xref:System.Windows.Forms.Timer> component.</span></span><!-- TODO For more information, see [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md).-->

## <a name="activex-controls"></a><span data-ttu-id="2ef56-156">ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="2ef56-156">ActiveX Controls</span></span>

<span data-ttu-id="2ef56-157">尽管 Windows 窗体基础结构已为承载 Windows 窗体控件进行了优化，但仍可以使用 ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="2ef56-157">Although the Windows Forms infrastructure has been optimized to host Windows Forms controls, you can still use ActiveX controls.</span></span> <span data-ttu-id="2ef56-158">Visual Studio 中对此任务提供支持。</span><span class="sxs-lookup"><span data-stu-id="2ef56-158">There's support for this task in Visual Studio.</span></span><!-- TODO For more information, see [How to: Add ActiveX Controls to Windows Forms](how-to-add-activex-controls-to-windows-forms.md).-->

## <a name="windowless-controls"></a><span data-ttu-id="2ef56-159">无窗口控件</span><span class="sxs-lookup"><span data-stu-id="2ef56-159">Windowless Controls</span></span>

<span data-ttu-id="2ef56-160">Microsoft Visual Basic® 6.0 和 ActiveX 技术支持无窗口控件。</span><span class="sxs-lookup"><span data-stu-id="2ef56-160">The Microsoft Visual Basic® 6.0 and ActiveX technologies support *windowless* controls.</span></span> <span data-ttu-id="2ef56-161">Windows 窗体中不支持无窗口控件。</span><span class="sxs-lookup"><span data-stu-id="2ef56-161">Windowless controls aren't supported in Windows Forms.</span></span>

## <a name="custom-design-experience"></a><span data-ttu-id="2ef56-162">自定义设计体验</span><span class="sxs-lookup"><span data-stu-id="2ef56-162">Custom Design Experience</span></span>

<span data-ttu-id="2ef56-163">如果需要实现自定义设计时体验，可以创作自己的设计器。</span><span class="sxs-lookup"><span data-stu-id="2ef56-163">If you need to implement a custom design-time experience, you can author your own designer.</span></span> <span data-ttu-id="2ef56-164">对于复合控件，从 <xref:System.Windows.Forms.Design.ParentControlDesigner> 或 <xref:System.Windows.Forms.Design.DocumentDesigner> 类派生自定义设计器类。</span><span class="sxs-lookup"><span data-stu-id="2ef56-164">For composite controls, derive your custom designer class from the <xref:System.Windows.Forms.Design.ParentControlDesigner> or the <xref:System.Windows.Forms.Design.DocumentDesigner> classes.</span></span> <span data-ttu-id="2ef56-165">对于扩展控件和自定义控件，从 <xref:System.Windows.Forms.Design.ControlDesigner> 类派生自定义设计器类。</span><span class="sxs-lookup"><span data-stu-id="2ef56-165">For extended and custom controls, derive your custom designer class from the <xref:System.Windows.Forms.Design.ControlDesigner> class.</span></span>

<span data-ttu-id="2ef56-166">使用 <xref:System.ComponentModel.DesignerAttribute> 将控件与设计器关联。</span><span class="sxs-lookup"><span data-stu-id="2ef56-166">Use the <xref:System.ComponentModel.DesignerAttribute> to associate your control with your designer.</span></span>

<span data-ttu-id="2ef56-167">以下信息已过时，但可能会对你有所帮助。</span><span class="sxs-lookup"><span data-stu-id="2ef56-167">The following information is out of date but may help you.</span></span>

- <span data-ttu-id="2ef56-168">[(Visual Studio 2013) 扩展设计时支持](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="2ef56-168">[(Visual Studio 2013) Extending Design-Time Support](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).</span></span>
- <span data-ttu-id="2ef56-169">[(Visual Studio 2013) 如何：创建利用设计时功能的 Windows 窗体控件](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="2ef56-169">[(Visual Studio 2013) How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).</span></span>

## <a name="see-also"></a><span data-ttu-id="2ef56-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ef56-170">See also</span></span>

- [<span data-ttu-id="2ef56-171">使用控件的概述（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="2ef56-171">Overview of Using Controls (Windows Forms .NET)</span></span>](overview.md)

<!-- TODO: link to the ..\custom-controls\ content 

- [Developing Custom Windows Forms Controls](developing-custom-windows-forms-controls.md)
- [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md)
- [Developing a Composite Windows Forms Control](developing-a-composite-windows-forms-control.md)
-->
