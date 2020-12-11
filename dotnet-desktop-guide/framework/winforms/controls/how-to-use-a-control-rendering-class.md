---
title: 如何：使用控件呈现类
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
ms.openlocfilehash: a0f450ff5f169026007002a0d2907ee35e79b29d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972541"
---
# <a name="how-to-use-a-control-rendering-class"></a><span data-ttu-id="38aca-102">如何：使用控件呈现类</span><span class="sxs-lookup"><span data-stu-id="38aca-102">How to: Use a Control Rendering Class</span></span>
<span data-ttu-id="38aca-103">此示例演示如何使用 <xref:System.Windows.Forms.ComboBoxRenderer> 类呈现组合框控件的下拉箭头。</span><span class="sxs-lookup"><span data-stu-id="38aca-103">This example demonstrates how to use the <xref:System.Windows.Forms.ComboBoxRenderer> class to render the drop-down arrow of a combo box control.</span></span> <span data-ttu-id="38aca-104">该示例包含 <xref:System.Windows.Forms.Control.OnPaint%2A> 一个简单的自定义控件的方法。</span><span class="sxs-lookup"><span data-stu-id="38aca-104">The example consists of the <xref:System.Windows.Forms.Control.OnPaint%2A> method of a simple custom control.</span></span> <span data-ttu-id="38aca-105"><xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType>属性用于确定是否在应用程序窗口的工作区中启用视觉样式。</span><span class="sxs-lookup"><span data-stu-id="38aca-105">The <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> property is used to determine whether visual styles are enabled in the client area of application windows.</span></span> <span data-ttu-id="38aca-106">如果视觉样式处于活动状态，则该 <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> 方法将呈现具有视觉样式的下拉箭头; 否则，该 <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> 方法将呈现经典 Windows 样式中的下拉箭头。</span><span class="sxs-lookup"><span data-stu-id="38aca-106">If visual styles are active, then the <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> method will render the drop-down arrow with visual styles; otherwise, the <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> method will render the drop-down arrow in the classic Windows style.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38aca-107">示例</span><span class="sxs-lookup"><span data-stu-id="38aca-107">Example</span></span>  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="38aca-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="38aca-108">Compiling the Code</span></span>  
 <span data-ttu-id="38aca-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="38aca-109">This example requires:</span></span>  
  
- <span data-ttu-id="38aca-110">派生自类的自定义控件 <xref:System.Windows.Forms.Control> 。</span><span class="sxs-lookup"><span data-stu-id="38aca-110">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
- <span data-ttu-id="38aca-111"><xref:System.Windows.Forms.Form>承载自定义控件的。</span><span class="sxs-lookup"><span data-stu-id="38aca-111">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
- <span data-ttu-id="38aca-112">对 <xref:System?displayProperty=nameWithType> 、 <xref:System.Drawing?displayProperty=nameWithType> 、 <xref:System.Windows.Forms?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="38aca-112">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38aca-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38aca-113">See also</span></span>

- [<span data-ttu-id="38aca-114">使用视觉样式呈现控件</span><span class="sxs-lookup"><span data-stu-id="38aca-114">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)
