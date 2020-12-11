---
title: 自定义控件的应用程序设置
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
ms.openlocfilehash: a4e477ce1c171b514482623595b2c5565564a2cb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970692"
---
# <a name="application-settings-for-custom-controls"></a><span data-ttu-id="896a4-102">自定义控件的应用程序设置</span><span class="sxs-lookup"><span data-stu-id="896a4-102">Application Settings for Custom Controls</span></span>
<span data-ttu-id="896a4-103">当控件承载于第三方应用程序中时，您必须完成某些任务以使您的自定义控件能够保存应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="896a4-103">You must complete certain tasks to give your custom controls the ability to persist application settings when the controls are hosted in third-party applications.</span></span>

 <span data-ttu-id="896a4-104">大多数关于应用程序设置功能的文档都是在创建独立的应用程序时编写的。</span><span class="sxs-lookup"><span data-stu-id="896a4-104">Most of the documentation about the Application Settings feature is written under the assumption that you are creating a standalone application.</span></span> <span data-ttu-id="896a4-105">但是，如果要创建其他开发人员将在其应用程序中承载的控件，则需要执行一些附加步骤，让控件正确保存其设置。</span><span class="sxs-lookup"><span data-stu-id="896a4-105">However, if you are creating a control that other developers will host in their applications, you need to take a few additional steps for your control to persist its settings properly.</span></span>

## <a name="application-settings-and-custom-controls"></a><span data-ttu-id="896a4-106">应用程序设置和自定义控件</span><span class="sxs-lookup"><span data-stu-id="896a4-106">Application Settings and Custom Controls</span></span>
 <span data-ttu-id="896a4-107">为了使控件正确地保留其设置，它必须通过创建其自己的专用应用程序设置包装器类（派生自）来封装该过程 <xref:System.Configuration.ApplicationSettingsBase> 。</span><span class="sxs-lookup"><span data-stu-id="896a4-107">For your control to properly persist its settings, it must encapsulate the process by creating its own dedicated applications settings wrapper class, derived from <xref:System.Configuration.ApplicationSettingsBase>.</span></span> <span data-ttu-id="896a4-108">此外，主控件类必须实现 <xref:System.Configuration.IPersistComponentSettings> 。</span><span class="sxs-lookup"><span data-stu-id="896a4-108">Additionally, the main control class must implement the <xref:System.Configuration.IPersistComponentSettings>.</span></span> <span data-ttu-id="896a4-109">接口包含多个属性，以及两个方法： <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> 和 <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> 。</span><span class="sxs-lookup"><span data-stu-id="896a4-109">The interface contains several properties as well as two methods, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> and <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>.</span></span> <span data-ttu-id="896a4-110">如果你使用 Visual Studio 中的 **Windows 窗体设计器** 将控件添加到窗体中，则 Windows 窗体会在 <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> 控件初始化时自动调用; 你必须 <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> 在控件的 `Dispose` 方法中调用。</span><span class="sxs-lookup"><span data-stu-id="896a4-110">If you add your control to a form using the **Windows Forms Designer** in Visual Studio, Windows Forms will call <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> automatically when the control is initialized; you must call <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> yourself in the `Dispose` method of your control.</span></span>

 <span data-ttu-id="896a4-111">此外，还应实现以下内容，以便自定义控件的应用程序设置在设计时环境（如 Visual Studio）中正常工作：</span><span class="sxs-lookup"><span data-stu-id="896a4-111">In addition, you should implement the following in order for application settings for custom controls to work properly in design-time environments such as Visual Studio:</span></span>

1. <span data-ttu-id="896a4-112">具有采用作为单个参数的构造函数的自定义应用程序设置类 <xref:System.ComponentModel.IComponent> 。</span><span class="sxs-lookup"><span data-stu-id="896a4-112">A custom application settings class with a constructor that takes an <xref:System.ComponentModel.IComponent> as a single parameter.</span></span> <span data-ttu-id="896a4-113">使用此类保存并加载所有应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="896a4-113">Use this class to save and load all of your application settings.</span></span> <span data-ttu-id="896a4-114">当你创建此类的新实例时，请使用构造函数传递你的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="896a4-114">When you create a new instance of this class, pass your custom control using the constructor.</span></span>

2. <span data-ttu-id="896a4-115">在窗体上创建并放置控件后创建此自定义设置类，例如在窗体的 <xref:System.Windows.Forms.Form.Load> 事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="896a4-115">Create this custom settings class after the control has been created and placed on a form, such as in the form's <xref:System.Windows.Forms.Form.Load> event handler.</span></span>

 <span data-ttu-id="896a4-116">有关创建自定义设置类的说明，请参阅 [如何：创建应用程序设置](how-to-create-application-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="896a4-116">For instructions on creating a custom settings class, see [How to: Create Application Settings](how-to-create-application-settings.md).</span></span>

## <a name="settings-keys-and-shared-settings"></a><span data-ttu-id="896a4-117">设置密钥和共享设置</span><span class="sxs-lookup"><span data-stu-id="896a4-117">Settings Keys and Shared Settings</span></span>
 <span data-ttu-id="896a4-118">某些控件可以在同一窗体中多次使用。</span><span class="sxs-lookup"><span data-stu-id="896a4-118">Some controls can be used multiple times within the same form.</span></span> <span data-ttu-id="896a4-119">大多数情况下，你希望这些控件保留自己的各个设置。</span><span class="sxs-lookup"><span data-stu-id="896a4-119">Most of the time, you will want these controls to persist their own individual settings.</span></span> <span data-ttu-id="896a4-120">使用 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 上的属性 <xref:System.Configuration.IPersistComponentSettings> ，可以提供一个唯一的字符串，用于区分窗体上控件的多个版本。</span><span class="sxs-lookup"><span data-stu-id="896a4-120">With the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> property on <xref:System.Configuration.IPersistComponentSettings>, you can supply a unique string that acts to disambiguate multiple versions of a control on a form.</span></span>

 <span data-ttu-id="896a4-121">实现的最简单方法 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 是使用的 <xref:System.Windows.Forms.Control.Name%2A> 控件的属性 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 。</span><span class="sxs-lookup"><span data-stu-id="896a4-121">The simplest way to implement <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> is to use the <xref:System.Windows.Forms.Control.Name%2A> property of the control for the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>.</span></span> <span data-ttu-id="896a4-122">加载或保存控件的设置时，将的值传递 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 到 <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> 类的属性 <xref:System.Configuration.ApplicationSettingsBase> 。</span><span class="sxs-lookup"><span data-stu-id="896a4-122">When you load or save the control's settings, you pass the value of <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> on to the <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> property of the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span> <span data-ttu-id="896a4-123">当应用程序设置将用户的设置保存到 XML 中时，它将使用此唯一键。</span><span class="sxs-lookup"><span data-stu-id="896a4-123">Application Settings uses this unique key when it persists the user's settings to XML.</span></span> <span data-ttu-id="896a4-124">下面的代码示例演示一个 `<userSettings>` 节如何查找名为的自定义控件的实例 `CustomControl1` ，该实例为其属性保存设置 `Text` 。</span><span class="sxs-lookup"><span data-stu-id="896a4-124">The following code example shows how a `<userSettings>` section may look for an instance of a custom control named `CustomControl1` that saves a setting for its `Text` property.</span></span>

```xml
<userSettings>
    <CustomControl1>
        <setting name="Text" serializedAs="string">
            <value>Hello, World</value>
        </setting>
    </CustomControl1>
</userSettings>
```

 <span data-ttu-id="896a4-125">不提供值的控件的任何实例 <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> 都将共享相同的设置。</span><span class="sxs-lookup"><span data-stu-id="896a4-125">Any instances of a control that do not supply a value for <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> will share the same settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="896a4-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="896a4-126">See also</span></span>

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.IPersistComponentSettings>
- [<span data-ttu-id="896a4-127">应用程序设置体系结构</span><span class="sxs-lookup"><span data-stu-id="896a4-127">Application Settings Architecture</span></span>](application-settings-architecture.md)
