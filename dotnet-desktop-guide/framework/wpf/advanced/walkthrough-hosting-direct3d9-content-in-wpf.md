---
title: 在 WPF 中托管 Direct3D9 内容
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: e65b0c59268b44abed289e54181bf0bda9355664
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973907"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a>演练：在 WPF 中承载 Direct3D9 内容

本演练演示如何在 Windows Presentation Foundation (WPF) 应用程序中承载 Direct3D9 内容。

在本演练中，您将执行下列任务：

- 创建用于托管 Direct3D9 内容的 WPF 项目。

- 导入 Direct3D9 内容。

- 使用类显示 Direct3D9 内容 <xref:System.Windows.Interop.D3DImage> 。

 完成后，你将了解如何在 WPF 应用程序中托管 Direct3D9 内容。

## <a name="prerequisites"></a>先决条件

您需要满足以下条件才能完成本演练：

- Visual Studio。

- DirectX SDK 9 或更高版本。

- 一个 DLL，其中包含与 WPF 兼容的格式的 Direct3D9 内容。 有关详细信息，请参阅 [wpf 和 Direct3D9 互操作](wpf-and-direct3d9-interoperation.md) 和 [演练：创建 Direct3D9 内容以便在 WPF 中承载](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)。

## <a name="creating-the-wpf-project"></a>创建 WPF 项目

第一步是创建 WPF 应用程序的项目。

### <a name="to-create-the-wpf-project"></a>创建 WPF 项目

在 Visual c # 中创建一个名为的新 WPF 应用程序项目 `D3DHost` 。 有关详细信息，请参阅 [演练：我的第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)。

Mainwindow.xaml 在 WPF 设计器中打开。

## <a name="importing-the-direct3d9-content"></a>导入 Direct3D9 内容

使用属性从非托管 DLL 导入 Direct3D9 内容 `DllImport` 。

### <a name="to-import-direct3d9-content"></a>导入 Direct3D9 内容

1. 在代码编辑器中打开 Mainwindow.xaml。

2. 将自动生成的代码替换为以下代码。

    [!code-csharp[System.Windows.Interop.D3DImage#1](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]

## <a name="hosting-the-direct3d9-content"></a>承载 Direct3D9 内容

最后，使用 <xref:System.Windows.Interop.D3DImage> 类来承载 Direct3D9 内容。

### <a name="to-host-the-direct3d9-content"></a>承载 Direct3D9 内容

1. 在 Mainwindow.xaml 中，将自动生成的 XAML 替换为以下 XAML。

    [!code-xaml[System.Windows.Interop.D3DImage#10](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]

2. 生成项目。

3. 将包含 Direct3D9 内容的 DLL 复制到 bin/Debug 文件夹。

4. 按 F5 运行项目。

    Direct3D9 内容显示在 WPF 应用程序中。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Interop.D3DImage>
- [Direct3D9 和 WPF 互操作性的性能注意事项](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
