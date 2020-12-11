---
title: 电源管理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
ms.openlocfilehash: 9ac39df43a08f62e50116c61c4bdeda4cd1c8281
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971606"
---
# <a name="power-management-in-windows-forms"></a><span data-ttu-id="ecafb-102">Windows 窗体中的电源管理</span><span class="sxs-lookup"><span data-stu-id="ecafb-102">Power Management in Windows Forms</span></span>
<span data-ttu-id="ecafb-103">Windows 窗体的应用程序可以利用 Windows 操作系统中的电源管理功能。</span><span class="sxs-lookup"><span data-stu-id="ecafb-103">Your Windows Forms applications can take advantage of the power management features in the Windows operating system.</span></span> <span data-ttu-id="ecafb-104">应用程序可以监视计算机的电源状态，并在状态发生更改时执行操作。</span><span class="sxs-lookup"><span data-stu-id="ecafb-104">Your applications can monitor the power status of a computer and take action when a status change occurs.</span></span> <span data-ttu-id="ecafb-105">例如，如果您的应用程序运行在便携式计算机上，则您可能希望在计算机的电池电量低于某个级别时禁用应用程序中的某些功能。</span><span class="sxs-lookup"><span data-stu-id="ecafb-105">For example, if your application is running on a portable computer, you might want to disable certain features in your application when the computer's battery charge falls under a certain level.</span></span>  
  
 <span data-ttu-id="ecafb-106">.NET Framework 提供了一种 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> 在电源状态发生变化时发生的事件，例如当用户挂起或恢复操作系统时，或者当 AC 电源状态或电池状态更改时出现。</span><span class="sxs-lookup"><span data-stu-id="ecafb-106">The .NET Framework provides a <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> event that occurs whenever there is a change in power status, such as when a user suspends or resumes the operating system, or when the AC power status or battery status changes.</span></span> <span data-ttu-id="ecafb-107"><xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>类的属性 <xref:System.Windows.Forms.SystemInformation> 可用于查询当前状态，如下面的代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="ecafb-107">The <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property of the <xref:System.Windows.Forms.SystemInformation> class can be used to query for the current status, as shown in the following code example.</span></span>  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <span data-ttu-id="ecafb-108">除了 <xref:System.Windows.Forms.BatteryChargeStatus> 枚举以外， <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> 属性还包含用于确定电池容量 (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) 和电池电量百分比 () 的 <xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A> 枚举 <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A> 。</span><span class="sxs-lookup"><span data-stu-id="ecafb-108">Besides the <xref:System.Windows.Forms.BatteryChargeStatus> enumerations, the <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property also contains enumerations for determining battery capacity (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) and battery charge percentage (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span></span>  
  
 <span data-ttu-id="ecafb-109">你可以使用的 <xref:System.Windows.Forms.Application.SetSuspendState%2A> 方法， <xref:System.Windows.Forms.Application> 使计算机进入休眠或挂起模式。</span><span class="sxs-lookup"><span data-stu-id="ecafb-109">You can use the <xref:System.Windows.Forms.Application.SetSuspendState%2A> method of the <xref:System.Windows.Forms.Application> to put a computer into hibernation or suspend mode.</span></span> <span data-ttu-id="ecafb-110">如果 `force` 参数设置为 `false` ，操作系统会将一个事件广播给所有请求挂起权限的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ecafb-110">If the `force` argument is set to `false`, the operating system will broadcast an event to all applications requesting permission to suspend.</span></span> <span data-ttu-id="ecafb-111">如果 `disableWakeEvent` 参数设置为 `true` ，则操作系统将禁用所有唤醒事件。</span><span class="sxs-lookup"><span data-stu-id="ecafb-111">If the `disableWakeEvent` argument is set to `true`, the operating system disables all wake events.</span></span>  
  
 <span data-ttu-id="ecafb-112">下面的代码示例演示如何使计算机进入休眠状态。</span><span class="sxs-lookup"><span data-stu-id="ecafb-112">The following code example demonstrates how to put a computer into hibernation.</span></span>  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ecafb-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ecafb-113">See also</span></span>

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
