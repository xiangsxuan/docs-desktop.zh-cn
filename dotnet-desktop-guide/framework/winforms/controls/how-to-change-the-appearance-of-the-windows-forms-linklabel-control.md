---
title: 更改 LinkLabel 控件的外观
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
ms.openlocfilehash: df66991289373a05fc7c27b7768a96643e3bbae0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971238"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a><span data-ttu-id="0496a-102">如何：更改 Windows 窗体 LinkLabel 控件的外观</span><span class="sxs-lookup"><span data-stu-id="0496a-102">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="0496a-103">您可以更改控件所显示的文本 <xref:System.Windows.Forms.LinkLabel> ，以适应各种目的。</span><span class="sxs-lookup"><span data-stu-id="0496a-103">You can change the text displayed by the <xref:System.Windows.Forms.LinkLabel> control to suit a variety of purposes.</span></span> <span data-ttu-id="0496a-104">例如，通常情况下，通过将文本设置为以带有下划线的特定颜色显示来向用户指示文本可以单击。</span><span class="sxs-lookup"><span data-stu-id="0496a-104">For example, it is common practice to indicate to the user that text can be clicked by setting the text to appear in a specific color with an underline.</span></span> <span data-ttu-id="0496a-105">用户单击文本后，颜色将变为不同的颜色。</span><span class="sxs-lookup"><span data-stu-id="0496a-105">After the user clicks the text, the color changes to a different color.</span></span> <span data-ttu-id="0496a-106">若要控制此行为，可以设置五个不同的属性： <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> 、 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 、 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> 、 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 和 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="0496a-106">To control this behavior, you can set five different properties: the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> properties.</span></span>  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a><span data-ttu-id="0496a-107">更改 LinkLabel 控件的外观</span><span class="sxs-lookup"><span data-stu-id="0496a-107">To change the appearance of a LinkLabel control</span></span>  
  
1. <span data-ttu-id="0496a-108">将 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> 和 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 属性设置为所需的颜色。</span><span class="sxs-lookup"><span data-stu-id="0496a-108">Set the <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> and <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> properties to the colors you want.</span></span>  
  
     <span data-ttu-id="0496a-109">可以通过编程方式或在设计时在 " **属性** " 窗口中完成此操作。</span><span class="sxs-lookup"><span data-stu-id="0496a-109">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    ' You can set the color using decimal values for red, green, and blue  
    LinkLabel1.LinkColor = Color.FromArgb(0, 0, 255)  
    ' Or you can set the color using defined constants  
    LinkLabel1.VisitedLinkColor = Color.Purple  
    ```  
  
    ```csharp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1.LinkColor = Color.FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1.VisitedLinkColor = Color.Purple;  
    ```  
  
    ```cpp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1->LinkColor = Color::FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1->VisitedLinkColor = Color::Purple;  
    ```  
  
2. <span data-ttu-id="0496a-110">将 <xref:System.Windows.Forms.LinkLabel.Text%2A> 属性设置为相应的标题。</span><span class="sxs-lookup"><span data-stu-id="0496a-110">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
     <span data-ttu-id="0496a-111">可以通过编程方式或在设计时在 " **属性** " 窗口中完成此操作。</span><span class="sxs-lookup"><span data-stu-id="0496a-111">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. <span data-ttu-id="0496a-112">设置 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 属性以确定显示为链接的标题部分。</span><span class="sxs-lookup"><span data-stu-id="0496a-112">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
     <span data-ttu-id="0496a-113"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A>值用一个 <xref:System.Windows.Forms.LinkArea> 包含两个数字、起始字符位置和字符数来表示。</span><span class="sxs-lookup"><span data-stu-id="0496a-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented with a <xref:System.Windows.Forms.LinkArea> containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="0496a-114">可以通过编程方式或在设计时在 " **属性** " 窗口中完成此操作。</span><span class="sxs-lookup"><span data-stu-id="0496a-114">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. <span data-ttu-id="0496a-115">将 <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> 属性设置为 <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline> 、 <xref:System.Windows.Forms.LinkBehavior.HoverUnderline> 或 <xref:System.Windows.Forms.LinkBehavior.NeverUnderline> 。</span><span class="sxs-lookup"><span data-stu-id="0496a-115">Set the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> property to <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, or <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span></span>  
  
     <span data-ttu-id="0496a-116">如果将其设置为 <xref:System.Windows.Forms.LinkBehavior.HoverUnderline> ，则在 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 指针停留在其上时，所确定的标题部分将仅带有下划线。</span><span class="sxs-lookup"><span data-stu-id="0496a-116">If it is set to <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, the part of the caption determined by <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> will only be underlined when the pointer rests on it.</span></span>  
  
5. <span data-ttu-id="0496a-117">在 <xref:System.Windows.Forms.LinkLabel.LinkClicked> 事件处理程序中，将 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="0496a-117">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="0496a-118">访问某个链接后，常见的做法是以某种方式（通常使用颜色）更改其外观。</span><span class="sxs-lookup"><span data-stu-id="0496a-118">When a link has been visited, it is common practice to change its appearance in some way, usually by color.</span></span> <span data-ttu-id="0496a-119">文本将更改为属性指定的颜色 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 。</span><span class="sxs-lookup"><span data-stu-id="0496a-119">The text will change to the color specified by the <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> property.</span></span>  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked (ByVal sender As Object, _  
       ByVal e As EventArgs) Handles LinkLabel1.LinkClicked  
       ' Change the color of the link text  
       ' by setting LinkVisited to True.  
       LinkLabel1.LinkVisited = True  
       ' Then do whatever other action is appropriate  
    End Sub  
    ```  
  
    ```csharp  
    protected void LinkLabel1_LinkClicked(object sender, System.EventArgs e)  
    {  
       // Change the color of the link text by setting LinkVisited
       // to True.  
       linkLabel1.LinkVisited = true;  
       // Then do whatever other action is appropriate  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Change the color of the link text by setting LinkVisited
          // to True.  
          linkLabel1->LinkVisited = true;  
          // Then do whatever other action is appropriate  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0496a-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0496a-120">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [<span data-ttu-id="0496a-121">LinkLabel 控件概述</span><span class="sxs-lookup"><span data-stu-id="0496a-121">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="0496a-122">如何：使用 Windows 窗体 LinkLabel 控件链接到对象或 Web 页面</span><span class="sxs-lookup"><span data-stu-id="0496a-122">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="0496a-123">LinkLabel 控件</span><span class="sxs-lookup"><span data-stu-id="0496a-123">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
