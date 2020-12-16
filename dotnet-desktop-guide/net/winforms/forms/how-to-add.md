---
title: 向项目添加窗体
description: 在 Visual Studio 中向 .NET Windows 窗体项目添加新窗体
ms.date: 10/26/2020
helpviewer_keywords:
- Windows Forms, create add form
ms.openlocfilehash: fb35c1b62ca0b7a21581c350ddca7f21f45ec27f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941955"
---
# <a name="how-to-add-a-form-to-a-project-windows-forms-net"></a><span data-ttu-id="6a894-103">如何向项目添加窗体（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="6a894-103">How to add a form to a project (Windows Forms .NET)</span></span>

<span data-ttu-id="6a894-104">在 Visual Studio 中向项目添加窗体。</span><span class="sxs-lookup"><span data-stu-id="6a894-104">Add forms to your project with Visual Studio.</span></span> <span data-ttu-id="6a894-105">如果应用具有多个窗体，你可以选择哪个作为应用的启动窗体，并且可以同时显示多个窗体。</span><span class="sxs-lookup"><span data-stu-id="6a894-105">When your app has multiple forms, you can choose which is the startup form for your app, and you can display multiple forms at the same time.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="add-a-new-form"></a><span data-ttu-id="6a894-106">添加新窗体</span><span class="sxs-lookup"><span data-stu-id="6a894-106">Add a new form</span></span>

<span data-ttu-id="6a894-107">在 Visual Studio 中添加新窗体。</span><span class="sxs-lookup"><span data-stu-id="6a894-107">Add a new form with Visual Studio.</span></span>

01. <span data-ttu-id="6a894-108">在 Visual Studio 中，找到“项目资源管理器”窗格。</span><span class="sxs-lookup"><span data-stu-id="6a894-108">In Visual Studio, find the **Project Explorer** pane.</span></span> <span data-ttu-id="6a894-109">右键单击项目，然后选择“添加” > “窗体(Windows 窗体)” 。</span><span class="sxs-lookup"><span data-stu-id="6a894-109">Right-click on the project and choose **Add** > **Form (Windows Forms)**.</span></span>

    :::image type="content" source="media/how-to-add/right-click.png" alt-text="右键单击解决方案资源管理器，将新窗体添加到 Windows 窗体项目中":::

01. <span data-ttu-id="6a894-111">在“名称”框中键入窗体的名称，例如 MyNewForm。</span><span class="sxs-lookup"><span data-stu-id="6a894-111">In the **Name** box, type a name for your form, such as *MyNewForm*.</span></span> <span data-ttu-id="6a894-112">Visual Studio 将提供一个默认名称，这也是你可以使用的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="6a894-112">Visual Studio will provide a default and unique name that you may use.</span></span>

    :::image type="content" source="media/how-to-add/new-form-dialog.png" alt-text="在 Visual Studio 中为 Windows 窗体添加项目对话框":::

<span data-ttu-id="6a894-114">添加窗体后，Visual Studio 将打开窗体的窗体设计器。</span><span class="sxs-lookup"><span data-stu-id="6a894-114">Once the form has been added, Visual Studio opens the form designer for the form.</span></span>

## <a name="add-a-project-reference-to-a-form"></a><span data-ttu-id="6a894-115">向窗体添加项目引用</span><span class="sxs-lookup"><span data-stu-id="6a894-115">Add a project reference to a form</span></span>

<span data-ttu-id="6a894-116">如果源文件包含在窗体中，则可以通过将文件复制到项目所在文件夹来将窗体添加到项目。</span><span class="sxs-lookup"><span data-stu-id="6a894-116">If you have the source files to a form, you can add the form to your project by copying the files into the same folder as your project.</span></span> <span data-ttu-id="6a894-117">项目会自动引用项目的同一文件夹或子文件夹中的所有代码文件。</span><span class="sxs-lookup"><span data-stu-id="6a894-117">The project automatically references any code files that are in the same folder or child folder of your project.</span></span>

<span data-ttu-id="6a894-118">窗体由两个同名文件构成：form2.cs（form2 是文件名的示例）和 form2.Designer.cs  。</span><span class="sxs-lookup"><span data-stu-id="6a894-118">Forms are made up of two files that share the same name: _form2.cs_ (_form2_ being an example of a file name) and _form2.Designer.cs_.</span></span> <span data-ttu-id="6a894-119">有时会存在同名资源文件，即 form2.resx。</span><span class="sxs-lookup"><span data-stu-id="6a894-119">Sometimes a resource file exists, sharing the same name, _form2.resx_.</span></span> <span data-ttu-id="6a894-120">在上一个示例中，form2 表示基本文件名。</span><span class="sxs-lookup"><span data-stu-id="6a894-120">In in the previous example, _form2_ represents the base file name.</span></span> <span data-ttu-id="6a894-121">建议将所有相关文件复制到项目文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a894-121">You'll want to copy all related files to your project folder.</span></span>

<span data-ttu-id="6a894-122">也可使用 Visual Studio 将文件导入项目。</span><span class="sxs-lookup"><span data-stu-id="6a894-122">Alternatively, you can use Visual Studio to import a file into your project.</span></span> <span data-ttu-id="6a894-123">将现有文件添加到项目时，该文件将复制到项目所在文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a894-123">When you add an existing file to your project, the file is copied into the same folder as your project.</span></span>

01. <span data-ttu-id="6a894-124">在 Visual Studio 中，找到“项目资源管理器”窗格。</span><span class="sxs-lookup"><span data-stu-id="6a894-124">In Visual Studio, find the **Project Explorer** pane.</span></span> <span data-ttu-id="6a894-125">右键单击项目，然后选择“添加” > “现有项” 。</span><span class="sxs-lookup"><span data-stu-id="6a894-125">Right-click on the project and choose **Add** > **Existing Item**.</span></span>

    :::image type="content" source="media/how-to-add/existing-right-click.png" alt-text="右键单击解决方案资源管理器，将现有窗体添加到 Windows 窗体项目中":::

02. <span data-ttu-id="6a894-127">导航到包含窗体文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a894-127">Navigate to the folder containing your form files.</span></span>

03. <span data-ttu-id="6a894-128">选择 form2.cs 文件，其中 form2 是相关窗体文件的基本文件名 。</span><span class="sxs-lookup"><span data-stu-id="6a894-128">Select the _form2.cs_ file, where _form2_ is the base file name of the related form files.</span></span> <span data-ttu-id="6a894-129">请勿选择其他文件，例如 form2.Designer.cs。</span><span class="sxs-lookup"><span data-stu-id="6a894-129">Don't select the other files, such as _form2.Designer.cs_.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a894-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a894-130">See also</span></span>

- [<span data-ttu-id="6a894-131">如何定位窗体并重设其大小（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="6a894-131">How to position and size a form (Windows Forms .NET)</span></span>](how-to-position-and-resize.md)
- [<span data-ttu-id="6a894-132">事件概述（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="6a894-132">Events overview (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="6a894-133">控件的位置和布局（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="6a894-133">Position and layout of controls (Windows Forms .NET)</span></span>](../controls/layout.md)
