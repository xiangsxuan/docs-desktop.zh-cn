---
title: 如何：通过在每个 Windows 窗体各自的线程上显示此 Windows 窗体来支持 COM 互操作
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: a9e04765-d2de-4389-a494-a9a6d07aa6ee
ms.openlocfilehash: 074fc2d3fcfe1bf02bc6f6af65a3d9aed39fe786
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971651"
---
# <a name="how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread"></a><span data-ttu-id="f2a05-102">如何：通过在各自的线程上显示每个 Windows 窗体来支持 COM 互操作</span><span class="sxs-lookup"><span data-stu-id="f2a05-102">How to: Support COM interop by displaying each Windows Form on its own thread</span></span>

<span data-ttu-id="f2a05-103">可以通过在 .NET Framework 消息循环上显示窗体来解决 COM 互操作性问题，该消息循环可以使用 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> 方法创建。</span><span class="sxs-lookup"><span data-stu-id="f2a05-103">You can resolve COM interoperability problems by displaying your form on a .NET Framework message loop, which you can create by using the <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="f2a05-104">若要使 Windows 窗体在 COM 客户端应用程序上正确工作，必须在 Windows 窗体消息循环上运行该窗体。</span><span class="sxs-lookup"><span data-stu-id="f2a05-104">To make a Windows Form work correctly from a COM client application, you must run the form on a Windows Forms message loop.</span></span> <span data-ttu-id="f2a05-105">若要执行此操作，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="f2a05-105">To do this, use one of the following approaches:</span></span>

- <span data-ttu-id="f2a05-106">使用 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 方法显示 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="f2a05-106">Use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to display the Windows Form.</span></span> <span data-ttu-id="f2a05-107">有关详细信息，请参阅 [How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method](com-interop-by-displaying-a-windows-form-shadow.md)。</span><span class="sxs-lookup"><span data-stu-id="f2a05-107">For more information, see [How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method](com-interop-by-displaying-a-windows-form-shadow.md).</span></span>

- <span data-ttu-id="f2a05-108">在单独的线程上显示每个 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="f2a05-108">Display each Windows Form on a separate thread.</span></span>

<span data-ttu-id="f2a05-109">Visual Studio 中提供了此功能的广泛支持。</span><span class="sxs-lookup"><span data-stu-id="f2a05-109">There is extensive support for this feature in Visual Studio.</span></span>

<span data-ttu-id="f2a05-110">另请参阅 [演练：通过在每个 Windows 窗体各自的线程上显示该 Windows 窗体来支持 COM 互操作](/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="f2a05-110">Also see [Walkthrough: Supporting COM Interop by Displaying Each Windows Form on Its Own Thread](/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).</span></span>

## <a name="example"></a><span data-ttu-id="f2a05-111">示例</span><span class="sxs-lookup"><span data-stu-id="f2a05-111">Example</span></span>

<span data-ttu-id="f2a05-112">下面的代码示例演示如何在单独的线程上显示窗体，并调用 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> 方法来启动该线程上的 Windows 窗体消息泵。</span><span class="sxs-lookup"><span data-stu-id="f2a05-112">The following code example demonstrates how to display the form on a separate thread and call the <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> method to start a Windows Forms message pump on that thread.</span></span> <span data-ttu-id="f2a05-113">若要使用此方法，必须使用 <xref:System.Windows.Forms.Control.Invoke%2A> 方法，封送任何从非托管应用程序对窗体的调用。</span><span class="sxs-lookup"><span data-stu-id="f2a05-113">To use this approach, you must marshal any calls to the form from the unmanaged application by using the <xref:System.Windows.Forms.Control.Invoke%2A> method.</span></span>

<span data-ttu-id="f2a05-114">此方法要求窗体上的每个实例通过使用其自身的消息循环在自己的线程上运行。</span><span class="sxs-lookup"><span data-stu-id="f2a05-114">This approach requires that each instance of a form runs on its own thread by using its own message loop.</span></span> <span data-ttu-id="f2a05-115">每个线程上运行的消息循环不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="f2a05-115">You cannot have more than one message loop running per thread.</span></span> <span data-ttu-id="f2a05-116">因此，不能更改客户端应用程序的消息循环。</span><span class="sxs-lookup"><span data-stu-id="f2a05-116">Therefore, you cannot change the client application's message loop.</span></span> <span data-ttu-id="f2a05-117">但是，您可以修改 .NET Framework 组件，以启动使用其自身的消息循环的新线程。</span><span class="sxs-lookup"><span data-stu-id="f2a05-117">However, you can modify the .NET Framework component to start a new thread that uses its own message loop.</span></span>

[!code-vb[System.Windows.Forms.ComInterop#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/COMForm.vb#1)]

[!code-vb[System.Windows.Forms.ComInterop#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/FormManager.vb#10)]

[!code-vb[System.Windows.Forms.ComInterop#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/Form1.vb#100)]

## <a name="compile-the-code"></a><span data-ttu-id="f2a05-118">编译代码</span><span class="sxs-lookup"><span data-stu-id="f2a05-118">Compile the code</span></span>

<span data-ttu-id="f2a05-119">将 `COMForm`、 `Form1`和 `FormManager` 类型编译成名为 `COMWinform.dll`的程序集。</span><span class="sxs-lookup"><span data-stu-id="f2a05-119">Compile the `COMForm`, `Form1`, and `FormManager` types into an assembly called `COMWinform.dll`.</span></span> <span data-ttu-id="f2a05-120">使用 [Packaging an Assembly for COM](/dotnet/framework/interop/packaging-an-assembly-for-co)中所述的一个方法来注册 COM 互操作的程序集。</span><span class="sxs-lookup"><span data-stu-id="f2a05-120">Register the assembly for COM interop by using one of the methods described in [Packaging an Assembly for COM](/dotnet/framework/interop/packaging-an-assembly-for-co).</span></span> <span data-ttu-id="f2a05-121">现在，你可以在非托管应用程序中使用该程序集以及它对应的的类型库 (.tlb) 文件。</span><span class="sxs-lookup"><span data-stu-id="f2a05-121">You can now use the assembly and its corresponding type library (.tlb) file in unmanaged applications.</span></span> <span data-ttu-id="f2a05-122">例如，可在 Visual Basic 6.0 可执行项目中将类型库用作引用。</span><span class="sxs-lookup"><span data-stu-id="f2a05-122">For example, you can use the type library as a reference in a Visual Basic 6.0 executable project.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2a05-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2a05-123">See also</span></span>

- [<span data-ttu-id="f2a05-124">向 COM 公开 .NET Framework 组件</span><span class="sxs-lookup"><span data-stu-id="f2a05-124">Exposing .NET Framework Components to COM</span></span>](/dotnet/framework/interop/exposing-dotnet-components-to-co)
- [<span data-ttu-id="f2a05-125">将 COM 的程序集打包</span><span class="sxs-lookup"><span data-stu-id="f2a05-125">Packaging an Assembly for COM</span></span>](/dotnet/framework/interop/packaging-an-assembly-for-co)
- [<span data-ttu-id="f2a05-126">向 COM 注册程序集</span><span class="sxs-lookup"><span data-stu-id="f2a05-126">Registering Assemblies with COM</span></span>](/dotnet/framework/interop/registering-assemblies-with-co)
- [<span data-ttu-id="f2a05-127">如何：通过使用 ShowDialog 方法显示 Windows 窗体来支持 COM 互操作</span><span class="sxs-lookup"><span data-stu-id="f2a05-127">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>](com-interop-by-displaying-a-windows-form-shadow.md)
- [<span data-ttu-id="f2a05-128">Windows 窗体和非托管应用程序概述</span><span class="sxs-lookup"><span data-stu-id="f2a05-128">Windows Forms and Unmanaged Applications Overview</span></span>](windows-forms-and-unmanaged-applications-overview.md)
