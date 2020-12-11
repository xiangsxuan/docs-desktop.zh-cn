---
title: 如何：提取与文件关联的图标
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: 28769144b0e1c631a31c3c541747a6215f861d0e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971448"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a><span data-ttu-id="9d504-102">如何：提取与 Windows 窗体中的文件关联的图标</span><span class="sxs-lookup"><span data-stu-id="9d504-102">How to: Extract the Icon Associated with a File in Windows Forms</span></span>
<span data-ttu-id="9d504-103">许多文件都具有嵌入的图标，可提供相关文件类型的直观表示形式。</span><span class="sxs-lookup"><span data-stu-id="9d504-103">Many files have embedded icons that provide a visual representation of the associated file type.</span></span> <span data-ttu-id="9d504-104">例如，Microsoft Word 文档包含一个图标，该图标将其标识为 Word 文档。</span><span class="sxs-lookup"><span data-stu-id="9d504-104">For example, Microsoft Word documents contain an icon that identifies them as Word documents.</span></span> <span data-ttu-id="9d504-105">当在列表控件或表控件中显示文件时，您可能希望显示表示每个文件名旁边的文件类型的图标。</span><span class="sxs-lookup"><span data-stu-id="9d504-105">When displaying files in a list control or table control, you may want to display the icon representing the file type next to each file name.</span></span> <span data-ttu-id="9d504-106">您可以使用方法轻松地执行此操作 <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> 。</span><span class="sxs-lookup"><span data-stu-id="9d504-106">You can do this easily by using the <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d504-107">示例</span><span class="sxs-lookup"><span data-stu-id="9d504-107">Example</span></span>  
 <span data-ttu-id="9d504-108">下面的代码示例演示如何提取与文件关联的图标，并在控件中显示文件名及其关联的图标 <xref:System.Windows.Forms.ListView> 。</span><span class="sxs-lookup"><span data-stu-id="9d504-108">The following code example demonstrates how to extract the icon associated with a file and display the file name and its associated icon in a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9d504-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="9d504-109">Compiling the Code</span></span>  
 <span data-ttu-id="9d504-110">若要编译该示例：</span><span class="sxs-lookup"><span data-stu-id="9d504-110">To compile the example:</span></span>  
  
- <span data-ttu-id="9d504-111">将前面的代码粘贴到 Windows 窗体中，并 `ExtractAssociatedIconExample` 从窗体的构造函数或 <xref:System.Windows.Forms.Form.Load> 事件处理方法调用方法。</span><span class="sxs-lookup"><span data-stu-id="9d504-111">Paste the preceding code into a Windows Form, and call the `ExtractAssociatedIconExample` method from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     <span data-ttu-id="9d504-112">你将需要确保你的窗体导入 <xref:System.IO> 命名空间。</span><span class="sxs-lookup"><span data-stu-id="9d504-112">You will need to make sure that your form imports the <xref:System.IO> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d504-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d504-113">See also</span></span>

- [<span data-ttu-id="9d504-114">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="9d504-114">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="9d504-115">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="9d504-115">ListView Control</span></span>](../controls/listview-control-windows-forms.md)
