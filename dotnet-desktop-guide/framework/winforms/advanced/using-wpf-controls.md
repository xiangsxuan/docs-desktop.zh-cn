---
title: 使用 WPF 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: e2e9fd6f0828d76494ed3d602b00b5d67770fc47
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957534"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a>在 Windows 窗体应用中使用 WPF 控件

您可以在基于 Windows 窗体的应用程序中使用 Windows Presentation Foundation (WPF) 控件。 尽管这是两种不同的视图技术，但它们可以顺畅地互操作。

Visual Studio 中的 Windows 窗体设计器提供了用于承载 Windows Presentation Foundation 控件的可视化设计环境。 WPF 控件由名为的特殊 Windows 窗体控件承载 <xref:System.Windows.Forms.Integration.ElementHost> 。 此控件允许 WPF 控件参与窗体的布局以及接收键盘和鼠标消息。 在设计时，您可以像对 <xref:System.Windows.Forms.Integration.ElementHost> 任何 Windows 窗体控件一样来排列控件。

你还可以在基于 WPF 的应用程序中使用 Windows 窗体控件。 有关详细信息，请参阅 [在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)。

## <a name="see-also"></a>另请参阅

- [WPF 和 Windows 窗体互操作](/dotnet/framework/wpf/advanced/wpf-and-windows-forms-interoperation)
