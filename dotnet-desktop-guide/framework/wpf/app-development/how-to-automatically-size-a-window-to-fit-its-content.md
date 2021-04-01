---
title: 如何：自动调整窗口大小以适应其内容
description: 了解如何设置属性，该属性指定如何调整窗口大小以适应其在 Windows Presentation Foundation (WPF) 的内容。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resizing windows to fit content [WPF]
- windows [WPF], resizing to fit content
- sizing windows to fit content [WPF]
ms.assetid: 333ca72a-c2f3-4414-9303-3fdabaaa1b32
ms.openlocfilehash: a04089c737102895f1ff6da19fa6a0d17cc60ab6
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973031"
---
# <a name="how-to-automatically-size-a-window-to-fit-its-content"></a><span data-ttu-id="9324b-103">如何：自动调整窗口大小以适应其内容</span><span class="sxs-lookup"><span data-stu-id="9324b-103">How to: Automatically Size a Window to Fit Its Content</span></span>
<span data-ttu-id="9324b-104">此示例演示如何设置 <xref:System.Windows.Window.SizeToContent%2A> 属性以指定如何调整窗口大小以适应其内容。</span><span class="sxs-lookup"><span data-stu-id="9324b-104">This example shows how to set the <xref:System.Windows.Window.SizeToContent%2A> property to specify how a window resizes to fit its content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9324b-105">示例</span><span class="sxs-lookup"><span data-stu-id="9324b-105">Example</span></span>  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]
