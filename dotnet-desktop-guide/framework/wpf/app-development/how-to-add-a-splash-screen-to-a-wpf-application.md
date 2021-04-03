---
title: 如何添加初始屏幕
description: 了解如何将启动窗口或初始屏幕添加到 Windows Presentation Foundation (WPF) 应用程序。
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 99a20dca755b7fd066ed6068ed2efa4cca8acaa9
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973033"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a>如何：将初始屏幕添加到 WPF 应用程序

本主题演示如何将启动窗口或 *初始屏幕* 添加到 WINDOWS PRESENTATION FOUNDATION (WPF) 应用程序。

## <a name="to-add-an-existing-image-as-a-splash-screen"></a>将现有图像添加为初始屏幕

1. 创建或查找要用于初始屏幕的映像。 可以使用 Windows 映像组件支持的任何图像格式 (WIC) 。 例如，可以使用 BMP、GIF、JPEG、PNG 或 TIFF 格式。

2. 将图像文件添加到 WPF 应用程序项目。

3. 在 **解决方案资源管理器** 中，选择图像。

4. 在属性窗口中，单击 " **生成操作** " 属性的下拉箭头。

5. 从下拉列表中选择 " **SplashScreen** "。

6. 按 F5 生成并运行应用程序。

     初始屏幕图像显示在屏幕的中心，然后在主应用程序窗口出现时淡化。

## <a name="to-exclude-the-splash-screen-from-build"></a>从生成中排除初始屏幕

1. 在 **解决方案资源管理器** 中，选择初始屏幕图像。

2. 在 " **属性** " 窗口中，将 " **生成操作** " 设置为 " **无**"。

## <a name="to-remove-the-splash-screen-from-an-application"></a>从应用程序中删除初始屏幕

在 **解决方案资源管理器** 中，删除初始屏幕图像。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.SplashScreen>
- [如何：向项目中添加现有项](/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))
