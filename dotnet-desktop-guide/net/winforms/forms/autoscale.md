---
title: 自动窗体缩放
description: 介绍适用于 .NET 的 Windows 窗体如何缩放 UI。
ms.date: 10/26/2020
ms.topic: overview
helpviewer_keywords:
- scalability [Windows Forms], automatic in Windows Forms
- Windows Forms, automatic scaling
ms.openlocfilehash: c414575c83723dc1930a0bfe298534eee9aa48c8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942000"
---
# <a name="automatic-scaling-windows-forms-net"></a>自动缩放（Windows 窗体 .NET）

借助自动缩放功能，在某台计算机上以某种显示分辨率或字体设计的窗体及其控件可以在其他计算机上以不同的显示分辨率或字体适当显示。 它确保窗体及其控件将以智能方式调整大小，以便与本机 Windows 以及用户和其他开发人员的计算机上的其他应用程序保持一致。 自动缩放和视觉样式使 Windows 窗体应用程序可以在与每个用户的计算机上的本机 Windows 应用程序比较时保持一致的外观和感觉。

大多数情况下，自动缩放可在 Windows 窗体中按预期方式工作。 但是，字体方案更改可能会产生问题。<!-- TODO For an example of how to resolve this, see [How to: Respond to Font Scheme Changes in a Windows Forms Application](how-to-respond-to-font-scheme-changes-in-a-windows-forms-application.md). -->

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="need-for-automatic-scaling"></a>自动缩放的必要性

若不进行自动缩放，在分辨率或字体更改时，为某个显示分辨率或字体设计的应用程序将显示太大或太小。 例如，如果应用程序是使用 Tahoma 9 point 作为基准而设计的，则在系统字体为 Tahoma 12 point 的计算机上运行时，若不进行调整它将显示太小。 与其他应用程序相比，呈现的文本元素（如标题、菜单、文本框内容等）要小一些。 此外，包含文本的用户界面 (UI) 元素（如标题栏、菜单和很多控件）的大小均取决于所使用的字体。 在此示例中，这些元素的显示也相对小一些。

如果应用程序是针对某种显示分辨率设计的，会发生类似情况。 最常见的显示分辨率为每英寸 96 点 (DPI)（即 100% 的显示比例），但支持 125%、150%、200%（分别等于 120、144 和 192 DPI）及以上的更高分辨率的显示器也越来越常见。 如果不进行调整，针对某个分辨率设计的应用程序（特别是基于图形的应用程序）在其他分辨率上运行时就会显示太大或太小。

自动缩放力求解决这些问题，方法是更具相对字体大小或显示分辨率自动调整窗体及其子控件的大小。 Windows 操作系统支持使用一种名为对话框单位的相对度量单位的自动缩放对话框。 对话框单位基于系统字体，并且它与像素的关系可由 Win32 SDK 函数 `GetDialogBaseUnits` 确定。 当用户更改 Windows 使用的主题时，所有对话框均自动进行相应调整。 此外，根据默认系统字体或显示分辨率，Windows 窗体支持自动缩放。 或者，可在应用程序中禁用自动缩放。

> [!CAUTION]
> 不支持任意混合的 DPI 和字体缩放模式。 虽然你可能成功使用某种模式（例如 DPI）缩放用户控件并以另一种模式（字体）将其放在窗体上，但混合使用一种模式下的基窗体和其他模式下的派生窗体时可能导致意外结果。

## <a name="automatic-scaling-in-action"></a>操作中的自动缩放

Windows 窗体使用以下逻辑自动缩放窗体及其内容：

01. 在设计时，每个 <xref:System.Windows.Forms.ContainerControl> 分别在 <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> 和 <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> 中记录缩放模式及其当前的分辨率。

01. 在运行时，实际的分辨率存储在 <xref:System.Windows.Forms.ContainerControl.CurrentAutoScaleDimensions%2A> 属性中。 <xref:System.Windows.Forms.ContainerControl.AutoScaleFactor%2A> 属性动态计算运行时和设计时缩放分辨率之间的比率。

01. 窗体加载时，如果 <xref:System.Windows.Forms.ContainerControl.CurrentAutoScaleDimensions%2A> 和 <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> 的值不同，则调用 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A> 方法来缩放控件及其子项。 此方法将挂起布局并调用 <xref:System.Windows.Forms.Control.Scale%2A> 方法来执行实际缩放。 随后将更新 <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> 的值以避免渐进式缩放。

01. 在以下情况下也可自动调用 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>：

    - 如果缩放模式为 <xref:System.Windows.Forms.AutoScaleMode.Font>，则响应 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 事件。

    - 当容器控件的布局继续执行并在 <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> 或 <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> 属性中检测到更改时。

    - 如上所述，当父 <xref:System.Windows.Forms.ContainerControl> 正在缩放时。 每个容器控件负责使用自己的比例因子（而不是其父容器的比例因子）缩放其子控件。

01. 子控件可通过多种方式修改其缩放行为：

    - 可重写 <xref:System.Windows.Forms.Control.ScaleChildren%2A> 属性以确定是否应缩放其子控件。

    - 可重写 <xref:System.Windows.Forms.Control.GetScaledBounds%2A> 方法以调整控件缩放到的边界，但不是调整缩放逻辑。

    - 可重写 <xref:System.Windows.Forms.Control.ScaleControl%2A> 方法以更改当前控件的缩放逻辑。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>
- <xref:System.Windows.Forms.Control.Scale%2A>
- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>

<!-- TODO
- [Rendering Controls with Visual Styles](controls/rendering-controls-with-visual-styles.md)
- [How to: Improve Performance by Avoiding Automatic Scaling](advanced/how-to-improve-performance-by-avoiding-automatic-scaling.md)-->
