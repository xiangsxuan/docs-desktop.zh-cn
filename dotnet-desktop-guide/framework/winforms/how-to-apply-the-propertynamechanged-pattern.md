---
title: 如何：应用 PropertyNameChanged 模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 01afa713e97206ea192ba55dc2affad20163f872
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970272"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="2bd35-102">如何：应用 PropertyNameChanged 模式</span><span class="sxs-lookup"><span data-stu-id="2bd35-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="2bd35-103">下面的代码示例演示如何将 *属性名称* 更改模式应用于自定义控件。</span><span class="sxs-lookup"><span data-stu-id="2bd35-103">The following code example demonstrates how to apply the *PropertyName* Changed pattern to a custom control.</span></span> <span data-ttu-id="2bd35-104">当实现与 Windows 窗体数据绑定引擎一起使用的自定义控件时，应用此模式。</span><span class="sxs-lookup"><span data-stu-id="2bd35-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bd35-105">示例</span><span class="sxs-lookup"><span data-stu-id="2bd35-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2bd35-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="2bd35-106">Compiling the Code</span></span>  
 <span data-ttu-id="2bd35-107">编译前面的代码示例：</span><span class="sxs-lookup"><span data-stu-id="2bd35-107">To compile the previous code example:</span></span>  
  
- <span data-ttu-id="2bd35-108">将代码粘贴到空代码文件中。</span><span class="sxs-lookup"><span data-stu-id="2bd35-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="2bd35-109">必须在包含方法的 Windows 窗体上使用自定义控件 `Main` 。</span><span class="sxs-lookup"><span data-stu-id="2bd35-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bd35-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bd35-110">See also</span></span>

- [<span data-ttu-id="2bd35-111">如何：实现 INotifyPropertyChanged 接口</span><span class="sxs-lookup"><span data-stu-id="2bd35-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](how-to-implement-the-inotifypropertychanged-interface.md)
- [<span data-ttu-id="2bd35-112">Windows 窗体数据绑定中的更改通知</span><span class="sxs-lookup"><span data-stu-id="2bd35-112">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="2bd35-113">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="2bd35-113">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
