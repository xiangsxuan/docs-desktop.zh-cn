---
title: BackgroundWorker 组件概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- BackgroundWorker
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 64e9b3ab-7443-4a77-ab17-b8b8c0cb3f62
ms.openlocfilehash: ba197331863b1b6dd49fbb26249bfd4a46106e34
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971322"
---
# <a name="backgroundworker-component-overview"></a>BackgroundWorker 组件概述

许多经常执行的操作可能需要很长的执行时间。 例如：  
  
- 图像下载  
  
- Web 服务调用  
  
- 文件下载和上载（包括点对点应用程序）  
  
- 复杂的本地计算  
  
- 数据库事务  
  
- 本地磁盘访问（相对于内存访问来说其速度很慢）  
  
 此类操作可能导致用户界面在运行时被阻止。 如果你需要能进行响应的 UI，而且面临与这类操作相关的长时间延迟，<xref:System.ComponentModel.BackgroundWorker> 组件可以提供一种方便的解决方案。  
  
 使用 <xref:System.ComponentModel.BackgroundWorker> 组件，你可以在不同于应用程序的主 UI 线程的另一线程上异步（“在后台”）执行耗时的操作。 若要使用 <xref:System.ComponentModel.BackgroundWorker>，只需要告诉该组件要在后台执行的耗时的辅助方法，然后调用 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 方法。 在辅助方法以异步方式运行的同时，你的调用线程将继续正常运行。 该方法运行完毕后，<xref:System.ComponentModel.BackgroundWorker> 通过引发 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 事件（可选择包含操作结果）可向调用线程发出警报。  
  
 <xref:System.ComponentModel.BackgroundWorker>组件可从 **工具箱** 的 "**组件**" 选项卡中获取。若要将添加 <xref:System.ComponentModel.BackgroundWorker> 到窗体，请将 <xref:System.ComponentModel.BackgroundWorker> 组件拖到窗体上。 它将显示在组件栏中，其属性将显示在 " **属性** " 窗口中。  
  
 若要启动异步操作，请使用 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 方法。 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 采用一个可选 `object` 参数，该参数可用于将变量传递给辅助方法。 <xref:System.ComponentModel.BackgroundWorker> 类公开 <xref:System.ComponentModel.BackgroundWorker.DoWork> 事件，你的辅助线程通过 <xref:System.ComponentModel.BackgroundWorker.DoWork> 事件处理程序附加到该事件。  
  
 <xref:System.ComponentModel.BackgroundWorker.DoWork> 事件处理程序采用一个 <xref:System.ComponentModel.DoWorkEventArgs> 参数，该参数具有 <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> 属性。 此属性接收来自 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 的参数，并可以传递给 <xref:System.ComponentModel.BackgroundWorker.DoWork> 事件处理程序中调用的辅助方法。 以下示例显示了如何分配名为 `ComputeFibonacci` 的辅助方法的结果。 它是一个更大示例的一部分，你可以在 [如何：实现使用后台操作的窗体](how-to-implement-a-form-that-uses-a-background-operation.md)中找到该示例。  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 有关使用事件处理程序的详细信息，请参阅 [事件](/dotnet/standard/events/index)。  
  
> [!CAUTION]
> 使用任何一种多线程都可能引起极为严重和复杂的 Bug。 在实现任何使用多线程处理的解决方案之前，请参阅[托管线程处理最佳做法](/dotnet/standard/threading/managed-threading-best-practices)。  
  
 有关使用类的详细信息 <xref:System.ComponentModel.BackgroundWorker> ，请参阅 [如何：在后台运行操作](how-to-run-an-operation-in-the-background.md)。  
  
## <a name="see-also"></a>另请参阅

- [托管线程](/dotnet/standard/threading/index)
- [基于事件的异步模式概述](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview)
- [如何：实现使用后台操作的窗体](how-to-implement-a-form-that-uses-a-background-operation.md)
