---
title: 安全策略和工程
ms.date: 03/30/2017
helpviewer_keywords:
- security [WPF], testing techniques
- Security Development Lifecycle (SDL), security analysis [WPF]
- Security Development Lifecycle (SDL), threat modeling
- Security Development Lifecycle (SDL), testing techniques
- Security Development Lifecycle (SDL), source analysis tools
- Security Development Lifecycle (SDL), critical code management
- threat modeling [WPF]
ms.assetid: 0fc04394-4e47-49ca-b0cf-8cd1161d95b9
ms.openlocfilehash: ef02c3e35250dfc28afb1e966a725048508da311
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668235"
---
# <a name="wpf-security-strategy---security-engineering"></a>WPF 安全策略 - 安全工程

可信计算是 Microsoft 为确保生成安全代码而首创的一项技术。 可信计算计划的关键要素是 (SDL) 的 Microsoft 安全开发生命周期。 SDL 是一种工程实践，与标准工程流程结合使用，以促进安全代码的交付。 SDL 包含10个阶段，其中包含规范化结合、可度量性和其他结构的最佳实践，其中包括：  
  
- 安全设计分析  
  
- 基于工具的质量检查  
  
- 渗透测试  
  
- 最终安全评审  
  
- 发布后产品安全管理  
  
## <a name="wpf-specifics"></a>WPF 详细信息  

 [!INCLUDE[TLA2#tla_winclient](../../includes/tla2sharptla-winclient-md.md)]工程团队共同应用和扩展 SDL，其中包括以下重要方面：  
  
 [威胁建模](#threat_modeling)  
  
 [安全分析和编辑工具](#tools)  
  
 [测试技术](#techniques)  
  
 [关键代码管理](#critical_code)  
  
<a name="threat_modeling"></a>

### <a name="threat-modeling"></a>威胁建模  

 威胁建模是 SDL 的核心组件，用于分析系统，以确定潜在的安全漏洞。 一旦确定漏洞，威胁模型还可以确保采取适当的缓解措施。  
  
 我们以一个杂货店为例，说明威胁模型在高级别上所涉及的以下关键步骤：  
  
1. **确定资产**。 杂货店的资产可能包括员工、保险箱、收银机和库存。  
  
2. **枚举入口点**。 杂货店的入口点可能包括前门和后门、窗户、装货区和空调设备。  
  
3. **使用入口点调查针对资产的攻击**。 可能进行的攻击包括通过空调入口点来对杂货店的保险箱资产进行攻击；有人可能会将空调设备拆掉，将保险箱通过空调处拉出杂货店。  
  
 威胁建模应用于整个 [!INCLUDE[TLA2#tla_winclient](../../includes/tla2sharptla-winclient-md.md)]，包含以下各项：  
  
- [!INCLUDE[TLA2#tla_xaml](../../includes/tla2sharptla-xaml-md.md)] 分析器读取文件、将文本映射到相应的对象模型类并创建实际代码的方式。  
  
- 创建窗口句柄 (hWnd) 并通过其发送消息和呈现窗口内容的方式。  
  
- 数据绑定获取资源以及与系统交互的方式。  
  
 这些威胁模型对于在开发过程中确定安全设计需求以及缓解威胁非常重要。  
  
<a name="tools"></a>

### <a name="source-analysis-and-editing-tools"></a>源分析和编辑工具  

 除了 SDL 的手动安全代码评审元素外， [!INCLUDE[TLA2#tla_winclient](../../includes/tla2sharptla-winclient-md.md)] 团队使用多个工具进行源分析和关联编辑以减少安全漏洞。 使用了多种源工具，包括以下各项：  
  
- **FXCop**：查找托管代码中的常见安全问题，包括继承规则、代码访问安全性的使用情况以及安全地与非托管代码交互操作的方式。 请参阅[FXCop](/previous-versions/dotnet/netframework-3.0/bb429476%28v=vs.80%29)。  
  
- **Prefix/Prefast**：查找非托管代码中的安全漏洞和常见安全问题，例如缓冲区溢出、格式字符串问题以及错误检查。  
  
- **已禁止的 API**：搜索源代码，以识别出众所周知的因意外使用而引发安全问题的函数，例如 `strcpy`。 一旦确定，这些函数将被替换为更安全的替代项。  
  
<a name="techniques"></a>

### <a name="testing-techniques"></a>测试技术  

 [!INCLUDE[TLA2#tla_winclient](../../includes/tla2sharptla-winclient-md.md)] 使用多种安全测试技术，包括：  
  
- **白盒测试**：测试人员查看源代码，然后构建利用测试。
  
- **黑盒测试**：测试人员尝试通过检查 API 和功能来查找安全问题，然后尝试对产品进行攻击。  
  
- **对来自其他产品的安全问题进行回归测试**：对来自相关产品的相关安全问题进行测试。 例如，已识别出 Internet Explorer 的大约60安全问题的适当变体，并尝试将其适用性用于 [!INCLUDE[TLA2#tla_winclient](../../includes/tla2sharptla-winclient-md.md)] 。  
  
- **借助文件模糊化执行基于工具的渗透测试**：文件模糊化指利用文件读取器多种输入的输入范围。 在 [!INCLUDE[TLA2#tla_winclient](../../includes/tla2sharptla-winclient-md.md)] 中的一个示例，使用此技术的一个示例就是检查图像解码代码的错误。  
  
<a name="critical_code"></a>

### <a name="critical-code-management"></a>关键代码管理  

 对于 XAML 浏览器应用程序 (Xbap) ， [!INCLUDE[TLA2#tla_winclient](../../includes/tla2sharptla-winclient-md.md)] 通过使用 .NET Framework 对标记和跟踪安全关键代码的支持来生成安全沙盒， (请参阅 [WPF 安全策略-平台) 安全性](wpf-security-strategy-platform-security.md)中的 **安全关键方法**。 考虑到对安全关键代码有较高的安全质量要求，因此需要对此类代码进行其他级别的源管理控制和安全审核。 大约有 5% 到 10% 的 [!INCLUDE[TLA2#tla_winclient](../../includes/tla2sharptla-winclient-md.md)] 由安全关键代码组成，这些代码由专门的审核团队进行审核。 通过跟踪安全关键代码和将每个关键实体（即，包含关键代码的方法）映射到其签署状态来对源代码和签入过程进行管理。 签署状态包括一个或多个审阅者的姓名。 [!INCLUDE[TLA2#tla_winclient](../../includes/tla2sharptla-winclient-md.md)] 的每个日常版本都将关键代码与前一版本中的该代码进行比较，以检查未经审批的更改。 如果工程师未经审核团队的批准而自行修改关键代码，则将识别并立即修复该代码。 通过这一过程，可以对 [!INCLUDE[TLA2#tla_winclient](../../includes/tla2sharptla-winclient-md.md)] 沙盒代码应用级别特高的审核并加以维护。  
  
## <a name="see-also"></a>请参阅

- [安全性](security-wpf.md)
- [WPF 部分信任安全](wpf-partial-trust-security.md)
- [WPF 安全策略 - 平台安全性](wpf-security-strategy-platform-security.md)
- [可信计算](https://www.microsoft.com/mscorp/twc/default.mspx)
- [.NET 中的安全性](/dotnet/standard/security/index)
