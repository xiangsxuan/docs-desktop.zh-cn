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
# <a name="how-to-play-media-using-a-videodrawing"></a><span data-ttu-id="1fdf5-102">如何：使用 VideoDrawing 播放媒体</span><span class="sxs-lookup"><span data-stu-id="1fdf5-102">How to: Play Media using a VideoDrawing</span></span>
<span data-ttu-id="1fdf5-103">若要播放音频或视频文件，请使用 <xref:System.Windows.Media.VideoDrawing> 和 <xref:System.Windows.Media.MediaPlayer> 。</span><span class="sxs-lookup"><span data-stu-id="1fdf5-103">To play an audio or video file, you use a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer>.</span></span> <span data-ttu-id="1fdf5-104">加载并播放媒体有两种方法。</span><span class="sxs-lookup"><span data-stu-id="1fdf5-104">There are two ways to load and play media.</span></span> <span data-ttu-id="1fdf5-105">第一种方法是 <xref:System.Windows.Media.MediaPlayer> 单独使用和 <xref:System.Windows.Media.VideoDrawing> ，第二种方法是创建您自己的 <xref:System.Windows.Media.MediaTimeline> 以便与和一起使用 <xref:System.Windows.Media.MediaPlayer> <xref:System.Windows.Media.VideoDrawing> 。</span><span class="sxs-lookup"><span data-stu-id="1fdf5-105">The first is to use a <xref:System.Windows.Media.MediaPlayer> and a <xref:System.Windows.Media.VideoDrawing> by themselves, and the second way is to create your own <xref:System.Windows.Media.MediaTimeline> to use with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1fdf5-106">当媒体随应用程序一起分发时，无法像图像那样将媒体文件用作项目资源。</span><span class="sxs-lookup"><span data-stu-id="1fdf5-106">When distributing media with your application, you cannot use a media file as a project resource, like you would an image.</span></span> <span data-ttu-id="1fdf5-107">在项目文件中，必须改为将媒体类型设置为 `Content` 并将 `CopyToOutputDirectory` 设置为 `PreserveNewest` 或 `Always`。</span><span class="sxs-lookup"><span data-stu-id="1fdf5-107">In your project file, you must instead set the media type to `Content` and set `CopyToOutputDirectory` to `PreserveNewest` or `Always`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fdf5-108">示例</span><span class="sxs-lookup"><span data-stu-id="1fdf5-108">Example</span></span>  
 <span data-ttu-id="1fdf5-109">下面的示例使用 <xref:System.Windows.Media.VideoDrawing> 和 <xref:System.Windows.Media.MediaPlayer> 来播放视频文件一次。</span><span class="sxs-lookup"><span data-stu-id="1fdf5-109">The following example uses a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer> to play a video file once.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 <span data-ttu-id="1fdf5-110">若要获取对媒体的其他计时控制，请将 <xref:System.Windows.Media.MediaTimeline> 与 <xref:System.Windows.Media.MediaPlayer> 和 <xref:System.Windows.Media.VideoDrawing> 对象一起使用。</span><span class="sxs-lookup"><span data-stu-id="1fdf5-110">To gain additional timing control over the media, use a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects.</span></span> <span data-ttu-id="1fdf5-111"><xref:System.Windows.Media.MediaTimeline>使您能够指定是否应重复视频。</span><span class="sxs-lookup"><span data-stu-id="1fdf5-111">The <xref:System.Windows.Media.MediaTimeline> enables you to specify whether the video should repeat.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fdf5-112">示例</span><span class="sxs-lookup"><span data-stu-id="1fdf5-112">Example</span></span>  
 <span data-ttu-id="1fdf5-113">下面的示例将 <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.MediaPlayer> 和和对象结合使用 <xref:System.Windows.Media.VideoDrawing> 来反复播放视频。</span><span class="sxs-lookup"><span data-stu-id="1fdf5-113">The following example uses a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects to play a video repeatedly.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <span data-ttu-id="1fdf5-114">请注意，当你使用时 <xref:System.Windows.Media.MediaTimeline> ，你将使用 <xref:System.Windows.Media.Animation.ClockController> 从的属性返回的交互式 <xref:System.Windows.Media.Animation.Clock.Controller%2A> <xref:System.Windows.Media.MediaClock> 来控制媒体播放，而不是的交互式方法 <xref:System.Windows.Media.MediaPlayer> 。</span><span class="sxs-lookup"><span data-stu-id="1fdf5-114">Note that, when you use a <xref:System.Windows.Media.MediaTimeline>, you use the interactive <xref:System.Windows.Media.Animation.ClockController> returned from the <xref:System.Windows.Media.Animation.Clock.Controller%2A> property of the <xref:System.Windows.Media.MediaClock> to control media playback instead of the interactive methods of <xref:System.Windows.Media.MediaPlayer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fdf5-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fdf5-115">See also</span></span>

- <xref:System.Windows.Media.VideoDrawing>
- [<span data-ttu-id="1fdf5-116">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="1fdf5-116">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
