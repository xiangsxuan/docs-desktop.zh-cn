---
title: 使用双缓冲
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: 5b22336221c7bdda3c9dd7adf23308a2b0bad450
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970775"
---
# <a name="using-double-buffering"></a>使用双缓冲
您可以使用双缓冲图形来减少应用程序中包含复杂绘制操作的闪烁。 .NET Framework 包含对双缓冲的内置支持，或者你可以手动管理和呈现图形。  
  
## <a name="in-this-section"></a>本节内容  
 [双缓冲图形](double-buffered-graphics.md)  
 介绍双重缓冲概念并概述 .NET Framework 支持。  
  
 [如何：通过对窗体和控件使用双缓冲来减少图形闪烁](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 演示如何使用 .NET Framework 中的默认双缓冲支持。  
  
 [如何：手动管理缓冲的图形](how-to-manually-manage-buffered-graphics.md)  
 演示如何管理应用程序中的双缓冲。  
  
 [如何：手动呈现缓冲的图形](how-to-manually-render-buffered-graphics.md)  
 演示如何呈现双缓冲图形。  
  
## <a name="reference"></a>参考  
 <xref:System.Windows.Forms.Control.SetStyle%2A> 启用双缓冲的控制方法。  
  
 <xref:System.Drawing.BufferedGraphicsContext> 提供用于创建图形缓冲区的方法。  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 提供对应用程序域的缓冲图形上下文的访问。
