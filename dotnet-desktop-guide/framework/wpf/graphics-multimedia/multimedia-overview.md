---
title: 多媒体概述
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: 6380e5cb11899c7995dc0dd0d3c9a79b9ea4868f
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667715"
---
# <a name="multimedia-overview"></a>多媒体概述
[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 中的多媒体功能能够使音频和视频集成到应用程序，增强用户体验。 本主题介绍了 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 的多媒体功能。  

<a name="mediaapi"></a>
## <a name="media-api"></a>媒体 API  
 <xref:System.Windows.Controls.MediaElement>和 <xref:System.Windows.Media.MediaPlayer> 类用于显示音频或视频内容。 可以以交互方式或时钟控制这些类。 这些类可在 Microsoft Windows Media Player 10 控件上用于播放媒体。 要使用哪个类取决于方案。  
  
 <xref:System.Windows.Controls.MediaElement> 是一个 <xref:System.Windows.UIElement> ，它受 [布局](../advanced/layout.md) 支持，并可用作许多控件的内容。 它也可用在 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 与代码中。 <xref:System.Windows.Media.MediaPlayer>另一方面，设计用于 <xref:System.Windows.Media.Drawing> 对象，缺少布局支持。 使用加载的媒体 <xref:System.Windows.Media.MediaPlayer> 只能使用 <xref:System.Windows.Media.VideoDrawing> 或直接与交互 <xref:System.Windows.Media.DrawingContext> 。 <xref:System.Windows.Media.MediaPlayer> 不能在 XAML 中使用。  
  
 有关绘图对象和绘图上下文的详细信息，请参阅 [Drawing 对象概述](drawing-objects-overview.md)。  
  
> [!NOTE]
> 使用应用程序分发媒体时，不可将媒体文件用作项目资源。 在项目文件中，必须改为将媒体类型设置为 `Content` 并将 `CopyToOutputDirectory` 设置为 `PreserveNewest` 或 `Always`。  
  
<a name="mediaplaybackmodes"></a>
## <a name="media-playback-modes"></a>媒体播放模式  
  
> [!NOTE]
> <xref:System.Windows.Controls.MediaElement>和都 <xref:System.Windows.Media.MediaPlayer> 具有类似的成员。 本节中的链接是指 <xref:System.Windows.Controls.MediaElement> 类成员。 除非特别注明，否则 <xref:System.Windows.Controls.MediaElement> 也可以在类中找到链接到类中的成员 <xref:System.Windows.Media.MediaPlayer> 。  
  
 要了解 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 中的媒体播放，需要了解可以播放媒体的不同模式。 <xref:System.Windows.Controls.MediaElement>和均 <xref:System.Windows.Media.MediaPlayer> 可用于两种不同的媒体模式：独立模式和时钟模式。 媒体模式由 <xref:System.Windows.Controls.MediaElement.Clock%2A> 属性确定。 如果 <xref:System.Windows.Controls.MediaElement.Clock%2A> 为 `null` ，则媒体对象处于独立模式。 如果 <xref:System.Windows.Controls.MediaElement.Clock%2A> 为非 null，则媒体对象处于时钟模式。 默认情况下，媒体对象处于独立模式。  
  
### <a name="independent-mode"></a>独立模式  
 在独立模式下，媒体内容驱动媒体播放。 独立模式可实现下列选项：  
  
- <xref:System.Uri>可以直接指定媒体。  
  
- 可以直接控制媒体播放。  
  
- <xref:System.Windows.Controls.MediaElement.Position%2A>可以修改媒体的和 <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> 属性。  
  
 可以通过设置 <xref:System.Windows.Controls.MediaElement> 对象的 <xref:System.Windows.Controls.MediaElement.Source%2A> 属性或通过调用 <xref:System.Windows.Media.MediaPlayer> 对象的方法加载媒体 <xref:System.Windows.Media.MediaPlayer.Open%2A> 。  
  
 要在独立模式下控制媒体播放，可使用媒体对象的控制方法。 可用的控制方法包括 <xref:System.Windows.Controls.MediaElement.Play%2A> 、 <xref:System.Windows.Controls.MediaElement.Pause%2A> 、 <xref:System.Windows.Controls.MediaElement.Close%2A> 和 <xref:System.Windows.Controls.MediaElement.Stop%2A> 。 对于 <xref:System.Windows.Controls.MediaElement> ，仅当设置为时，才可以使用这些方法的交互式控件 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual> 。 这些方法在媒体对象处于时钟模式时不可用。  
  
 请参阅[控制 MediaElement（Play、Pause、Stop、Volume 和 Speed）](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)了解独立模式的示例。  
  
### <a name="clock-mode"></a>时钟模式  
 在时钟模式下， <xref:System.Windows.Media.MediaTimeline> 驱动器将播放。 时钟模式具有以下特征：  
  
- 媒体的 <xref:System.Uri> 通过间接设置 <xref:System.Windows.Media.MediaTimeline> 。  
  
- 可由时钟控制媒体播放。 不可使用媒体对象的控制方法。  
  
- 通过设置 <xref:System.Windows.Media.MediaTimeline> 对象的 <xref:System.Windows.Media.MediaTimeline.Source%2A> 属性，从时间线创建时钟，并将时钟分配给 media 对象，可以加载媒体。 如果 <xref:System.Windows.Media.MediaTimeline> 中的位于目标中，则还会以这种方式加载媒体 <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Controls.MediaElement> 。  
  
 若要以时钟模式控制媒体播放， <xref:System.Windows.Media.Animation.ClockController> 必须使用控制方法。 <xref:System.Windows.Media.Animation.ClockController>从 <xref:System.Windows.Media.Animation.ClockController> 的属性获取 <xref:System.Windows.Media.MediaClock> 。 如果在时钟模式下尝试使用或对象的控制 <xref:System.Windows.Controls.MediaElement> 方法 <xref:System.Windows.Media.MediaPlayer> ， <xref:System.InvalidOperationException> 将引发。  
  
 请参阅[动画概述](animation-overview.md)了解有关时钟和时间线的更多信息。  
  
 请参阅[使用情节提要控制 MediaElement](how-to-control-a-mediaelement-by-using-a-storyboard.md) 了解时钟模式的示例。  
  
<a name="mediaelement"></a>
## <a name="mediaelement-class"></a>MediaElement 类  
 向应用程序添加媒体非常简单，只需将 <xref:System.Windows.Controls.MediaElement> 控件添加到 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 应用程序的，并 <xref:System.Uri> 向要包括的媒体提供。 支持 Microsoft Windows Media Player 10 支持的所有媒体类型 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。 下面的示例演示中的的简单用法 <xref:System.Windows.Controls.MediaElement> [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 在此示例中，媒体一旦加载会自动播放。 媒体完成播放后会关闭并且所有媒体资源已发布（包括视频内存）。 这是对象的默认行为 <xref:System.Windows.Controls.MediaElement> ，由 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 和属性控制 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 。  
  
### <a name="controlling-a-mediaelement"></a>控制 MediaElement  
 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> <xref:System.Windows.Controls.MediaElement> 当为或时，和属性分别控制的行为 <xref:System.Windows.FrameworkElement.IsLoaded%2A> `true` `false` 。 <xref:System.Windows.Controls.MediaState>属性设置为会影响媒体播放行为。 例如，默认值 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 为 <xref:System.Windows.Controls.MediaState.Play> ，默认值 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 为 <xref:System.Windows.Controls.MediaState.Close> 。 这意味着，一旦 <xref:System.Windows.Controls.MediaElement> 加载并完成预缓冲，就会开始播放媒体。 一旦播放完毕，媒体就会关闭并且发布所有媒体资源。  
  
 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>和 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 属性不是控制媒体播放的唯一方法。 在时钟模式下，时钟可以控制， <xref:System.Windows.Controls.MediaElement> 当是时，交互式控制方法即可控制 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual> 。 <xref:System.Windows.Controls.MediaElement> 通过评估以下优先级来处理这种控制。  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. 卸载媒体时就位。 这可确保默认情况下释放所有媒体资源，即使 <xref:System.Windows.Media.MediaClock> 是与关联的 <xref:System.Windows.Controls.MediaElement> 。  
  
2. <xref:System.Windows.Media.MediaClock>. 如果媒体具有，则为 <xref:System.Windows.Controls.MediaElement.Clock%2A> 。 如果卸载了媒体，则 <xref:System.Windows.Media.MediaClock> 只要为，就会生效 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual> 。 时钟模式始终会重写的加载行为 <xref:System.Windows.Controls.MediaElement> 。  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. 加载媒体时就位。  
  
4. 交互式控制方法。 如果 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 为，则为 <xref:System.Windows.Controls.MediaState.Manual> 。 可用的控制方法包括 <xref:System.Windows.Controls.MediaElement.Play%2A> 、 <xref:System.Windows.Controls.MediaElement.Pause%2A> 、 <xref:System.Windows.Controls.MediaElement.Close%2A> 和 <xref:System.Windows.Controls.MediaElement.Stop%2A> 。  
  
### <a name="displaying-a-mediaelement"></a>显示 MediaElement  
 若要显示 <xref:System.Windows.Controls.MediaElement> 它，必须具有要呈现的内容，并且在 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 加载内容之前，它的和 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 属性将设置为零。 对于仅包含音频的内容，这些属性将始终为零。 对于视频内容，一旦 <xref:System.Windows.Controls.MediaElement.MediaOpened> 引发了事件， <xref:System.Windows.FrameworkElement.ActualWidth%2A> <xref:System.Windows.FrameworkElement.ActualHeight%2A> 就会报告加载的媒体的大小。 这意味着在加载媒体之前， <xref:System.Windows.Controls.MediaElement> 将不会占用中的任何物理空间， [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 除非 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> 设置或属性。  
  
 同时设置 <xref:System.Windows.FrameworkElement.Width%2A> 和 <xref:System.Windows.FrameworkElement.Height%2A> 属性会使媒体拉伸以填充为提供的区域 <xref:System.Windows.Controls.MediaElement> 。 若要保留媒体的原始纵横比， <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> 应设置或属性，但不能同时设置二者。 同时设置 <xref:System.Windows.FrameworkElement.Width%2A> 和 <xref:System.Windows.FrameworkElement.Height%2A> 属性将导致媒体以固定元素大小显示，这可能并不理想。  
  
 要避免出现固定大小元素，[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 可以预滚媒体。 这是通过将设置 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 为或来完成的 <xref:System.Windows.Controls.MediaState.Play> <xref:System.Windows.Controls.MediaState.Pause> 。 在 <xref:System.Windows.Controls.MediaState.Pause> 状态下，媒体将预缓冲，并显示第一帧。 在 <xref:System.Windows.Controls.MediaState.Play> 状态下，媒体将预缓冲并开始播放。  
  
<a name="mediaplayer"></a>
## <a name="mediaplayer-class"></a>MediaPlayer 类  
 如果 <xref:System.Windows.Controls.MediaElement> 类是框架元素，则 <xref:System.Windows.Media.MediaPlayer> 类设计为在对象中使用 <xref:System.Windows.Media.Drawing> 。 当你可能会牺牲框架级别功能来获得性能优势或需要功能时，使用绘图对象 <xref:System.Windows.Freezable> 。 <xref:System.Windows.Media.MediaPlayer> 使你能够利用这些功能，同时在应用程序中提供媒体内容。 与类似 <xref:System.Windows.Controls.MediaElement> ， <xref:System.Windows.Media.MediaPlayer> 可以在独立模式或时钟模式下使用，但不会使对象处于已 <xref:System.Windows.Controls.MediaElement> 卸载状态和已加载状态。 这会降低的播放控制复杂性 <xref:System.Windows.Media.MediaPlayer> 。  
  
### <a name="controlling-mediaplayer"></a>控制 MediaPlayer  
 由于 <xref:System.Windows.Media.MediaPlayer> 是无状态的，因此仅有两种方法可控制媒体播放。  
  
1. 交互式控制方法。 在独立模式下就地 (`null` <xref:System.Windows.Media.MediaPlayer.Clock%2A> 属性) 。  
  
2. <xref:System.Windows.Media.MediaClock>. 如果媒体具有，则为 <xref:System.Windows.Media.MediaPlayer.Clock%2A> 。  
  
### <a name="displaying-a-mediaplayer"></a>显示 MediaPlayer  
 从技术上说， <xref:System.Windows.Media.MediaPlayer> 无法显示，因为它没有物理表示形式。 但是，它可用于在中使用类提供媒体 <xref:System.Windows.Media.Drawing> <xref:System.Windows.Media.VideoDrawing> 。 下面的示例演示 <xref:System.Windows.Media.VideoDrawing> 如何使用来显示媒体。  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 有关对象的详细信息，请参阅 [绘图对象概述](drawing-objects-overview.md) <xref:System.Windows.Media.Drawing> 。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.DrawingGroup>
- [布局](../advanced/layout.md)
- [操作指南主题](audio-and-video-how-to-topics.md)
