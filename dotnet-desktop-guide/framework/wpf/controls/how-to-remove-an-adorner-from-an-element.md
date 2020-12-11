---
title: 如何：从元素移除装饰器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: 256dd6fa0117f88aec2ef6b60c6dcd4c33b57855
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972939"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a>如何：从元素移除装饰器
此示例演示如何以编程方式从指定的中删除特定的装饰器 <xref:System.Windows.UIElement> 。  
  
## <a name="example"></a>示例  
 此详细的代码示例删除由返回的装饰器数组中的第一个装饰器 <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> 。  此示例将在已命名的 MyTextBox 上检索装饰器 <xref:System.Windows.UIElement> 。   如果对的调用中指定的元素 <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> 没有装饰器， `null` 则返回。  此代码显式检查 null 数组，最适用于预计空数组相对较为常见的应用程序。  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a>示例  
 此简洁的代码示例在功能上等效于上面所示的详细示例。 此代码不显式检查 null 数组，因此 <xref:System.NullReferenceException> 可能会引发异常。  此代码最适合于应极少出现空数组的应用程序。  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a>另请参阅

- [装饰器概述](adorners-overview.md)
