---
title: 鼠标输入的工作原理
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- Windows Forms, mouse input
- mouse [Windows Forms], input
ms.assetid: 48fc5240-75a6-44bf-9fce-6aa21b49705a
ms.openlocfilehash: 39977be71054a16baf9be81c566eb3cdca09a916
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970274"
---
# <a name="how-mouse-input-works-in-windows-forms"></a>Windows 窗体中鼠标输入的工作原理
接收和处理鼠标输入是每个 Windows 应用程序的重要组成部分。 可以处理鼠标事件，以便在应用程序中执行某项操作，或使用鼠标位置信息执行命中测试或其他操作。 此外，你可以更改应用程序中的控件处理鼠标输入的方式。 本主题详细介绍了这些鼠标事件，以及如何获取和更改鼠标的系统设置。 有关与鼠标事件一起提供的数据以及引发鼠标单击事件顺序的详细信息，请参阅 [中的鼠标事件 Windows 窗体](mouse-events-in-windows-forms.md)。  
  
## <a name="mouse-location-and-hit-testing"></a>鼠标位置和 Hit-Testing  
 当用户移动鼠标时，操作系统将移动鼠标指针。 鼠标指针包含一个称为 "热点" 的像素，操作系统将跟踪该像素，并将其识别为指针的位置。 当用户移动鼠标或按下鼠标按钮时，包含的将 <xref:System.Windows.Forms.Control> <xref:System.Windows.Forms.Cursor.HotSpot%2A> 引发相应的鼠标事件。 <xref:System.Windows.Forms.MouseEventArgs.Location%2A> <xref:System.Windows.Forms.MouseEventArgs> 当处理鼠标事件或使用类的属性时，可以使用的属性获取当前鼠标的位置 <xref:System.Windows.Forms.Cursor.Position%2A> <xref:System.Windows.Forms.Cursor> 。 随后可以使用鼠标位置信息来执行命中测试，然后根据鼠标的位置执行操作。 命中测试功能内置于 Windows 窗体中的多个控件 <xref:System.Windows.Forms.ListView> ，例如、 <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.MonthCalendar> 和 <xref:System.Windows.Forms.DataGridView> 控件。 与相应的鼠标事件一起使用， <xref:System.Windows.Forms.Control.MouseHover> 例如，命中测试非常适用于确定应用程序何时应执行特定操作。  
  
## <a name="mouse-events"></a>鼠标事件  
 响应鼠标输入的主要方法是处理鼠标事件。 下表显示了鼠标事件，并说明了何时引发这些事件。  
  
|鼠标事件|描述|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.Click>|此事件在释放鼠标按钮时发生，通常在事件之前发生 <xref:System.Windows.Forms.Control.MouseUp> 。 此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。 当只需要确定何时发生单击时，处理此事件。|  
|<xref:System.Windows.Forms.Control.MouseClick>|当用户用鼠标单击控件时发生此事件。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。 当你需要在单击时获取有关鼠标的信息时，请处理此事件。|  
|<xref:System.Windows.Forms.Control.DoubleClick>|双击控件时发生此事件。 此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。 如果只需要确定双击发生的时间，请处理此事件。|  
|<xref:System.Windows.Forms.Control.MouseDoubleClick>|当用户用鼠标双击控件时发生此事件。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。 当你需要在双击时获取有关鼠标的信息时，请处理此事件。|  
|<xref:System.Windows.Forms.Control.MouseDown>|当鼠标指针位于控件上并且用户按下鼠标按钮时发生此事件。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。|  
|<xref:System.Windows.Forms.Control.MouseEnter>|当鼠标指针进入控件的边框或工作区时，将发生此事件，具体取决于控件的类型。 此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。|  
|<xref:System.Windows.Forms.Control.MouseHover>|当鼠标指针停留在控件上时发生此事件。 此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。|  
|<xref:System.Windows.Forms.Control.MouseLeave>|当鼠标指针离开控件的边框或工作区时，将发生此事件，具体取决于控件的类型。 此事件的处理程序接收类型为 <xref:System.EventArgs> 的参数。|  
|<xref:System.Windows.Forms.Control.MouseMove>|当鼠标指针位于控件上并且移动鼠标指针时发生此事件。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。|  
|<xref:System.Windows.Forms.Control.MouseUp>|当鼠标指针位于控件上并且用户释放鼠标按钮时发生此事件。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。|  
|<xref:System.Windows.Forms.Control.MouseWheel>|当用户在控件有焦点的情况下旋转鼠标滚轮时发生此事件。 此事件的处理程序接收类型为 <xref:System.Windows.Forms.MouseEventArgs> 的参数。 您可以使用的 <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> 属性 <xref:System.Windows.Forms.MouseEventArgs> 来确定鼠标的滚动程度。|  
  
## <a name="changing-mouse-input-and-detecting-system-settings"></a>更改鼠标输入和检测系统设置  
 您可以通过从控件派生并使用和方法，检测并更改控件处理鼠标输入的方式 <xref:System.Windows.Forms.Control.GetStyle%2A> <xref:System.Windows.Forms.Control.SetStyle%2A> 。 <xref:System.Windows.Forms.Control.SetStyle%2A>方法使用值的按位组合 <xref:System.Windows.Forms.ControlStyles> 来确定控件是否将具有标准的单击或双击行为，或者控件是否将处理其自己的鼠标处理。 此外，类还 <xref:System.Windows.Forms.SystemInformation> 包括描述鼠标功能的属性，并指定鼠标如何与操作系统交互。 下表汇总了这些属性。  
  
|属性|描述|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>|获取一个区域的尺寸（以像素为单位），用户必须在该区域中单击两次，操作系统才将这两次单击视为双击。|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>|获取在第一次单击与第二次单击之间可以经过的最大毫秒数，以使操作系统将鼠标操作视为双击。|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>|获取鼠标上的按钮数。|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>|获取一个值，该值指示是否已交换鼠标左右按钮的功能。|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>|获取特定矩形的尺寸（以像素为单位），鼠标指针必须在该矩形范围内停留达到鼠标悬停时间后，才会生成鼠标悬停消息。|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>|获取一个以毫秒为单位的时间，鼠标指针必须在悬停矩形中停留该时间后，才会生成鼠标悬停消息。|  
|<xref:System.Windows.Forms.SystemInformation.MousePresent%2A>|获取一个值，该值指示是否安装了鼠标。|  
|<xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>|获取一个值，该值指示当前鼠标的速度，从1到20。|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>|获取一个值，该值指示是否安装了带有鼠标轮的鼠标。|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A>|获取单次鼠标轮旋转增量的增量值。|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A>|获取滚动鼠标轮时所滚动过的行数。|  
  
## <a name="see-also"></a>另请参阅

- [Windows 窗体应用程序中的鼠标输入](mouse-input-in-a-windows-forms-application.md)
- [Windows 窗体中的鼠标捕获](mouse-capture-in-windows-forms.md)
- [Windows 窗体中的鼠标指针](mouse-pointers-in-windows-forms.md)
