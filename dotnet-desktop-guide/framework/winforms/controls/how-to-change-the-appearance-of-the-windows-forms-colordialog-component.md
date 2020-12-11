---
title: 更改 ColorDialog 组件的外观
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
ms.openlocfilehash: 0402d7f3c03a0771512a03ac54e1b093c9fe6e9b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971889"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a><span data-ttu-id="d67f2-102">如何：更改 Windows 窗体 ColorDialog 组件的外观</span><span class="sxs-lookup"><span data-stu-id="d67f2-102">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>
<span data-ttu-id="d67f2-103">可以 <xref:System.Windows.Forms.ColorDialog> 使用多个属性的属性来配置 Windows 窗体组件的外观。</span><span class="sxs-lookup"><span data-stu-id="d67f2-103">You can configure the appearance of the Windows Forms <xref:System.Windows.Forms.ColorDialog> component with a number of its properties.</span></span> <span data-ttu-id="d67f2-104">此对话框包含两个部分：一个显示基本颜色，另一个允许用户定义自定义颜色。</span><span class="sxs-lookup"><span data-stu-id="d67f2-104">The dialog box has two sections — one that shows basic colors and one that allows the user to define custom colors.</span></span>  
  
 <span data-ttu-id="d67f2-105">大多数属性限制用户可从对话框中选择的颜色。</span><span class="sxs-lookup"><span data-stu-id="d67f2-105">Most of the properties restrict what colors the user can select from the dialog box.</span></span> <span data-ttu-id="d67f2-106">如果将 <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> 属性设置为 `true` ，则允许用户定义自定义颜色。</span><span class="sxs-lookup"><span data-stu-id="d67f2-106">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `true`, the user is allowed to define custom colors.</span></span> <span data-ttu-id="d67f2-107"><xref:System.Windows.Forms.ColorDialog.FullOpen%2A> `true` 如果展开对话框以定义自定义颜色，则属性为; 否则用户必须单击 "定义自定义颜色" 按钮。</span><span class="sxs-lookup"><span data-stu-id="d67f2-107">The <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> property is `true` if the dialog box is expanded to define custom colors; otherwise the user must click a "Define Custom Colors" button.</span></span> <span data-ttu-id="d67f2-108">当 <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> 属性设置为时 `true` ，该对话框将显示基本颜色集中的所有可用颜色。</span><span class="sxs-lookup"><span data-stu-id="d67f2-108">When the <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> property is set to `true`, the dialog box displays all available colors in the set of basic colors.</span></span> <span data-ttu-id="d67f2-109">如果将 <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> 属性设置为 `true` ，则用户无法选择抖动颜色; 只有纯色可供选择。</span><span class="sxs-lookup"><span data-stu-id="d67f2-109">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors; only solid colors are available to select.</span></span>  
  
 <span data-ttu-id="d67f2-110">如果将 <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> 属性设置为 `true` ，则会在对话框中显示 "帮助" 按钮。</span><span class="sxs-lookup"><span data-stu-id="d67f2-110">If the <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> property is set to `true`, a Help button appears on the dialog box.</span></span> <span data-ttu-id="d67f2-111">当用户单击 "帮助" 按钮时，将 <xref:System.Windows.Forms.ColorDialog> 引发组件的 <xref:System.Windows.Forms.CommonDialog.HelpRequest> 事件。</span><span class="sxs-lookup"><span data-stu-id="d67f2-111">When the user clicks the Help button, the <xref:System.Windows.Forms.ColorDialog> component's <xref:System.Windows.Forms.CommonDialog.HelpRequest> event is raised.</span></span>  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a><span data-ttu-id="d67f2-112">配置 "颜色" 对话框的外观</span><span class="sxs-lookup"><span data-stu-id="d67f2-112">To configure the appearance of the color dialog box</span></span>  
  
1. <span data-ttu-id="d67f2-113">将 <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> 、 <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> 、 <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> 和属性设置 <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> 为所需的值。</span><span class="sxs-lookup"><span data-stu-id="d67f2-113">Set the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, and <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> properties to the desired values.</span></span>  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d67f2-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d67f2-114">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="d67f2-115">ColorDialog 组件</span><span class="sxs-lookup"><span data-stu-id="d67f2-115">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
- [<span data-ttu-id="d67f2-116">ColorDialog 组件概述</span><span class="sxs-lookup"><span data-stu-id="d67f2-116">ColorDialog Component Overview</span></span>](colordialog-component-overview-windows-forms.md)
