---
title: 如何：在 Windows 窗体内异步加载声音
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SoundPlayer class [Windows Forms], loading sounds asynchronously
- sounds [Windows Forms], loading on separate threads
- threading [Windows Forms], sounds
ms.assetid: 3b6a9296-1d5e-4d52-a4ba-94366d6fe302
ms.openlocfilehash: 5f533d82fcca07a2b64bdbbfb160a7b2a23ce540
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972509"
---
# <a name="how-to-load-a-sound-asynchronously-within-a-windows-form"></a><span data-ttu-id="acfd7-102">如何：在 Windows 窗体内异步加载声音</span><span class="sxs-lookup"><span data-stu-id="acfd7-102">How to: Load a Sound Asynchronously within a Windows Form</span></span>
<span data-ttu-id="acfd7-103">以下代码示例从 URL 异步上载了一个声音，然后在新线程中播放。</span><span class="sxs-lookup"><span data-stu-id="acfd7-103">The following code example asynchronously loads a sound from an URL and then plays it on a new thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acfd7-104">示例</span><span class="sxs-lookup"><span data-stu-id="acfd7-104">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.LoadAsync#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.LoadAsync#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="acfd7-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="acfd7-105">Compiling the Code</span></span>  
 <span data-ttu-id="acfd7-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="acfd7-106">This example requires:</span></span>  
  
- <span data-ttu-id="acfd7-107">对 System 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="acfd7-107">References to the System and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="acfd7-108">即，使用有效的文件名替换文件名 `"http://www.tailspintoys.com/sounds/stop.wav"`。</span><span class="sxs-lookup"><span data-stu-id="acfd7-108">That you replace the file name `"http://www.tailspintoys.com/sounds/stop.wav"` with a valid file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="acfd7-109">可靠编程</span><span class="sxs-lookup"><span data-stu-id="acfd7-109">Robust Programming</span></span>  
 <span data-ttu-id="acfd7-110">文件操作应包含在相应的异常处理块内。</span><span class="sxs-lookup"><span data-stu-id="acfd7-110">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="acfd7-111">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="acfd7-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="acfd7-112">路径名称格式不正确。</span><span class="sxs-lookup"><span data-stu-id="acfd7-112">The path name is malformed.</span></span> <span data-ttu-id="acfd7-113">例如，路径名称包含无效的字符或它仅为空白（<xref:System.ArgumentException> 类）。</span><span class="sxs-lookup"><span data-stu-id="acfd7-113">For example, it contains characters that are not valid or is only white space (<xref:System.ArgumentException> class).</span></span>  
  
- <span data-ttu-id="acfd7-114">此路径为只读路径（<xref:System.IO.IOException> 类）。</span><span class="sxs-lookup"><span data-stu-id="acfd7-114">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
- <span data-ttu-id="acfd7-115">此路径名为 `Nothing`（<xref:System.ArgumentNullException> 类）。</span><span class="sxs-lookup"><span data-stu-id="acfd7-115">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
- <span data-ttu-id="acfd7-116">此路径名过长（<xref:System.IO.PathTooLongException> 类）。</span><span class="sxs-lookup"><span data-stu-id="acfd7-116">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
- <span data-ttu-id="acfd7-117">此路径无效（<xref:System.IO.DirectoryNotFoundException> 类）。</span><span class="sxs-lookup"><span data-stu-id="acfd7-117">The path is not valid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
- <span data-ttu-id="acfd7-118">此路径仅为冒号“:”（<xref:System.NotSupportedException> 类）。</span><span class="sxs-lookup"><span data-stu-id="acfd7-118">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="acfd7-119">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="acfd7-119">.NET Framework Security</span></span>  
 <span data-ttu-id="acfd7-120">不要根据文件的名称来判断文件的内容。</span><span class="sxs-lookup"><span data-stu-id="acfd7-120">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="acfd7-121">例如，文件 `Form1.vb` 可能不是 Visual Basic 源文件。</span><span class="sxs-lookup"><span data-stu-id="acfd7-121">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="acfd7-122">在应用程序中使用输入的数据之前，需验证所有的输入内容。</span><span class="sxs-lookup"><span data-stu-id="acfd7-122">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acfd7-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="acfd7-123">See also</span></span>

- <xref:System.Media.SoundPlayer.LoadAsync%2A>
- <xref:System.Media.SoundPlayer.LoadCompleted>
- <xref:System.Media.SoundPlayer.Play%2A>
- [<span data-ttu-id="acfd7-124">如何：从 Windows 窗体播放声音</span><span class="sxs-lookup"><span data-stu-id="acfd7-124">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
