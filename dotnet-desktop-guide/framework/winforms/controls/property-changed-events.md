---
title: 属性更改事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
ms.openlocfilehash: 939972713ad95e9302c436268f4a6288a659ca6e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972856"
---
# <a name="property-changed-events"></a>属性更改事件

如果希望控件在名为 *propertyname* 的属性发生更改时发送通知，请定义名为 *propertyname* 的事件 `Changed` 和 `On` 引发事件的名为 *propertyname* 的方法 `Changed` 。 Windows 窗体中的命名约定是将 *更改* 的单词附加到属性的名称。 属性更改事件的关联事件委托类型为 <xref:System.EventHandler> ，事件数据类型为 <xref:System.EventArgs> 。 基类 <xref:System.Windows.Forms.Control> 定义许多属性更改事件，例如、、、等 <xref:System.Windows.Forms.Control.BackColorChanged> <xref:System.Windows.Forms.Control.BackgroundImageChanged> <xref:System.Windows.Forms.Control.FontChanged> <xref:System.Windows.Forms.Control.LocationChanged> 。 有关事件的背景信息，请参阅[Windows 窗体控件中的](events-in-windows-forms-controls.md)[事件](/dotnet/standard/events/index)和事件。  
  
 属性更改事件很有用，因为它们允许控件的使用者附加响应更改的事件处理程序。 如果控件需要响应它引发的属性更改的事件，请重写相应的 `On` *PropertyName* `Changed` 方法，而不是将委托附加到事件。 控件通常通过更新其他属性或通过重绘其部分或全部绘制图面来响应属性更改事件。  
  
 下面的示例演示 `FlashTrackBar` 自定义控件如何响应其继承自的某些属性更改事件 <xref:System.Windows.Forms.Control> 。 有关完整示例，请参阅 [如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)。  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a>请参阅

- [事件](/dotnet/standard/events/index)
- [Windows 窗体控件中的事件](events-in-windows-forms-controls.md)
- [Windows 窗体控件中的属性](properties-in-windows-forms-controls.md)
