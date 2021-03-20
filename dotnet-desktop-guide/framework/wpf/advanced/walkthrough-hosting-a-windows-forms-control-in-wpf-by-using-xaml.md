---
title: 使用 XAML 在 WPF 中承载 Windows 窗体控件
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 2b67c1c888c9f5a9845940220fe5cc042fe574d3
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665141"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="61697-102">演练：使用 XAML 在 WPF 中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="61697-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="61697-103">提供了许多具有丰富功能集的控件。</span><span class="sxs-lookup"><span data-stu-id="61697-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="61697-104">但是，有时可能需要使用页面上 Windows 窗体控件 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="61697-104">However, you may sometimes want to use Windows Forms controls on your [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="61697-105">例如，您可能在现有 Windows 窗体控件中有大量投资，或者您可能有一个提供独特功能的 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="61697-105">For example, you may have a substantial investment in existing Windows Forms controls, or you may have a Windows Forms control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="61697-106">本演练演示如何 <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> 使用在页面上承载 Windows 窗体控件 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="61697-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="61697-107">有关本演练中所示任务的完整代码列表，请参阅 [使用 XAML 在 WPF 中承载 Windows 窗体控件](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)。</span><span class="sxs-lookup"><span data-stu-id="61697-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="61697-108">必备条件</span><span class="sxs-lookup"><span data-stu-id="61697-108">Prerequisites</span></span>  

<span data-ttu-id="61697-109">若要完成本演练，必须具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="61697-109">You need Visual Studio to complete this walkthrough.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="61697-110">承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="61697-110">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="61697-111">承载 MaskedTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="61697-111">To host the MaskedTextBox control</span></span>  
  
1. <span data-ttu-id="61697-112">创建一个名为的 WPF 应用程序项目 `HostingWfInWpfWithXaml` 。</span><span class="sxs-lookup"><span data-stu-id="61697-112">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2. <span data-ttu-id="61697-113">添加对下列程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="61697-113">Add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="61697-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="61697-114">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="61697-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="61697-115">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="61697-116">在 WPF 设计器中打开 Mainwindow.xaml。</span><span class="sxs-lookup"><span data-stu-id="61697-116">Open MainWindow.xaml in the WPF Designer.</span></span>  
  
4. <span data-ttu-id="61697-117">在 <xref:System.Windows.Window> 元素中，添加以下命名空间映射。</span><span class="sxs-lookup"><span data-stu-id="61697-117">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="61697-118">`wf`命名空间映射将建立对包含 Windows 窗体控件的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="61697-118">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. <span data-ttu-id="61697-119">在 <xref:System.Windows.Controls.Grid> 元素中添加以下 XAML。</span><span class="sxs-lookup"><span data-stu-id="61697-119">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="61697-120"><xref:System.Windows.Forms.MaskedTextBox>控件将创建为控件的子控件 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。</span><span class="sxs-lookup"><span data-stu-id="61697-120">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. <span data-ttu-id="61697-121">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="61697-121">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61697-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="61697-122">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="61697-123">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="61697-123">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="61697-124">演练：在 WPF 中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="61697-124">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="61697-125">演练：在 WPF 中托管 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="61697-125">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="61697-126">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="61697-126">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="61697-127">Windows 窗体控件和等效的 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="61697-127">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="61697-128">使用 XAML 在 WPF 中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="61697-128">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)
