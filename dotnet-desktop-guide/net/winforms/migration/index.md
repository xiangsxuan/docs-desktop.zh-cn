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
# <a name="how-to-migrate-a-windows-forms-desktop-app-to-net-5"></a>如何将 Windows 窗体桌面应用迁移到 .NET 5

本文介绍如何将 Windows 窗体桌面应用从 .NET Framework 迁移到 .NET 5 或更高版本。 .NET SDK 支持 Windows 窗体应用程序。 Windows 窗体仍是仅适用于 Windows 的框架，并且只能在 Windows 上运行。

将应用从 .NET Framework 迁移到 .NET 5 通常需要一个新的项目文件。 NET 5 使用 SDK 样式的项目文件，而 .NET Framework 通常使用较旧的 Visual Studio 项目文件。 如果你曾经在文本编辑器中打开过 Visual Studio 项目文件，你就会知道它有多么详细。 SDK 样式的项目较小，不需要像旧版项目文件格式那样多的条目。

要详细了解 .NET 5，请参阅 [.NET 简介](/dotnet/core/introduction)。

## <a name="prerequisites"></a>先决条件

- [Visual Studio 2019 版本 16.8 预览版](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms)

  - 选择 [Visual Studio Desktop 工作负载](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)。

  - 选择 [.NET 5 单个组件](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)。

- 预览 Visual Studio 中的 WinForms 设计器。

  若要启用该设计器，请转到“工具” > “选项” > “环境” > “预览功能”，然后选择“将预览版 Windows 窗体设计器用于 .NET Core 应用”选项。

- 本文使用[匹配游戏](https://github.com/dotnet/samples/tree/master/windowsforms/matching-game/net45/)示例应用。 若想使用该示例应用进行操作，请下载该应用程序并在 Visual Studio 中将其打开。 否则，请使用自己的应用。

### <a name="consider"></a>考虑

迁移 .NET Framework Windows 窗体应用程序时，必须考虑以下几个事项。

01. 检查应用程序是否适合迁移。

    使用 [.NET 可移植性分析器](/dotnet/standard/analyzers/portability-analyzer)确定项目将会迁移到 .NET 5。 如果项目存在 .NET 5 相关问题，分析器可帮助你识别这些问题。 .NET 可移植性分析器工具可安装为 Visual Studio 扩展，也可在命令行中使用。 有关详细信息，请参阅 [.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer)。

01. 使用的是不同版本的 Windows 窗体。

    发布 .NET Core 3.0 时，Windows 窗体[在 GitHub 上开放源代码](https://github.com/dotnet/winforms)。 .NET 5 的 Windows 窗体的代码是 .NET Framework Windows 窗体代码库的一个分支。 可能存在一些差异导致应用难以迁移。

01. 使用 [Windows 兼容包][compat-pack]可有助于进行迁移。

    某些 API 可在 .NET Framework 中使用，但不可用于 .NET 5。 [Windows 兼容包][compat-pack]增加了很多这些 API，有助于使 Windows 窗体应用与 .NET 5 兼容。

01. 更新项目使用的 NuGet 包。

    在执行任何迁移之前使用最新版 NuGet 包始终是一个不错的做法。 如果应用程序引用任何 NuGet 包，请将它们更新到最新版本。 确保成功生成应用程序。 升级后，如果存在任何包错误，请将包降级到不会破坏代码的最新版本。

## <a name="back-up-your-projects"></a>备份项目

迁移项目的第一步是备份项目！ 如果出现问题，可以通过还原备份将代码还原为其原始状态。 不要依赖于 .NET 可移植性分析器等工具来备份项目，即使它们似乎可以完成备份。 最好是亲自创建原始项目的副本。

## <a name="nuget-packages"></a>NuGet 包

如果项目引用了 NuGet 包，则项目文件夹中可能包含 packages.config 文件。 对于 SDK 样式的项目，NuGet 包引用是在项目文件中配置的。 Visual Studio 项目文件也可以选择在项目文件中定义 NuGet 包。 .NET 5 不会将 packages.config 用于 NuGet 包。 在迁移之前，必须将 NuGet 包引用迁移到项目文件中。

要迁移 packages.config 文件，请执行以下步骤：

01. 在“解决方案资源管理器”中，找到要迁移的项目。
02. 右键单击“packages.config” > “将 packages.config 迁移到 PackageReference”。
03. 选择所有顶级包。

系统会生成一个生成报告，让你知道与迁移 NuGet 包有关的任何问题。

## <a name="project-file"></a>项目文件

迁移应用的下一步是转换项目文件。 如前文所述，NET 5 使用 SDK 样式的项目文件，不会加载 .NET Framework 使用的 Visual Studio 项目文件。 但是，你可能已经在使用 SDK 样式的项目。 你可以轻松地在 Visual Studio 中发现差异。 在“解决方案资源管理器”中右键单击项目文件，查找“编辑项目文件”菜单选项 。 如果此菜单项缺失，则你使用的是旧版 Visual Studio 项目格式，需要升级。

转换解决方案中的每个项目。 如果你使用的是之前引用的示例应用，则会转换 MatchingGame 和 MatchingGame.Logic 项目 。

要转换项目，请执行以下步骤：

01. 在“解决方案资源管理器”中，找到要迁移的项目。
01. 右键单击项目，并选择“上传项目”。
01. 右键单击项目，并选择“编辑项目文件”。
01. 复制项目 XML 并将其粘贴到文本编辑器中。 你需要一个副本，以便轻松地将内容移动到新项目中。
01. 擦除文件的内容，并粘贴以下 XML：

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
    > 库不需要定义 `<OutputType>` 设置。 如果要升级库项目，请删除该条目。

此 XML 提供项目的基本结构。 但是，它不包含旧项目文件中的任何设置。 使用之前复制到文本编辑器的旧项目信息执行以下步骤：

01. 将以下元素从旧项目文件复制到新项目文件的 `<PropertyGroup>` 元素中：

    - `<RootNamespace>`
    - `<AssemblyName>`

    你的项目文件应类似于以下 XML：

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

01. 将 `<ItemGroup>` 元素从包含 `<ProjectReference>` 或 `<PackageReference>` 的旧项目文件复制到 `</PropertyGroup>` 结束标记之后的新文件中。

    你的项目文件应类似于以下 XML：

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

    `<ProjectReference>` 元素不需要 `<Project>` 和 `<Name>` 子级，因此你可以删除这些设置：

    ```xml
    <ItemGroup>
      <ProjectReference Include="..\MatchingGame.Logic\MatchingGame.Logic.csproj" />
    </ItemGroup>
    ```

### <a name="resources-and-settings"></a>资源和设置

关于 .NET Framework 项目和 .NET 5 使用的 SDK 样式项目之间的差异，需要注意的一点是，.NET Framework 项目对代码文件使用选择加入模型。 要编译的任何代码文件都需要在项目文件中进行显式地定义。 SDK 样式项目相反，它们默认采用选择退出行为：从项目的目录及其下级目录开始的所有代码文件都会自动包含在你的项目中。 如果这些项很简单且没有设置，则无需迁移它们。 这对于其他常见文件（如 resx）是相同的。

Windows 窗体项目还包含 Properties/Settings.settings 和 Properties/Resources.resx 等 Windows 窗体项目特定文件 。 可能需要迁移这些文件，因为它们在原始项目中进行了声明。

将旧项目文件中的条目复制到新项目的 `<ItemGroup>` 元素中。 复制条目后，将所有 `<Compile Include="value">` 元素更改为改用 `Update` 属性而不是 `Include`。

- 导入 Settings.settings 文件的配置。

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

  请注意，Properties\Settings.settings 项仍然为 `Include`。 该项目不会自动包含 settings 文件。

  > [!IMPORTANT]
  > Visual Basic 项目通常使用“我的项目”文件夹来存储默认项目设置文件，而 C# 项目通常使用“属性”文件夹 。
  
- 导入任何 resx 文件（如 properties/Resources.resx 文件）的配置 。 请注意，`Include` 属性已更改为 `<Compile>` 元素上的 `Update`，并且从 `<EmbeddedResource>` 中删除了 `<SubType>`：

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
  > Visual Basic 项目通常使用“我的项目”文件夹来存储默认项目资源文件，而 C# 项目通常使用“属性”文件夹 。

### <a name="visual-basic"></a>Visual Basic

Visual Basic 语言项目需要额外的配置。

01. 导入配置文件“My Project\Application.myapp”设置。 请注意，`<Compile>` 元素使用 `Update` 属性而不是 `Include` 属性。

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

01. 向 `<PropertyGroup>` 元素添加 `<MyType>WindowsForms</MyType>` 设置：

    ```xml
    <PropertyGroup>
      (contains settings previously described)

      <MyType>WindowsForms</MyType>
    </PropertyGroup>
    ```

    此设置将导入 Visual Basic 程序员熟悉的 `My` 命名空间成员。

01. 导入项目定义的命名空间。

    Visual Basic 项目可自动将命名空间导入每个代码文件中。 将 `<ItemGroup>` 元素从包含 `<Import>` 的旧项目文件复制到 `</PropertyGroup>` 结束标记之后的新文件中。

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

    如果找不到任何 `<Import>` 语句，或项目编译失败，请确保你至少在项目中定义了以下 `<Import>` 语句：

    ```xml
    <ItemGroup>
      <Import Include="System.Data" />
      <Import Include="System.Drawing" />
      <Import Include="System.Windows.Forms" />
    </ItemGroup>
    ```

01. 从原始项目中，将 `<Option*>` 和 `<StartupObject>` 设置复制到 `<PropertyGroup>` 元素：

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

### <a name="reload-the-project"></a>重载项目

将项目转换为新的 SDK 样式格式后，请在 Visual Studio 中重载项目：

01. 在“解决方案资源管理器”中，找到要转换的项目。
01. 右键单击项目，选择“重载项目”。

    如果项目加载失败，则可能是因为在项目的 XML 中引入了一个错误。 打开项目文件以进行编辑，并尝试识别和修复错误。 如果找不到错误，请尝试重启。

## <a name="edit-appconfig"></a>编辑 App.config

如果你的应用包含 app.config 文件，则删除 `<supportedRuntime>` 元素：

```xml
<supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
```

对于 App.config 文件，有一些事项需要考虑。 .NET Framework 中的 App.config 文件不仅用于配置应用，还用于配置运行时设置和行为，如日志记录。 .NET 5+（和 .NET Core）中的 App.config 文件不再用于运行时配置。 如果 App.config 文件包含这些部分，则不会考虑这些部分。

## <a name="add-the-compatibility-package"></a>添加兼容性包

如果项目文件正确加载，但项目编译失败，则会收到类似以下形式的错误消息：

- 找不到类型或命名空间 \<some name>
- 当前上下文中不存在名称 \<some name>

你可能需要向应用添加 [`Microsoft.Windows.Compatibility`](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/) 包。 此包会添加 .NET Framework 中的约 21,000 个 .NET API，如 `System.Configuration.ConfigurationManager` 类和用于与 Windows 注册表交互的 API。 添加 `Microsoft.Windows.Compatibility` 程序包。

编辑项目文件并添加以下 `<ItemGroup>` 元素：

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.Windows.Compatibility" Version="5.0.0" />
</ItemGroup>
```

## <a name="test-your-app"></a>测试应用

完成应用迁移后，请进行测试！

## <a name="next-steps"></a>后续步骤

- 了解 [Windows 窗体的重大变更](/dotnet/core/compatibility/winforms)。
- 详细了解 [Windows 兼容包][compat-pack]。

[compat-pack]: /dotnet/core/porting/windows-compat-pack
