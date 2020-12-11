---
title: 如何：从 Windows 窗体播放系统提示音
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing for system events
- playing sounds [Windows Forms], Windows Forms
- system sounds [Windows Forms], playing from Windows Forms
- playing sounds [Windows Forms], system
- SoundPlayer class [Windows Forms], system sounds
- sounds [Windows Forms], playing
- examples [Windows Forms], sounds
ms.assetid: afb206ff-4824-4804-a8d4-185bf5ad8e7c
ms.openlocfilehash: 765021875767a754e62e3ec11e56487e4de91e93
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970552"
---
# <a name="how-to-play-a-system-sound-from-a-windows-form"></a><span data-ttu-id="cedb4-102">如何：从 Windows 窗体播放系统提示音</span><span class="sxs-lookup"><span data-stu-id="cedb4-102">How to: Play a System Sound from a Windows Form</span></span>
<span data-ttu-id="cedb4-103">下面的代码示例在运行时播放 `Exclamation` 系统声音。</span><span class="sxs-lookup"><span data-stu-id="cedb4-103">The following code example plays the `Exclamation` system sound at run time.</span></span> <span data-ttu-id="cedb4-104">有关系统声音的详细信息，请参阅 <xref:System.Media.SystemSounds> 。</span><span class="sxs-lookup"><span data-stu-id="cedb4-104">For more information about system sounds, see <xref:System.Media.SystemSounds>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cedb4-105">示例</span><span class="sxs-lookup"><span data-stu-id="cedb4-105">Example</span></span>  
  
```vb  
Public Sub PlayExclamation()  
    SystemSounds.Exclamation.Play()  
End Sub  
```  
  
```csharp  
public void playExclamation()  
{  
    SystemSounds.Exclamation.Play();  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cedb4-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="cedb4-106">Compiling the Code</span></span>  
 <span data-ttu-id="cedb4-107">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="cedb4-107">This example requires:</span></span>  
  
- <span data-ttu-id="cedb4-108">对 <xref:System.Media?displayProperty=nameWithType> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="cedb4-108">A reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cedb4-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cedb4-109">See also</span></span>

- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
- [<span data-ttu-id="cedb4-110">如何：从 Windows 窗体播放提示音</span><span class="sxs-lookup"><span data-stu-id="cedb4-110">How to: Play a Beep from a Windows Form</span></span>](how-to-play-a-beep-from-a-windows-form.md)
- [<span data-ttu-id="cedb4-111">如何：从 Windows 窗体播放声音</span><span class="sxs-lookup"><span data-stu-id="cedb4-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
