---
title: 如何：取消文件对话框自动升级
ms.date: 03/30/2017
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
ms.openlocfilehash: 154953680426f98a9506feb0b8f4de25c873b795
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972568"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>如何：取消文件对话框自动升级
在 <xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.SaveFileDialog> 应用程序中使用和类时，它们的外观和行为取决于运行应用程序的 Windows 的版本。 当在 Windows Vista 上显示在 .NET Framework 2.0 或更早版本上创建的应用程序时， <xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.SaveFileDialog> 将自动显示 windows vista 外观和行为。 从 .NET Framework 3.0 开始，你可以选择退出自动升级，以 <xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.SaveFileDialog> 使用 Windows XP 样式的外观和行为显示和。  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>取消文件对话框自动升级  
  
1. 在 <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> <xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.SaveFileDialog> 显示对话框之前，将或的属性设置为 `false` 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.FileDialog>
