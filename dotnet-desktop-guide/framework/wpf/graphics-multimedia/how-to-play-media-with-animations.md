---
title: 如何：播放带有动画的媒体
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: 200f9d62c67a02088fe5a5789cdb41a04837d430
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970850"
---
# <a name="how-to-play-media-with-animations"></a><span data-ttu-id="feee2-102">如何：播放带有动画的媒体</span><span class="sxs-lookup"><span data-stu-id="feee2-102">How to: Play Media with Animations</span></span>
<span data-ttu-id="feee2-103">此示例演示如何使用相同的和类同时播放媒体和动画 <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> <xref:System.Windows.Media.Animation.Storyboard> 。</span><span class="sxs-lookup"><span data-stu-id="feee2-103">This example shows how to play media and animations at the same time by using the <xref:System.Windows.Media.MediaTimeline> and <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classes in the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="feee2-104">示例</span><span class="sxs-lookup"><span data-stu-id="feee2-104">Example</span></span>  
 <span data-ttu-id="feee2-105">您可以将一个或多个 <xref:System.Windows.Media.MediaTimeline> 对象 <xref:System.Windows.Media.Animation.Storyboard> 与其他对象（ <xref:System.Windows.Media.Animation.Timeline> 如动画）一起使用。</span><span class="sxs-lookup"><span data-stu-id="feee2-105">You can use one or more <xref:System.Windows.Media.MediaTimeline> objects in a <xref:System.Windows.Media.Animation.Storyboard> together with other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span>  
  
 <span data-ttu-id="feee2-106">下面的示例将 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> 的属性设置 <xref:System.Windows.Media.Animation.Storyboard> 为的值，该值 `Slip` 指定在此示例中的媒体 (视频) 进度之前，动画不会进行。</span><span class="sxs-lookup"><span data-stu-id="feee2-106">The following example sets the <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> property of the <xref:System.Windows.Media.Animation.Storyboard> to a value of `Slip`, which specifies that the animation does not progress until the media (video in this example) progresses.</span></span> <span data-ttu-id="feee2-107">如果媒体播放因加载时间而延迟，可能需要此功能。</span><span class="sxs-lookup"><span data-stu-id="feee2-107">This functionality might be needed if media playback is delayed because of loading time.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="feee2-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="feee2-108">See also</span></span>

- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>
- [<span data-ttu-id="feee2-109">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="feee2-109">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="feee2-110">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="feee2-110">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="feee2-111">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="feee2-111">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="feee2-112">动画概述</span><span class="sxs-lookup"><span data-stu-id="feee2-112">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="feee2-113">图形和多媒体</span><span class="sxs-lookup"><span data-stu-id="feee2-113">Graphics and Multimedia</span></span>](index.md)
