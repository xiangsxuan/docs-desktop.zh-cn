---
title: 如何：从 Windows 窗体播放提示音
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], beep
- Windows Forms, sounds
- sounds [Windows Forms], playing
- forms [Windows Forms], sounds
- examples [Windows Forms], sounds
ms.assetid: 7ea5cded-4888-4f35-8f28-5cab1a55c973
ms.openlocfilehash: 7fecc5d5b7259b743926713f87d9303596803582
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971151"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a><span data-ttu-id="74cd1-102">如何：从 Windows 窗体播放提示音</span><span class="sxs-lookup"><span data-stu-id="74cd1-102">How to: Play a Beep from a Windows Form</span></span>
<span data-ttu-id="74cd1-103">本示例在运行时播放提示音。</span><span class="sxs-lookup"><span data-stu-id="74cd1-103">This example plays a beep at run time.</span></span>

## <a name="example"></a><span data-ttu-id="74cd1-104">示例</span><span class="sxs-lookup"><span data-stu-id="74cd1-104">Example</span></span>

```vb
Public Sub OnePing()
    Beep()
End Sub
```

```csharp
public void onePing()
{
    SystemSounds.Beep.Play();
}
```

> [!NOTE]
> <span data-ttu-id="74cd1-105">C # 代码示例中播放的声音由 <xref:System.Media.SystemSounds.Beep%2A> 系统声音设置确定。</span><span class="sxs-lookup"><span data-stu-id="74cd1-105">The sound played in the C# code sample is determined by the <xref:System.Media.SystemSounds.Beep%2A> system sound setting.</span></span> <span data-ttu-id="74cd1-106">有关详细信息，请参阅 <xref:System.Media.SystemSounds>。</span><span class="sxs-lookup"><span data-stu-id="74cd1-106">For more information, see <xref:System.Media.SystemSounds>.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="74cd1-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="74cd1-107">Compiling the Code</span></span>
 <span data-ttu-id="74cd1-108">对于 c #，此示例需要引用 <xref:System.Media?displayProperty=nameWithType> 命名空间。</span><span class="sxs-lookup"><span data-stu-id="74cd1-108">For C#, this example requires  a reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="74cd1-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74cd1-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="74cd1-110">如何：从 Windows 窗体播放系统提示音</span><span class="sxs-lookup"><span data-stu-id="74cd1-110">How to: Play a System Sound from a Windows Form</span></span>](how-to-play-a-system-sound-from-a-windows-form.md)
- [<span data-ttu-id="74cd1-111">如何：从 Windows 窗体播放声音</span><span class="sxs-lookup"><span data-stu-id="74cd1-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
