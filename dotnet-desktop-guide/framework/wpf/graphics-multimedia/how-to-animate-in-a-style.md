---
title: 如何在样式中进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
ms.openlocfilehash: 82a1406f180de26a48808f7a094a8addab29a042
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973831"
---
# <a name="how-to-animate-in-a-style"></a>如何在样式中进行动画处理

此示例演示如何在样式中对属性进行动画处理。 在样式中进行动画处理时，只有定义了该样式的框架元素才能直接作为目标。 若要以可冻结的对象为目标，必须从带样式的元素的属性 "向下"。

在下面的示例中，多个动画是在样式中定义的，并应用于 <xref:System.Windows.Controls.Button> 。 当用户将鼠标移动到该按钮上时，它会不断地从不透明过渡到部分半透明并再次后退。 当用户将鼠标移出按钮时，它将完全不透明。 单击该按钮时，它的背景色将从橙色变为白色，并再次返回。 由于 <xref:System.Windows.Media.SolidColorBrush> 不能直接将用于绘制按钮的用于绘制按钮，因此可通过对从按钮的属性进行访问 <xref:System.Windows.Controls.Control.Background%2A> 。

## <a name="example"></a>示例

[!code-xaml[timingbehaviors_snip#21](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]

请注意，在样式中进行动画处理时，可以将不存在的对象设定为目标。 例如，假设您的样式使用 <xref:System.Windows.Media.SolidColorBrush> 来设置按钮的背景属性，但在某些时候将重写样式，并使用设置按钮的背景 <xref:System.Windows.Media.LinearGradientBrush> 。  尝试对进行动画处理 <xref:System.Windows.Media.SolidColorBrush> 不会引发异常，动画将自动失败。

有关情节提要目标语法的详细信息，请参阅 [情节提要概述](storyboards-overview.md)。 有关动画的详细信息，请参阅 [动画概述](animation-overview.md)。 有关样式的详细信息，请参阅 [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)。
