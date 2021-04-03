---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: 5249d7ea359db5d5c58ae87600f61048b465b4c1
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973887"
---
# <a name="ienumrawinputdevice"></a><span data-ttu-id="7347e-102">IEnumRAWINPUTDEVICE</span><span class="sxs-lookup"><span data-stu-id="7347e-102">IEnumRAWINPUTDEVICE</span></span>
<span data-ttu-id="7347e-103">此接口枚举原始输入设备，并仅供 PresentationHost.exe 使用。</span><span class="sxs-lookup"><span data-stu-id="7347e-103">This interface enumerates the raw input devices, and is only used by PresentationHost.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7347e-104">此 API 预期仅支持在本地客户端计算机上使用</span><span class="sxs-lookup"><span data-stu-id="7347e-104">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="7347e-105">成员</span><span class="sxs-lookup"><span data-stu-id="7347e-105">Members</span></span>  
  
|<span data-ttu-id="7347e-106">成员</span><span class="sxs-lookup"><span data-stu-id="7347e-106">Member</span></span>|<span data-ttu-id="7347e-107">说明</span><span class="sxs-lookup"><span data-stu-id="7347e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7347e-108">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="7347e-108">IEnumRAWINPUTDEVIC:Next</span></span>](ienumrawinputdevic-next.md)|<span data-ttu-id="7347e-109">在枚举器列表中枚举下一个 `celt` 元素（即 RAWINPUTDEVICE 结构），将它们和 `rgelt` 中枚举元素的实际数量返回至 `pceltFetched`。</span><span class="sxs-lookup"><span data-stu-id="7347e-109">Enumerates the next `celt` elements (that is, RAWINPUTDEVICE structures) in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>|  
|[<span data-ttu-id="7347e-110">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="7347e-110">IEnumRAWINPUTDEVIC:Skip</span></span>](ienumrawinputdevic-skip.md)|<span data-ttu-id="7347e-111">指示枚举器跳过枚举中的下一个 `celt` 元素，以便对 [IEnumRAWINPUTDEVIC： next](ienumrawinputdevic-next.md) 的下一次调用将不返回这些元素。</span><span class="sxs-lookup"><span data-stu-id="7347e-111">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>|  
|[<span data-ttu-id="7347e-112">IEnumRAWINPUTDEVIC:Reset</span><span class="sxs-lookup"><span data-stu-id="7347e-112">IEnumRAWINPUTDEVIC:Reset</span></span>](ienumrawinputdevic-reset.md)|<span data-ttu-id="7347e-113">将枚举序列重置到开头。</span><span class="sxs-lookup"><span data-stu-id="7347e-113">Resets the enumeration sequence to the beginning.</span></span>|  
|[<span data-ttu-id="7347e-114">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="7347e-114">IEnumRAWINPUTDEVIC:Clone</span></span>](ienumrawinputdevic-clone.md)|<span data-ttu-id="7347e-115">创建一个与当权枚举器相同状态的原始输入设备枚举器，以循环访问相同的列表。</span><span class="sxs-lookup"><span data-stu-id="7347e-115">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7347e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7347e-116">See also</span></span>

- [<span data-ttu-id="7347e-117">关于原始输入</span><span class="sxs-lookup"><span data-stu-id="7347e-117">About Raw Input</span></span>](/windows/desktop/inputdev/about-raw-input)
