---
title: 如何：实现使用后台操作的窗体
description: 了解如何实现一个 Windows 窗体，该窗体使用后台操作，以便一个操作可以继续运行，同时另一个操作继续运行。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- background threads
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9f483f93-1613-4be1-a021-b4934e9c78f3
ms.openlocfilehash: 85a583ce81c8d7e169302dd9e3e304c22977327a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972015"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="39c34-103">如何：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="39c34-103">How to: Implement a Form That Uses a Background Operation</span></span>

<span data-ttu-id="39c34-104">以下示例程序创建一个计算 Fibonacci 数字的窗体。</span><span class="sxs-lookup"><span data-stu-id="39c34-104">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="39c34-105">计算在独立于用户界面线程的线程上运行，因此用户界面将随计算继续运行，不会延迟。</span><span class="sxs-lookup"><span data-stu-id="39c34-105">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="39c34-106">Visual Studio 中对此任务提供广泛支持。</span><span class="sxs-lookup"><span data-stu-id="39c34-106">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="39c34-107">另请参阅[演练：实现使用后台操作的窗体](walkthrough-implementing-a-form-that-uses-a-background-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="39c34-107">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="39c34-108">示例</span><span class="sxs-lookup"><span data-stu-id="39c34-108">Example</span></span>  

 [!code-cpp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="39c34-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="39c34-109">Compiling the Code</span></span>  

 <span data-ttu-id="39c34-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="39c34-110">This example requires:</span></span>  
  
- <span data-ttu-id="39c34-111">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="39c34-111">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="39c34-112">可靠编程</span><span class="sxs-lookup"><span data-stu-id="39c34-112">Robust Programming</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="39c34-113">使用任何一种多线程都可能引起极为严重和复杂的 Bug。</span><span class="sxs-lookup"><span data-stu-id="39c34-113">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="39c34-114">在实现任何使用多线程处理的解决方案之前，请参阅[托管线程处理最佳做法](/dotnet/standard/threading/managed-threading-best-practices)。</span><span class="sxs-lookup"><span data-stu-id="39c34-114">Consult the [Managed Threading Best Practices](/dotnet/standard/threading/managed-threading-best-practices) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c34-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39c34-115">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="39c34-116">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="39c34-116">Event-based Asynchronous Pattern Overview</span></span>](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview)
- [<span data-ttu-id="39c34-117">托管线程处理的最佳做法</span><span class="sxs-lookup"><span data-stu-id="39c34-117">Managed Threading Best Practices</span></span>](/dotnet/standard/threading/managed-threading-best-practices)
