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
# <a name="more-secure-printing-in-windows-forms"></a><span data-ttu-id="a3e5b-102">Windows 窗体中的更加安全的打印</span><span class="sxs-lookup"><span data-stu-id="a3e5b-102">More Secure Printing in Windows Forms</span></span>
<span data-ttu-id="a3e5b-103">Windows 窗体应用程序通常包括打印功能。</span><span class="sxs-lookup"><span data-stu-id="a3e5b-103">Windows Forms applications frequently include printing abilities.</span></span> <span data-ttu-id="a3e5b-104">.NET Framework 使用 <xref:System.Drawing.Printing.PrintingPermission> 类控制对打印功能的访问，并使用关联的 <xref:System.Drawing.Printing.PrintingPermissionLevel> 枚举值来指示访问级别。</span><span class="sxs-lookup"><span data-stu-id="a3e5b-104">The .NET Framework uses the <xref:System.Drawing.Printing.PrintingPermission> class to control access to printing capabilities and the associated <xref:System.Drawing.Printing.PrintingPermissionLevel> enumeration value to indicate the level of access.</span></span> <span data-ttu-id="a3e5b-105">默认情况下，默认情况下，在本地 Intranet 和 Internet 区域中启用打印;但是，这两个区域中的访问级别都受到限制。</span><span class="sxs-lookup"><span data-stu-id="a3e5b-105">By default, printing is enabled by default in the Local Intranet and Internet zones; however, the level of access is restricted in both zones.</span></span> <span data-ttu-id="a3e5b-106">您的应用程序是可以打印、需要用户交互还是无法打印取决于授予应用程序的权限值。</span><span class="sxs-lookup"><span data-stu-id="a3e5b-106">Whether your application can print, requires user interaction, or cannot print depends upon the permission value granted to the application.</span></span> <span data-ttu-id="a3e5b-107">默认情况下，本地 Intranet 区域接收 <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> 访问权限，并且 Intranet 区域接收 <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> 访问权限。</span><span class="sxs-lookup"><span data-stu-id="a3e5b-107">By default, the Local Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> access and the Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> access.</span></span>  
  
 <span data-ttu-id="a3e5b-108">下表显示了每个打印权限级别的可用功能。</span><span class="sxs-lookup"><span data-stu-id="a3e5b-108">The following table shows the functionality available at each printing permission level.</span></span>  
  
|<span data-ttu-id="a3e5b-109">PrintingPermissionLevel</span><span class="sxs-lookup"><span data-stu-id="a3e5b-109">PrintingPermissionLevel</span></span>|<span data-ttu-id="a3e5b-110">描述</span><span class="sxs-lookup"><span data-stu-id="a3e5b-110">Description</span></span>|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|<span data-ttu-id="a3e5b-111">提供对所有已安装打印机的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="a3e5b-111">Provides full access to all installed printers.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|<span data-ttu-id="a3e5b-112">允许以编程方式打印到默认打印机，并通过限制性打印对话框更安全地打印。</span><span class="sxs-lookup"><span data-stu-id="a3e5b-112">Enables programmatic printing to the default printer and safer printing through a restrictive printing dialog box.</span></span> <span data-ttu-id="a3e5b-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> 是 <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting> 的子集。</span><span class="sxs-lookup"><span data-stu-id="a3e5b-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|<span data-ttu-id="a3e5b-114">仅从受限制的对话框提供打印。</span><span class="sxs-lookup"><span data-stu-id="a3e5b-114">Provides printing only from a more-restricted dialog box.</span></span> <span data-ttu-id="a3e5b-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> 是 <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> 的子集。</span><span class="sxs-lookup"><span data-stu-id="a3e5b-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|<span data-ttu-id="a3e5b-116">禁止对打印机的访问。</span><span class="sxs-lookup"><span data-stu-id="a3e5b-116">Prevents access to printers.</span></span> <span data-ttu-id="a3e5b-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> 是 <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> 的子集。</span><span class="sxs-lookup"><span data-stu-id="a3e5b-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3e5b-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3e5b-118">See also</span></span>

- [<span data-ttu-id="a3e5b-119">Windows 窗体中更加安全的文件和数据访问</span><span class="sxs-lookup"><span data-stu-id="a3e5b-119">More Secure File and Data Access in Windows Forms</span></span>](more-secure-file-and-data-access-in-windows-forms.md)
- [<span data-ttu-id="a3e5b-120">Windows 窗体中额外的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="a3e5b-120">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)
- [<span data-ttu-id="a3e5b-121">Windows 窗体中的安全性概述</span><span class="sxs-lookup"><span data-stu-id="a3e5b-121">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)
- [<span data-ttu-id="a3e5b-122">Windows 窗体安全</span><span class="sxs-lookup"><span data-stu-id="a3e5b-122">Windows Forms Security</span></span>](windows-forms-security.md)
