---
title: 示例 OpenType 字体包
ms.date: 03/30/2017
helpviewer_keywords:
- OpenType font pack [WPF]
- fonts [WPF], OpenType font pack
- typography [WPF], OpenType font pack
ms.assetid: 56b46fa1-a44e-419b-8f14-25ad51c715c3
ms.openlocfilehash: 2581241225f12a5a1de4b552351c7771c7830871
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973395"
---
# <a name="sample-opentype-font-pack"></a>示例 OpenType 字体包
本主题概述了随 Windows SDK 一起分发的示例 OpenType 字体。 示例字体支持应用程序可使用的扩展 OpenType 功能 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。  

<a name="overview"></a>
## <a name="fonts-in-the-opentype-font-pack"></a>OpenType 字体包中的字体  
 Windows SDK 提供了一组可在创建应用程序时使用的示例 OpenType 字体 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。 这些示例字体在 Ascender Corporation 的许可下提供。 这些字体仅实现由 OpenType 格式定义的全部功能的子集。 下表列出了示例 OpenType 字体的名称。  
  
|名称 - **|**文件**|  
|--------------|--------------|  
|Kootenay|Kooten.ttf|  
|Lindsey|Linds.ttf|  
|Miramonte|Miramo.ttf|  
|Miramonte Bold|Miramob.ttf|  
|Pericles|Peric.ttf|  
|Pericles Light|Pericl.ttf|  
|Pescadero|Pesca.ttf|  
|Pescadero Bold|Pescab.ttf|  
  
 下图显示了示例 OpenType 字体的外观。  
  
 ![示例字体包中的字体名称列表](./media/sample-opentype-font-pack/font-names-sample-pack.gif)  
  
 这些示例字体在 Ascender Corporation 的许可下提供。 Ascender 是一家高级字体产品提供商。 若要对示例字体的扩展版本或自定义版本进行授权，请参阅 [Ascender Corporation 的网站](https://www.monotype.com/)。  
  
> [!NOTE]
> 开发人员有责任确保自己具备必要的许可权，可以在应用程序中嵌入相应的字体或者以其他方式重新分布。  
  
<a name="installing_the_fonts"></a>
## <a name="installing-the-fonts"></a>安装字体  
 你可以选择将示例 OpenType 字体安装到默认 Windows 字体目录 **\WINDOWS\Fonts**。 使用“字体”控制面板安装字体。 一旦这些字体位于您的计算机上，引用默认 Windows 字体的所有应用程序都可以访问它们。 可以通过双击字体文件以多种字体大小来显示具有代表性的字符集。 下面的屏幕截图显示 Lindsey 字体文件 Linds.ttf。  
  
 ![Lindsey 字体 (OpenType)](./media/typographyinwpf-04.png "TypographyInWPF_04")  
显示 Lindsey 字体  
  
<a name="using_the_fonts"></a>
## <a name="using-the-fonts"></a>使用字体  
 可以通过两种方法在应用程序中使用字体。 可以将字体作为项目内容项添加到应用程序中，这些项目内容项不会作为资源嵌入到程序集中。 此外，还可以将字体作为嵌入到应用程序程序集文件中的项目资源项添加到应用程序中。 有关详细信息，请参阅[将字体与应用程序一起打包](packaging-fonts-with-applications.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Documents.Typography>
- [OpenType 字体功能](opentype-font-features.md)
- [将字体与应用程序一起打包](packaging-fonts-with-applications.md)
