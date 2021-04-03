---
title: 如何：定义名称范围
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- name scope [WPF], defining
- Storyboards [WPF], animating in procedural code
- animation [WPF], Storyboards [WPF], in procedural code
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
ms.openlocfilehash: a03f477dd31909e8cb9dde9cd29da6f38d665758
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970378"
---
# <a name="how-to-define-a-name-scope"></a><span data-ttu-id="21409-102">如何：定义名称范围</span><span class="sxs-lookup"><span data-stu-id="21409-102">How to: Define a Name Scope</span></span>
<span data-ttu-id="21409-103">若要 <xref:System.Windows.Media.Animation.Storyboard> 在代码中进行动画处理，必须创建 <xref:System.Windows.NameScope> 并向拥有该名称范围的元素注册目标对象的名称。</span><span class="sxs-lookup"><span data-stu-id="21409-103">To animate with <xref:System.Windows.Media.Animation.Storyboard> in code, you must create a <xref:System.Windows.NameScope> and register the target objects' names with the element that owns that name scope.</span></span> <span data-ttu-id="21409-104">在下面的示例中，为 <xref:System.Windows.NameScope> 创建了 `myMainPanel` 。</span><span class="sxs-lookup"><span data-stu-id="21409-104">In the following example, a <xref:System.Windows.NameScope> is created for `myMainPanel`.</span></span> <span data-ttu-id="21409-105">将 `button1` 向面板中添加两个按钮，并将 `button2` 其名称注册到其中。</span><span class="sxs-lookup"><span data-stu-id="21409-105">Two buttons, `button1` and `button2`, are added to the panel, and their names registered.</span></span> <span data-ttu-id="21409-106">创建了多个动画和 <xref:System.Windows.Media.Animation.Storyboard> 。</span><span class="sxs-lookup"><span data-stu-id="21409-106">Several animations and a <xref:System.Windows.Media.Animation.Storyboard> are created.</span></span> <span data-ttu-id="21409-107">情节提要的 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 方法用于启动动画。</span><span class="sxs-lookup"><span data-stu-id="21409-107">The storyboard's <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method is used to start the animations.</span></span>  
  
 <span data-ttu-id="21409-108">由于 `button1` 、 `button2` 和 `myMainPanel` 均共享相同的名称范围，因此可以将其中任何一个与方法结合使用 <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 来启动动画。</span><span class="sxs-lookup"><span data-stu-id="21409-108">Because `button1`, `button2`, and `myMainPanel` all share the same name scope, any one of them can be used with the <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method to start the animations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21409-109">示例</span><span class="sxs-lookup"><span data-stu-id="21409-109">Example</span></span>  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="21409-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21409-110">See also</span></span>

- [<span data-ttu-id="21409-111">使用情节提要对属性进行动画处理</span><span class="sxs-lookup"><span data-stu-id="21409-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="21409-112">动画概述</span><span class="sxs-lookup"><span data-stu-id="21409-112">Animation Overview</span></span>](animation-overview.md)
