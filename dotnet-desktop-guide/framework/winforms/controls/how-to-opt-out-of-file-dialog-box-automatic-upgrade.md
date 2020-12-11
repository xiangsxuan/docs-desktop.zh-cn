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
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="93d6f-102">如何：取消文件对话框自动升级</span><span class="sxs-lookup"><span data-stu-id="93d6f-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="93d6f-103">在 <xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.SaveFileDialog> 应用程序中使用和类时，它们的外观和行为取决于运行应用程序的 Windows 的版本。</span><span class="sxs-lookup"><span data-stu-id="93d6f-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="93d6f-104">当在 Windows Vista 上显示在 .NET Framework 2.0 或更早版本上创建的应用程序时， <xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.SaveFileDialog> 将自动显示 windows vista 外观和行为。</span><span class="sxs-lookup"><span data-stu-id="93d6f-104">When an application that was created on the .NET Framework 2.0 or earlier is displayed on Windows Vista, <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the Windows Vista appearance and behavior.</span></span> <span data-ttu-id="93d6f-105">从 .NET Framework 3.0 开始，你可以选择退出自动升级，以 <xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.SaveFileDialog> 使用 Windows XP 样式的外观和行为显示和。</span><span class="sxs-lookup"><span data-stu-id="93d6f-105">Starting in the .NET Framework 3.0, you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a Windows XP-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="93d6f-106">取消文件对话框自动升级</span><span class="sxs-lookup"><span data-stu-id="93d6f-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1. <span data-ttu-id="93d6f-107">在 <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> <xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.SaveFileDialog> 显示对话框之前，将或的属性设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="93d6f-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d6f-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93d6f-108">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
