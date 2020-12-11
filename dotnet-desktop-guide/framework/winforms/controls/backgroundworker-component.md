---
title: BackgroundWorker 组件
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
ms.openlocfilehash: 6a059a9d1eaf2238f21675fec5dc0329a1c714fa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970733"
---
# <a name="backgroundworker-component"></a><span data-ttu-id="d193a-102">BackgroundWorker 组件</span><span class="sxs-lookup"><span data-stu-id="d193a-102">BackgroundWorker Component</span></span>

<span data-ttu-id="d193a-103">`BackgroundWorker`组件允许窗体或控件以异步方式运行操作。</span><span class="sxs-lookup"><span data-stu-id="d193a-103">The `BackgroundWorker` component enables your form or control to run an operation asynchronously.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d193a-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="d193a-104">In This Section</span></span>  

 [<span data-ttu-id="d193a-105">BackgroundWorker 组件概述</span><span class="sxs-lookup"><span data-stu-id="d193a-105">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="d193a-106">描述 `BackgroundWorker` 组件，该组件使你能够在与应用程序的主 UI 线程不同的线程上以异步方式 ( "在后台" ) 执行耗时操作。</span><span class="sxs-lookup"><span data-stu-id="d193a-106">Describes the `BackgroundWorker` component, which gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span>  
  
 [<span data-ttu-id="d193a-107">演练：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="d193a-107">Walkthrough: Running an Operation in the Background</span></span>](walkthrough-running-an-operation-in-the-background.md)  
 <span data-ttu-id="d193a-108">演示如何使用 `BackgroundWorker` 设计器中的组件在单独的线程上运行耗时的操作。</span><span class="sxs-lookup"><span data-stu-id="d193a-108">Demonstrates how to use the `BackgroundWorker` component in the designer to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="d193a-109">如何：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="d193a-109">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="d193a-110">演示如何使用 `BackgroundWorker` 组件在单独的线程上运行耗时的操作。</span><span class="sxs-lookup"><span data-stu-id="d193a-110">Demonstrates how to use the `BackgroundWorker` component to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="d193a-111">演练：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="d193a-111">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>](walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="d193a-112">使用设计器创建一个应用程序，该应用程序以异步方式执行数学计算。</span><span class="sxs-lookup"><span data-stu-id="d193a-112">Creates an application using the designer that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="d193a-113">如何：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="d193a-113">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="d193a-114">创建异步执行数学计算的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d193a-114">Creates an application that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="d193a-115">如何：在后台下载文件</span><span class="sxs-lookup"><span data-stu-id="d193a-115">How to: Download a File in the Background</span></span>](how-to-download-a-file-in-the-background.md)  
 <span data-ttu-id="d193a-116">演示如何使用 `BackgroundWorker` 组件在单独的线程上下载文件。</span><span class="sxs-lookup"><span data-stu-id="d193a-116">Demonstrates how to use the `BackgroundWorker` component to download a file on a separate thread.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d193a-117">参考</span><span class="sxs-lookup"><span data-stu-id="d193a-117">Reference</span></span>  

 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="d193a-118">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="d193a-118">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 <span data-ttu-id="d193a-119">介绍保存事件数据的类型 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 。</span><span class="sxs-lookup"><span data-stu-id="d193a-119">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span>  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 <span data-ttu-id="d193a-120">介绍保存事件数据的类型 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 。</span><span class="sxs-lookup"><span data-stu-id="d193a-120">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d193a-121">相关章节</span><span class="sxs-lookup"><span data-stu-id="d193a-121">Related Sections</span></span>  

 [<span data-ttu-id="d193a-122">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="d193a-122">Event-based Asynchronous Pattern Overview</span></span>](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview)  
 <span data-ttu-id="d193a-123">介绍如何在隐藏多线程设计中固有的许多复杂问题的同时，使用多线程应用程序的优点。</span><span class="sxs-lookup"><span data-stu-id="d193a-123">Describes how the asynchronous pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>
