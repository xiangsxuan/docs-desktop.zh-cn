---
title: 如何：向窗体提供标准菜单项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- menu items [Windows Forms], standard
- ToolStrip control [Windows Forms]
ms.assetid: 75db9126-e70c-4e81-921d-b83c0a4a9f50
ms.openlocfilehash: a95476ff3d182bf2a56e6527c9ee83c8c56af246
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971144"
---
# <a name="how-to-provide-standard-menu-items-to-a-form"></a><span data-ttu-id="e7381-102">如何：向窗体提供标准菜单项</span><span class="sxs-lookup"><span data-stu-id="e7381-102">How to: Provide Standard Menu Items to a Form</span></span>
<span data-ttu-id="e7381-103">可使用 <xref:System.Windows.Forms.MenuStrip> 控件向窗体提供标准菜单。</span><span class="sxs-lookup"><span data-stu-id="e7381-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="e7381-104">Visual Studio 中提供了此功能的广泛支持。</span><span class="sxs-lookup"><span data-stu-id="e7381-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="e7381-105">另请参阅[演练：向窗体提供标准菜单项](walkthrough-providing-standard-menu-items-to-a-form.md)。</span><span class="sxs-lookup"><span data-stu-id="e7381-105">Also see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7381-106">示例</span><span class="sxs-lookup"><span data-stu-id="e7381-106">Example</span></span>  
 <span data-ttu-id="e7381-107">下面的代码示例演示了如何使用 <xref:System.Windows.Forms.MenuStrip> 控件创建带有标准菜单的窗体。</span><span class="sxs-lookup"><span data-stu-id="e7381-107">The following code example demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a form with a standard menu.</span></span> <span data-ttu-id="e7381-108"><xref:System.Windows.Forms.StatusStrip> 控件中将显示菜单项选择。</span><span class="sxs-lookup"><span data-stu-id="e7381-108">Menu item selections are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e7381-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="e7381-109">Compiling the Code</span></span>  
 <span data-ttu-id="e7381-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="e7381-110">This example requires:</span></span>  
  
- <span data-ttu-id="e7381-111">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="e7381-111">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7381-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7381-112">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="e7381-113">MenuStrip 控件</span><span class="sxs-lookup"><span data-stu-id="e7381-113">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
