---
title: 演练：在后台运行操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
ms.openlocfilehash: ad0955937965c89b52648e37cd151e0cd266e527
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972497"
---
# <a name="walkthrough-running-an-operation-in-the-background"></a>演练：在后台运行操作

如果某项操作需要很长时间才能完成，而你不希望造成用户界面的延迟，则可以使用 <xref:System.ComponentModel.BackgroundWorker> 类在另一个线程上运行此操作。

有关此示例中使用的代码的完整列表，请参阅 [如何：在后台运行操作](how-to-run-an-operation-in-the-background.md)。

## <a name="run-an-operation-in-the-background"></a>在后台运行操作

1. 在 Visual Studio 中的 Windows 窗体设计器中激活窗体后，将两个 <xref:System.Windows.Forms.Button> 控件从 **工具箱** 拖到窗体上，然后 `Name` <xref:System.Windows.Forms.Control.Text%2A> 根据下表设置这些按钮的和属性。

    |Button|名称|文本|
    |------------|----------|----------|
    |`button1`|`startBtn`|**启动**|
    |`button2`|`cancelBtn`|**取消**|

2. 打开 " **工具箱**"，单击 " **组件** " 选项卡，然后将 <xref:System.ComponentModel.BackgroundWorker> 组件拖到窗体上。

     `backgroundWorker1`组件将出现在 **组件栏** 中。

3. 在“属性”  窗口中，将 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 属性设置为 `true`。

4. 在 " **属性** " 窗口中，单击 " **事件** " 按钮，然后双击 <xref:System.ComponentModel.BackgroundWorker.DoWork> 和 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 事件创建事件处理程序。

5. 将耗时的代码插入到 <xref:System.ComponentModel.BackgroundWorker.DoWork> 事件处理程序中。

6. 从参数的属性中提取操作所需的所有参数 <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> <xref:System.ComponentModel.DoWorkEventArgs> 。

7. 将计算结果分配给 <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> 的属性 <xref:System.ComponentModel.DoWorkEventArgs> 。

     此事件处理程序将提供此功能 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 。

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]

8. 用于在事件处理程序中检索操作结果的插入代码 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 。

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]

9. 实现 `TimeConsumingOperation` 方法。

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]

10. 在 Windows 窗体设计器中，双击 `startButton` 创建 <xref:System.Windows.Forms.Control.Click> 事件处理程序。

11. <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>在的 <xref:System.Windows.Forms.Control.Click> 事件处理程序中调用方法 `startButton` 。

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]

12. 在 Windows 窗体设计器中，双击 `cancelButton` 创建 <xref:System.Windows.Forms.Control.Click> 事件处理程序。

13. <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>在的 <xref:System.Windows.Forms.Control.Click> 事件处理程序中调用方法 `cancelButton` 。

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]

14. 在该文件的顶部，导入 System.componentmodel 和 System.object 命名空间。

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]

15. 按 **F6** 生成解决方案，然后按 **Ctrl** + **F5** 在调试器外部运行该应用程序。

    > [!NOTE]
    > 如果按 **F5** 在调试器下运行该应用程序， `TimeConsumingOperation` 调试器将捕获并显示该方法中引发的异常。 当你在调试器外部运行应用程序时， <xref:System.ComponentModel.BackgroundWorker> 会处理异常并将其缓存在 <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> 的属性中 <xref:System.ComponentModel.RunWorkerCompletedEventArgs> 。

16. 单击 " **启动** " 按钮运行异步操作，然后单击 " **取消** " 按钮停止正在运行的异步操作。

     每个操作的结果显示在 <xref:System.Windows.Forms.MessageBox> 中。

## <a name="next-steps"></a>后续步骤

- 实现一个窗体，该窗体在异步操作继续时报告进度。 有关详细信息，请参阅 [如何：实现使用后台操作的窗体](how-to-implement-a-form-that-uses-a-background-operation.md)。

- 实现支持组件的异步模式的类。 有关详细信息，请参阅 [实现基于事件的异步模式](/dotnet/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern)。

## <a name="see-also"></a>另请参阅

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [如何：实现使用后台操作的窗体](how-to-implement-a-form-that-uses-a-background-operation.md)
- [如何：在后台运行操作](how-to-run-an-operation-in-the-background.md)
- [BackgroundWorker 组件](backgroundworker-component.md)
