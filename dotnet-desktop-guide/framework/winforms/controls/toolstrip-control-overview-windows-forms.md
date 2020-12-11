---
title: ToolStrip 控件概述
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 931a6a0ea09f9b684b793c05cb1c3db8ee8fb7c7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973075"
---
# <a name="toolstrip-control-overview-windows-forms"></a>ToolStrip 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.ToolStrip> 控件及其关联的类提供一个公共框架，用于将用户界面元素合并到工具栏、状态栏和菜单中。 <xref:System.Windows.Forms.ToolStrip> 控件提供丰富的设计时体验，其中包括就地激活和编辑、自定义布局和漂浮（这是工具栏共享水平或垂直空间的能力）。  
  
 尽管 <xref:System.Windows.Forms.ToolStrip> 在以前的版本中将替换和添加到控件中的功能，但仍 <xref:System.Windows.Forms.ToolBar> 会保留以实现向后兼容性和将来使用（如果需要）。  
  
## <a name="features-of-the-toolstrip-controls"></a>ToolStrip 控件的功能  
 使用 <xref:System.Windows.Forms.ToolStrip> 控件可以：  
  
- 跨容器显示公共用户界面。  
  
- 创建可轻松自定义的常用工具栏，这些工具栏支持高级用户界面和布局功能，如停靠、漂浮、带有文本和图像的按钮、下拉按钮和控件、溢出按钮以及项的运行时重新排序 <xref:System.Windows.Forms.ToolStrip> 。  
  
- 支持溢出和运行时项重新排序。 如果没有足够空间在中显示项，溢出功能会将项移动到下拉菜单 <xref:System.Windows.Forms.ToolStrip> 。  
  
- 通过常见的呈现模型支持操作系统的典型外观和行为。  
  
- 以一致的方式处理所有容器和包含项的事件，其方式与处理其他控件的事件的方式相同。  
  
- 将项从一项拖动 <xref:System.Windows.Forms.ToolStrip> 到另一个 <xref:System.Windows.Forms.ToolStrip> 。  
  
- 在中创建具有高级布局的下拉控件和用户界面类型编辑器 <xref:System.Windows.Forms.ToolStripDropDown> 。  
  
 使用 <xref:System.Windows.Forms.ToolStripControlHost> 类来使用上的其他控件 <xref:System.Windows.Forms.ToolStrip> ，并获取 <xref:System.Windows.Forms.ToolStrip> 这些控件的功能。  
  
 可以通过将 <xref:System.Windows.Forms.ToolStripRenderer> 、 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 和 <xref:System.Windows.Forms.ToolStripManager> 与 <xref:System.Windows.Forms.ToolStripRenderMode> 和 <xref:System.Windows.Forms.ToolStripManagerRenderMode> 枚举一起使用来扩展功能并修改外观和行为。  
  
 <xref:System.Windows.Forms.ToolStrip>控件高度可配置且可扩展，并且提供了许多属性、方法和事件来自定义外观和行为。 下面是一些值得注意的成员：  
  
### <a name="important-toolstrip-members"></a>重要 ToolStrip 成员  
  
|名称|描述|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|获取或设置将停靠到的父容器的边缘 <xref:System.Windows.Forms.ToolStrip> 。|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|获取或设置一个用于指示是否专门由 <xref:System.Windows.Forms.ToolStrip> 类处理拖放和项重新排序操作的值。|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|获取或设置一个值，该值指示如何对 <xref:System.Windows.Forms.ToolStrip> 项进行布局。|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|获取或设置 <xref:System.Windows.Forms.ToolStripItem> 是附加到或，还是 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripOverflowButton> 可以在两者之间浮动。|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|获取一个值，该值指示在 <xref:System.Windows.Forms.ToolStripItem> 单击时是否在下拉列表中显示其他项 <xref:System.Windows.Forms.ToolStripItem> 。|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|获取 <xref:System.Windows.Forms.ToolStripItem>，它是启用了溢出的 <xref:System.Windows.Forms.ToolStrip> 的“溢出”按钮。|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|获取或设置一个，它 <xref:System.Windows.Forms.ToolStripRenderer> 用于自定义的外观和行为 (的外观和感觉) <xref:System.Windows.Forms.ToolStrip> 。|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|获取或设置要应用于 <xref:System.Windows.Forms.ToolStrip> 的绘制样式。|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|在 <xref:System.Windows.Forms.ToolStrip.Renderer%2A> 属性更改时引发。|  
  
 <xref:System.Windows.Forms.ToolStrip>通过使用多个伴生类来实现控件的灵活性。 下面是一些最值得注意的事项：  
  
### <a name="important-toolstrip-companion-classes"></a>重要的 ToolStrip 伴生类  
  
|名称|描述|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|替换类并向类添加功能 <xref:System.Windows.Forms.MainMenu> 。|  
|<xref:System.Windows.Forms.StatusStrip>|替换类并向类添加功能 <xref:System.Windows.Forms.StatusBar> 。|  
|<xref:System.Windows.Forms.ContextMenuStrip>|替换类并向类添加功能 <xref:System.Windows.Forms.ContextMenu> 。|  
|<xref:System.Windows.Forms.ToolStripItem>|管理 <xref:System.Windows.Forms.ToolStrip> 、 <xref:System.Windows.Forms.ToolStripControlHost> 或可以包含的所有元素的事件和布局的抽象基类 <xref:System.Windows.Forms.ToolStripDropDown> 。|  
|<xref:System.Windows.Forms.ToolStripContainer>|提供一个容器，该容器在窗体的每一侧有一个面板，可通过多种方式排列控件。|  
|<xref:System.Windows.Forms.ToolStripRenderer>|处理 <xref:System.Windows.Forms.ToolStrip> 对象的绘制功能。|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|提供 Microsoft Office 样式的外观。|  
|<xref:System.Windows.Forms.ToolStripManager>|控制 <xref:System.Windows.Forms.ToolStrip> 的呈现和漂浮，以及 <xref:System.Windows.Forms.MenuStrip>、<xref:System.Windows.Forms.ToolStripDropDownMenu> 和 <xref:System.Windows.Forms.ToolStripMenuItem> 对象的合并。|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|指定 (自定义、Windows XP 或 Microsoft Office Professional) 应用于 <xref:System.Windows.Forms.ToolStrip> 窗体中包含的多个对象的绘制样式。|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|指定 (自定义、Windows XP 或 Microsoft Office Professional) 应用于 <xref:System.Windows.Forms.ToolStrip> 窗体中包含的一个对象的绘制样式。|  
|<xref:System.Windows.Forms.ToolStripControlHost>|承载并非专门 <xref:System.Windows.Forms.ToolStrip> 控制但需要其功能的其他控件 <xref:System.Windows.Forms.ToolStrip> 。|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|指定 <xref:System.Windows.Forms.ToolStripItem> 是要在主上还是在溢出上进行布局 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip> 。|  
  
 有关详细信息，请参阅 [Toolstrip 技术摘要](toolstrip-technology-summary.md) 和 [Toolstrip 控件体系结构](toolstrip-control-architecture.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
