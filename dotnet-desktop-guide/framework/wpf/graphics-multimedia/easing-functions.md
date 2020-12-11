---
title: 缓动函数
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applying mathematical formulas to animations [WPF]
- applying easing functions to animations [WPF]
- mathematical formulas [WPF], applying to animations
- animations [WPF], realistic movement
- easing functions [WPF]
- customizing easing functions [WPF]
- easing functions [WPF], definition
- easing functions [WPF], customizing
- animations [WPF], applying
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
ms.openlocfilehash: a25bde5098af853c3906a174a189fc35f33f0525
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973427"
---
# <a name="easing-functions"></a>缓动函数
缓动函数允许将自定义的数学公式应用到动画。 例如，用户可能希望某个对象逼真地弹跳或表现出像在弹簧上一样。 可使用关键帧甚至 From/To/By 动画来近似地实现这些效果，但它将需要大量工作，并且动画不如使用数学公式准确。  
  
 除了通过继承来创建自己的自定义缓动函数外 <xref:System.Windows.Media.Animation.EasingFunctionBase> ，还可以使用运行时提供的多个缓动函数之一来创建常见效果。  
  
- <xref:System.Windows.Media.Animation.BackEase>：先退动画运动，然后再开始在指示的路径中进行动画处理。  
  
- <xref:System.Windows.Media.Animation.BounceEase>：创建弹跳效果。  
  
- <xref:System.Windows.Media.Animation.CircleEase>：使用循环函数创建加速和/或减速的动画。  
  
- <xref:System.Windows.Media.Animation.CubicEase>：使用公式 *f* (*t*) = *t*<sup>3</sup>创建加速和/或减速的动画。  
  
- <xref:System.Windows.Media.Animation.ElasticEase>：创建类似于弹簧前后振荡的动画，直到其进入 rest 状态。  
  
- <xref:System.Windows.Media.Animation.ExponentialEase>：使用指数公式创建加速和/或减速的动画。  
  
- <xref:System.Windows.Media.Animation.PowerEase>：使用公式 *f* (*t*) = *t*<sup>p</sup> 创建加速和/或减速的动画，其中 p 等于 <xref:System.Windows.Media.Animation.PowerEase.Power%2A> 属性。  
  
- <xref:System.Windows.Media.Animation.QuadraticEase>：使用公式 *f* (*t*) = *t*<sup>2</sup>创建加速和/或减速的动画。  
  
- <xref:System.Windows.Media.Animation.QuarticEase>：使用公式 *f* (*t*) = *t*<sup>4</sup>创建加速和/或减速的动画。  
  
- <xref:System.Windows.Media.Animation.QuinticEase>：使用公式 *f* (*t*) = *t*<sup>5</sup>创建加速和/或减速的动画。  
  
- <xref:System.Windows.Media.Animation.SineEase>：使用正弦公式创建加速和/或减速的动画。  
  
 若要将缓动函数应用于动画，请使用 `EasingFunction` 动画的属性指定要应用于动画的缓动函数。 下面的示例将 <xref:System.Windows.Media.Animation.BounceEase> 缓动函数应用到 <xref:System.Windows.Media.Animation.DoubleAnimation> ，以创建弹跳效果。  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 在上一示例中，缓动函数应用于 From/To/By 动画。 还可以将这些缓动函数应用到关键帧动画。 以下示例显示如何将关键帧与其相关联的缓动函数结合使用，以创建一个协定上升、减速、向下展开（如同下落），然后弹跳至停止的矩形的动画。  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 您可以使用 <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> 属性更改缓动函数的行为方式，即更改动画内插的方式。 可以为以下三个值提供 <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> ：  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseIn>：内插遵循与缓动函数关联的数学公式。  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseOut>：内插遵循100% 内插减去与缓动函数关联的公式的输出。  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseInOut>：内插用于 <xref:System.Windows.Media.Animation.EasingMode.EaseIn> 动画的前半部分和后 <xref:System.Windows.Media.Animation.EasingMode.EaseOut> 半部分。  
  
 下图演示了 <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> *f* (*x*) 表示动画进度的不同值， *t* 表示时间。  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![BackEase EasingMode 图。](./media/backease-graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![BounceEase EasingMode 图。](./media/bounceease-graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![CircleEase EasingMode 图。](./media/circleease-graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![CubicEase EasingMode 图。](./media/cubicease-graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![带不同缓动模式图的 ElasticEase。](./media/elasticease-graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![带不同缓动模式的 ExponentialEase 图。](./media/exponentialease-graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![带不同缓动模式图的 QuarticEase。](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![带不同缓动模式图的 QuadraticEase](./media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![带不同缓动模式图的 QuarticEase。](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![带不同缓动模式图的 QuinticEase。](./media/quinticease-graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![不同 EasingMode 值的 SineEase](./media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
> 你可以使用 <xref:System.Windows.Media.Animation.PowerEase> 来创建与、、和相同的行为 <xref:System.Windows.Media.Animation.CubicEase> ， <xref:System.Windows.Media.Animation.QuadraticEase> 方法是 <xref:System.Windows.Media.Animation.QuarticEase> <xref:System.Windows.Media.Animation.QuinticEase> 使用 <xref:System.Windows.Media.Animation.PowerEase.Power%2A> 属性。 例如，如果要使用 <xref:System.Windows.Media.Animation.PowerEase> 替换 <xref:System.Windows.Media.Animation.CubicEase> ，请将值指定为 <xref:System.Windows.Media.Animation.PowerEase.Power%2A> 3。  
  
 除了使用运行时中包含的缓动函数外，还可以通过从继承来创建自己的自定义缓动函数 <xref:System.Windows.Media.Animation.EasingFunctionBase> 。 以下示例演示如何创建简单的自定义缓动函数。 可以通过重写方法，为缓动函数的行为方式添加自己的数学逻辑 <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> 。
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
