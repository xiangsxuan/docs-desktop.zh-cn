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
# <a name="how-to-implement-validation-logic-on-custom-objects"></a><span data-ttu-id="2cf8e-102">如何：在自定义对象上实现验证逻辑</span><span class="sxs-lookup"><span data-stu-id="2cf8e-102">How to: Implement Validation Logic on Custom Objects</span></span>
<span data-ttu-id="2cf8e-103">此示例演示如何在自定义对象上实现验证逻辑，然后将其绑定到该对象。</span><span class="sxs-lookup"><span data-stu-id="2cf8e-103">This example shows how to implement validation logic on a custom object and then bind to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cf8e-104">示例</span><span class="sxs-lookup"><span data-stu-id="2cf8e-104">Example</span></span>  
 <span data-ttu-id="2cf8e-105">如果源对象实现，则可以在业务层上提供验证逻辑 <xref:System.ComponentModel.IDataErrorInfo> ，如下面的示例所示，该示例定义了一个 `Person` 实现的对象 <xref:System.ComponentModel.IDataErrorInfo> ：</span><span class="sxs-lookup"><span data-stu-id="2cf8e-105">You can provide validation logic on the business layer if your source object implements <xref:System.ComponentModel.IDataErrorInfo>, as in the following example, which defines a `Person` object that implements <xref:System.ComponentModel.IDataErrorInfo>:</span></span>  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](~/samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 <span data-ttu-id="2cf8e-106">在下面的示例中，文本框的 text 属性绑定到 `Person.Age` 属性，该属性可用于通过给定的资源声明进行绑定 `x:Key` `data` 。</span><span class="sxs-lookup"><span data-stu-id="2cf8e-106">In the following example, the text property of the text box binds to the `Person.Age` property, which has been made available for binding through a resource declaration that is given the `x:Key` `data`.</span></span> <span data-ttu-id="2cf8e-107"><xref:System.Windows.Controls.DataErrorValidationRule>检查实现所引发的验证错误 <xref:System.ComponentModel.IDataErrorInfo> 。</span><span class="sxs-lookup"><span data-stu-id="2cf8e-107">The <xref:System.Windows.Controls.DataErrorValidationRule> checks for the validation errors raised by the <xref:System.ComponentModel.IDataErrorInfo> implementation.</span></span>  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml?highlight=8,11-19,25-42)]  
  
 <span data-ttu-id="2cf8e-108">或者， <xref:System.Windows.Controls.DataErrorValidationRule> 您可以将属性设置为，而不是使用 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> `true` 。</span><span class="sxs-lookup"><span data-stu-id="2cf8e-108">Alternatively, instead of using the <xref:System.Windows.Controls.DataErrorValidationRule>, you can set the <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cf8e-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cf8e-109">See also</span></span>

- <xref:System.Windows.Controls.ExceptionValidationRule>
- [<span data-ttu-id="2cf8e-110">实现绑定验证</span><span class="sxs-lookup"><span data-stu-id="2cf8e-110">Implement Binding Validation</span></span>](how-to-implement-binding-validation.md)
- [<span data-ttu-id="2cf8e-111">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="2cf8e-111">How-to Topics</span></span>](data-binding-how-to-topics.md)
