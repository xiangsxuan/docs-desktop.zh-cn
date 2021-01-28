---
title: 如何：为控件提供工具箱位图
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
ms.openlocfilehash: ed4f40d5b25014e5f8222a7406ea3d7eb3f8a98b
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957651"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a><span data-ttu-id="16e0a-102">如何：为控件提供工具箱位图</span><span class="sxs-lookup"><span data-stu-id="16e0a-102">How to: Provide a Toolbox Bitmap for a Control</span></span>

<span data-ttu-id="16e0a-103">如果希望在 Visual Studio 的 " **工具箱** " 中显示控件的特殊图标，则可以使用指定特定图像 <xref:System.Drawing.ToolboxBitmapAttribute> 。</span><span class="sxs-lookup"><span data-stu-id="16e0a-103">If you want to have a special icon for your control appear in the **Toolbox** of Visual Studio, you can specify a particular image by using the <xref:System.Drawing.ToolboxBitmapAttribute>.</span></span> <span data-ttu-id="16e0a-104">此类是一个特性，是一种可以附加到其他类上的特殊类。</span><span class="sxs-lookup"><span data-stu-id="16e0a-104">This class is an *attribute*, a special kind of class you can attach to other classes.</span></span> <span data-ttu-id="16e0a-105">有关特性的详细信息，请参阅 [属性概述 (](/dotnet/visual-basic/programming-guide/concepts/attributes/index) c [# (c # ) c # ](/dotnet/csharp/programming-guide/concepts/attributes/index) 的 Visual Basic 或特性) Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="16e0a-105">For more information about attributes, see [Attributes overview (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/attributes/index) for Visual Basic or [Attributes (C#)](/dotnet/csharp/programming-guide/concepts/attributes/index) for C#.</span></span>

<span data-ttu-id="16e0a-106">使用 <xref:System.Drawing.ToolboxBitmapAttribute> ，可以指定一个字符串，该字符串指示 16 x 16 像素位图的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="16e0a-106">Using the <xref:System.Drawing.ToolboxBitmapAttribute>, you can specify a string that indicates the path and file name for a 16 by 16 pixel bitmap.</span></span> <span data-ttu-id="16e0a-107">添加到“工具箱”后，此位图显示在对应的控件旁边。</span><span class="sxs-lookup"><span data-stu-id="16e0a-107">This bitmap then appears next to your control when added to the **Toolbox**.</span></span> <span data-ttu-id="16e0a-108">你还可以指定 <xref:System.Type> ，在这种情况下，将加载与该类型关联的位图。</span><span class="sxs-lookup"><span data-stu-id="16e0a-108">You can also specify a <xref:System.Type>, in which case the bitmap associated with that type is loaded.</span></span> <span data-ttu-id="16e0a-109">如果同时指定一个 <xref:System.Type> 和一个字符串，则控件将在包含参数指定的类型的程序集中搜索具有指定名称的图像资源 <xref:System.Type> 。</span><span class="sxs-lookup"><span data-stu-id="16e0a-109">If you specify both a <xref:System.Type> and a string, the control searches for an image resource with the name specified by the string parameter in the assembly containing the type specified by the <xref:System.Type> parameter.</span></span>

## <a name="to-specify-a-toolbox-bitmap-for-your-control"></a><span data-ttu-id="16e0a-110">指定控件的工具箱位图</span><span class="sxs-lookup"><span data-stu-id="16e0a-110">To specify a Toolbox bitmap for your control</span></span>

1. <span data-ttu-id="16e0a-111">将添加 <xref:System.Drawing.ToolboxBitmapAttribute> 到控件的类声明 `Class` 中，在 visual Basic 的关键字之前，在 Visual c # 的类声明之上。</span><span class="sxs-lookup"><span data-stu-id="16e0a-111">Add the <xref:System.Drawing.ToolboxBitmapAttribute> to the class declaration of your control before the `Class` keyword for visual Basic, and above the class declaration for Visual C#.</span></span>

    ```vb
    ' Specifies the bitmap associated with the Button type.
    <ToolboxBitmap(GetType(Button))> Class MyControl1
    ' Specifies a bitmap file.
    End Class
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _
       Class MyControl2
    End Class
    ' Specifies a type that indicates the assembly to search, and the name
    ' of an image resource to look for.
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl
    End Class
    ```

    ```csharp
    // Specifies the bitmap associated with the Button type.
    [ToolboxBitmap(typeof(Button))]
    class MyControl1 : UserControl
    {
    }
    // Specifies a bitmap file.
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]
    class MyControl2 : UserControl
    {
    }
    // Specifies a type that indicates the assembly to search, and the name
    // of an image resource to look for.
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]
    class MyControl : UserControl
    {
    }
    ```

2. <span data-ttu-id="16e0a-112">重新生成项目。</span><span class="sxs-lookup"><span data-stu-id="16e0a-112">Rebuild the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="16e0a-113">对于自动生成的控件和组件，位图不会出现在工具箱中。</span><span class="sxs-lookup"><span data-stu-id="16e0a-113">The bitmap does not appear in the Toolbox for autogenerated controls and components.</span></span> <span data-ttu-id="16e0a-114">若要查看位图，请使用“选择工具箱项”对话框重载控件。</span><span class="sxs-lookup"><span data-stu-id="16e0a-114">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="16e0a-115">有关详细信息，请参阅[演练：使用自定义组件自动填充工具箱](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)。</span><span class="sxs-lookup"><span data-stu-id="16e0a-115">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="16e0a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16e0a-116">See also</span></span>

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [<span data-ttu-id="16e0a-117">演练：使用自定义组件自动填充工具箱</span><span class="sxs-lookup"><span data-stu-id="16e0a-117">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [<span data-ttu-id="16e0a-118">设计时开发 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="16e0a-118">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="16e0a-119">特性概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16e0a-119">Attributes overview (Visual Basic)</span></span>](/dotnet/visual-basic/programming-guide/concepts/attributes/index)
- [<span data-ttu-id="16e0a-120">特性 (C#)</span><span class="sxs-lookup"><span data-stu-id="16e0a-120">Attributes (C#)</span></span>](/dotnet/csharp/programming-guide/concepts/attributes/index)
