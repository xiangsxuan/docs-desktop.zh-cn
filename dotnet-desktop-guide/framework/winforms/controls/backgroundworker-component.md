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
# <a name="backgroundworker-component"></a>BackgroundWorker 组件

`BackgroundWorker`组件允许窗体或控件以异步方式运行操作。  
  
## <a name="in-this-section"></a>本节内容  

 [BackgroundWorker 组件概述](backgroundworker-component-overview.md)  
 描述 `BackgroundWorker` 组件，该组件使你能够在与应用程序的主 UI 线程不同的线程上以异步方式 ( "在后台" ) 执行耗时操作。  
  
 [演练：在后台运行操作](walkthrough-running-an-operation-in-the-background.md)  
 演示如何使用 `BackgroundWorker` 设计器中的组件在单独的线程上运行耗时的操作。  
  
 [如何：在后台运行操作](how-to-run-an-operation-in-the-background.md)  
 演示如何使用 `BackgroundWorker` 组件在单独的线程上运行耗时的操作。  
  
 [演练：实现使用后台操作的窗体](walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 使用设计器创建一个应用程序，该应用程序以异步方式执行数学计算。  
  
 [如何：实现使用后台操作的窗体](how-to-implement-a-form-that-uses-a-background-operation.md)  
 创建异步执行数学计算的应用程序。  
  
 [如何：在后台下载文件](how-to-download-a-file-in-the-background.md)  
 演示如何使用 `BackgroundWorker` 组件在单独的线程上下载文件。  
  
## <a name="reference"></a>参考  

 <xref:System.ComponentModel.BackgroundWorker>  
 对此类进行描述，并提供指向其所有成员的链接。  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 介绍保存事件数据的类型 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 。  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 介绍保存事件数据的类型 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 。  
  
## <a name="related-sections"></a>相关章节  

 [基于事件的异步模式概述](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview)  
 介绍如何在隐藏多线程设计中固有的许多复杂问题的同时，使用多线程应用程序的优点。
