---
title: 控件类型建议
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- user controls [Windows Forms], when to use
- custom controls [Windows Forms], types
- controls [Windows Forms], creating
ms.assetid: 5235fe9d-c36a-4c08-ae76-6cb90b50085e
ms.openlocfilehash: c26b25fba47c9e63290d64ca3b6cd9a4bfd7c3b1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970178"
---
# <a name="control-type-recommendations"></a><span data-ttu-id="42777-102">控件类型建议</span><span class="sxs-lookup"><span data-stu-id="42777-102">Control Type Recommendations</span></span>

<span data-ttu-id="42777-103">.NET Framework 使你能够开发和实现新控件。</span><span class="sxs-lookup"><span data-stu-id="42777-103">The .NET Framework gives you power to develop and implement new controls.</span></span> <span data-ttu-id="42777-104">除了已熟悉的用户控件，现在你会发现你能够编写自定义控件用于执行其自己的绘制，甚至能够通过继承扩展现有控件的功能。</span><span class="sxs-lookup"><span data-stu-id="42777-104">In addition to the familiar user control, you will now find that you are able to write custom controls that perform their own painting, and are even able to extend the functionality of existing controls through inheritance.</span></span> <span data-ttu-id="42777-105">决定创建哪种类型的控件可能令人困惑。</span><span class="sxs-lookup"><span data-stu-id="42777-105">Deciding which type of control to create can be confusing.</span></span> <span data-ttu-id="42777-106">本节重点介绍可以从其继承的各类控件之间的区别，并提供要为你的项目选择的类型的相关注意事项。</span><span class="sxs-lookup"><span data-stu-id="42777-106">This section highlights the differences between the various types of controls from which you can inherit, and gives considerations regarding the type to choose for your project.</span></span>

> [!NOTE]
> <span data-ttu-id="42777-107">如果要编写在 Web 窗体上使用的控件，请参阅[开发自定义 ASP.NET 服务器控件](/previous-versions/aspnet/zt27tfhy(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="42777-107">If you want to author a control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>

## <a name="inheriting-from-a-windows-forms-control"></a><span data-ttu-id="42777-108">从 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="42777-108">Inheriting from a Windows Forms Control</span></span>

<span data-ttu-id="42777-109">你可以从任何现有的 Windows 窗体控件派生继承的控件。</span><span class="sxs-lookup"><span data-stu-id="42777-109">You can derive an inherited control from any existing Windows Forms control.</span></span> <span data-ttu-id="42777-110">此方法使你可以保留 Windows 窗体控件的所有固有功能，然后通过添加自定义属性、方法或其他功能来扩展该功能。</span><span class="sxs-lookup"><span data-stu-id="42777-110">This approach allows you to retain all of the inherent functionality of a Windows Forms control, and to then extend that functionality by adding custom properties, methods, or other functionality.</span></span> <span data-ttu-id="42777-111">例如，可以创建一个派生自 <xref:System.Windows.Forms.TextBox> 的控件，它只能接受数字并自动将输入转换为一个值。</span><span class="sxs-lookup"><span data-stu-id="42777-111">For example, you might create a control derived from <xref:System.Windows.Forms.TextBox> that can accept only numbers and automatically converts input into a value.</span></span> <span data-ttu-id="42777-112">此类控件可能包含验证代码，该代码每当文本框中的文本更改时即被调用，而且可能具有附加属性，即“值”。</span><span class="sxs-lookup"><span data-stu-id="42777-112">Such a control might contain validation code that was called whenever the text in the text box changed, and could have an additional property, Value.</span></span> <span data-ttu-id="42777-113">在某些控件中，还可以通过重写基类的方法，向控件的图形界面添加自定义外观 <xref:System.Windows.Forms.Control.OnPaint%2A> 。</span><span class="sxs-lookup"><span data-stu-id="42777-113">In some controls, you can also add a custom appearance to the graphical interface of your control by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span>

 <span data-ttu-id="42777-114">如果为以下情况，则从 Windows 窗体控件继承：</span><span class="sxs-lookup"><span data-stu-id="42777-114">Inherit from a Windows Forms control if:</span></span>

- <span data-ttu-id="42777-115">大部分所需功能与现有的 Windows 窗体控件相同。</span><span class="sxs-lookup"><span data-stu-id="42777-115">Most of the functionality you need is already identical to an existing Windows Forms control.</span></span>

- <span data-ttu-id="42777-116">不需要自定义图形界面，或者你想要为现有控件设计一个新图形前端。</span><span class="sxs-lookup"><span data-stu-id="42777-116">You do not need a custom graphical interface, or you want to design a new graphical front end for an existing control.</span></span>

## <a name="inheriting-from-the-usercontrol-class"></a><span data-ttu-id="42777-117">从 UserControl 类继承</span><span class="sxs-lookup"><span data-stu-id="42777-117">Inheriting from the UserControl Class</span></span>

<span data-ttu-id="42777-118">用户控件是封装到一个公共容器中的 Windows 窗体控件的集合。</span><span class="sxs-lookup"><span data-stu-id="42777-118">A user control is a collection of Windows Forms controls encapsulated into a common container.</span></span> <span data-ttu-id="42777-119">容器保有与每个 Windows 窗体控件关联的所有固有功能，并允许你选择性地公开和绑定它们的属性。</span><span class="sxs-lookup"><span data-stu-id="42777-119">The container holds all of the inherent functionality associated with each of the Windows Forms controls and allows you to selectively expose and bind their properties.</span></span> <span data-ttu-id="42777-120">用户控件的一个示例可能是这样一个控件，其生成的目的是显示来自数据库的客户地址数据。</span><span class="sxs-lookup"><span data-stu-id="42777-120">An example of a user control might be a control built to display customer address data from a database.</span></span> <span data-ttu-id="42777-121">该控件将包括多个用以显示每个字段的文本框以及用以在记录中导航的按钮控件。</span><span class="sxs-lookup"><span data-stu-id="42777-121">This control would include several textboxes to display each field, and button controls to navigate through the records.</span></span> <span data-ttu-id="42777-122">可以选择性地公开数据绑定属性，并可以打包整个控件，并将其重复应用于不同的应用程序。</span><span class="sxs-lookup"><span data-stu-id="42777-122">Data-binding properties could be selectively exposed, and the entire control could be packaged and reused from application to application.</span></span>

<span data-ttu-id="42777-123">如果为以下情况，则从 <xref:System.Windows.Forms.UserControl> 类继承：</span><span class="sxs-lookup"><span data-stu-id="42777-123">Inherit from the <xref:System.Windows.Forms.UserControl> class if:</span></span>

- <span data-ttu-id="42777-124">你想要将多个 Windows 窗体控件的功能组合到单个可重用单元。</span><span class="sxs-lookup"><span data-stu-id="42777-124">You want to combine the functionality of several Windows Forms controls into a single reusable unit.</span></span>

## <a name="inheriting-from-the-control-class"></a><span data-ttu-id="42777-125">从 Control 类继承</span><span class="sxs-lookup"><span data-stu-id="42777-125">Inheriting from the Control Class</span></span>

<span data-ttu-id="42777-126">创建控件的另一种方法是通过从 <xref:System.Windows.Forms.Control> 继承，从头开始充分创建一个控件。</span><span class="sxs-lookup"><span data-stu-id="42777-126">Another way to create a control is to create one substantially from scratch by inheriting from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="42777-127"><xref:System.Windows.Forms.Control> 类提供控件（例如，事件）所需的所有基本功能，但没有特定于控件的功能或图形界面。</span><span class="sxs-lookup"><span data-stu-id="42777-127">The <xref:System.Windows.Forms.Control> class provides all of the basic functionality required by controls (for example, events), but no control-specific functionality or graphical interface.</span></span> <span data-ttu-id="42777-128">相比从用户控件或现有 Windows 窗体控件继承来说，通过从 <xref:System.Windows.Forms.Control> 类继承来创建控件需要更多的心思和精力。</span><span class="sxs-lookup"><span data-stu-id="42777-128">Creating a control by inheriting from the <xref:System.Windows.Forms.Control> class requires a lot more thought and effort than inheriting from user control or an existing Windows Forms control.</span></span> <span data-ttu-id="42777-129">作者必须为控件的 <xref:System.Windows.Forms.Control.OnPaint%2A> 事件以及任何所需的功能特定的代码编写代码。</span><span class="sxs-lookup"><span data-stu-id="42777-129">The author must write code for the <xref:System.Windows.Forms.Control.OnPaint%2A> event of the control, as well as any functionality specific code that is needed.</span></span> <span data-ttu-id="42777-130">但是允许更大的灵活性，并且可以自定义定制控件以满足你的具体需求。</span><span class="sxs-lookup"><span data-stu-id="42777-130">Greater flexibility is allowed, however, and you can custom tailor a control to suit your exact needs.</span></span> <span data-ttu-id="42777-131">自定义控件的一个示例是一个时钟控件，它复制了模拟时钟的外观和操作。</span><span class="sxs-lookup"><span data-stu-id="42777-131">An example of a custom control is a clock control that duplicates the look and action of an analog clock.</span></span> <span data-ttu-id="42777-132">将调用自定义绘制来使指针移动，以响应来自内部计时器组件的 <xref:System.Windows.Forms.Timer.Tick> 事件。</span><span class="sxs-lookup"><span data-stu-id="42777-132">Custom painting would be invoked to cause the hands of the clock to move in response to <xref:System.Windows.Forms.Timer.Tick> events from an internal timer component.</span></span>

<span data-ttu-id="42777-133">如果为以下情况，则从 <xref:System.Windows.Forms.Control> 类继承：</span><span class="sxs-lookup"><span data-stu-id="42777-133">Inherit from the <xref:System.Windows.Forms.Control> class if:</span></span>

- <span data-ttu-id="42777-134">你想要提供控件的自定义图形表示形式。</span><span class="sxs-lookup"><span data-stu-id="42777-134">You want to provide a custom graphical representation of your control.</span></span>

- <span data-ttu-id="42777-135">你需要实现不能通过标准控件实现的自定义功能。</span><span class="sxs-lookup"><span data-stu-id="42777-135">You need to implement custom functionality that is not available through standard controls.</span></span>

## <a name="related-articles"></a><span data-ttu-id="42777-136">相关文章</span><span class="sxs-lookup"><span data-stu-id="42777-136">Related articles</span></span>

- [<span data-ttu-id="42777-137">如何：在“选择工具箱项”对话框中显示控件</span><span class="sxs-lookup"><span data-stu-id="42777-137">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)

- [<span data-ttu-id="42777-138">演练：使用 DesignerSerializationVisibilityAttribute 序列化标准类型的集合</span><span class="sxs-lookup"><span data-stu-id="42777-138">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)

- [<span data-ttu-id="42777-139">演练：从 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="42777-139">Walkthrough: Inheriting from a Windows Forms Control</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)

- [<span data-ttu-id="42777-140">如何：为控件提供工具箱位图</span><span class="sxs-lookup"><span data-stu-id="42777-140">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)

- [<span data-ttu-id="42777-141">如何：从现有 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="42777-141">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)

- [<span data-ttu-id="42777-142">演练：设计时调试自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="42777-142">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)

- [<span data-ttu-id="42777-143">如何：从 Control 类继承</span><span class="sxs-lookup"><span data-stu-id="42777-143">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)

- [<span data-ttu-id="42777-144">如何：测试 UserControl 的运行时行为</span><span class="sxs-lookup"><span data-stu-id="42777-144">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)

- [<span data-ttu-id="42777-145">如何：设计时将控件与窗体边缘对齐</span><span class="sxs-lookup"><span data-stu-id="42777-145">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)

- [<span data-ttu-id="42777-146">如何：从 UserControl 类继承</span><span class="sxs-lookup"><span data-stu-id="42777-146">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)

- [<span data-ttu-id="42777-147">如何：创作 Windows 窗体的控件</span><span class="sxs-lookup"><span data-stu-id="42777-147">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)

- [<span data-ttu-id="42777-148">如何：创作复合控件</span><span class="sxs-lookup"><span data-stu-id="42777-148">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)

- [<span data-ttu-id="42777-149">演练：创作复合控件</span><span class="sxs-lookup"><span data-stu-id="42777-149">Walkthrough: Authoring a Composite Control</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)

- [<span data-ttu-id="42777-150">演练：创建利用 Visual Studio Design-Time 功能的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="42777-150">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

- <span data-ttu-id="42777-151">[如何：创建利用设计时功能的 Windows 窗体控件](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="42777-151">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>

## <a name="see-also"></a><span data-ttu-id="42777-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42777-152">See also</span></span>

- [<span data-ttu-id="42777-153">如何：开发简单的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="42777-153">How to: Develop a Simple Windows Forms Control</span></span>](how-to-develop-a-simple-windows-forms-control.md)
- [<span data-ttu-id="42777-154">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="42777-154">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
