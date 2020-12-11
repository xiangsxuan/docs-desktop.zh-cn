---
title: 值（XAttribute 动态属性）
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XAttribute.Value
apitype: Assembly
ms.openlocfilehash: 32c15a89a976b5f9af12f040c43e724a25357ead
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974038"
---
# <a name="value-xattribute-dynamic-property"></a><span data-ttu-id="79da0-102">值（XAttribute 动态属性）</span><span class="sxs-lookup"><span data-stu-id="79da0-102">Value (XAttribute dynamic property)</span></span>

<span data-ttu-id="79da0-103">获取或设置 XML 属性的值。</span><span class="sxs-lookup"><span data-stu-id="79da0-103">Gets or sets the value of the XML attribute.</span></span>

## <a name="syntax"></a><span data-ttu-id="79da0-104">语法</span><span class="sxs-lookup"><span data-stu-id="79da0-104">Syntax</span></span>

```xaml
attrib.Value
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="79da0-105">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="79da0-105">Property value/return value</span></span>

<span data-ttu-id="79da0-106">包含此属性的值的 <xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="79da0-106">A <xref:System.String> containing the value of this attribute.</span></span>

## <a name="exceptions"></a><span data-ttu-id="79da0-107">例外</span><span class="sxs-lookup"><span data-stu-id="79da0-107">Exceptions</span></span>

|<span data-ttu-id="79da0-108">例外类型</span><span class="sxs-lookup"><span data-stu-id="79da0-108">Exception type</span></span>|<span data-ttu-id="79da0-109">条件</span><span class="sxs-lookup"><span data-stu-id="79da0-109">Condition</span></span>|
| - |---------------|
|<xref:System.ArgumentNullException>|<span data-ttu-id="79da0-110">设置时，`value` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="79da0-110">When setting, the `value` is `null`.</span></span>|

## <a name="remarks"></a><span data-ttu-id="79da0-111">备注</span><span class="sxs-lookup"><span data-stu-id="79da0-111">Remarks</span></span>

<span data-ttu-id="79da0-112">此属性等效于 <xref:System.Xml.Linq.XAttribute.Value%2A> 类的 <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> 属性，但此动态属性还支持更改通知。</span><span class="sxs-lookup"><span data-stu-id="79da0-112">This property is equivalent to the <xref:System.Xml.Linq.XAttribute.Value%2A> property of the <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> class, but this dynamic property also supports change notifications.</span></span>

## <a name="see-also"></a><span data-ttu-id="79da0-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79da0-113">See also</span></span>

- <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>
- [<span data-ttu-id="79da0-114">XAttribute 类动态属性</span><span class="sxs-lookup"><span data-stu-id="79da0-114">XAttribute class dynamic properties</span></span>](value-xattribute-dynamic-property.md)
- [<span data-ttu-id="79da0-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="79da0-115">Attribute</span></span>](attribute-xelement-dynamic-property.md)