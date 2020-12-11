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
# <a name="how-to-loop-a-sound-playing-on-a-windows-form"></a><span data-ttu-id="44b52-102">如何：在 Windows 窗体上循环播放声音</span><span class="sxs-lookup"><span data-stu-id="44b52-102">How to: Loop a Sound Playing on a Windows Form</span></span>
<span data-ttu-id="44b52-103">以下代码示例重复播放声音。</span><span class="sxs-lookup"><span data-stu-id="44b52-103">The following code example plays a sound repeatedly.</span></span> <span data-ttu-id="44b52-104">当 `stopPlayingButton_Click` 事件处理程序中的代码运行时，当前播放的所有声音都将停止。</span><span class="sxs-lookup"><span data-stu-id="44b52-104">When the code in the `stopPlayingButton_Click` event handler runs, any sound currently playing stops.</span></span> <span data-ttu-id="44b52-105">如果未播放任何声音，则无任何操作。</span><span class="sxs-lookup"><span data-stu-id="44b52-105">If no sound is playing, nothing happens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44b52-106">示例</span><span class="sxs-lookup"><span data-stu-id="44b52-106">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="44b52-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="44b52-107">Compiling the Code</span></span>  
 <span data-ttu-id="44b52-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="44b52-108">This example requires:</span></span>  
  
- <span data-ttu-id="44b52-109">对 System 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="44b52-109">References to the System and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="44b52-110">即，使用有效的文件名替换文件名 `"c:\Windows\Media\chimes.wav"`。</span><span class="sxs-lookup"><span data-stu-id="44b52-110">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="44b52-111">可靠编程</span><span class="sxs-lookup"><span data-stu-id="44b52-111">Robust Programming</span></span>  
 <span data-ttu-id="44b52-112">文件操作应包含在相应的异常处理块内。</span><span class="sxs-lookup"><span data-stu-id="44b52-112">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="44b52-113">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="44b52-113">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="44b52-114">路径名称格式不正确。</span><span class="sxs-lookup"><span data-stu-id="44b52-114">The path name is malformed.</span></span> <span data-ttu-id="44b52-115">例如，它包含无效字符或仅为空白（<xref:System.ArgumentException> 类）。</span><span class="sxs-lookup"><span data-stu-id="44b52-115">For example, it contains characters that are not valid or it is only white space (<xref:System.ArgumentException> class).</span></span>  
  
- <span data-ttu-id="44b52-116">此路径为只读路径（<xref:System.IO.IOException> 类）。</span><span class="sxs-lookup"><span data-stu-id="44b52-116">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
- <span data-ttu-id="44b52-117">此路径名为 `Nothing`（<xref:System.ArgumentNullException> 类）。</span><span class="sxs-lookup"><span data-stu-id="44b52-117">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
- <span data-ttu-id="44b52-118">此路径名过长（<xref:System.IO.PathTooLongException> 类）。</span><span class="sxs-lookup"><span data-stu-id="44b52-118">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
- <span data-ttu-id="44b52-119">路径无效（<xref:System.IO.DirectoryNotFoundException> 类）。</span><span class="sxs-lookup"><span data-stu-id="44b52-119">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
- <span data-ttu-id="44b52-120">此路径仅为冒号“:”（<xref:System.NotSupportedException> 类）。</span><span class="sxs-lookup"><span data-stu-id="44b52-120">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="44b52-121">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="44b52-121">.NET Framework Security</span></span>  
 <span data-ttu-id="44b52-122">不要根据文件的名称来判断文件的内容。</span><span class="sxs-lookup"><span data-stu-id="44b52-122">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="44b52-123">例如，文件 Form1.vb 可能不是 Visual Basic 源文件。</span><span class="sxs-lookup"><span data-stu-id="44b52-123">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="44b52-124">在应用程序中使用输入的数据之前，需验证所有的输入内容。</span><span class="sxs-lookup"><span data-stu-id="44b52-124">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44b52-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="44b52-125">See also</span></span>

- <xref:System.Media.SoundPlayer.PlayLooping%2A>
- [<span data-ttu-id="44b52-126">如何：从 Windows 窗体播放声音</span><span class="sxs-lookup"><span data-stu-id="44b52-126">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
- [<span data-ttu-id="44b52-127">SoundPlayer 类概述</span><span class="sxs-lookup"><span data-stu-id="44b52-127">SoundPlayer Class Overview</span></span>](soundplayer-class-overview.md)
