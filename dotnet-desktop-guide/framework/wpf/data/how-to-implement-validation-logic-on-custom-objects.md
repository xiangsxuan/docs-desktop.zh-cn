---
title: 如何：在自定义对象上实现验证逻辑
ms.date: 08/02/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
ms.openlocfilehash: 8520504757e9e9ec9557b84ca2608b4cb99daf62
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973701"
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a>如何：在自定义对象上实现验证逻辑
此示例演示如何在自定义对象上实现验证逻辑，然后将其绑定到该对象。  
  
## <a name="example"></a>示例  
 如果源对象实现，则可以在业务层上提供验证逻辑 <xref:System.ComponentModel.IDataErrorInfo> ，如下面的示例所示，该示例定义了一个 `Person` 实现的对象 <xref:System.ComponentModel.IDataErrorInfo> ：  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](~/samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 在下面的示例中，文本框的 text 属性绑定到 `Person.Age` 属性，该属性可用于通过给定的资源声明进行绑定 `x:Key` `data` 。 <xref:System.Windows.Controls.DataErrorValidationRule>检查实现所引发的验证错误 <xref:System.ComponentModel.IDataErrorInfo> 。  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml?highlight=8,11-19,25-42)]  
  
 或者， <xref:System.Windows.Controls.DataErrorValidationRule> 您可以将属性设置为，而不是使用 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> `true` 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.ExceptionValidationRule>
- [实现绑定验证](how-to-implement-binding-validation.md)
- [操作指南主题](data-binding-how-to-topics.md)
