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
# <a name="how-to-localize-an-application"></a>如何：对应用程序进行本地化

本教程介绍如何通过使用 LocBaml 工具创建本地化应用程序。  
  
> [!NOTE]
> LocBaml 工具不是可直接用于生产的应用程序。 它表示为一个示例，该示例使用某些本地化 API 并演示编写一个本地化工具的方法。  
  
## <a name="overview"></a>概述

本文提供了用于本地化应用程序的分步方法。 首先，准备好应用程序，以便可以提取将翻译的文本。 翻译文本后，将翻译的文本合并到原始应用程序的新副本中。
  
## <a name="create-a-sample-application"></a>创建示例应用程序

在此步骤中，您准备好应用程序进行本地化。 在 Windows Presentation Foundation (WPF) 示例中，提供了一个 Helloapp.resources.dll 示例，该示例将用于本讨论中的代码示例。 如果要使用此示例，请从 [LocBaml 工具示例](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml)下载 EXTENSIBLE APPLICATION MARKUP LANGUAGE (XAML) 文件。  
  
1. 将应用程序开发到想要开始进行本地化的位置。  
  
2. 在项目文件中指定开发语言，以便 MSBuild (包含非特定语言资源的 .resources.dll 扩展) 生成主程序集和附属程序集。 HelloApp 示例中的项目文件是 HelloApp.csproj。 在该文件中，你将找到标识如下的开发语言：  
  
   `<UICulture>en-US</UICulture>`  
  
3. 将 Uid 添加到 XAML 文件。 Uid 用于跟踪对文件的更改并标识必须翻译的项。 若要将 Uid 添加到文件，请 `updateuid` 在项目文件中运行：  

   `msbuild -t:updateuid helloapp.csproj`

   若要验证没有缺少或重复的 Uid，请运行 `checkuid` ：  

   `msbuild -t:checkuid helloapp.csproj`

   运行后 `updateuid` ，文件应包含 uid。 例如，在 Helloapp.resources.dll 的 *pane1.xaml* 文件中，应会看到以下内容：  

   ```xaml
   <StackPanel x:Uid="StackPanel_1">
     <TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>
     <TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>
   </StackPanel>
   ```

## <a name="create-the-neutral-language-resources-satellite-assembly"></a>创建非特定语言资源附属程序集

在将应用程序配置为生成非特定语言资源附属程序集后，将生成应用程序。 这会生成主应用程序程序集，以及 LocBaml 本地化所需的非特定语言资源附属程序集。

若要生成应用程序，请执行以下操作：  
  
1. 编译 Helloapp.resources.dll 以创建动态链接库 (DLL) ：  
  
   `msbuild helloapp.csproj`
  
2. 将在以下文件夹中创建新创建的主应用程序程序集 HelloApp.exe： *C:\HelloApp\Bin\Debug*
  
3. 在以下文件夹中创建新创建的非特定语言资源附属程序集 HelloApp.resources.dll： *C:\HelloApp\Bin\Debug\en-US*
  
## <a name="build-the-locbaml-tool"></a>生成 LocBaml 工具  
  
1. 生成 LocBaml 所需的所有文件都位于 WPF 示例中。 从 [LocBaml 工具示例](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml)下载 c # 文件。  
  
2. 从命令行运行项目文件 (locbaml.csproj) 来生成该工具：  

   `msbuild locbaml.csproj`
  
3. 请在 *Bin\Release* 目录中查找新创建的可执行文件 (locbaml.exe) 。 示例： *C:\LocBaml\Bin\Release\locbaml.exe*
  
4. 运行 LocBaml 时可以指定的选项如下所示。

   | 选项 | 说明|
   | - | - |
   | `parse` 或 `-p` | 分析 Baml、资源或 DLL 文件以生成 .csv 或 .txt 文件。 |
   | `generate` 或 `-g` | 使用翻译的文件生成本地化的二进制文件。 |
   | `out` 或 `-o` {*filedirectory*] | 输出文件名。 |
   | `culture` 或 `-cul` {*culture*] | 输出程序集的区域设置。 |
   | `translation` 或 `-trans` {*translation.csv*] | 已翻译或本地化的文件。 |
   | `asmpath` 或 `-asmpath` {*filedirectory*] | 如果 XAML 代码包含自定义控件，则必须 `asmpath` 向自定义控件程序集提供。 |
   | `nologo` |  显示没有徽标或版权信息。 |
   | `verbose` |  显示详细模式信息。 |
  
   > [!NOTE]
   > 如果在运行该工具时需要选项列表，请输入 `LocBaml.exe` ，然后按 **enter**。
  
## <a name="use-locbaml-to-parse-a-file"></a>使用 LocBaml 分析文件

由于已创建 LocBaml 工具，就可使用它来分析 HelloApp.resources.dll，从而提取将进行本地化的文本内容。  
  
1. 将 LocBaml.exe 复制到应用程序的 bin\debug 文件夹，这也是创建主应用程序程序集的位置。  
  
2. 若要分析附属程序集文件并将输出存储为 .csv 文件，请使用下列命令：  
  
   `LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv`
  
   > [!NOTE]
   > 如果输入文件 HelloApp.resources.dll 不在 LocBaml.exe 所在的同一目录中，请移动其中一个文件以使两个文件都位于同一目录中。  
  
3. 当运行 LocBaml 来分析文件时，输出包含由逗号（.csv 文件）或制表符（.txt 文件）分隔的七个字段。 下面显示了 HelloApp.resources.dll 的已分析的 .csv 文件：

   | |
   |-|
   |HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;|
   |HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World|
   |HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World|

   这七个字段是：  
  
   - **BAML 名称**。 与源语言附属程序集相关的 BAML 资源的名称。  
  
   - **资源键**。 本地化的资源标识符。  
  
   - **类别**。 值类型。 请参阅 [本地化特性和注释](localization-attributes-and-comments.md)。  
  
   - **可读性**。 值是否可以由本地化人员读取。 请参阅 [本地化特性和注释](localization-attributes-and-comments.md)。  
  
   - **Modifiability**。 值是否可以由本地化人员修改。 请参阅 [本地化特性和注释](localization-attributes-and-comments.md)。  
  
   - **注释**。 值的附加说明，用于确定值被本地化的方式。 请参阅 [本地化特性和注释](localization-attributes-and-comments.md)。  
  
   - **值**。 要翻译为所需区域性设置的文本值。  
  
   下表显示了这些字段映射到 .csv 文件的分隔值的方式：  
  
   |BAML 名称|资源键|类别|可读性|可修改性|注释|值|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |HelloApp.g.en-US.resources:window1.baml|Stack1:System.Windows.Controls.StackPanel.$Content|忽略|false|false||#Text1;#Text2|
   |HelloApp.g.en-US.resources:window1.baml|Text1:System.Windows.Controls.TextBlock.$Content|None|TRUE|TRUE||Hello World|
   |HelloApp.g.en-US.resources:window1.baml|Text2:System.Windows.Controls.TextBlock.$Content|None|TRUE|TRUE||Goodbye World|
  
   请注意， **注释** 字段的所有值不包含任何值;如果字段没有值，则为空。 另请注意，第一行中的项既不可读也不可修改，并且具有 "Ignore" 作为其 **类别** 值，所有这些都指示该值不可本地化。  
  
4. 为了便于发现已分析文件中的可本地化项（特别是在大型文件中），可以按 **类别**、 **可读性** 和可 **修改** 性对项进行排序或筛选。 例如，你可以筛选出不可读且不可修改的值。  
  
## <a name="translate-the-localizable-content"></a>翻译可本地化的内容

使用任何你可用的工具翻译提取的内容。 实现此目的的一种好方法是将资源写入 .csv 文件，并在 Microsoft Excel 中查看这些资源，对最后一列 (值) 进行转换更改。  
  
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a>使用 LocBaml 生成新的 .resources.dll 文件

通过使用 LocBaml 分析 HelloApp.resources.dll 而标识的内容已被翻译，且必须合并回原始应用程序。 使用 `generate` 或 `-g` 选项生成新的 .resources.dll 文件。  
  
1. 使用下列语法来生成新的 HelloApp.resources.dll 文件。 将区域性标记为 zh-CN (/cul:zh-CN)。  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US`  

   > [!NOTE]
   > 如果输入文件 Hello.csv 与可执行文件 LocBaml.exe 不在的同一目录中，请移动其中一个文件以使两个文件都位于同一目录中。  
  
2. 将 *C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll* 目录中的旧 *HelloApp.resources.dll* 文件替换为新创建的 *HelloApp.resources.dll* 文件。  
  
3. 应在你的应用程序中将“Hello World”和“Goodbye World”翻译过来。  
  
4. 若要翻译到不同的区域性设置，请使用目标语言的区域设置。 下列示例演示了如何翻译为加拿大法语：  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA`  
  
5. 在主应用程序程序集所在的程序集，创建一个新的特定于区域性的文件夹，以容纳新的附属程序集。 对于加拿大法语，该文件夹将为 fr-CA。  
  
6. 将生成的附属程序集复制到新建文件夹。  
  
7. 若要测试新的附属程序集，你需要更改应用程序将在其下运行的区域性设置。 可以通过两种方法执行此操作：  
  
   - 更改操作系统的区域设置。
  
   - 在你的应用程序中，将下列代码添加到 App.xaml.cs 中：  
  
     [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
     [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
     [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
## <a name="tips-for-using-locbaml"></a>使用 LocBaml 的提示  
  
- 所有定义自定义控件的依赖程序集必须复制到 LocBaml 的本地目录，或安装到 GAC。 这是必需的，因为本地化 API 在读取二进制 XAML (BAML) 时必须具有对依赖程序集的访问权限。  
  
- 如果主程序集已签名，则生成的资源 DLL 也必须签名以进行加载。  
  
- 本地化的资源 DLL 的版本需与主程序集进行同步。
  
## <a name="see-also"></a>另请参阅

- [WPF 的全球化](globalization-for-wpf.md)
- [使用自动布局概述](use-automatic-layout-overview.md)
