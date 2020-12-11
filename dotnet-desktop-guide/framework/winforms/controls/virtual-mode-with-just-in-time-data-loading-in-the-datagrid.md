---
title: 在 DataGridView 控件中实现实时数据加载的虚拟模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: 33825f92-7a22-40ee-86d9-9a2ed1ead7b7
ms.openlocfilehash: 7b7990ceacba9e5f479149c934db1914e8dd0bef
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973158"
---
# <a name="how-to-implement-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="1cc57-102">如何：在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式</span><span class="sxs-lookup"><span data-stu-id="1cc57-102">How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="1cc57-103">下面的代码示例显示如何使用 <xref:System.Windows.Forms.DataGridView> 控件中的虚拟模式及仅在需要时从服务器加载数据的数据缓存。</span><span class="sxs-lookup"><span data-stu-id="1cc57-103">The following code example shows how to use virtual mode in the <xref:System.Windows.Forms.DataGridView> control with a data cache that loads data from a server only when it is needed.</span></span> <span data-ttu-id="1cc57-104">在 [Windows 窗体 DataGridView 控件中实现包含实时数据加载的虚拟模式](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)一文中详细介绍了此示例。</span><span class="sxs-lookup"><span data-stu-id="1cc57-104">This example is described in detail in [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cc57-105">示例</span><span class="sxs-lookup"><span data-stu-id="1cc57-105">Example</span></span>  

 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1cc57-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="1cc57-106">Compiling the Code</span></span>  

 <span data-ttu-id="1cc57-107">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="1cc57-107">This example requires:</span></span>  
  
- <span data-ttu-id="1cc57-108">引用 System、System.Data、System.Xml 和 System.Windows.Forms 程序集。</span><span class="sxs-lookup"><span data-stu-id="1cc57-108">References to the System, System.Data, System.Xml, and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="1cc57-109">可访问安装有 Northwind SQL Server 示例数据库的服务器。</span><span class="sxs-lookup"><span data-stu-id="1cc57-109">Access to a server with the Northwind SQL Server sample database installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1cc57-110">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="1cc57-110">.NET Framework Security</span></span>  

 <span data-ttu-id="1cc57-111">将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="1cc57-111">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="1cc57-112">若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。</span><span class="sxs-lookup"><span data-stu-id="1cc57-112">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="1cc57-113">有关详细信息，请参阅 [保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)。</span><span class="sxs-lookup"><span data-stu-id="1cc57-113">For more information, see [Protecting Connection Information](/dotnet/framework/data/adonet/protecting-connection-information).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cc57-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1cc57-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- [<span data-ttu-id="1cc57-115">在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式</span><span class="sxs-lookup"><span data-stu-id="1cc57-115">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [<span data-ttu-id="1cc57-116">Windows 窗体 DataGridView 控件中的性能优化</span><span class="sxs-lookup"><span data-stu-id="1cc57-116">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1cc57-117">Windows 窗体 DataGridView 控件中的虚拟模式</span><span class="sxs-lookup"><span data-stu-id="1cc57-117">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)
