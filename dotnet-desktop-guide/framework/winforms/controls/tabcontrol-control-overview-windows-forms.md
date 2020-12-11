---
title: TabControl 控件概述
ms.date: 03/30/2017
f1_keywords:
- TabControl
helpviewer_keywords:
- TabControl control [Windows Forms], about TabControl control
- tab pages [Windows Forms], about tab pages
- property pages [Windows Forms], Windows Forms
- Windows Forms dialog boxes [Windows Forms], tabs
ms.assetid: 2b4ea784-a39d-463c-81d8-af74ce068476
ms.openlocfilehash: 2668169488b4087673fbf2552650c23cda780642
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970895"
---
# <a name="tabcontrol-control-overview-windows-forms"></a>TabControl 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.TabControl> 显示多个选项卡，就像笔记本中的分隔线或档案柜中一组文件夹的标签。 选项卡可以包含图片和其他控件。 您可以使用选项卡控件来生成在 Windows 操作系统中显示的多个位置的多页对话框，如 "控制面板" 的 "显示属性"。 此外，还 <xref:System.Windows.Forms.TabControl> 可用于创建用于设置一组相关属性的属性页。  
  
## <a name="working-with-tabcontrol"></a>使用 TabControl  
 的最重要的属性 <xref:System.Windows.Forms.TabControl> 是 <xref:System.Windows.Forms.TabControl.TabPages%2A> ，其中包含各个选项卡。 每个单独的选项卡都是一个 <xref:System.Windows.Forms.TabPage> 对象。 当单击某个选项卡时，它将引发 <xref:System.Windows.Forms.Control.Click> 该对象的事件 <xref:System.Windows.Forms.TabPage> 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.TabControl>
- [TabControl 控件](tabcontrol-control-windows-forms.md)
- [如何：更改 Windows 窗体 TabControl 的外观](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [如何：将控件添加到选项卡页](how-to-add-a-control-to-a-tab-page.md)
- [如何：使用 Windows 窗体 TabControl 添加和移除选项卡](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [如何：禁用选项卡页](how-to-disable-tab-pages.md)
- [Windows 窗体中的对话框](../dialog-boxes-in-windows-forms.md)
