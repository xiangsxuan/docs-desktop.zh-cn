---
title: 应用程序设置特性
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
ms.openlocfilehash: b38ed931cab3a333a56dd027d5843b1c8f00dcb9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970598"
---
# <a name="application-settings-attributes"></a>应用程序设置特性
应用程序设置体系结构提供了许多可应用于应用程序设置包装器类或其各自的属性的属性。 这些属性是在运行时由应用程序设置基础结构（通常是特定于设置提供程序）进行检查，以便为自定义包装器的规定需求进行定制。  
  
 下表列出了可应用于应用程序设置包装器类的属性、此类的单个属性，或同时适用于这两种属性。 按照定义，必须将单个范围属性（**UserScopedSettingAttribute** 或 **ApplicationScopedSettingAttribute**）应用到每个设置属性和每个设置属性。  
  
> [!NOTE]
> 从类派生的自定义设置提供程序 <xref:System.Configuration.SettingsProvider> 只需要识别以下三个属性： **ApplicationScopedSettingAttribute**、 **UserScopedSettingAttribute** 和 **system.configuration.defaultsettingvalueattribute>**。  
  
|Attribute|目标|描述|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|推送、请求和匿名|指定要用于持久性的设置提供程序的短名称。<br /><br /> 如果未提供此属性，则假定为默认提供程序 <xref:System.Configuration.LocalFileSettingsProvider> 。|  
|<xref:System.Configuration.UserScopedSettingAttribute>|推送、请求和匿名|将属性定义为用户范围的应用程序设置。|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|推送、请求和匿名|将属性定义为应用程序范围的应用程序设置。|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|属性|指定一个字符串，提供程序可以将该字符串反序列化为此属性的硬编码默认值。<br /><br /> 不 <xref:System.Configuration.LocalFileSettingsProvider> 需要此特性，如果已保留值，则将重写由此特性提供的任何值。|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|属性|为单个设置提供描述性测试，主要由运行时和设计时工具使用。|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|类|提供设置组的显式名称。 如果缺少此属性，则 <xref:System.Configuration.ApplicationSettingsBase> 使用包装类名称。|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|类|为设置组提供描述性测试，主要由运行时和设计时工具使用。|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|推送、请求和匿名|指定零个或多个应提供给 settings 组或属性的可管理性服务。 可用服务由 <xref:System.Configuration.SettingsManageability> 枚举描述。|  
|<xref:System.Configuration.SpecialSettingAttribute>|属性|指示某个设置属于特殊的预定义类别（如连接字符串），该类别建议由设置提供程序进行特殊处理。 此特性的预定义类别由 <xref:System.Configuration.SpecialSetting> 枚举定义。|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|推送、请求和匿名|为设置组或属性指定首选的序列化机制。 可用的序列化机制由枚举定义 <xref:System.Configuration.SettingsSerializeAs> 。|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|属性|指定设置提供程序应禁用标记的属性的所有应用程序升级功能。|  
  
 *类* 指示该属性只能应用于应用程序设置包装器类。 *属性* 指示特性只能应用于设置属性。 *这两个都* 表示可以在任一级别应用该属性。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- [应用程序设置体系结构](application-settings-architecture.md)
- [如何：创建应用程序设置](how-to-create-application-settings.md)
