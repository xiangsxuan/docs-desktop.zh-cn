---
title: 键盘输入工作原理
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- keyboard input [Windows Forms], about keyboard input
- keyboards [Windows Forms], keyboard input
- Windows Forms, keyboard input
ms.assetid: 9a29433c-a180-49bb-b74c-d187786584c8
ms.openlocfilehash: aafc7b27cdd2d4c9c013a1f9632ee68ab2364dcd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970276"
---
# <a name="how-keyboard-input-works"></a>键盘输入工作原理

Windows 窗体通过引发键盘事件来处理键盘输入，以响应 Windows 消息。 大多数 Windows 窗体应用程序都通过处理键盘事件来以独占方式处理键盘输入。 但是，必须了解键盘消息的工作方式，才能实现更高级的键盘输入方案（如在按键到达控件之前截获它们）。 本主题描述 Windows 窗体能够识别的按键数据的类型，并概述键盘消息的传送方式。 有关键盘事件的信息，请参阅[使用键盘事件](using-keyboard-events.md)。  
  
## <a name="types-of-keys"></a>按键的类型  

 Windows 窗体将键盘输入标识为按位枚举表示的虚拟键代码 <xref:System.Windows.Forms.Keys> 。 使用 <xref:System.Windows.Forms.Keys> 枚举，可以组合一系列按下的键来产生单个值。 这些值与 WM_KEYDOWN 和 WM_SYSKEYDOWN Windows 消息所伴随的值相对应。 可以通过处理或事件来检测大多数物理按键 <xref:System.Windows.Forms.Control.KeyDown> <xref:System.Windows.Forms.Control.KeyUp> 。 字符键是枚举的一个子集 <xref:System.Windows.Forms.Keys> ，并且与 WM_CHAR 和 WM_SYSCHAR Windows 消息附带的值相对应。 如果按下的键的组合产生一个字符，则可以通过处理事件来检测该字符 <xref:System.Windows.Forms.Control.KeyPress> 。 或者，你可以使用 <xref:Microsoft.VisualBasic.Devices.Keyboard> Visual Basic 编程接口公开的，以发现按下了哪些键并发送键。 有关详细信息，请参阅[访问键盘](/dotnet/visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboar)。  
  
## <a name="order-of-keyboard-events"></a>键盘事件的顺序  

 正如上面列出的那样，在一个控件上可能出现三个与键盘相关的事件。 以下顺序是发生这些事件的常规顺序：  
  
1. 用户推送 "a" 键，对密钥进行预处理、调度，并 <xref:System.Windows.Forms.Control.KeyDown> 发生事件。  
  
2. 用户保存 "a" 键，该键经过预处理、调度，并 <xref:System.Windows.Forms.Control.KeyPress> 发生事件。  
  
     当用户按住某个键时，此事件会发生多次。  
  
3. 用户释放 "a" 键，该键经过预处理，并 <xref:System.Windows.Forms.Control.KeyUp> 发生事件。  
  
## <a name="preprocessing-keys"></a>键的预处理  

 与其他消息一样，键盘消息是在 <xref:System.Windows.Forms.Control.WndProc%2A> 窗体或控件的方法中处理的。 但是，在处理键盘消息之前，该 <xref:System.Windows.Forms.Control.PreProcessMessage%2A> 方法调用一个或多个可重写的方法来处理特殊的字符键和物理键。 可以重写这些方法，以便在控件处理消息之前检测并筛选某些按键。 下表按照方法出现的顺序列出了正在执行的操作以及所出现的相关方法。  
  
### <a name="preprocessing-for-a-keydown-event"></a>KeyDown 事件的预处理  
  
|操作|相关方法|说明|  
|------------|--------------------|-----------|  
|检查命令键（如快捷键或菜单快捷键）。|<xref:System.Windows.Forms.Control.ProcessCmdKey%2A>|此方法处理命令键，命令键的优先级高于常规键。 如果此方法返回 `true`，则不调度键消息，而且不发生键事件。 如果它返回 `false` ， <xref:System.Windows.Forms.Control.IsInputKey%2A> 则调用`.`|  
|检查是否需要预处理的特殊键或应引发 <xref:System.Windows.Forms.Control.KeyDown> 事件并将其调度到控件的普通字符键。|<xref:System.Windows.Forms.Control.IsInputKey%2A>|如果该方法返回 `true` ，则表示该控件是一个常规字符，并 <xref:System.Windows.Forms.Control.KeyDown> 引发事件。 如果 `false` <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> 为，则调用。 **注意：**  若要确保控件获取键或键组合，你可以处理 <xref:System.Windows.Forms.Control.PreviewKeyDown> 事件，并将设置为所 <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> 需的键的 <xref:System.Windows.Forms.PreviewKeyDownEventArgs> `true` 。|  
|检查该键是否为导航键（Esc、Tab、回车键或箭头键）。|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|此方法处理在控件内实现特殊功能（如在控件与其父级之间切换焦点）的物理按键。 如果直接控件不处理该键，则 <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> 会对父控件调用，并在层次结构中的最顶层控件上调用。 如果此方法返回 `true`，则完成预处理，而且不生成按键事件。 如果它返回 `false` ，则 <xref:System.Windows.Forms.Control.KeyDown> 发生事件。|  
  
### <a name="preprocessing-for-a-keypress-event"></a>KeyPress 事件的预处理  
  
|操作|相关方法|说明|  
|------------|--------------------|-----------|  
|检查该键是否为控件应当处理的普通字符|<xref:System.Windows.Forms.Control.IsInputChar%2A>|如果该字符是普通字符，则此方法返回 `true` ，将 <xref:System.Windows.Forms.Control.KeyPress> 引发事件，并且不会进一步进行预处理。 否则， <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> 将调用。|  
|检查该字符是否为助记键（如按钮上的“确定(&O)”）|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|此方法类似于 <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> ，将向上调用控件层次结构。 如果控件是容器控件，则它通过 <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> 对自身及其子控件调用来检查助记键。 如果 <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> 返回 `true` ，则 <xref:System.Windows.Forms.Control.KeyPress> 不会发生事件。|  
  
## <a name="processing-keyboard-messages"></a>处理键盘消息  

 在键盘消息到达 <xref:System.Windows.Forms.Control.WndProc%2A> 窗体或控件的方法后，将通过一组可以重写的方法来处理这些消息。 其中每个方法都将返回一个 <xref:System.Boolean> 值，该值指定键盘消息是否已由控件处理和使用。 如果其中的某种方法返回 `true`，则键盘消息被视为已处理，而且它不传递到控件的基控件或父控件进行进一步处理。 否则，消息停留在消息队列中，而且可能会在控件的基控件或父控件的其他方法中进行处理。 下表显示用来处理键盘消息的方法。  
  
|方法|说明|  
|------------|-----------|  
|<xref:System.Windows.Forms.Control.ProcessKeyMessage%2A>|此方法处理由该控件的方法接收的所有键盘消息 <xref:System.Windows.Forms.Control.WndProc%2A> 。|  
|<xref:System.Windows.Forms.Control.ProcessKeyPreview%2A>|此方法将键盘消息发送到控件的父控件。 如果 <xref:System.Windows.Forms.Control.ProcessKeyPreview%2A> 返回 `true` ，则不生成键事件，否则 <xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A> 会调用。|  
|<xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A>|此方法会 <xref:System.Windows.Forms.Control.KeyDown> <xref:System.Windows.Forms.Control.KeyPress> 根据需要引发、和 <xref:System.Windows.Forms.Control.KeyUp> 事件。|  
  
## <a name="overriding-keyboard-methods"></a>重写键盘方法  

 在预处理和处理键盘消息时，可以使用许多方法进行重写；但是，这些方法有好有坏。 下表显示可能需要完成的任务以及重写键盘方法的最佳方式。 有关重写方法的详细信息，请参阅 [重写派生类中的属性和方法](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics#overriding-properties-and-methods-in-derived-classes)。  
  
|任务|方法|  
|----------|------------|  
|截获导航键并引发 <xref:System.Windows.Forms.Control.KeyDown> 事件。 例如，希望在文本框中处理 Tab 键和回车键。|替代 <xref:System.Windows.Forms.Control.IsInputKey%2A>。 **注意：**  另外，还可以处理 <xref:System.Windows.Forms.Control.PreviewKeyDown> 事件，并为所需的一个或一组 <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> 键处理的 <xref:System.Windows.Forms.PreviewKeyDownEventArgs> `true` 。|  
|在控件上执行特殊的输入或导航处理。 例如，你可能希望在列表控件中使用箭头键更改选定项。|重写 <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|  
|截获导航键并引发 <xref:System.Windows.Forms.Control.KeyPress> 事件。 例如，你希望在数字调整框控件中，多次按箭头键来加快项的调整进度。|替代 <xref:System.Windows.Forms.Control.IsInputChar%2A>。|  
|在事件期间执行特殊的输入或导航处理 <xref:System.Windows.Forms.Control.KeyPress> 。 例如，在列表控件中，按住“r”键将跳到以字母 r 开头的项并在这些项间切换。|重写 <xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|  
|执行自定义的助记键处理；例如，你希望处理所有者描述的、包含在工具栏中的按钮上的助记键。|替代 <xref:System.Windows.Forms.Control.ProcessMnemonic%2A>。|  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.WndProc%2A>
- <xref:System.Windows.Forms.Control.PreProcessMessage%2A>
- [My.Computer.Keyboard 对象](/dotnet/visual-basic/language-reference/objects/my-computer-keyboard-object)
- [访问键盘](/dotnet/visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboar)
- [使用键盘事件](using-keyboard-events.md)
