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
# <a name="walkthrough-creating-your-first-touch-application"></a>演练：创建你的第一个触控应用程序
[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 使应用程序可以响应触摸。 例如，你可以通过对触摸敏感设备使用一个或多个手指来与应用程序进行交互，如触摸屏，此演练将创建一个应用程序，该应用程序使用户能够通过使用触控移动、重设大小或旋转单个对象。  
  
## <a name="prerequisites"></a>先决条件  
 您需要满足以下条件才能完成本演练：  
  
- Visual Studio。  
  
- 一种设备，它接受支持 Windows Touch 的触摸输入，如触摸屏。  
  
 此外，您应该对如何在中创建应用程序有一个基本的了解 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，尤其是如何订阅和处理事件。 有关详细信息，请参阅 [演练：我的第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)。  
  
## <a name="creating-the-application"></a>创建应用程序  
  
#### <a name="to-create-the-application"></a>创建应用程序  
  
1. 在 Visual Basic 或 Visual C# 中创建名为 `BasicManipulation` 的新 WPF 应用程序项目。 有关详细信息，请参阅 [演练：我的第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)。  
  
2. 将 Mainwindow.xaml 的内容替换为以下 XAML。  
  
     此标记创建一个在上包含红色的简单应用程序 <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.Controls.Canvas> 。 <xref:System.Windows.UIElement.IsManipulationEnabled%2A>的属性 <xref:System.Windows.Shapes.Rectangle> 设置为 true，以便它将接收操作事件。 应用程序订阅 <xref:System.Windows.UIElement.ManipulationStarting> 、 <xref:System.Windows.UIElement.ManipulationDelta> 和 <xref:System.Windows.UIElement.ManipulationInertiaStarting> 事件。 这些事件包含当用户操作时用于移动的逻辑 <xref:System.Windows.Shapes.Rectangle> 。  
  
     [!code-xaml[BasicManipulation#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3. 如果使用 Visual Basic，请在 Mainwindow.xaml 的第一行中将替换 `x:Class="BasicManipulation.MainWindow"` 为 `x:Class="MainWindow"` 。  
  
4. 在 `MainWindow` 类中，添加以下 <xref:System.Windows.UIElement.ManipulationStarting> 事件处理程序。  
  
     <xref:System.Windows.UIElement.ManipulationStarting>当 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 检测到触摸输入开始处理对象时，将发生此事件。 此代码通过设置属性来指定操作的位置应与相关 <xref:System.Windows.Window> <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> 。  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](~/samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]

5. 在 `MainWindow` 类中，添加以下 <xref:System.Windows.Input.ManipulationDelta> 事件处理程序。

     <xref:System.Windows.Input.ManipulationDelta>触摸输入更改位置时发生该事件，在操作过程中可以多次出现该事件。 引发手指后也可能发生该事件。 例如，如果用户在屏幕上拖动手指， <xref:System.Windows.Input.ManipulationDelta> 事件会随着手指移动发生多次。 当用户从屏幕中抬起手指时，事件会 <xref:System.Windows.Input.ManipulationDelta> 持续进行以模拟惯性。

     <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> <xref:System.Windows.UIElement.RenderTransform%2A> <xref:System.Windows.Shapes.Rectangle> 当用户移动触摸输入时，代码会将应用到的。 它还检查在 <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.Window> 惯性期间发生事件时是否超出的界限。 如果是这样，则应用程序会调用 <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> 方法来结束操作。

     [!code-csharp[BasicManipulation#ManipulationDelta](~/samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]

6. 在 `MainWindow` 类中，添加以下 <xref:System.Windows.UIElement.ManipulationInertiaStarting> 事件处理程序。

     <xref:System.Windows.UIElement.ManipulationInertiaStarting>当用户从屏幕中抬起所有手指时发生此事件。 此代码为矩形的移动、展开和旋转设置初始速度和减速度。

     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](~/samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]

7. 生成并运行该项目。

     窗口中会出现一个红色方块。

## <a name="testing-the-application"></a>测试应用程序
 若要测试应用程序，请尝试执行以下操作。 请注意，您可以同时执行以下多项操作。

- 若要移动 <xref:System.Windows.Shapes.Rectangle> ，请将手指置于上， <xref:System.Windows.Shapes.Rectangle> 并在屏幕上移动手指。

- 若要重设大小 <xref:System.Windows.Shapes.Rectangle> ，请将两个手指放在上， <xref:System.Windows.Shapes.Rectangle> 并将手指向彼此靠近或彼此分开。

- 若要旋转 <xref:System.Windows.Shapes.Rectangle> ，请将两根手指放在上， <xref:System.Windows.Shapes.Rectangle> 旋转手指。

 若要导致惯性，请在执行前面的操作时从屏幕快速抬起手指。 <xref:System.Windows.Shapes.Rectangle>将继续移动、调整大小或旋转几秒钟，然后停止。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>
