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
# <a name="how-to-play-media-with-animations"></a>如何：播放带有动画的媒体
此示例演示如何使用相同的和类同时播放媒体和动画 <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> <xref:System.Windows.Media.Animation.Storyboard> 。  
  
## <a name="example"></a>示例  
 您可以将一个或多个 <xref:System.Windows.Media.MediaTimeline> 对象 <xref:System.Windows.Media.Animation.Storyboard> 与其他对象（ <xref:System.Windows.Media.Animation.Timeline> 如动画）一起使用。  
  
 下面的示例将 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> 的属性设置 <xref:System.Windows.Media.Animation.Storyboard> 为的值，该值 `Slip` 指定在此示例中的媒体 (视频) 进度之前，动画不会进行。 如果媒体播放因加载时间而延迟，可能需要此功能。  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>
- [操作指南主题](audio-and-video-how-to-topics.md)
- [演示图板概述](storyboards-overview.md)
- [关键帧动画概述](key-frame-animations-overview.md)
- [动画概述](animation-overview.md)
- [图形和多媒体](index.md)
