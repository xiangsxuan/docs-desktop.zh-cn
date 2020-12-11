---
title: 如何：使控件在运行时不可见
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
ms.openlocfilehash: e9af529541a40a951d6defea180dbbef04c8f3be
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970563"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="b78b7-102">如何：使控件在运行时不可见</span><span class="sxs-lookup"><span data-stu-id="b78b7-102">How to: Make Your Control Invisible at Run Time</span></span>
<span data-ttu-id="b78b7-103">有时，可能需要创建一个在运行时不可见的用户控件。</span><span class="sxs-lookup"><span data-stu-id="b78b7-103">There are times when you might want to create a user control that is invisible at run time.</span></span> <span data-ttu-id="b78b7-104">例如，警报时钟的控件可能不可见，除非警报发出警报。</span><span class="sxs-lookup"><span data-stu-id="b78b7-104">For example, a control that is an alarm clock might be invisible except when the alarm was sounding.</span></span> <span data-ttu-id="b78b7-105">这可以通过设置属性轻松完成 <xref:System.Windows.Forms.Control.Visible%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b78b7-105">This is easily accomplished by setting the <xref:System.Windows.Forms.Control.Visible%2A> property.</span></span> <span data-ttu-id="b78b7-106">如果 <xref:System.Windows.Forms.Control.Visible%2A> 属性为 `true` ，则控件将显示为 "正常"。</span><span class="sxs-lookup"><span data-stu-id="b78b7-106">If the <xref:System.Windows.Forms.Control.Visible%2A> property is `true`, your control will appear as normal.</span></span> <span data-ttu-id="b78b7-107">如果 `false` 为，则控件将隐藏。</span><span class="sxs-lookup"><span data-stu-id="b78b7-107">If `false`, your control will be hidden.</span></span> <span data-ttu-id="b78b7-108">尽管控件中的代码在不可见时仍可能运行，但你将无法通过用户界面与控件进行交互。</span><span class="sxs-lookup"><span data-stu-id="b78b7-108">Although code in your control may still run while invisible, you will not be able to interact with the control through the user interface.</span></span> <span data-ttu-id="b78b7-109">若要创建仍响应用户输入的不可见控件 (例如，鼠标单击) ，应创建透明控件。</span><span class="sxs-lookup"><span data-stu-id="b78b7-109">If you want to create an invisible control that still responds to user input (for example, mouse clicks), you should create a transparent control.</span></span> <span data-ttu-id="b78b7-110">有关详细信息，请参阅为 [控件提供透明背景](how-to-give-your-control-a-transparent-background.md)。</span><span class="sxs-lookup"><span data-stu-id="b78b7-110">For more information, see [Giving Your Control a Transparent Background](how-to-give-your-control-a-transparent-background.md).</span></span>  
  
### <a name="to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="b78b7-111">使控件在运行时不可见</span><span class="sxs-lookup"><span data-stu-id="b78b7-111">To make your control invisible at run time</span></span>  
  
1. <span data-ttu-id="b78b7-112">将 <xref:System.Windows.Forms.Control.Visible%2A> 属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="b78b7-112">Set the <xref:System.Windows.Forms.Control.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b78b7-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b78b7-113">See also</span></span>

- <xref:System.Windows.Forms.Control.Visible%2A>
- [<span data-ttu-id="b78b7-114">使用 .NET Framework 开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="b78b7-114">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="b78b7-115">如何：使控件拥有透明背景</span><span class="sxs-lookup"><span data-stu-id="b78b7-115">How to: Give Your Control a Transparent Background</span></span>](how-to-give-your-control-a-transparent-background.md)
