---
title: 使用视觉样式呈现控件
ms.date: 03/30/2017
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- themes [Windows Forms], XP visual styles in Window Forms
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- visual themes [Windows Forms], rendering Windows Forms controls
- user controls [Windows Forms], painting
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a5b178ba-610e-46c4-a6c0-509c0886a744
ms.openlocfilehash: 32bcbab585c39be4a72150bf49820d4a16f1691f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972012"
---
# <a name="rendering-controls-with-visual-styles"></a>使用视觉样式呈现控件
.NET Framework 支持在支持使用视觉样式的操作系统中使用视觉样式呈现控件和其他 Windows 用户界面 (UI) 元素。 本主题讨论了在 .NET Framework 中的几个级别的支持，这些控件和其他 UI 元素都具有操作系统的当前视觉样式。  
  
## <a name="rendering-classes-for-common-controls"></a>公共控件的呈现类  
 呈现控件是指绘制控件的用户界面。 <xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间提供了用来呈现某些公共 Windows 窗体控件的 <xref:System.Windows.Forms.ControlPaint> 类。 但是，此类以经典 Windows 样式绘制的控件，当在启用了视觉样式的应用程序中绘制自定义控件时，难以维护 UI 体验的一致性。  
  
 .NET Framework 2.0 包括命名空间中的类 <xref:System.Windows.Forms?displayProperty=nameWithType> ，这些类可呈现具有视觉样式的公共控件的部件和状态。 每个这样的类都包括使用操作系统当前视觉样式绘制控件和特定状态控件部件的 `static` 方法。  
  
 其中一些类旨在绘制相关控件，而不考虑视觉样式是否可用。 如果启用了视觉样式，类成员将使用视觉样式绘制相关控件；如果禁用了视觉样式，类成员将以经典 Windows 样式绘制控件。 这些类包括：  
  
- <xref:System.Windows.Forms.ButtonRenderer>  
  
- <xref:System.Windows.Forms.CheckBoxRenderer>  
  
- <xref:System.Windows.Forms.GroupBoxRenderer>  
  
- <xref:System.Windows.Forms.RadioButtonRenderer>  
  
 视觉样式可用时，其他类才能绘制相关控件，如果禁用了视觉样式，则类成员会引发异常。 这些类包括：  
  
- <xref:System.Windows.Forms.ComboBoxRenderer>  
  
- <xref:System.Windows.Forms.ProgressBarRenderer>  
  
- <xref:System.Windows.Forms.ScrollBarRenderer>  
  
- <xref:System.Windows.Forms.TabRenderer>  
  
- <xref:System.Windows.Forms.TextBoxRenderer>  
  
- <xref:System.Windows.Forms.TrackBarRenderer>  
  
 有关使用这些类绘制控件的详细信息，请参阅 [How to: Use a Control Rendering Class](how-to-use-a-control-rendering-class.md)。  
  
## <a name="visual-style-element-and-rendering-classes"></a>视觉样式元素和呈现类  
 <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> 命名空间包含用于绘制和获取视觉样式支持的任何控件或 UI 元素信息的类。 支持的控件包括在 <xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间中具有呈现类的公共控件（请参阅上一节）以及诸如选项卡控件和 rebar 控件的其他控件。 其他受支持的 UI 元素包括“开始”  菜单、任务栏和 Windows 非工作区的各部分。  
  
 <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> 命名空间的主要类为 <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> 和 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer>。 <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> 是一个基础类，用于标识视觉样式支持的任何控件或用户界面元素。 除了 <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> 本身， <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> 命名空间包含许多 <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> 嵌套类，这些类具有为视觉样式支持的控件、控件部件或其他 UI 元素的状态返回 `static` 的 <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> 属性。  
  
 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> 提供一些方法，这些方法可以绘制和获取由操作系统当前视觉样式定义的每个 <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> 的信息。 可以检索的元素信息包括其默认大小、背景类型和颜色定义。 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> 包装来自 Windows Platform SDK 的 Windows Shell 部分的视觉样式 (UxTheme) API 的功能。 有关详细信息，请参阅 [启用视觉样式](/windows/desktop/controls/cookbook-overview)。  
  
 有关使用 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> 和 <xref:System.Windows.Forms.VisualStyles.VisualStyleElement>的详细信息，请参阅 [How to: Render a Visual Style Element](how-to-render-a-visual-style-element.md)。  
  
## <a name="enabling-visual-styles"></a>启用视觉样式  
 若要为 .NET Framework 版本1.0 编写的应用程序启用视觉样式，程序员必须包括一个应用程序清单，该清单指定将用于绘制控件的 ComCtl32.dll 版本6或更高版本。 使用 .NET Framework 版本1.1 或更高版本生成的应用程序可以使用 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 类的方法 <xref:System.Windows.Forms.Application> 。  
  
## <a name="checking-for-visual-styles-support"></a>检查视觉样式支持  
 <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A> 类的 <xref:System.Windows.Forms.Application> 属性指示当前应用程序是否正在使用视觉样式绘制控件。 绘制自定义控件时，可以检查 <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A> 的值来确定是否应使用视觉样式呈现控件。 下表列出了 <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A> 返回 `true`必须存在的四个条件。  
  
|条件|说明|  
|---------------|-----------|  
|操作系统支持视觉样式。|若要单独验证这种情况，请使用 <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation.IsSupportedByOS%2A> 类的 <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation> 属性。|  
|用户已在操作系统中启用视觉样式。|若要单独验证这种情况，请使用 <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation.IsEnabledByUser%2A> 类的 <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation> 属性。|  
|应用程序中已启用视觉样式。|可以通过调用 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 方法或使用指定用 ComCtl32.dll 版本 6 或更高版本绘制控件的应用程序清单来启用应用程序中的视觉样式。|  
|正在使用视觉样式来绘制应用程序窗口的工作区。|若要单独验证这种情况，请使用 <xref:System.Windows.Forms.Application.VisualStyleState%2A> 类的 <xref:System.Windows.Forms.Application> 属性，验证它是否具有 <xref:System.Windows.Forms.VisualStyles.VisualStyleState.ClientAreaEnabled?displayProperty=nameWithType> 或 <xref:System.Windows.Forms.VisualStyles.VisualStyleState.ClientAndNonClientAreasEnabled?displayProperty=nameWithType>值。|  
  
 若要确定用户何时启用或禁用视觉样式，或何时从一种视觉样式切换到另种，请检查 <xref:Microsoft.Win32.UserPreferenceCategory.VisualStyle?displayProperty=nameWithType> 或 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanging?displayProperty=nameWithType> 事件处理程序中的 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged?displayProperty=nameWithType> 值。  
  
> [!IMPORTANT]
> 如果想要在用户启用或切换视觉样式时使用 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> 来呈现控件或 UI 元素，请确保在处理 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 事件而非 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanging> 事件时这样做。 处理 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> 时如果使用 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanging>类，则会引发异常。  
  
## <a name="see-also"></a>另请参阅

- [自定义控件的绘制和呈现](custom-control-painting-and-rendering.md)
