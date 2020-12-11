---
title: 表单继承
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: d016eb52802a729ef3b41a1140cae3d64022d403
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971442"
---
# <a name="how-to-inherit-windows-forms"></a><span data-ttu-id="443f9-102">如何：继承 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="443f9-102">How to: Inherit Windows Forms</span></span>

<span data-ttu-id="443f9-103">通过从基窗体继承创建新的 Windows 窗体是事半功倍的便捷途径，而每次需要用它时，都无需完全重新创建窗体。</span><span class="sxs-lookup"><span data-stu-id="443f9-103">Creating new Windows Forms by inheriting from base forms is a handy way to duplicate your best efforts without going through the process of entirely recreating a form every time you require it.</span></span>

<span data-ttu-id="443f9-104">若要深入了解如何使用“继承选择器”对话框在设计时继承窗体以及如何直观地区分继承控件的安全级别，请参阅[如何：使用“继承选择器”对话框继承窗体](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md)。</span><span class="sxs-lookup"><span data-stu-id="443f9-104">For more information about inheriting forms at design time using the **Inheritance Picker** dialog box and how to visually distinguish between security levels of inherited controls, see [How to: Inherit Forms Using the Inheritance Picker Dialog Box](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span></span>

> [!NOTE]
> <span data-ttu-id="443f9-105">为了从窗体继承，包含该窗体的文件或命名空间必须已内置到可执行文件或 DLL 中。</span><span class="sxs-lookup"><span data-stu-id="443f9-105">In order to inherit from a form, the file or namespace containing that form must have been built into an executable file or DLL.</span></span> <span data-ttu-id="443f9-106">若要生成项目，请从“生成”菜单选择“生成”。</span><span class="sxs-lookup"><span data-stu-id="443f9-106">To build the project, choose **Build** from the **Build** menu.</span></span> <span data-ttu-id="443f9-107">此外，对命名空间的引用必须添加到继承窗体的类。</span><span class="sxs-lookup"><span data-stu-id="443f9-107">Also, a reference to the namespace must be added to the class inheriting the form.</span></span>

## <a name="inherit-a-form-programmatically"></a><span data-ttu-id="443f9-108">以编程方式继承窗体</span><span class="sxs-lookup"><span data-stu-id="443f9-108">Inherit a form programmatically</span></span>

1. <span data-ttu-id="443f9-109">在类中，添加对命名空间的引用，该命名空间包含想要被继承的窗体。</span><span class="sxs-lookup"><span data-stu-id="443f9-109">In your class, add a reference to the namespace containing the form you wish to inherit from.</span></span>

2. <span data-ttu-id="443f9-110">在类定义中，将引用添加到将被继承的窗体。</span><span class="sxs-lookup"><span data-stu-id="443f9-110">In the class definition, add a reference to the form to inherit from.</span></span> <span data-ttu-id="443f9-111">引用应包括包含窗体的命名空间，后跟一个句点，然后是基本窗体本身的名称。</span><span class="sxs-lookup"><span data-stu-id="443f9-111">The reference should include the namespace that contains the form, followed by a period, then the name of the base form itself.</span></span>

    ```vb
    Public Class Form2
        Inherits Namespace1.Form1
    ```

    ```csharp
    public class Form2 : Namespace1.Form1
    ```

 <span data-ttu-id="443f9-112">当继承窗体时，请记住，由于每个事件是由基类和继承类一起进行处理的，所以事件处理程序被调用两次时可能会出现问题。</span><span class="sxs-lookup"><span data-stu-id="443f9-112">When inheriting forms, keep in mind that issues may arise with regard to event handlers being called twice, because each event is being handled by both the base class and the inherited class.</span></span> <span data-ttu-id="443f9-113">若要深入了解如何避免此问题，请参阅[有关 Visual Basic 中继承的事件处理程序的疑难解答](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers)。</span><span class="sxs-lookup"><span data-stu-id="443f9-113">For more information on how to avoid this problem, see [Troubleshooting Inherited Event Handlers in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers).</span></span>

## <a name="see-also"></a><span data-ttu-id="443f9-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="443f9-114">See also</span></span>

- [<span data-ttu-id="443f9-115">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="443f9-115">Inherits Statement</span></span>](/dotnet/visual-basic/language-reference/statements/inherits-statement)
- [<span data-ttu-id="443f9-116">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="443f9-116">Imports Statement (.NET Namespace and Type)</span></span>](/dotnet/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type)
- [<span data-ttu-id="443f9-117">using</span><span class="sxs-lookup"><span data-stu-id="443f9-117">using</span></span>](/dotnet/csharp/language-reference/keywords/using)
- [<span data-ttu-id="443f9-118">修改基窗体的外观的效果</span><span class="sxs-lookup"><span data-stu-id="443f9-118">Effects of Modifying a Base Form's Appearance</span></span>](effects-of-modifying-base-form-appearance.md)
- [<span data-ttu-id="443f9-119">Windows 窗体可视化继承</span><span class="sxs-lookup"><span data-stu-id="443f9-119">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
