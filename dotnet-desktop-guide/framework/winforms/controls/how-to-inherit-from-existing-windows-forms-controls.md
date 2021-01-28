---
title: 从现有控件继承
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
ms.openlocfilehash: 7d9766c1bb1812cc5978221ccec42f5eb2c8c4ff
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957716"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="5b035-102">如何：从现有 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="5b035-102">How to: Inherit from Existing Windows Forms Controls</span></span>

<span data-ttu-id="5b035-103">如果想要扩展现有控件的功能，可以通过继承创建一个派生自现有控件的控件。</span><span class="sxs-lookup"><span data-stu-id="5b035-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="5b035-104">从现有控件继承时，将继承该控件的的所有功能和可视属性。</span><span class="sxs-lookup"><span data-stu-id="5b035-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="5b035-105">例如，如果您正在创建一个从继承的控件 <xref:System.Windows.Forms.Button> ，则新控件的外观和行为与标准控件完全相同 <xref:System.Windows.Forms.Button> 。</span><span class="sxs-lookup"><span data-stu-id="5b035-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="5b035-106">然后可以通过实现自定义方法和属性来扩展或修改新控件的功能。</span><span class="sxs-lookup"><span data-stu-id="5b035-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="5b035-107">在某些控件中，还可以通过重写继承控件的方法来更改该控件的可视外观 <xref:System.Windows.Forms.Control.OnPaint%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5b035-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

## <a name="to-create-an-inherited-control"></a><span data-ttu-id="5b035-108">创建继承的控件</span><span class="sxs-lookup"><span data-stu-id="5b035-108">To create an inherited control</span></span>

1. <span data-ttu-id="5b035-109">在 Visual Studio 中，创建一个新的 **Windows 窗体应用程序** 项目。</span><span class="sxs-lookup"><span data-stu-id="5b035-109">In Visual Studio, create a new **Windows Forms Application** project.</span></span>

1. <span data-ttu-id="5b035-110">从“项目”菜单中选择“添加新项”。</span><span class="sxs-lookup"><span data-stu-id="5b035-110">From the **Project** menu, choose **Add New Item**.</span></span>

    <span data-ttu-id="5b035-111">“添加新项”  对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="5b035-111">The **Add New Item** dialog box appears.</span></span>

1. <span data-ttu-id="5b035-112">在“添加新项”对话框中，双击“自定义控件”。</span><span class="sxs-lookup"><span data-stu-id="5b035-112">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>

    <span data-ttu-id="5b035-113">一个新的自定义控件将被添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="5b035-113">A new custom control is added to your project.</span></span>

1. <span data-ttu-id="5b035-114">如果使用的是：</span><span class="sxs-lookup"><span data-stu-id="5b035-114">If you're using:</span></span>

    - <span data-ttu-id="5b035-115">Visual Basic 上，单击 **解决方案资源管理器** 顶部的 " **显示所有文件**"。</span><span class="sxs-lookup"><span data-stu-id="5b035-115">Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="5b035-116">展开 CustomControl1.vb，然后在“代码编辑器”中打开 CustomControl1.Designer.vb。</span><span class="sxs-lookup"><span data-stu-id="5b035-116">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>
    - <span data-ttu-id="5b035-117">C # 中，在代码编辑器中打开 CustomControl1.cs。</span><span class="sxs-lookup"><span data-stu-id="5b035-117">C#, open CustomControl1.cs in the Code Editor.</span></span>

1. <span data-ttu-id="5b035-118">找到继承自的类声明 <xref:System.Windows.Forms.Control> 。</span><span class="sxs-lookup"><span data-stu-id="5b035-118">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>

1. <span data-ttu-id="5b035-119">将基类更改为要从中继承的控件。</span><span class="sxs-lookup"><span data-stu-id="5b035-119">Change the base class to the control that you want to inherit from.</span></span>

     <span data-ttu-id="5b035-120">例如，如果要从继承 <xref:System.Windows.Forms.Button> ，请将类声明更改为以下内容：</span><span class="sxs-lookup"><span data-stu-id="5b035-120">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. <span data-ttu-id="5b035-121">如果使用的是 Visual Basic，则保存并关闭 CustomControl1.Designer.vb。</span><span class="sxs-lookup"><span data-stu-id="5b035-121">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="5b035-122">在“代码编辑器”中打开 CustomControl1.vb。</span><span class="sxs-lookup"><span data-stu-id="5b035-122">Open CustomControl1.vb in the Code Editor.</span></span>

1. <span data-ttu-id="5b035-123">实现控件将纳入的任何自定义方法或属性。</span><span class="sxs-lookup"><span data-stu-id="5b035-123">Implement any custom methods or properties that your control will incorporate.</span></span>

1. <span data-ttu-id="5b035-124">如果要修改控件的图形外观，请重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="5b035-124">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5b035-125">重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 将不允许修改所有控件的外观。</span><span class="sxs-lookup"><span data-stu-id="5b035-125">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="5b035-126">这些控件具有 Windows (完成的所有绘制，例如 <xref:System.Windows.Forms.TextBox>) 从不调用其 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法，因此永远不会使用自定义代码。</span><span class="sxs-lookup"><span data-stu-id="5b035-126">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="5b035-127">请参阅要修改的特定控件的帮助文档，查看该 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法是否可用。</span><span class="sxs-lookup"><span data-stu-id="5b035-127">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="5b035-128">有关所有 Windows 窗体控件的列表，请参阅[在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="5b035-128">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="5b035-129">如果某个控件未 <xref:System.Windows.Forms.Control.OnPaint%2A> 列出为成员方法，则不能通过重写此方法来更改其外观。</span><span class="sxs-lookup"><span data-stu-id="5b035-129">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="5b035-130">有关自定义绘制的详细信息，请参阅[自定义控件的绘制和呈现](custom-control-painting-and-rendering.md)。</span><span class="sxs-lookup"><span data-stu-id="5b035-130">For more information about custom painting, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

    ```vb
    Protected Overrides Sub OnPaint(ByVal e As _
       System.Windows.Forms.PaintEventArgs)
       MyBase.OnPaint(e)
       ' Insert code to do custom painting.
       ' If you want to completely change the appearance of your control,
       ' do not call MyBase.OnPaint(e).
    End Sub
    ```

    ```csharp
    protected override void OnPaint(PaintEventArgs pe)
    {
       base.OnPaint(pe);
       // Insert code to do custom painting.
       // If you want to completely change the appearance of your control,
       // do not call base.OnPaint(pe).
    }
    ```

1. <span data-ttu-id="5b035-131">保存并测试控件。</span><span class="sxs-lookup"><span data-stu-id="5b035-131">Save and test your control.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b035-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b035-132">See also</span></span>

- [<span data-ttu-id="5b035-133">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="5b035-133">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="5b035-134">如何：从 Control 类继承</span><span class="sxs-lookup"><span data-stu-id="5b035-134">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="5b035-135">如何：从 UserControl 类继承</span><span class="sxs-lookup"><span data-stu-id="5b035-135">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="5b035-136">如何：创作 Windows 窗体的控件</span><span class="sxs-lookup"><span data-stu-id="5b035-136">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="5b035-137">Visual Basic 中继承的事件处理程序疑难解答</span><span class="sxs-lookup"><span data-stu-id="5b035-137">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers)
- [<span data-ttu-id="5b035-138">演练：从 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="5b035-138">Walkthrough: Inheriting from a Windows Forms Control</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
