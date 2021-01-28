---
title: 如何：从 Control 类继承
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
ms.openlocfilehash: e897519a7c4ba4f16e315e69322c27543964c215
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957703"
---
# <a name="how-to-inherit-from-the-control-class"></a><span data-ttu-id="72cf4-102">如何：从 Control 类继承</span><span class="sxs-lookup"><span data-stu-id="72cf4-102">How to: Inherit from the Control Class</span></span>

<span data-ttu-id="72cf4-103">如果要创建完全自定义的控件以在 Windows 窗体上使用，应从 <xref:System.Windows.Forms.Control> 类继承。</span><span class="sxs-lookup"><span data-stu-id="72cf4-103">If you want to create a completely custom control to use on a Windows Form, you should inherit from the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="72cf4-104">从类继承时 <xref:System.Windows.Forms.Control> ，需要执行更多规划和实现，它还提供了最大范围的选项。</span><span class="sxs-lookup"><span data-stu-id="72cf4-104">While inheriting from the <xref:System.Windows.Forms.Control> class requires that you perform more planning and implementation, it also provides you with the largest range of options.</span></span> <span data-ttu-id="72cf4-105">从继承时 <xref:System.Windows.Forms.Control> ，您将继承使控件工作的非常基本的功能。</span><span class="sxs-lookup"><span data-stu-id="72cf4-105">When inheriting from <xref:System.Windows.Forms.Control>, you inherit the very basic functionality that makes controls work.</span></span> <span data-ttu-id="72cf4-106">类中固有的功能 <xref:System.Windows.Forms.Control> 通过键盘和鼠标处理用户输入，定义控件的边界和大小，提供 windows 句柄，并提供消息处理和安全性。</span><span class="sxs-lookup"><span data-stu-id="72cf4-106">The functionality inherent in the <xref:System.Windows.Forms.Control> class handles user input through the keyboard and mouse, defines the bounds and size of the control, provides a windows handle, and provides message handling and security.</span></span> <span data-ttu-id="72cf4-107">它没有纳入任何绘图功能（这里指的是控件的图形界面的实际呈现），也没有纳入任何特定的用户交互功能。</span><span class="sxs-lookup"><span data-stu-id="72cf4-107">It does not incorporate any painting, which in this case is the actual rendering of the graphical interface of the control, nor does it incorporate any specific user interaction functionality.</span></span> <span data-ttu-id="72cf4-108">必须通过自定义代码提供所有的这些功能。</span><span class="sxs-lookup"><span data-stu-id="72cf4-108">You must provide all of these aspects through custom code.</span></span>

## <a name="to-create-a-custom-control"></a><span data-ttu-id="72cf4-109">创建自定义控件</span><span class="sxs-lookup"><span data-stu-id="72cf4-109">To create a custom control</span></span>

1. <span data-ttu-id="72cf4-110">在 Visual Studio 中，创建一个新的 " **Windows 应用程序** " 或 " **windows 控件库** " 项目。</span><span class="sxs-lookup"><span data-stu-id="72cf4-110">In Visual Studio, create a new **Windows Application** or **Windows Control Library** project.</span></span>

2. <span data-ttu-id="72cf4-111">从“项目”菜单中，选择“添加类”。</span><span class="sxs-lookup"><span data-stu-id="72cf4-111">From the **Project** menu, choose **Add Class**.</span></span>

3. <span data-ttu-id="72cf4-112">在“添加新项”对话框中，单击“自定义控件”。</span><span class="sxs-lookup"><span data-stu-id="72cf4-112">In the **Add New Item** dialog box, click **Custom Control**.</span></span>

   <span data-ttu-id="72cf4-113">一个新的自定义控件将被添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="72cf4-113">A new custom control is added to your project.</span></span>

4. <span data-ttu-id="72cf4-114">按 **F7** 以打开自定义控件的 **代码编辑器** 。</span><span class="sxs-lookup"><span data-stu-id="72cf4-114">Press **F7** to open the **Code Editor** for your custom control.</span></span>

5. <span data-ttu-id="72cf4-115">找到 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法，该方法将为空，除非调用 <xref:System.Windows.Forms.Control.OnPaint%2A> 基类的方法。</span><span class="sxs-lookup"><span data-stu-id="72cf4-115">Locate the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which will be empty except for a call to the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span>

6. <span data-ttu-id="72cf4-116">修改代码以纳入控件所需的任何自定义绘图。</span><span class="sxs-lookup"><span data-stu-id="72cf4-116">Modify the code to incorporate any custom painting you want for your control.</span></span>

   <span data-ttu-id="72cf4-117">有关编写代码来呈现控件的图形的信息，请参阅[自定义控件的绘制和呈现](custom-control-painting-and-rendering.md)。</span><span class="sxs-lookup"><span data-stu-id="72cf4-117">For information about writing code to render graphics for controls, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

7. <span data-ttu-id="72cf4-118">实现控件将纳入的任何自定义方法、属性或事件。</span><span class="sxs-lookup"><span data-stu-id="72cf4-118">Implement any custom methods, properties, or events that your control will incorporate.</span></span>

8. <span data-ttu-id="72cf4-119">保存并测试控件。</span><span class="sxs-lookup"><span data-stu-id="72cf4-119">Save and test your control.</span></span>

## <a name="see-also"></a><span data-ttu-id="72cf4-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72cf4-120">See also</span></span>

- [<span data-ttu-id="72cf4-121">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="72cf4-121">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="72cf4-122">如何：从 UserControl 类继承</span><span class="sxs-lookup"><span data-stu-id="72cf4-122">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="72cf4-123">如何：从现有 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="72cf4-123">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="72cf4-124">如何：创作 Windows 窗体的控件</span><span class="sxs-lookup"><span data-stu-id="72cf4-124">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="72cf4-125">Visual Basic 中继承的事件处理程序疑难解答</span><span class="sxs-lookup"><span data-stu-id="72cf4-125">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers)
- [<span data-ttu-id="72cf4-126">设计时开发 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="72cf4-126">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
