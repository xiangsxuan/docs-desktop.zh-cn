---
title: TreeView 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TreeView
- templates [WPF], TreeView
- parts [WPF], TreeView
- states [WPF], TreeView
- styles [WPF], TreeView
- TreeView [WPF], styles and templates
ms.assetid: a49adb77-0202-4caa-b94a-8bb110d7fa9a
ms.openlocfilehash: e3c5743b2afefb4abfac5d71c6f5ccd8281ce453
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971027"
---
# <a name="treeview-styles-and-templates"></a>TreeView 样式和模板
本主题描述控件的样式和模板 <xref:System.Windows.Controls.TreeView> 。 您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。 有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。  
  
## <a name="treeview-parts"></a>TreeView 部件  
 <xref:System.Windows.Controls.TreeView>控件没有任何命名部分。  
  
 为创建时 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.TreeView> ，模板 <xref:System.Windows.Controls.ItemsPresenter> 在中可能包含 <xref:System.Windows.Controls.ScrollViewer> 。  (<xref:System.Windows.Controls.ItemsPresenter> 显示中的每一项，则在 <xref:System.Windows.Controls.TreeView> <xref:System.Windows.Controls.ScrollViewer> 控件内启用滚动) 。  如果不 <xref:System.Windows.Controls.ItemsPresenter> 是的直接子级 <xref:System.Windows.Controls.ScrollViewer> ，则必须指定 <xref:System.Windows.Controls.ItemsPresenter> 名称 `ItemsPresenter` 。  
  
## <a name="treeview-states"></a>TreeView 状态  
 下表列出了控件的可视状态 <xref:System.Windows.Controls.TreeView> 。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。|  
  
## <a name="treeviewitem-parts"></a>TreeViewItem 部件  
 下表列出了控件的已命名部件 <xref:System.Windows.Controls.TreeViewItem> 。  
  
|组成部分|类型|描述|  
|----------|----------|-----------------|  
|PART_Header|<xref:System.Windows.FrameworkElement>|包含控件标题内容的视觉元素 <xref:System.Windows.Controls.TreeView> 。|  
  
## <a name="treeviewitem-states"></a>TreeViewItem 状态  
 下表列出了控件的可视状态 <xref:System.Windows.Controls.TreeViewItem> 。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|----------------------|---------------------------|-----------------|  
|普通|CommonStates|默认状态。|  
|MouseOver|CommonStates|鼠标指针置于上 <xref:System.Windows.Controls.TreeViewItem> 。|  
|已禁用|CommonStates|<xref:System.Windows.Controls.TreeViewItem>已禁用。|  
|已设定焦点|FocusStates|<xref:System.Windows.Controls.TreeViewItem>具有焦点。|  
|失去焦点|FocusStates|没有 <xref:System.Windows.Controls.TreeViewItem> 焦点。|  
|展开|ExpansionStates|<xref:System.Windows.Controls.TreeViewItem>控件已展开。|  
|Collapsed|ExpansionStates|<xref:System.Windows.Controls.TreeViewItem>控件已折叠。|  
|HasItems|HasItemsStates|<xref:System.Windows.Controls.TreeViewItem>具有项。|  
|NoItems|HasItemsStates|没有 <xref:System.Windows.Controls.TreeViewItem> 项。|  
|选定|SelectionStates|<xref:System.Windows.Controls.TreeViewItem> 已选定。|  
|SelectedInactive|SelectionStates|<xref:System.Windows.Controls.TreeViewItem>处于选中状态，但不处于活动状态。|  
|未选定|SelectionStates|<xref:System.Windows.Controls.TreeViewItem> 未选定。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。|  
  
## <a name="treeview-controltemplate-example"></a>TreeView System.windows.controls.controltemplate> 示例  
 下面的示例演示如何为 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.TreeView> 控件及其关联的类型定义。  
  
 [!code-xaml[ControlTemplateExamples#TreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
 上一示例使用了一个或多个以下资源。  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Control 样式和模板](control-styles-and-templates.md)
- [控件自定义](control-customization.md)
- [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [创建控件模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
