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
# <a name="power-management-in-windows-forms"></a>Windows 窗体中的电源管理
Windows 窗体的应用程序可以利用 Windows 操作系统中的电源管理功能。 应用程序可以监视计算机的电源状态，并在状态发生更改时执行操作。 例如，如果您的应用程序运行在便携式计算机上，则您可能希望在计算机的电池电量低于某个级别时禁用应用程序中的某些功能。  
  
 .NET Framework 提供了一种 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> 在电源状态发生变化时发生的事件，例如当用户挂起或恢复操作系统时，或者当 AC 电源状态或电池状态更改时出现。 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>类的属性 <xref:System.Windows.Forms.SystemInformation> 可用于查询当前状态，如下面的代码示例中所示。  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 除了 <xref:System.Windows.Forms.BatteryChargeStatus> 枚举以外， <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> 属性还包含用于确定电池容量 (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) 和电池电量百分比 () 的 <xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A> 枚举 <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A> 。  
  
 你可以使用的 <xref:System.Windows.Forms.Application.SetSuspendState%2A> 方法， <xref:System.Windows.Forms.Application> 使计算机进入休眠或挂起模式。 如果 `force` 参数设置为 `false` ，操作系统会将一个事件广播给所有请求挂起权限的应用程序。 如果 `disableWakeEvent` 参数设置为 `true` ，则操作系统将禁用所有唤醒事件。  
  
 下面的代码示例演示如何使计算机进入休眠状态。  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a>另请参阅

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
