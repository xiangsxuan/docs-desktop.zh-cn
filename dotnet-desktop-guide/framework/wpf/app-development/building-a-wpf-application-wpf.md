---
title: 编译应用
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF application [WPF], building
ms.assetid: a58696fd-bdad-4b55-9759-136dfdf8b91c
ms.openlocfilehash: 9cb7750eb719bfe30bde81548be0df6776c1acba
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667742"
---
# <a name="compile-a-wpf-application"></a><span data-ttu-id="1efb8-102">编译 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="1efb8-102">Compile a WPF Application</span></span>

<span data-ttu-id="1efb8-103">Windows Presentation Foundation (WPF) 应用程序可以生成为 .NET Framework 可执行文件 () 、库 () 或这两种类型的程序集的组合。</span><span class="sxs-lookup"><span data-stu-id="1efb8-103">Windows Presentation Foundation (WPF) applications can be built as .NET Framework executables (.exe), libraries (.dll), or a combination of both types of assemblies.</span></span> <span data-ttu-id="1efb8-104">本主题介绍如何构建 WPF 应用程序，并介绍生成过程中的关键步骤。</span><span class="sxs-lookup"><span data-stu-id="1efb8-104">This topic introduces how to build WPF applications and describes the key steps in the build process.</span></span>

<a name="Building_a_WPF_Application_using_Command_Line"></a>

## <a name="building-a-wpf-application"></a><span data-ttu-id="1efb8-105">生成 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="1efb8-105">Building a WPF Application</span></span>

<span data-ttu-id="1efb8-106">WPF 应用程序可通过以下方式编译：</span><span class="sxs-lookup"><span data-stu-id="1efb8-106">A WPF application can be compiled in the following ways:</span></span>

- <span data-ttu-id="1efb8-107">命令行。</span><span class="sxs-lookup"><span data-stu-id="1efb8-107">Command-line.</span></span> <span data-ttu-id="1efb8-108">应用程序必须只包含代码（并非 XAML）和一个应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="1efb8-108">The application must contain only code (no XAML) and an application definition file.</span></span> <span data-ttu-id="1efb8-109">有关详细信息，请参阅[在命令行上使用 csc.exe 生成](/dotnet/csharp/language-reference/compiler-options/command-line-building-with-csc-exe)或[从命令行生成 (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/building-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="1efb8-109">For more information, see [Command-line Building With csc.exe](/dotnet/csharp/language-reference/compiler-options/command-line-building-with-csc-exe) or [Building from the Command Line (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/building-from-the-command-line).</span></span>

- <span data-ttu-id="1efb8-110">Microsoft 生成引擎 (MSBuild)。</span><span class="sxs-lookup"><span data-stu-id="1efb8-110">Microsoft Build Engine (MSBuild).</span></span> <span data-ttu-id="1efb8-111">除了代码和 XAML 文件之外，应用程序还必须包含一个 MSBuild 项目文件。</span><span class="sxs-lookup"><span data-stu-id="1efb8-111">In addition to the code and XAML files, the application must contain an MSBuild project file.</span></span> <span data-ttu-id="1efb8-112">有关详细信息，请参阅“MSBuild”。</span><span class="sxs-lookup"><span data-stu-id="1efb8-112">For more information, see "MSBuild".</span></span>

- <span data-ttu-id="1efb8-113">Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="1efb8-113">Visual Studio.</span></span> <span data-ttu-id="1efb8-114">Visual Studio 是一个集成式开发环境，可编译使用 MSBuild 生成的 WPF 应用程序，并包含可用于创建 UI 的可视化设计器。</span><span class="sxs-lookup"><span data-stu-id="1efb8-114">Visual Studio is an integrated development environment that compiles WPF applications with MSBuild and includes a visual designer for creating UI.</span></span> <span data-ttu-id="1efb8-115">有关详细信息，请参阅 [使用 Visual Studio 编写和管理代码](/visualstudio/ide/index-writing-code) 和 [在 Visual STUDIO 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="1efb8-115">For more information, see [Write and manage code using Visual Studio](/visualstudio/ide/index-writing-code) and [Design XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).</span></span>

<a name="The_Windows_Presentation_Foundation_Build_Pipeline"></a>

## <a name="wpf-build-pipeline"></a><span data-ttu-id="1efb8-116">WPF 生成管道</span><span class="sxs-lookup"><span data-stu-id="1efb8-116">WPF Build Pipeline</span></span>

<span data-ttu-id="1efb8-117">生成 WPF 项目时，将调用语言特定目标和特定于 WPF 的目标的组合。</span><span class="sxs-lookup"><span data-stu-id="1efb8-117">When a WPF project is built, the combination of language-specific and WPF-specific targets are invoked.</span></span> <span data-ttu-id="1efb8-118">执行这些目标的进程被称为生成管道，相关的关键步骤已显示在下图中。</span><span class="sxs-lookup"><span data-stu-id="1efb8-118">The process of executing these targets is called the build pipeline, and the key steps are illustrated by the following figure.</span></span>

<span data-ttu-id="1efb8-119">![WPF 生成过程](./media/wpfbuildsystem-figure1.png "WPFBuildSystem_Figure1")</span><span class="sxs-lookup"><span data-stu-id="1efb8-119">![WPF build process](./media/wpfbuildsystem-figure1.png "WPFBuildSystem_Figure1")</span></span>

<a name="Pre_Build_Initializations"></a>

### <a name="pre-build-initializations"></a><span data-ttu-id="1efb8-120">预生成初始化</span><span class="sxs-lookup"><span data-stu-id="1efb8-120">Pre-Build Initializations</span></span>

<span data-ttu-id="1efb8-121">在生成之前，MSBuild 确定重要工具和库的位置，包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="1efb8-121">Before building, MSBuild determines the location of important tools and libraries, including the following:</span></span>

- <span data-ttu-id="1efb8-122">.NET Framework。</span><span class="sxs-lookup"><span data-stu-id="1efb8-122">The .NET Framework.</span></span>

- <span data-ttu-id="1efb8-123">Windows SDK 的目录。</span><span class="sxs-lookup"><span data-stu-id="1efb8-123">The Windows SDK directories.</span></span>

- <span data-ttu-id="1efb8-124">WPF 引用程序集的位置。</span><span class="sxs-lookup"><span data-stu-id="1efb8-124">The location of WPF reference assemblies.</span></span>

- <span data-ttu-id="1efb8-125">程序集搜索路径的属性。</span><span class="sxs-lookup"><span data-stu-id="1efb8-125">The property for the assembly search paths.</span></span>

<span data-ttu-id="1efb8-126">MSBuild 在其中搜索程序集的第一个位置是引用程序集目录 (%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.0 \\) 。</span><span class="sxs-lookup"><span data-stu-id="1efb8-126">The first location where MSBuild searches for assemblies is the reference assembly directory (%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.0\\).</span></span> <span data-ttu-id="1efb8-127">在执行这个步骤时，生成进程还会初始化各种属性和项组，并执行所有必要的清理工作。</span><span class="sxs-lookup"><span data-stu-id="1efb8-127">During this step, the build process also initializes the various properties and item groups and performs any required cleanup work.</span></span>

<a name="Resolving_references"></a>

### <a name="resolving-references"></a><span data-ttu-id="1efb8-128">解析引用</span><span class="sxs-lookup"><span data-stu-id="1efb8-128">Resolving References</span></span>

<span data-ttu-id="1efb8-129">生成进程会查找并绑定生成应用程序项目所需的程序集。</span><span class="sxs-lookup"><span data-stu-id="1efb8-129">The build process locates and binds the assemblies required to build the application project.</span></span> <span data-ttu-id="1efb8-130">这个逻辑包含在 `ResolveAssemblyReference` 任务中。</span><span class="sxs-lookup"><span data-stu-id="1efb8-130">This logic is contained in the `ResolveAssemblyReference` task.</span></span> <span data-ttu-id="1efb8-131">在项目文件中声明为 `Reference` 的所有程序集会连同有关搜索路径的信息以及系统上已安装的程序集的元数据一并提供给任务。</span><span class="sxs-lookup"><span data-stu-id="1efb8-131">All assemblies declared as `Reference` in the project file are provided to the task along with information on the search paths and metadata on assemblies already installed on the system.</span></span> <span data-ttu-id="1efb8-132">该任务将查找程序集，并使用已安装的程序集的元数据来筛选出那些不需要显示在输出清单中的核心 WPF 程序集。</span><span class="sxs-lookup"><span data-stu-id="1efb8-132">The task looks up assemblies and uses the installed assembly's metadata to filter out those core WPF assemblies that need not show up in the output manifests.</span></span> <span data-ttu-id="1efb8-133">这么做可以避免 ClickOnce 清单中出现冗余信息。</span><span class="sxs-lookup"><span data-stu-id="1efb8-133">This is done to avoid redundant information in the ClickOnce manifests.</span></span> <span data-ttu-id="1efb8-134">例如，由于可以将 PresentationFramework.dll 视为在和 WPF 上构建的应用程序的代表，并且由于所有 WPF 程序集都存在于安装了 .NET Framework 的每台计算机上的同一位置，因此无需在清单中包含所有 .NET Framework 引用程序集的所有信息。</span><span class="sxs-lookup"><span data-stu-id="1efb8-134">For example, since PresentationFramework.dll can be considered representative of an application built on and for WPF, and since all WPF assemblies exist at the same location on every machine that has the .NET Framework installed, there's no need to include all information on all .NET Framework reference assemblies in the manifests.</span></span>

<a name="Markup_Compilation___Pass_1"></a>

### <a name="markup-compilationpass-1"></a><span data-ttu-id="1efb8-135">标记编译 - 第 1 次传递</span><span class="sxs-lookup"><span data-stu-id="1efb8-135">Markup Compilation—Pass 1</span></span>

<span data-ttu-id="1efb8-136">在此步骤中， [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 将对文件进行分析和编译，使运行时不会花费时间分析 XML 和验证属性值。</span><span class="sxs-lookup"><span data-stu-id="1efb8-136">In this step, [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] files are parsed and compiled so that the runtime does not spend time parsing XML and validating property values.</span></span> <span data-ttu-id="1efb8-137">编译型 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 文件会进行预标记，因此其在运行时的加载速度应该要远高于 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 文件的加载速度。</span><span class="sxs-lookup"><span data-stu-id="1efb8-137">The compiled [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file is pre-tokenized so that, at run time, loading it should be much faster than loading a [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file.</span></span>

<span data-ttu-id="1efb8-138">这个步骤会针对属于 `Page` 生成项的每一个 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 文件完成以下活动：</span><span class="sxs-lookup"><span data-stu-id="1efb8-138">During this step, the following activities take place for every [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file that is a `Page` build item:</span></span>

1. <span data-ttu-id="1efb8-139">由标记编译器对 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 文件进行分析。</span><span class="sxs-lookup"><span data-stu-id="1efb8-139">The [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file is parsed by the markup compiler.</span></span>

2. <span data-ttu-id="1efb8-140">创建编译型 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 并将其复制到 obj\Release 文件夹。</span><span class="sxs-lookup"><span data-stu-id="1efb8-140">A compiled representation is created for that [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] and copied to the obj\Release folder.</span></span>

3. <span data-ttu-id="1efb8-141">创建 CodeDOM 型新分部类并将其复制到 obj\Release 文件夹。</span><span class="sxs-lookup"><span data-stu-id="1efb8-141">A CodeDOM representation of a new partial class is created and copied to the obj\Release folder.</span></span>

<span data-ttu-id="1efb8-142">另外，还会针对每一个 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 文件生成特定于语言的代码文件。</span><span class="sxs-lookup"><span data-stu-id="1efb8-142">In addition, a language-specific code file is generated for every [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="1efb8-143">例如，对于 Visual Basic 项目中的 Page1 页，生成了 Page1. g.;对于 c # 项目中的 Page1 页，生成一个 Page1. .cs。</span><span class="sxs-lookup"><span data-stu-id="1efb8-143">For example, for a Page1.xaml page in a Visual Basic project, a Page1.g.vb is generated; for a Page1.xaml page in a C# project, a Page1.g.cs is generated.</span></span> <span data-ttu-id="1efb8-144">文件名中的“.g”表明文件包含的是生成的代码，这些代码针对标记文件的顶级元素（如 `Page` 或 `Window`）进行了分部类声明。</span><span class="sxs-lookup"><span data-stu-id="1efb8-144">The ".g" in the file name indicates the file is generated code that has a partial class declaration for the top-level element of the markup file (such as `Page` or `Window`).</span></span> <span data-ttu-id="1efb8-145">此类是用 c # 中的修饰符声明的 `partial` `Extends` Visual Basic) 中 (，这种声明通常出现在代码隐藏文件中。</span><span class="sxs-lookup"><span data-stu-id="1efb8-145">The class is declared with the `partial` modifier in C# (`Extends` in Visual Basic) to indicate there is another declaration for the class elsewhere, usually in the code-behind file Page1.xaml.cs.</span></span>

<span data-ttu-id="1efb8-146">分部类从适当的基类进行扩展 (如 <xref:System.Windows.Controls.Page> 用于页面) 并实现 <xref:System.Windows.Markup.IComponentConnector?displayProperty=nameWithType> 接口。</span><span class="sxs-lookup"><span data-stu-id="1efb8-146">The partial class extends from the appropriate base class (such as <xref:System.Windows.Controls.Page> for a page) and implements the <xref:System.Windows.Markup.IComponentConnector?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="1efb8-147"><xref:System.Windows.Markup.IComponentConnector>接口包含用于初始化组件并连接其内容中元素上的名称和事件的方法。</span><span class="sxs-lookup"><span data-stu-id="1efb8-147">The <xref:System.Windows.Markup.IComponentConnector> interface has methods to initialize a component and connect names and events on elements in its content.</span></span> <span data-ttu-id="1efb8-148">因此，生成的代码文件中都包含如下所示的方法实现：</span><span class="sxs-lookup"><span data-stu-id="1efb8-148">Consequently, the generated code file has a method implementation like the following:</span></span>

```csharp
public void InitializeComponent() {
    if (_contentLoaded) {
        return;
    }
    _contentLoaded = true;
    System.Uri resourceLocater =
        new System.Uri(
            "window1.xaml",
            System.UriKind.RelativeOrAbsolute);
    System.Windows.Application.LoadComponent(this, resourceLocater);
}
```

```vb
Public Sub InitializeComponent() _

    If _contentLoaded Then
        Return
    End If

    _contentLoaded = True
    Dim resourceLocater As System.Uri = _
        New System.Uri("mainwindow.xaml", System.UriKind.Relative)

    System.Windows.Application.LoadComponent(Me, resourceLocater)

End Sub
```

<span data-ttu-id="1efb8-149">默认情况下，标记编译在与 MSBuild 引擎相同的情况下运行 <xref:System.AppDomain> 。</span><span class="sxs-lookup"><span data-stu-id="1efb8-149">By default, markup compilation runs in the same <xref:System.AppDomain> as the MSBuild engine.</span></span> <span data-ttu-id="1efb8-150">这可以显著提高性能。</span><span class="sxs-lookup"><span data-stu-id="1efb8-150">This provides significant performance gains.</span></span> <span data-ttu-id="1efb8-151">此行为可通过 `AlwaysCompileMarkupFilesInSeparateDomain` 属性来切换。</span><span class="sxs-lookup"><span data-stu-id="1efb8-151">This behavior can be toggled with the `AlwaysCompileMarkupFilesInSeparateDomain` property.</span></span> <span data-ttu-id="1efb8-152">此方法的优点是通过卸载单独的来卸载所有引用程序集 <xref:System.AppDomain> 。</span><span class="sxs-lookup"><span data-stu-id="1efb8-152">This has the advantage of unloading all reference assemblies by unloading the separate <xref:System.AppDomain>.</span></span>

<a name="Pass_2_of_Markup_Compilation"></a>

### <a name="markup-compilationpass-2"></a><span data-ttu-id="1efb8-153">标记编译 - 第 2 次传递</span><span class="sxs-lookup"><span data-stu-id="1efb8-153">Markup Compilation—Pass 2</span></span>

<span data-ttu-id="1efb8-154">并非所有 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 页面都会在标记编译的第 1 次传递过程中完成编译。</span><span class="sxs-lookup"><span data-stu-id="1efb8-154">Not all [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] pages are compiled at during pass 1 of markup compilation.</span></span> <span data-ttu-id="1efb8-155">包含本地定义类型引用（引用同一项目中其他位置的代码所定义的类型）的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 文件就不会在此期间进行编译。</span><span class="sxs-lookup"><span data-stu-id="1efb8-155">[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] files that have locally defined type references (references to types defined in code elsewhere in the same project) are exempt from compilation at this time.</span></span> <span data-ttu-id="1efb8-156">这是因为这些本地定义的类型仅存在于源中，并且尚未编译。</span><span class="sxs-lookup"><span data-stu-id="1efb8-156">This is because those locally defined types exist only in source and have not yet been compiled.</span></span> <span data-ttu-id="1efb8-157">分析器会采用试探法来确定文件是否已编译，而这一操作会涉及在标记文件中查找 `x:Name` 之类的项。</span><span class="sxs-lookup"><span data-stu-id="1efb8-157">In order to determine this, the parser uses heuristics that involve looking for items such as `x:Name` in the markup file.</span></span> <span data-ttu-id="1efb8-158">如果找到此类实例，标记文件的编译将会推迟，直至代码文件完成编译；在代码文件完成编译后，标记文件会在第二次标记编译传递期间得到处理。</span><span class="sxs-lookup"><span data-stu-id="1efb8-158">When such an instance is found, that markup file’s compilation is postponed until the code files have been compiled, after which, the second markup compilation pass processes these files.</span></span>

<a name="File_Classification"></a>

### <a name="file-classification"></a><span data-ttu-id="1efb8-159">文件分类</span><span class="sxs-lookup"><span data-stu-id="1efb8-159">File Classification</span></span>

<span data-ttu-id="1efb8-160">生成进程会根据输出文件将被置于哪个应用程序集中，将输出文件放入不同的资源组。</span><span class="sxs-lookup"><span data-stu-id="1efb8-160">The build process puts output files into different resource groups based on which application assembly they will be placed in.</span></span> <span data-ttu-id="1efb8-161">在典型的非本地化应用程序中，所有被标记为 `Resource` 的数据文件都会置于主程序集（可执行文件或库）中。</span><span class="sxs-lookup"><span data-stu-id="1efb8-161">In a typical nonlocalized application, all data files marked as `Resource` are placed in the main assembly (executable or library).</span></span> <span data-ttu-id="1efb8-162">如果在项目中设置了 `UICulture`，则所有编译型 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 文件以及那些专门标记为特定于语言的资源会置于附属资源程序集中。</span><span class="sxs-lookup"><span data-stu-id="1efb8-162">When `UICulture` is set in the project, all compiled [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] files and those resources specifically marked as language-specific are placed in the satellite resource assembly.</span></span> <span data-ttu-id="1efb8-163">此外，所有中性语言资源都会置于主程序集中。</span><span class="sxs-lookup"><span data-stu-id="1efb8-163">Furthermore, all language-neutral resources are placed in the main assembly.</span></span> <span data-ttu-id="1efb8-164">生成进程会在执行这个步骤时确定放置位置。</span><span class="sxs-lookup"><span data-stu-id="1efb8-164">In this step of the build process, that determination is made.</span></span>

<span data-ttu-id="1efb8-165">项目文件中的 `ApplicationDefinition`、`Page` 和 `Resource` 生成操作可以使用 `Localizable` 元数据（可接受的值为 `true` 和 `false`）来扩充，该元数据会指明文件是特定于语言的文件还是中性语言文件。</span><span class="sxs-lookup"><span data-stu-id="1efb8-165">The `ApplicationDefinition`, `Page`, and `Resource` build actions in the project file can be augmented with the `Localizable` metadata (acceptable values are `true` and `false`), which dictates whether the file is language-specific or language-neutral.</span></span>

<a name="Core_Compilation"></a>

### <a name="core-compilation"></a><span data-ttu-id="1efb8-166">内核编译</span><span class="sxs-lookup"><span data-stu-id="1efb8-166">Core Compilation</span></span>

<span data-ttu-id="1efb8-167">内核编译步骤涉及代码文件的编译。</span><span class="sxs-lookup"><span data-stu-id="1efb8-167">The core compile step involves compilation of code files.</span></span> <span data-ttu-id="1efb8-168">这要由特定于语言的目标文件 Microsoft.CSharp.targets 和 Microsoft.VisualBasic.targets 中的逻辑来协调。</span><span class="sxs-lookup"><span data-stu-id="1efb8-168">This is orchestrated by logic in the language-specific targets files Microsoft.CSharp.targets and Microsoft.VisualBasic.targets.</span></span> <span data-ttu-id="1efb8-169">如果试探法确定标记编译器只需要进行一次传递，则会生成主程序集。</span><span class="sxs-lookup"><span data-stu-id="1efb8-169">If heuristics have determined that a single pass of the markup compiler is sufficient, then the main assembly is generated.</span></span> <span data-ttu-id="1efb8-170">但是，如果项目中的一个或多个 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 文件引用了本地定义的类型，则会生成一个临时的.dll 文件，最终的应用程序集则可能会在标记编译的第二次传递完成后再创建。</span><span class="sxs-lookup"><span data-stu-id="1efb8-170">However, if one or more [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] files in the project have references to locally defined types, then a temporary .dll file is generated so the final application assemblies may be created after the second pass of markup compilation is complete.</span></span>

<a name="Manifest_generation"></a>

### <a name="manifest-generation"></a><span data-ttu-id="1efb8-171">清单生成</span><span class="sxs-lookup"><span data-stu-id="1efb8-171">Manifest Generation</span></span>

<span data-ttu-id="1efb8-172">在生成过程结束时，所有应用程序程序集和内容文件都准备就绪后，将生成应用程序的 ClickOnce 清单。</span><span class="sxs-lookup"><span data-stu-id="1efb8-172">At the end of the build process, after all the application assemblies and content files are ready, the ClickOnce manifests for the application are generated.</span></span>

<span data-ttu-id="1efb8-173">部署清单文件可描述部署模型：当前版本、更新行为、发布服务器标识以及数字签名。</span><span class="sxs-lookup"><span data-stu-id="1efb8-173">The deployment manifest file describes the deployment model: the current version, update behavior, and publisher identity along with digital signature.</span></span> <span data-ttu-id="1efb8-174">该清单应由负责处理部署的管理员来编写。</span><span class="sxs-lookup"><span data-stu-id="1efb8-174">This manifest is intended to be authored by administrators who handle deployment.</span></span> <span data-ttu-id="1efb8-175">文件扩展名为 XAML 浏览器应用程序的 xbap ( (Xbap) ) 和应用程序的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1efb8-175">The file extension is .xbap (for XAML browser applications (XBAPs)) and .application for installed applications.</span></span> <span data-ttu-id="1efb8-176">前者受 `HostInBrowser` 项目属性支配，因此清单会将应用程序标识为由浏览器承载。</span><span class="sxs-lookup"><span data-stu-id="1efb8-176">The former is dictated by the `HostInBrowser` project property and as a result the manifest identifies the application as browser-hosted.</span></span>

<span data-ttu-id="1efb8-177">应用程序清单（一个 .exe.manifest 文件）可描述应用程序集和依赖库，并列出应用程序所需的权限。</span><span class="sxs-lookup"><span data-stu-id="1efb8-177">The application manifest (an .exe.manifest file) describes the application assemblies and dependent libraries and lists permissions required by the application.</span></span> <span data-ttu-id="1efb8-178">该文件应由应用程序开发者编写。</span><span class="sxs-lookup"><span data-stu-id="1efb8-178">This file is intended to be authored by the application developer.</span></span> <span data-ttu-id="1efb8-179">为了启动 ClickOnce 应用程序，用户将打开该应用程序的部署清单文件。</span><span class="sxs-lookup"><span data-stu-id="1efb8-179">In order to launch a ClickOnce application, a user opens the application's deployment manifest file.</span></span>

<span data-ttu-id="1efb8-180">这些清单文件始终为 Xbap 创建。</span><span class="sxs-lookup"><span data-stu-id="1efb8-180">These manifest files are always created for XBAPs.</span></span> <span data-ttu-id="1efb8-181">对于已安装的应用程序，这些文件不会创建，除非在项目文件中为 `GenerateManifests` 属性指定值 `true`。</span><span class="sxs-lookup"><span data-stu-id="1efb8-181">For installed applications, they are not created unless the `GenerateManifests` property is specified in the project file with value `true`.</span></span>

<span data-ttu-id="1efb8-182">Xbap 在分配给典型 Internet 区域应用程序的权限（和更高版本）上获取另外两个权限： <xref:System.Security.Permissions.WebBrowserPermission> 和 <xref:System.Security.Permissions.MediaPermission> 。</span><span class="sxs-lookup"><span data-stu-id="1efb8-182">XBAPs get two additional permissions over and above those permissions assigned to typical Internet zone applications: <xref:System.Security.Permissions.WebBrowserPermission> and <xref:System.Security.Permissions.MediaPermission>.</span></span> <span data-ttu-id="1efb8-183">WPF 生成系统会在应用程序清单中声明这些权限。</span><span class="sxs-lookup"><span data-stu-id="1efb8-183">The WPF build system declares those permissions in the application manifest.</span></span>

<a name="Incremental_Build_Support"></a>

## <a name="incremental-build-support"></a><span data-ttu-id="1efb8-184">增量生成支持</span><span class="sxs-lookup"><span data-stu-id="1efb8-184">Incremental Build Support</span></span>

<span data-ttu-id="1efb8-185">WPF 生成系统为增量生成提供支持。</span><span class="sxs-lookup"><span data-stu-id="1efb8-185">The WPF build system provides support for incremental builds.</span></span> <span data-ttu-id="1efb8-186">该系统能以非常智能化的方式来检测对标记或代码所做的各种更改，而且只会编译那些受到更改操作影响的项目。</span><span class="sxs-lookup"><span data-stu-id="1efb8-186">It is fairly intelligent about detecting changes made to markup or code, and it compiles only those artifacts affected by the change.</span></span> <span data-ttu-id="1efb8-187">增量生成机制会使用以下文件：</span><span class="sxs-lookup"><span data-stu-id="1efb8-187">The incremental build mechanism uses the following files:</span></span>

- <span data-ttu-id="1efb8-188">$(*AssemblyName*)_MarkupCompiler.Cache 文件，用于维护当前的编译器状态。</span><span class="sxs-lookup"><span data-stu-id="1efb8-188">An $(*AssemblyName*)_MarkupCompiler.Cache file to maintain current compiler state.</span></span>

- <span data-ttu-id="1efb8-189">$(*AssemblyName*)_MarkupCompiler.lref 文件，用于缓存引用了本地定义类型的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 文件。</span><span class="sxs-lookup"><span data-stu-id="1efb8-189">An $(*AssemblyName*)_MarkupCompiler.lref file to cache the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] files with references to locally defined types.</span></span>

<span data-ttu-id="1efb8-190">下面显示了一组用于控制增量生成的规则：</span><span class="sxs-lookup"><span data-stu-id="1efb8-190">The following is a set of rules governing incremental build:</span></span>

- <span data-ttu-id="1efb8-191">文件是生成系统检测更改时的最小单位。</span><span class="sxs-lookup"><span data-stu-id="1efb8-191">The file is the smallest unit at which the build system detects change.</span></span> <span data-ttu-id="1efb8-192">因此，对于代码文件，生成系统无法判断类型是否已更改或者是否添加了代码。</span><span class="sxs-lookup"><span data-stu-id="1efb8-192">So, for a code file, the build system cannot tell if a type was changed or if code was added.</span></span> <span data-ttu-id="1efb8-193">对于项目文件也是如此。</span><span class="sxs-lookup"><span data-stu-id="1efb8-193">The same holds for project files.</span></span>

- <span data-ttu-id="1efb8-194">增量生成机制必须确定 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 页面是定义了一个类，还是使用了其他类。</span><span class="sxs-lookup"><span data-stu-id="1efb8-194">The incremental build mechanism must be cognizant that a [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] page either defines a class or uses other classes.</span></span>

- <span data-ttu-id="1efb8-195">如果 `Reference` 条目发生变化，则会重新编译所有页面。</span><span class="sxs-lookup"><span data-stu-id="1efb8-195">If `Reference` entries change, then recompile all pages.</span></span>

- <span data-ttu-id="1efb8-196">如果代码文件发生变化，则会重新编译引用了本地定义类型的所有页面。</span><span class="sxs-lookup"><span data-stu-id="1efb8-196">If a code file changes, recompile all pages with locally defined type references.</span></span>

- <span data-ttu-id="1efb8-197">如果 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 文件发生变化：</span><span class="sxs-lookup"><span data-stu-id="1efb8-197">If a [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file changes:</span></span>

  - <span data-ttu-id="1efb8-198">如果 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 在项目中被声明为 `Page`：如果 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 没有引用本地定义的类型，则会重新编译 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 以及包含本地引用的所有 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 页面；如果 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 包含本地引用，则会重新编译包含本地引用的所有 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 页面。</span><span class="sxs-lookup"><span data-stu-id="1efb8-198">If [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] is declared as `Page` in the project: if the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] does not have locally defined type references, recompile that [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] plus all [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] pages with local references; if the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] has local references, recompile all [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] pages with local references.</span></span>

  - <span data-ttu-id="1efb8-199">如果 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 在项目中声明为，则 `ApplicationDefinition` 重新编译所有 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 页面 (原因：每个页面 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 都引用了 <xref:System.Windows.Application> 可能已更改) 的类型。</span><span class="sxs-lookup"><span data-stu-id="1efb8-199">If [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] is declared as `ApplicationDefinition` in the project: recompile all [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] pages (reason: each [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] has reference to an <xref:System.Windows.Application> type that may have changed).</span></span>

- <span data-ttu-id="1efb8-200">如果项目文件将代码文件声明为应用程序定义，而不是 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 文件：</span><span class="sxs-lookup"><span data-stu-id="1efb8-200">If the project file declares a code file as application definition instead of a [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file:</span></span>

  - <span data-ttu-id="1efb8-201">检查项目文件中的 `ApplicationClassName` 值是不是发生了变化（是不是有新的应用程序类型？）。</span><span class="sxs-lookup"><span data-stu-id="1efb8-201">Check if the `ApplicationClassName` value in the project file has changed (is there a new application type?).</span></span> <span data-ttu-id="1efb8-202">如果是，则重新编译整个应用程序。</span><span class="sxs-lookup"><span data-stu-id="1efb8-202">If so, recompile the entire application.</span></span>

  - <span data-ttu-id="1efb8-203">否则，重新编译包含本地引用的所有 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 页面。</span><span class="sxs-lookup"><span data-stu-id="1efb8-203">Otherwise, recompile all [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] pages with local references.</span></span>

- <span data-ttu-id="1efb8-204">如果项目文件发生变化：应用前面的所有规则，并确认哪些内容需要重新编译。</span><span class="sxs-lookup"><span data-stu-id="1efb8-204">If a project file changes: apply all preceding rules and see what needs to be recompiled.</span></span> <span data-ttu-id="1efb8-205">以下属性发生变化会触发全面的重新编译：`AssemblyName`、`IntermediateOutputPath`、`RootNamespace` 和 `HostInBrowser`。</span><span class="sxs-lookup"><span data-stu-id="1efb8-205">Changes to the following properties trigger a complete recompile: `AssemblyName`, `IntermediateOutputPath`, `RootNamespace`, and `HostInBrowser`.</span></span>

<span data-ttu-id="1efb8-206">可能会出现以下重新编译情形：</span><span class="sxs-lookup"><span data-stu-id="1efb8-206">The following recompile scenarios are possible:</span></span>

- <span data-ttu-id="1efb8-207">重新编译整个应用程序。</span><span class="sxs-lookup"><span data-stu-id="1efb8-207">The entire application is recompiled.</span></span>

- <span data-ttu-id="1efb8-208">仅重新编译那些引用了本地定义类型的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 文件。</span><span class="sxs-lookup"><span data-stu-id="1efb8-208">Only those [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] files that have locally defined type references are recompiled.</span></span>

- <span data-ttu-id="1efb8-209">不会重新编译任何内容（如果项目未发生任何变化）。</span><span class="sxs-lookup"><span data-stu-id="1efb8-209">Nothing is recompiled (if nothing in the project has changed).</span></span>

## <a name="see-also"></a><span data-ttu-id="1efb8-210">请参阅</span><span class="sxs-lookup"><span data-stu-id="1efb8-210">See also</span></span>

- [<span data-ttu-id="1efb8-211">部署 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="1efb8-211">Deploying a WPF Application</span></span>](deploying-a-wpf-application-wpf.md)
- [<span data-ttu-id="1efb8-212">WPF MSBuild 参考</span><span class="sxs-lookup"><span data-stu-id="1efb8-212">WPF MSBuild Reference</span></span>](/visualstudio/msbuild/wpf-msbuild-reference)
- [<span data-ttu-id="1efb8-213">WPF 中的 Pack URI</span><span class="sxs-lookup"><span data-stu-id="1efb8-213">Pack URIs in WPF</span></span>](pack-uris-in-wpf.md)
- [<span data-ttu-id="1efb8-214">WPF 应用程序资源、内容和数据文件</span><span class="sxs-lookup"><span data-stu-id="1efb8-214">WPF Application Resource, Content, and Data Files</span></span>](wpf-application-resource-content-and-data-files.md)
