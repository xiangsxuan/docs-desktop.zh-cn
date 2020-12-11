---
title: 如何：区分单击和双击
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- mouse [Windows Forms], click
- mouse [Windows Forms], double-click
- mouse clicks [Windows Forms], single versus double
ms.assetid: d836ac8c-85bc-4f3a-a761-8aee03dc682c
ms.openlocfilehash: cff6c283651b5994e869756524a3ee83ecdcfda9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970249"
---
# <a name="how-to-distinguish-between-clicks-and-double-clicks"></a><span data-ttu-id="7e418-102">如何：区分单击和双击</span><span class="sxs-lookup"><span data-stu-id="7e418-102">How to: Distinguish Between Clicks and Double-Clicks</span></span>
<span data-ttu-id="7e418-103">通常情况下，一次 *单击* 会启动一个用户界面 (UI) 操作，而一次 *双击* 则会扩展该操作。</span><span class="sxs-lookup"><span data-stu-id="7e418-103">Typically, a single *click* initiates a user interface (UI) action and a *double-click* extends the action.</span></span> <span data-ttu-id="7e418-104">例如，一次单击通常可选择一个项，而双击则可编辑所选的项。</span><span class="sxs-lookup"><span data-stu-id="7e418-104">For example, one click usually selects an item, and a double-click edits the selected item.</span></span> <span data-ttu-id="7e418-105">但是，Windows 窗体 Click 事件无法轻松应用于单击和双击执行多个不兼容操作的方案，因为绑定到 <xref:System.Windows.Forms.Control.Click> 或 <xref:System.Windows.Forms.Control.MouseClick> 事件的操作会在操作绑定到 <xref:System.Windows.Forms.Control.DoubleClick> 或 <xref:System.Windows.Forms.Control.MouseDoubleClick> 事件之前执行。</span><span class="sxs-lookup"><span data-stu-id="7e418-105">However, the Windows Forms click events do not easily accommodate a scenario where a click and a double-click perform incompatible actions, because an action tied to the <xref:System.Windows.Forms.Control.Click> or <xref:System.Windows.Forms.Control.MouseClick> event is performed before the action tied to the <xref:System.Windows.Forms.Control.DoubleClick> or <xref:System.Windows.Forms.Control.MouseDoubleClick> event.</span></span> <span data-ttu-id="7e418-106">本主题演示此问题的两种解决方案。</span><span class="sxs-lookup"><span data-stu-id="7e418-106">This topic demonstrates two solutions to this problem.</span></span> <span data-ttu-id="7e418-107">一种解决方案是处理双击事件，并回滚单击事件处理过程中的操作。</span><span class="sxs-lookup"><span data-stu-id="7e418-107">One solution is to handle the double-click event and roll back the actions in the handling of the click event.</span></span> <span data-ttu-id="7e418-108">在极少数情况下，可能需要通过处理 <xref:System.Windows.Forms.Control.MouseDown> 事件并使用 <xref:System.Windows.Forms.SystemInformation> 类的 <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> 和 <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> 属性来模拟单击和双击行为。</span><span class="sxs-lookup"><span data-stu-id="7e418-108">In rare situations you may need to simulate click and double-click behavior by handling the <xref:System.Windows.Forms.Control.MouseDown> event and by using the <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> and <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> properties of the <xref:System.Windows.Forms.SystemInformation> class.</span></span> <span data-ttu-id="7e418-109">度量点击之间的时间，如果在达到 <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> 值之前发生第二次单击，并且单击发生在由 <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> 定义的矩形范围内，请执行双击操作；否则，请执行单击操作。</span><span class="sxs-lookup"><span data-stu-id="7e418-109">You measure the time between clicks and if a second click occurs before the value of <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> is reached and the click is within a rectangle defined by <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>, perform the double-click action; otherwise, perform the click action.</span></span>  
  
### <a name="to-roll-back-a-click-action"></a><span data-ttu-id="7e418-110">回滚单击操作</span><span class="sxs-lookup"><span data-stu-id="7e418-110">To roll back a click action</span></span>  
  
- <span data-ttu-id="7e418-111">请确保你正在使用的控件具有标准双击行为。</span><span class="sxs-lookup"><span data-stu-id="7e418-111">Ensure that the control you are working with has standard double-click behavior.</span></span> <span data-ttu-id="7e418-112">如果不具有标准双击行为，请启用具有 <xref:System.Windows.Forms.Control.SetStyle%2A> 方法的控件。</span><span class="sxs-lookup"><span data-stu-id="7e418-112">If not, enable the control with the <xref:System.Windows.Forms.Control.SetStyle%2A> method.</span></span> <span data-ttu-id="7e418-113">处理双击事件，并回滚单击操作以及双击操作。</span><span class="sxs-lookup"><span data-stu-id="7e418-113">Handle the double-click event and roll back the click action as well as the double-click action.</span></span> <span data-ttu-id="7e418-114">下面的代码示例演示了如何在启用了双击的情况下创建自定义按钮，以及如何回滚双击事件处理代码中的单击操作。</span><span class="sxs-lookup"><span data-stu-id="7e418-114">The following code example demonstrates a how to create a custom button with double-click enabled, as well as how to roll back the click action in the double-click event handling code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ButtonDoubleClick#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ButtonDoubleClick#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/VB/Form1.vb#1)]  
  
### <a name="to-distinguish-between-clicks-in-the-mousedown-event"></a><span data-ttu-id="7e418-115">区分 MouseDown 事件中的点击</span><span class="sxs-lookup"><span data-stu-id="7e418-115">To distinguish between clicks in the MouseDown event</span></span>  
  
- <span data-ttu-id="7e418-116">请使用适当的 <xref:System.Windows.Forms.SystemInformation> 属性和 <xref:System.Windows.Forms.Timer> 组件来处理 <xref:System.Windows.Forms.Control.MouseDown> 事件和确定点击之间的位置和时间跨度。</span><span class="sxs-lookup"><span data-stu-id="7e418-116">Handle the <xref:System.Windows.Forms.Control.MouseDown> event and determine the location and time span between clicks using the appropriate <xref:System.Windows.Forms.SystemInformation> properties and a <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="7e418-117">根据是否发生单击或双击执行相应的操作。</span><span class="sxs-lookup"><span data-stu-id="7e418-117">Perform the appropriate action depending on whether a click or double-click takes place.</span></span> <span data-ttu-id="7e418-118">下面的代码示例演示如何实现这一点。</span><span class="sxs-lookup"><span data-stu-id="7e418-118">The following code example demonstrates how this can be done.</span></span>  
  
     [!code-cpp[System.Windows.Forms.SingleVersusDoubleClick#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/cpp/form1.cpp#0)]
     [!code-csharp[System.Windows.Forms.SingleVersusDoubleClick#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/CS/form1.cs#0)]
     [!code-vb[System.Windows.Forms.SingleVersusDoubleClick#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7e418-119">编译代码</span><span class="sxs-lookup"><span data-stu-id="7e418-119">Compiling the Code</span></span>  
 <span data-ttu-id="7e418-120">这些示例需要：</span><span class="sxs-lookup"><span data-stu-id="7e418-120">These examples require:</span></span>  
  
- <span data-ttu-id="7e418-121">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="7e418-121">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e418-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e418-122">See also</span></span>

- [<span data-ttu-id="7e418-123">Windows 窗体应用程序中的鼠标输入</span><span class="sxs-lookup"><span data-stu-id="7e418-123">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
