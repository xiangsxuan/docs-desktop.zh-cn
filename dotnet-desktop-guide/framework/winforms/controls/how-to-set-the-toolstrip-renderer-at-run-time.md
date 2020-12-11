---
title: 如何：在运行时设置 ToolStrip 呈现器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripManager class [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 525e2347-0804-49aa-b9a3-9b2cabbf1c35
ms.openlocfilehash: 90a80ba421698a108cd7a358f89b64810b06efc9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972559"
---
# <a name="how-to-set-the-toolstrip-renderer-at-run-time"></a><span data-ttu-id="9bef5-102">如何：在运行时设置 ToolStrip 呈现器</span><span class="sxs-lookup"><span data-stu-id="9bef5-102">How to: Set the ToolStrip Renderer at Run Time</span></span>
<span data-ttu-id="9bef5-103">你可以通过创建一个自定义 `ProfessionalColorTable` 类来自定义 <xref:System.Windows.Forms.ToolStrip> 控件的外观。</span><span class="sxs-lookup"><span data-stu-id="9bef5-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> control by creating a custom `ProfessionalColorTable` class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bef5-104">示例</span><span class="sxs-lookup"><span data-stu-id="9bef5-104">Example</span></span>  
 <span data-ttu-id="9bef5-105">下列代码示例演示了如何创建自定义 `ProfessionalColorTable` 类。</span><span class="sxs-lookup"><span data-stu-id="9bef5-105">The following code example demonstrates how to create a custom `ProfessionalColorTable` class.</span></span> <span data-ttu-id="9bef5-106">此类定义了 <xref:System.Windows.Forms.MenuStrip> 和 <xref:System.Windows.Forms.ToolStrip> 控件的渐变。</span><span class="sxs-lookup"><span data-stu-id="9bef5-106">This class defines gradients for a <xref:System.Windows.Forms.MenuStrip> and a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
 <span data-ttu-id="9bef5-107">若要使用此代码示例，则编译并运行应用程序，然后单击“更改颜色”以应用在自定义 `ProfessionalColorTable` 类中定义的渐变。</span><span class="sxs-lookup"><span data-stu-id="9bef5-107">To use this code example, compile and run the application, and then click **Change Colors** to apply the gradients defined in the custom `ProfessionalColorTable` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="defining-a-custom-professionalcolortable-class"></a><span data-ttu-id="9bef5-108">定义自定义 ProfessionalColorTable 类</span><span class="sxs-lookup"><span data-stu-id="9bef5-108">Defining a Custom ProfessionalColorTable class</span></span>  
 <span data-ttu-id="9bef5-109">在 `CustomProfessionalColors` 类中定义自定义渐变。</span><span class="sxs-lookup"><span data-stu-id="9bef5-109">The custom gradients are defined in the `CustomProfessionalColors` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#30)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#30)]  
  
## <a name="assigning-a-custom-renderer"></a><span data-ttu-id="9bef5-110">分配自定义呈现器</span><span class="sxs-lookup"><span data-stu-id="9bef5-110">Assigning a Custom Renderer</span></span>  
 <span data-ttu-id="9bef5-111">使用 `CustomProfessionalColors` 类创建一个新 `ToolStripProfessionalRenderer`，并将其分配给 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="9bef5-111">Create a new `ToolStripProfessionalRenderer` with a `CustomProfessionalColors` class, and assign it to the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#22)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9bef5-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="9bef5-112">Compiling the Code</span></span>  
 <span data-ttu-id="9bef5-113">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="9bef5-113">This example requires:</span></span>  
  
- <span data-ttu-id="9bef5-114">对 System.Design、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="9bef5-114">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bef5-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9bef5-115">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- [<span data-ttu-id="9bef5-116">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="9bef5-116">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
