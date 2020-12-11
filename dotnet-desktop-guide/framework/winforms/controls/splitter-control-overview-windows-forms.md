---
title: Splitter 控件概述
ms.date: 03/30/2017
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
ms.openlocfilehash: 3d6da8daf9bb0e8df4f69554a87725a7ddb65acb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970902"
---
# <a name="splitter-control-overview-windows-forms"></a><span data-ttu-id="5b206-102">Splitter 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="5b206-102">Splitter Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="5b206-103">尽管 <xref:System.Windows.Forms.SplitContainer> 替换了早期版本的 <xref:System.Windows.Forms.Splitter> 控件并添加了功能；但是也可选择保留 <xref:System.Windows.Forms.Splitter> 以备向后兼容和将来使用。</span><span class="sxs-lookup"><span data-stu-id="5b206-103">Although <xref:System.Windows.Forms.SplitContainer> replaces and adds functionality to the <xref:System.Windows.Forms.Splitter> control of previous versions, <xref:System.Windows.Forms.Splitter> is retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="5b206-104">Windows 窗体 <xref:System.Windows.Forms.Splitter> 控件用于在运行时调整停靠控件的大小。</span><span class="sxs-lookup"><span data-stu-id="5b206-104">Windows Forms <xref:System.Windows.Forms.Splitter> controls are used to resize docked controls at run time.</span></span> <span data-ttu-id="5b206-105"><xref:System.Windows.Forms.Splitter>控件通常用在具有不同的数据长度（如 Windows 资源管理器）的窗体上，其数据窗格包含不同时间的不同宽度的信息。</span><span class="sxs-lookup"><span data-stu-id="5b206-105">The <xref:System.Windows.Forms.Splitter> control is often used on forms with controls that have varying lengths of data to present, like Windows Explorer, whose data panes contain information of varying widths at different times.</span></span>  
  
## <a name="working-with-the-splitter-control"></a><span data-ttu-id="5b206-106">使用拆分器控件</span><span class="sxs-lookup"><span data-stu-id="5b206-106">Working with the Splitter Control</span></span>  
 <span data-ttu-id="5b206-107">当用户将鼠标指针指向可通过拆分器控件调整大小的控件的未停靠边缘时，指针将更改其外观，以指示可调整控件的大小。</span><span class="sxs-lookup"><span data-stu-id="5b206-107">When the user points the mouse pointer at the undocked edge of a control that can be resized by a splitter control, the pointer changes its appearance to indicate that the control can be resized.</span></span> <span data-ttu-id="5b206-108">利用拆分器控件，用户可以重设紧靠其后的停靠控件的大小。</span><span class="sxs-lookup"><span data-stu-id="5b206-108">With the splitter control, the user can resize the docked control that is immediately before it.</span></span> <span data-ttu-id="5b206-109">因此，若要使用户能够在运行时调整停靠控件的大小，请将调整大小的控件停靠到容器的边缘，然后将拆分器控件停靠到该容器的同一侧。</span><span class="sxs-lookup"><span data-stu-id="5b206-109">Therefore, to enable the user to resize a docked control at run time, dock the control to be resized to an edge of a container, and then dock a splitter control to the same side of that container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b206-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b206-110">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="5b206-111">如何：在 Windows 窗体上停靠控件</span><span class="sxs-lookup"><span data-stu-id="5b206-111">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="5b206-112">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="5b206-112">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
