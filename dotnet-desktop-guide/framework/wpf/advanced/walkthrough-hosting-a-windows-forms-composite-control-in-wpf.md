---
title: 在 WPF 中承载 Windows 窗体复合控件
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: 0df41af90957a041554f63bd66e5c86757b11dee
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665183"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a><span data-ttu-id="d5860-102">演练：在 WPF 中托管 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="d5860-102">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>

[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="d5860-103">提供了用于创建应用程序的丰富环境。</span><span class="sxs-lookup"><span data-stu-id="d5860-103">provides a rich environment for creating applications.</span></span> <span data-ttu-id="d5860-104">但是，当你对 Windows 窗体代码有大量投资时，在应用程序中重复使用至少一些代码， [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 而不是从头重新编写它会更有效。</span><span class="sxs-lookup"><span data-stu-id="d5860-104">However, when you have a substantial investment in Windows Forms code, it can be more effective to reuse at least some of that code in your [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] application rather than to rewrite it from scratch.</span></span> <span data-ttu-id="d5860-105">最常见的情况是现有 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="d5860-105">The most common scenario is when you have existing Windows Forms controls.</span></span> <span data-ttu-id="d5860-106">在某些情况下，你甚至可能无法使用这些控件的源代码。</span><span class="sxs-lookup"><span data-stu-id="d5860-106">In some cases, you might not even have access to the source code for these controls.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="d5860-107">提供在应用程序中承载此类控件的简单过程 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="d5860-107">provides a straightforward procedure for hosting such controls in a [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="d5860-108">例如，你可以将 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 用于大多数编程，同时承载专用 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="d5860-108">For example, you can use [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] for most of your programming while hosting your specialized <xref:System.Windows.Forms.DataGridView> controls.</span></span>  
  
 <span data-ttu-id="d5860-109">本演练将指导你完成承载 Windows 窗体复合控件以在应用程序中执行数据输入的应用程序 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="d5860-109">This walkthrough steps you through an application that hosts a Windows Forms composite control to perform data entry in a [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="d5860-110">复合控件打包在一个 DLL 中。</span><span class="sxs-lookup"><span data-stu-id="d5860-110">The composite control is packaged in a DLL.</span></span> <span data-ttu-id="d5860-111">此常规步骤可扩展到更复杂的应用程序和控件。</span><span class="sxs-lookup"><span data-stu-id="d5860-111">This general procedure can be extended to more complex applications and controls.</span></span> <span data-ttu-id="d5860-112">本演练的设计与演练的外观和功能几乎完全相同 [：在 Windows 窗体中承载 WPF 复合控件](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="d5860-112">This walkthrough is designed to be nearly identical in appearance and functionality to [Walkthrough: Hosting a WPF Composite Control in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).</span></span> <span data-ttu-id="d5860-113">主要区别在于承载方案是相反的。</span><span class="sxs-lookup"><span data-stu-id="d5860-113">The primary difference is that the hosting scenario is reversed.</span></span>  
  
 <span data-ttu-id="d5860-114">本演练分为两个部分。</span><span class="sxs-lookup"><span data-stu-id="d5860-114">The walkthrough is divided into two sections.</span></span> <span data-ttu-id="d5860-115">第一部分简要介绍 Windows 窗体复合控件的实现。</span><span class="sxs-lookup"><span data-stu-id="d5860-115">The first section briefly describes the implementation of the Windows Forms composite control.</span></span> <span data-ttu-id="d5860-116">第二部分详细讨论如何在应用程序中承载复合控件 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 、从控件接收事件以及访问控件的某些属性。</span><span class="sxs-lookup"><span data-stu-id="d5860-116">The second section discusses in detail how to host the composite control in a [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] application, receive events from the control, and access some of the control's properties.</span></span>  
  
 <span data-ttu-id="d5860-117">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="d5860-117">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="d5860-118">实现 Windows 窗体复合控件。</span><span class="sxs-lookup"><span data-stu-id="d5860-118">Implementing the Windows Forms composite control.</span></span>  
  
- <span data-ttu-id="d5860-119">实现 WPF 主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="d5860-119">Implementing the WPF host application.</span></span>  
  
 <span data-ttu-id="d5860-120">有关本演练中阐释的任务的完整代码列表，请参阅 [在 WPF 中承载 Windows 窗体复合控件示例](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF)。</span><span class="sxs-lookup"><span data-stu-id="d5860-120">For a complete code listing of the tasks illustrated in this walkthrough, see [Hosting a Windows Forms Composite Control in WPF Sample](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d5860-121">必备条件</span><span class="sxs-lookup"><span data-stu-id="d5860-121">Prerequisites</span></span>  

<span data-ttu-id="d5860-122">若要完成本演练，必须具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="d5860-122">You need Visual Studio to complete this walkthrough.</span></span>
  
## <a name="implementing-the-windows-forms-composite-control"></a><span data-ttu-id="d5860-123">实现 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="d5860-123">Implementing the Windows Forms Composite Control</span></span>  

 <span data-ttu-id="d5860-124">本示例中使用的 Windows 窗体复合控件是一个简单的数据输入窗体。</span><span class="sxs-lookup"><span data-stu-id="d5860-124">The Windows Forms composite control used in this example is a simple data-entry form.</span></span> <span data-ttu-id="d5860-125">此窗体需要用户名和地址，然后使用自定义事件将该信息返回到主机。</span><span class="sxs-lookup"><span data-stu-id="d5860-125">This form takes the user's name and address and then uses a custom event to return that information to the host.</span></span> <span data-ttu-id="d5860-126">下图显示呈现的控件。</span><span class="sxs-lookup"><span data-stu-id="d5860-126">The following illustration shows the rendered control.</span></span>  

 <span data-ttu-id="d5860-127">下图显示了一个 Windows 窗体复合控件：</span><span class="sxs-lookup"><span data-stu-id="d5860-127">The following image shows a Windows Forms composite control:</span></span>  

 ![显示简单 Windows 窗体控件的屏幕截图。](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-forms-control.gif)  
  
### <a name="creating-the-project"></a><span data-ttu-id="d5860-129">创建项目</span><span class="sxs-lookup"><span data-stu-id="d5860-129">Creating the Project</span></span>  

 <span data-ttu-id="d5860-130">启动项目：</span><span class="sxs-lookup"><span data-stu-id="d5860-130">To start the project:</span></span>  
  
1. <span data-ttu-id="d5860-131">启动 Visual Studio，然后打开 " **新建项目** " 对话框。</span><span class="sxs-lookup"><span data-stu-id="d5860-131">Launch Visual Studio, and open the **New Project** dialog box.</span></span>  
  
2. <span data-ttu-id="d5860-132">在 "窗口" 类别中，选择 " **Windows 窗体控件库** " 模板。</span><span class="sxs-lookup"><span data-stu-id="d5860-132">In the Window category, select the **Windows Forms Control Library** template.</span></span>  
  
3. <span data-ttu-id="d5860-133">将新项目命名为 `MyControls`。</span><span class="sxs-lookup"><span data-stu-id="d5860-133">Name the new project `MyControls`.</span></span>  
  
4. <span data-ttu-id="d5860-134">对于 "位置"，指定一个便于命名的顶层文件夹，例如 `WpfHostingWindowsFormsControl` 。</span><span class="sxs-lookup"><span data-stu-id="d5860-134">For the location, specify a conveniently named top-level folder, such as `WpfHostingWindowsFormsControl`.</span></span> <span data-ttu-id="d5860-135">随后，将主机应用程序放在此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d5860-135">Later, you will put the host application in this folder.</span></span>  
  
5. <span data-ttu-id="d5860-136">单击“确定”以创建该项目  。</span><span class="sxs-lookup"><span data-stu-id="d5860-136">Click **OK** to create the project.</span></span> <span data-ttu-id="d5860-137">默认项目包含一个名为的控件 `UserControl1` 。</span><span class="sxs-lookup"><span data-stu-id="d5860-137">The default project contains a single control named `UserControl1`.</span></span>  
  
6. <span data-ttu-id="d5860-138">在解决方案资源管理器中， `UserControl1` 将重命名为 `MyControl1` 。</span><span class="sxs-lookup"><span data-stu-id="d5860-138">In Solution Explorer, rename `UserControl1` to `MyControl1`.</span></span>  
  
 <span data-ttu-id="d5860-139">项目应具有对以下系统 DLL 的引用。</span><span class="sxs-lookup"><span data-stu-id="d5860-139">Your project should have references to the following system DLLs.</span></span> <span data-ttu-id="d5860-140">如果默认不包含其中任何 DLL，则将它们添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="d5860-140">If any of these DLLs are not included by default, add them to the project.</span></span>  
  
- <span data-ttu-id="d5860-141">System</span><span class="sxs-lookup"><span data-stu-id="d5860-141">System</span></span>  
  
- <span data-ttu-id="d5860-142">System.Data</span><span class="sxs-lookup"><span data-stu-id="d5860-142">System.Data</span></span>  
  
- <span data-ttu-id="d5860-143">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="d5860-143">System.Drawing</span></span>  
  
- <span data-ttu-id="d5860-144">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="d5860-144">System.Windows.Forms</span></span>  
  
- <span data-ttu-id="d5860-145">System.Xml</span><span class="sxs-lookup"><span data-stu-id="d5860-145">System.Xml</span></span>  
  
### <a name="adding-controls-to-the-form"></a><span data-ttu-id="d5860-146">将控件添加到窗体</span><span class="sxs-lookup"><span data-stu-id="d5860-146">Adding Controls to the Form</span></span>  

 <span data-ttu-id="d5860-147">向窗体添加控件：</span><span class="sxs-lookup"><span data-stu-id="d5860-147">To add controls to the form:</span></span>  
  
- <span data-ttu-id="d5860-148">`MyControl1`在设计器中打开。</span><span class="sxs-lookup"><span data-stu-id="d5860-148">Open `MyControl1` in the designer.</span></span>  
  
 <span data-ttu-id="d5860-149">在 <xref:System.Windows.Forms.Label> 窗体上，添加五个控件及其相应 <xref:System.Windows.Forms.TextBox> 的控件，并将其调整大小并按上图所示进行排列。</span><span class="sxs-lookup"><span data-stu-id="d5860-149">Add five <xref:System.Windows.Forms.Label> controls and their corresponding <xref:System.Windows.Forms.TextBox> controls, sized and arranged as they are in the preceding illustration, on the form.</span></span> <span data-ttu-id="d5860-150">在此示例中， <xref:System.Windows.Forms.TextBox> 控件的名称为：</span><span class="sxs-lookup"><span data-stu-id="d5860-150">In the example, the <xref:System.Windows.Forms.TextBox> controls are named:</span></span>  
  
- `txtName`  
  
- `txtAddress`  
  
- `txtCity`  
  
- `txtState`  
  
- `txtZip`  
  
 <span data-ttu-id="d5860-151">添加 <xref:System.Windows.Forms.Button> 标记为 **"确定" 和 "** **取消**" 的两个控件。</span><span class="sxs-lookup"><span data-stu-id="d5860-151">Add two <xref:System.Windows.Forms.Button> controls labeled **OK** and **Cancel**.</span></span> <span data-ttu-id="d5860-152">在此示例中，按钮名称 `btnOK` 分别为和 `btnCancel` 。</span><span class="sxs-lookup"><span data-stu-id="d5860-152">In the example, the button names are `btnOK` and `btnCancel`, respectively.</span></span>  
  
### <a name="implementing-the-supporting-code"></a><span data-ttu-id="d5860-153">实现支持代码</span><span class="sxs-lookup"><span data-stu-id="d5860-153">Implementing the Supporting Code</span></span>  

 <span data-ttu-id="d5860-154">在代码视图中打开窗体。</span><span class="sxs-lookup"><span data-stu-id="d5860-154">Open the form in code view.</span></span> <span data-ttu-id="d5860-155">控件通过引发自定义事件将收集的数据返回到其主机 `OnButtonClick` 。</span><span class="sxs-lookup"><span data-stu-id="d5860-155">The control returns the collected data to its host by raising the custom `OnButtonClick` event.</span></span> <span data-ttu-id="d5860-156">数据包含在事件自变量对象中。</span><span class="sxs-lookup"><span data-stu-id="d5860-156">The data is contained in the event argument object.</span></span> <span data-ttu-id="d5860-157">以下代码演示事件和委托声明。</span><span class="sxs-lookup"><span data-stu-id="d5860-157">The following code shows the event and delegate declaration.</span></span>  
  
 <span data-ttu-id="d5860-158">将以下代码添加到 `MyControl1` 类。</span><span class="sxs-lookup"><span data-stu-id="d5860-158">Add the following code to the `MyControl1` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 <span data-ttu-id="d5860-159">`MyControlEventArgs`类包含要返回给主机的信息。</span><span class="sxs-lookup"><span data-stu-id="d5860-159">The `MyControlEventArgs` class contains the information to be returned to the host.</span></span>

 <span data-ttu-id="d5860-160">将以下类添加到窗体中。</span><span class="sxs-lookup"><span data-stu-id="d5860-160">Add the following class to the form.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 <span data-ttu-id="d5860-161">当用户单击 **"确定" 或 "** **取消** " 按钮时， <xref:System.Windows.Forms.Control.Click> 事件处理程序创建一个 `MyControlEventArgs` 包含数据的对象，并引发 `OnButtonClick` 事件。</span><span class="sxs-lookup"><span data-stu-id="d5860-161">When the user clicks the **OK** or **Cancel** button, the <xref:System.Windows.Forms.Control.Click> event handlers create a `MyControlEventArgs` object that contains the data and raises the `OnButtonClick` event.</span></span> <span data-ttu-id="d5860-162">这两个处理程序的唯一区别在于事件参数的 `IsOK` 属性。</span><span class="sxs-lookup"><span data-stu-id="d5860-162">The only difference between the two handlers is the event argument's `IsOK` property.</span></span> <span data-ttu-id="d5860-163">此属性使主机可以确定单击的按钮。</span><span class="sxs-lookup"><span data-stu-id="d5860-163">This property enables the host to determine which button was clicked.</span></span> <span data-ttu-id="d5860-164">对于 " `true` **确定"** 按钮，将设置为， `false` 为 " **取消** " 按钮设置。</span><span class="sxs-lookup"><span data-stu-id="d5860-164">It is set to `true` for the **OK** button, and `false` for the **Cancel** button.</span></span> <span data-ttu-id="d5860-165">以下代码演示两个按钮处理程序。</span><span class="sxs-lookup"><span data-stu-id="d5860-165">The following code shows the two button handlers.</span></span>

 <span data-ttu-id="d5860-166">将以下代码添加到 `MyControl1` 类。</span><span class="sxs-lookup"><span data-stu-id="d5860-166">Add the following code to the `MyControl1` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a><span data-ttu-id="d5860-167">赋予程序集强名称并生成程序集</span><span class="sxs-lookup"><span data-stu-id="d5860-167">Giving the Assembly a Strong Name and Building the Assembly</span></span>

 <span data-ttu-id="d5860-168">对于应用程序要引用此程序集 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，该程序集必须具有强名称。</span><span class="sxs-lookup"><span data-stu-id="d5860-168">For this assembly to be referenced by a [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] application, it must have a strong name.</span></span> <span data-ttu-id="d5860-169">若要创建强名称，请使用 Sn.exe 创建密钥文件并将其添加到你的项目中。</span><span class="sxs-lookup"><span data-stu-id="d5860-169">To create a strong name, create a key file with Sn.exe and add it to your project.</span></span>

1. <span data-ttu-id="d5860-170">打开 Visual Studio 命令提示。</span><span class="sxs-lookup"><span data-stu-id="d5860-170">Open a Visual Studio command prompt.</span></span> <span data-ttu-id="d5860-171">为此，请单击 " **开始** " 菜单，然后选择 " **所有程序/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio 命令提示**"。</span><span class="sxs-lookup"><span data-stu-id="d5860-171">To do so, click the **Start** menu, and then select **All Programs/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio Command Prompt**.</span></span> <span data-ttu-id="d5860-172">这将启动包含自定义环境变量的控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="d5860-172">This launches a console window with customized environment variables.</span></span>

2. <span data-ttu-id="d5860-173">在命令提示符下，使用 `cd` 命令来打开项目文件夹。</span><span class="sxs-lookup"><span data-stu-id="d5860-173">At the command prompt, use the `cd` command to go to your project folder.</span></span>

3. <span data-ttu-id="d5860-174">通过运行以下命令生成名为 MyControls.snk 的密钥文件。</span><span class="sxs-lookup"><span data-stu-id="d5860-174">Generate a key file named MyControls.snk by running the following command.</span></span>

    ```console
    Sn.exe -k MyControls.snk
    ```

4. <span data-ttu-id="d5860-175">若要在项目中包含密钥文件，请在解决方案资源管理器中右键单击项目名称，然后单击 " **属性**"。</span><span class="sxs-lookup"><span data-stu-id="d5860-175">To include the key file in your project, right-click the project name in Solution Explorer and then click **Properties**.</span></span> <span data-ttu-id="d5860-176">在 "项目设计器" 中，单击 " **签名** " 选项卡，选中 "为 **程序集签名** " 复选框，然后浏览到密钥文件。</span><span class="sxs-lookup"><span data-stu-id="d5860-176">In the Project Designer, click the **Signing** tab, select the **Sign the assembly** check box and then browse to your key file.</span></span>

5. <span data-ttu-id="d5860-177">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="d5860-177">Build the solution.</span></span> <span data-ttu-id="d5860-178">生成将产生一个名为 MyControls.dll 的 DLL。</span><span class="sxs-lookup"><span data-stu-id="d5860-178">The build will produce a DLL named MyControls.dll.</span></span>

## <a name="implementing-the-wpf-host-application"></a><span data-ttu-id="d5860-179">实现 WPF 主机应用程序</span><span class="sxs-lookup"><span data-stu-id="d5860-179">Implementing the WPF Host Application</span></span>

 <span data-ttu-id="d5860-180">[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]宿主应用程序使用 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件进行宿主 `MyControl1` 。</span><span class="sxs-lookup"><span data-stu-id="d5860-180">The [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] host application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control to host `MyControl1`.</span></span> <span data-ttu-id="d5860-181">应用程序处理 `OnButtonClick` 事件以接收来自控件的数据。</span><span class="sxs-lookup"><span data-stu-id="d5860-181">The application handles the `OnButtonClick` event to receive the data from the control.</span></span> <span data-ttu-id="d5860-182">它还包含一个选项按钮集合，使你能够从应用程序更改控件的某些属性 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="d5860-182">It also has a collection of option buttons that enable you to change some of the control's properties from the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="d5860-183">下图显示已完成的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d5860-183">The following illustration shows the finished application.</span></span>

<span data-ttu-id="d5860-184">下图显示了完整的应用程序，包括嵌入在 WPF 应用程序中的控件：</span><span class="sxs-lookup"><span data-stu-id="d5860-184">The following image shows the complete application, including the control embedded in the WPF application:</span></span>

 ![显示嵌入在 WPF 页中的控件的屏幕截图。](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a><span data-ttu-id="d5860-186">创建项目</span><span class="sxs-lookup"><span data-stu-id="d5860-186">Creating the Project</span></span>

 <span data-ttu-id="d5860-187">启动项目：</span><span class="sxs-lookup"><span data-stu-id="d5860-187">To start the project:</span></span>

1. <span data-ttu-id="d5860-188">打开 Visual Studio，然后选择 " **新建项目**"。</span><span class="sxs-lookup"><span data-stu-id="d5860-188">Open Visual Studio, and select **New Project**.</span></span>

2. <span data-ttu-id="d5860-189">在 "窗口" 类别中，选择 " **WPF 应用程序** " 模板。</span><span class="sxs-lookup"><span data-stu-id="d5860-189">In the Window category, select the **WPF Application** template.</span></span>

3. <span data-ttu-id="d5860-190">将新项目命名为 `WpfHost`。</span><span class="sxs-lookup"><span data-stu-id="d5860-190">Name the new project `WpfHost`.</span></span>

4. <span data-ttu-id="d5860-191">对于位置，指定包含 MyControls 项目的同一顶层文件夹。</span><span class="sxs-lookup"><span data-stu-id="d5860-191">For the location, specify the same top-level folder that contains the MyControls project.</span></span>

5. <span data-ttu-id="d5860-192">单击“确定”以创建该项目  。</span><span class="sxs-lookup"><span data-stu-id="d5860-192">Click **OK** to create the project.</span></span>

 <span data-ttu-id="d5860-193">还需要添加对包含 `MyControl1` 和其他程序集的 DLL 的引用。</span><span class="sxs-lookup"><span data-stu-id="d5860-193">You also need to add references to the DLL that contains `MyControl1` and other assemblies.</span></span>

1. <span data-ttu-id="d5860-194">在解决方案资源管理器中右键单击项目名称，然后选择 " **添加引用**"。</span><span class="sxs-lookup"><span data-stu-id="d5860-194">Right-click the project name in Solution Explorer and select **Add Reference**.</span></span>

2. <span data-ttu-id="d5860-195">单击 " **浏览** " 选项卡，然后浏览到包含 MyControls.dll 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d5860-195">Click the **Browse** tab, and browse to the folder that contains MyControls.dll.</span></span> <span data-ttu-id="d5860-196">在本演练中，此文件夹位于 MyControls\bin\Debug。</span><span class="sxs-lookup"><span data-stu-id="d5860-196">For this walkthrough, this folder is MyControls\bin\Debug.</span></span>

3. <span data-ttu-id="d5860-197">选择 "MyControls.dll"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d5860-197">Select MyControls.dll, and then click **OK**.</span></span>

4. <span data-ttu-id="d5860-198">添加对 WindowsFormsIntegration 程序集的引用，该程序集名为 WindowsFormsIntegration.dll。</span><span class="sxs-lookup"><span data-stu-id="d5860-198">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

### <a name="implementing-the-basic-layout"></a><span data-ttu-id="d5860-199">实现基本布局</span><span class="sxs-lookup"><span data-stu-id="d5860-199">Implementing the Basic Layout</span></span>

 <span data-ttu-id="d5860-200">[!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)]主机应用程序的是在 mainwindow.xaml 中实现的。</span><span class="sxs-lookup"><span data-stu-id="d5860-200">The [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] of the host application is implemented in MainWindow.xaml.</span></span> <span data-ttu-id="d5860-201">此文件包含 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 用于定义布局的标记，并承载 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="d5860-201">This file contains [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] markup that defines the layout, and hosts the Windows Forms control.</span></span> <span data-ttu-id="d5860-202">该应用程序分为三个区域：</span><span class="sxs-lookup"><span data-stu-id="d5860-202">The application is divided into three regions:</span></span>

- <span data-ttu-id="d5860-203">" **控件属性** " 面板，其中包含选项按钮的集合，您可以使用这些按钮来修改所承载控件的各种属性。</span><span class="sxs-lookup"><span data-stu-id="d5860-203">The **Control Properties** panel, which contains a collection of option buttons that you can use to modify various properties of the hosted control.</span></span>

- <span data-ttu-id="d5860-204">" **控制面板** " 中的数据，其中包含多个 <xref:System.Windows.Controls.TextBlock> 显示从寄宿控件返回的数据的元素。</span><span class="sxs-lookup"><span data-stu-id="d5860-204">The **Data from Control** panel, which contains several <xref:System.Windows.Controls.TextBlock> elements that display the data returned from the hosted control.</span></span>

- <span data-ttu-id="d5860-205">所承载控件本身。</span><span class="sxs-lookup"><span data-stu-id="d5860-205">The hosted control itself.</span></span>

 <span data-ttu-id="d5860-206">基本布局如下面的 XAML 中所示。</span><span class="sxs-lookup"><span data-stu-id="d5860-206">The basic layout is shown in the following XAML.</span></span> <span data-ttu-id="d5860-207">在此示例中省略了主机需要的标记 `MyControl1` ，稍后将对此进行讨论。</span><span class="sxs-lookup"><span data-stu-id="d5860-207">The markup that is needed to host `MyControl1` is omitted from this example, but will be discussed later.</span></span>

 <span data-ttu-id="d5860-208">将 MainWindow.xaml 中的 XAML 替换为以下内容。</span><span class="sxs-lookup"><span data-stu-id="d5860-208">Replace the XAML in MainWindow.xaml with the following.</span></span> <span data-ttu-id="d5860-209">如果使用 Visual Basic，请将类更改为 `x:Class="MainWindow"` 。</span><span class="sxs-lookup"><span data-stu-id="d5860-209">If you are using Visual Basic, change the class to `x:Class="MainWindow"`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 <span data-ttu-id="d5860-210">第一个 <xref:System.Windows.Controls.StackPanel> 元素包含多组 <xref:System.Windows.Controls.RadioButton> 控件，这些控件可用于修改所承载控件的各种默认属性。</span><span class="sxs-lookup"><span data-stu-id="d5860-210">The first <xref:System.Windows.Controls.StackPanel> element contains several sets of <xref:System.Windows.Controls.RadioButton> controls that enable you to modify various default properties of the hosted control.</span></span> <span data-ttu-id="d5860-211">后跟一个承载的 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素 `MyControl1` 。</span><span class="sxs-lookup"><span data-stu-id="d5860-211">That is followed by a <xref:System.Windows.Forms.Integration.WindowsFormsHost> element, which hosts `MyControl1`.</span></span> <span data-ttu-id="d5860-212">最后一个 <xref:System.Windows.Controls.StackPanel> 元素包含多个 <xref:System.Windows.Controls.TextBlock> 元素，这些元素显示由寄宿控件返回的数据。</span><span class="sxs-lookup"><span data-stu-id="d5860-212">The final <xref:System.Windows.Controls.StackPanel> element contains several <xref:System.Windows.Controls.TextBlock> elements that display the data that is returned by the hosted control.</span></span> <span data-ttu-id="d5860-213">元素的顺序以及 <xref:System.Windows.Controls.DockPanel.Dock%2A> 和 <xref:System.Windows.FrameworkElement.Height%2A> 特性设置将承载的控件嵌入窗口中，而不会出现空白或失真。</span><span class="sxs-lookup"><span data-stu-id="d5860-213">The ordering of the elements and the <xref:System.Windows.Controls.DockPanel.Dock%2A> and <xref:System.Windows.FrameworkElement.Height%2A> attribute settings embed the hosted control into the window with no gaps or distortion.</span></span>

#### <a name="hosting-the-control"></a><span data-ttu-id="d5860-214">承载控件</span><span class="sxs-lookup"><span data-stu-id="d5860-214">Hosting the Control</span></span>

 <span data-ttu-id="d5860-215">下面的 XAML 的编辑版本重点介绍承载所需的元素 `MyControl1` 。</span><span class="sxs-lookup"><span data-stu-id="d5860-215">The following edited version of the previous XAML focuses on the elements that are needed to host `MyControl1`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 <span data-ttu-id="d5860-216">`xmlns`命名空间映射特性创建对 `MyControls` 包含所承载控件的命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="d5860-216">The `xmlns` namespace mapping attribute creates a reference to the `MyControls` namespace that contains the hosted control.</span></span> <span data-ttu-id="d5860-217">通过此映射，你可以将 `MyControl1` 中的表示 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 为 `<mcl:MyControl1>` 。</span><span class="sxs-lookup"><span data-stu-id="d5860-217">This mapping enables you to represent `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] as `<mcl:MyControl1>`.</span></span>

 <span data-ttu-id="d5860-218">XAML 中的两个元素处理承载：</span><span class="sxs-lookup"><span data-stu-id="d5860-218">Two elements in the XAML handle the hosting:</span></span>

- <span data-ttu-id="d5860-219">`WindowsFormsHost` 表示 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 一个元素，该元素使您能够在应用程序中承载 Windows 窗体控件 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="d5860-219">`WindowsFormsHost` represents the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element that enables you to host a Windows Forms control in a [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

- <span data-ttu-id="d5860-220">`mcl:MyControl1`，它表示 `MyControl1` 将添加到 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的子集合。</span><span class="sxs-lookup"><span data-stu-id="d5860-220">`mcl:MyControl1`, which represents `MyControl1`, is added to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child collection.</span></span> <span data-ttu-id="d5860-221">因此，此 Windows 窗体控件将呈现为窗口的一部分 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，您可以从应用程序与控件进行通信。</span><span class="sxs-lookup"><span data-stu-id="d5860-221">As a result, this Windows Forms control is rendered as part of the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] window, and you can communicate with the control from the application.</span></span>

### <a name="implementing-the-code-behind-file"></a><span data-ttu-id="d5860-222">实现代码隐藏文件</span><span class="sxs-lookup"><span data-stu-id="d5860-222">Implementing the Code-Behind File</span></span>

 <span data-ttu-id="d5860-223">代码隐藏文件（Mainwindow.xaml 或 Mainwindow.xaml）包含实现上一部分所述的功能的过程代码，该代码可实现 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="d5860-223">The code-behind file, MainWindow.xaml.vb or MainWindow.xaml.cs, contains the procedural code that implements the functionality of the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] discussed in the preceding section.</span></span> <span data-ttu-id="d5860-224">主要任务有：</span><span class="sxs-lookup"><span data-stu-id="d5860-224">The primary tasks are:</span></span>

- <span data-ttu-id="d5860-225">将事件处理程序附加到 `MyControl1` 的 `OnButtonClick` 事件。</span><span class="sxs-lookup"><span data-stu-id="d5860-225">Attaching an event handler to `MyControl1`'s `OnButtonClick` event.</span></span>

- <span data-ttu-id="d5860-226">`MyControl1`根据设置选项按钮集合的方式修改的各种属性。</span><span class="sxs-lookup"><span data-stu-id="d5860-226">Modifying various properties of `MyControl1`, based on how the collection of option buttons are set.</span></span>

- <span data-ttu-id="d5860-227">显示控件收集的数据。</span><span class="sxs-lookup"><span data-stu-id="d5860-227">Displaying the data collected by the control.</span></span>

#### <a name="initializing-the-application"></a><span data-ttu-id="d5860-228">初始化应用程序</span><span class="sxs-lookup"><span data-stu-id="d5860-228">Initializing the Application</span></span>

 <span data-ttu-id="d5860-229">初始化代码包含在窗口事件的事件处理程序中 <xref:System.Windows.FrameworkElement.Loaded> ，并将事件处理程序附加到控件的 `OnButtonClick` 事件。</span><span class="sxs-lookup"><span data-stu-id="d5860-229">The initialization code is contained in an event handler for the window's <xref:System.Windows.FrameworkElement.Loaded> event and attaches an event handler to the control's `OnButtonClick` event.</span></span>

 <span data-ttu-id="d5860-230">在 Mainwindow.xaml 或 Mainwindow.xaml 中，将以下代码添加到 `MainWindow` 类。</span><span class="sxs-lookup"><span data-stu-id="d5860-230">In MainWindow.xaml.vb or MainWindow.xaml.cs, add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 <span data-ttu-id="d5860-231">由于前面所述的是在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] `MyControl1` <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的子元素集合中添加的，因此可以强制转换该 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素，以获取对的 <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> 引用 `MyControl1` 。</span><span class="sxs-lookup"><span data-stu-id="d5860-231">Because the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] discussed previously added `MyControl1` to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child element collection, you can cast the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> to get the reference to `MyControl1`.</span></span> <span data-ttu-id="d5860-232">然后，可以使用该引用将事件处理程序附加到 `OnButtonClick` 。</span><span class="sxs-lookup"><span data-stu-id="d5860-232">You can then use that reference to attach an event handler to `OnButtonClick`.</span></span>

 <span data-ttu-id="d5860-233">除了提供对控件本身的引用外，还 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 公开了许多控件属性，您可以从应用程序中操作。</span><span class="sxs-lookup"><span data-stu-id="d5860-233">In addition to providing a reference to the control itself, <xref:System.Windows.Forms.Integration.WindowsFormsHost> exposes a number of the control's properties, which you can manipulate from the application.</span></span> <span data-ttu-id="d5860-234">初始化代码将这些值分配给私有全局变量，以供稍后在应用程序中使用。</span><span class="sxs-lookup"><span data-stu-id="d5860-234">The initialization code assigns those values to private global variables for later use in the application.</span></span>

 <span data-ttu-id="d5860-235">为了能够轻松地访问 DLL 中的类型 `MyControls` ，请将以下 `Imports` 或语句添加 `using` 到文件的顶部。</span><span class="sxs-lookup"><span data-stu-id="d5860-235">So that you can easily access the types in the `MyControls` DLL, add the following `Imports` or `using` statement to the top of the file.</span></span>

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a><span data-ttu-id="d5860-236">处理 OnButtonClick 事件</span><span class="sxs-lookup"><span data-stu-id="d5860-236">Handling the OnButtonClick Event</span></span>

 <span data-ttu-id="d5860-237">`MyControl1``OnButtonClick`当用户单击控件的任一按钮时，引发事件。</span><span class="sxs-lookup"><span data-stu-id="d5860-237">`MyControl1` raises the `OnButtonClick` event when the user clicks either of the control's buttons.</span></span>

 <span data-ttu-id="d5860-238">将以下代码添加到 `MainWindow` 类。</span><span class="sxs-lookup"><span data-stu-id="d5860-238">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 <span data-ttu-id="d5860-239">文本框中的数据将打包到 `MyControlEventArgs` 对象中。</span><span class="sxs-lookup"><span data-stu-id="d5860-239">The data in the text boxes is packed into the `MyControlEventArgs` object.</span></span> <span data-ttu-id="d5860-240">如果用户单击 **"确定"** 按钮，事件处理程序将提取数据并将其显示在下面的面板中 `MyControl1` 。</span><span class="sxs-lookup"><span data-stu-id="d5860-240">If the user clicks the **OK** button, the event handler extracts the data and displays it in the panel below `MyControl1`.</span></span>

#### <a name="modifying-the-controls-properties"></a><span data-ttu-id="d5860-241">修改控件属性</span><span class="sxs-lookup"><span data-stu-id="d5860-241">Modifying the Control’s Properties</span></span>

 <span data-ttu-id="d5860-242"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素公开几个托管控件的默认属性。</span><span class="sxs-lookup"><span data-stu-id="d5860-242">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element exposes several of the hosted control's default properties.</span></span> <span data-ttu-id="d5860-243">因此，可以更改空间外观，以更贴合应用程序的样式。</span><span class="sxs-lookup"><span data-stu-id="d5860-243">As a result, you can change the appearance of the control to match the style of your application more closely.</span></span> <span data-ttu-id="d5860-244">位于左侧面板中的选项按钮组使用户能够修改多个颜色和字体属性。</span><span class="sxs-lookup"><span data-stu-id="d5860-244">The sets of option buttons in the left panel enable the user to modify several color and font properties.</span></span> <span data-ttu-id="d5860-245">每组按钮都具有事件的处理程序 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> ，该处理程序检测用户的选项按钮选择并更改控件上的相应属性。</span><span class="sxs-lookup"><span data-stu-id="d5860-245">Each set of buttons has a handler for the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which detects the user's option button selections and changes the corresponding property on the control.</span></span>

 <span data-ttu-id="d5860-246">将以下代码添加到 `MainWindow` 类。</span><span class="sxs-lookup"><span data-stu-id="d5860-246">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 <span data-ttu-id="d5860-247">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="d5860-247">Build and run the application.</span></span> <span data-ttu-id="d5860-248">在 Windows 窗体复合控件中添加一些文本，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d5860-248">Add some text in the Windows Forms composite control and then click **OK**.</span></span> <span data-ttu-id="d5860-249">文本将显示在标签中。</span><span class="sxs-lookup"><span data-stu-id="d5860-249">The text appears in the labels.</span></span> <span data-ttu-id="d5860-250">单击不同的单选按钮查看在控件上的效果。</span><span class="sxs-lookup"><span data-stu-id="d5860-250">Click the different radio buttons to see the effect on the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5860-251">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5860-251">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="d5860-252">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="d5860-252">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="d5860-253">演练：在 WPF 中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="d5860-253">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="d5860-254">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="d5860-254">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
