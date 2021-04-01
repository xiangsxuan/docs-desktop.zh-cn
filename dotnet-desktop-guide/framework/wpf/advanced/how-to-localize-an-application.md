---
title: 对应用进行本地化
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: dc7d8f4f56b26fffbd883e1e1d6e420026e1f94f
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972785"
---
# <a name="how-to-localize-an-application"></a><span data-ttu-id="45a47-102">如何：对应用程序进行本地化</span><span class="sxs-lookup"><span data-stu-id="45a47-102">How to: Localize an application</span></span>

<span data-ttu-id="45a47-103">本教程介绍如何通过使用 LocBaml 工具创建本地化应用程序。</span><span class="sxs-lookup"><span data-stu-id="45a47-103">This tutorial explains how to create a localized application by using the LocBaml tool.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="45a47-104">LocBaml 工具不是可直接用于生产的应用程序。</span><span class="sxs-lookup"><span data-stu-id="45a47-104">The LocBaml tool is not a production-ready application.</span></span> <span data-ttu-id="45a47-105">它表示为一个示例，该示例使用某些本地化 API 并演示编写一个本地化工具的方法。</span><span class="sxs-lookup"><span data-stu-id="45a47-105">It is presented as a sample that uses some of the localization APIs and illustrates how you might write a localization tool.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="45a47-106">概述</span><span class="sxs-lookup"><span data-stu-id="45a47-106">Overview</span></span>

<span data-ttu-id="45a47-107">本文提供了用于本地化应用程序的分步方法。</span><span class="sxs-lookup"><span data-stu-id="45a47-107">This article gives you a step-by-step approach to localizing an application.</span></span> <span data-ttu-id="45a47-108">首先，准备好应用程序，以便可以提取将翻译的文本。</span><span class="sxs-lookup"><span data-stu-id="45a47-108">First, you prepare your application so that the text that will be translated can be extracted.</span></span> <span data-ttu-id="45a47-109">翻译文本后，将翻译的文本合并到原始应用程序的新副本中。</span><span class="sxs-lookup"><span data-stu-id="45a47-109">After the text is translated, you merge the translated text into a new copy of the original application.</span></span>
  
## <a name="create-a-sample-application"></a><span data-ttu-id="45a47-110">创建示例应用程序</span><span class="sxs-lookup"><span data-stu-id="45a47-110">Create a sample application</span></span>

<span data-ttu-id="45a47-111">在此步骤中，您准备好应用程序进行本地化。</span><span class="sxs-lookup"><span data-stu-id="45a47-111">In this step, you prepare your app for localization.</span></span> <span data-ttu-id="45a47-112">在 Windows Presentation Foundation (WPF) 示例中，提供了一个 Helloapp.resources.dll 示例，该示例将用于本讨论中的代码示例。</span><span class="sxs-lookup"><span data-stu-id="45a47-112">In the Windows Presentation Foundation (WPF) samples, a HelloApp sample is supplied that will be used for the code examples in this discussion.</span></span> <span data-ttu-id="45a47-113">如果要使用此示例，请从 [LocBaml 工具示例](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml)下载 EXTENSIBLE APPLICATION MARKUP LANGUAGE (XAML) 文件。</span><span class="sxs-lookup"><span data-stu-id="45a47-113">If you would like to use this sample, download the Extensible Application Markup Language (XAML) files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
1. <span data-ttu-id="45a47-114">将应用程序开发到想要开始进行本地化的位置。</span><span class="sxs-lookup"><span data-stu-id="45a47-114">Develop your application to the point where you want to start localization.</span></span>  
  
2. <span data-ttu-id="45a47-115">在项目文件中指定开发语言，以便 MSBuild (包含非特定语言资源的 .resources.dll 扩展) 生成主程序集和附属程序集。</span><span class="sxs-lookup"><span data-stu-id="45a47-115">Specify the development language in the project file so that MSBuild generates a main assembly and a satellite assembly (a file with the .resources.dll extension) to contain the neutral language resources.</span></span> <span data-ttu-id="45a47-116">HelloApp 示例中的项目文件是 HelloApp.csproj。</span><span class="sxs-lookup"><span data-stu-id="45a47-116">The project file in the HelloApp sample is HelloApp.csproj.</span></span> <span data-ttu-id="45a47-117">在该文件中，你将找到标识如下的开发语言：</span><span class="sxs-lookup"><span data-stu-id="45a47-117">In that file, you will find the development language identified as follows:</span></span>  
  
   `<UICulture>en-US</UICulture>`  
  
3. <span data-ttu-id="45a47-118">将 Uid 添加到 XAML 文件。</span><span class="sxs-lookup"><span data-stu-id="45a47-118">Add Uids to your XAML files.</span></span> <span data-ttu-id="45a47-119">Uid 用于跟踪对文件的更改并标识必须翻译的项。</span><span class="sxs-lookup"><span data-stu-id="45a47-119">Uids are used to keep track of changes to files and to identify items that must be translated.</span></span> <span data-ttu-id="45a47-120">若要将 Uid 添加到文件，请 `updateuid` 在项目文件中运行：</span><span class="sxs-lookup"><span data-stu-id="45a47-120">To add Uids to your files, run `updateuid` on your project file:</span></span>  

   `msbuild -t:updateuid helloapp.csproj`

   <span data-ttu-id="45a47-121">若要验证没有缺少或重复的 Uid，请运行 `checkuid` ：</span><span class="sxs-lookup"><span data-stu-id="45a47-121">To verify that you have no missing or duplicate Uids, run `checkuid`:</span></span>  

   `msbuild -t:checkuid helloapp.csproj`

   <span data-ttu-id="45a47-122">运行后 `updateuid` ，文件应包含 uid。</span><span class="sxs-lookup"><span data-stu-id="45a47-122">After running `updateuid`, your files should contain Uids.</span></span> <span data-ttu-id="45a47-123">例如，在 Helloapp.resources.dll 的 *pane1.xaml* 文件中，应会看到以下内容：</span><span class="sxs-lookup"><span data-stu-id="45a47-123">For example, in the *Pane1.xaml* file of HelloApp, you should find the following:</span></span>  

   ```xaml
   <StackPanel x:Uid="StackPanel_1">
     <TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>
     <TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>
   </StackPanel>
   ```

## <a name="create-the-neutral-language-resources-satellite-assembly"></a><span data-ttu-id="45a47-124">创建非特定语言资源附属程序集</span><span class="sxs-lookup"><span data-stu-id="45a47-124">Create the neutral-language resources satellite assembly</span></span>

<span data-ttu-id="45a47-125">在将应用程序配置为生成非特定语言资源附属程序集后，将生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="45a47-125">After the application is configured to generate a neutral-language resources satellite assembly, you build the application.</span></span> <span data-ttu-id="45a47-126">这会生成主应用程序程序集，以及 LocBaml 本地化所需的非特定语言资源附属程序集。</span><span class="sxs-lookup"><span data-stu-id="45a47-126">This generates the main application assembly as well as the neutral-language resources satellite assembly that's required by LocBaml for localization.</span></span>

<span data-ttu-id="45a47-127">若要生成应用程序，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="45a47-127">To build the application:</span></span>  
  
1. <span data-ttu-id="45a47-128">编译 Helloapp.resources.dll 以创建动态链接库 (DLL) ：</span><span class="sxs-lookup"><span data-stu-id="45a47-128">Compile HelloApp to create a dynamic-link library (DLL):</span></span>  
  
   `msbuild helloapp.csproj`
  
2. <span data-ttu-id="45a47-129">将在以下文件夹中创建新创建的主应用程序程序集 HelloApp.exe： *C:\HelloApp\Bin\Debug*</span><span class="sxs-lookup"><span data-stu-id="45a47-129">The newly created main application assembly, HelloApp.exe, is created in the following folder: *C:\HelloApp\Bin\Debug*</span></span>
  
3. <span data-ttu-id="45a47-130">在以下文件夹中创建新创建的非特定语言资源附属程序集 HelloApp.resources.dll： *C:\HelloApp\Bin\Debug\en-US*</span><span class="sxs-lookup"><span data-stu-id="45a47-130">The newly created neutral-language resources satellite assembly, HelloApp.resources.dll, is created in the following folder: *C:\HelloApp\Bin\Debug\en-US*</span></span>
  
## <a name="build-the-locbaml-tool"></a><span data-ttu-id="45a47-131">生成 LocBaml 工具</span><span class="sxs-lookup"><span data-stu-id="45a47-131">Build the LocBaml tool</span></span>  
  
1. <span data-ttu-id="45a47-132">生成 LocBaml 所需的所有文件都位于 WPF 示例中。</span><span class="sxs-lookup"><span data-stu-id="45a47-132">All the files necessary to build LocBaml are located in the WPF samples.</span></span> <span data-ttu-id="45a47-133">从 [LocBaml 工具示例](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml)下载 c # 文件。</span><span class="sxs-lookup"><span data-stu-id="45a47-133">Download the C# files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
2. <span data-ttu-id="45a47-134">从命令行运行项目文件 (locbaml.csproj) 来生成该工具：</span><span class="sxs-lookup"><span data-stu-id="45a47-134">From the command line, run the project file (locbaml.csproj) to build the tool:</span></span>  

   `msbuild locbaml.csproj`
  
3. <span data-ttu-id="45a47-135">请在 *Bin\Release* 目录中查找新创建的可执行文件 (locbaml.exe) 。</span><span class="sxs-lookup"><span data-stu-id="45a47-135">Go to the *Bin\Release* directory to find the newly created executable file (locbaml.exe).</span></span> <span data-ttu-id="45a47-136">示例： *C:\LocBaml\Bin\Release\locbaml.exe*</span><span class="sxs-lookup"><span data-stu-id="45a47-136">Example: *C:\LocBaml\Bin\Release\locbaml.exe*</span></span>
  
4. <span data-ttu-id="45a47-137">运行 LocBaml 时可以指定的选项如下所示。</span><span class="sxs-lookup"><span data-stu-id="45a47-137">The options that you can specify when you run LocBaml are as follows.</span></span>

   | <span data-ttu-id="45a47-138">选项</span><span class="sxs-lookup"><span data-stu-id="45a47-138">Option</span></span> | <span data-ttu-id="45a47-139">描述</span><span class="sxs-lookup"><span data-stu-id="45a47-139">Description</span></span>|
   | - | - |
   | <span data-ttu-id="45a47-140">`parse` 或 `-p`</span><span class="sxs-lookup"><span data-stu-id="45a47-140">`parse` or `-p`</span></span> | <span data-ttu-id="45a47-141">分析 Baml、资源或 DLL 文件以生成 .csv 或 .txt 文件。</span><span class="sxs-lookup"><span data-stu-id="45a47-141">Parses Baml, resources, or DLL files to generate a .csv or .txt file.</span></span> |
   | <span data-ttu-id="45a47-142">`generate` 或 `-g`</span><span class="sxs-lookup"><span data-stu-id="45a47-142">`generate` or `-g`</span></span> | <span data-ttu-id="45a47-143">使用翻译的文件生成本地化的二进制文件。</span><span class="sxs-lookup"><span data-stu-id="45a47-143">Generates a localized binary file by using a translated file.</span></span> |
   | <span data-ttu-id="45a47-144">`out` 或 `-o` {*filedirectory*]</span><span class="sxs-lookup"><span data-stu-id="45a47-144">`out` or `-o` {*filedirectory*]</span></span> | <span data-ttu-id="45a47-145">输出文件名。</span><span class="sxs-lookup"><span data-stu-id="45a47-145">Output file name.</span></span> |
   | <span data-ttu-id="45a47-146">`culture` 或 `-cul` {*culture*]</span><span class="sxs-lookup"><span data-stu-id="45a47-146">`culture` or `-cul` {*culture*]</span></span> | <span data-ttu-id="45a47-147">输出程序集的区域设置。</span><span class="sxs-lookup"><span data-stu-id="45a47-147">Locale of output assemblies.</span></span> |
   | <span data-ttu-id="45a47-148">`translation` 或 `-trans` {*translation.csv*]</span><span class="sxs-lookup"><span data-stu-id="45a47-148">`translation` or `-trans` {*translation.csv*]</span></span> | <span data-ttu-id="45a47-149">已翻译或本地化的文件。</span><span class="sxs-lookup"><span data-stu-id="45a47-149">Translated or localized file.</span></span> |
   | <span data-ttu-id="45a47-150">`asmpath` 或 `-asmpath` {*filedirectory*]</span><span class="sxs-lookup"><span data-stu-id="45a47-150">`asmpath` or `-asmpath` {*filedirectory*]</span></span> | <span data-ttu-id="45a47-151">如果 XAML 代码包含自定义控件，则必须 `asmpath` 向自定义控件程序集提供。</span><span class="sxs-lookup"><span data-stu-id="45a47-151">If your XAML code contains custom controls, you must supply the `asmpath` to the custom control assembly.</span></span> |
   | `nologo` | <span data-ttu-id="45a47-152"> 显示没有徽标或版权信息。</span><span class="sxs-lookup"><span data-stu-id="45a47-152">Displays no logo or copyright information.</span></span> |
   | `verbose` | <span data-ttu-id="45a47-153"> 显示详细模式信息。</span><span class="sxs-lookup"><span data-stu-id="45a47-153">Displays verbose mode information.</span></span> |
  
   > [!NOTE]
   > <span data-ttu-id="45a47-154">如果在运行该工具时需要选项列表，请输入 `LocBaml.exe` ，然后按 **enter**。</span><span class="sxs-lookup"><span data-stu-id="45a47-154">If you need a list of the options when you are running the tool, enter `LocBaml.exe` and then press **Enter**.</span></span>
  
## <a name="use-locbaml-to-parse-a-file"></a><span data-ttu-id="45a47-155">使用 LocBaml 分析文件</span><span class="sxs-lookup"><span data-stu-id="45a47-155">Use LocBaml to parse a file</span></span>

<span data-ttu-id="45a47-156">由于已创建 LocBaml 工具，就可使用它来分析 HelloApp.resources.dll，从而提取将进行本地化的文本内容。</span><span class="sxs-lookup"><span data-stu-id="45a47-156">Now that you have created the LocBaml tool, you are ready to use it to parse HelloApp.resources.dll to extract the text content that will be localized.</span></span>  
  
1. <span data-ttu-id="45a47-157">将 LocBaml.exe 复制到应用程序的 bin\debug 文件夹，这也是创建主应用程序程序集的位置。</span><span class="sxs-lookup"><span data-stu-id="45a47-157">Copy LocBaml.exe to your application's bin\debug folder, where the main application assembly was created.</span></span>  
  
2. <span data-ttu-id="45a47-158">若要分析附属程序集文件并将输出存储为 .csv 文件，请使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="45a47-158">To parse the satellite assembly file and store the output as a .csv file, use the following command:</span></span>  
  
   `LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv`
  
   > [!NOTE]
   > <span data-ttu-id="45a47-159">如果输入文件 HelloApp.resources.dll 不在 LocBaml.exe 所在的同一目录中，请移动其中一个文件以使两个文件都位于同一目录中。</span><span class="sxs-lookup"><span data-stu-id="45a47-159">If the input file, HelloApp.resources.dll, is not in the same directory as LocBaml.exe move one of the files so that both files are in the same directory.</span></span>  
  
3. <span data-ttu-id="45a47-160">当运行 LocBaml 来分析文件时，输出包含由逗号（.csv 文件）或制表符（.txt 文件）分隔的七个字段。</span><span class="sxs-lookup"><span data-stu-id="45a47-160">When you run LocBaml to parse files, the output consists of seven fields delimited by commas (.csv files) or tabs (.txt files).</span></span> <span data-ttu-id="45a47-161">下面显示了 HelloApp.resources.dll 的已分析的 .csv 文件：</span><span class="sxs-lookup"><span data-stu-id="45a47-161">The following shows the parsed .csv file for the HelloApp.resources.dll:</span></span>

   | |
   |-|
   |<span data-ttu-id="45a47-162">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="45a47-162">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span></span>|
   |<span data-ttu-id="45a47-163">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span><span class="sxs-lookup"><span data-stu-id="45a47-163">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span></span>|
   |<span data-ttu-id="45a47-164">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span><span class="sxs-lookup"><span data-stu-id="45a47-164">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span></span>|

   <span data-ttu-id="45a47-165">这七个字段是：</span><span class="sxs-lookup"><span data-stu-id="45a47-165">The seven fields are:</span></span>  
  
   - <span data-ttu-id="45a47-166">**BAML 名称**。</span><span class="sxs-lookup"><span data-stu-id="45a47-166">**BAML Name**.</span></span> <span data-ttu-id="45a47-167">与源语言附属程序集相关的 BAML 资源的名称。</span><span class="sxs-lookup"><span data-stu-id="45a47-167">The name of the BAML resource with respect to the source language satellite assembly.</span></span>  
  
   - <span data-ttu-id="45a47-168">**资源键**。</span><span class="sxs-lookup"><span data-stu-id="45a47-168">**Resource Key**.</span></span> <span data-ttu-id="45a47-169">本地化的资源标识符。</span><span class="sxs-lookup"><span data-stu-id="45a47-169">The localized resource identifier.</span></span>  
  
   - <span data-ttu-id="45a47-170">**类别**。</span><span class="sxs-lookup"><span data-stu-id="45a47-170">**Category**.</span></span> <span data-ttu-id="45a47-171">值类型。</span><span class="sxs-lookup"><span data-stu-id="45a47-171">The value type.</span></span> <span data-ttu-id="45a47-172">请参阅 [本地化特性和注释](localization-attributes-and-comments.md)。</span><span class="sxs-lookup"><span data-stu-id="45a47-172">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="45a47-173">**可读性**。</span><span class="sxs-lookup"><span data-stu-id="45a47-173">**Readability**.</span></span> <span data-ttu-id="45a47-174">值是否可以由本地化人员读取。</span><span class="sxs-lookup"><span data-stu-id="45a47-174">Whether the value can be read by a localizer.</span></span> <span data-ttu-id="45a47-175">请参阅 [本地化特性和注释](localization-attributes-and-comments.md)。</span><span class="sxs-lookup"><span data-stu-id="45a47-175">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="45a47-176">**Modifiability**。</span><span class="sxs-lookup"><span data-stu-id="45a47-176">**Modifiability**.</span></span> <span data-ttu-id="45a47-177">值是否可以由本地化人员修改。</span><span class="sxs-lookup"><span data-stu-id="45a47-177">Whether the value can be modified by a localizer.</span></span> <span data-ttu-id="45a47-178">请参阅 [本地化特性和注释](localization-attributes-and-comments.md)。</span><span class="sxs-lookup"><span data-stu-id="45a47-178">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="45a47-179">**注释**。</span><span class="sxs-lookup"><span data-stu-id="45a47-179">**Comments**.</span></span> <span data-ttu-id="45a47-180">值的附加说明，用于确定值被本地化的方式。</span><span class="sxs-lookup"><span data-stu-id="45a47-180">Additional description of the value to help determine how a value is localized.</span></span> <span data-ttu-id="45a47-181">请参阅 [本地化特性和注释](localization-attributes-and-comments.md)。</span><span class="sxs-lookup"><span data-stu-id="45a47-181">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="45a47-182">**值**。</span><span class="sxs-lookup"><span data-stu-id="45a47-182">**Value**.</span></span> <span data-ttu-id="45a47-183">要翻译为所需区域性设置的文本值。</span><span class="sxs-lookup"><span data-stu-id="45a47-183">The text value to translate to the desired culture.</span></span>  
  
   <span data-ttu-id="45a47-184">下表显示了这些字段映射到 .csv 文件的分隔值的方式：</span><span class="sxs-lookup"><span data-stu-id="45a47-184">The following table shows how these fields map to the delimited values of the .csv file:</span></span>  
  
   |<span data-ttu-id="45a47-185">BAML 名称</span><span class="sxs-lookup"><span data-stu-id="45a47-185">BAML name</span></span>|<span data-ttu-id="45a47-186">资源键</span><span class="sxs-lookup"><span data-stu-id="45a47-186">Resource key</span></span>|<span data-ttu-id="45a47-187">类别</span><span class="sxs-lookup"><span data-stu-id="45a47-187">Category</span></span>|<span data-ttu-id="45a47-188">可读性</span><span class="sxs-lookup"><span data-stu-id="45a47-188">Readability</span></span>|<span data-ttu-id="45a47-189">可修改性</span><span class="sxs-lookup"><span data-stu-id="45a47-189">Modifiability</span></span>|<span data-ttu-id="45a47-190">注释</span><span class="sxs-lookup"><span data-stu-id="45a47-190">Comments</span></span>|<span data-ttu-id="45a47-191">值</span><span class="sxs-lookup"><span data-stu-id="45a47-191">Value</span></span>|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |<span data-ttu-id="45a47-192">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="45a47-192">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="45a47-193">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="45a47-193">Stack1:System.Windows.Controls.StackPanel.$Content</span></span>|<span data-ttu-id="45a47-194">忽略</span><span class="sxs-lookup"><span data-stu-id="45a47-194">Ignore</span></span>|<span data-ttu-id="45a47-195">false</span><span class="sxs-lookup"><span data-stu-id="45a47-195">FALSE</span></span>|<span data-ttu-id="45a47-196">false</span><span class="sxs-lookup"><span data-stu-id="45a47-196">FALSE</span></span>||<span data-ttu-id="45a47-197">#Text1;#Text2</span><span class="sxs-lookup"><span data-stu-id="45a47-197">#Text1;#Text2</span></span>|
   |<span data-ttu-id="45a47-198">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="45a47-198">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="45a47-199">Text1:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="45a47-199">Text1:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="45a47-200">无</span><span class="sxs-lookup"><span data-stu-id="45a47-200">None</span></span>|<span data-ttu-id="45a47-201">TRUE</span><span class="sxs-lookup"><span data-stu-id="45a47-201">TRUE</span></span>|<span data-ttu-id="45a47-202">TRUE</span><span class="sxs-lookup"><span data-stu-id="45a47-202">TRUE</span></span>||<span data-ttu-id="45a47-203">Hello World</span><span class="sxs-lookup"><span data-stu-id="45a47-203">Hello World</span></span>|
   |<span data-ttu-id="45a47-204">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="45a47-204">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="45a47-205">Text2:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="45a47-205">Text2:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="45a47-206">无</span><span class="sxs-lookup"><span data-stu-id="45a47-206">None</span></span>|<span data-ttu-id="45a47-207">TRUE</span><span class="sxs-lookup"><span data-stu-id="45a47-207">TRUE</span></span>|<span data-ttu-id="45a47-208">TRUE</span><span class="sxs-lookup"><span data-stu-id="45a47-208">TRUE</span></span>||<span data-ttu-id="45a47-209">Goodbye World</span><span class="sxs-lookup"><span data-stu-id="45a47-209">Goodbye World</span></span>|
  
   <span data-ttu-id="45a47-210">请注意， **注释** 字段的所有值不包含任何值;如果字段没有值，则为空。</span><span class="sxs-lookup"><span data-stu-id="45a47-210">Notice that all the values for the **Comments** field contain no values; if a field doesn't have a value, it is empty.</span></span> <span data-ttu-id="45a47-211">另请注意，第一行中的项既不可读也不可修改，并且具有 "Ignore" 作为其 **类别** 值，所有这些都指示该值不可本地化。</span><span class="sxs-lookup"><span data-stu-id="45a47-211">Also notice that the item in the first row is neither readable nor modifiable, and has "Ignore" as its **Category** value, all of which indicates that the value is not localizable.</span></span>  
  
4. <span data-ttu-id="45a47-212">为了便于发现已分析文件中的可本地化项（特别是在大型文件中），可以按 **类别**、 **可读性** 和可 **修改** 性对项进行排序或筛选。</span><span class="sxs-lookup"><span data-stu-id="45a47-212">To facilitate discovery of localizable items in parsed files, particularly in large files, you can sort or filter the items by **Category**, **Readability**, and **Modifiability**.</span></span> <span data-ttu-id="45a47-213">例如，你可以筛选出不可读且不可修改的值。</span><span class="sxs-lookup"><span data-stu-id="45a47-213">For example, you can filter out unreadable and unmodifiable values.</span></span>  
  
## <a name="translate-the-localizable-content"></a><span data-ttu-id="45a47-214">翻译可本地化的内容</span><span class="sxs-lookup"><span data-stu-id="45a47-214">Translate the localizable content</span></span>

<span data-ttu-id="45a47-215">使用任何你可用的工具翻译提取的内容。</span><span class="sxs-lookup"><span data-stu-id="45a47-215">Use any tool that you have available to translate the extracted content.</span></span> <span data-ttu-id="45a47-216">实现此目的的一种好方法是将资源写入 .csv 文件，并在 Microsoft Excel 中查看这些资源，对最后一列 (值) 进行转换更改。</span><span class="sxs-lookup"><span data-stu-id="45a47-216">A good way to do this is to write the resources to a .csv file and view them in Microsoft Excel, making translation changes to the last column (value).</span></span>  
  
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a><span data-ttu-id="45a47-217">使用 LocBaml 生成新的 .resources.dll 文件</span><span class="sxs-lookup"><span data-stu-id="45a47-217">Use LocBaml to generate a new .resources.dll file</span></span>

<span data-ttu-id="45a47-218">通过使用 LocBaml 分析 HelloApp.resources.dll 而标识的内容已被翻译，且必须合并回原始应用程序。</span><span class="sxs-lookup"><span data-stu-id="45a47-218">The content that was identified by parsing HelloApp.resources.dll with LocBaml has been translated and must be merged back into the original application.</span></span> <span data-ttu-id="45a47-219">使用 `generate` 或 `-g` 选项生成新的 .resources.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="45a47-219">Use the `generate` or `-g` option to generate a new .resources.dll file.</span></span>  
  
1. <span data-ttu-id="45a47-220">使用下列语法来生成新的 HelloApp.resources.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="45a47-220">Use the following syntax to generate a new HelloApp.resources.dll file.</span></span> <span data-ttu-id="45a47-221">将区域性标记为 zh-CN (/cul:zh-CN)。</span><span class="sxs-lookup"><span data-stu-id="45a47-221">Mark the culture as en-US (/cul:en-US).</span></span>  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US`  

   > [!NOTE]
   > <span data-ttu-id="45a47-222">如果输入文件 Hello.csv 与可执行文件 LocBaml.exe 不在的同一目录中，请移动其中一个文件以使两个文件都位于同一目录中。</span><span class="sxs-lookup"><span data-stu-id="45a47-222">If the input file, Hello.csv, is not in the same directory as the executable, LocBaml.exe, move one of the files so that both files are in the same directory.</span></span>  
  
2. <span data-ttu-id="45a47-223">将 *C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll* 目录中的旧 *HelloApp.resources.dll* 文件替换为新创建的 *HelloApp.resources.dll* 文件。</span><span class="sxs-lookup"><span data-stu-id="45a47-223">Replace the old *HelloApp.resources.dll* file in the *C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll* directory with your newly created *HelloApp.resources.dll* file.</span></span>  
  
3. <span data-ttu-id="45a47-224">应在你的应用程序中将“Hello World”和“Goodbye World”翻译过来。</span><span class="sxs-lookup"><span data-stu-id="45a47-224">"Hello World" and "Goodbye World" should now be translated in your application.</span></span>  
  
4. <span data-ttu-id="45a47-225">若要翻译到不同的区域性设置，请使用目标语言的区域设置。</span><span class="sxs-lookup"><span data-stu-id="45a47-225">To translate to a different culture, use the culture of the language that you are translating to.</span></span> <span data-ttu-id="45a47-226">下列示例演示了如何翻译为加拿大法语：</span><span class="sxs-lookup"><span data-stu-id="45a47-226">The following example shows how to translate to French-Canadian:</span></span>  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA`  
  
5. <span data-ttu-id="45a47-227">在主应用程序程序集所在的程序集，创建一个新的特定于区域性的文件夹，以容纳新的附属程序集。</span><span class="sxs-lookup"><span data-stu-id="45a47-227">In the same assembly as the main application assembly, create a new culture-specific folder to house the new satellite assembly.</span></span> <span data-ttu-id="45a47-228">对于加拿大法语，该文件夹将为 fr-CA。</span><span class="sxs-lookup"><span data-stu-id="45a47-228">For French-Canadian, the folder would be fr-CA.</span></span>  
  
6. <span data-ttu-id="45a47-229">将生成的附属程序集复制到新建文件夹。</span><span class="sxs-lookup"><span data-stu-id="45a47-229">Copy the generated satellite assembly to the new folder.</span></span>  
  
7. <span data-ttu-id="45a47-230">若要测试新的附属程序集，你需要更改应用程序将在其下运行的区域性设置。</span><span class="sxs-lookup"><span data-stu-id="45a47-230">To test the new satellite assembly, you need to change the culture under which your application will run.</span></span> <span data-ttu-id="45a47-231">可以通过两种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="45a47-231">You can do this in one of two ways:</span></span>  
  
   - <span data-ttu-id="45a47-232">更改操作系统的区域设置。</span><span class="sxs-lookup"><span data-stu-id="45a47-232">Change your operating system's regional settings.</span></span>
  
   - <span data-ttu-id="45a47-233">在你的应用程序中，将下列代码添加到 App.xaml.cs 中：</span><span class="sxs-lookup"><span data-stu-id="45a47-233">In your application, add the following code to App.xaml.cs:</span></span>  
  
     [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
     [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
     [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
## <a name="tips-for-using-locbaml"></a><span data-ttu-id="45a47-234">使用 LocBaml 的提示</span><span class="sxs-lookup"><span data-stu-id="45a47-234">Tips for Using LocBaml</span></span>  
  
- <span data-ttu-id="45a47-235">所有定义自定义控件的依赖程序集必须复制到 LocBaml 的本地目录，或安装到 GAC。</span><span class="sxs-lookup"><span data-stu-id="45a47-235">All dependent assemblies that define custom controls must be copied into the local directory of LocBaml or installed into the GAC.</span></span> <span data-ttu-id="45a47-236">这是必需的，因为本地化 API 在读取二进制 XAML (BAML) 时必须具有对依赖程序集的访问权限。</span><span class="sxs-lookup"><span data-stu-id="45a47-236">This is necessary because the localization API must have access to the dependent assemblies when it reads the binary XAML (BAML).</span></span>  
  
- <span data-ttu-id="45a47-237">如果主程序集已签名，则生成的资源 DLL 也必须签名以进行加载。</span><span class="sxs-lookup"><span data-stu-id="45a47-237">If the main assembly is signed, the generated resource DLL must also be signed in order for it to be loaded.</span></span>  
  
- <span data-ttu-id="45a47-238">本地化的资源 DLL 的版本需与主程序集进行同步。</span><span class="sxs-lookup"><span data-stu-id="45a47-238">The version of the localized resource DLL needs to be synchronized with the main assembly.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="45a47-239">请参阅</span><span class="sxs-lookup"><span data-stu-id="45a47-239">See also</span></span>

- [<span data-ttu-id="45a47-240">WPF 的全球化</span><span class="sxs-lookup"><span data-stu-id="45a47-240">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="45a47-241">使用自动布局概述</span><span class="sxs-lookup"><span data-stu-id="45a47-241">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
