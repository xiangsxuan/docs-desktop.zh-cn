---
title: 如何：禁用选项卡页
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
ms.openlocfilehash: 9074aedb81a485267dc4faff92e0fe8d0d3b467f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971845"
---
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="5ffa6-102">如何：禁用选项卡页</span><span class="sxs-lookup"><span data-stu-id="5ffa6-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="5ffa6-103">在某些情况下，你需要限制对 Windows 窗体应用程序中提供的数据的访问。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="5ffa6-104">在选项卡控件的选项卡页中显示数据时，可能会出现这种情况的一个示例：管理员可以在 "选项卡" 页上了解要从来宾或较低级别用户限制的信息。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="5ffa6-105">以编程方式禁用选项卡页</span><span class="sxs-lookup"><span data-stu-id="5ffa6-105">To disable tab pages programmatically</span></span>  
  
1. <span data-ttu-id="5ffa6-106">编写代码来处理选项卡控件的 <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> 事件。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="5ffa6-107">这是用户从一个选项卡切换到下一个选项卡时引发的事件。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2. <span data-ttu-id="5ffa6-108">检查凭据。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-108">Check credentials.</span></span> <span data-ttu-id="5ffa6-109">根据提供的信息，可能需要检查用户已登录的用户名或其他形式的凭据，然后允许用户查看该选项卡。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3. <span data-ttu-id="5ffa6-110">如果用户具有适当的凭据，则显示所单击的选项卡。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="5ffa6-111">如果用户没有适当的凭据，则显示一个消息框或其他一些用户界面，指出他们没有访问权限，并返回初始选项卡。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="5ffa6-112">当你在生产应用程序中实现此功能时，你可以在窗体事件期间执行此凭据检查 <xref:System.Windows.Forms.Form.Load> 。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="5ffa6-113">这将允许您在显示任何用户界面之前隐藏该选项卡，这是一种更清晰的编程方法。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="5ffa6-114">下面使用的方法 (检查凭据并禁用事件) 期间的选项卡， <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> 用于说明目的。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4. <span data-ttu-id="5ffa6-115">或者，如果有两个以上的选项卡页，则显示与原始选项卡页不同的选项卡页。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="5ffa6-116">在下面的示例中， <xref:System.Windows.Forms.CheckBox> 使用控件代替检查凭据，因为对该选项卡的访问条件将因应用程序而异。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="5ffa6-117"><xref:System.Windows.Forms.TabControl.SelectedIndexChanged>引发事件时，如果凭据检查为 true (即，复选框处于选中状态) 并且选中的选项卡 `TabPage2` (包含机密信息的选项卡) ，则 `TabPage2` 会显示。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="5ffa6-118">否则， `TabPage3` 将显示并向用户显示一个消息框，指示它们没有适当的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="5ffa6-119">下面的代码假设窗体具有 <xref:System.Windows.Forms.CheckBox> 控件 (`CredentialCheck`) 和 <xref:System.Windows.Forms.TabControl> 具有三个选项卡页的控件。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
    ```vb  
    Private Sub TabControl1_SelectedIndexChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles TabControl1.SelectedIndexChanged  
       ' Check Credentials Here  
  
       If CredentialCheck.Checked = True And _
       TabControl1.SelectedTab Is TabPage2 Then  
          TabControl1.SelectedTab = TabPage2  
       ElseIf CredentialCheck.Checked = False _
       And TabControl1.SelectedTab Is TabPage2 Then  
          MessageBox.Show _
         ("Unable to load tab. You have insufficient access privileges.")  
          TabControl1.SelectedTab = TabPage3  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void tabControl1_SelectedIndexChanged(object sender, System.EventArgs e)  
    {  
        // Check Credentials Here  
  
        if ((CredentialCheck.Checked == true) && (tabControl1.SelectedTab == tabPage2))
        {  
            tabControl1.SelectedTab = tabPage2;  
        }  
        else if ((CredentialCheck.Checked == false) && (tabControl1.SelectedTab == tabPage2))  
        {  
            MessageBox.Show("Unable to load tab. You have insufficient access privileges.");  
            tabControl1.SelectedTab = tabPage3;  
        }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void tabControl1_SelectedIndexChanged(  
          System::Object ^ sender,  
          System::EventArgs ^  e)  
       {  
          // Check Credentials Here  
          if ((CredentialCheck->Checked == true) &&  
              (tabControl1->SelectedTab == tabPage2))  
          {  
             tabControl1->SelectedTab = tabPage2;  
          }  
          else if ((CredentialCheck->Checked == false) &&  
                   (tabControl1->SelectedTab == tabPage2))  
          {  
             MessageBox::Show(String::Concat("Unable to load tab. ",  
                "You have insufficient access privileges."));  
             tabControl1->SelectedTab = tabPage3;  
          }  
       }  
    ```  
  
     <span data-ttu-id="5ffa6-120"> (Visual c # 中，Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5ffa6-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5ffa6-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ffa6-121">See also</span></span>

- [<span data-ttu-id="5ffa6-122">TabControl 控件概述</span><span class="sxs-lookup"><span data-stu-id="5ffa6-122">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="5ffa6-123">如何：将控件添加到选项卡页</span><span class="sxs-lookup"><span data-stu-id="5ffa6-123">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="5ffa6-124">如何：使用 Windows 窗体 TabControl 添加和移除选项卡</span><span class="sxs-lookup"><span data-stu-id="5ffa6-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="5ffa6-125">如何：更改 Windows 窗体 TabControl 的外观</span><span class="sxs-lookup"><span data-stu-id="5ffa6-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
