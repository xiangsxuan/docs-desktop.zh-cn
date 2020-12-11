---
title: 应用程序设置体系结构
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], architecture
ms.assetid: c8eb2ad0-fac6-4ea2-9140-675a4a44d562
ms.openlocfilehash: 2f4cdbc5b41646e6879be8b36367bfd008e5acde
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970599"
---
# <a name="application-settings-architecture"></a>应用程序设置体系结构

本主题介绍应用程序设置体系结构的工作原理，并探讨了体系结构的高级功能，如分组设置和设置键。

 应用程序设置体系结构支持定义应用程序或用户范围的强类型设置，并支持保留应用程序会话间的设置。 该体系结构提供一个默认的持久性引擎，用于将设置保存到本地文件系统以及从本地文件系统加载设置。 该体系结构还定义了用于提供自定义持久性引擎的接口。

 在应用程序中托管自定义组件时，利用提供的接口可使这些自定义组件保留其自己的设置。 通过使用设置键，组件能够保持分隔组件多个实例的设置。

## <a name="defining-settings"></a>定义设置

 应用程序设置体系结构在 ASP.NET 和 Windows 窗体中使用，并且包含许多在两个环境中共享的基类。 最重要的是 <xref:System.Configuration.SettingsBase> ，它通过集合提供对设置的访问，并为加载和保存设置提供低级别方法。 每个环境实现自己的派生自 <xref:System.Configuration.SettingsBase> 的类，以便为该环境提供其他设置功能。 在基于 Windows 窗体的应用程序中，必须在派生自类的类上定义所有应用程序设置 <xref:System.Configuration.ApplicationSettingsBase> ，这会将以下功能添加到基类：

- 高层加载和保存操作

- 对用户范围设置的支持

- 将用户的设置还原为预定义的默认值

- 从以前的应用程序版本升级设置

- 在更改设置前或在保存设置前验证设置

 可以使用在命名空间中定义的多个属性对设置进行描述 <xref:System.Configuration> ; " [应用程序设置" 属性](application-settings-attributes.md)中对这些属性进行了说明。 定义设置时，必须将其应用于 <xref:System.Configuration.ApplicationScopedSettingAttribute> 或 <xref:System.Configuration.UserScopedSettingAttribute> ，这说明了该设置是应用于整个应用程序，还是仅应用于当前用户。

 以下代码示例定义一个具有单个设置 `BackgroundColor` 的自定义设置类。

 [!code-csharp[ApplicationSettings.Create#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
 [!code-vb[ApplicationSettings.Create#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]

## <a name="settings-persistence"></a>设置持久性

 <xref:System.Configuration.ApplicationSettingsBase>类本身不会持久保存或加载设置; 此作业将归入设置提供程序，这是一个派生自的类 <xref:System.Configuration.SettingsProvider> 。 如果的派生类 <xref:System.Configuration.ApplicationSettingsBase> 未通过指定设置提供程序 <xref:System.Configuration.SettingsProviderAttribute> ，则使用默认提供程序 <xref:System.Configuration.LocalFileSettingsProvider> 。

 最初随 .NET Framework 一起发布的配置系统支持通过本地计算机的 machine.config 文件或在 `app.` 你使用应用程序部署的exe.config 文件中提供静态应用程序配置数据。 <xref:System.Configuration.LocalFileSettingsProvider>类通过以下方式扩展此本机支持：

- 应用程序范围设置可存储在 machine.config 或 `app.`exe.config 文件中。 Machine.config 始终为只读，而出于安全考虑，`app`.exe.config 对大多数应用程序也限制为只读。

- 用户范围设置可存储在 `app`.exe.config 文件中，在这种情况下，这些设置被视为静态默认设置。

- 非默认的用户范围设置存储在新文件 *user*.config 中，其中 *user* 是当前执行应用程序的用户的用户名。 您可以使用指定用户范围设置的默认值 <xref:System.Configuration.DefaultSettingValueAttribute> 。 由于用户范围设置在应用程序执行期间经常更改，因此 `user`.config 始终可读/写。

 所有这 3 种配置文件都以 XML 格式存储设置。 应用程序范围设置的顶级 XML 元素为 `<appSettings>`，而 `<userSettings>` 用于用户范围设置。 同时包含应用程序范围设置和用户范围设置默认值的 `app`.exe.config 文件如下所示：

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <configSections>
        <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >
            <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
        </sectionGroup>
        <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >
            <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
        </sectionGroup>
    </configSections>
    <applicationSettings>
        <WindowsApplication1.Properties.Settings>
            <setting name="Cursor" serializeAs="String">
                <value>Default</value>
            </setting>
            <setting name="DoubleBuffering" serializeAs="String">
                <value>False</value>
            </setting>
        </WindowsApplication1.Properties.Settings>
    </applicationSettings>
    <userSettings>
        <WindowsApplication1.Properties.Settings>
            <setting name="FormTitle" serializeAs="String">
                <value>Form1</value>
            </setting>
            <setting name="FormSize" serializeAs="String">
                <value>595, 536</value>
            </setting>
        </WindowsApplication1.Properties.Settings>
    </userSettings>
</configuration>
```

 若要了解配置文件的应用程序设置部分内的元素定义，请参阅[应用程序设置架构](/dotnet/framework/configure-apps/file-schema/application-settings-schema)。

### <a name="settings-bindings"></a>设置绑定

 应用程序设置使用 Windows 窗体数据绑定体系结构，提供设置对象和组件间设置更新的双向通信。 如果使用 Visual Studio 创建应用程序设置并将其分配给组件属性，则会自动生成这些绑定。

 只能将应用程序设置绑定到支持该接口的组件 <xref:System.Windows.Forms.IBindableComponent> 。 此外，组件必须为特定绑定属性实现更改事件，或通知应用程序设置属性已通过 <xref:System.ComponentModel.INotifyPropertyChanged> 接口更改。 如果该组件未实现 <xref:System.Windows.Forms.IBindableComponent> 并且您是通过 Visual Studio 绑定的，则将首次设置绑定属性，但不会更新。 如果组件实现 <xref:System.Windows.Forms.IBindableComponent> 但不支持属性更改通知，则在属性更改时，绑定将不会在设置文件中更新。

 某些 Windows 窗体组件（如 <xref:System.Windows.Forms.ToolStripItem> ）不支持设置绑定。

### <a name="settings-serialization"></a>设置序列化

 当 <xref:System.Configuration.LocalFileSettingsProvider> 必须将设置保存到磁盘时，它将执行以下操作：

1. 使用反射检查在派生类上定义的所有属性 <xref:System.Configuration.ApplicationSettingsBase> ，查找使用或应用的属性 <xref:System.Configuration.ApplicationScopedSettingAttribute> <xref:System.Configuration.UserScopedSettingAttribute> 。

2. 将属性序列化到磁盘。 它首先尝试对关联的 <xref:System.ComponentModel.TypeConverter.ConvertToString%2A> 类型调用或 <xref:System.ComponentModel.TypeConverter.ConvertFromString%2A> <xref:System.ComponentModel.TypeConverter> 。 如果不成功，则改用 XML 序列化。

3. 基于设置的特性，确定设置应保存到的文件。

 如果实现自己的设置类，则可以使用 <xref:System.Configuration.SettingsSerializeAsAttribute> 通过枚举标记二进制或自定义序列化的设置 <xref:System.Configuration.SettingsSerializeAs> 。 若要深入了解如何在代码中创建自己的设置类，请参阅[如何：创建应用程序设置](how-to-create-application-settings.md)。

### <a name="settings-file-locations"></a>设置文件位置

 `app`.exe.config 和 *user*.config 文件的位置因应用程序的安装方式而异。 对于复制到本地计算机上的基于 Windows 窗体的应用程序， `app`.exe.config 将位于应用程序的主可执行文件的基目录所在的同一目录中，并且 *用户*.config 将驻留在由属性指定的位置 <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A?displayProperty=nameWithType> 。 对于通过 ClickOnce 安装的应用程序，这两个文件都将位于 "%InstallRoot%\Documents" 下的 "ClickOnce 数据目录" 和 "设置 \\ *用户名*\Local" 设置。

 如果用户启用了漫游配置文件，则这些文件的存储位置会略有不同，使用户能够在域中使用其他计算机时定义不同的 Windows 和应用程序设置。 在这种情况下，ClickOnce 应用程序和非 ClickOnce 应用程序都将其 `app`.exe.config 和 *用户*.config 文件存储在%InstallRoot%\Documents 下，并设置 \\ *username*\Application Data。

 若要深入了解应用程序设置功能如何与新部署技术协同使用，请参阅 [ClickOnce 和应用程序设置](/visualstudio/deployment/clickonce-and-application-settings)。 有关 ClickOnce 数据目录的详细信息，请参阅 [在 Clickonce 应用程序中访问本地数据和远程数据](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications)。

## <a name="application-settings-and-security"></a>应用程序设置和安全

 应用程序设置设计为在部分信任的受限环境中运行，该环境是通过 Internet 或 Intranet 托管的 Windows 窗体应用程序的默认环境。 通过默认设置提供程序使用应用程序设置时，不需要超出部分信任之外的特殊权限。

 在 ClickOnce 应用程序中使用应用程序设置时， `user` .config 文件存储在 clickonce 数据目录中。 应用程序的 `user` .config 文件的大小不能超过 ClickOnce 所设置的数据目录配额。 有关详细信息，请参阅 [ClickOnce 和应用程序设置](/visualstudio/deployment/clickonce-and-application-settings)。

## <a name="custom-settings-providers"></a>自定义设置提供程序

 在应用程序设置体系结构中，应用程序设置包装类（派生自 <xref:System.Configuration.ApplicationSettingsBase> ）与派生自的关联设置提供程序或提供程序之间存在松散耦合 <xref:System.Configuration.SettingsProvider> 。 此关联仅由 <xref:System.Configuration.SettingsProviderAttribute> 应用于包装器类或其各自的属性的定义。 如果未显式指定设置提供程序，则使用默认提供程序 <xref:System.Configuration.LocalFileSettingsProvider> 。 因此，此体系结构支持创建和使用自定义设置提供程序。

 例如，假定要开发和使用提供程序 `SqlSettingsProvider`，它将所有设置数据存储在 Microsoft SQL Server 数据库中。 <xref:System.Configuration.SettingsProvider>派生类将此信息 `Initialize` 作为类型的参数在其方法中接收 <xref:System.Collections.Specialized.NameValueCollection?displayProperty=nameWithType> 。 然后，实现 <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> 方法以从数据存储中检索设置并 <xref:System.Configuration.SettingsProvider.SetPropertyValues%2A> 保存设置。 提供程序可以使用 <xref:System.Configuration.SettingsPropertyCollection> 提供的来 <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> 确定属性的名称、类型和范围，以及为该属性定义的任何其他设置特性。

 提供程序需要实现一个属性和一个方法，这些实现可能不太明显。 <xref:System.Configuration.SettingsProvider.ApplicationName%2A>属性是的抽象属性 <xref:System.Configuration.SettingsProvider> ; 您应该对其进行编程以返回以下内容：

 [!code-csharp[ApplicationSettings.Architecture#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#2)]
 [!code-vb[ApplicationSettings.Architecture#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#2)]

 派生类还必须实现一个 `Initialize` 方法，该方法既不采用参数也不返回值。 此方法不是由定义的 <xref:System.Configuration.SettingsProvider> 。

 最后，在 <xref:System.Configuration.IApplicationSettingsProvider> 提供程序上实现，以提供对刷新设置、将设置还原为默认值以及将设置从一个应用程序版本升级到另一个应用程序的支持。

 实现并编译了提供程序后，需要指示设置类使用此提供程序，而不是使用默认的提供程序。 可以通过实现此目的 <xref:System.Configuration.SettingsProviderAttribute> 。 如果应用于整个设置类，则提供程序将用于该类定义的每个设置;如果应用于单个设置，则应用程序设置体系结构仅对这些设置使用该提供程序，并 <xref:System.Configuration.LocalFileSettingsProvider> 将用于其余设置。 以下代码示例说明如何指示设置类使用自定义提供程序。

 [!code-csharp[ApplicationSettings.Architecture#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#1)]
 [!code-vb[ApplicationSettings.Architecture#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#1)]

 提供程序可能会同时从多个线程调用，但其始终会写入同一存储位置；因此，应用程序设置体系结构在任何时候都仅实例化提供程序类的单个实例。

> [!IMPORTANT]
> 应确保提供程序是线程安全的，并且一次只允许一个线程写入配置文件。

 你的提供程序不需要支持命名空间中定义的所有设置属性 <xref:System.Configuration?displayProperty=nameWithType> ，但必须至少支持 <xref:System.Configuration.ApplicationScopedSettingAttribute> 和 <xref:System.Configuration.UserScopedSettingAttribute> ，并且还应支持 <xref:System.Configuration.DefaultSettingValueAttribute> 。 对于其不支持的特性，提供程序应直接失败，而不另行通知；提供程序不应引发异常。 如果设置类使用了无效的属性组合（如将 <xref:System.Configuration.ApplicationScopedSettingAttribute> 和应用 <xref:System.Configuration.UserScopedSettingAttribute> 到相同的设置），则提供程序应引发异常和停止操作。

## <a name="see-also"></a>另请参阅

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- <xref:System.Configuration.LocalFileSettingsProvider>
- [应用程序设置概述](application-settings-overview.md)
- [自定义控件的应用程序设置](application-settings-for-custom-controls.md)
- [ClickOnce 和应用程序设置](/visualstudio/deployment/clickonce-and-application-settings)
- [应用程序设置架构](/dotnet/framework/configure-apps/file-schema/application-settings-schema)
