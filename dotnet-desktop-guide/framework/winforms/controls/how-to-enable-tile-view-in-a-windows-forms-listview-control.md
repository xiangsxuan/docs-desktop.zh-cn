---
title: 在 ListView 控件中启用磁贴视图
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tile view feature
- tiling
- Windows Forms, controls
- ListView control [Windows Forms], tile view
ms.assetid: c20e67a3-2d94-413d-9fcf-ecbd0fe251da
ms.openlocfilehash: 1478ba5e4f175cd7d9ec7ab5c3c4bc9050ce02fb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972033"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control"></a>如何：在 Windows 窗体 ListView 控件中启用平铺视图
使用 <xref:System.Windows.Forms.ListView> 控件的磁贴视图功能，可以在图形和文本信息之间提供一种视觉平衡。 磁贴视图中，为项目显示的文本信息与为详细信息视图定义的列信息相同。 磁贴视图与 <xref:System.Windows.Forms.ListView> 控件中的分组或插入标记功能配合使用。  
  
 磁贴视图使用 32 x 32 像素的图标和若干行文本，如以下图像中所示。  
  
 ![ListView 控件中的平铺视图](./media/how-to-enable-tile-view-in-a-windows-forms-listview-control/tile-view-in-listview-control.gif "磁贴视图图标和文本")  

 若要启用磁贴视图，请将 <xref:System.Windows.Forms.ListView.View%2A> 属性设置为 <xref:System.Windows.Forms.View.Tile>。 可以通过设置 <xref:System.Windows.Forms.ListView.TileSize%2A> 属性来调整平铺大小，并通过调整 <xref:System.Windows.Forms.ListView.Columns%2A> 集合，来调整磁贴中显示的文本行数。  
  
### <a name="to-set-tile-view-programmatically"></a>若要以编程方式设置磁贴视图  
  
1. 使用 <xref:System.Windows.Forms.ListView> 控件的 <xref:System.Windows.Forms.View> 枚举。  
  
    ```vb  
    ListView1.View = View.Tile  
    ```  
  
    ```csharp  
    listView1.View = View.Tile;  
    ```  
  
## <a name="example"></a>示例  
 以下完整的代码示例演示了修改磁贴以显示三行文本的磁贴视图。 已经调整了磁贴大小，以防止自动换行。  
  
 [!code-cpp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CPP/listviewtilingexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CS/listviewtilingexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/VB/listviewtilingexample.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System 和 System.Windows.Forms 程序集的引用。  
  
- 在执行文件相同的目录中的一个名为 book.ico 的图标文件。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [ListView 控件](listview-control-windows-forms.md)
- [ListView 控件概述](listview-control-overview-windows-forms.md)
