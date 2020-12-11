---
title: 如何：向文件对话框添加自定义区域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: 7172e484451cf932413920910ec9124b3388bd76
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971284"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>如何：向文件对话框添加自定义区域
Windows Vista 上的默认 "打开" 和 "保存" 对话框中有一个区域，其标题为 " **收藏夹链接**"。 此区域称为自定义区域。 <xref:System.Windows.Forms.OpenFileDialog>和 <xref:System.Windows.Forms.SaveFileDialog> 类允许将文件夹添加到 <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> 集合中。  
  
> [!NOTE]
> 若要使自定义位置显示在或中 <xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.SaveFileDialog> ，则 <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> 属性必须设置为 `true` (默认) 。  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>向文件对话框添加自定义区域  
  
- 将路径、已知文件夹 GUID 或 <xref:System.Windows.Forms.FileDialogCustomPlace> 对象添加到对话框的集合中 <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> 。  
  
     以下代码示例演示了如何添加路径：  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [文件对话框自定义区域的已知文件夹 GUID](known-folder-guids-for-file-dialog-custom-places.md)
