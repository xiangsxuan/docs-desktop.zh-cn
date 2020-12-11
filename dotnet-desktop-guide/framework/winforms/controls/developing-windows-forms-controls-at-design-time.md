---
title: 在设计时开发控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 4e192983c5818ddb81ed4581d91ae61375bb808e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970076"
---
# <a name="develop-windows-forms-controls-at-design-time"></a><span data-ttu-id="2c000-102">在设计时开发 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="2c000-102">Develop Windows Forms controls at design time</span></span>

<span data-ttu-id="2c000-103">.NET Framework 为控件创作者提供了丰富的控件创作技术。</span><span class="sxs-lookup"><span data-stu-id="2c000-103">For control authors, the .NET Framework provides a wealth of control authoring technology.</span></span> <span data-ttu-id="2c000-104">作者不再局限于设计作为现有控件集合的复合控件。</span><span class="sxs-lookup"><span data-stu-id="2c000-104">Authors are no longer limited to designing composite controls that act as a collection of preexisting controls.</span></span> <span data-ttu-id="2c000-105">通过继承，可根据现有复合控件或现有 Windows 窗体控件创建自己的控件。</span><span class="sxs-lookup"><span data-stu-id="2c000-105">Through inheritance, you can create your own controls from preexisting composite controls or preexisting Windows Forms controls.</span></span> <span data-ttu-id="2c000-106">还可以自己设计实现自定义绘制的控件。</span><span class="sxs-lookup"><span data-stu-id="2c000-106">You can also design your own controls that implement custom painting.</span></span> <span data-ttu-id="2c000-107">这些选项对可视化界面的设计和功能赋予了很大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="2c000-107">These options enable a great deal of flexibility to the design and functionality of the visual interface.</span></span> <span data-ttu-id="2c000-108">若要利用这些功能，应熟悉基于对象的编程概念。</span><span class="sxs-lookup"><span data-stu-id="2c000-108">To take advantage of these features, you should be familiar with object-based programming concepts.</span></span>

> [!NOTE]
> <span data-ttu-id="2c000-109">无需透彻地理解继承，但你可能会发现 [ (Visual Basic) 引用继承基础知识 ](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)会很有用。</span><span class="sxs-lookup"><span data-stu-id="2c000-109">It is not necessary to have a thorough understanding of inheritance, but you may find it useful to refer to [Inheritance basics (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics).</span></span>

<span data-ttu-id="2c000-110">如果要创建在 Web 窗体上使用的自定义控件，请参阅[开发自定义 ASP.NET 服务器控件](/previous-versions/aspnet/zt27tfhy(v=vs.100)).。</span><span class="sxs-lookup"><span data-stu-id="2c000-110">If you want to create custom controls to use on Web Forms, see [Developing Custom ASP.NET Server Controls](/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2c000-111">在本节中</span><span class="sxs-lookup"><span data-stu-id="2c000-111">In this section</span></span>

<span data-ttu-id="2c000-112">[演练：创作复合控件](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-112">[Walkthrough: Authoring a Composite Control](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span></span>\
<span data-ttu-id="2c000-113">演示如何在 C# 中创建简单的复合控件。</span><span class="sxs-lookup"><span data-stu-id="2c000-113">Shows how to create a simple composite control in C#.</span></span>

<span data-ttu-id="2c000-114">[演练：从 Windows 窗体控件继承](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-114">[Walkthrough: Inheriting from a Windows Forms Control](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)</span></span>\
<span data-ttu-id="2c000-115">演示如何在 C# 中使用继承创建简单的 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="2c000-115">Shows how to create a simple Windows Forms control using inheritance in C#.</span></span>

<span data-ttu-id="2c000-116">[演练：使用设计操作执行常规任务](perform-common-tasks-design-actions.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-116">[Walkthrough: Perform common tasks using designer actions](perform-common-tasks-design-actions.md)</span></span>\
<span data-ttu-id="2c000-117">演示如何在 Windows 窗体控件上使用智能标记功能。</span><span class="sxs-lookup"><span data-stu-id="2c000-117">Shows how to use the smart tag feature on Windows Forms controls.</span></span>

<span data-ttu-id="2c000-118">[演练：通过 DesignerSerializationVisibilityAttribute 序列化标准类型的集合](serializing-collections-designerserializationvisibilityattribute.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-118">[Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)</span></span>\
<span data-ttu-id="2c000-119">演示如何使用 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> 特性序列化集合。</span><span class="sxs-lookup"><span data-stu-id="2c000-119">Shows how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> attribute to serialize a collection.</span></span>

<span data-ttu-id="2c000-120">[演练：在设计时调试自定义 Windows 窗体控件](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-120">[Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)</span></span>\
<span data-ttu-id="2c000-121">演示如何调试 Windows 窗体控件的设计时行为。</span><span class="sxs-lookup"><span data-stu-id="2c000-121">Shows how to debug the design-time behavior of a Windows Forms control.</span></span>

<span data-ttu-id="2c000-122">[演练：创建利用 Visual Studio Design-Time 功能的 Windows 窗体控件](creating-a-wf-control-design-time-features.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-122">[Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md)</span></span>\
<span data-ttu-id="2c000-123">演示如何将复合控件紧密集成到设计环境中。</span><span class="sxs-lookup"><span data-stu-id="2c000-123">Shows how to tightly integrate a composite control into the design environment.</span></span>

<span data-ttu-id="2c000-124">[如何：创作 Windows 窗体的控件](how-to-author-controls-for-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-124">[How to: Author Controls for Windows Forms](how-to-author-controls-for-windows-forms.md)</span></span>\
<span data-ttu-id="2c000-125">概述实现 Windows 窗体控件的注意事项。</span><span class="sxs-lookup"><span data-stu-id="2c000-125">Provides an overview of considerations for implementing a Windows Forms control.</span></span>

<span data-ttu-id="2c000-126">[如何：创作复合控件](how-to-author-composite-controls.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-126">[How to: Author Composite Controls](how-to-author-composite-controls.md)</span></span>\
<span data-ttu-id="2c000-127">演示如何通过继承复合控件来创建控件。</span><span class="sxs-lookup"><span data-stu-id="2c000-127">Shows how to create a control by inheriting from a composite control.</span></span>

<span data-ttu-id="2c000-128">[如何：从 UserControl 类继承](how-to-inherit-from-the-usercontrol-class.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-128">[How to: Inherit from the UserControl Class](how-to-inherit-from-the-usercontrol-class.md)</span></span>\
<span data-ttu-id="2c000-129">概述复合控件的创建过程。</span><span class="sxs-lookup"><span data-stu-id="2c000-129">Provides an overview of the procedure for creating a composite control.</span></span>

<span data-ttu-id="2c000-130">[如何：从现有 Windows 窗体控件继承](how-to-inherit-from-existing-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-130">[How to: Inherit from Existing Windows Forms Controls](how-to-inherit-from-existing-windows-forms-controls.md)</span></span>\
<span data-ttu-id="2c000-131">演示如何通过从 control 类继承来创建扩展控件 <xref:System.Windows.Forms.Button> 。</span><span class="sxs-lookup"><span data-stu-id="2c000-131">Shows how to create an extended control by inheriting from the <xref:System.Windows.Forms.Button> control class.</span></span>

<span data-ttu-id="2c000-132">[如何：从 Control 类继承](how-to-inherit-from-the-control-class.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-132">[How to: Inherit from the Control Class](how-to-inherit-from-the-control-class.md)</span></span>\
<span data-ttu-id="2c000-133">概述如何创建扩展的控件。</span><span class="sxs-lookup"><span data-stu-id="2c000-133">Provides an overview of creating an extended control.</span></span>

<span data-ttu-id="2c000-134">[如何：在设计时将控件与窗体边缘对齐](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-134">[How to: Align a Control to the Edges of Forms at Design Time](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)</span></span>\
<span data-ttu-id="2c000-135">演示如何使用属性将 <xref:System.Windows.Forms.Control.Dock%2A> 控件与它所占有窗体的边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="2c000-135">Shows how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>

<span data-ttu-id="2c000-136">[如何：在 "选择工具箱项" 对话框中显示控件](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-136">[How to: Display a Control in the Choose Toolbox Items Dialog Box](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span></span>\
<span data-ttu-id="2c000-137">演示安装控件以将其显示在“自定义工具箱”对话框中的过程。</span><span class="sxs-lookup"><span data-stu-id="2c000-137">Shows the procedure for installing your control so that it appears in the **Customize Toolbox** dialog box.</span></span>

<span data-ttu-id="2c000-138">[如何：为控件提供工具箱位图](how-to-provide-a-toolbox-bitmap-for-a-control.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-138">[How to: Provide a Toolbox Bitmap for a Control](how-to-provide-a-toolbox-bitmap-for-a-control.md)</span></span>\
<span data-ttu-id="2c000-139">演示如何使用在 <xref:System.Drawing.ToolboxBitmapAttribute> **工具箱** 中的自定义控件旁边显示一个图标。</span><span class="sxs-lookup"><span data-stu-id="2c000-139">Shows how to use the <xref:System.Drawing.ToolboxBitmapAttribute> to display an icon next to your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="2c000-140">[如何：测试 UserControl 的 Run-Time 行为](how-to-test-the-run-time-behavior-of-a-usercontrol.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-140">[How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)</span></span>\
<span data-ttu-id="2c000-141">演示如何使用 **UserControl 测试容器** 来测试组合控件的行为。</span><span class="sxs-lookup"><span data-stu-id="2c000-141">Shows how to use the **UserControl Test Container** to test the behavior of a composite control.</span></span>

<span data-ttu-id="2c000-142">[Windows 窗体设计器中的设计时错误](design-time-errors-in-the-windows-forms-designer.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-142">[Design-Time Errors in the Windows Forms Designer](design-time-errors-in-the-windows-forms-designer.md)</span></span>\
<span data-ttu-id="2c000-143">说明 Windows 窗体设计器加载失败时出现在 Microsoft Visual Studio 中的设计时错误列表的含义和用法。</span><span class="sxs-lookup"><span data-stu-id="2c000-143">Explains the meaning and use of the Design-Time Error List that appears in Microsoft Visual Studio when the Windows Forms designer fails to load.</span></span>

<span data-ttu-id="2c000-144">[控件和组件创作疑难解答](troubleshooting-control-and-component-authoring.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-144">[Troubleshooting Control and Component Authoring](troubleshooting-control-and-component-authoring.md)</span></span>\
<span data-ttu-id="2c000-145">演示如何诊断和解决创作自定义组件或控件时可能出现的常见问题。</span><span class="sxs-lookup"><span data-stu-id="2c000-145">Shows how to diagnose and fix common issues that can occur when you author a custom component or control.</span></span>

## <a name="reference"></a><span data-ttu-id="2c000-146">参考</span><span class="sxs-lookup"><span data-stu-id="2c000-146">Reference</span></span>

- <xref:System.Windows.Forms.Control?displayProperty=nameWithType>

- <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>

## <a name="related-sections"></a><span data-ttu-id="2c000-147">相关章节</span><span class="sxs-lookup"><span data-stu-id="2c000-147">Related sections</span></span>

<span data-ttu-id="2c000-148">[利用 .NET Framework 开发自定义 Windows 窗体控件](developing-custom-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-148">[Developing Custom Windows Forms Controls with the .NET Framework](developing-custom-windows-forms-controls.md)</span></span>\
<span data-ttu-id="2c000-149">讨论如何通过 .NET Framework 创建自己的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="2c000-149">Discusses how to create your own custom controls with the .NET Framework.</span></span>

<span data-ttu-id="2c000-150">[语言独立性和 Language-Independent 组件](/dotnet/standard/language-independence-and-language-independent-components)</span><span class="sxs-lookup"><span data-stu-id="2c000-150">[Language Independence and Language-Independent Components](/dotnet/standard/language-independence-and-language-independent-components)</span></span>\
<span data-ttu-id="2c000-151">介绍公共语言运行时，它旨在简化组件的创建和使用。</span><span class="sxs-lookup"><span data-stu-id="2c000-151">Introduces the common language runtime, which is designed to simplify the creation and use of components.</span></span> <span data-ttu-id="2c000-152">这种简化的一个重要方面是提高了采用不同编程语言编写的组件间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="2c000-152">An important aspect of this simplification is enhanced interoperability between components written using different programming languages.</span></span> <span data-ttu-id="2c000-153">通过公共语言规范 (CLS) 可创建使用多个编程语言的工具和组件。</span><span class="sxs-lookup"><span data-stu-id="2c000-153">The Common Language Specification (CLS) makes it possible to create tools and components that work with multiple programming languages.</span></span>

<span data-ttu-id="2c000-154">[演练：用自定义组件自动填充工具箱](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)</span><span class="sxs-lookup"><span data-stu-id="2c000-154">[Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)</span></span>\
<span data-ttu-id="2c000-155">描述如何在“自定义工具箱”对话框中显示组件或控件。</span><span class="sxs-lookup"><span data-stu-id="2c000-155">Describes how to enable your component or control to be displayed in the **Customize Toolbox** dialog box.</span></span>
