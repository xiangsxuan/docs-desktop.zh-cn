---
title: 如何：拉伸 ToolStripTextBox 以填充 ToolStrip 的剩余宽度
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: c60cc2a377f08a73159f25b2ab5f2812d41f0c10
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971991"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a><span data-ttu-id="34480-102">如何：拉伸 ToolStripTextBox 以填充 ToolStrip 的其余宽度（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="34480-102">How to: Stretch a ToolStripTextBox to Fill the Remaining Width of a ToolStrip (Windows Forms)</span></span>
<span data-ttu-id="34480-103">当您将 <xref:System.Windows.Forms.ToolStrip.Stretch%2A> 控件的属性设置 <xref:System.Windows.Forms.ToolStrip> 为时 `true` ，控件将从端到端填充其容器，并在其容器调整大小时调整其大小。</span><span class="sxs-lookup"><span data-stu-id="34480-103">When you set the <xref:System.Windows.Forms.ToolStrip.Stretch%2A> property of a <xref:System.Windows.Forms.ToolStrip> control to `true`, the control fills its container from end to end, and resizes when its container resizes.</span></span> <span data-ttu-id="34480-104">在此配置中，你可能会发现在控件中拉伸项（如 <xref:System.Windows.Forms.ToolStripTextBox> ）以填充可用空间并在控件调整大小时调整大小很有用。</span><span class="sxs-lookup"><span data-stu-id="34480-104">In this configuration, you may find it useful to stretch an item in the control, such as a <xref:System.Windows.Forms.ToolStripTextBox>, to fill the available space and to resize when the control resizes.</span></span> <span data-ttu-id="34480-105">例如，如果想要获得与 Microsoft® Internet Explorer 中的地址栏类似的外观和行为，此拉伸很有用。</span><span class="sxs-lookup"><span data-stu-id="34480-105">This stretching is useful, for example, if you want to achieve appearance and behavior similar to the address bar in Microsoft® Internet Explorer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34480-106">示例</span><span class="sxs-lookup"><span data-stu-id="34480-106">Example</span></span>  
 <span data-ttu-id="34480-107">下面的代码示例提供了一个派生自的类 <xref:System.Windows.Forms.ToolStripTextBox> `ToolStripSpringTextBox` 。</span><span class="sxs-lookup"><span data-stu-id="34480-107">The following code example provides a class derived from <xref:System.Windows.Forms.ToolStripTextBox> called `ToolStripSpringTextBox`.</span></span> <span data-ttu-id="34480-108">此类重写 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> 方法，以便 <xref:System.Windows.Forms.ToolStrip> 在减去所有其他项的组合宽度之后计算父控件的可用宽度。</span><span class="sxs-lookup"><span data-stu-id="34480-108">This class overrides the <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> method to calculate the available width of the parent <xref:System.Windows.Forms.ToolStrip> control after the combined width of all other items has been subtracted.</span></span> <span data-ttu-id="34480-109">此代码示例还提供了一个 <xref:System.Windows.Forms.Form> 类和一个 `Program` 类，用于演示新的行为。</span><span class="sxs-lookup"><span data-stu-id="34480-109">This code example also provides a <xref:System.Windows.Forms.Form> class and a `Program` class to demonstrate the new behavior.</span></span>  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="34480-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="34480-110">Compiling the Code</span></span>  
 <span data-ttu-id="34480-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="34480-111">This example requires:</span></span>  
  
- <span data-ttu-id="34480-112">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="34480-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34480-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34480-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [<span data-ttu-id="34480-114">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="34480-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="34480-115">如何：在 StatusStrip 中以交互方式使用 Spring 属性</span><span class="sxs-lookup"><span data-stu-id="34480-115">How to: Use the Spring Property Interactively in a StatusStrip</span></span>](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
