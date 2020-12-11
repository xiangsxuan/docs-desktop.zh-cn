---
title: 如何：显示对话框
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, displaying
- Windows Forms dialog boxes [Windows Forms], displaying
- Windows Forms, calling one form from another
- dialog boxes [Windows Forms], displaying for Windows Forms
ms.assetid: aaac1b38-c651-495a-8d3d-5a9bfb32fee3
ms.openlocfilehash: 3625080c7c322e297a9de92e4f95a40c0caf3e72
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970251"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a><span data-ttu-id="bf6f1-102">如何：显示 Windows 窗体的对话框</span><span class="sxs-lookup"><span data-stu-id="bf6f1-102">How to: Display Dialog Boxes for Windows Forms</span></span>
<span data-ttu-id="bf6f1-103">您可以使用与在应用程序中显示任何其他窗体相同的方式来显示对话框。</span><span class="sxs-lookup"><span data-stu-id="bf6f1-103">You display a dialog box in the same way you display any other form in an application.</span></span> <span data-ttu-id="bf6f1-104">启动窗体在应用程序运行时自动加载。</span><span class="sxs-lookup"><span data-stu-id="bf6f1-104">The startup form loads automatically when the application is run.</span></span> <span data-ttu-id="bf6f1-105">若要使第二个窗体或对话框显示在应用程序中，请编写用于加载和显示它的代码。</span><span class="sxs-lookup"><span data-stu-id="bf6f1-105">To make a second form or dialog box appear in the application, write code to load and display it.</span></span> <span data-ttu-id="bf6f1-106">同样，若要使窗体或对话框消失，请编写代码来卸载或隐藏它。</span><span class="sxs-lookup"><span data-stu-id="bf6f1-106">Similarly, to make the form or dialog box disappear, write code to unload or hide it.</span></span>  
  
### <a name="to-display-a-dialog-box"></a><span data-ttu-id="bf6f1-107">显示对话框</span><span class="sxs-lookup"><span data-stu-id="bf6f1-107">To display a dialog box</span></span>  
  
1. <span data-ttu-id="bf6f1-108">导航到要用于打开对话框的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="bf6f1-108">Navigate to the event handler with which you want to open the dialog box.</span></span> <span data-ttu-id="bf6f1-109">如果选择了菜单命令、单击按钮或发生其他任何事件，则会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="bf6f1-109">This can happen when a menu command is selected, when a button is clicked, or when any other event occurs.</span></span>  
  
2. <span data-ttu-id="bf6f1-110">在事件处理程序中，添加代码以打开对话框。</span><span class="sxs-lookup"><span data-stu-id="bf6f1-110">In the event handler, add code to open the dialog box.</span></span> <span data-ttu-id="bf6f1-111">在此示例中，按钮单击事件用于显示对话框：</span><span class="sxs-lookup"><span data-stu-id="bf6f1-111">In this example, a button-click event is used to show the dialog box:</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim dlg1 as new Form()  
       dlg1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)
    {  
       Form dlg1 = new Form();  
       dlg1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:
      void button1_Click(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        Form ^ dlg1 = gcnew Form();  
        dlg1->ShowDialog();  
      }  
    ```
