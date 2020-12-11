---
title: 控件中的多线程处理
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 79832e12a10f02c909d2a28270594bcb4ea68656
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971079"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="d56c3-102">Windows 窗体控件中的多线程处理</span><span class="sxs-lookup"><span data-stu-id="d56c3-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="d56c3-103">在许多应用程序中，你可以通过在另一个线程上执行耗时的操作，使用户界面 (UI) 更快地响应。</span><span class="sxs-lookup"><span data-stu-id="d56c3-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="d56c3-104">许多工具可用于多线程处理 Windows 窗体控件，包括 <xref:System.Threading> 命名空间、 <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> 方法和 `BackgroundWorker` 组件。</span><span class="sxs-lookup"><span data-stu-id="d56c3-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d56c3-105">`BackgroundWorker`组件替换 <xref:System.Threading> 命名空间和方法并向其添加功能 <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> ; 但是，如果选择，这些功能将保留以实现向后兼容性和将来使用。</span><span class="sxs-lookup"><span data-stu-id="d56c3-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="d56c3-106">有关详细信息，请参阅 [BackgroundWorker 组件概述](backgroundworker-component-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d56c3-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d56c3-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="d56c3-107">In This Section</span></span>  
 [<span data-ttu-id="d56c3-108">如何：对 Windows 窗体控件进行线程安全的调用</span><span class="sxs-lookup"><span data-stu-id="d56c3-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="d56c3-109">演示如何对 Windows 窗体控件进行线程安全的调用。</span><span class="sxs-lookup"><span data-stu-id="d56c3-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="d56c3-110">如何：使用后台线程搜索文件</span><span class="sxs-lookup"><span data-stu-id="d56c3-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="d56c3-111">演示如何使用 <xref:System.Threading> 命名空间和 <xref:System.Windows.Forms.Control.BeginInvoke%2A> 方法以异步方式搜索文件。</span><span class="sxs-lookup"><span data-stu-id="d56c3-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d56c3-112">参考</span><span class="sxs-lookup"><span data-stu-id="d56c3-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="d56c3-113">记录一个组件，该组件封装用于异步操作的工作线程。</span><span class="sxs-lookup"><span data-stu-id="d56c3-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="d56c3-114">记录如何以异步方式加载声音。</span><span class="sxs-lookup"><span data-stu-id="d56c3-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="d56c3-115">记录如何以异步方式加载图像。</span><span class="sxs-lookup"><span data-stu-id="d56c3-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d56c3-116">相关章节</span><span class="sxs-lookup"><span data-stu-id="d56c3-116">Related Sections</span></span>  
 [<span data-ttu-id="d56c3-117">如何：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="d56c3-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="d56c3-118">演示如何使用组件执行耗时的操作 <xref:System.ComponentModel.BackgroundWorker> 。</span><span class="sxs-lookup"><span data-stu-id="d56c3-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="d56c3-119">BackgroundWorker 组件概述</span><span class="sxs-lookup"><span data-stu-id="d56c3-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="d56c3-120">提供一些主题，这些主题介绍如何将 <xref:System.ComponentModel.BackgroundWorker> 组件用于异步操作。</span><span class="sxs-lookup"><span data-stu-id="d56c3-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
