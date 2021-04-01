---
title: LINQ to XML 数据绑定示例
ms.date: 10/22/2019
ms.topic: sample
helpviewer_keywords:
- linq to xml data binding sample
ms.openlocfilehash: aac814e4768a863a93e69e34cd18c941a9b35c89
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972528"
---
# <a name="linq-to-xml-data-binding-sample"></a>LINQ to XML 数据绑定示例

本文介绍了 LinqToXmlDataBinding 示例，它是将用户界面组件绑定到嵌入的 XML 数据源的 Windows Presentation Foundation (WPF) 应用程序。

## <a name="overview"></a>概述

LinqToXmlDataBinding 示例是包含 c # 和 XAML 源文件 (WPF) 应用的 Windows Presentation Foundation。 嵌入的 XML 文档定义书籍列表。 应用使用户能够查看、添加、删除和编辑书籍条目。

有两个主要源文件：

- L2DBForm.xaml 包含主窗口的用户界面 (UI) 的 XAML 声明代码[](l2dbform-xaml-source-code.md)。 它还包含一个为书籍列表定义数据提供程序和嵌入式 XML 文档的窗口资源部分。

- L2DBForm.xaml.cs 包含与用户界面关联的初始化和事件处理方法[](l2dbform-xaml-cs-source-code.md)。

主窗口分为以下四个垂直用户界面部分：

- “XML”显示嵌入式书籍列表的原始 XML 源。

- “Book List”（书籍列表）以标准文本形式显示书籍项，允许用户选择和删除各项。

- “Edit Selected Book”（编辑所选书籍）允许用户编辑与当前所选书籍项关联的值。

- “Add New Book”（添加新书籍）允许根据用户输入的值创建新书。

## <a name="run-the-sample"></a>运行示例

本部分演示如何在 Visual Studio 中创建和生成 LinqToXmlDataBinding 项目，以及如何 (WPF) 应用程序运行生成的 LinqToXmlDataBinding Windows Presentation Foundation。

### <a name="create-the-project"></a>创建项目

1. 打开 Visual Studio 并创建一个名为 LinqToXmlDataBinding 的 C# WPF 应用。

   该项目应面向 .NET Framework 3.5（或更高版本）。

1. 为以下 .NET 程序集添加项目引用（如果尚不存在）：

    - System.Data
    - System.Data.DataSetExtensions
    - System.Xml
    - System.Xml

1. 按 **Ctrl** + **Shift** + **B** 生成解决方案，然后按 **F5** 运行该解决方案。

   该项目应正确编译而不出错，并作为一般 WPF 应用程序运行。

### <a name="add-code"></a>添加代码

1. 在 **解决方案资源管理器** 中，将源文件 **window1.xaml** 重命名为 **l2xdbform.xaml**。

   相关的源文件 Window1.xaml 会自动重命名为 L2xdbform.xaml。

1. 将 **l2xdbform.xaml** 文件中找到的源代码替换为 [l2dbform.xaml 源代码](l2dbform-xaml-source-code.md)。 使用 XAML 源视图来处理此文件。

1. 同样，请将 **l2xdbform.xaml** 中的源替换为 [l2dbform.xaml 源代码](l2dbform-xaml-cs-source-code.md)。

1. 在文件 **app.xaml** 中，将出现的所有字符串 **Window1.xaml** 替换为 **l2xdbform.xaml**。

1. 按 **Ctrl** + **Shift** + **B** 生成解决方案。

### <a name="run-the-app"></a>运行应用

用户可以使用 LinqToXmlDataBinding 应用查看和操作以嵌入 XML 元素形式存储的书籍的列表。 按 **f5** ("开始调试") 或按 **Ctrl** + **f5** ("启动但不调试) " 来运行应用。

显示标题为“使用 LINQ to XML 的 WPF 数据绑定”的程序窗口。

UI 的顶部显示表示书籍列表的原始 **XML** 。 它使用 WPF <xref:System.Windows.Controls.TextBlock> 控件来显示，该控件不启用通过鼠标或键盘交互。

标记为“书籍列表”的第二个垂直区域以排序的纯文本列表形式显示书籍。 它使用启用通过鼠标或键盘进行选择的 <xref:System.Windows.Controls.ListBox> 控件。

### <a name="add-and-delete-books"></a>添加和删除书籍

若要向列表中添加新书籍，请在上一节 "  <xref:System.Windows.Controls.TextBox> **添加新书籍**" 中的 "ID" 和 "值" 控件中输入值，然后选择 "**添加图书**"。 本书将追加到书籍和 XML 清单中的列表中。 此程序不验证输入值。

若要从列表中删除现有书籍，请在 " **书籍列表** " 部分中将其选中，然后选择 " **删除所选书籍**"。 本书条目将从书籍和原始 XML 源列表中删除。

### <a name="edit-a-book-entry"></a>编辑书条目

1. 在第二个“书籍列表”区域中选择书籍条目。

   其当前值将显示在 " **编辑所选书籍** " 部分中。

1. 使用键盘编辑值。 一旦任一 <xref:System.Windows.Controls.TextBox> 控件失去焦点，更改就会自动传播到 XML 源和书籍列表。
