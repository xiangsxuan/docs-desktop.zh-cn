---
title: 使用 ErrorProvider 组件查看数据集中的错误
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: 8c2155bf288db89b5d53567738fd399b915d50b6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973107"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="53470-102">如何：使用 Windows 窗体 ErrorProvider 组件查看数据集中的错误</span><span class="sxs-lookup"><span data-stu-id="53470-102">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="53470-103">您可以使用 Windows 窗体 <xref:System.Windows.Forms.ErrorProvider> 组件来查看数据集或其他数据源中的列错误。</span><span class="sxs-lookup"><span data-stu-id="53470-103">You can use the Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to view column errors within a dataset or other data source.</span></span> <span data-ttu-id="53470-104">为了使 <xref:System.Windows.Forms.ErrorProvider> 组件能够在窗体上显示数据错误，无需直接与控件关联。</span><span class="sxs-lookup"><span data-stu-id="53470-104">For an <xref:System.Windows.Forms.ErrorProvider> component to display data errors on a form, it does not have to be directly associated with a control.</span></span> <span data-ttu-id="53470-105">绑定到数据源后，它可以在绑定到同一个数据源的任何控件旁显示错误图标。</span><span class="sxs-lookup"><span data-stu-id="53470-105">Once it is bound to a data source, it can display an error icon next to any control that is bound to the same data source.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53470-106">如果在运行时更改错误提供程序的 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> 和 <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> 属性，则应使用 <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> 方法以避免冲突。</span><span class="sxs-lookup"><span data-stu-id="53470-106">If you change the error provider's <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> and <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> properties at run time, you should use the <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> method to avoid conflicts.</span></span>  
  
### <a name="to-display-data-errors"></a><span data-ttu-id="53470-107">显示数据错误</span><span class="sxs-lookup"><span data-stu-id="53470-107">To display data errors</span></span>  
  
1. <span data-ttu-id="53470-108">将组件绑定到数据表中的特定列。</span><span class="sxs-lookup"><span data-stu-id="53470-108">Bind the component to a specific column within a data table.</span></span>  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
    ```  
  
2. <span data-ttu-id="53470-109">将 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 属性设置为窗体。</span><span class="sxs-lookup"><span data-stu-id="53470-109">Set the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property to the form.</span></span>  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3. <span data-ttu-id="53470-110">将当前记录的位置设置为包含列错误的行。</span><span class="sxs-lookup"><span data-stu-id="53470-110">Set the position of the current record to a row that contains a column error.</span></span>  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="53470-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53470-111">See also</span></span>

- [<span data-ttu-id="53470-112">ErrorProvider 组件概述</span><span class="sxs-lookup"><span data-stu-id="53470-112">ErrorProvider Component Overview</span></span>](errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="53470-113">如何：使用 Windows 窗体 ErrorProvider 组件显示窗体验证的错误图标</span><span class="sxs-lookup"><span data-stu-id="53470-113">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](display-error-icons-for-form-validation-with-wf-errorprovider.md)