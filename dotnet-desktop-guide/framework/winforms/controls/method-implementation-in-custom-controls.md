---
title: 自定义控件中的方法实现
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], method implementation
- custom controls [Windows Forms], overloading methods
- custom controls [Windows Forms], method implementation
- methods [Windows Forms]
- methods [Windows Forms], custom controls
ms.assetid: 35d14fca-4bb4-4a27-8211-1f7a98ea27de
ms.openlocfilehash: 8541e38f3ccdf45a41c806e2d3d69ff1e8210daf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971081"
---
# <a name="method-implementation-in-custom-controls"></a><span data-ttu-id="b7157-102">自定义控件中的方法实现</span><span class="sxs-lookup"><span data-stu-id="b7157-102">Method Implementation in Custom Controls</span></span>

<span data-ttu-id="b7157-103">控件中方法的实现与任何其他组件中方法的实现方式相同。</span><span class="sxs-lookup"><span data-stu-id="b7157-103">A method is implemented in a control in the same manner a method would be implemented in any other component.</span></span>  
  
 <span data-ttu-id="b7157-104">在 Visual Basic 中，如果要求方法返回一个值，则方法以 `Public Function` 形式实现。</span><span class="sxs-lookup"><span data-stu-id="b7157-104">In Visual Basic, if a method is required to return a value, it is implemented as a `Public Function`.</span></span> <span data-ttu-id="b7157-105">如果不返回值，则方法以 `Public Sub` 形式实现。</span><span class="sxs-lookup"><span data-stu-id="b7157-105">If no value is returned, it is implemented as a `Public Sub`.</span></span> <span data-ttu-id="b7157-106">使用以下语法声明方法：</span><span class="sxs-lookup"><span data-stu-id="b7157-106">Methods are declared using the following syntax:</span></span>  
  
```vb  
Public Function ConvertMatterToEnergy(Matter as Integer) As Integer  
   ' Conversion code goes here.  
End Function  
```  
  
 <span data-ttu-id="b7157-107">由于函数返回一个值，所以这些数必须指定返回类型（例如整型、字符串型、对象等等）。</span><span class="sxs-lookup"><span data-stu-id="b7157-107">Because functions return a value, they must specify a return type, such as integer, string, object, and so on.</span></span> <span data-ttu-id="b7157-108">可能的话，还须指定 `Function` 或 `Sub` 过程所使用的参数。</span><span class="sxs-lookup"><span data-stu-id="b7157-108">The arguments `Function` or `Sub` procedures take, if any, must also be specified.</span></span>  
  
 <span data-ttu-id="b7157-109">C# 与 Visual Basic 一样，不区分函数和过程。</span><span class="sxs-lookup"><span data-stu-id="b7157-109">C# makes no distinction between functions and procedures, as Visual Basic does.</span></span> <span data-ttu-id="b7157-110">方法返回值或返回 `void`。</span><span class="sxs-lookup"><span data-stu-id="b7157-110">A method either returns a value or returns `void`.</span></span> <span data-ttu-id="b7157-111">声明 C# 公共方法的语法是：</span><span class="sxs-lookup"><span data-stu-id="b7157-111">The syntax for declaring a C# public method is:</span></span>  
  
```csharp  
public int ConvertMatterToEnergy(int matter)  
{  
   // Conversion code goes here.  
}  
```  
  
 <span data-ttu-id="b7157-112">在声明方法时，应尽可能将它的所有参数都声明为显式数据类型。</span><span class="sxs-lookup"><span data-stu-id="b7157-112">When you declare a method, declare all of its arguments as explicit data types whenever possible.</span></span> <span data-ttu-id="b7157-113">接受对象引用的参数应被声明为特定的类类型，例如 `As Widget` 而不是 `As Object`。</span><span class="sxs-lookup"><span data-stu-id="b7157-113">Arguments that take object references should be declared as specific class types — for example, `As Widget` instead of `As Object`.</span></span> <span data-ttu-id="b7157-114">在 Visual Basic 中，默认设置 `Option Strict` 将自动执行此规则。</span><span class="sxs-lookup"><span data-stu-id="b7157-114">In Visual Basic, the default setting `Option Strict` automatically enforces this rule.</span></span>  
  
 <span data-ttu-id="b7157-115">键入的参数允许编译器捕获由开发人员犯的很多错误，而不是在运行时才捕获。</span><span class="sxs-lookup"><span data-stu-id="b7157-115">Typed arguments allow many developer errors to be caught by the compiler, rather than at run time.</span></span> <span data-ttu-id="b7157-116">编译器总是捕获错误，而运行时测试只相当于测试套件。</span><span class="sxs-lookup"><span data-stu-id="b7157-116">The compiler always catches errors, whereas run-time testing is only as good as the test suite.</span></span>  
  
## <a name="overloaded-methods"></a><span data-ttu-id="b7157-117">重载方法</span><span class="sxs-lookup"><span data-stu-id="b7157-117">Overloaded Methods</span></span>  

 <span data-ttu-id="b7157-118">如果想允许控件的用户为某个方法提供参数的不同组合，则应使用显式数据类型提供该方法的多个重载。</span><span class="sxs-lookup"><span data-stu-id="b7157-118">If you want to allow users of your control to supply different combinations of parameters to a method, provide multiple overloads of the method, using explicit data types.</span></span> <span data-ttu-id="b7157-119">应避免创建声明 `As Object` 的参数，这样声明的参数可以包含任何数据类型，从而会产生测试时无法捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="b7157-119">Avoid creating parameters declared `As Object` that can contain any data type, as this can lead to errors that might not be caught in testing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b7157-120">公共语言运行时中的通用数据类型是 `Object` 而不是 `Variant`。</span><span class="sxs-lookup"><span data-stu-id="b7157-120">The universal data type in the common language runtime is `Object` rather than `Variant`.</span></span> <span data-ttu-id="b7157-121">`Variant` 已从该语言中移除。</span><span class="sxs-lookup"><span data-stu-id="b7157-121">`Variant` has been removed from the language.</span></span>  
  
 <span data-ttu-id="b7157-122">例如，有一个假想的 `Spin` 控件，其 `Widget` 方法可能允许直接指定旋转方向和速度，或者允许指定另一个 `Widget` 对象作为角动力的来源：</span><span class="sxs-lookup"><span data-stu-id="b7157-122">For example, the `Spin` method of a hypothetical `Widget` control might allow either direct specification of spin direction and speed, or specification of another `Widget` object from which angular momentum is to be absorbed:</span></span>  
  
```vb  
Overloads Public Sub Spin( _  
   ByVal SpinDirection As SpinDirectionsEnum, _  
   ByVal RevolutionsPerSecond As Double)  
   ' Implementation code here.  
End Sub  
Overloads Public Sub Spin(ByVal Driver As Widget) _  
   ' Implementation code here.  
End Sub  
```  
  
```csharp  
public void Spin(SpinDirectionsEnum spinDirection, double revolutionsPerSecond)  
{  
   // Implementation code here.  
}  
  
public void Spin(Widget driver)  
{  
   // Implementation code here.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7157-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7157-123">See also</span></span>

- [<span data-ttu-id="b7157-124">事件</span><span class="sxs-lookup"><span data-stu-id="b7157-124">Events</span></span>](/dotnet/standard/events/index)
- [<span data-ttu-id="b7157-125">Windows 窗体控件中的属性</span><span class="sxs-lookup"><span data-stu-id="b7157-125">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
