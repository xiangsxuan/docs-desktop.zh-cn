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
# <a name="linq-to-xml-data-binding-sample"></a><span data-ttu-id="46d5c-102">LINQ to XML 数据绑定示例</span><span class="sxs-lookup"><span data-stu-id="46d5c-102">LINQ to XML data binding sample</span></span>

<span data-ttu-id="46d5c-103">本文介绍了 LinqToXmlDataBinding 示例，它是将用户界面组件绑定到嵌入的 XML 数据源的 Windows Presentation Foundation (WPF) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="46d5c-103">This article describes the LinqToXmlDataBinding sample, a Windows Presentation Foundation (WPF) app that binds user interface components to an embedded XML data source.</span></span>

## <a name="overview"></a><span data-ttu-id="46d5c-104">概述</span><span class="sxs-lookup"><span data-stu-id="46d5c-104">Overview</span></span>

<span data-ttu-id="46d5c-105">LinqToXmlDataBinding 示例是包含 c # 和 XAML 源文件 (WPF) 应用的 Windows Presentation Foundation。</span><span class="sxs-lookup"><span data-stu-id="46d5c-105">The LinqToXmlDataBinding sample is a Windows Presentation Foundation (WPF) app that contains C# and XAML source files.</span></span> <span data-ttu-id="46d5c-106">嵌入的 XML 文档定义书籍列表。</span><span class="sxs-lookup"><span data-stu-id="46d5c-106">An embedded XML document defines a list of books.</span></span> <span data-ttu-id="46d5c-107">应用使用户能够查看、添加、删除和编辑书籍条目。</span><span class="sxs-lookup"><span data-stu-id="46d5c-107">The app enables the user to view, add, delete, and edit the book entries.</span></span>

<span data-ttu-id="46d5c-108">有两个主要源文件：</span><span class="sxs-lookup"><span data-stu-id="46d5c-108">There are two primary source files:</span></span>

- <span data-ttu-id="46d5c-109">L2DBForm.xaml 包含主窗口的用户界面 (UI) 的 XAML 声明代码[](l2dbform-xaml-source-code.md)。</span><span class="sxs-lookup"><span data-stu-id="46d5c-109">[L2DBForm.xaml](l2dbform-xaml-source-code.md) contains the XAML declaration code for the user interface (UI) of the main window.</span></span> <span data-ttu-id="46d5c-110">它还包含一个为书籍列表定义数据提供程序和嵌入式 XML 文档的窗口资源部分。</span><span class="sxs-lookup"><span data-stu-id="46d5c-110">It also contains a window resource section that defines a data provider and an embedded XML document for the book listings.</span></span>

- <span data-ttu-id="46d5c-111">L2DBForm.xaml.cs 包含与用户界面关联的初始化和事件处理方法[](l2dbform-xaml-cs-source-code.md)。</span><span class="sxs-lookup"><span data-stu-id="46d5c-111">[L2DBForm.xaml.cs](l2dbform-xaml-cs-source-code.md) contains the initialization and event-handling methods associated with the UI.</span></span>

<span data-ttu-id="46d5c-112">主窗口分为以下四个垂直用户界面部分：</span><span class="sxs-lookup"><span data-stu-id="46d5c-112">The main window is divided into the following four vertical UI sections:</span></span>

- <span data-ttu-id="46d5c-113">“XML”显示嵌入式书籍列表的原始 XML 源。</span><span class="sxs-lookup"><span data-stu-id="46d5c-113">**XML** displays the raw XML source of the embedded book listing.</span></span>

- <span data-ttu-id="46d5c-114">“Book List”（书籍列表）以标准文本形式显示书籍项，允许用户选择和删除各项。</span><span class="sxs-lookup"><span data-stu-id="46d5c-114">**Book List** displays the book entries as standard text and enables the user to select and delete individual entries.</span></span>

- <span data-ttu-id="46d5c-115">“Edit Selected Book”（编辑所选书籍）允许用户编辑与当前所选书籍项关联的值。</span><span class="sxs-lookup"><span data-stu-id="46d5c-115">**Edit Selected Book** enables the user to edit the values associated with the currently selected book entry.</span></span>

- <span data-ttu-id="46d5c-116">“Add New Book”（添加新书籍）允许根据用户输入的值创建新书。</span><span class="sxs-lookup"><span data-stu-id="46d5c-116">**Add New Book** enables the creation of a new book entry based on values entered by the user.</span></span>

## <a name="run-the-sample"></a><span data-ttu-id="46d5c-117">运行示例</span><span class="sxs-lookup"><span data-stu-id="46d5c-117">Run the sample</span></span>

<span data-ttu-id="46d5c-118">本部分演示如何在 Visual Studio 中创建和生成 LinqToXmlDataBinding 项目，以及如何 (WPF) 应用程序运行生成的 LinqToXmlDataBinding Windows Presentation Foundation。</span><span class="sxs-lookup"><span data-stu-id="46d5c-118">This section shows how to create and build the LinqToXmlDataBinding project in Visual Studio, and how to run the resulting LinqToXmlDataBinding Windows Presentation Foundation (WPF) app.</span></span>

### <a name="create-the-project"></a><span data-ttu-id="46d5c-119">创建项目</span><span class="sxs-lookup"><span data-stu-id="46d5c-119">Create the project</span></span>

1. <span data-ttu-id="46d5c-120">打开 Visual Studio 并创建一个名为 LinqToXmlDataBinding 的 C# WPF 应用。</span><span class="sxs-lookup"><span data-stu-id="46d5c-120">Open Visual Studio and create a C# **WPF App** named **LinqToXmlDataBinding**.</span></span>

   <span data-ttu-id="46d5c-121">该项目应面向 .NET Framework 3.5（或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="46d5c-121">The project should target the .NET Framework 3.5 (or later).</span></span>

1. <span data-ttu-id="46d5c-122">为以下 .NET 程序集添加项目引用（如果尚不存在）：</span><span class="sxs-lookup"><span data-stu-id="46d5c-122">If not already present, add project references for the following .NET assemblies:</span></span>

    - <span data-ttu-id="46d5c-123">System.Data</span><span class="sxs-lookup"><span data-stu-id="46d5c-123">System.Data</span></span>
    - <span data-ttu-id="46d5c-124">System.Data.DataSetExtensions</span><span class="sxs-lookup"><span data-stu-id="46d5c-124">System.Data.DataSetExtensions</span></span>
    - <span data-ttu-id="46d5c-125">System.Xml</span><span class="sxs-lookup"><span data-stu-id="46d5c-125">System.Xml</span></span>
    - <span data-ttu-id="46d5c-126">System.Xml</span><span class="sxs-lookup"><span data-stu-id="46d5c-126">System.Xml</span></span>

1. <span data-ttu-id="46d5c-127">按 **Ctrl** + **Shift** + **B** 生成解决方案，然后按 **F5** 运行该解决方案。</span><span class="sxs-lookup"><span data-stu-id="46d5c-127">Build the solution by pressing **Ctrl**+**Shift**+**B**, then run it by pressing **F5**.</span></span>

   <span data-ttu-id="46d5c-128">该项目应正确编译而不出错，并作为一般 WPF 应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="46d5c-128">The project should compile without errors and run as a generic WPF application.</span></span>

### <a name="add-code"></a><span data-ttu-id="46d5c-129">添加代码</span><span class="sxs-lookup"><span data-stu-id="46d5c-129">Add code</span></span>

1. <span data-ttu-id="46d5c-130">在 **解决方案资源管理器** 中，将源文件 **window1.xaml** 重命名为 **l2xdbform.xaml**。</span><span class="sxs-lookup"><span data-stu-id="46d5c-130">In **Solution Explorer**, rename the source file **Window1.xaml** to **L2XDBForm.xaml**.</span></span>

   <span data-ttu-id="46d5c-131">相关的源文件 Window1.xaml 会自动重命名为 L2xdbform.xaml。</span><span class="sxs-lookup"><span data-stu-id="46d5c-131">The dependent source file Window1.xaml.cs is automatically renamed to L2XDBForm.xaml.cs.</span></span>

1. <span data-ttu-id="46d5c-132">将 **l2xdbform.xaml** 文件中找到的源代码替换为 [l2dbform.xaml 源代码](l2dbform-xaml-source-code.md)。</span><span class="sxs-lookup"><span data-stu-id="46d5c-132">Replace the source code found in the file **L2XDBForm.xaml** with the [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span> <span data-ttu-id="46d5c-133">使用 XAML 源视图来处理此文件。</span><span class="sxs-lookup"><span data-stu-id="46d5c-133">Use the XAML source view to work with this file.</span></span>

1. <span data-ttu-id="46d5c-134">同样，请将 **l2xdbform.xaml** 中的源替换为 [l2dbform.xaml 源代码](l2dbform-xaml-cs-source-code.md)。</span><span class="sxs-lookup"><span data-stu-id="46d5c-134">Similarly, replace the source in **L2XDBForm.xaml.cs** with the [L2DBForm.xaml.cs source code](l2dbform-xaml-cs-source-code.md).</span></span>

1. <span data-ttu-id="46d5c-135">在文件 **app.xaml** 中，将出现的所有字符串 **Window1.xaml** 替换为 **l2xdbform.xaml**。</span><span class="sxs-lookup"><span data-stu-id="46d5c-135">In the file **App.xaml**, replace all occurrences of the string **Window1.xaml** with **L2XDBForm.xaml**.</span></span>

1. <span data-ttu-id="46d5c-136">按 **Ctrl** + **Shift** + **B** 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="46d5c-136">Build the solution by pressing **Ctrl**+**Shift**+**B**.</span></span>

### <a name="run-the-app"></a><span data-ttu-id="46d5c-137">运行应用</span><span class="sxs-lookup"><span data-stu-id="46d5c-137">Run the app</span></span>

<span data-ttu-id="46d5c-138">用户可以使用 LinqToXmlDataBinding 应用查看和操作以嵌入 XML 元素形式存储的书籍的列表。</span><span class="sxs-lookup"><span data-stu-id="46d5c-138">The LinqToXmlDataBinding app enables the user to view and manipulate a list of books that's stored as an embedded XML element.</span></span> <span data-ttu-id="46d5c-139">按 **f5** ("开始调试") 或按 **Ctrl** + **f5** ("启动但不调试) " 来运行应用。</span><span class="sxs-lookup"><span data-stu-id="46d5c-139">Run the app by pressing **F5** (Start Debugging) or **Ctrl**+**F5** (Start Without Debugging).</span></span>

<span data-ttu-id="46d5c-140">显示标题为“使用 LINQ to XML 的 WPF 数据绑定”的程序窗口。</span><span class="sxs-lookup"><span data-stu-id="46d5c-140">A program window with the title **WPF Data Binding using LINQ to XML** appears.</span></span>

<span data-ttu-id="46d5c-141">UI 的顶部显示表示书籍列表的原始 **XML** 。</span><span class="sxs-lookup"><span data-stu-id="46d5c-141">The top section of the UI displays the raw **XML** that represents the book list.</span></span> <span data-ttu-id="46d5c-142">它使用 WPF <xref:System.Windows.Controls.TextBlock> 控件来显示，该控件不启用通过鼠标或键盘交互。</span><span class="sxs-lookup"><span data-stu-id="46d5c-142">It is displayed using a WPF <xref:System.Windows.Controls.TextBlock> control, which does not enable interaction through the mouse or keyboard.</span></span>

<span data-ttu-id="46d5c-143">标记为“书籍列表”的第二个垂直区域以排序的纯文本列表形式显示书籍。</span><span class="sxs-lookup"><span data-stu-id="46d5c-143">The second vertical section, labeled **Book List**, displays the books as a plain text ordered list.</span></span> <span data-ttu-id="46d5c-144">它使用启用通过鼠标或键盘进行选择的 <xref:System.Windows.Controls.ListBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="46d5c-144">It uses a <xref:System.Windows.Controls.ListBox> control that enables selection though the mouse or keyboard.</span></span>

### <a name="add-and-delete-books"></a><span data-ttu-id="46d5c-145">添加和删除书籍</span><span class="sxs-lookup"><span data-stu-id="46d5c-145">Add and delete books</span></span>

<span data-ttu-id="46d5c-146">若要向列表中添加新书籍，请在上一节 "  <xref:System.Windows.Controls.TextBox> **添加新书籍**" 中的 "ID" 和 "值" 控件中输入值，然后选择 "**添加图书**"。</span><span class="sxs-lookup"><span data-stu-id="46d5c-146">To add a new book to the list, enter values into the **ID** and **Value** <xref:System.Windows.Controls.TextBox> controls in the last section, **Add New Book**, and then select **Add Book**.</span></span> <span data-ttu-id="46d5c-147">本书将追加到书籍和 XML 清单中的列表中。</span><span class="sxs-lookup"><span data-stu-id="46d5c-147">The book is appended to the list in both the book and XML listings.</span></span> <span data-ttu-id="46d5c-148">此程序不验证输入值。</span><span class="sxs-lookup"><span data-stu-id="46d5c-148">This program does not validate input values.</span></span>

<span data-ttu-id="46d5c-149">若要从列表中删除现有书籍，请在 " **书籍列表** " 部分中将其选中，然后选择 " **删除所选书籍**"。</span><span class="sxs-lookup"><span data-stu-id="46d5c-149">To delete an existing book from the list, select it in the **Book List** section, and then select **Remove Selected Book**.</span></span> <span data-ttu-id="46d5c-150">本书条目将从书籍和原始 XML 源列表中删除。</span><span class="sxs-lookup"><span data-stu-id="46d5c-150">The book entry is removed from both the book and the raw XML source listings.</span></span>

### <a name="edit-a-book-entry"></a><span data-ttu-id="46d5c-151">编辑书条目</span><span class="sxs-lookup"><span data-stu-id="46d5c-151">Edit a book entry</span></span>

1. <span data-ttu-id="46d5c-152">在第二个“书籍列表”区域中选择书籍条目。</span><span class="sxs-lookup"><span data-stu-id="46d5c-152">Select the book entry in the second **Book List** section.</span></span>

   <span data-ttu-id="46d5c-153">其当前值将显示在 " **编辑所选书籍** " 部分中。</span><span class="sxs-lookup"><span data-stu-id="46d5c-153">Its current values are displayed in the **Edit Selected Book** section.</span></span>

1. <span data-ttu-id="46d5c-154">使用键盘编辑值。</span><span class="sxs-lookup"><span data-stu-id="46d5c-154">Edit the values using the keyboard.</span></span> <span data-ttu-id="46d5c-155">一旦任一 <xref:System.Windows.Controls.TextBox> 控件失去焦点，更改就会自动传播到 XML 源和书籍列表。</span><span class="sxs-lookup"><span data-stu-id="46d5c-155">As soon as either <xref:System.Windows.Controls.TextBox> control loses focus, changes are automatically propagated to the XML source and book listings.</span></span>
