---
title: 将 Windows 窗体应用迁移到 .NET 5
description: 了解如何将 .NET Framework Windows 窗体应用程序移植到 .NET 5。
ms.date: 11/02/2020
ms.topic: how-to
ms.openlocfilehash: adf87df169217a5d190338bf9c4beaec873f0b69
ms.sourcegitcommit: d7d89e96c827b6e20d9353d34c0aa329fdae0144
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506706"
---
# <a name="how-to-migrate-a-windows-forms-desktop-app-to-net-5"></a><span data-ttu-id="dbab3-103">如何将 Windows 窗体桌面应用迁移到 .NET 5</span><span class="sxs-lookup"><span data-stu-id="dbab3-103">How to migrate a Windows Forms desktop app to .NET 5</span></span>

<span data-ttu-id="dbab3-104">本文介绍如何将 Windows 窗体桌面应用从 .NET Framework 迁移到 .NET 5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="dbab3-104">This article describes how to migrate a Windows Forms desktop app from .NET Framework to .NET 5 or later.</span></span> <span data-ttu-id="dbab3-105">.NET SDK 支持 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="dbab3-105">The .NET SDK includes support for Windows Forms applications.</span></span> <span data-ttu-id="dbab3-106">Windows 窗体仍是仅适用于 Windows 的框架，并且只能在 Windows 上运行。</span><span class="sxs-lookup"><span data-stu-id="dbab3-106">Windows Forms is still a Windows-only framework and only runs on Windows.</span></span>

<span data-ttu-id="dbab3-107">将应用从 .NET Framework 迁移到 .NET 5 通常需要一个新的项目文件。</span><span class="sxs-lookup"><span data-stu-id="dbab3-107">Migrating your app from .NET Framework to .NET 5 generally requires a new project file.</span></span> <span data-ttu-id="dbab3-108">NET 5 使用 SDK 样式的项目文件，而 .NET Framework 通常使用较旧的 Visual Studio 项目文件。</span><span class="sxs-lookup"><span data-stu-id="dbab3-108">.NET 5 uses SDK-style project files while .NET Framework typically uses the older Visual Studio project file.</span></span> <span data-ttu-id="dbab3-109">如果你曾经在文本编辑器中打开过 Visual Studio 项目文件，你就会知道它有多么详细。</span><span class="sxs-lookup"><span data-stu-id="dbab3-109">If you've ever opened a Visual Studio project file in a text editor, you know how verbose it is.</span></span> <span data-ttu-id="dbab3-110">SDK 样式的项目较小，不需要像旧版项目文件格式那样多的条目。</span><span class="sxs-lookup"><span data-stu-id="dbab3-110">SDK-style projects are smaller and don't require as many entries as the older project file format does.</span></span>

<span data-ttu-id="dbab3-111">要详细了解 .NET 5，请参阅 [.NET 简介](/dotnet/core/introduction)。</span><span class="sxs-lookup"><span data-stu-id="dbab3-111">To learn more about .NET 5, see [Introduction to .NET](/dotnet/core/introduction).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dbab3-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="dbab3-112">Prerequisites</span></span>

- [<span data-ttu-id="dbab3-113">Visual Studio 2019 版本 16.8 预览版</span><span class="sxs-lookup"><span data-stu-id="dbab3-113">Visual Studio 2019 version 16.8 Preview</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms)

  - <span data-ttu-id="dbab3-114">选择 [Visual Studio Desktop 工作负载](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)。</span><span class="sxs-lookup"><span data-stu-id="dbab3-114">Select the [Visual Studio Desktop workload](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads).</span></span>

  - <span data-ttu-id="dbab3-115">选择 [.NET 5 单个组件](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)。</span><span class="sxs-lookup"><span data-stu-id="dbab3-115">Select the [.NET 5 individual component](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components).</span></span>

- <span data-ttu-id="dbab3-116">预览 Visual Studio 中的 WinForms 设计器。</span><span class="sxs-lookup"><span data-stu-id="dbab3-116">Preview WinForms designer in Visual Studio.</span></span>

  <span data-ttu-id="dbab3-117">若要启用该设计器，请转到“工具” > “选项” > “环境” > “预览功能”，然后选择“将预览版 Windows 窗体设计器用于 .NET Core 应用”选项。</span><span class="sxs-lookup"><span data-stu-id="dbab3-117">To enable the designer, go to **Tools** > **Options** > **Environment** > **Preview Features** and select the **Use the preview Windows Forms designer for .NET Core apps** option.</span></span>

- <span data-ttu-id="dbab3-118">本文使用[匹配游戏](https://github.com/dotnet/samples/tree/master/windowsforms/matching-game/net45/)示例应用。</span><span class="sxs-lookup"><span data-stu-id="dbab3-118">This article uses the [Matching game](https://github.com/dotnet/samples/tree/master/windowsforms/matching-game/net45/) sample app.</span></span> <span data-ttu-id="dbab3-119">若想使用该示例应用进行操作，请下载该应用程序并在 Visual Studio 中将其打开。</span><span class="sxs-lookup"><span data-stu-id="dbab3-119">If you want to follow along, download and open the application in Visual Studio.</span></span> <span data-ttu-id="dbab3-120">否则，请使用自己的应用。</span><span class="sxs-lookup"><span data-stu-id="dbab3-120">Otherwise, use your own app.</span></span>

### <a name="consider"></a><span data-ttu-id="dbab3-121">考虑</span><span class="sxs-lookup"><span data-stu-id="dbab3-121">Consider</span></span>

<span data-ttu-id="dbab3-122">迁移 .NET Framework Windows 窗体应用程序时，必须考虑以下几个事项。</span><span class="sxs-lookup"><span data-stu-id="dbab3-122">When migrating a .NET Framework Windows Forms application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="dbab3-123">检查应用程序是否适合迁移。</span><span class="sxs-lookup"><span data-stu-id="dbab3-123">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="dbab3-124">使用 [.NET 可移植性分析器](/dotnet/standard/analyzers/portability-analyzer)确定项目将会迁移到 .NET 5。</span><span class="sxs-lookup"><span data-stu-id="dbab3-124">Use the [.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer) to determine if your project will migrate to .NET 5.</span></span> <span data-ttu-id="dbab3-125">如果项目存在 .NET 5 相关问题，分析器可帮助你识别这些问题。</span><span class="sxs-lookup"><span data-stu-id="dbab3-125">If your project has issues with .NET 5, the analyzer helps you identify those problems.</span></span> <span data-ttu-id="dbab3-126">.NET 可移植性分析器工具可安装为 Visual Studio 扩展，也可在命令行中使用。</span><span class="sxs-lookup"><span data-stu-id="dbab3-126">The .NET Portability Analyzer tool can be installed as a Visual Studio extension or used from the command line.</span></span> <span data-ttu-id="dbab3-127">有关详细信息，请参阅 [.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer)。</span><span class="sxs-lookup"><span data-stu-id="dbab3-127">For more information, see [.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer).</span></span>

01. <span data-ttu-id="dbab3-128">使用的是不同版本的 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="dbab3-128">You're using a different version of Windows Forms.</span></span>

    <span data-ttu-id="dbab3-129">发布 .NET Core 3.0 时，Windows 窗体[在 GitHub 上开放源代码](https://github.com/dotnet/winforms)。</span><span class="sxs-lookup"><span data-stu-id="dbab3-129">When .NET Core 3.0 was released, Windows Forms went [open source on GitHub](https://github.com/dotnet/winforms).</span></span> <span data-ttu-id="dbab3-130">.NET 5 的 Windows 窗体的代码是 .NET Framework Windows 窗体代码库的一个分支。</span><span class="sxs-lookup"><span data-stu-id="dbab3-130">The code for Windows Forms for .NET 5 is a fork of the .NET Framework Windows Forms codebase.</span></span> <span data-ttu-id="dbab3-131">可能存在一些差异导致应用难以迁移。</span><span class="sxs-lookup"><span data-stu-id="dbab3-131">It's possible some differences exist and your app will be difficult to migrate.</span></span>

01. <span data-ttu-id="dbab3-132">使用 [Windows 兼容包][compat-pack]可有助于进行迁移。</span><span class="sxs-lookup"><span data-stu-id="dbab3-132">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="dbab3-133">某些 API 可在 .NET Framework 中使用，但不可用于 .NET 5。</span><span class="sxs-lookup"><span data-stu-id="dbab3-133">Some APIs that are available in .NET Framework aren't available in .NET 5.</span></span> <span data-ttu-id="dbab3-134">[Windows 兼容包][compat-pack]增加了很多这些 API，有助于使 Windows 窗体应用与 .NET 5 兼容。</span><span class="sxs-lookup"><span data-stu-id="dbab3-134">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your Windows Forms app become compatible with .NET 5.</span></span>

01. <span data-ttu-id="dbab3-135">更新项目使用的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="dbab3-135">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="dbab3-136">在执行任何迁移之前使用最新版 NuGet 包始终是一个不错的做法。</span><span class="sxs-lookup"><span data-stu-id="dbab3-136">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="dbab3-137">如果应用程序引用任何 NuGet 包，请将它们更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="dbab3-137">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="dbab3-138">确保成功生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="dbab3-138">Ensure your application builds successfully.</span></span> <span data-ttu-id="dbab3-139">升级后，如果存在任何包错误，请将包降级到不会破坏代码的最新版本。</span><span class="sxs-lookup"><span data-stu-id="dbab3-139">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

## <a name="back-up-your-projects"></a><span data-ttu-id="dbab3-140">备份项目</span><span class="sxs-lookup"><span data-stu-id="dbab3-140">Back up your projects</span></span>

<span data-ttu-id="dbab3-141">迁移项目的第一步是备份项目！</span><span class="sxs-lookup"><span data-stu-id="dbab3-141">The first step to migrating a project is to back up your project!</span></span> <span data-ttu-id="dbab3-142">如果出现问题，可以通过还原备份将代码还原为其原始状态。</span><span class="sxs-lookup"><span data-stu-id="dbab3-142">If something goes wrong, you can restore your code to its original state by restoring your backup.</span></span> <span data-ttu-id="dbab3-143">不要依赖于 .NET 可移植性分析器等工具来备份项目，即使它们似乎可以完成备份。</span><span class="sxs-lookup"><span data-stu-id="dbab3-143">Don't rely on tools such as the .NET Portability Analyzer to back up your project, even if they seem to.</span></span> <span data-ttu-id="dbab3-144">最好是亲自创建原始项目的副本。</span><span class="sxs-lookup"><span data-stu-id="dbab3-144">It's best to personally create a copy of the original project.</span></span>

## <a name="nuget-packages"></a><span data-ttu-id="dbab3-145">NuGet 包</span><span class="sxs-lookup"><span data-stu-id="dbab3-145">NuGet packages</span></span>

<span data-ttu-id="dbab3-146">如果项目引用了 NuGet 包，则项目文件夹中可能包含 packages.config 文件。</span><span class="sxs-lookup"><span data-stu-id="dbab3-146">If your project is referencing NuGet packages, you probably have a **packages.config** file in your project folder.</span></span> <span data-ttu-id="dbab3-147">对于 SDK 样式的项目，NuGet 包引用是在项目文件中配置的。</span><span class="sxs-lookup"><span data-stu-id="dbab3-147">With SDK-style projects, NuGet package references are configured in the project file.</span></span> <span data-ttu-id="dbab3-148">Visual Studio 项目文件也可以选择在项目文件中定义 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="dbab3-148">Visual Studio project files can optionally define NuGet packages in the project file too.</span></span> <span data-ttu-id="dbab3-149">.NET 5 不会将 packages.config 用于 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="dbab3-149">.NET 5 doesn't use **packages.config** for NuGet packages.</span></span> <span data-ttu-id="dbab3-150">在迁移之前，必须将 NuGet 包引用迁移到项目文件中。</span><span class="sxs-lookup"><span data-stu-id="dbab3-150">NuGet package references must be migrated into the project file before migration.</span></span>

<span data-ttu-id="dbab3-151">要迁移 packages.config 文件，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="dbab3-151">To migrate the **packages.config** file, do the following steps:</span></span>

01. <span data-ttu-id="dbab3-152">在“解决方案资源管理器”中，找到要迁移的项目。</span><span class="sxs-lookup"><span data-stu-id="dbab3-152">In **Solution explorer**, find the project you're migrating.</span></span>
02. <span data-ttu-id="dbab3-153">右键单击“packages.config” > “将 packages.config 迁移到 PackageReference”。</span><span class="sxs-lookup"><span data-stu-id="dbab3-153">Right-click on **packages.config** > **Migrate packages.config to PackageReference**.</span></span>
03. <span data-ttu-id="dbab3-154">选择所有顶级包。</span><span class="sxs-lookup"><span data-stu-id="dbab3-154">Select all of the top-level packages.</span></span>

<span data-ttu-id="dbab3-155">系统会生成一个生成报告，让你知道与迁移 NuGet 包有关的任何问题。</span><span class="sxs-lookup"><span data-stu-id="dbab3-155">A build report is generated to let you know of any issues migrating the NuGet packages.</span></span>

## <a name="project-file"></a><span data-ttu-id="dbab3-156">项目文件</span><span class="sxs-lookup"><span data-stu-id="dbab3-156">Project file</span></span>

<span data-ttu-id="dbab3-157">迁移应用的下一步是转换项目文件。</span><span class="sxs-lookup"><span data-stu-id="dbab3-157">The next step in migrating your app is converting the project file.</span></span> <span data-ttu-id="dbab3-158">如前文所述，NET 5 使用 SDK 样式的项目文件，不会加载 .NET Framework 使用的 Visual Studio 项目文件。</span><span class="sxs-lookup"><span data-stu-id="dbab3-158">As previously stated, .NET 5 uses SDK-style project files and won't load the Visual Studio project files that .NET Framework uses.</span></span> <span data-ttu-id="dbab3-159">但是，你可能已经在使用 SDK 样式的项目。</span><span class="sxs-lookup"><span data-stu-id="dbab3-159">However, there's the possibility that you're already using SDK-style projects.</span></span> <span data-ttu-id="dbab3-160">你可以轻松地在 Visual Studio 中发现差异。</span><span class="sxs-lookup"><span data-stu-id="dbab3-160">You can easily spot the difference in Visual Studio.</span></span> <span data-ttu-id="dbab3-161">在“解决方案资源管理器”中右键单击项目文件，查找“编辑项目文件”菜单选项 。</span><span class="sxs-lookup"><span data-stu-id="dbab3-161">Right-click on the project file in **Solution explorer** and look for the **Edit Project File** menu option.</span></span> <span data-ttu-id="dbab3-162">如果此菜单项缺失，则你使用的是旧版 Visual Studio 项目格式，需要升级。</span><span class="sxs-lookup"><span data-stu-id="dbab3-162">If this menu item is missing, you're using the old Visual Studio project format and need to upgrade.</span></span>

<span data-ttu-id="dbab3-163">转换解决方案中的每个项目。</span><span class="sxs-lookup"><span data-stu-id="dbab3-163">Convert each project in your solution.</span></span> <span data-ttu-id="dbab3-164">如果你使用的是之前引用的示例应用，则会转换 MatchingGame 和 MatchingGame.Logic 项目 。</span><span class="sxs-lookup"><span data-stu-id="dbab3-164">If you're using the sample app previously referenced, both the **MatchingGame** and **MatchingGame.Logic** projects would be converted.</span></span>

<span data-ttu-id="dbab3-165">要转换项目，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="dbab3-165">To convert a project, do the following steps:</span></span>

01. <span data-ttu-id="dbab3-166">在“解决方案资源管理器”中，找到要迁移的项目。</span><span class="sxs-lookup"><span data-stu-id="dbab3-166">In **Solution explorer**, find the project you're migrating.</span></span>
01. <span data-ttu-id="dbab3-167">右键单击项目，并选择“上传项目”。</span><span class="sxs-lookup"><span data-stu-id="dbab3-167">Right-click on the project and select **Unload Project**.</span></span>
01. <span data-ttu-id="dbab3-168">右键单击项目，并选择“编辑项目文件”。</span><span class="sxs-lookup"><span data-stu-id="dbab3-168">Right-click on the project and select **Edit Project File**.</span></span>
01. <span data-ttu-id="dbab3-169">复制项目 XML 并将其粘贴到文本编辑器中。</span><span class="sxs-lookup"><span data-stu-id="dbab3-169">Copy-and-paste the project XML into a text editor.</span></span> <span data-ttu-id="dbab3-170">你需要一个副本，以便轻松地将内容移动到新项目中。</span><span class="sxs-lookup"><span data-stu-id="dbab3-170">You'll want a copy so that it's easy to move content into the new project.</span></span>
01. <span data-ttu-id="dbab3-171">擦除文件的内容，并粘贴以下 XML：</span><span class="sxs-lookup"><span data-stu-id="dbab3-171">Erase the content of the file and paste the following XML:</span></span>

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">

      <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>net5.0-windows</TargetFramework>
        <UseWindowsForms>true</UseWindowsForms>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
      </PropertyGroup>

    </Project>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="dbab3-172">库不需要定义 `<OutputType>` 设置。</span><span class="sxs-lookup"><span data-stu-id="dbab3-172">Libraries don't need to define an `<OutputType>` setting.</span></span> <span data-ttu-id="dbab3-173">如果要升级库项目，请删除该条目。</span><span class="sxs-lookup"><span data-stu-id="dbab3-173">Remove that entry if you're upgrading a library project.</span></span>

<span data-ttu-id="dbab3-174">此 XML 提供项目的基本结构。</span><span class="sxs-lookup"><span data-stu-id="dbab3-174">This XML gives you the basic structure of the project.</span></span> <span data-ttu-id="dbab3-175">但是，它不包含旧项目文件中的任何设置。</span><span class="sxs-lookup"><span data-stu-id="dbab3-175">However, it doesn't contain any of the settings from the old project file.</span></span> <span data-ttu-id="dbab3-176">使用之前复制到文本编辑器的旧项目信息执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="dbab3-176">Using the old project information you previously copied to a text editor, do the following steps:</span></span>

01. <span data-ttu-id="dbab3-177">将以下元素从旧项目文件复制到新项目文件的 `<PropertyGroup>` 元素中：</span><span class="sxs-lookup"><span data-stu-id="dbab3-177">Copy the following elements from the old project file into the `<PropertyGroup>` element in the new project file:</span></span>

    - `<RootNamespace>`
    - `<AssemblyName>`

    <span data-ttu-id="dbab3-178">你的项目文件应类似于以下 XML：</span><span class="sxs-lookup"><span data-stu-id="dbab3-178">Your project file should look similar to the following XML:</span></span>

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">

      <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>net5.0-windows</TargetFramework>
        <UseWindowsForms>true</UseWindowsForms>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>

        <RootNamespace>MatchingGame</RootNamespace>
        <AssemblyName>MatchingGame</AssemblyName>
      </PropertyGroup>

    </Project>
    ```

01. <span data-ttu-id="dbab3-179">将 `<ItemGroup>` 元素从包含 `<ProjectReference>` 或 `<PackageReference>` 的旧项目文件复制到 `</PropertyGroup>` 结束标记之后的新文件中。</span><span class="sxs-lookup"><span data-stu-id="dbab3-179">Copy the `<ItemGroup>` elements from the old project file that contain `<ProjectReference>` or `<PackageReference>` into the new file after the `</PropertyGroup>` closing tag.</span></span>

    <span data-ttu-id="dbab3-180">你的项目文件应类似于以下 XML：</span><span class="sxs-lookup"><span data-stu-id="dbab3-180">Your project file should look similar to the following XML:</span></span>

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">

      <PropertyGroup>
        (contains settings previously described)
      </PropertyGroup>

      <ItemGroup>
        <ProjectReference Include="..\MatchingGame.Logic\MatchingGame.Logic.csproj">
          <Project>{36b3e6e2-a9ae-4924-89ae-7f0120ce08bd}</Project>
          <Name>MatchingGame.Logic</Name>
        </ProjectReference>
      </ItemGroup>
      <ItemGroup>
        <PackageReference Include="MetroFramework">
          <Version>1.2.0.3</Version>
        </PackageReference>
      </ItemGroup>

    </Project>
    ```

    <span data-ttu-id="dbab3-181">`<ProjectReference>` 元素不需要 `<Project>` 和 `<Name>` 子级，因此你可以删除这些设置：</span><span class="sxs-lookup"><span data-stu-id="dbab3-181">The `<ProjectReference>` elements don't need the `<Project>` and `<Name>` children, so you can remove those settings:</span></span>

    ```xml
    <ItemGroup>
      <ProjectReference Include="..\MatchingGame.Logic\MatchingGame.Logic.csproj" />
    </ItemGroup>
    ```

### <a name="resources-and-settings"></a><span data-ttu-id="dbab3-182">资源和设置</span><span class="sxs-lookup"><span data-stu-id="dbab3-182">Resources and settings</span></span>

<span data-ttu-id="dbab3-183">关于 .NET Framework 项目和 .NET 5 使用的 SDK 样式项目之间的差异，需要注意的一点是，.NET Framework 项目对代码文件使用选择加入模型。</span><span class="sxs-lookup"><span data-stu-id="dbab3-183">One thing to note about the difference between .NET Framework projects and the SDK-style projects used by .NET 5 is that .NET Framework projects use an opt-in model for code files.</span></span> <span data-ttu-id="dbab3-184">要编译的任何代码文件都需要在项目文件中进行显式地定义。</span><span class="sxs-lookup"><span data-stu-id="dbab3-184">Any code file you want to compile needs to be explicitly defined in your project file.</span></span> <span data-ttu-id="dbab3-185">SDK 样式项目相反，它们默认采用选择退出行为：从项目的目录及其下级目录开始的所有代码文件都会自动包含在你的项目中。</span><span class="sxs-lookup"><span data-stu-id="dbab3-185">SDK-style projects are reverse, they default to opt-out behavior: All code files starting from the project's directory and below are automatically included in your project.</span></span> <span data-ttu-id="dbab3-186">如果这些项很简单且没有设置，则无需迁移它们。</span><span class="sxs-lookup"><span data-stu-id="dbab3-186">You don't need to migrate these entries if they are simple and without settings.</span></span> <span data-ttu-id="dbab3-187">这对于其他常见文件（如 resx）是相同的。</span><span class="sxs-lookup"><span data-stu-id="dbab3-187">This is the same for other common files such as _resx_.</span></span>

<span data-ttu-id="dbab3-188">Windows 窗体项目还包含 Properties/Settings.settings 和 Properties/Resources.resx 等 Windows 窗体项目特定文件 。</span><span class="sxs-lookup"><span data-stu-id="dbab3-188">Windows Forms projects also include Windows Form project specific files, such as _Properties/Settings.settings_ and _Properties/Resources.resx_.</span></span> <span data-ttu-id="dbab3-189">可能需要迁移这些文件，因为它们在原始项目中进行了声明。</span><span class="sxs-lookup"><span data-stu-id="dbab3-189">These files may need to be migrated they are declared in your original project.</span></span>

<span data-ttu-id="dbab3-190">将旧项目文件中的条目复制到新项目的 `<ItemGroup>` 元素中。</span><span class="sxs-lookup"><span data-stu-id="dbab3-190">Copy those entries from the old project file into an `<ItemGroup>` element in the new project.</span></span> <span data-ttu-id="dbab3-191">复制条目后，将所有 `<Compile Include="value">` 元素更改为改用 `Update` 属性而不是 `Include`。</span><span class="sxs-lookup"><span data-stu-id="dbab3-191">After you copy the entries, change all `<Compile Include="value">` elements to instead use the `Update` attribute instead of `Include`.</span></span>

- <span data-ttu-id="dbab3-192">导入 Settings.settings 文件的配置。</span><span class="sxs-lookup"><span data-stu-id="dbab3-192">Import the configuration for the _Settings.settings_ file.</span></span>

  ```xml
  <ItemGroup>
    <None Include="Properties\Settings.settings">
      <Generator>SettingsSingleFileGenerator</Generator>
      <LastGenOutput>Settings.Designer.cs</LastGenOutput>
    </None>
    <Compile Update="Properties\Settings.Designer.cs">
      <AutoGen>True</AutoGen>
      <DependentUpon>Settings.settings</DependentUpon>
      <DesignTimeSharedInput>True</DesignTimeSharedInput>
    </Compile>
  </ItemGroup>
  ```

  <span data-ttu-id="dbab3-193">请注意，Properties\Settings.settings 项仍然为 `Include`。</span><span class="sxs-lookup"><span data-stu-id="dbab3-193">Notice that the _Properties\Settings.settings_ entry remained `Include`.</span></span> <span data-ttu-id="dbab3-194">该项目不会自动包含 settings 文件。</span><span class="sxs-lookup"><span data-stu-id="dbab3-194">The project doesn't automatically include _settings_ files.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="dbab3-195">Visual Basic 项目通常使用“我的项目”文件夹来存储默认项目设置文件，而 C# 项目通常使用“属性”文件夹 。</span><span class="sxs-lookup"><span data-stu-id="dbab3-195">**Visual Basic** projects typically use the folder _My Project_ while C# projects typically use the folder _Properties_ for the default project settings file.</span></span>
  
- <span data-ttu-id="dbab3-196">导入任何 resx 文件（如 properties/Resources.resx 文件）的配置 。</span><span class="sxs-lookup"><span data-stu-id="dbab3-196">Import the configuration for any _resx_ file, such as the _properties/Resources.resx_ file.</span></span> <span data-ttu-id="dbab3-197">请注意，`Include` 属性已更改为 `<Compile>` 元素上的 `Update`，并且从 `<EmbeddedResource>` 中删除了 `<SubType>`：</span><span class="sxs-lookup"><span data-stu-id="dbab3-197">Notice that the `Include` attribute was changed to `Update` on the `<Compile>` element, and `<SubType>` was removed from `<EmbeddedResource>`:</span></span>

  ```xml
  <ItemGroup>
    <EmbeddedResource Include="Properties\Resources.resx">
      <Generator>ResXFileCodeGenerator</Generator>
      <LastGenOutput>Resources.Designer.cs</LastGenOutput>
    </EmbeddedResource>
    <Compile Update="Properties\Resources.Designer.cs">
      <AutoGen>True</AutoGen>
      <DependentUpon>Resources.resx</DependentUpon>
      <DesignTime>True</DesignTime>
    </Compile>
  </ItemGroup>
  ```

  > [!IMPORTANT]
  > <span data-ttu-id="dbab3-198">Visual Basic 项目通常使用“我的项目”文件夹来存储默认项目资源文件，而 C# 项目通常使用“属性”文件夹 。</span><span class="sxs-lookup"><span data-stu-id="dbab3-198">**Visual Basic** projects typically use the folder _My Project_ while C# projects typically use the folder _Properties_ for the default project resource file.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="dbab3-199">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dbab3-199">Visual Basic</span></span>

<span data-ttu-id="dbab3-200">Visual Basic 语言项目需要额外的配置。</span><span class="sxs-lookup"><span data-stu-id="dbab3-200">Visual Basic language projects require extra configuration.</span></span>

01. <span data-ttu-id="dbab3-201">导入配置文件“My Project\Application.myapp”设置。</span><span class="sxs-lookup"><span data-stu-id="dbab3-201">Import the configuration file _My Project\Application.myapp_ setting.</span></span> <span data-ttu-id="dbab3-202">请注意，`<Compile>` 元素使用 `Update` 属性而不是 `Include` 属性。</span><span class="sxs-lookup"><span data-stu-id="dbab3-202">Notice that the `<Compile>` element uses the `Update` attribute instead of the `Include` attribute.</span></span>

    ```xml
    <ItemGroup>
      <None Include="My Project\Application.myapp">
        <Generator>MyApplicationCodeGenerator</Generator>
        <LastGenOutput>Application.Designer.vb</LastGenOutput>
      </None>
      <Compile Update="My Project\Application.Designer.vb">
        <AutoGen>True</AutoGen>
        <DependentUpon>Application.myapp</DependentUpon>
        <DesignTime>True</DesignTime>
      </Compile>
    </ItemGroup>
    ```

01. <span data-ttu-id="dbab3-203">向 `<PropertyGroup>` 元素添加 `<MyType>WindowsForms</MyType>` 设置：</span><span class="sxs-lookup"><span data-stu-id="dbab3-203">Add the `<MyType>WindowsForms</MyType>` setting to the `<PropertyGroup>` element:</span></span>

    ```xml
    <PropertyGroup>
      (contains settings previously described)

      <MyType>WindowsForms</MyType>
    </PropertyGroup>
    ```

    <span data-ttu-id="dbab3-204">此设置将导入 Visual Basic 程序员熟悉的 `My` 命名空间成员。</span><span class="sxs-lookup"><span data-stu-id="dbab3-204">This setting imports the `My` namespace members Visual Basic programmers are familiar with.</span></span>

01. <span data-ttu-id="dbab3-205">导入项目定义的命名空间。</span><span class="sxs-lookup"><span data-stu-id="dbab3-205">Import the namespaces defined by your project.</span></span>

    <span data-ttu-id="dbab3-206">Visual Basic 项目可自动将命名空间导入每个代码文件中。</span><span class="sxs-lookup"><span data-stu-id="dbab3-206">Visual Basic projects can automatically import namespaces into every code file.</span></span> <span data-ttu-id="dbab3-207">将 `<ItemGroup>` 元素从包含 `<Import>` 的旧项目文件复制到 `</PropertyGroup>` 结束标记之后的新文件中。</span><span class="sxs-lookup"><span data-stu-id="dbab3-207">Copy the `<ItemGroup>` elements from the old project file that contain `<Import>` into the new file after the `</PropertyGroup>` closing tag.</span></span>

    ```xml
    <ItemGroup>
      <Import Include="Microsoft.VisualBasic" />
      <Import Include="System" />
      <Import Include="System.Collections" />
      <Import Include="System.Collections.Generic" />
      <Import Include="System.Data" />
      <Import Include="System.Drawing" />
      <Import Include="System.Diagnostics" />
      <Import Include="System.Windows.Forms" />
      <Import Include="System.Linq" />
      <Import Include="System.Xml.Linq" />
      <Import Include="System.Threading.Tasks" />
    </ItemGroup>
    ```

    <span data-ttu-id="dbab3-208">如果找不到任何 `<Import>` 语句，或项目编译失败，请确保你至少在项目中定义了以下 `<Import>` 语句：</span><span class="sxs-lookup"><span data-stu-id="dbab3-208">If you can't find any `<Import>` statements, or your project fails to compile, make sure you at least have the following `<Import>` statements defined in your project:</span></span>

    ```xml
    <ItemGroup>
      <Import Include="System.Data" />
      <Import Include="System.Drawing" />
      <Import Include="System.Windows.Forms" />
    </ItemGroup>
    ```

01. <span data-ttu-id="dbab3-209">从原始项目中，将 `<Option*>` 和 `<StartupObject>` 设置复制到 `<PropertyGroup>` 元素：</span><span class="sxs-lookup"><span data-stu-id="dbab3-209">From the original project, copy the `<Option*>` and `<StartupObject>` settings to the `<PropertyGroup>` element:</span></span>

    ```xml
    <PropertyGroup>
      (contains settings previously described)

      <OptionExplicit>On</OptionExplicit>
      <OptionCompare>Binary</OptionCompare>
      <OptionStrict>Off</OptionStrict>
      <OptionInfer>On</OptionInfer>
      <StartupObject>MatchingGame.My.MyApplication</StartupObject>
    </PropertyGroup>
    ```

### <a name="reload-the-project"></a><span data-ttu-id="dbab3-210">重载项目</span><span class="sxs-lookup"><span data-stu-id="dbab3-210">Reload the project</span></span>

<span data-ttu-id="dbab3-211">将项目转换为新的 SDK 样式格式后，请在 Visual Studio 中重载项目：</span><span class="sxs-lookup"><span data-stu-id="dbab3-211">After you convert a project to the new SDK-style format, reload the project in Visual Studio:</span></span>

01. <span data-ttu-id="dbab3-212">在“解决方案资源管理器”中，找到要转换的项目。</span><span class="sxs-lookup"><span data-stu-id="dbab3-212">In **Solution Explorer**, find the project you converted.</span></span>
01. <span data-ttu-id="dbab3-213">右键单击项目，选择“重载项目”。</span><span class="sxs-lookup"><span data-stu-id="dbab3-213">Right-click on the project and select **Reload Project**.</span></span>

    <span data-ttu-id="dbab3-214">如果项目加载失败，则可能是因为在项目的 XML 中引入了一个错误。</span><span class="sxs-lookup"><span data-stu-id="dbab3-214">If the project fails to load, you may have introduced a mistake in the XML of the project.</span></span> <span data-ttu-id="dbab3-215">打开项目文件以进行编辑，并尝试识别和修复错误。</span><span class="sxs-lookup"><span data-stu-id="dbab3-215">Open the project file for editing and try to identify and fix the mistake.</span></span> <span data-ttu-id="dbab3-216">如果找不到错误，请尝试重启。</span><span class="sxs-lookup"><span data-stu-id="dbab3-216">If you can't find a mistake, try starting over.</span></span>

## <a name="edit-appconfig"></a><span data-ttu-id="dbab3-217">编辑 App.config</span><span class="sxs-lookup"><span data-stu-id="dbab3-217">Edit App.config</span></span>

<span data-ttu-id="dbab3-218">如果你的应用包含 app.config 文件，则删除 `<supportedRuntime>` 元素：</span><span class="sxs-lookup"><span data-stu-id="dbab3-218">If your app has an _App.config_ file, remove the `<supportedRuntime>` element:</span></span>

```xml
<supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
```

<span data-ttu-id="dbab3-219">对于 App.config 文件，有一些事项需要考虑。</span><span class="sxs-lookup"><span data-stu-id="dbab3-219">There are some things you should consider with the *App.config* file.</span></span> <span data-ttu-id="dbab3-220">.NET Framework 中的 App.config 文件不仅用于配置应用，还用于配置运行时设置和行为，如日志记录。</span><span class="sxs-lookup"><span data-stu-id="dbab3-220">The *App.config* file in .NET Framework was used not only to configure the app, but to configure runtime settings and behavior, such as logging.</span></span> <span data-ttu-id="dbab3-221">.NET 5+（和 .NET Core）中的 App.config 文件不再用于运行时配置。</span><span class="sxs-lookup"><span data-stu-id="dbab3-221">The *App.config* file in .NET 5+ (and .NET Core) is no longer used for runtime configuration.</span></span> <span data-ttu-id="dbab3-222">如果 App.config 文件包含这些部分，则不会考虑这些部分。</span><span class="sxs-lookup"><span data-stu-id="dbab3-222">If your *App.config* file has these sections, they won't be respected.</span></span>

## <a name="add-the-compatibility-package"></a><span data-ttu-id="dbab3-223">添加兼容性包</span><span class="sxs-lookup"><span data-stu-id="dbab3-223">Add the compatibility package</span></span>

<span data-ttu-id="dbab3-224">如果项目文件正确加载，但项目编译失败，则会收到类似以下形式的错误消息：</span><span class="sxs-lookup"><span data-stu-id="dbab3-224">If your project file is loading correctly, but compilation fails for your project and you receive errors similar to the following:</span></span>

- <span data-ttu-id="dbab3-225">找不到类型或命名空间 \<some name></span><span class="sxs-lookup"><span data-stu-id="dbab3-225">**The type or namespace \<some name> could not be found**</span></span>
- <span data-ttu-id="dbab3-226">当前上下文中不存在名称 \<some name></span><span class="sxs-lookup"><span data-stu-id="dbab3-226">**The name \<some name> does not exist in the current context**</span></span>

<span data-ttu-id="dbab3-227">你可能需要向应用添加 [`Microsoft.Windows.Compatibility`](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/) 包。</span><span class="sxs-lookup"><span data-stu-id="dbab3-227">You may need to add the [`Microsoft.Windows.Compatibility`](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/) package to your app.</span></span> <span data-ttu-id="dbab3-228">此包会添加 .NET Framework 中的约 21,000 个 .NET API，如 `System.Configuration.ConfigurationManager` 类和用于与 Windows 注册表交互的 API。</span><span class="sxs-lookup"><span data-stu-id="dbab3-228">This package adds ~21,000 .NET APIs from .NET Framework, such as the `System.Configuration.ConfigurationManager` class and APIs for interacting with the Windows Registry.</span></span> <span data-ttu-id="dbab3-229">添加 `Microsoft.Windows.Compatibility` 程序包。</span><span class="sxs-lookup"><span data-stu-id="dbab3-229">Add the `Microsoft.Windows.Compatibility` package.</span></span>

<span data-ttu-id="dbab3-230">编辑项目文件并添加以下 `<ItemGroup>` 元素：</span><span class="sxs-lookup"><span data-stu-id="dbab3-230">Edit your project file and add the following `<ItemGroup>` element:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.Windows.Compatibility" Version="5.0.0" />
</ItemGroup>
```

## <a name="test-your-app"></a><span data-ttu-id="dbab3-231">测试应用</span><span class="sxs-lookup"><span data-stu-id="dbab3-231">Test your app</span></span>

<span data-ttu-id="dbab3-232">完成应用迁移后，请进行测试！</span><span class="sxs-lookup"><span data-stu-id="dbab3-232">After you've finished migrating your app, test it!</span></span>

## <a name="next-steps"></a><span data-ttu-id="dbab3-233">后续步骤</span><span class="sxs-lookup"><span data-stu-id="dbab3-233">Next steps</span></span>

- <span data-ttu-id="dbab3-234">了解 [Windows 窗体的重大变更](/dotnet/core/compatibility/winforms)。</span><span class="sxs-lookup"><span data-stu-id="dbab3-234">Learn about [breaking changes in Windows Forms](/dotnet/core/compatibility/winforms).</span></span>
- <span data-ttu-id="dbab3-235">详细了解 [Windows 兼容包][compat-pack]。</span><span class="sxs-lookup"><span data-stu-id="dbab3-235">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>

[compat-pack]: /dotnet/core/porting/windows-compat-pack
