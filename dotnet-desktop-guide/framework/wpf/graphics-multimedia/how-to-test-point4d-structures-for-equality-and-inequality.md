---
title: 如何：测试 Point4D 结构是否相等和不相等
ms.date: 03/30/2017
helpviewer_keywords:
- inequality [WPF], testing Point4D structures for
- equality [WPF], testing Point4D structures for
- testing [WPF], Point4D structures for equality
- Point4D structures [WPF], testing for inequality
- testing [WPF], Point4D structures for inequality
- Point4D structures [WPF], testing for equality
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
ms.openlocfilehash: ce1188e99ef2b0682427cc2e227aaccd27f7c4f4
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972771"
---
# <a name="how-to-test-point4d-structures-for-equality-and-inequality"></a>如何：测试 Point4D 结构是否相等和不相等
此示例演示如何测试 <xref:System.Windows.Media.Media3D.Point4D> 结构是否相等和不相等。  
  
 下面的代码演示如何 <xref:System.Windows.Media.Media3D.Point4D> 使用相等方法测试结构是否相等和不相等 <xref:System.Windows.Media.Media3D.Point4D> 。  使用 <xref:System.Windows.Media.Media3D.Point4D> 重载的相等 () 运算符测试结构是否相等 `==` ，然后使用重载不等 () 运算符来表示不相等， `!=` 最后使用 <xref:System.Windows.Media.Media3D.Point3D> <xref:System.Windows.Media.Media3D.Point4D> 静态方法检查结构和结构是否相等 <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> 。  
  
## <a name="example"></a>示例  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>
