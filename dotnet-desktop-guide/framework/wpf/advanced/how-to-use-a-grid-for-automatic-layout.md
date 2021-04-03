---
title: 如何：使用网格进行自动布局
ms.date: 03/30/2017
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
ms.openlocfilehash: 5389d8d6130367d36a5c81b3bdc316c989474ce2
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971814"
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a><span data-ttu-id="b4ae9-102">如何：使用网格进行自动布局</span><span class="sxs-lookup"><span data-stu-id="b4ae9-102">How to: Use a Grid for Automatic Layout</span></span>
<span data-ttu-id="b4ae9-103">本示例介绍如何通过自动布局方法使用网格来创建可本地化的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b4ae9-103">This example describes how to use a grid in the automatic layout approach to creating a localizable application.</span></span>  
  
 <span data-ttu-id="b4ae9-104">的本地化 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 可能是一个耗时的过程。</span><span class="sxs-lookup"><span data-stu-id="b4ae9-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="b4ae9-105">通常，本地化人员除翻译文本外，还需要重新调整元素大小并重新定位元素。</span><span class="sxs-lookup"><span data-stu-id="b4ae9-105">Often localizers need to re-size and reposition elements in addition to translating text.</span></span> <span data-ttu-id="b4ae9-106">过去，每种语言都是 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 针对所需调整进行修改的。</span><span class="sxs-lookup"><span data-stu-id="b4ae9-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="b4ae9-107">现在， [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 您可以设计可减少调整需求的元素。</span><span class="sxs-lookup"><span data-stu-id="b4ae9-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="b4ae9-108">编写可以更轻松地调整大小和重新定位的应用程序的方法称为 `auto layout` 。</span><span class="sxs-lookup"><span data-stu-id="b4ae9-108">The approach to writing applications that can be more easily re-sized and repositioned is called `auto layout`.</span></span>  
  
 <span data-ttu-id="b4ae9-109">下面的 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 示例演示如何使用网格来定位某些按钮和文本。</span><span class="sxs-lookup"><span data-stu-id="b4ae9-109">The following [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="b4ae9-110">请注意，单元格的高度和宽度设置为 `Auto` ; 因此，包含带图像按钮的单元格会调整以适应图像。</span><span class="sxs-lookup"><span data-stu-id="b4ae9-110">Notice that the height and width of the cells are set to `Auto`; therefore the cell that contains the button with an image adjusts to fit the image.</span></span> <span data-ttu-id="b4ae9-111">由于 <xref:System.Windows.Controls.Grid> 元素可以调整到其内容，因此在采用自动布局方法设计可本地化的应用程序时，它可能非常有用。</span><span class="sxs-lookup"><span data-stu-id="b4ae9-111">Because the <xref:System.Windows.Controls.Grid> element can adjust to its content it can be useful when taking the automatic layout approach to designing applications that can be localized.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4ae9-112">示例</span><span class="sxs-lookup"><span data-stu-id="b4ae9-112">Example</span></span>  
 <span data-ttu-id="b4ae9-113">下面的示例演示如何使用网格。</span><span class="sxs-lookup"><span data-stu-id="b4ae9-113">The following example shows how to use a grid.</span></span>  
  
 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="b4ae9-114">下图显示了代码示例的输出。</span><span class="sxs-lookup"><span data-stu-id="b4ae9-114">The following graphic shows the output of the code sample.</span></span>  
  
 <span data-ttu-id="b4ae9-115">![网格示例](./media/glob-grid.png "glob_grid")</span><span class="sxs-lookup"><span data-stu-id="b4ae9-115">![Grid example](./media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="b4ae9-116">网格</span><span class="sxs-lookup"><span data-stu-id="b4ae9-116">Grid</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4ae9-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4ae9-117">See also</span></span>

- [<span data-ttu-id="b4ae9-118">使用自动布局概述</span><span class="sxs-lookup"><span data-stu-id="b4ae9-118">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
- [<span data-ttu-id="b4ae9-119">使用自动布局创建按钮</span><span class="sxs-lookup"><span data-stu-id="b4ae9-119">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
