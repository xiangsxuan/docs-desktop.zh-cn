---
title: 图形概述
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: e2cc534c32c24f3ac13248bd16b177205e480820
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970800"
---
# <a name="overview-of-graphics"></a>图形概述
GDI + 是一种应用程序编程接口， (API) 构成 Microsoft Windows 操作系统的子系统。 GDI + 负责在屏幕和打印机上显示信息。 顾名思义，GDI + 是 GDI 的后续版本，图形设备接口包含在 Windows 的早期版本中。  
  
## <a name="managed-class-interface"></a>托管类接口  
 GDI + API 通过作为托管代码部署的一组类公开。 这组类称为 GDI + 的 *托管类接口* 。 以下命名空间构成托管类接口：  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 使用图形设备接口（如 GDI +），可以在屏幕或打印机上显示信息，而不必担心特定显示设备的详细信息。 程序员调用 GDI + 类提供的方法。 这些方法，反过来，对特定的设备驱动程序进行适当的调用。 GDI + 将应用程序与图形硬件隔离开来。 正是这种隔离使程序员能够创建独立于设备的应用程序。  
  
## <a name="see-also"></a>另请参阅

- [图形概述](graphics-overview-windows-forms.md)
