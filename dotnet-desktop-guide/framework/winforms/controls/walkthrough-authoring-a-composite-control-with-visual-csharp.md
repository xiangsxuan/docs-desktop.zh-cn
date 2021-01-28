---
title: 演练：使用 Visual C# 创作复合控件
ms.date: 03/30/2017
dev_langs:
- CSharp
helpviewer_keywords:
- custom controls [C#]
- user controls [Windows Forms], creating with Visual C#
- UserControl class [Windows Forms], walkthroughs
- user controls [C#]
- custom controls [Windows Forms], creating
ms.assetid: f88481a8-c746-4a36-9479-374ce5f2e91f
ms.openlocfilehash: 1b1ad5daab8e62817d94ca6bb942ede293949c88
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957599"
---
# <a name="walkthrough-author-a-composite-control-with-c"></a><span data-ttu-id="e54e0-102">演练：使用 C 创作复合控件\#</span><span class="sxs-lookup"><span data-stu-id="e54e0-102">Walkthrough: Author a Composite Control with C\#</span></span>

<span data-ttu-id="e54e0-103">复合控件提供了一种创建和重用自定义图形界面的方法。</span><span class="sxs-lookup"><span data-stu-id="e54e0-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="e54e0-104">复合控件本质上是具有可视化表示形式的组件。</span><span class="sxs-lookup"><span data-stu-id="e54e0-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="e54e0-105">因此，它可能包含一个或多个 Windows 窗体控件、组件或代码块，它们能够通过验证用户输入、修改显示属性或执行作者所需的其他任务来扩展功能。</span><span class="sxs-lookup"><span data-stu-id="e54e0-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="e54e0-106">可以按照与其他控件相同的方式将复合控件置于 Windows 窗体中。</span><span class="sxs-lookup"><span data-stu-id="e54e0-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="e54e0-107">在本演练的第一部分，将创建一个名为 `ctlClock` 的简单复合控件。</span><span class="sxs-lookup"><span data-stu-id="e54e0-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="e54e0-108">在本演练的第二部分，将通过继承扩展 `ctlClock` 的功能。</span><span class="sxs-lookup"><span data-stu-id="e54e0-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="e54e0-109">创建项目</span><span class="sxs-lookup"><span data-stu-id="e54e0-109">Create the Project</span></span>

<span data-ttu-id="e54e0-110">创建新的项目时应指定其名称，以设置根命名空间、程序集名称和项目名称，并确保默认组件将位于正确的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="e54e0-110">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="e54e0-111">创建 ctlClockLib 控件库和 ctlClock 控件</span><span class="sxs-lookup"><span data-stu-id="e54e0-111">To create the ctlClockLib control library and the ctlClock control</span></span>

1. <span data-ttu-id="e54e0-112">在 Visual Studio 中，创建一个新的 **Windows 窗体控件库** 项目，并将其命名为 **ctlClockLib**。</span><span class="sxs-lookup"><span data-stu-id="e54e0-112">In Visual Studio, create a new **Windows Forms Control Library** project, and name it **ctlClockLib**.</span></span>

     <span data-ttu-id="e54e0-113">默认情况下，项目名称 `ctlClockLib` 也会分配到根命名空间中。</span><span class="sxs-lookup"><span data-stu-id="e54e0-113">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="e54e0-114">根命名空间用于限定程序集中的组件名。</span><span class="sxs-lookup"><span data-stu-id="e54e0-114">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="e54e0-115">例如，如果两个程序集都提供名为 `ctlClock` 的组件，则可以使用 `ctlClockLib.ctlClock.` 指定 `ctlClock` 组件</span><span class="sxs-lookup"><span data-stu-id="e54e0-115">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>

2. <span data-ttu-id="e54e0-116">在 **解决方案资源管理器** 中，右键单击 **UserControl1.cs**，然后单击 " **重命名**"。</span><span class="sxs-lookup"><span data-stu-id="e54e0-116">In **Solution Explorer**, right-click **UserControl1.cs**, and then click **Rename**.</span></span> <span data-ttu-id="e54e0-117">将文件名更改为 `ctlClock.cs`。</span><span class="sxs-lookup"><span data-stu-id="e54e0-117">Change the file name to `ctlClock.cs`.</span></span> <span data-ttu-id="e54e0-118">当系统询问是否重命名对代码元素“UserControl1”的所有引用时，单击“是”按钮。</span><span class="sxs-lookup"><span data-stu-id="e54e0-118">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>

    > [!NOTE]
    > <span data-ttu-id="e54e0-119">默认情况下，复合控件继承自 <xref:System.Windows.Forms.UserControl> 系统提供的类。</span><span class="sxs-lookup"><span data-stu-id="e54e0-119">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="e54e0-120"><xref:System.Windows.Forms.UserControl>类提供所有复合控件所需的功能，并实现标准方法和属性。</span><span class="sxs-lookup"><span data-stu-id="e54e0-120">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>

3. <span data-ttu-id="e54e0-121">在“文件”菜单上，单击“全部保存”保存项目。</span><span class="sxs-lookup"><span data-stu-id="e54e0-121">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="add-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="e54e0-122">将 Windows 控件和组件添加到复合控件</span><span class="sxs-lookup"><span data-stu-id="e54e0-122">Add Windows Controls and Components to the Composite Control</span></span>

<span data-ttu-id="e54e0-123">可视化界面是复合控件的基本部分。</span><span class="sxs-lookup"><span data-stu-id="e54e0-123">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="e54e0-124">这种可视化界面通过向设计器图面添加一个或多个 Windows 控件实现。</span><span class="sxs-lookup"><span data-stu-id="e54e0-124">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="e54e0-125">在下面的演示中，将向复合控件中加入 Windows 控件并编写代码实现功能。</span><span class="sxs-lookup"><span data-stu-id="e54e0-125">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>

### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="e54e0-126">将标签和计时器添加到复合控件</span><span class="sxs-lookup"><span data-stu-id="e54e0-126">To add a Label and a Timer to your composite control</span></span>

1. <span data-ttu-id="e54e0-127">在 **解决方案资源管理器** 中，右键单击 **ctlClock.cs**，然后单击 " **查看设计器**"。</span><span class="sxs-lookup"><span data-stu-id="e54e0-127">In **Solution Explorer**, right-click **ctlClock.cs**, and then click **View Designer**.</span></span>

2. <span data-ttu-id="e54e0-128">在 " **工具箱**" 中，展开 " **公共控件** " 节点，然后双击 " **标签**"。</span><span class="sxs-lookup"><span data-stu-id="e54e0-128">In the **Toolbox**, expand the **Common Controls** node, and then double-click **Label**.</span></span>

     <span data-ttu-id="e54e0-129">名为的 <xref:System.Windows.Forms.Label> 控件 `label1` 将添加到设计器图面上的控件中。</span><span class="sxs-lookup"><span data-stu-id="e54e0-129">A <xref:System.Windows.Forms.Label> control named `label1` is added to your control on the designer surface.</span></span>

3. <span data-ttu-id="e54e0-130">在设计器中，单击 " **label1**"。</span><span class="sxs-lookup"><span data-stu-id="e54e0-130">In the designer, click **label1**.</span></span> <span data-ttu-id="e54e0-131">在“属性”窗口中，设置下列属性。</span><span class="sxs-lookup"><span data-stu-id="e54e0-131">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="e54e0-132">properties</span><span class="sxs-lookup"><span data-stu-id="e54e0-132">Property</span></span>|<span data-ttu-id="e54e0-133">更改为</span><span class="sxs-lookup"><span data-stu-id="e54e0-133">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="e54e0-134">**名称**</span><span class="sxs-lookup"><span data-stu-id="e54e0-134">**Name**</span></span>|`lblDisplay`|
    |<span data-ttu-id="e54e0-135">**Text**</span><span class="sxs-lookup"><span data-stu-id="e54e0-135">**Text**</span></span>|`(blank space)`|
    |<span data-ttu-id="e54e0-136">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="e54e0-136">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="e54e0-137">**字体大小**</span><span class="sxs-lookup"><span data-stu-id="e54e0-137">**Font.Size**</span></span>|`14`|

4. <span data-ttu-id="e54e0-138">在“工具箱”中，展开“组件”节点，然后双击“计时器”。</span><span class="sxs-lookup"><span data-stu-id="e54e0-138">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>

     <span data-ttu-id="e54e0-139">由于 <xref:System.Windows.Forms.Timer> 是一个组件，因此它在运行时不具有可视表示形式。</span><span class="sxs-lookup"><span data-stu-id="e54e0-139">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="e54e0-140">因此，它不会显示在设计器图面上，而是显示在 " **组件设计器** " 中 (设计器图) 面底部的一栏。</span><span class="sxs-lookup"><span data-stu-id="e54e0-140">Therefore, it does not appear with the controls on the designer surface, but rather in the **Component Designer** (a tray at the bottom of the designer surface).</span></span>

5. <span data-ttu-id="e54e0-141">在 " **组件设计器**" 中，单击 " **timer1**"，然后将 <xref:System.Windows.Forms.Timer.Interval%2A> 属性设置为 `1000` ，并将属性设置 <xref:System.Windows.Forms.Timer.Enabled%2A> 为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="e54e0-141">In the **Component Designer**, click **timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>

     <span data-ttu-id="e54e0-142"><xref:System.Windows.Forms.Timer.Interval%2A>属性控制 <xref:System.Windows.Forms.Timer> 组件的计时频率。</span><span class="sxs-lookup"><span data-stu-id="e54e0-142">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the <xref:System.Windows.Forms.Timer> component ticks.</span></span> <span data-ttu-id="e54e0-143">`timer1` 每走过一个刻度，它都会运行一次 `timer1_Tick` 事件中的代码。</span><span class="sxs-lookup"><span data-stu-id="e54e0-143">Each time `timer1` ticks, it runs the code in the `timer1_Tick` event.</span></span> <span data-ttu-id="e54e0-144">间隔表示计时之间的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="e54e0-144">The interval represents the number of milliseconds between ticks.</span></span>

6. <span data-ttu-id="e54e0-145">在 " **组件设计器**" 中，双击 " **timer1** " 以前往的 `timer1_Tick` 事件 `ctlClock` 。</span><span class="sxs-lookup"><span data-stu-id="e54e0-145">In the **Component Designer**, double-click **timer1** to go to the `timer1_Tick` event for `ctlClock`.</span></span>

7. <span data-ttu-id="e54e0-146">将代码修改为类似如下所示的代码示例。</span><span class="sxs-lookup"><span data-stu-id="e54e0-146">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="e54e0-147">确保将访问修饰符从 `private` 更改为 `protected`。</span><span class="sxs-lookup"><span data-stu-id="e54e0-147">Be sure to change the access modifier from `private` to `protected`.</span></span>

    ```csharp
    protected void timer1_Tick(object sender, System.EventArgs e)
    {
        // Causes the label to display the current time.
        lblDisplay.Text = DateTime.Now.ToLongTimeString();
    }
    ```

     <span data-ttu-id="e54e0-148">此代码将使得当前时间显示在 `lblDisplay` 中。</span><span class="sxs-lookup"><span data-stu-id="e54e0-148">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="e54e0-149">因为 `timer1` 的间隔设置为 `1000`，所以该事件每 1000 毫秒发生一次，从而每一秒更新一次当前时间。</span><span class="sxs-lookup"><span data-stu-id="e54e0-149">Because the interval of `timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>

8. <span data-ttu-id="e54e0-150">修改该方法使其可通过 `virtual` 关键字重写。</span><span class="sxs-lookup"><span data-stu-id="e54e0-150">Modify the method to be overridable with the `virtual` keyword.</span></span> <span data-ttu-id="e54e0-151">有关详细信息，请参阅下面的“从用户控件继承”一节。</span><span class="sxs-lookup"><span data-stu-id="e54e0-151">For more information, see the  "Inheriting from a User Control" section below.</span></span>

    ```csharp
    protected virtual void timer1_Tick(object sender, System.EventArgs e)
    ```

9. <span data-ttu-id="e54e0-152">在“文件”菜单上，单击“全部保存”保存项目。</span><span class="sxs-lookup"><span data-stu-id="e54e0-152">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="add-properties-to-the-composite-control"></a><span data-ttu-id="e54e0-153">向复合控件添加属性</span><span class="sxs-lookup"><span data-stu-id="e54e0-153">Add Properties to the Composite Control</span></span>

<span data-ttu-id="e54e0-154">时钟控件现在封装一个 <xref:System.Windows.Forms.Label> 控件和一个 <xref:System.Windows.Forms.Timer> 组件，每个组件都有其自己的固有属性集。</span><span class="sxs-lookup"><span data-stu-id="e54e0-154">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="e54e0-155">尽管控件的后续用户无法访问这些控件的单个属性，但可以通过编写适当的代码块来创建和公开自定义属性。</span><span class="sxs-lookup"><span data-stu-id="e54e0-155">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="e54e0-156">在下面的过程中，将向控件添加属性，这些属性可使用户能够更改背景和文本的颜色。</span><span class="sxs-lookup"><span data-stu-id="e54e0-156">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>

### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="e54e0-157">将属性添加到复合控件</span><span class="sxs-lookup"><span data-stu-id="e54e0-157">To add a property to your composite control</span></span>

1. <span data-ttu-id="e54e0-158">在 **解决方案资源管理器** 中，右键单击 **ctlClock.cs**，然后单击 " **查看代码**"。</span><span class="sxs-lookup"><span data-stu-id="e54e0-158">In **Solution Explorer**, right-click **ctlClock.cs**, and then click **View Code**.</span></span>

     <span data-ttu-id="e54e0-159">控件的 " **代码编辑器** " 随即打开。</span><span class="sxs-lookup"><span data-stu-id="e54e0-159">The **Code Editor** for your control opens.</span></span>

2. <span data-ttu-id="e54e0-160">找到 `public partial class ctlClock` 语句。</span><span class="sxs-lookup"><span data-stu-id="e54e0-160">Locate the `public partial class ctlClock` statement.</span></span> <span data-ttu-id="e54e0-161">在左大括号 (`{)` 下键入下以下代码。</span><span class="sxs-lookup"><span data-stu-id="e54e0-161">Beneath the opening brace (`{)`, type the following code.</span></span>

    ```csharp
    private Color colFColor;
    private Color colBColor;
    ```

     <span data-ttu-id="e54e0-162">这些语句会创建私有变量，用来存储要创建的属性的值。</span><span class="sxs-lookup"><span data-stu-id="e54e0-162">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>

3. <span data-ttu-id="e54e0-163">在步骤2中的变量声明下面输入或粘贴以下代码。</span><span class="sxs-lookup"><span data-stu-id="e54e0-163">Enter or paste the following code beneath the variable declarations from step 2.</span></span>

    ```csharp
    // Declares the name and type of the property.
    public Color ClockBackColor
    {
        // Retrieves the value of the private variable colBColor.
        get
        {
            return colBColor;
        }
        // Stores the selected value in the private variable colBColor, and
        // updates the background color of the label control lblDisplay.
        set
        {
            colBColor = value;
            lblDisplay.BackColor = colBColor;
        }
    }
    // Provides a similar set of instructions for the foreground color.
    public Color ClockForeColor
    {
        get
        {
            return colFColor;
        }
        set
        {
            colFColor = value;
            lblDisplay.ForeColor = colFColor;
        }
    }
    ```

     <span data-ttu-id="e54e0-164">上述代码使得后续用户能够使用 `ClockForeColor` 和 `ClockBackColor` 这两个自定义属性。</span><span class="sxs-lookup"><span data-stu-id="e54e0-164">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control.</span></span> <span data-ttu-id="e54e0-165">`get` 和 `set` 语句提供了该属性值的存储和检索，还提供了实现适合于该属性的功能的代码。</span><span class="sxs-lookup"><span data-stu-id="e54e0-165">The `get` and `set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>

4. <span data-ttu-id="e54e0-166">在“文件”菜单上，单击“全部保存”保存项目。</span><span class="sxs-lookup"><span data-stu-id="e54e0-166">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="test-the-control"></a><span data-ttu-id="e54e0-167">测试控件</span><span class="sxs-lookup"><span data-stu-id="e54e0-167">Test the Control</span></span>

<span data-ttu-id="e54e0-168">控件不是独立应用程序，它们必须托管在容器中。</span><span class="sxs-lookup"><span data-stu-id="e54e0-168">Controls are not stand-alone applications; they must be hosted in a container.</span></span> <span data-ttu-id="e54e0-169">测试控件的运行时行为，并使用“UserControl 测试容器”运用其属性。</span><span class="sxs-lookup"><span data-stu-id="e54e0-169">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="e54e0-170">有关详细信息，请参阅 [如何：测试 UserControl 的 Run-Time 行为](how-to-test-the-run-time-behavior-of-a-usercontrol.md)。</span><span class="sxs-lookup"><span data-stu-id="e54e0-170">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

### <a name="to-test-your-control"></a><span data-ttu-id="e54e0-171">测试控件</span><span class="sxs-lookup"><span data-stu-id="e54e0-171">To test your control</span></span>

1. <span data-ttu-id="e54e0-172">按 **F5** 生成项目并在 " **UserControl 测试容器**" 中运行控件。</span><span class="sxs-lookup"><span data-stu-id="e54e0-172">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="e54e0-173">在测试容器的属性网格中，找到 `ClockBackColor` 属性，然后选择该属性以显示调色板。</span><span class="sxs-lookup"><span data-stu-id="e54e0-173">In the test container's property grid, locate the `ClockBackColor` property, and then select the property to display the color palette.</span></span>

3. <span data-ttu-id="e54e0-174">通过单击选择颜色。</span><span class="sxs-lookup"><span data-stu-id="e54e0-174">Choose a color by clicking it.</span></span>

   <span data-ttu-id="e54e0-175">控件的背景颜色更改为你选择的颜色。</span><span class="sxs-lookup"><span data-stu-id="e54e0-175">The background color of your control changes to the color you selected.</span></span>

4. <span data-ttu-id="e54e0-176">使用类似的事件序列来验证 `ClockForeColor` 属性的功能是否与预期的相符。</span><span class="sxs-lookup"><span data-stu-id="e54e0-176">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>

   <span data-ttu-id="e54e0-177">本节和前面的几节演示了如何将组件和 Windows 控件与代码和打包相结合，以复合控件的形式提供自定义功能。</span><span class="sxs-lookup"><span data-stu-id="e54e0-177">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="e54e0-178">你现已了解如何在复合控件中公开属性，以及如何在完成后对控件进行测试。</span><span class="sxs-lookup"><span data-stu-id="e54e0-178">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="e54e0-179">下一节将介绍如何以 `ctlClock` 为基础构造继承的复合控件。</span><span class="sxs-lookup"><span data-stu-id="e54e0-179">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>

## <a name="inherit-from-a-composite-control"></a><span data-ttu-id="e54e0-180">从复合控件继承</span><span class="sxs-lookup"><span data-stu-id="e54e0-180">Inherit from a Composite Control</span></span>

<span data-ttu-id="e54e0-181">前面的章节中介绍了如何将 Windows 控件、组件和代码组合成可重用的复合控件。</span><span class="sxs-lookup"><span data-stu-id="e54e0-181">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="e54e0-182">现在即可将复合控件用作生成其他控件的基础。</span><span class="sxs-lookup"><span data-stu-id="e54e0-182">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="e54e0-183">从基类派生类的过程称为继承。</span><span class="sxs-lookup"><span data-stu-id="e54e0-183">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="e54e0-184">在本节中，将创建一个称为 `ctlAlarmClock` 的复合控件。</span><span class="sxs-lookup"><span data-stu-id="e54e0-184">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="e54e0-185">此控件将从其父控件 `ctlClock` 派生。</span><span class="sxs-lookup"><span data-stu-id="e54e0-185">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="e54e0-186">将介绍如何通过重写父级方法并添加新的方法和属性来扩展 `ctlClock` 的功能。</span><span class="sxs-lookup"><span data-stu-id="e54e0-186">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>

<span data-ttu-id="e54e0-187">创建继承控件的第一步是从它的父控件派生。</span><span class="sxs-lookup"><span data-stu-id="e54e0-187">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="e54e0-188">该操作创建一个新控件，它具有父控件的所有属性、方法和图形特征，但也可以用作添加新功能或修改过的功能的基础。</span><span class="sxs-lookup"><span data-stu-id="e54e0-188">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>

### <a name="to-create-the-inherited-control"></a><span data-ttu-id="e54e0-189">创建继承的控件</span><span class="sxs-lookup"><span data-stu-id="e54e0-189">To create the inherited control</span></span>

1. <span data-ttu-id="e54e0-190">在 **解决方案资源管理器** 中，右键单击 **ctlClockLib**，指向 " **添加**"，然后单击 " **用户控件**"。</span><span class="sxs-lookup"><span data-stu-id="e54e0-190">In **Solution Explorer**, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>

     <span data-ttu-id="e54e0-191">此时将打开“添加新项”对话框。</span><span class="sxs-lookup"><span data-stu-id="e54e0-191">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="e54e0-192">选择“继承的用户控件”模板。</span><span class="sxs-lookup"><span data-stu-id="e54e0-192">Select the **Inherited User Control** template.</span></span>

3. <span data-ttu-id="e54e0-193">在“名称”框中，键入 `ctlAlarmClock.cs`，然后单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="e54e0-193">In the **Name** box, type `ctlAlarmClock.cs`, and then click **Add**.</span></span>

     <span data-ttu-id="e54e0-194">“继承选择器”对话框将出现。</span><span class="sxs-lookup"><span data-stu-id="e54e0-194">The **Inheritance Picker** dialog box appears.</span></span>

4. <span data-ttu-id="e54e0-195">在“组件名称”下，双击“ctlClock”。</span><span class="sxs-lookup"><span data-stu-id="e54e0-195">Under **Component Name**, double-click **ctlClock**.</span></span>

5. <span data-ttu-id="e54e0-196">在 **解决方案资源管理器** 中，浏览当前项目。</span><span class="sxs-lookup"><span data-stu-id="e54e0-196">In **Solution Explorer**, browse through the current projects.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e54e0-197">当前项目中添加了一个名为“ctlAlarmClock.cs”的文件。</span><span class="sxs-lookup"><span data-stu-id="e54e0-197">A file called **ctlAlarmClock.cs** has been added to the current project.</span></span>

### <a name="add-the-alarm-properties"></a><span data-ttu-id="e54e0-198">添加警报属性</span><span class="sxs-lookup"><span data-stu-id="e54e0-198">Add the Alarm Properties</span></span>

<span data-ttu-id="e54e0-199">将属性添加到继承的控件的方法与将其添加到复合控件的方法相同。</span><span class="sxs-lookup"><span data-stu-id="e54e0-199">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="e54e0-200">现在将使用属性声明语法向控件中添加两个属性：`AlarmTime` 和 `AlarmSet`，前者将存储发出警报的日期和时间值，后者指示是否设置了警报。</span><span class="sxs-lookup"><span data-stu-id="e54e0-200">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>

#### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="e54e0-201">将属性添加到复合控件</span><span class="sxs-lookup"><span data-stu-id="e54e0-201">To add properties to your composite control</span></span>

1. <span data-ttu-id="e54e0-202">在 **解决方案资源管理器** 中，右键单击 **ctlAlarmClock**，然后单击 " **查看代码**"。</span><span class="sxs-lookup"><span data-stu-id="e54e0-202">In **Solution Explorer**, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>

2. <span data-ttu-id="e54e0-203">找到 `public class` 语句。</span><span class="sxs-lookup"><span data-stu-id="e54e0-203">Locate the `public class` statement.</span></span> <span data-ttu-id="e54e0-204">请注意，控件继承自 `ctlClockLib.ctlClock`。</span><span class="sxs-lookup"><span data-stu-id="e54e0-204">Note that your control inherits from `ctlClockLib.ctlClock`.</span></span> <span data-ttu-id="e54e0-205">在左大括号 (`{)` 语句下键入下以下代码。</span><span class="sxs-lookup"><span data-stu-id="e54e0-205">Beneath the opening brace (`{)` statement, type the following code.</span></span>

    ```csharp
    private DateTime dteAlarmTime;
    private bool blnAlarmSet;
    // These properties will be declared as public to allow future
    // developers to access them.
    public DateTime AlarmTime
    {
        get
        {
            return dteAlarmTime;
        }
        set
        {
            dteAlarmTime = value;
        }
    }
    public bool AlarmSet
    {
        get
        {
            return blnAlarmSet;
        }
        set
        {
            blnAlarmSet = value;
        }
    }
    ```

### <a name="add-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="e54e0-206">添加到控件的图形界面</span><span class="sxs-lookup"><span data-stu-id="e54e0-206">Add to the Graphical Interface of the Control</span></span>

<span data-ttu-id="e54e0-207">继承的控件具有可视化界面，该界面与它从中继承的控件的界面完全相同。</span><span class="sxs-lookup"><span data-stu-id="e54e0-207">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="e54e0-208">它与其父控件拥有相同的构成控件，但除非将构成控件的属性特别公开，否则它们将不可用。</span><span class="sxs-lookup"><span data-stu-id="e54e0-208">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="e54e0-209">可以向继承的复合控件的图形界面进行添加，方法与向任意复合控件进行添加相同。</span><span class="sxs-lookup"><span data-stu-id="e54e0-209">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="e54e0-210">若要继续向警报时钟的可视化界面进行添加，请添加一个标签控件，它将在警报响起时闪烁。</span><span class="sxs-lookup"><span data-stu-id="e54e0-210">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>

#### <a name="to-add-the-label-control"></a><span data-ttu-id="e54e0-211">添加标签控件</span><span class="sxs-lookup"><span data-stu-id="e54e0-211">To add the label control</span></span>

1. <span data-ttu-id="e54e0-212">在 **解决方案资源管理器** 中，右键单击 **ctlAlarmClock**，然后单击 " **查看设计器**"。</span><span class="sxs-lookup"><span data-stu-id="e54e0-212">In **Solution Explorer**, right-click **ctlAlarmClock**, and then click **View Designer**.</span></span>

     <span data-ttu-id="e54e0-213">`ctlAlarmClock` 的设计器将在主窗口中打开。</span><span class="sxs-lookup"><span data-stu-id="e54e0-213">The designer for `ctlAlarmClock` opens in the main window.</span></span>

2. <span data-ttu-id="e54e0-214">单击该控件的显示部分，然后查看“属性”窗口。</span><span class="sxs-lookup"><span data-stu-id="e54e0-214">Click the display portion of the control, and view the Properties window.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e54e0-215">当显示所有属性时，属性是浅灰色的。</span><span class="sxs-lookup"><span data-stu-id="e54e0-215">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="e54e0-216">这表示这些属性是 `lblDisplay` 所固有的，不能在“属性”窗口中修改或访问。</span><span class="sxs-lookup"><span data-stu-id="e54e0-216">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="e54e0-217">默认情况下，复合控件中所包含的控件为 `private`，通过任何途径都无法访问其属性。</span><span class="sxs-lookup"><span data-stu-id="e54e0-217">By default, controls contained in a composite control are `private`, and their properties are not accessible by any means.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e54e0-218">如果希望复合控件的后续用户可以访问其内部控件，则可将其声明为 `public` 或 `protected`。</span><span class="sxs-lookup"><span data-stu-id="e54e0-218">If you want subsequent users of your composite control to have access to its internal controls, declare them as `public` or `protected`.</span></span> <span data-ttu-id="e54e0-219">如此即可使用适当的代码设置和修改复合控件内所包含控件的属性。</span><span class="sxs-lookup"><span data-stu-id="e54e0-219">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>

3. <span data-ttu-id="e54e0-220">向 <xref:System.Windows.Forms.Label> 复合控件添加控件。</span><span class="sxs-lookup"><span data-stu-id="e54e0-220">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>

4. <span data-ttu-id="e54e0-221">使用鼠标将控件拖到 <xref:System.Windows.Forms.Label> 显示框的正下方。</span><span class="sxs-lookup"><span data-stu-id="e54e0-221">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="e54e0-222">在“属性”窗口中，设置下列属性。</span><span class="sxs-lookup"><span data-stu-id="e54e0-222">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="e54e0-223">Property</span><span class="sxs-lookup"><span data-stu-id="e54e0-223">Property</span></span>|<span data-ttu-id="e54e0-224">设置</span><span class="sxs-lookup"><span data-stu-id="e54e0-224">Setting</span></span>|
    |--------------|-------------|
    |<span data-ttu-id="e54e0-225">**名称**</span><span class="sxs-lookup"><span data-stu-id="e54e0-225">**Name**</span></span>|`lblAlarm`|
    |<span data-ttu-id="e54e0-226">**Text**</span><span class="sxs-lookup"><span data-stu-id="e54e0-226">**Text**</span></span>|<span data-ttu-id="e54e0-227">**警报!**</span><span class="sxs-lookup"><span data-stu-id="e54e0-227">**Alarm!**</span></span>|
    |<span data-ttu-id="e54e0-228">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="e54e0-228">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="e54e0-229">**Visible**</span><span class="sxs-lookup"><span data-stu-id="e54e0-229">**Visible**</span></span>|`false`|

### <a name="add-the-alarm-functionality"></a><span data-ttu-id="e54e0-230">添加警报功能</span><span class="sxs-lookup"><span data-stu-id="e54e0-230">Add the Alarm Functionality</span></span>

<span data-ttu-id="e54e0-231">在前面的章节中，已经添加了一些属性和一个控件，它们将启用复合控件中的警报功能。</span><span class="sxs-lookup"><span data-stu-id="e54e0-231">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="e54e0-232">在本过程中，将添加代码以比较当前时间和警报时间，如果两者相同，则警报闪烁。</span><span class="sxs-lookup"><span data-stu-id="e54e0-232">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to flash an alarm.</span></span> <span data-ttu-id="e54e0-233">通过重写 `ctlClock` 的 `timer1_Tick` 方法并向其中添加其他代码，可扩展 `ctlAlarmClock` 的功能，同时会保留 `ctlClock` 的所有固有功能。</span><span class="sxs-lookup"><span data-stu-id="e54e0-233">By overriding the `timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>

#### <a name="to-override-the-timer1_tick-method-of-ctlclock"></a><span data-ttu-id="e54e0-234">重写 ctlClock 的 timer1_Tick 方法</span><span class="sxs-lookup"><span data-stu-id="e54e0-234">To override the timer1_Tick method of ctlClock</span></span>

1. <span data-ttu-id="e54e0-235">在“代码编辑器”中，找到 `private bool blnAlarmSet;` 语句。</span><span class="sxs-lookup"><span data-stu-id="e54e0-235">In the **Code Editor**, locate the `private bool blnAlarmSet;` statement.</span></span> <span data-ttu-id="e54e0-236">在其紧下方添加下列语句。</span><span class="sxs-lookup"><span data-stu-id="e54e0-236">Immediately beneath it, add the following statement.</span></span>

    ```csharp
    private bool blnColorTicker;
    ```

2. <span data-ttu-id="e54e0-237">在“代码编辑器”中，在类的结尾找到右大括号 (`})`。</span><span class="sxs-lookup"><span data-stu-id="e54e0-237">In the **Code Editor**, locate the closing brace (`})` at the end of the class.</span></span> <span data-ttu-id="e54e0-238">在大括号的前面添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="e54e0-238">Just before the brace, add the following code.</span></span>

    ```csharp
    protected override void timer1_Tick(object sender, System.EventArgs e)
    {
        // Calls the Timer1_Tick method of ctlClock.
        base.timer1_Tick(sender, e);
        // Checks to see if the alarm is set.
        if (AlarmSet == false)
            return;
        else
            // If the date, hour, and minute of the alarm time are the same as
            // the current time, flash an alarm.
        {
            if (AlarmTime.Date == DateTime.Now.Date && AlarmTime.Hour ==
                DateTime.Now.Hour && AlarmTime.Minute == DateTime.Now.Minute)
            {
                // Sets lblAlarmVisible to true, and changes the background color based on
                // the value of blnColorTicker. The background color of the label
                // will flash once per tick of the clock.
                lblAlarm.Visible = true;
                if (blnColorTicker == false)
                {
                    lblAlarm.BackColor = Color.Red;
                    blnColorTicker = true;
                }
                else
                {
                    lblAlarm.BackColor = Color.Blue;
                    blnColorTicker = false;
                }
            }
            else
            {
                // Once the alarm has sounded for a minute, the label is made
                // invisible again.
                lblAlarm.Visible = false;
            }
        }
    }
    ```

     <span data-ttu-id="e54e0-239">添加此代码将完成多项任务。</span><span class="sxs-lookup"><span data-stu-id="e54e0-239">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="e54e0-240">`override` 语句指示控件使用此方法替换从基控件继承的方法。</span><span class="sxs-lookup"><span data-stu-id="e54e0-240">The `override` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="e54e0-241">调用此方法时，它通过调用 `base.timer1_Tick` 语句来调用它重写的方法，从而确保在该控件中重现原始控件包含的所有功能。</span><span class="sxs-lookup"><span data-stu-id="e54e0-241">When this method is called, it calls the method it overrides by invoking the `base.timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="e54e0-242">然后，运行附加代码以合并警报功能。</span><span class="sxs-lookup"><span data-stu-id="e54e0-242">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="e54e0-243">警报触发时，将会出现闪烁的标签控件。</span><span class="sxs-lookup"><span data-stu-id="e54e0-243">A flashing label control will appear when the alarm occurs.</span></span>

     <span data-ttu-id="e54e0-244">警报时钟控件已基本完成。</span><span class="sxs-lookup"><span data-stu-id="e54e0-244">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="e54e0-245">剩下的唯一事情是实现关闭它的方法。</span><span class="sxs-lookup"><span data-stu-id="e54e0-245">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="e54e0-246">为此，将向 `lblAlarm_Click` 方法添加代码。</span><span class="sxs-lookup"><span data-stu-id="e54e0-246">To do this, you will add code to the `lblAlarm_Click` method.</span></span>

#### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="e54e0-247">实现关闭方法</span><span class="sxs-lookup"><span data-stu-id="e54e0-247">To implement the shutoff method</span></span>

1. <span data-ttu-id="e54e0-248">在 **解决方案资源管理器** 中，右键单击 **ctlAlarmClock.cs**，然后单击 " **查看设计器**"。</span><span class="sxs-lookup"><span data-stu-id="e54e0-248">In **Solution Explorer**, right-click **ctlAlarmClock.cs**, and then click **View Designer**.</span></span>

     <span data-ttu-id="e54e0-249">设计器随即打开。</span><span class="sxs-lookup"><span data-stu-id="e54e0-249">The designer opens.</span></span>

2. <span data-ttu-id="e54e0-250">将按钮添加到控件。</span><span class="sxs-lookup"><span data-stu-id="e54e0-250">Add a button to the control.</span></span> <span data-ttu-id="e54e0-251">按如下方式设置该按钮的属性。</span><span class="sxs-lookup"><span data-stu-id="e54e0-251">Set the properties of the button as follows.</span></span>

    |<span data-ttu-id="e54e0-252">properties</span><span class="sxs-lookup"><span data-stu-id="e54e0-252">Property</span></span>|<span data-ttu-id="e54e0-253">值</span><span class="sxs-lookup"><span data-stu-id="e54e0-253">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="e54e0-254">**名称**</span><span class="sxs-lookup"><span data-stu-id="e54e0-254">**Name**</span></span>|`btnAlarmOff`|
    |<span data-ttu-id="e54e0-255">**Text**</span><span class="sxs-lookup"><span data-stu-id="e54e0-255">**Text**</span></span>|<span data-ttu-id="e54e0-256">**禁用警报**</span><span class="sxs-lookup"><span data-stu-id="e54e0-256">**Disable Alarm**</span></span>|

3. <span data-ttu-id="e54e0-257">在设计器中，双击“btnAlarmOff”控件。</span><span class="sxs-lookup"><span data-stu-id="e54e0-257">In the designer, double-click **btnAlarmOff**.</span></span>

     <span data-ttu-id="e54e0-258">“代码编辑器”随即打开并显示 `private void btnAlarmOff_Click` 行。</span><span class="sxs-lookup"><span data-stu-id="e54e0-258">The **Code Editor** opens to the `private void btnAlarmOff_Click` line.</span></span>

4. <span data-ttu-id="e54e0-259">将此方法修改为类似如下所示的代码。</span><span class="sxs-lookup"><span data-stu-id="e54e0-259">Modify this method so that it resembles the following code.</span></span>

    ```csharp
    private void btnAlarmOff_Click(object sender, System.EventArgs e)
    {
        // Turns off the alarm.
        AlarmSet = false;
        // Hides the flashing label.
        lblAlarm.Visible = false;
    }
    ```

5. <span data-ttu-id="e54e0-260">在“文件”菜单上，单击“全部保存”保存项目。</span><span class="sxs-lookup"><span data-stu-id="e54e0-260">On the **File** menu, click **Save All** to save the project.</span></span>

### <a name="use-the-inherited-control-on-a-form"></a><span data-ttu-id="e54e0-261">在窗体上使用继承的控件</span><span class="sxs-lookup"><span data-stu-id="e54e0-261">Use the Inherited Control on a Form</span></span>

<span data-ttu-id="e54e0-262">可以采用与测试基类控件相同的方式来测试继承的控件， `ctlClock` ：按 **F5** 生成项目并在 " **UserControl 测试容器**" 中运行控件。</span><span class="sxs-lookup"><span data-stu-id="e54e0-262">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="e54e0-263">有关详细信息，请参阅 [如何：测试 UserControl 的 Run-Time 行为](how-to-test-the-run-time-behavior-of-a-usercontrol.md)。</span><span class="sxs-lookup"><span data-stu-id="e54e0-263">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

<span data-ttu-id="e54e0-264">若要使用控件，还需要将其放入窗体中。</span><span class="sxs-lookup"><span data-stu-id="e54e0-264">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="e54e0-265">与标准复合控件一样，继承的复合控件不能独立存在，而必须承载在窗体或其他容器中。</span><span class="sxs-lookup"><span data-stu-id="e54e0-265">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="e54e0-266">由于 `ctlAlarmClock` 的功能更加深入，因此需要附加代码以对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="e54e0-266">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="e54e0-267">在本过程中，将编写一个简单的程序来测试 `ctlAlarmClock` 的功能。</span><span class="sxs-lookup"><span data-stu-id="e54e0-267">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="e54e0-268">将编写代码来设置和显示 `ctlAlarmClock` 的 `AlarmTime` 属性，并测试其固有功能。</span><span class="sxs-lookup"><span data-stu-id="e54e0-268">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>

#### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="e54e0-269">生成测试窗体并将控件添加到该窗体</span><span class="sxs-lookup"><span data-stu-id="e54e0-269">To build and add your control to a test form</span></span>

1. <span data-ttu-id="e54e0-270">在 **解决方案资源管理器** 中，右键单击 **ctlClockLib**，然后单击 " **生成**"。</span><span class="sxs-lookup"><span data-stu-id="e54e0-270">In **Solution Explorer**, right-click **ctlClockLib**, and then click **Build**.</span></span>

2. <span data-ttu-id="e54e0-271">将新的 **Windows 窗体应用程序** 项目添加到解决方案，并将其命名为 **Test**。</span><span class="sxs-lookup"><span data-stu-id="e54e0-271">Add a new **Windows Forms Application** project to the solution, and name it **Test**.</span></span>

3. <span data-ttu-id="e54e0-272">在 **解决方案资源管理器** 中，右键单击测试项目的 " **引用** " 节点。</span><span class="sxs-lookup"><span data-stu-id="e54e0-272">In **Solution Explorer**, right-click the **References** node for your test project.</span></span> <span data-ttu-id="e54e0-273">单击“添加引用”，显示“添加引用”对话框。</span><span class="sxs-lookup"><span data-stu-id="e54e0-273">Click **Add Reference** to display the **Add Reference** dialog box.</span></span> <span data-ttu-id="e54e0-274">单击标记为“项目”的选项卡。</span><span class="sxs-lookup"><span data-stu-id="e54e0-274">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="e54e0-275">“项目名称”下将列出 `ctlClockLib` 项目。</span><span class="sxs-lookup"><span data-stu-id="e54e0-275">Your `ctlClockLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="e54e0-276">双击该项目将引用添加到测试项目。</span><span class="sxs-lookup"><span data-stu-id="e54e0-276">Double-click the project to add the reference to the test project.</span></span>

4. <span data-ttu-id="e54e0-277">在 **解决方案资源管理器** 中，右键单击 " **测试**"，然后单击 " **生成**"。</span><span class="sxs-lookup"><span data-stu-id="e54e0-277">In **Solution Explorer**, right-click **Test**, and then click **Build**.</span></span>

5. <span data-ttu-id="e54e0-278">在“工具箱”中，展开“ctlClockLib 组件”节点。</span><span class="sxs-lookup"><span data-stu-id="e54e0-278">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>

6. <span data-ttu-id="e54e0-279">双击“ctlAlarmClock”向窗体添加 `ctlAlarmClock` 的副本。</span><span class="sxs-lookup"><span data-stu-id="e54e0-279">Double-click **ctlAlarmClock** to add a copy of `ctlAlarmClock` to your form.</span></span>

7. <span data-ttu-id="e54e0-280">在 " **工具箱**" 中，找到并双击 " **DateTimePicker** " 将 <xref:System.Windows.Forms.DateTimePicker> 控件添加到窗体，然后双击 " <xref:System.Windows.Forms.Label> **标签**" 添加控件。</span><span class="sxs-lookup"><span data-stu-id="e54e0-280">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>

8. <span data-ttu-id="e54e0-281">使用鼠标将这些控件放置在窗体上合适的位置。</span><span class="sxs-lookup"><span data-stu-id="e54e0-281">Use the mouse to position the controls in a convenient place on the form.</span></span>

9. <span data-ttu-id="e54e0-282">按下述方法设置这些控件的属性。</span><span class="sxs-lookup"><span data-stu-id="e54e0-282">Set the properties of these controls in the following manner.</span></span>

    |<span data-ttu-id="e54e0-283">控制</span><span class="sxs-lookup"><span data-stu-id="e54e0-283">Control</span></span>|<span data-ttu-id="e54e0-284">属性</span><span class="sxs-lookup"><span data-stu-id="e54e0-284">Property</span></span>|<span data-ttu-id="e54e0-285">值</span><span class="sxs-lookup"><span data-stu-id="e54e0-285">Value</span></span>|
    |-------------|--------------|-----------|
    |`label1`|<span data-ttu-id="e54e0-286">**Text**</span><span class="sxs-lookup"><span data-stu-id="e54e0-286">**Text**</span></span>|`(blank space)`|
    ||<span data-ttu-id="e54e0-287">**名称**</span><span class="sxs-lookup"><span data-stu-id="e54e0-287">**Name**</span></span>|`lblTest`|
    |`dateTimePicker1`|<span data-ttu-id="e54e0-288">**名称**</span><span class="sxs-lookup"><span data-stu-id="e54e0-288">**Name**</span></span>|`dtpTest`|
    ||<span data-ttu-id="e54e0-289">**格式**</span><span class="sxs-lookup"><span data-stu-id="e54e0-289">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|

10. <span data-ttu-id="e54e0-290">在设计器中，双击“dtpTest”。</span><span class="sxs-lookup"><span data-stu-id="e54e0-290">In the designer, double-click **dtpTest**.</span></span>

     <span data-ttu-id="e54e0-291">“代码编辑器”随即打开并显示 `private void dtpTest_ValueChanged`。</span><span class="sxs-lookup"><span data-stu-id="e54e0-291">The **Code Editor** opens to `private void dtpTest_ValueChanged`.</span></span>

11. <span data-ttu-id="e54e0-292">像如下所示修改代码。</span><span class="sxs-lookup"><span data-stu-id="e54e0-292">Modify the code so that it resembles the following.</span></span>

    ```csharp
    private void dtpTest_ValueChanged(object sender, System.EventArgs e)
    {
        ctlAlarmClock1.AlarmTime = dtpTest.Value;
        ctlAlarmClock1.AlarmSet = true;
        lblTest.Text = "Alarm Time is " +
            ctlAlarmClock1.AlarmTime.ToShortTimeString();
    }
    ```

12. <span data-ttu-id="e54e0-293">在 **解决方案资源管理器** 中，右键单击 " **测试**"，然后单击 " **设为启动项目**"。</span><span class="sxs-lookup"><span data-stu-id="e54e0-293">In **Solution Explorer**, right-click **Test**, and then click **Set as StartUp Project**.</span></span>

13. <span data-ttu-id="e54e0-294">在“调试”菜单上，单击“启动调试”。</span><span class="sxs-lookup"><span data-stu-id="e54e0-294">On the **Debug** menu, click **Start Debugging**.</span></span>

     <span data-ttu-id="e54e0-295">测试程序随即启动。</span><span class="sxs-lookup"><span data-stu-id="e54e0-295">The test program starts.</span></span> <span data-ttu-id="e54e0-296">请注意，控件中的当前时间已更新 `ctlAlarmClock` ，并且开始时间显示在 <xref:System.Windows.Forms.DateTimePicker> 控件中。</span><span class="sxs-lookup"><span data-stu-id="e54e0-296">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>

14. <span data-ttu-id="e54e0-297">单击 " <xref:System.Windows.Forms.DateTimePicker> 小时" 的显示位置。</span><span class="sxs-lookup"><span data-stu-id="e54e0-297">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>

15. <span data-ttu-id="e54e0-298">使用键盘设置一个分钟值，使它比 `ctlAlarmClock` 显示的当前时间快一分钟。</span><span class="sxs-lookup"><span data-stu-id="e54e0-298">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>

     <span data-ttu-id="e54e0-299">警报设置的时间在 `lblTest` 中显示。</span><span class="sxs-lookup"><span data-stu-id="e54e0-299">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="e54e0-300">等候显示的时间到达警报设置时间。</span><span class="sxs-lookup"><span data-stu-id="e54e0-300">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="e54e0-301">显示时间到达警报设置的时间时，`lblAlarm` 会闪烁。</span><span class="sxs-lookup"><span data-stu-id="e54e0-301">When the displayed time reaches the time to which the alarm is set, the `lblAlarm` will flash.</span></span>

16. <span data-ttu-id="e54e0-302">单击 `btnAlarmOff` 关闭警报。</span><span class="sxs-lookup"><span data-stu-id="e54e0-302">Turn off the alarm by clicking `btnAlarmOff`.</span></span> <span data-ttu-id="e54e0-303">现在可以重置警报。</span><span class="sxs-lookup"><span data-stu-id="e54e0-303">You may now reset the alarm.</span></span>

<span data-ttu-id="e54e0-304">本文介绍了许多关键概念。</span><span class="sxs-lookup"><span data-stu-id="e54e0-304">This article has covered a number of key concepts.</span></span> <span data-ttu-id="e54e0-305">现已应了解如何通过将控件和组件组合到复合控件容器中来创建复合控件。</span><span class="sxs-lookup"><span data-stu-id="e54e0-305">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="e54e0-306">还应了解图和将属性添加到控件，以及如何编写代码以实现自定义功能。</span><span class="sxs-lookup"><span data-stu-id="e54e0-306">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="e54e0-307">在最后一节中，应了解到如何通过继承来扩展给定复合控件的功能，以及如何通过重写承载方法来改变这些方法的功能。</span><span class="sxs-lookup"><span data-stu-id="e54e0-307">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>

## <a name="see-also"></a><span data-ttu-id="e54e0-308">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e54e0-308">See also</span></span>

- [<span data-ttu-id="e54e0-309">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="e54e0-309">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="e54e0-310">如何：在“选择工具箱项”对话框中显示控件</span><span class="sxs-lookup"><span data-stu-id="e54e0-310">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="e54e0-311">演练：使用 Visual C# 从 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="e54e0-311">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
