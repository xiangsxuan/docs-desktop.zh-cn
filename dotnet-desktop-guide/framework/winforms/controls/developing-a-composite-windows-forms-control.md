---
title: 开发复合控件
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: 6887de62857fc260fb53e33f462b07af80658178
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970080"
---
# <a name="develop-a-composite-windows-forms-control"></a><span data-ttu-id="cf346-102">开发复合 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="cf346-102">Develop a composite Windows Forms control</span></span>

<span data-ttu-id="cf346-103">可以通过组合其它 Windows 窗体控件来开发复合 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="cf346-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="cf346-104">派生自的复合控件 <xref:System.Web.UI.UserControl> 称为用户控件。</span><span class="sxs-lookup"><span data-stu-id="cf346-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="cf346-105">基类 <xref:System.Windows.Forms.UserControl> 为子控件提供了键盘路由，从而确保子控件可以接收焦点。</span><span class="sxs-lookup"><span data-stu-id="cf346-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="cf346-106">有关用户控件的示例，请参阅 <xref:System.Windows.Forms.UserControl> [如何：在 Windows 窗体控件中应用特性中](how-to-apply-attributes-in-windows-forms-controls.md)的示例。</span><span class="sxs-lookup"><span data-stu-id="cf346-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).</span></span>

<span data-ttu-id="cf346-107">Visual Studio 中的 Windows 窗体设计器为创作用户控件提供丰富的设计时支持。</span><span class="sxs-lookup"><span data-stu-id="cf346-107">The Windows Forms designer in Visual Studio provides rich design-time support for authoring user controls.</span></span>

- [<span data-ttu-id="cf346-108">如何：在“选择工具箱项”对话框中显示控件</span><span class="sxs-lookup"><span data-stu-id="cf346-108">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)

- [<span data-ttu-id="cf346-109">演练：使用 DesignerSerializationVisibilityAttribute 序列化标准类型的集合</span><span class="sxs-lookup"><span data-stu-id="cf346-109">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)

- [<span data-ttu-id="cf346-110">演练：使用 Visual C# 从 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="cf346-110">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)

- [<span data-ttu-id="cf346-111">如何：为控件提供工具箱位图</span><span class="sxs-lookup"><span data-stu-id="cf346-111">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)

- [<span data-ttu-id="cf346-112">如何：从现有 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="cf346-112">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)

- [<span data-ttu-id="cf346-113">演练：设计时调试自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="cf346-113">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)

- [<span data-ttu-id="cf346-114">如何：从 Control 类继承</span><span class="sxs-lookup"><span data-stu-id="cf346-114">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)

- [<span data-ttu-id="cf346-115">如何：测试 UserControl 的运行时行为</span><span class="sxs-lookup"><span data-stu-id="cf346-115">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)

- [<span data-ttu-id="cf346-116">如何：设计时将控件与窗体边缘对齐</span><span class="sxs-lookup"><span data-stu-id="cf346-116">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)

- [<span data-ttu-id="cf346-117">如何：从 UserControl 类继承</span><span class="sxs-lookup"><span data-stu-id="cf346-117">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)

- [<span data-ttu-id="cf346-118">如何：创作 Windows 窗体的控件</span><span class="sxs-lookup"><span data-stu-id="cf346-118">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)

- [<span data-ttu-id="cf346-119">如何：创作复合控件</span><span class="sxs-lookup"><span data-stu-id="cf346-119">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)

- [<span data-ttu-id="cf346-120">演练：使用 Visual C# 创作复合控件</span><span class="sxs-lookup"><span data-stu-id="cf346-120">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)

- [<span data-ttu-id="cf346-121">演练：创建利用 Visual Studio Design-Time 功能的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="cf346-121">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

- <span data-ttu-id="cf346-122">[如何：创建利用设计时功能的 Windows 窗体控件](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="cf346-122">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>

## <a name="see-also"></a><span data-ttu-id="cf346-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf346-123">See also</span></span>

- [<span data-ttu-id="cf346-124">如何：应用 Windows 窗体控件中的特性</span><span class="sxs-lookup"><span data-stu-id="cf346-124">How to: Apply Attributes in Windows Forms Controls</span></span>](how-to-apply-attributes-in-windows-forms-controls.md)
- [<span data-ttu-id="cf346-125">使用 .NET Framework 开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="cf346-125">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="cf346-126">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="cf346-126">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
