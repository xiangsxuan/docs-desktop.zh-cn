---
title: 如何：在 Windows 窗体上循环播放声音
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sound loops
- SoundPlayer class [Windows Forms], play looping
- sounds [Windows Forms], looping
- playing sounds [Windows Forms], looping
ms.assetid: ea95dd46-10a3-46c0-8263-4b205f00df7f
ms.openlocfilehash: e14d9de2326234b86c1f24b227e86f822fbfdb71
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972572"
---
# <a name="how-to-loop-a-sound-playing-on-a-windows-form"></a>如何：在 Windows 窗体上循环播放声音
以下代码示例重复播放声音。 当 `stopPlayingButton_Click` 事件处理程序中的代码运行时，当前播放的所有声音都将停止。 如果未播放任何声音，则无任何操作。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System 和 System.Windows.Forms 程序集的引用。  
  
- 即，使用有效的文件名替换文件名 `"c:\Windows\Media\chimes.wav"`。  
  
## <a name="robust-programming"></a>可靠编程  
 文件操作应包含在相应的异常处理块内。  
  
 以下情况可能会导致异常：  
  
- 路径名称格式不正确。 例如，它包含无效字符或仅为空白（<xref:System.ArgumentException> 类）。  
  
- 此路径为只读路径（<xref:System.IO.IOException> 类）。  
  
- 此路径名为 `Nothing`（<xref:System.ArgumentNullException> 类）。  
  
- 此路径名过长（<xref:System.IO.PathTooLongException> 类）。  
  
- 路径无效（<xref:System.IO.DirectoryNotFoundException> 类）。  
  
- 此路径仅为冒号“:”（<xref:System.NotSupportedException> 类）。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 不要根据文件的名称来判断文件的内容。 例如，文件 Form1.vb 可能不是 Visual Basic 源文件。 在应用程序中使用输入的数据之前，需验证所有的输入内容。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Media.SoundPlayer.PlayLooping%2A>
- [如何：从 Windows 窗体播放声音](how-to-play-a-sound-from-a-windows-form.md)
- [SoundPlayer 类概述](soundplayer-class-overview.md)
