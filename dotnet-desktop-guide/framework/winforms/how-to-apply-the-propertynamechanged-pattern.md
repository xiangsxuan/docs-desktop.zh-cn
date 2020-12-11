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
# <a name="how-to-apply-the-propertynamechanged-pattern"></a>如何：应用 PropertyNameChanged 模式
下面的代码示例演示如何将 *属性名称* 更改模式应用于自定义控件。 当实现与 Windows 窗体数据绑定引擎一起使用的自定义控件时，应用此模式。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>编译代码  
 编译前面的代码示例：  
  
- 将代码粘贴到空代码文件中。 必须在包含方法的 Windows 窗体上使用自定义控件 `Main` 。  
  
## <a name="see-also"></a>另请参阅

- [如何：实现 INotifyPropertyChanged 接口](how-to-implement-the-inotifypropertychanged-interface.md)
- [Windows 窗体数据绑定中的更改通知](change-notification-in-windows-forms-data-binding.md)
- [Windows 窗体数据绑定](windows-forms-data-binding.md)
