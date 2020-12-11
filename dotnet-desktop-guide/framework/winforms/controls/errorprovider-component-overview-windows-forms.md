---
title: ErrorProvider 组件概述
ms.date: 03/30/2017
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
ms.openlocfilehash: b66e97d97d0d8c2ea4e9bdba29f8ff35e486e1f6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971311"
---
# <a name="errorprovider-component-overview-windows-forms"></a>ErrorProvider 组件概述（Windows 窗体）
Windows 窗体 [ErrorProvider](errorprovider-component-windows-forms.md) 组件用于验证窗体或控件上的用户输入。 它通常与验证窗体上的用户输入，或在数据集内显示错误一起使用。 错误提供程序是一种比在消息框中显示错误消息的更好的替代方法，因为一旦关闭消息框，错误消息就不再可见。 <xref:System.Windows.Forms.ErrorProvider>组件在红圈内显示一个错误图标 (![ 一个白色感叹号。在 ](./media/errorprovider-component-overview-windows-forms/vb-error-provider-icon.gif) 相关控件（如文本框）旁) ，当用户将鼠标指针放在错误图标上时，将显示一个工具提示，其中显示错误消息字符串。  
  
## <a name="key-properties"></a>键属性  
 <xref:System.Windows.Forms.ErrorProvider>组件的键属性为 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> 、 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 和 <xref:System.Windows.Forms.ErrorProvider.Icon%2A> 。 当使用 <xref:System.Windows.Forms.ErrorProvider> 包含数据绑定控件的组件时， <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 必须将属性设置为适当的容器 (通常是 Windows 窗体) ，以便组件在窗体上显示错误图标。 将组件添加到设计器中时， <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 属性将设置为包含窗体; 如果您在代码中添加控件，则必须自行设置。  
  
 <xref:System.Windows.Forms.ErrorProvider.Icon%2A>属性可以设置为自定义错误图标而不是默认值。 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>设置属性时， <xref:System.Windows.Forms.ErrorProvider> 组件可以显示数据集的错误消息。 组件的关键方法 <xref:System.Windows.Forms.ErrorProvider> 是 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 方法，它指定错误消息字符串和应显示错误图标的位置。  
  
> [!NOTE]
> <xref:System.Windows.Forms.ErrorProvider>组件不为辅助功能客户端提供内置支持。 若要使应用程序在使用此组件时可访问，你必须提供其他可访问的反馈机制。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ErrorProvider>
- [如何：使用 Windows 窗体 ErrorProvider 组件查看数据集中的错误](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
- [如何：使用 Windows 窗体 ErrorProvider 组件显示窗体验证的错误图标](display-error-icons-for-form-validation-with-wf-errorprovider.md)
