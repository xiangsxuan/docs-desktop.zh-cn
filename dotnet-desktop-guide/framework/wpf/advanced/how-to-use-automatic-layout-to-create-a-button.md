---
title: 如何：使用自动布局创建按钮
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 05b874f9894841d3c318ee131d15165111fd596a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971807"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a><span data-ttu-id="81df7-102">如何：使用自动布局创建按钮</span><span class="sxs-lookup"><span data-stu-id="81df7-102">How to: Use Automatic Layout to Create a Button</span></span>
<span data-ttu-id="81df7-103">本示例介绍如何使用自动布局方法在可本地化的应用程序中创建按钮。</span><span class="sxs-lookup"><span data-stu-id="81df7-103">This example describes how to use the automatic layout approach to create a button in a localizable application.</span></span>  
  
 <span data-ttu-id="81df7-104">的本地化 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 可能是一个耗时的过程。</span><span class="sxs-lookup"><span data-stu-id="81df7-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="81df7-105">通常，本地化人员除翻译文本外，还需要重新调整元素大小并重新定位元素。</span><span class="sxs-lookup"><span data-stu-id="81df7-105">Often localizers need to resize and reposition elements in addition to translating text.</span></span> <span data-ttu-id="81df7-106">过去，每种语言都是 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 针对所需调整进行修改的。</span><span class="sxs-lookup"><span data-stu-id="81df7-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="81df7-107">现在， [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 您可以设计可减少调整需求的元素。</span><span class="sxs-lookup"><span data-stu-id="81df7-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="81df7-108">编写可以更方便地调整大小和重新定位的应用程序的方法称为 `automatic layout` 。</span><span class="sxs-lookup"><span data-stu-id="81df7-108">The approach to writing applications that can be more easily resized and repositioned is called `automatic layout`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81df7-109">示例</span><span class="sxs-lookup"><span data-stu-id="81df7-109">Example</span></span>  

<span data-ttu-id="81df7-110">下面两个 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 示例创建实例化按钮的应用程序; 一个使用英语文本，另一个使用西班牙语文本。</span><span class="sxs-lookup"><span data-stu-id="81df7-110">The following two [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] examples create applications that instantiate a button; one with English text and one with Spanish text.</span></span> <span data-ttu-id="81df7-111">请注意，除文本之外，代码都一样；按钮会配合文字进行调整。</span><span class="sxs-lookup"><span data-stu-id="81df7-111">Notice that the code is the same except for the text; the button adjusts to fit the text.</span></span>

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="81df7-112">下图显示了带有自动调整大小的按钮的代码示例的输出：</span><span class="sxs-lookup"><span data-stu-id="81df7-112">The following graphic shows the output of the code samples with auto-resizable buttons:</span></span>
  
 ![具有不同语言的文本的同一按钮](./media/use-automatic-layout-overview/auto-resizable-button.png)  
  
## <a name="see-also"></a><span data-ttu-id="81df7-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81df7-114">See also</span></span>

- [<span data-ttu-id="81df7-115">使用自动布局概述</span><span class="sxs-lookup"><span data-stu-id="81df7-115">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
- [<span data-ttu-id="81df7-116">使用网格进行自动布局</span><span class="sxs-lookup"><span data-stu-id="81df7-116">Use a Grid for Automatic Layout</span></span>](how-to-use-a-grid-for-automatic-layout.md)
