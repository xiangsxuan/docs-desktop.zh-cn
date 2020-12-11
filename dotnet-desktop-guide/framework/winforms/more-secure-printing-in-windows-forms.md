---
title: 更安全的打印
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
ms.openlocfilehash: 6285b76d01660bfa761ea606421f264bdc0c0af5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972729"
---
# <a name="more-secure-printing-in-windows-forms"></a>Windows 窗体中的更加安全的打印
Windows 窗体应用程序通常包括打印功能。 .NET Framework 使用 <xref:System.Drawing.Printing.PrintingPermission> 类控制对打印功能的访问，并使用关联的 <xref:System.Drawing.Printing.PrintingPermissionLevel> 枚举值来指示访问级别。 默认情况下，默认情况下，在本地 Intranet 和 Internet 区域中启用打印;但是，这两个区域中的访问级别都受到限制。 您的应用程序是可以打印、需要用户交互还是无法打印取决于授予应用程序的权限值。 默认情况下，本地 Intranet 区域接收 <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> 访问权限，并且 Intranet 区域接收 <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> 访问权限。  
  
 下表显示了每个打印权限级别的可用功能。  
  
|PrintingPermissionLevel|描述|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|提供对所有已安装打印机的完全访问权限。|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|允许以编程方式打印到默认打印机，并通过限制性打印对话框更安全地打印。 <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> 是 <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting> 的子集。|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|仅从受限制的对话框提供打印。 <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> 是 <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> 的子集。|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|禁止对打印机的访问。 <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> 是 <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> 的子集。|  
  
## <a name="see-also"></a>另请参阅

- [Windows 窗体中更加安全的文件和数据访问](more-secure-file-and-data-access-in-windows-forms.md)
- [Windows 窗体中额外的安全注意事项](additional-security-considerations-in-windows-forms.md)
- [Windows 窗体中的安全性概述](security-in-windows-forms-overview.md)
- [Windows 窗体安全](windows-forms-security.md)
