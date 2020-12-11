---
title: 系统信息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- domain names [Windows Forms], retrieving
- SystemInformation class [Windows Forms]
- user names [Windows Forms], retrieving
- system information [Windows Forms]
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
ms.openlocfilehash: a91e2fd8db0ef338ce30f89f11869f1b6698af3b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971598"
---
# <a name="system-information-and-windows-forms"></a>系统信息和 Windows 窗体
有时需要收集有关运行应用程序的计算机的信息，以便在代码中做出决策。 例如，在连接到特定的网络域时，可能会有一个仅适用于的函数;在这种情况下，如果域不存在，则需要一种方法来确定域并禁用该函数。  
  
 Windows 窗体应用程序可以使用 <xref:System.Windows.Forms.SystemInformation> 类在运行时确定计算机上的一些东西。 下面的示例演示如何使用 <xref:System.Windows.Forms.SystemInformation> 类检索 <xref:System.Windows.Forms.SystemInformation.UserName%2A> 和 <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A> ：  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to "
+ Domain);
```  
  
 类的所有成员 <xref:System.Windows.Forms.SystemInformation> 都是只读的; 无法修改用户的设置。 类有超过100个成员，从连接到计算机的监视器数量中返回信息 (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) 到 Windows 资源管理器中的图标的间距 (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> 和 <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>) 。  
  
 类的一些更有用的成员 <xref:System.Windows.Forms.SystemInformation> 包括、、 <xref:System.Windows.Forms.SystemInformation.ComputerName%2A> <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A> <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> 和 <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A> 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.SystemInformation>
- [Windows 窗体中的电源管理](power-management-in-windows-forms.md)
