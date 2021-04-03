---
title: 元素（XElement 动态属性）
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Elements
apitype: Assembly
ms.openlocfilehash: 812adabd3bfb01fd9313ce3f35e6cb0a5e23344e
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970404"
---
# <a name="elements-xelement-dynamic-property"></a><span data-ttu-id="4ab7a-102">元素（XElement 动态属性）</span><span class="sxs-lookup"><span data-stu-id="4ab7a-102">Elements (XElement dynamic property)</span></span>

<span data-ttu-id="4ab7a-103">获取一个索引器，用于检索与指定扩展名匹配的当前元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="4ab7a-103">Gets an indexer used to retrieve the child elements of the current element that match the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="4ab7a-104">语法</span><span class="sxs-lookup"><span data-stu-id="4ab7a-104">Syntax</span></span>

```xaml
elem.Elements[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="4ab7a-105">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="4ab7a-105">Property value/return value</span></span>

<span data-ttu-id="4ab7a-106">一个类型为 `IEnumerable<XElement> Item(String expandedName)` 的索引器。</span><span class="sxs-lookup"><span data-stu-id="4ab7a-106">An indexer of the type `IEnumerable<XElement> Item(String expandedName)`.</span></span> <span data-ttu-id="4ab7a-107">此索引器获取所需子元素的扩展名，并返回 <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` 集合中的匹配子元素。</span><span class="sxs-lookup"><span data-stu-id="4ab7a-107">This indexer takes the expanded name of the desired child elements and returns the matching child elements in an <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="4ab7a-108">注解</span><span class="sxs-lookup"><span data-stu-id="4ab7a-108">Remarks</span></span>

<span data-ttu-id="4ab7a-109">此属性等效于 <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> 类的 <xref:System.Xml.Linq.XContainer> 方法。</span><span class="sxs-lookup"><span data-stu-id="4ab7a-109">This property is equivalent to the <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> method of the <xref:System.Xml.Linq.XContainer> class.</span></span>

<span data-ttu-id="4ab7a-110">返回集合中的元素按 XML 源文档顺序排列。</span><span class="sxs-lookup"><span data-stu-id="4ab7a-110">The elements in the returned collection are in XML source document order.</span></span>

<span data-ttu-id="4ab7a-111">此属性使用延迟执行。</span><span class="sxs-lookup"><span data-stu-id="4ab7a-111">This property uses deferred execution.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ab7a-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ab7a-112">See also</span></span>

- [<span data-ttu-id="4ab7a-113">XElement 类动态属性</span><span class="sxs-lookup"><span data-stu-id="4ab7a-113">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="4ab7a-114">元素</span><span class="sxs-lookup"><span data-stu-id="4ab7a-114">Element</span></span>](element-xelement-dynamic-property.md)
- [<span data-ttu-id="4ab7a-115">子代</span><span class="sxs-lookup"><span data-stu-id="4ab7a-115">Descendants</span></span>](descendants-xelement-dynamic-property.md)
