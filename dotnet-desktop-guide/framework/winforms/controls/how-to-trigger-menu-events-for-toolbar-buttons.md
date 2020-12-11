---
title: 如何：触发工具栏按钮的菜单事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], click event handlers
- ToolBar control [Windows Forms], coding button click events
- toolbars [Windows Forms], click event handlers
ms.assetid: 98374f70-993d-4ca4-89fb-48fea6ce5b45
ms.openlocfilehash: 99db077b41a59fe9263f7283b58b8c31959c7c79
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972545"
---
# <a name="how-to-trigger-menu-events-for-toolbar-buttons"></a><span data-ttu-id="2d45f-102">如何：触发工具栏按钮的菜单事件</span><span class="sxs-lookup"><span data-stu-id="2d45f-102">How to: Trigger Menu Events for Toolbar Buttons</span></span>
> [!NOTE]
> <span data-ttu-id="2d45f-103"><xref:System.Windows.Forms.ToolStrip> 控件取代了 <xref:System.Windows.Forms.ToolBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ToolBar> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="2d45f-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="2d45f-104">如果 Windows 窗体 <xref:System.Windows.Forms.ToolBar> 使用工具栏按钮作为控件的功能，则需要知道用户单击了哪个按钮。</span><span class="sxs-lookup"><span data-stu-id="2d45f-104">If your Windows Form features a <xref:System.Windows.Forms.ToolBar> control with toolbar buttons, you will want to know which button the user clicks.</span></span>  
  
 <span data-ttu-id="2d45f-105">在 <xref:System.Windows.Forms.ToolBar.ButtonClick> 控件的事件 <xref:System.Windows.Forms.ToolBar> 中，可以计算类的 <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> 属性 <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> 。</span><span class="sxs-lookup"><span data-stu-id="2d45f-105">On the <xref:System.Windows.Forms.ToolBar.ButtonClick> event of the <xref:System.Windows.Forms.ToolBar> control, you can evaluate the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> property of the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> class.</span></span> <span data-ttu-id="2d45f-106">在下面的示例中，将显示一个消息框，指示单击了哪个按钮。</span><span class="sxs-lookup"><span data-stu-id="2d45f-106">In the example below, a message box is shown, indicating which button was clicked.</span></span> <span data-ttu-id="2d45f-107">有关详细信息，请参阅 <xref:System.Windows.Forms.MessageBox>。</span><span class="sxs-lookup"><span data-stu-id="2d45f-107">For details, see <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="2d45f-108">下面的示例假定已将 <xref:System.Windows.Forms.ToolBar> 控件添加到 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="2d45f-108">The example below assumes a <xref:System.Windows.Forms.ToolBar> control has been added to a Windows Form.</span></span>  
  
### <a name="to-handle-the-click-event-on-a-toolbar"></a><span data-ttu-id="2d45f-109">处理工具栏上的单击事件</span><span class="sxs-lookup"><span data-stu-id="2d45f-109">To handle the Click event on a toolbar</span></span>  
  
1. <span data-ttu-id="2d45f-110">在过程中，将工具栏按钮添加到 <xref:System.Windows.Forms.ToolBar> 控件。</span><span class="sxs-lookup"><span data-stu-id="2d45f-110">In a procedure, add toolbar buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
    ```vb  
    Public Sub ToolBarConfig()  
    ' Instantiate the toolbar buttons, set their Text properties  
    ' and add them to the ToolBar control.  
       ToolBar1.Buttons.Add(New ToolBarButton("One"))  
       ToolBar1.Buttons.Add(New ToolBarButton("Two"))  
       ToolBar1.Buttons.Add(New ToolBarButton("Three"))  
    ' Add the event handler delegate.  
       AddHandler ToolBar1.ButtonClick, AddressOf Me.ToolBar1_ButtonClick  
    End Sub  
    ```  
  
    ```csharp  
    public void ToolBarConfig()
    {  
       toolBar1.Buttons.Add(new ToolBarButton("One"));  
       toolBar1.Buttons.Add(new ToolBarButton("Two"));  
       toolBar1.Buttons.Add(new ToolBarButton("Three"));  
  
       toolBar1.ButtonClick +=
          new ToolBarButtonClickEventHandler(this.toolBar1_ButtonClick);  
    }  
    ```  
  
    ```cpp  
    public:  
       void ToolBarConfig()  
       {  
          toolBar1->Buttons->Add(gcnew ToolBarButton("One"));  
          toolBar1->Buttons->Add(gcnew ToolBarButton("Two"));  
          toolBar1->Buttons->Add(gcnew ToolBarButton("Three"));  
  
          toolBar1->ButtonClick +=
             gcnew ToolBarButtonClickEventHandler(this,  
             &Form1::toolBar1_ButtonClick);  
       }  
    ```  
  
2. <span data-ttu-id="2d45f-111">为 <xref:System.Windows.Forms.ToolBar> 控件的事件添加事件处理程序 <xref:System.Windows.Forms.ToolBar.ButtonClick> 。</span><span class="sxs-lookup"><span data-stu-id="2d45f-111">Add an event handler for the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ButtonClick> event.</span></span> <span data-ttu-id="2d45f-112">使用 case 切换语句和 <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> 类来确定单击的工具栏按钮。</span><span class="sxs-lookup"><span data-stu-id="2d45f-112">Use a case switching statement and the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> class to determine the toolbar button that was clicked.</span></span> <span data-ttu-id="2d45f-113">并据此显示相应的消息框。</span><span class="sxs-lookup"><span data-stu-id="2d45f-113">Based on this, show an appropriate message box.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="2d45f-114">在本示例中，消息框仅用作占位符。</span><span class="sxs-lookup"><span data-stu-id="2d45f-114">A message box is being used solely as a placeholder in this example.</span></span> <span data-ttu-id="2d45f-115">可随意添加在单击工具栏按钮时要执行的其他代码。</span><span class="sxs-lookup"><span data-stu-id="2d45f-115">Feel free to add other code to execute when the toolbar buttons are clicked.</span></span>  
  
    ```vb  
    Protected Sub ToolBar1_ButtonClick(ByVal sender As Object, _  
    ByVal e As ToolBarButtonClickEventArgs)  
    ' Evaluate the Button property of the ToolBarButtonClickEventArgs  
    ' to determine which button was clicked.  
       Select Case ToolBar1.Buttons.IndexOf(e.Button)  
         Case 0  
           MessageBox.Show("First toolbar button clicked")  
         Case 1  
           MessageBox.Show("Second toolbar button clicked")  
         Case 2  
           MessageBox.Show("Third toolbar button clicked")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    protected void toolBar1_ButtonClick(object sender,  
    ToolBarButtonClickEventArgs e)  
    {  
       // Evaluate the Button property of the ToolBarButtonClickEventArgs  
       // to determine which button was clicked.  
       switch (toolBar1.Buttons.IndexOf(e.Button))  
       {  
          case 0 :  
             MessageBox.Show("First toolbar button clicked");  
             break;  
          case 1 :  
             MessageBox.Show("Second toolbar button clicked");  
             break;  
          case 2 :  
             MessageBox.Show("Third toolbar button clicked");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    protected:  
       void toolBar1_ButtonClick(System::Object ^ sender,  
          ToolBarButtonClickEventArgs ^ e)  
       {  
         // Evaluate the Button property of the ToolBarButtonClickEventArgs  
         // to determine which button was clicked.  
          switch (toolBar1->Buttons->IndexOf(e->Button))  
          {  
             case 0 :  
                MessageBox::Show("First toolbar button clicked");  
                break;  
             case 1 :  
                MessageBox::Show("Second toolbar button clicked");  
                break;  
             case 2 :  
                MessageBox::Show("Third toolbar button clicked");  
                break;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2d45f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d45f-116">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="2d45f-117">如何：向 ToolBar 控件添加按钮</span><span class="sxs-lookup"><span data-stu-id="2d45f-117">How to: Add Buttons to a ToolBar Control</span></span>](how-to-add-buttons-to-a-toolbar-control.md)
- [<span data-ttu-id="2d45f-118">如何：定义工具栏按钮的图标</span><span class="sxs-lookup"><span data-stu-id="2d45f-118">How to: Define an Icon for a ToolBar Button</span></span>](how-to-define-an-icon-for-a-toolbar-button.md)
- [<span data-ttu-id="2d45f-119">ToolBar 控件</span><span class="sxs-lookup"><span data-stu-id="2d45f-119">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
