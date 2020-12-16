---
title: 使用控件的概述
description: 了解如何在 .NET 的 Windows 窗体中使用控件。 控件是为用户提供功能的可重用的组件。 提供了许多现成的控件。 还可以创建新的控件。
ms.date: 10/26/2020
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, controls
- controls [Windows Forms]
- custom controls [Windows Forms]
ms.openlocfilehash: 7476ce47a1767a2ab13c25a7408f5861014e7de8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941991"
---
# <a name="overview-of-using-controls-windows-forms-net"></a>使用控件的概述（Windows 窗体 .NET）

Windows 窗体控件是可重用的组件，可以封装用户界面功能并用于基于 Windows 的客户端应用程序。 Windows 窗体不仅可以提供许多易用的控件，而且还可以提供用于开发你自己的控件的基础结构。 你可以组合现有的控件、扩展现有的控件或创作你自己的自定义控件。 有关详细信息，请参阅[自定义控件的类型](custom.md)。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="adding-controls"></a>添加控件

控件是通过 Visual Studio 设计器添加的。 利用设计器，可以放置、对齐和移动控件并调整其大小。 也可通过代码添加控件。 有关详细信息，请参阅[添加控件（Windows 窗体）](how-to-add-to-a-form.md)。

## <a name="layout-options"></a>布局选项

控件在父级上的位置由父级表面左上角的 <xref:System.Windows.Forms.Control.Location> 属性的值确定。 父级中左上角的位置坐标为 `(x0,y0)`。 控件的大小由 <xref:System.Windows.Forms.Control.Size> 属性确定，表示控件的宽度和高度。

除了手动定位和调整大小，还提供各种容器控件来帮助自动放置控件。

有关详细信息，请参阅[控件的位置和布局](layout.md)。
<!-- TODO

## Control events

-->

## <a name="see-also"></a>另请参阅

- [控件的位置和布局](layout.md)
- [Label 控件概述（Windows 窗体 .NET）](labels.md)
- [添加控件（Windows 窗体 .NET）](how-to-add-to-a-form.md)
