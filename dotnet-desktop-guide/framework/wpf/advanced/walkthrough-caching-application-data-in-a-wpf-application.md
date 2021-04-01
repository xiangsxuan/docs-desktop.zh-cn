---
title: 缓存应用数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: 03d54614b018c7cb8e17858eba61bb6efaa93cd0
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973845"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="25e8b-102">演练：在 WPF 应用程序中缓存应用程序数据</span><span class="sxs-lookup"><span data-stu-id="25e8b-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="25e8b-103">缓存可以将数据存储在内存中以便快速访问。</span><span class="sxs-lookup"><span data-stu-id="25e8b-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="25e8b-104">再次访问数据时，应用程序可以从缓存获取数据，而不是从原始源检索数据。</span><span class="sxs-lookup"><span data-stu-id="25e8b-104">When the data is accessed again, applications can get the data from the cache instead of retrieving it from the original source.</span></span> <span data-ttu-id="25e8b-105">这可改善性能和可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="25e8b-105">This can improve performance and scalability.</span></span> <span data-ttu-id="25e8b-106">此外，数据源暂时不可用时，缓存可提供数据。</span><span class="sxs-lookup"><span data-stu-id="25e8b-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>

 <span data-ttu-id="25e8b-107">.NET Framework 提供使你能够在 .NET Framework 应用程序中使用缓存的类。</span><span class="sxs-lookup"><span data-stu-id="25e8b-107">The .NET Framework provides classes that enable you to use caching in .NET Framework applications.</span></span> <span data-ttu-id="25e8b-108">这些类位于 <xref:System.Runtime.Caching> 命名空间中。</span><span class="sxs-lookup"><span data-stu-id="25e8b-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="25e8b-109"><xref:System.Runtime.Caching>命名空间是 .NET Framework 4 中的新命名空间。</span><span class="sxs-lookup"><span data-stu-id="25e8b-109">The <xref:System.Runtime.Caching> namespace is new in the .NET Framework 4.</span></span> <span data-ttu-id="25e8b-110">此命名空间使缓存可供所有 .NET Framework 应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="25e8b-110">This namespace makes caching is available to all .NET Framework applications.</span></span> <span data-ttu-id="25e8b-111">在 .NET Framework 的以前版本中，仅在命名空间中提供缓存， <xref:System.Web> 因此需要依赖 ASP.NET 类。</span><span class="sxs-lookup"><span data-stu-id="25e8b-111">In previous versions of the .NET Framework, caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>

 <span data-ttu-id="25e8b-112">本演练演示如何使用 .NET Framework 中提供的缓存功能作为 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 应用程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="25e8b-112">This walkthrough shows you how to use the caching functionality that is available in the .NET Framework as part of a [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="25e8b-113">在本演练中，您将缓存文本文件的内容。</span><span class="sxs-lookup"><span data-stu-id="25e8b-113">In the walkthrough, you cache the contents of a text file.</span></span>

 <span data-ttu-id="25e8b-114">本演练演示以下任务：</span><span class="sxs-lookup"><span data-stu-id="25e8b-114">Tasks illustrated in this walkthrough include the following:</span></span>

- <span data-ttu-id="25e8b-115">创建 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="25e8b-115">Creating a WPF application project.</span></span>

- <span data-ttu-id="25e8b-116">添加对 .NET Framework 4 的引用。</span><span class="sxs-lookup"><span data-stu-id="25e8b-116">Adding a reference to the .NET Framework 4.</span></span>

- <span data-ttu-id="25e8b-117">初始化缓存。</span><span class="sxs-lookup"><span data-stu-id="25e8b-117">Initializing a cache.</span></span>

- <span data-ttu-id="25e8b-118">添加包含文本文件内容的缓存项。</span><span class="sxs-lookup"><span data-stu-id="25e8b-118">Adding a cache entry that contains the contents of a text file.</span></span>

- <span data-ttu-id="25e8b-119">为缓存条目提供逐出策略。</span><span class="sxs-lookup"><span data-stu-id="25e8b-119">Providing an eviction policy for the cache entry.</span></span>

- <span data-ttu-id="25e8b-120">监视缓存文件的路径，并通知缓存实例对被监视项的更改。</span><span class="sxs-lookup"><span data-stu-id="25e8b-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="25e8b-121">先决条件</span><span class="sxs-lookup"><span data-stu-id="25e8b-121">Prerequisites</span></span>
 <span data-ttu-id="25e8b-122">若要完成本演练，你将需要：</span><span class="sxs-lookup"><span data-stu-id="25e8b-122">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="25e8b-123">Visual Studio 2010。</span><span class="sxs-lookup"><span data-stu-id="25e8b-123">Visual Studio 2010.</span></span>

- <span data-ttu-id="25e8b-124">包含少量文本的文本文件。</span><span class="sxs-lookup"><span data-stu-id="25e8b-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="25e8b-125"> (将在消息框中显示文本文件的内容。 ) 本演练中所示的代码假定您正在使用以下文件：</span><span class="sxs-lookup"><span data-stu-id="25e8b-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>

     `c:\cache\cacheText.txt`

     <span data-ttu-id="25e8b-126">但是，您可以使用任何文本文件并对此演练中的代码进行较小的更改。</span><span class="sxs-lookup"><span data-stu-id="25e8b-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>

## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="25e8b-127">创建 WPF 应用程序项目</span><span class="sxs-lookup"><span data-stu-id="25e8b-127">Creating a WPF Application Project</span></span>
 <span data-ttu-id="25e8b-128">首先创建一个 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="25e8b-128">You will start by creating a WPF application project.</span></span>

#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="25e8b-129">创建 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="25e8b-129">To create a WPF application</span></span>

1. <span data-ttu-id="25e8b-130">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="25e8b-130">Start Visual Studio.</span></span>

2. <span data-ttu-id="25e8b-131">在 " **文件** " 菜单中，单击 " **新建**"，然后单击 " **新建项目**"。</span><span class="sxs-lookup"><span data-stu-id="25e8b-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>

     <span data-ttu-id="25e8b-132">显示 **“新项目”** 对话框。</span><span class="sxs-lookup"><span data-stu-id="25e8b-132">The **New Project** dialog box is displayed.</span></span>

3. <span data-ttu-id="25e8b-133">在 " **已安装的模板**" 下，选择要 (**Visual Basic** 或 **Visual c #**) 使用的编程语言。</span><span class="sxs-lookup"><span data-stu-id="25e8b-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>

4. <span data-ttu-id="25e8b-134">在 " **新建项目** " 对话框中，选择 " **WPF 应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="25e8b-134">In the **New Project** dialog box, select **WPF Application**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="25e8b-135">如果看不到 " **Wpf 应用程序** " 模板，请确保以支持 WPF 的 .NET Framework 的版本为目标。</span><span class="sxs-lookup"><span data-stu-id="25e8b-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the .NET Framework that supports WPF.</span></span> <span data-ttu-id="25e8b-136">在 " **新建项目** " 对话框中，从列表中选择 ".NET Framework 4"。</span><span class="sxs-lookup"><span data-stu-id="25e8b-136">In the **New Project** dialog box, select .NET Framework 4 from the list.</span></span>

5. <span data-ttu-id="25e8b-137">在 " **名称** " 文本框中，输入项目的名称。</span><span class="sxs-lookup"><span data-stu-id="25e8b-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="25e8b-138">例如，可以输入 **WPFCaching**。</span><span class="sxs-lookup"><span data-stu-id="25e8b-138">For example, you can enter **WPFCaching**.</span></span>

6. <span data-ttu-id="25e8b-139">选择“为解决方案创建目录”复选框。</span><span class="sxs-lookup"><span data-stu-id="25e8b-139">Select the **Create directory for solution** check box.</span></span>

7. <span data-ttu-id="25e8b-140">单击 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="25e8b-140">Click **OK**.</span></span>

     <span data-ttu-id="25e8b-141">WPF 设计器将在 " **设计** " 视图中打开并显示 mainwindow.xaml 文件。</span><span class="sxs-lookup"><span data-stu-id="25e8b-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> <span data-ttu-id="25e8b-142">Visual Studio 将创建 " **我的项目** " 文件夹、应用程序 .xaml 文件和 mainwindow.xaml 文件。</span><span class="sxs-lookup"><span data-stu-id="25e8b-142">Visual Studio creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="25e8b-143">针对 .NET Framework 并添加对缓存程序集的引用</span><span class="sxs-lookup"><span data-stu-id="25e8b-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>
 <span data-ttu-id="25e8b-144">默认情况下，WPF 应用程序以 .NET Framework 4 客户端配置文件为目标。</span><span class="sxs-lookup"><span data-stu-id="25e8b-144">By default, WPF applications target the .NET Framework 4 Client Profile.</span></span> <span data-ttu-id="25e8b-145">若要 <xref:System.Runtime.Caching> 在 WPF 应用程序中使用命名空间，应用程序必须以 .NET Framework 4 (而不是 .NET Framework 4 客户端配置) 文件为目标，并且必须包括对命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="25e8b-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the .NET Framework 4 (not the .NET Framework 4 Client Profile) and must include a reference to the namespace.</span></span>

 <span data-ttu-id="25e8b-146">因此，下一步是更改 .NET Framework 目标并添加对 <xref:System.Runtime.Caching> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="25e8b-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="25e8b-147">更改 .NET Framework 目标的过程在 Visual Basic 项目和 Visual c # 项目中是不同的。</span><span class="sxs-lookup"><span data-stu-id="25e8b-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="25e8b-148">更改目标 .NET Framework Visual Basic</span><span class="sxs-lookup"><span data-stu-id="25e8b-148">To change the target .NET Framework in Visual Basic</span></span>

1. <span data-ttu-id="25e8b-149">在 " **解决方案资源管理器**" 中，右键单击项目名称，然后单击 " **属性**"。</span><span class="sxs-lookup"><span data-stu-id="25e8b-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>

     <span data-ttu-id="25e8b-150">将显示应用程序的 "属性" 窗口。</span><span class="sxs-lookup"><span data-stu-id="25e8b-150">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="25e8b-151">单击“编译”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="25e8b-151">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="25e8b-152">在窗口底部，单击 " **高级编译选项 ...**"。</span><span class="sxs-lookup"><span data-stu-id="25e8b-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>

     <span data-ttu-id="25e8b-153">将显示 " **高级编译器设置** " 对话框。</span><span class="sxs-lookup"><span data-stu-id="25e8b-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>

4. <span data-ttu-id="25e8b-154">在 " **目标框架 (" 所有配置 ")** 列表中，选择" .NET Framework 4 "。</span><span class="sxs-lookup"><span data-stu-id="25e8b-154">In the **Target framework (all configurations)** list, select .NET Framework 4.</span></span> <span data-ttu-id="25e8b-155"> (不要选择 .NET Framework 4 客户端配置文件。 ) </span><span class="sxs-lookup"><span data-stu-id="25e8b-155">(Do not select .NET Framework 4 Client Profile.)</span></span>

5. <span data-ttu-id="25e8b-156">单击 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="25e8b-156">Click **OK**.</span></span>

     <span data-ttu-id="25e8b-157">随即显示“目标框架更改”对话框。</span><span class="sxs-lookup"><span data-stu-id="25e8b-157">The **Target Framework Change** dialog box is displayed.</span></span>

6. <span data-ttu-id="25e8b-158">在 " **目标框架更改** " 对话框中，单击 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="25e8b-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>

     <span data-ttu-id="25e8b-159">项目已关闭，然后重新打开。</span><span class="sxs-lookup"><span data-stu-id="25e8b-159">The project is closed and is then reopened.</span></span>

7. <span data-ttu-id="25e8b-160">按照以下步骤添加对缓存程序集的引用：</span><span class="sxs-lookup"><span data-stu-id="25e8b-160">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="25e8b-161">在 **解决方案资源管理器** 中，右键单击项目名称，然后单击 " **添加引用**"。</span><span class="sxs-lookup"><span data-stu-id="25e8b-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="25e8b-162">选择 " **.net** " 选项卡，选择 `System.Runtime.Caching` ，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="25e8b-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="25e8b-163">在 Visual c # 项目中更改目标 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="25e8b-163">To change the target .NET Framework in a Visual C# project</span></span>

1. <span data-ttu-id="25e8b-164">在 **解决方案资源管理器** 中，右键单击项目名称，然后单击 " **属性**"。</span><span class="sxs-lookup"><span data-stu-id="25e8b-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>

     <span data-ttu-id="25e8b-165">将显示应用程序的 "属性" 窗口。</span><span class="sxs-lookup"><span data-stu-id="25e8b-165">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="25e8b-166">单击“应用程序”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="25e8b-166">Click the **Application** tab.</span></span>

3. <span data-ttu-id="25e8b-167">在 " **目标框架** " 列表中，选择 ".NET Framework 4"。</span><span class="sxs-lookup"><span data-stu-id="25e8b-167">In the **Target framework** list, select .NET Framework 4.</span></span> <span data-ttu-id="25e8b-168"> (不要选择 **.NET Framework 4 客户端配置文件**。 ) </span><span class="sxs-lookup"><span data-stu-id="25e8b-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>

4. <span data-ttu-id="25e8b-169">按照以下步骤添加对缓存程序集的引用：</span><span class="sxs-lookup"><span data-stu-id="25e8b-169">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="25e8b-170">右键单击 " **引用** " 文件夹，然后单击 " **添加引用**"。</span><span class="sxs-lookup"><span data-stu-id="25e8b-170">Right-click the **References** folder and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="25e8b-171">选择 " **.net** " 选项卡，选择 `System.Runtime.Caching` ，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="25e8b-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="25e8b-172">将按钮添加到 WPF 窗口</span><span class="sxs-lookup"><span data-stu-id="25e8b-172">Adding a Button to the WPF Window</span></span>
 <span data-ttu-id="25e8b-173">接下来，您将添加一个按钮控件，并为该按钮的事件创建一个事件处理程序 `Click` 。</span><span class="sxs-lookup"><span data-stu-id="25e8b-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="25e8b-174">稍后你将向添加代码，以便在单击按钮时，将缓存并显示文本文件的内容。</span><span class="sxs-lookup"><span data-stu-id="25e8b-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>

#### <a name="to-add-a-button-control"></a><span data-ttu-id="25e8b-175">添加按钮控件</span><span class="sxs-lookup"><span data-stu-id="25e8b-175">To add a button control</span></span>

1. <span data-ttu-id="25e8b-176">在 **解决方案资源管理器** 中，双击 mainwindow.xaml 文件以将其打开。</span><span class="sxs-lookup"><span data-stu-id="25e8b-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>

2. <span data-ttu-id="25e8b-177">从 " **工具箱**" 的 " **常用 WPF 控件**" 下，将 `Button` 控件拖动到 `MainWindow` 窗口。</span><span class="sxs-lookup"><span data-stu-id="25e8b-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>

3. <span data-ttu-id="25e8b-178">在 " **属性** " 窗口中，将 `Content` 控件的属性设置为 " `Button` **获取缓存**"。</span><span class="sxs-lookup"><span data-stu-id="25e8b-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>

## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="25e8b-179">初始化缓存并缓存项</span><span class="sxs-lookup"><span data-stu-id="25e8b-179">Initializing the Cache and Caching an Entry</span></span>
 <span data-ttu-id="25e8b-180">接下来，你将添加代码来执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="25e8b-180">Next, you will add the code to perform the following tasks:</span></span>

- <span data-ttu-id="25e8b-181">创建缓存类的实例，即，将实例化一个新的 <xref:System.Runtime.Caching.MemoryCache> 对象。</span><span class="sxs-lookup"><span data-stu-id="25e8b-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>

- <span data-ttu-id="25e8b-182">指定缓存使用 <xref:System.Runtime.Caching.HostFileChangeMonitor> 对象来监视文本文件中的更改。</span><span class="sxs-lookup"><span data-stu-id="25e8b-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>

- <span data-ttu-id="25e8b-183">读取文本文件并将其内容缓存为缓存条目。</span><span class="sxs-lookup"><span data-stu-id="25e8b-183">Read the text file and cache its contents as a cache entry.</span></span>

- <span data-ttu-id="25e8b-184">显示缓存的文本文件的内容。</span><span class="sxs-lookup"><span data-stu-id="25e8b-184">Display the contents of the cached text file.</span></span>

#### <a name="to-create-the-cache-object"></a><span data-ttu-id="25e8b-185">创建缓存对象</span><span class="sxs-lookup"><span data-stu-id="25e8b-185">To create the cache object</span></span>

1. <span data-ttu-id="25e8b-186">双击您刚添加的按钮，以便在 Mainwindow.xaml 或 Mainwindow.xaml 文件中创建事件处理程序，。</span><span class="sxs-lookup"><span data-stu-id="25e8b-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>

2. <span data-ttu-id="25e8b-187">在类声明) 之前 (文件顶部，添加以下 `Imports` (Visual Basic) 或 `using` (c # ) 语句：</span><span class="sxs-lookup"><span data-stu-id="25e8b-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3. <span data-ttu-id="25e8b-188">在事件处理程序中，添加以下代码以实例化缓存对象：</span><span class="sxs-lookup"><span data-stu-id="25e8b-188">In the event handler, add the following code to instantiate the cache object:</span></span>

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     <span data-ttu-id="25e8b-189"><xref:System.Runtime.Caching.ObjectCache>类是提供内存中对象缓存的内置类。</span><span class="sxs-lookup"><span data-stu-id="25e8b-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>

4. <span data-ttu-id="25e8b-190">添加以下代码以读取名为的缓存条目的内容 `filecontents` ：</span><span class="sxs-lookup"><span data-stu-id="25e8b-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5. <span data-ttu-id="25e8b-191">添加以下代码以检查是否存在名为的缓存条目 `filecontents` ：</span><span class="sxs-lookup"><span data-stu-id="25e8b-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     <span data-ttu-id="25e8b-192">如果指定的缓存项不存在，则必须读取文本文件并将其作为缓存项添加到缓存中。</span><span class="sxs-lookup"><span data-stu-id="25e8b-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>

6. <span data-ttu-id="25e8b-193">在 `if/then` 块中，添加以下代码，以创建一个新 <xref:System.Runtime.Caching.CacheItemPolicy> 的对象，该对象指定缓存项在10秒后过期。</span><span class="sxs-lookup"><span data-stu-id="25e8b-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     <span data-ttu-id="25e8b-194">如果未提供任何逐出或过期信息，则默认值为 <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration> ，这意味着缓存条目永远不会仅基于绝对时间过期。</span><span class="sxs-lookup"><span data-stu-id="25e8b-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="25e8b-195">相反，缓存项仅在存在内存压力时过期。</span><span class="sxs-lookup"><span data-stu-id="25e8b-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="25e8b-196">最佳做法是，应始终显式提供绝对或可调过期。</span><span class="sxs-lookup"><span data-stu-id="25e8b-196">As a best practice, you should always explicitly provide either an absolute or a sliding expiration.</span></span>

7. <span data-ttu-id="25e8b-197">在 `if/then` 块中并在上一步中添加的代码后面添加以下代码，以便为要监视的文件路径创建集合，并将文本文件的路径添加到集合中：</span><span class="sxs-lookup"><span data-stu-id="25e8b-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    > <span data-ttu-id="25e8b-198">如果要使用的文本文件不是 `c:\cache\cacheText.txt` ，请指定要使用的文本文件所在的路径。</span><span class="sxs-lookup"><span data-stu-id="25e8b-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>

8. <span data-ttu-id="25e8b-199">在上一步中添加的代码后面，添加以下代码以将新 <xref:System.Runtime.Caching.HostFileChangeMonitor> 对象添加到缓存项的更改监视器集合中：</span><span class="sxs-lookup"><span data-stu-id="25e8b-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     <span data-ttu-id="25e8b-200"><xref:System.Runtime.Caching.HostFileChangeMonitor>对象监视文本文件的路径，并在发生更改时通知缓存。</span><span class="sxs-lookup"><span data-stu-id="25e8b-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="25e8b-201">在此示例中，如果文件的内容发生更改，缓存项将过期。</span><span class="sxs-lookup"><span data-stu-id="25e8b-201">In this example, the cache entry will expire if the content of the file changes.</span></span>

9. <span data-ttu-id="25e8b-202">在上一步中添加的代码后面，添加以下代码以读取文本文件的内容：</span><span class="sxs-lookup"><span data-stu-id="25e8b-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     <span data-ttu-id="25e8b-203">添加了日期和时间戳，以便您能够查看缓存条目的过期时间。</span><span class="sxs-lookup"><span data-stu-id="25e8b-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>

10. <span data-ttu-id="25e8b-204">在上一步中添加的代码后面，添加以下代码，以将文件内容作为实例插入到缓存对象中 <xref:System.Runtime.Caching.CacheItem> ：</span><span class="sxs-lookup"><span data-stu-id="25e8b-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     <span data-ttu-id="25e8b-205">可以通过将 <xref:System.Runtime.Caching.CacheItemPolicy> 之前创建的对象作为参数传递来指定有关如何逐出缓存项的信息。</span><span class="sxs-lookup"><span data-stu-id="25e8b-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>

11. <span data-ttu-id="25e8b-206">在块的后面 `if/then` ，添加以下代码以在消息框中显示缓存的文件内容：</span><span class="sxs-lookup"><span data-stu-id="25e8b-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. <span data-ttu-id="25e8b-207">在 " **生成** " 菜单中，单击 " **生成 WPFCaching** " 以生成项目。</span><span class="sxs-lookup"><span data-stu-id="25e8b-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>

## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="25e8b-208">在 WPF 应用程序中测试缓存</span><span class="sxs-lookup"><span data-stu-id="25e8b-208">Testing Caching in the WPF Application</span></span>
 <span data-ttu-id="25e8b-209">现在可以测试此应用程序。</span><span class="sxs-lookup"><span data-stu-id="25e8b-209">You can now test the application.</span></span>

#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="25e8b-210">在 WPF 应用程序中测试缓存</span><span class="sxs-lookup"><span data-stu-id="25e8b-210">To test caching in the WPF application</span></span>

1. <span data-ttu-id="25e8b-211">按 Ctrl+F5 运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="25e8b-211">Press CTRL+F5 to run the application.</span></span>

     <span data-ttu-id="25e8b-212">`MainWindow`随即显示窗口。</span><span class="sxs-lookup"><span data-stu-id="25e8b-212">The `MainWindow` window is displayed.</span></span>

2. <span data-ttu-id="25e8b-213">单击 " **获取缓存**"。</span><span class="sxs-lookup"><span data-stu-id="25e8b-213">Click **Get Cache**.</span></span>

     <span data-ttu-id="25e8b-214">文本文件中的缓存内容显示在一个消息框中。</span><span class="sxs-lookup"><span data-stu-id="25e8b-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="25e8b-215">请注意该文件上的时间戳。</span><span class="sxs-lookup"><span data-stu-id="25e8b-215">Notice the timestamp on the file.</span></span>

3. <span data-ttu-id="25e8b-216">关闭消息框，然后再次单击 " **获取缓存** "。</span><span class="sxs-lookup"><span data-stu-id="25e8b-216">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="25e8b-217">时间戳未更改。</span><span class="sxs-lookup"><span data-stu-id="25e8b-217">The timestamp is unchanged.</span></span> <span data-ttu-id="25e8b-218">这表示显示缓存内容。</span><span class="sxs-lookup"><span data-stu-id="25e8b-218">This indicates the cached content is displayed.</span></span>

4. <span data-ttu-id="25e8b-219">等待10秒钟或更多，然后再次单击 " **获取缓存** "。</span><span class="sxs-lookup"><span data-stu-id="25e8b-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>

     <span data-ttu-id="25e8b-220">此时将显示新的时间戳。</span><span class="sxs-lookup"><span data-stu-id="25e8b-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="25e8b-221">这表示策略使缓存条目过期，并显示新的缓存内容。</span><span class="sxs-lookup"><span data-stu-id="25e8b-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>

5. <span data-ttu-id="25e8b-222">在文本编辑器中，打开您创建的文本文件。</span><span class="sxs-lookup"><span data-stu-id="25e8b-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="25e8b-223">不要进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="25e8b-223">Do not make any changes yet.</span></span>

6. <span data-ttu-id="25e8b-224">关闭消息框，然后再次单击 " **获取缓存** "。</span><span class="sxs-lookup"><span data-stu-id="25e8b-224">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="25e8b-225">再次注意时间戳。</span><span class="sxs-lookup"><span data-stu-id="25e8b-225">Notice the timestamp again.</span></span>

7. <span data-ttu-id="25e8b-226">对文本文件进行更改，然后保存该文件。</span><span class="sxs-lookup"><span data-stu-id="25e8b-226">Make a change to the text file and then save the file.</span></span>

8. <span data-ttu-id="25e8b-227">关闭消息框，然后再次单击 " **获取缓存** "。</span><span class="sxs-lookup"><span data-stu-id="25e8b-227">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="25e8b-228">此消息框包含文本文件中的更新内容和新的时间戳。</span><span class="sxs-lookup"><span data-stu-id="25e8b-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="25e8b-229">这表明在更改文件时，主机文件更改监视器会立即逐出缓存项，即使绝对超时期限尚未过期。</span><span class="sxs-lookup"><span data-stu-id="25e8b-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>

    > [!NOTE]
    > <span data-ttu-id="25e8b-230">你可以将逐出时间增加到20秒或更多，以允许更多的时间来对文件进行更改。</span><span class="sxs-lookup"><span data-stu-id="25e8b-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>

## <a name="code-example"></a><span data-ttu-id="25e8b-231">代码示例</span><span class="sxs-lookup"><span data-stu-id="25e8b-231">Code Example</span></span>
 <span data-ttu-id="25e8b-232">完成本演练后，你创建的项目的代码将与以下示例类似。</span><span class="sxs-lookup"><span data-stu-id="25e8b-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="25e8b-233">请参阅</span><span class="sxs-lookup"><span data-stu-id="25e8b-233">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [<span data-ttu-id="25e8b-234">.NET Framework 应用程序中的缓存</span><span class="sxs-lookup"><span data-stu-id="25e8b-234">Caching in .NET Framework Applications</span></span>](/dotnet/framework/performance/caching-in-net-framework-applications)
