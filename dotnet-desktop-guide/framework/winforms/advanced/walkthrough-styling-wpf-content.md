---
title: 演练：样式 WPF 内容
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: f7acec4edb31dba0aa014943dde7f758fe8e4575
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957391"
---
# <a name="walkthrough-style-wpf-content"></a>演练：样式 WPF 内容

本文介绍如何将样式应用于 Windows 窗体上承载的 Windows Presentation Foundation (WPF) 控件。

## <a name="prerequisites"></a>先决条件

若要完成本演练，必须具有 Visual Studio。

## <a name="create-the-project"></a>创建项目

打开 Visual Studio，并在名为的 Visual Basic 或 Visual c # 中创建新的 Windows 窗体应用程序项目 `StylingWpfContent` 。

> [!NOTE]
> 承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。

## <a name="create-the-wpf-control-types"></a>创建 WPF 控件类型

将 WPF 控件类型添加到项目后，就可在 <xref:System.Windows.Forms.Integration.ElementHost> 控件中托管它。

1. 将新的 WPF <xref:System.Windows.Controls.UserControl> 项目添加到解决方案。 使用控件类型的默认名称，`UserControl1.xaml`。 有关详细信息，请参阅 [演练：在设计时在 Windows 窗体上创建新的 WPF 内容](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。

2. 在设计视图中，请确保已选中 `UserControl1`。

3. 在 " **属性** " 窗口中，将和属性的值设置 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> 为 **200**。

4. 向添加一个 <xref:System.Windows.Controls.Button?displayProperty=nameWithType> 控件 <xref:System.Windows.Controls.UserControl> ，并将属性的值设置 <xref:System.Windows.Controls.ContentControl.Content%2A> 为 " **取消**"。

5. 将第二个 <xref:System.Windows.Controls.Button?displayProperty=nameWithType> 控件添加到 <xref:System.Windows.Controls.UserControl> ，并将属性的值设置 <xref:System.Windows.Controls.ContentControl.Content%2A> 为 **"确定"**。

6. 生成项目。

## <a name="apply-a-style-to-a-wpf-control"></a>将样式应用到 WPF 控件

可对 WPF 控件应用不同样式以更改它的外观和行为。

1. 在 Windows 窗体设计器中打开 `Form1`。

1. 在 " **工具箱**" 中，双击在 `UserControl1` `UserControl1` 窗体上创建的实例。

   `UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。

1. 在的智能标记面板中 `elementHost1` ，单击下拉列表中的 " **编辑托管内容** "。

   `UserControl1` 在 WPF 设计器中打开。

1. 在 XAML 视图中，将以下 XAML 插到 `<UserControl>` 开始标记后面。 此 XAML 创建具有对比渐变边框的渐变。 单击此控件后，将更改渐变以生成按下按钮的外观。 有关详细信息，请参阅 [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)。

   ```xaml
   <UserControl.Resources>
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#FFF" Offset="0.0"/>
        <GradientStop Color="#CCC" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#BBB" Offset="0.0"/>
        <GradientStop Color="#EEE" Offset="0.1"/>
        <GradientStop Color="#EEE" Offset="0.9"/>
        <GradientStop Color="#FFF" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#444" Offset="0.0"/>
        <GradientStop Color="#888" Offset="1.0"/>
    </LinearGradientBrush>

    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="{x:Type Button}">
                    <Grid x:Name="Grid">
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>
                    </Grid>
                    <ControlTemplate.Triggers>
                        <Trigger Property="IsPressed" Value="true">
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>
                        </Trigger>
                    </ControlTemplate.Triggers>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>
   </UserControl.Resources>
   ```

1. 通过在 " `SimpleButton` 取消" 按钮的标记中插入以下 XAML，将上一步中定义的样式应用于 "取消" 按钮 `<Button>` 。 

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   按钮声明将类似于以下 XAML：

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. 生成项目。

1. 在 Windows 窗体设计器中打开 `Form1`。

1. 将新样式应用到按钮控件中。

1. 从 " **调试** " 菜单中，选择 " **启动调试** " 以运行应用程序。

1. 单击 **"确定" 和 "** **取消** " 按钮，查看不同之处。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [迁移和互操作性](/dotnet/framework/wpf/advanced/migration-and-interoperability)
- [使用 WPF 控件](using-wpf-controls.md)
- [在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [XAML 概述 (WPF)](/dotnet/desktop-wpf/fundamentals/xaml)
- [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
