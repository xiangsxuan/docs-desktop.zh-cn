---
title: 如何：在后台下载文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9b7bc5ae-051c-4904-9720-18f6667388bd
ms.openlocfilehash: ed7d5593a29726412f5ea75812cf5a6d800ee77a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971182"
---
# <a name="how-to-download-a-file-in-the-background"></a>如何：在后台下载文件
下载文件是一项常见任务，在单独线程上运行这个可能很耗时的操作通常很有用。 使用 <xref:System.ComponentModel.BackgroundWorker> 组件来完成此任务，几乎不使用任何代码。  
  
## <a name="example"></a>示例  
 以下代码示例演示如何使用 <xref:System.ComponentModel.BackgroundWorker> 组件从 URL 加载 XML 文件。 当用户单击 " **下载** " 按钮时， <xref:System.Windows.Forms.Control.Click> 事件处理程序将调用 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 组件的方法 <xref:System.ComponentModel.BackgroundWorker> 来启动下载操作。 按钮在下载期间处于禁用状态，下载完毕后处于启用状态。 <xref:System.Windows.Forms.MessageBox> 显示文件的内容。  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#1)]  
  
 **下载文件**  
  
 文件被下载到 <xref:System.ComponentModel.BackgroundWorker> 组件的工作线程上，该线程运行 <xref:System.ComponentModel.BackgroundWorker.DoWork> 事件处理程序。 当代码调用 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 方法时，将启动此线程。  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#3)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#3)]  
  
 **等待 BackgroundWorker 完成**  
  
 `downloadButton_Click` 事件处理程序演示如何等待 <xref:System.ComponentModel.BackgroundWorker> 组件完成其异步任务。  
  
 在等待后台线程完成时，如果你只希望应用程序响应事件，而不希望在主线程中执行任何操作，直接退出处理程序即可。  
  
 如果想要继续在主线程中执行操作，可使用 <xref:System.ComponentModel.BackgroundWorker.IsBusy%2A> 属性来确定 <xref:System.ComponentModel.BackgroundWorker> 线程是否仍在运行。 在示例中，进度条随下载进行而更新。 请确保调用 <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> 方法以保持 UI 响应能力。  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#2)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#2)]  
  
 **显示结果**  
  
 `backgroundWorker1_RunWorkerCompleted` 方法处理 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 事件，并在后台操作完成时被调用。 此方法首先检查 <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> 属性。 如果 <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> 为 `null`，则此方法显示文件的内容。 然后它启用在下载开始后被禁用的下载按钮，并重置进度栏。  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#4)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 引用 System.Drawing、System.Windows.Forms 和 System.Xml 程序集。  
  
## <a name="robust-programming"></a>可靠编程  
 始终先检查 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 事件处理程序中的 <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> 属性，然后再尝试访问 <xref:System.ComponentModel.RunWorkerCompletedEventArgs.Result%2A?displayProperty=nameWithType> 属性或可能受 <xref:System.ComponentModel.BackgroundWorker.DoWork> 事件处理程序影响的任何其他对象。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.ComponentModel.BackgroundWorker>
- [如何：在后台运行操作](how-to-run-an-operation-in-the-background.md)
- [如何：实现使用后台操作的窗体](how-to-implement-a-form-that-uses-a-background-operation.md)
