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
# <a name="application-settings-for-custom-controls"></a>自定义控件的应用程序设置
当控件承载于第三方应用程序中时，您必须完成某些任务以使您的自定义控件能够保存应用程序设置。

 大多数关于应用程序设置功能的文档都是在创建独立的应用程序时编写的。 但是，如果要创建其他开发人员将在其应用程序中承载的控件，则需要执行一些附加步骤，让控件正确保存其设置。

## <a name="application-settings-and-custom-controls"></a>应用程序设置和自定义控件
 为了使控件正确地保留其设置，它必须通过创建其自己的专用应用程序设置包装器类（派生自）来封装该过程 <xref:System.Configuration.ApplicationSettingsBase> 。 此外，主控件类必须实现 <xref:System.Configuration.IPersistComponentSettings> 。 接口包含多个属性，以及两个方法： <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> 和 <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> 。 如果你使用 Visual Studio 中的 **Windows 窗体设计器** 将控件添加到窗体中，则 Windows 窗体会在 <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> 控件初始化时自动调用; 你必须 <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> 在控件的 `Dispose` 方法中调用。

 此外，还应实现以下内容，以便自定义控件的应用程序设置在设计时环境（如 Visual Studio）中正常工作：

1. 具有采用作为单个参数的构造函数的自定义应用程序设置类 <xref:System.ComponentModel.IComponent> 。 使用此类保存并加载所有应用程序设置。 当你创建此类的新实例时，请使用构造函数传递你的自定义控件。

2. 在窗体上创建并放置控件后创建此自定义设置类，例如在窗体的 <xref:System.Windows.Forms.Form.Load> 事件处理程序中。

 有关创建自定义设置类的说明，请参阅 [如何：创建应用程序设置](how-to-create-application-settings.md)。

## <a name="settings-keys-and-shared-settings"></a>设置密钥和共享设置
 某些控件可以在同一窗体中多次使用。 大多数情况下，你希望这些控件保留自己的各个设置。 使用 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 上的属性 <xref:System.Configuration.IPersistComponentSettings> ，可以提供一个唯一的字符串，用于区分窗体上控件的多个版本。

 实现的最简单方法 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 是使用的 <xref:System.Windows.Forms.Control.Name%2A> 控件的属性 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 。 加载或保存控件的设置时，将的值传递 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 到 <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> 类的属性 <xref:System.Configuration.ApplicationSettingsBase> 。 当应用程序设置将用户的设置保存到 XML 中时，它将使用此唯一键。 下面的代码示例演示一个 `<userSettings>` 节如何查找名为的自定义控件的实例 `CustomControl1` ，该实例为其属性保存设置 `Text` 。

```xml
<userSettings>
    <CustomControl1>
        <setting name="Text" serializedAs="string">
            <value>Hello, World</value>
        </setting>
    </CustomControl1>
</userSettings>
```

 不提供值的控件的任何实例 <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> 都将共享相同的设置。

## <a name="see-also"></a>另请参阅

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.IPersistComponentSettings>
- [应用程序设置体系结构](application-settings-architecture.md)
