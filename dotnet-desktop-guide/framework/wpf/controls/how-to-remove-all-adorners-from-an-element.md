---
title: 如何：从元素移除所有装饰器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
ms.openlocfilehash: 8504bb1ec70de188033b2b092bbb66cf9da3dc11
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974053"
---
# <a name="how-to-remove-all-adorners-from-an-element"></a>如何：从元素移除所有装饰器
此示例演示如何以编程方式从指定的中移除所有装饰器 <xref:System.Windows.UIElement> 。  
  
## <a name="example"></a>示例  
 此详细的代码示例删除由返回的装饰器数组中的所有装饰器 <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> 。  此示例将在已命名的 MyTextBox 上检索装饰器 <xref:System.Windows.UIElement> 。   如果对的调用中指定的元素 <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> 没有装饰器， `null` 则返回。  此代码显式检查 null 数组，最适用于预计空数组相对较为常见的应用程序。  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a>示例  
 此简洁的代码示例在功能上等效于上面所示的详细示例。 此代码不显式检查 null 数组，因此 <xref:System.NullReferenceException> 可能会引发异常。  此代码最适合于应极少出现空数组的应用程序。  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a>另请参阅

- [装饰器概述](adorners-overview.md)
