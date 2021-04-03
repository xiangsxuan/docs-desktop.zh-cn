---
title: 激活函数 WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: c97069613a96009d0b9bb84e55c37b29c2d3ea5b
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970500"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="e6b07-102"> (WPF 非托管 API 引用中激活函数) </span><span class="sxs-lookup"><span data-stu-id="e6b07-102">Activate Function (WPF Unmanaged API Reference)</span></span>

<span data-ttu-id="e6b07-103">此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="e6b07-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>

<span data-ttu-id="e6b07-104">由用于 Windows 管理的 Windows Presentation Foundation (WPF) 基础结构使用。</span><span class="sxs-lookup"><span data-stu-id="e6b07-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6b07-105">语法</span><span class="sxs-lookup"><span data-stu-id="e6b07-105">Syntax</span></span>

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a><span data-ttu-id="e6b07-106">参数</span><span class="sxs-lookup"><span data-stu-id="e6b07-106">Parameters</span></span>

`pParameters`\
<span data-ttu-id="e6b07-107">指向窗口的激活参数的指针。</span><span class="sxs-lookup"><span data-stu-id="e6b07-107">A pointer to the window's activation parameters.</span></span>

`ppInner`\
<span data-ttu-id="e6b07-108">一个指针，指向包含指向对象的指针的单元素缓冲区的地址 <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> 。</span><span class="sxs-lookup"><span data-stu-id="e6b07-108">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>

## <a name="requirements"></a><span data-ttu-id="e6b07-109">要求</span><span class="sxs-lookup"><span data-stu-id="e6b07-109">Requirements</span></span>

<span data-ttu-id="e6b07-110">**平台：** 请参阅 [.NET Framework 系统要求](/dotnet/framework/get-started/system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="e6b07-110">**Platforms:** See [.NET Framework System Requirements](/dotnet/framework/get-started/system-requirements).</span></span>

<span data-ttu-id="e6b07-111">**.DLL**</span><span class="sxs-lookup"><span data-stu-id="e6b07-111">**DLL:**</span></span>

<span data-ttu-id="e6b07-112">在 .NET Framework 3.0 和3.5： PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="e6b07-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>

<span data-ttu-id="e6b07-113">在 .NET Framework 4 及更高版本中： PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="e6b07-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>

<span data-ttu-id="e6b07-114">**.NET Framework 版本：**[!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6b07-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e6b07-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6b07-115">See also</span></span>

- [<span data-ttu-id="e6b07-116">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="e6b07-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
