---
title: TableLayoutPanel 控件的最佳做法
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
ms.openlocfilehash: e46d0fe6913bec61bd56199b7cb56a9b24d15bd0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971323"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a>TableLayoutPanel 控件的最佳做法
<xref:System.Windows.Forms.TableLayoutPanel>控件提供了强大的布局功能，您应该在 Windows 窗体上使用之前仔细考虑。

## <a name="recommendations"></a>建议
 以下建议将帮助你将控件用于 <xref:System.Windows.Forms.TableLayoutPanel> 其最佳优势。

### <a name="targeted-use"></a>目标使用
 谨慎使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件。 在需要可调整大小的布局的所有情况下，不应使用此方法。 下面的列表介绍了使用控件的最大优势 <xref:System.Windows.Forms.TableLayoutPanel> ：

- 布局，其中，窗体的多个部分都按比例调整大小。

- 将在运行时动态修改或生成的布局，例如基于首选项添加或缩减用户可自定义字段的数据输入窗体。

- 应保持整体固定大小的布局。 例如，你可能会有一个对话框，该对话框应保持小于 800 x 600，但你需要支持本地化的字符串。

 下面的列表介绍了使用控件无法显著提高的布局 <xref:System.Windows.Forms.TableLayoutPanel> ：

- 简单的数据输入窗体，其中包含一列标签和单列文本输入区域。

- 具有单个大型显示区域的窗体，当发生调整大小时，应填充所有可用空间。 这种情况的一个示例是显示单个控件的窗体 <xref:System.Windows.Forms.PropertyGrid> 。 在这种情况下，请使用锚定，因为在调整窗体大小时，其他任何内容都不应扩展。

 仔细选择哪些控件需要在 <xref:System.Windows.Forms.TableLayoutPanel> 控件中。 如果你有足够的空间使文本使用锚定增长30%，请考虑 <xref:System.Windows.Forms.Control.Anchor%2A> 只使用属性。 如果可以估计布局所需的空间，则和的使用 <xref:System.Windows.Forms.Control.Dock%2A> <xref:System.Windows.Forms.Control.Anchor%2A> 比估计剩余空间和行为的详细信息更容易 <xref:System.Windows.Forms.Control.AutoSize%2A> 。

 通常，在通过控件设计布局时 <xref:System.Windows.Forms.TableLayoutPanel> ，请尽可能简化设计。

### <a name="use-the-document-outline-window"></a>使用 "文档大纲" 窗口
 "文档大纲" 窗口提供布局的树状视图，您可以使用这些视图来操作控件的 z 顺序和父子关系。 从 " **视图" 菜单** 中选择 " **其他窗口**"，然后选择 " **文档大纲**"。

### <a name="avoid-nesting"></a>避免嵌套
 避免 <xref:System.Windows.Forms.TableLayoutPanel> 在控件内嵌套其他控件 <xref:System.Windows.Forms.TableLayoutPanel> 。 调试嵌套布局可能比较困难。

### <a name="avoid-visual-inheritance"></a>避免视觉对象继承
 <xref:System.Windows.Forms.TableLayoutPanel>控件不支持 Visual Studio 的 Windows 窗体设计器中的可视化继承。 <xref:System.Windows.Forms.TableLayoutPanel>派生类中的控件在设计时显示为 "已锁定"。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
