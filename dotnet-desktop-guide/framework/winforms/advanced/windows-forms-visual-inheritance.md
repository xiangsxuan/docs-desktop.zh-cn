---
title: 可视化继承
ms.date: 03/30/2017
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inheritance
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 857eb737-3602-4d49-bd8b-f70d33ace345
ms.openlocfilehash: dfc5d1b74e7892463317d841e7fcb9c63cf2b9c8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970752"
---
# <a name="windows-forms-visual-inheritance"></a><span data-ttu-id="f51e3-102">Windows 窗体可视化继承</span><span class="sxs-lookup"><span data-stu-id="f51e3-102">Windows Forms Visual Inheritance</span></span>

<span data-ttu-id="f51e3-103">有时，项目可能需要一个与之前项目中创建的窗体类似的窗体。</span><span class="sxs-lookup"><span data-stu-id="f51e3-103">Occasionally, you may decide that a project calls for a form similar to one that you have created in a previous project.</span></span> <span data-ttu-id="f51e3-104">或者，可能需要创建一个基本窗体，其中包含某些设置，如随后将再次在项目中使用的水印或某种控件布局，然后每次重复使用时，都需要对该原始窗体模板进行修改。</span><span class="sxs-lookup"><span data-stu-id="f51e3-104">Or, you may want to create a basic form with settings such as a watermark or certain control layout that you will then use again within a project, with each iteration containing modifications to the original form template.</span></span> <span data-ttu-id="f51e3-105">通过窗体继承，可创建基窗体，然后从其继承并进行修改，同时保留所需的任何原始设置。</span><span class="sxs-lookup"><span data-stu-id="f51e3-105">Form inheritance enables you to create a base form and then inherit from it and make modifications while preserving whatever original settings you need.</span></span>  
  
 <span data-ttu-id="f51e3-106">可通过编程方式或使用视觉继承选取器创建派生类窗体。</span><span class="sxs-lookup"><span data-stu-id="f51e3-106">You can create derived-class forms programmatically or by using the Visual Inheritance picker.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f51e3-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="f51e3-107">In This Section</span></span>  

 [<span data-ttu-id="f51e3-108">如何：继承 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="f51e3-108">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)  
 <span data-ttu-id="f51e3-109">提供在代码中创建继承窗体的指导性说明。</span><span class="sxs-lookup"><span data-stu-id="f51e3-109">Gives directions for creating inherited forms in code.</span></span>  
  
 [<span data-ttu-id="f51e3-110">如何：使用“继承选择器”对话框继承窗体</span><span class="sxs-lookup"><span data-stu-id="f51e3-110">How to: Inherit Forms Using the Inheritance Picker Dialog Box</span></span>](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md)  
 <span data-ttu-id="f51e3-111">提供使用继承选取器创建继承窗体的指导性说明。</span><span class="sxs-lookup"><span data-stu-id="f51e3-111">Gives directions for creating inherited forms with the Inheritance Picker.</span></span>  
  
 [<span data-ttu-id="f51e3-112">修改基窗体的外观的效果</span><span class="sxs-lookup"><span data-stu-id="f51e3-112">Effects of Modifying a Base Form's Appearance</span></span>](effects-of-modifying-base-form-appearance.md)  
 <span data-ttu-id="f51e3-113">提供更改基窗体控件及其属性的指导性说明。</span><span class="sxs-lookup"><span data-stu-id="f51e3-113">Gives directions for changing a base form's controls and their properties.</span></span>  
  
 [<span data-ttu-id="f51e3-114">演练：演示可视化继承</span><span class="sxs-lookup"><span data-stu-id="f51e3-114">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)  
 <span data-ttu-id="f51e3-115">描述如何创建基 Windows 窗体并将其编译为类库。</span><span class="sxs-lookup"><span data-stu-id="f51e3-115">Describes how to create a base Windows Form and compile it into a class library.</span></span> <span data-ttu-id="f51e3-116">可将此类库导入另一个项目，并创建一个从基窗体继承的新窗体。</span><span class="sxs-lookup"><span data-stu-id="f51e3-116">You will import this class library into another project, and create a new form that inherits from the base form.</span></span>  
  
 [<span data-ttu-id="f51e3-117">如何：使用 Modifiers 和 GenerateMember 属性</span><span class="sxs-lookup"><span data-stu-id="f51e3-117">How to: Use the Modifiers and GenerateMember Properties</span></span>](how-to-use-the-modifiers-and-generatemember-properties.md)  
 <span data-ttu-id="f51e3-118">提供有关如何使用 `GenerateMember` 和 `Modifiers` 属性的指导性说明，Windows 窗体设计器为组件生成成员变量时会涉及这些属性。</span><span class="sxs-lookup"><span data-stu-id="f51e3-118">Gives directions for using the `GenerateMember` and `Modifiers` properties, which are relevant when the Windows Forms Designer generates a member variable for a component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f51e3-119">相关章节</span><span class="sxs-lookup"><span data-stu-id="f51e3-119">Related Sections</span></span>  

 [<span data-ttu-id="f51e3-120">继承基础 (Visual Basic) </span><span class="sxs-lookup"><span data-stu-id="f51e3-120">Inheritance basics (Visual Basic)</span></span>](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)  
 <span data-ttu-id="f51e3-121">描述如何定义作为其他类的基础的 Visual Basic 类。</span><span class="sxs-lookup"><span data-stu-id="f51e3-121">Describes how to define Visual Basic classes that serve as the basis for other classes.</span></span>  
  
 [<span data-ttu-id="f51e3-122">class</span><span class="sxs-lookup"><span data-stu-id="f51e3-122">class</span></span>](/dotnet/csharp/language-reference/keywords/class)  
 <span data-ttu-id="f51e3-123">描述类的 C# 方法，此方法中允许单个继承。</span><span class="sxs-lookup"><span data-stu-id="f51e3-123">Describes the C# approach of classes, in which single inheritance is allowed.</span></span>  
  
 [<span data-ttu-id="f51e3-124">Visual Basic 中继承的事件处理程序疑难解答</span><span class="sxs-lookup"><span data-stu-id="f51e3-124">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers)  
 <span data-ttu-id="f51e3-125">列出了由继承组件中的事件处理程序引发的常见问题</span><span class="sxs-lookup"><span data-stu-id="f51e3-125">Lists common issues that arise with event handlers in inherited components</span></span>
