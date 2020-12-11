---
title: 如何：设置应用程序的 ToolStrip 呈现器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Renderer property [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], customizing
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
ms.openlocfilehash: c9250b723e68ac97d1486a896392bf64c66cdfbc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972662"
---
# <a name="how-to-set-the-toolstrip-renderer-for-an-application"></a><span data-ttu-id="598d6-102">如何：设置应用程序的 ToolStrip 呈现器</span><span class="sxs-lookup"><span data-stu-id="598d6-102">How to: Set the ToolStrip Renderer for an Application</span></span>
<span data-ttu-id="598d6-103">可以单独自定义 <xref:System.Windows.Forms.ToolStrip> 控件的外观，或应用程序中所有 <xref:System.Windows.Forms.ToolStrip> 控件的外观。</span><span class="sxs-lookup"><span data-stu-id="598d6-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> controls individually or for all the <xref:System.Windows.Forms.ToolStrip> controls in your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="598d6-104">示例</span><span class="sxs-lookup"><span data-stu-id="598d6-104">Example</span></span>  
 <span data-ttu-id="598d6-105">下面的代码示例演示如何有选择地应用自定义呈现器到 <xref:System.Windows.Forms.ToolStrip> 控件和 <xref:System.Windows.Forms.MenuStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="598d6-105">The following code example demonstrates how to selectively apply a custom renderer to a <xref:System.Windows.Forms.ToolStrip> control and a <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="598d6-106">若要使用此代码示例，请编译并运行该应用程序，然后从 <xref:System.Windows.Forms.ComboBox> 控件中选择自定义呈现的作用域。</span><span class="sxs-lookup"><span data-stu-id="598d6-106">To use this code example, compile and run the application, and then select the scope of the custom rending from the <xref:System.Windows.Forms.ComboBox> control.</span></span> <span data-ttu-id="598d6-107">单击“应用”设置呈现器。</span><span class="sxs-lookup"><span data-stu-id="598d6-107">Click **Apply** to set the renderer.</span></span>  
  
 <span data-ttu-id="598d6-108">若要查看自定义菜单项呈现，请从控件中选择该 <xref:System.Windows.Forms.MenuStrip> 选项 <xref:System.Windows.Forms.ComboBox> ，单击 " **应用**"，然后打开 " **文件** " 菜单项。</span><span class="sxs-lookup"><span data-stu-id="598d6-108">To see custom menu item rendering, select the <xref:System.Windows.Forms.MenuStrip> option from the <xref:System.Windows.Forms.ComboBox> control, click **Apply**, and then open the **File** menu item.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 <span data-ttu-id="598d6-109">设置 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 属性，将自定义呈现器应用到你的应用程序中所有的 <xref:System.Windows.Forms.ToolStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="598d6-109">Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to apply a custom renderer to all the <xref:System.Windows.Forms.ToolStrip> controls in your application.</span></span>  
  
 <span data-ttu-id="598d6-110">设置 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 属性，将自定义呈现器应用到单个 <xref:System.Windows.Forms.ToolStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="598d6-110">Set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to apply a custom renderer to an individual <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="598d6-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="598d6-111">Compiling the Code</span></span>  
 <span data-ttu-id="598d6-112">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="598d6-112">This example requires:</span></span>  
  
- <span data-ttu-id="598d6-113">对 System.Design、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="598d6-113">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="598d6-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="598d6-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- [<span data-ttu-id="598d6-115">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="598d6-115">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
