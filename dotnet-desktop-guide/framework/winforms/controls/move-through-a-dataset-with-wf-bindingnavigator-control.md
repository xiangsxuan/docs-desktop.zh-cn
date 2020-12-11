---
title: 使用 BindingNavigator 控件浏览数据集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- datasets [Windows Forms], moving through
- BindingNavigator control [Windows Forms], moving through datasets
- examples [Windows Forms], BindingNavigator control
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
ms.openlocfilehash: 8f023521ab78f6a0bf44b2c6afcbf618eb745ad9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972606"
---
# <a name="how-to-move-through-a-dataset-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="0abb2-102">如何：使用 Windows 窗体 BindingNavigator 控件浏览数据集</span><span class="sxs-lookup"><span data-stu-id="0abb2-102">How to: Move Through a DataSet with the Windows Forms BindingNavigator Control</span></span>

<span data-ttu-id="0abb2-103">生成数据驱动的应用程序时，经常需要向用户显示数据集合。</span><span class="sxs-lookup"><span data-stu-id="0abb2-103">As you build data-driven applications, you will often need to display collections of data to users.</span></span> <span data-ttu-id="0abb2-104"><xref:System.Windows.Forms.BindingNavigator> 控件与 <xref:System.Windows.Forms.BindingSource> 组件一起为滚动集合并按顺序显示其中的项提供方便的可扩展解决方案。</span><span class="sxs-lookup"><span data-stu-id="0abb2-104">The <xref:System.Windows.Forms.BindingNavigator> control, in conjunction with the <xref:System.Windows.Forms.BindingSource> component, provides a convenient and extensible solution for moving through a collection and displaying items sequentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0abb2-105">示例</span><span class="sxs-lookup"><span data-stu-id="0abb2-105">Example</span></span>  

 <span data-ttu-id="0abb2-106">下面的代码示例演示如何使用 <xref:System.Windows.Forms.BindingNavigator> 控件来浏览数据。</span><span class="sxs-lookup"><span data-stu-id="0abb2-106">The following code example demonstrates how to use a <xref:System.Windows.Forms.BindingNavigator> control to move through data.</span></span> <span data-ttu-id="0abb2-107">集合包含在 <xref:System.Data.DataView> 中，后者使用 <xref:System.Windows.Forms.BindingSource> 组件绑定到 <xref:System.Windows.Forms.TextBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="0abb2-107">The set is contained in a <xref:System.Data.DataView>, which is bound to a <xref:System.Windows.Forms.TextBox> control with a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0abb2-108">将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="0abb2-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="0abb2-109">若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。</span><span class="sxs-lookup"><span data-stu-id="0abb2-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="0abb2-110">有关详细信息，请参阅 [保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)。</span><span class="sxs-lookup"><span data-stu-id="0abb2-110">For more information, see [Protecting Connection Information](/dotnet/framework/data/adonet/protecting-connection-information).</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0abb2-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="0abb2-111">Compiling the Code</span></span>  

 <span data-ttu-id="0abb2-112">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="0abb2-112">This example requires:</span></span>  
  
- <span data-ttu-id="0abb2-113">对 System、System.Data、System.Drawing、System.Windows.Forms 和 System.Xml 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="0abb2-113">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0abb2-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0abb2-114">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="0abb2-115">BindingNavigator 控件</span><span class="sxs-lookup"><span data-stu-id="0abb2-115">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="0abb2-116">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="0abb2-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="0abb2-117">如何：将 Windows 窗体控件绑定到类型</span><span class="sxs-lookup"><span data-stu-id="0abb2-117">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
