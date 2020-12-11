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
# <a name="how-to-play-a-beep-from-a-windows-form"></a>如何：从 Windows 窗体播放提示音
本示例在运行时播放提示音。

## <a name="example"></a>示例

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
> C # 代码示例中播放的声音由 <xref:System.Media.SystemSounds.Beep%2A> 系统声音设置确定。 有关详细信息，请参阅 <xref:System.Media.SystemSounds>。

## <a name="compiling-the-code"></a>编译代码
 对于 c #，此示例需要引用 <xref:System.Media?displayProperty=nameWithType> 命名空间。

## <a name="see-also"></a>另请参阅

- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [如何：从 Windows 窗体播放系统提示音](how-to-play-a-system-sound-from-a-windows-form.md)
- [如何：从 Windows 窗体播放声音](how-to-play-a-sound-from-a-windows-form.md)
