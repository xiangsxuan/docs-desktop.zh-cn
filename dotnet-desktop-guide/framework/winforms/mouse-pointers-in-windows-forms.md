---
title: 鼠标指针
ms.date: 03/30/2017
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
ms.openlocfilehash: 4e8349effcd9b59045e39b763b4cb8b7d2fceb91
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972852"
---
# <a name="mouse-pointers-in-windows-forms"></a>Windows 窗体中的鼠标指针
鼠标 *指针* 有时称为光标，它是一种位图，用鼠标指定用户在屏幕上的焦点。 本主题概述了 Windows 窗体中的鼠标指针，并介绍了一些修改和控制鼠标指针的方法。  
  
## <a name="accessing-the-mouse-pointer"></a>访问鼠标指针  
 鼠标指针由 <xref:System.Windows.Forms.Cursor> 类表示，每个都 <xref:System.Windows.Forms.Control> 有一个 <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> 属性，该属性指定该控件的指针。 <xref:System.Windows.Forms.Cursor>类包含描述指针的属性（如 <xref:System.Windows.Forms.Cursor.Position%2A> 和 <xref:System.Windows.Forms.Cursor.HotSpot%2A> 属性）和可修改指针外观的方法，例如 <xref:System.Windows.Forms.Cursor.Show%2A> 、 <xref:System.Windows.Forms.Cursor.Hide%2A> 和 <xref:System.Windows.Forms.Cursor.DrawStretched%2A> 方法。  
  
## <a name="controlling-the-mouse-pointer"></a>控制鼠标指针  
 有时，您可能希望限制可以使用鼠标指针的区域或更改鼠标的位置。 您可以使用的属性获取或设置鼠标的当前位置 <xref:System.Windows.Forms.Cursor.Position%2A> <xref:System.Windows.Forms.Cursor> 。 此外，你可以限制在设置属性时可以使用鼠标指针的区域 <xref:System.Windows.Forms.Cursor.Clip%2A> 。 默认情况下，剪辑区域是整个屏幕。  
  
## <a name="changing-the-mouse-pointer"></a>更改鼠标指针  
 更改鼠标指针是向用户提供反馈的重要方式。 例如，可以在和事件的处理程序中修改鼠标指针， <xref:System.Windows.Forms.Control.MouseEnter> <xref:System.Windows.Forms.Control.MouseLeave> 告诉用户发生计算，并限制控件中的用户交互。 有时，由于系统事件（例如，当应用程序包含在拖放操作中时），鼠标指针将发生变化。  
  
 更改鼠标指针的主要方式是将 <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> 控件的或属性设置 <xref:System.Windows.Forms.Control.DefaultCursor%2A> 为新的 <xref:System.Windows.Forms.Cursor> 。 有关更改鼠标指针的示例，请参阅类中的代码示例 <xref:System.Windows.Forms.Cursor> 。 此外，类还 <xref:System.Windows.Forms.Cursors> <xref:System.Windows.Forms.Cursor> 为许多不同类型的指针公开了一组对象，如类似于手的指针。 若要在鼠标指针位于控件上时显示等待指针（相当于沙漏），请使用类的 <xref:System.Windows.Forms.Control.UseWaitCursor%2A> 属性 <xref:System.Windows.Forms.Control> 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Cursor>
- [Windows 窗体应用程序中的鼠标输入](mouse-input-in-a-windows-forms-application.md)
- [Windows 窗体中的拖放功能](drag-and-drop-functionality-in-windows-forms.md)
