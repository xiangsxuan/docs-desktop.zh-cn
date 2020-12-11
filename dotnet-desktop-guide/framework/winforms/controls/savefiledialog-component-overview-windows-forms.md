---
title: SaveFileDialog 组件概述
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: 7609c29b7e932ecee7dc8a289617094bd8d480e2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970292"
---
# <a name="savefiledialog-component-overview-windows-forms"></a>SaveFileDialog 组件概述（Windows 窗体）

Windows 窗体 <xref:System.Windows.Forms.SaveFileDialog> 组件是一个预配置的对话框。 它与 Windows 使用的标准 " **保存文件** " 对话框相同。 它继承自 <xref:System.Windows.Forms.CommonDialog> 类。

## <a name="working-with-the-savefiledialog-component"></a>使用 SaveFileDialog 组件

将其用作使用户能够保存文件而不是配置自己的对话框的简单解决方案。 通过依赖标准 Windows 对话框，用户可以立即熟悉您创建的应用程序的基本功能。 但请注意，在使用 <xref:System.Windows.Forms.SaveFileDialog> 组件时，必须编写自己的文件保存逻辑。

您可以使用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法在运行时显示该对话框。 您可以使用方法在读/写模式下打开文件 <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> 。

将该组件添加到窗体时，该 <xref:System.Windows.Forms.SaveFileDialog> 组件将出现在 Visual Studio 中 Windows 窗体设计器底部的托盘中。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.SaveFileDialog>
- [SaveFileDialog 组件](savefiledialog-component-windows-forms.md)
