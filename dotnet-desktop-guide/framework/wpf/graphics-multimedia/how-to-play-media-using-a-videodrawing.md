---
title: 如何：使用 VideoDrawing 播放媒体
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 2e2007525be770186a17cf9d2d42a7c52ba93fba
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973016"
---
# <a name="how-to-play-media-using-a-videodrawing"></a>如何：使用 VideoDrawing 播放媒体
若要播放音频或视频文件，请使用 <xref:System.Windows.Media.VideoDrawing> 和 <xref:System.Windows.Media.MediaPlayer> 。 加载并播放媒体有两种方法。 第一种方法是 <xref:System.Windows.Media.MediaPlayer> 单独使用和 <xref:System.Windows.Media.VideoDrawing> ，第二种方法是创建您自己的 <xref:System.Windows.Media.MediaTimeline> 以便与和一起使用 <xref:System.Windows.Media.MediaPlayer> <xref:System.Windows.Media.VideoDrawing> 。  
  
> [!NOTE]
> 当媒体随应用程序一起分发时，无法像图像那样将媒体文件用作项目资源。 在项目文件中，必须改为将媒体类型设置为 `Content` 并将 `CopyToOutputDirectory` 设置为 `PreserveNewest` 或 `Always`。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.VideoDrawing> 和 <xref:System.Windows.Media.MediaPlayer> 来播放视频文件一次。  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 若要获取对媒体的其他计时控制，请将 <xref:System.Windows.Media.MediaTimeline> 与 <xref:System.Windows.Media.MediaPlayer> 和 <xref:System.Windows.Media.VideoDrawing> 对象一起使用。 <xref:System.Windows.Media.MediaTimeline>使您能够指定是否应重复视频。  
  
## <a name="example"></a>示例  
 下面的示例将 <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.MediaPlayer> 和和对象结合使用 <xref:System.Windows.Media.VideoDrawing> 来反复播放视频。  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 请注意，当你使用时 <xref:System.Windows.Media.MediaTimeline> ，你将使用 <xref:System.Windows.Media.Animation.ClockController> 从的属性返回的交互式 <xref:System.Windows.Media.Animation.Clock.Controller%2A> <xref:System.Windows.Media.MediaClock> 来控制媒体播放，而不是的交互式方法 <xref:System.Windows.Media.MediaPlayer> 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.VideoDrawing>
- [Drawing 对象概述](drawing-objects-overview.md)
