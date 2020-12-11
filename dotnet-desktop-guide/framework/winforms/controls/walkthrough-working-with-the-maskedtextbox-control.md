---
title: 演练：使用 MaskedTextBox 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: db32b3ec88a07747ea3e286af9f04edce3f1ba3b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972489"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a><span data-ttu-id="43117-102">演练：使用 MaskedTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="43117-102">Walkthrough: Working with the MaskedTextBox Control</span></span>
<span data-ttu-id="43117-103">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="43117-103">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="43117-104">初始化 <xref:System.Windows.Forms.MaskedTextBox> 控件</span><span class="sxs-lookup"><span data-stu-id="43117-104">Initializing the <xref:System.Windows.Forms.MaskedTextBox> control</span></span>  
  
- <span data-ttu-id="43117-105">使用 <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> 事件处理程序在字符不符合掩码时向用户发出警报</span><span class="sxs-lookup"><span data-stu-id="43117-105">Using the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event handler to alert the user when a character does not conform to the mask</span></span>  
  
- <span data-ttu-id="43117-106">将类型分配给 <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 属性，并使用 <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> 事件处理程序在尝试提交的值对类型无效时向用户发出警报</span><span class="sxs-lookup"><span data-stu-id="43117-106">Assigning a type to the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property and using the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event handler to alert the user when the value they're attempting to commit is not valid for the type</span></span>  
  
## <a name="creating-the-project-and-adding-a-control"></a><span data-ttu-id="43117-107">创建项目并添加控件</span><span class="sxs-lookup"><span data-stu-id="43117-107">Creating the Project and Adding a Control</span></span>  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a><span data-ttu-id="43117-108">向窗体中添加 MaskedTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="43117-108">To add a MaskedTextBox control to your form</span></span>  
  
1. <span data-ttu-id="43117-109">打开要在其上放置控件的窗体 <xref:System.Windows.Forms.MaskedTextBox> 。</span><span class="sxs-lookup"><span data-stu-id="43117-109">Open the form on which you want to place the <xref:System.Windows.Forms.MaskedTextBox> control.</span></span>  
  
2. <span data-ttu-id="43117-110">将 <xref:System.Windows.Forms.MaskedTextBox> 控件从 **工具箱** 拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="43117-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control from the **Toolbox** to your form.</span></span>  
  
3. <span data-ttu-id="43117-111">右键单击控件，然后选择 " **属性**"。</span><span class="sxs-lookup"><span data-stu-id="43117-111">Right-click the control and choose **Properties**.</span></span> <span data-ttu-id="43117-112">在 " **属性** " 窗口中，选择 " **Mask** " 属性，然后单击属性名称旁边的 " **...** (省略号) " 按钮。</span><span class="sxs-lookup"><span data-stu-id="43117-112">In the **Properties** window, select the **Mask** property and click the **...** (ellipsis) button next to the property name.</span></span>  
  
4. <span data-ttu-id="43117-113">在 " **输入掩码** " 对话框中，选择 **短日期** 掩码，并单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="43117-113">In the **Input Mask** dialog box, select the **Short Date** mask and click **OK**.</span></span>  
  
5. <span data-ttu-id="43117-114">在 " **属性** " 窗口中，将 <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> 属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="43117-114">In the **Properties** window set the <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> property to `true`.</span></span> <span data-ttu-id="43117-115">每次用户尝试输入违反掩码定义的字符时，此属性会导致短提示音。</span><span class="sxs-lookup"><span data-stu-id="43117-115">This property causes a short beep to sound every time the user attempts to input a character that violates the mask definition.</span></span>  
  
 <span data-ttu-id="43117-116">有关 Mask 属性支持的字符摘要，请参阅属性的 "备注" 部分 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 。</span><span class="sxs-lookup"><span data-stu-id="43117-116">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
## <a name="alert-the-user-to-input-errors"></a><span data-ttu-id="43117-117">提醒用户输入错误</span><span class="sxs-lookup"><span data-stu-id="43117-117">Alert the User to Input Errors</span></span>  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a><span data-ttu-id="43117-118">为拒绝的掩码输入添加气球提示</span><span class="sxs-lookup"><span data-stu-id="43117-118">Add a balloon tip for rejected mask input</span></span>  
  
1. <span data-ttu-id="43117-119">返回到 " **工具箱** "，并将添加 <xref:System.Windows.Forms.ToolTip> 到窗体。</span><span class="sxs-lookup"><span data-stu-id="43117-119">Return to the **Toolbox** and add a <xref:System.Windows.Forms.ToolTip> to your form.</span></span>  
  
2. <span data-ttu-id="43117-120">为 <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> 引发输入错误时引发的事件创建事件处理程序 <xref:System.Windows.Forms.ToolTip> 。</span><span class="sxs-lookup"><span data-stu-id="43117-120">Create an event handler for the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event that raises the <xref:System.Windows.Forms.ToolTip> when an input error occurs.</span></span> <span data-ttu-id="43117-121">气球状提示在5秒内保持可见，或在用户单击它之前显示。</span><span class="sxs-lookup"><span data-stu-id="43117-121">The balloon tip remains visible for five seconds, or until the user clicks it.</span></span>  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a><span data-ttu-id="43117-122">向用户通知无效类型</span><span class="sxs-lookup"><span data-stu-id="43117-122">Alert the User to a Type that Is Not Valid</span></span>  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a><span data-ttu-id="43117-123">为无效数据类型添加气球状提示</span><span class="sxs-lookup"><span data-stu-id="43117-123">Add a balloon tip for invalid data types</span></span>  
  
1. <span data-ttu-id="43117-124">在窗体的 <xref:System.Windows.Forms.Form.Load> 事件处理程序中，将 <xref:System.Type> 表示类型的对象分配 <xref:System.DateTime> 给 <xref:System.Windows.Forms.MaskedTextBox> 控件的 <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 属性：</span><span class="sxs-lookup"><span data-stu-id="43117-124">In your form's <xref:System.Windows.Forms.Form.Load> event handler, assign a <xref:System.Type> object representing the <xref:System.DateTime> type to the <xref:System.Windows.Forms.MaskedTextBox> control's <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property:</span></span>  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2. <span data-ttu-id="43117-125">为 <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> 事件添加事件处理程序：</span><span class="sxs-lookup"><span data-stu-id="43117-125">Add an event handler for the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event:</span></span>  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="43117-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43117-126">See also</span></span>

- <xref:System.Windows.Forms.MaskedTextBox>
- [<span data-ttu-id="43117-127">MaskedTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="43117-127">MaskedTextBox Control</span></span>](maskedtextbox-control-windows-forms.md)
