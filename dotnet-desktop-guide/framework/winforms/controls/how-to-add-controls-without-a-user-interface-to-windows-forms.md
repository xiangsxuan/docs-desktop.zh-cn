---
title: 不使用用户界面而添加控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
ms.openlocfilehash: c1ab1ec848b4c7a19ed9a65b67e17679bac215cd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971787"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="abf25-102">如何：向 Windows 窗体添加无用户界面的控件</span><span class="sxs-lookup"><span data-stu-id="abf25-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>

<span data-ttu-id="abf25-103"> (或组件) 的非可视控件向您的应用程序提供功能。</span><span class="sxs-lookup"><span data-stu-id="abf25-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="abf25-104">与其他控件不同，组件并不为用户提供用户界面，因此不需要在 Windows 窗体设计器表面上显示。</span><span class="sxs-lookup"><span data-stu-id="abf25-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="abf25-105">将组件添加到窗体时，Windows 窗体设计器将在显示所有组件的窗体底部显示可调整大小的托盘。</span><span class="sxs-lookup"><span data-stu-id="abf25-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="abf25-106">将控件添加到组件栏后，您可以选择该组件并设置其属性，就像对窗体上的任何其他控件一样。</span><span class="sxs-lookup"><span data-stu-id="abf25-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>

## <a name="add-a-component-to-a-windows-form"></a><span data-ttu-id="abf25-107">将组件添加到 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="abf25-107">Add a component to a Windows Form</span></span>

1. <span data-ttu-id="abf25-108">在 Visual Studio 中打开窗体。</span><span class="sxs-lookup"><span data-stu-id="abf25-108">Open the form in Visual Studio.</span></span> <span data-ttu-id="abf25-109">有关详细信息，请参阅 [如何：在设计器中显示 Windows 窗体](/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="abf25-109">For details, see [How to: Display Windows Forms in the Designer](/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="abf25-110">在 " **工具箱**" 中，单击某个组件，然后将其拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="abf25-110">In the **Toolbox**, click a component and drag it to your form.</span></span>

     <span data-ttu-id="abf25-111">组件将出现在组件栏中。</span><span class="sxs-lookup"><span data-stu-id="abf25-111">Your component appears in the component tray.</span></span>

<span data-ttu-id="abf25-112">此外，可以在运行时将组件添加到窗体中。</span><span class="sxs-lookup"><span data-stu-id="abf25-112">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="abf25-113">这是一个常见方案，尤其是因为组件没有可视表达式，这不同于具有用户界面的控件。</span><span class="sxs-lookup"><span data-stu-id="abf25-113">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="abf25-114">在下面的示例中，将 <xref:System.Windows.Forms.Timer> 在运行时添加组件。</span><span class="sxs-lookup"><span data-stu-id="abf25-114">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="abf25-115"> (请注意，Visual Studio 包含许多不同的计时器;在这种情况下，请使用 Windows 窗体 <xref:System.Windows.Forms.Timer> 组件。</span><span class="sxs-lookup"><span data-stu-id="abf25-115">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="abf25-116">有关 Visual Studio 中不同计时器的详细信息，请参阅 [Server-Based 计时器简介](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))。 ) </span><span class="sxs-lookup"><span data-stu-id="abf25-116">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span></span>

> [!CAUTION]
> <span data-ttu-id="abf25-117">组件通常具有特定于控件的属性，必须对其进行设置，组件才能有效工作。</span><span class="sxs-lookup"><span data-stu-id="abf25-117">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="abf25-118">对于 <xref:System.Windows.Forms.Timer> 下面的组件，请设置 `Interval` 属性。</span><span class="sxs-lookup"><span data-stu-id="abf25-118">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="abf25-119">在将组件添加到项目时，请确保为该组件设置必要的属性。</span><span class="sxs-lookup"><span data-stu-id="abf25-119">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>

## <a name="add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="abf25-120">以编程方式向 Windows 窗体添加组件</span><span class="sxs-lookup"><span data-stu-id="abf25-120">Add a component to a Windows Form programmatically</span></span>

1. <span data-ttu-id="abf25-121"><xref:System.Windows.Forms.Timer>在代码中创建类的实例。</span><span class="sxs-lookup"><span data-stu-id="abf25-121">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>

2. <span data-ttu-id="abf25-122">设置 `Interval` 属性以确定计时器计时周期之间的时间。</span><span class="sxs-lookup"><span data-stu-id="abf25-122">Set the `Interval` property to determine the time between ticks of the timer.</span></span>

3. <span data-ttu-id="abf25-123">配置组件的任何其他必要属性。</span><span class="sxs-lookup"><span data-stu-id="abf25-123">Configure any other necessary properties for your component.</span></span>

     <span data-ttu-id="abf25-124">下面的代码演示如何创建 <xref:System.Windows.Forms.Timer> 具有其 `Interval` 属性集的。</span><span class="sxs-lookup"><span data-stu-id="abf25-124">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>

    ```vb
    Public Sub CreateTimer()
       Dim timerKeepTrack As New System.Windows.Forms.Timer
       timerKeepTrack.Interval = 1000
    End Sub
    ```

    ```csharp
    public void createTimer()
    {
       System.Windows.Forms.Timer timerKeepTrack = new
           System.Windows.Forms.Timer();
       timerKeepTrack.Interval = 1000;
    }
    ```

    ```cpp
    public:
       void createTimer()
       {
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew
             System::Windows::Forms::Timer();
          timerKeepTrack->Interval = 1000;
       }
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="abf25-125">通过引用恶意用户，你可以通过网络将你的本地计算机泄露给安全风险。</span><span class="sxs-lookup"><span data-stu-id="abf25-125">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="abf25-126">这只是在恶意用户创建有破坏性的自定义控件时，然后错误地将其添加到项目中时需要注意的问题。</span><span class="sxs-lookup"><span data-stu-id="abf25-126">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="abf25-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="abf25-127">See also</span></span>

- [<span data-ttu-id="abf25-128">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="abf25-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="abf25-129">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="abf25-129">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="abf25-130">如何：向 Windows 窗体添加 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="abf25-130">How to: Add ActiveX Controls to Windows Forms</span></span>](how-to-add-activex-controls-to-windows-forms.md)
- [<span data-ttu-id="abf25-131">将控件放在 Windows 窗体上</span><span class="sxs-lookup"><span data-stu-id="abf25-131">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
- [<span data-ttu-id="abf25-132">标记单个 Windows 窗体控件并提供它们的快捷方式</span><span class="sxs-lookup"><span data-stu-id="abf25-132">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="abf25-133">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="abf25-133">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="abf25-134">根据功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="abf25-134">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
