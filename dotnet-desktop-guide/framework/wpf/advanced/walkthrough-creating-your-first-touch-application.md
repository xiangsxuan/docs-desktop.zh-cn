---
title: 演练：创建你的第一个触控应用程序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating a touch-sensitive application [WPF]
- touchscreen applications [WPF], creating
- touch-sensitive applications [WPF], creating
- creating a touchscreen application [WPF]
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
ms.openlocfilehash: 103efe18690fc316000934de3d9a6b447e383bd2
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665167"
---
# <a name="walkthrough-creating-your-first-touch-application"></a><span data-ttu-id="17b1c-102">演练：创建你的第一个触控应用程序</span><span class="sxs-lookup"><span data-stu-id="17b1c-102">Walkthrough: Creating Your First Touch Application</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="17b1c-103">使应用程序可以响应触摸。</span><span class="sxs-lookup"><span data-stu-id="17b1c-103">enables applications to respond to touch.</span></span> <span data-ttu-id="17b1c-104">例如，你可以通过对触摸敏感设备使用一个或多个手指来与应用程序进行交互，如触摸屏，此演练将创建一个应用程序，该应用程序使用户能够通过使用触控移动、重设大小或旋转单个对象。</span><span class="sxs-lookup"><span data-stu-id="17b1c-104">For example, you can interact with an application by using one or more fingers on a touch-sensitive device, such as a touchscreen This walkthrough creates an application that enables the user to move, resize, or rotate a single object by using touch.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="17b1c-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="17b1c-105">Prerequisites</span></span>  
 <span data-ttu-id="17b1c-106">您需要满足以下条件才能完成本演练：</span><span class="sxs-lookup"><span data-stu-id="17b1c-106">You need the following components to complete this walkthrough:</span></span>  
  
- <span data-ttu-id="17b1c-107">Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="17b1c-107">Visual Studio.</span></span>  
  
- <span data-ttu-id="17b1c-108">一种设备，它接受支持 Windows Touch 的触摸输入，如触摸屏。</span><span class="sxs-lookup"><span data-stu-id="17b1c-108">A device that accepts touch input, such as a touchscreen, that supports Windows Touch.</span></span>  
  
 <span data-ttu-id="17b1c-109">此外，您应该对如何在中创建应用程序有一个基本的了解 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，尤其是如何订阅和处理事件。</span><span class="sxs-lookup"><span data-stu-id="17b1c-109">Additionally, you should have a basic understanding of how to create an application in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], especially how to subscribe to and handle an event.</span></span> <span data-ttu-id="17b1c-110">有关详细信息，请参阅 [演练：我的第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)。</span><span class="sxs-lookup"><span data-stu-id="17b1c-110">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="creating-the-application"></a><span data-ttu-id="17b1c-111">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="17b1c-111">Creating the Application</span></span>  
  
#### <a name="to-create-the-application"></a><span data-ttu-id="17b1c-112">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="17b1c-112">To create the application</span></span>  
  
1. <span data-ttu-id="17b1c-113">在 Visual Basic 或 Visual C# 中创建名为 `BasicManipulation` 的新 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="17b1c-113">Create a new WPF Application project in Visual Basic or Visual C# named `BasicManipulation`.</span></span> <span data-ttu-id="17b1c-114">有关详细信息，请参阅 [演练：我的第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)。</span><span class="sxs-lookup"><span data-stu-id="17b1c-114">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
2. <span data-ttu-id="17b1c-115">将 Mainwindow.xaml 的内容替换为以下 XAML。</span><span class="sxs-lookup"><span data-stu-id="17b1c-115">Replace the contents of MainWindow.xaml with the following XAML.</span></span>  
  
     <span data-ttu-id="17b1c-116">此标记创建一个在上包含红色的简单应用程序 <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.Controls.Canvas> 。</span><span class="sxs-lookup"><span data-stu-id="17b1c-116">This markup creates a simple application that contains a red <xref:System.Windows.Shapes.Rectangle> on a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="17b1c-117"><xref:System.Windows.UIElement.IsManipulationEnabled%2A>的属性 <xref:System.Windows.Shapes.Rectangle> 设置为 true，以便它将接收操作事件。</span><span class="sxs-lookup"><span data-stu-id="17b1c-117">The <xref:System.Windows.UIElement.IsManipulationEnabled%2A> property of the <xref:System.Windows.Shapes.Rectangle> is set to true so that it will receive manipulation events.</span></span> <span data-ttu-id="17b1c-118">应用程序订阅 <xref:System.Windows.UIElement.ManipulationStarting> 、 <xref:System.Windows.UIElement.ManipulationDelta> 和 <xref:System.Windows.UIElement.ManipulationInertiaStarting> 事件。</span><span class="sxs-lookup"><span data-stu-id="17b1c-118">The application subscribes to the <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, and <xref:System.Windows.UIElement.ManipulationInertiaStarting> events.</span></span> <span data-ttu-id="17b1c-119">这些事件包含当用户操作时用于移动的逻辑 <xref:System.Windows.Shapes.Rectangle> 。</span><span class="sxs-lookup"><span data-stu-id="17b1c-119">These events contain the logic to move the <xref:System.Windows.Shapes.Rectangle> when the user manipulates it.</span></span>  
  
     [!code-xaml[BasicManipulation#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3. <span data-ttu-id="17b1c-120">如果使用 Visual Basic，请在 Mainwindow.xaml 的第一行中将替换 `x:Class="BasicManipulation.MainWindow"` 为 `x:Class="MainWindow"` 。</span><span class="sxs-lookup"><span data-stu-id="17b1c-120">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="BasicManipulation.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
4. <span data-ttu-id="17b1c-121">在 `MainWindow` 类中，添加以下 <xref:System.Windows.UIElement.ManipulationStarting> 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="17b1c-121">In the `MainWindow` class, add the following <xref:System.Windows.UIElement.ManipulationStarting> event handler.</span></span>  
  
     <span data-ttu-id="17b1c-122"><xref:System.Windows.UIElement.ManipulationStarting>当 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 检测到触摸输入开始处理对象时，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="17b1c-122">The <xref:System.Windows.UIElement.ManipulationStarting> event occurs when [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] detects that touch input begins to manipulate an object.</span></span> <span data-ttu-id="17b1c-123">此代码通过设置属性来指定操作的位置应与相关 <xref:System.Windows.Window> <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> 。</span><span class="sxs-lookup"><span data-stu-id="17b1c-123">The code specifies that the position of the manipulation should be relative to the <xref:System.Windows.Window> by setting the <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> property.</span></span>  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](~/samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]

5. <span data-ttu-id="17b1c-124">在 `MainWindow` 类中，添加以下 <xref:System.Windows.Input.ManipulationDelta> 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="17b1c-124">In the `MainWindow` class, add the following <xref:System.Windows.Input.ManipulationDelta> event handler.</span></span>

     <span data-ttu-id="17b1c-125"><xref:System.Windows.Input.ManipulationDelta>触摸输入更改位置时发生该事件，在操作过程中可以多次出现该事件。</span><span class="sxs-lookup"><span data-stu-id="17b1c-125">The <xref:System.Windows.Input.ManipulationDelta> event occurs when the touch input changes position and can occur multiple times during a manipulation.</span></span> <span data-ttu-id="17b1c-126">引发手指后也可能发生该事件。</span><span class="sxs-lookup"><span data-stu-id="17b1c-126">The event can also occur after a finger is raised.</span></span> <span data-ttu-id="17b1c-127">例如，如果用户在屏幕上拖动手指， <xref:System.Windows.Input.ManipulationDelta> 事件会随着手指移动发生多次。</span><span class="sxs-lookup"><span data-stu-id="17b1c-127">For example, if the user drags a finger across a screen, the <xref:System.Windows.Input.ManipulationDelta> event occurs multiple times as the finger moves.</span></span> <span data-ttu-id="17b1c-128">当用户从屏幕中抬起手指时，事件会 <xref:System.Windows.Input.ManipulationDelta> 持续进行以模拟惯性。</span><span class="sxs-lookup"><span data-stu-id="17b1c-128">When the user raises a finger from the screen, the <xref:System.Windows.Input.ManipulationDelta> event keeps occurring to simulate inertia.</span></span>

     <span data-ttu-id="17b1c-129"><xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> <xref:System.Windows.UIElement.RenderTransform%2A> <xref:System.Windows.Shapes.Rectangle> 当用户移动触摸输入时，代码会将应用到的。</span><span class="sxs-lookup"><span data-stu-id="17b1c-129">The code applies the <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> to the <xref:System.Windows.UIElement.RenderTransform%2A> of the <xref:System.Windows.Shapes.Rectangle> to move it as the user moves the touch input.</span></span> <span data-ttu-id="17b1c-130">它还检查在 <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.Window> 惯性期间发生事件时是否超出的界限。</span><span class="sxs-lookup"><span data-stu-id="17b1c-130">It also checks whether the <xref:System.Windows.Shapes.Rectangle> is outside the bounds of the <xref:System.Windows.Window> when the event occurs during inertia.</span></span> <span data-ttu-id="17b1c-131">如果是这样，则应用程序会调用 <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> 方法来结束操作。</span><span class="sxs-lookup"><span data-stu-id="17b1c-131">If so, the application calls the <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> method to end the manipulation.</span></span>

     [!code-csharp[BasicManipulation#ManipulationDelta](~/samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]

6. <span data-ttu-id="17b1c-132">在 `MainWindow` 类中，添加以下 <xref:System.Windows.UIElement.ManipulationInertiaStarting> 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="17b1c-132">In the `MainWindow` class, add the following <xref:System.Windows.UIElement.ManipulationInertiaStarting> event handler.</span></span>

     <span data-ttu-id="17b1c-133"><xref:System.Windows.UIElement.ManipulationInertiaStarting>当用户从屏幕中抬起所有手指时发生此事件。</span><span class="sxs-lookup"><span data-stu-id="17b1c-133">The <xref:System.Windows.UIElement.ManipulationInertiaStarting> event occurs when the user raises all fingers from the screen.</span></span> <span data-ttu-id="17b1c-134">此代码为矩形的移动、展开和旋转设置初始速度和减速度。</span><span class="sxs-lookup"><span data-stu-id="17b1c-134">The code sets the initial velocity and deceleration for the movement, expansion, and rotation of the rectangle.</span></span>

     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](~/samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]

7. <span data-ttu-id="17b1c-135">生成并运行该项目。</span><span class="sxs-lookup"><span data-stu-id="17b1c-135">Build and run the project.</span></span>

     <span data-ttu-id="17b1c-136">窗口中会出现一个红色方块。</span><span class="sxs-lookup"><span data-stu-id="17b1c-136">You should see a red square appear in the window.</span></span>

## <a name="testing-the-application"></a><span data-ttu-id="17b1c-137">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="17b1c-137">Testing the Application</span></span>
 <span data-ttu-id="17b1c-138">若要测试应用程序，请尝试执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="17b1c-138">To test the application, try the following manipulations.</span></span> <span data-ttu-id="17b1c-139">请注意，您可以同时执行以下多项操作。</span><span class="sxs-lookup"><span data-stu-id="17b1c-139">Note that you can do more than one of the following at the same time.</span></span>

- <span data-ttu-id="17b1c-140">若要移动 <xref:System.Windows.Shapes.Rectangle> ，请将手指置于上， <xref:System.Windows.Shapes.Rectangle> 并在屏幕上移动手指。</span><span class="sxs-lookup"><span data-stu-id="17b1c-140">To move the <xref:System.Windows.Shapes.Rectangle>, put a finger on the <xref:System.Windows.Shapes.Rectangle> and move the finger across the screen.</span></span>

- <span data-ttu-id="17b1c-141">若要重设大小 <xref:System.Windows.Shapes.Rectangle> ，请将两个手指放在上， <xref:System.Windows.Shapes.Rectangle> 并将手指向彼此靠近或彼此分开。</span><span class="sxs-lookup"><span data-stu-id="17b1c-141">To resize the <xref:System.Windows.Shapes.Rectangle>, put two fingers on the <xref:System.Windows.Shapes.Rectangle> and move the fingers closer together or farther apart from each other.</span></span>

- <span data-ttu-id="17b1c-142">若要旋转 <xref:System.Windows.Shapes.Rectangle> ，请将两根手指放在上， <xref:System.Windows.Shapes.Rectangle> 旋转手指。</span><span class="sxs-lookup"><span data-stu-id="17b1c-142">To rotate the <xref:System.Windows.Shapes.Rectangle>, put two fingers on the <xref:System.Windows.Shapes.Rectangle> and rotate the fingers around each other.</span></span>

 <span data-ttu-id="17b1c-143">若要导致惯性，请在执行前面的操作时从屏幕快速抬起手指。</span><span class="sxs-lookup"><span data-stu-id="17b1c-143">To cause inertia, quickly raise your fingers from the screen as you perform the previous manipulations.</span></span> <span data-ttu-id="17b1c-144"><xref:System.Windows.Shapes.Rectangle>将继续移动、调整大小或旋转几秒钟，然后停止。</span><span class="sxs-lookup"><span data-stu-id="17b1c-144">The <xref:System.Windows.Shapes.Rectangle> will continue to move, resize, or rotate for a few seconds before it stops.</span></span>

## <a name="see-also"></a><span data-ttu-id="17b1c-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="17b1c-145">See also</span></span>

- <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>
