---
title: 如何：将控件添加到选项卡页
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
ms.openlocfilehash: 9806583fda60f1cb8a5ef2d97f42eba158593f61
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971287"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a><span data-ttu-id="882c7-102">如何：将控件添加到选项卡页</span><span class="sxs-lookup"><span data-stu-id="882c7-102">How to: Add a Control to a Tab Page</span></span>
<span data-ttu-id="882c7-103">您可以使用 Windows 窗体 <xref:System.Windows.Forms.TabControl> 以有序的方式显示其他控件。</span><span class="sxs-lookup"><span data-stu-id="882c7-103">You can use the Windows Forms <xref:System.Windows.Forms.TabControl> to display other controls in an organized fashion.</span></span> <span data-ttu-id="882c7-104">下面的过程演示如何将按钮添加到第一个选项卡。有关向选项卡页的标签部分添加图标的信息，请参阅 [如何：更改 Windows 窗体 TabControl 的外观](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)。</span><span class="sxs-lookup"><span data-stu-id="882c7-104">The following procedure shows how to add a button to the first tab. For information about adding an icon to the label part of a tab page, see [How to: Change the Appearance of the Windows Forms TabControl](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span></span>  
  
### <a name="to-add-a-control-programmatically"></a><span data-ttu-id="882c7-105">以编程方式添加控件</span><span class="sxs-lookup"><span data-stu-id="882c7-105">To add a control programmatically</span></span>  
  
1. <span data-ttu-id="882c7-106">使用的 <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> 属性返回的集合的方法 <xref:System.Windows.Forms.Control.Controls%2A> <xref:System.Windows.Forms.TabPage> ：</span><span class="sxs-lookup"><span data-stu-id="882c7-106">Use the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.Control.Controls%2A> property of <xref:System.Windows.Forms.TabPage>:</span></span>  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="882c7-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="882c7-107">See also</span></span>

- [<span data-ttu-id="882c7-108">TabControl 控件</span><span class="sxs-lookup"><span data-stu-id="882c7-108">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="882c7-109">TabControl 控件概述</span><span class="sxs-lookup"><span data-stu-id="882c7-109">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="882c7-110">如何：更改 Windows 窗体 TabControl 的外观</span><span class="sxs-lookup"><span data-stu-id="882c7-110">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="882c7-111">如何：禁用选项卡页</span><span class="sxs-lookup"><span data-stu-id="882c7-111">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="882c7-112">如何：使用 Windows 窗体 TabControl 添加和移除选项卡</span><span class="sxs-lookup"><span data-stu-id="882c7-112">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
