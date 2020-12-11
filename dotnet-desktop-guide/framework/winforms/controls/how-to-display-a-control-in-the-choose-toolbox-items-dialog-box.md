---
title: 如何：在“选择工具箱项”对话框中显示控件
ms.date: 08/23/2019
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: b105c45e0d55417066c7f8658f0cb23a12c7f768
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971197"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="ba060-102">如何：在“选择工具箱项”对话框中显示控件</span><span class="sxs-lookup"><span data-stu-id="ba060-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>

<span data-ttu-id="ba060-103">开发和分发控件时，可能希望这些控件出现在 Visual Studio 的 " **选择工具箱项** " 对话框中，当您右键单击 " **工具箱** " 并选择 " **选择项**" 时，将显示该对话框。</span><span class="sxs-lookup"><span data-stu-id="ba060-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box of Visual Studio, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="ba060-104">可以通过使用 AssemblyFoldersEx 注册过程，使控件显示在此对话框中。</span><span class="sxs-lookup"><span data-stu-id="ba060-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>

<span data-ttu-id="ba060-105">若要在 "选择工具箱项" 对话框中显示控件：</span><span class="sxs-lookup"><span data-stu-id="ba060-105">To display your control in the Choose Toolbox Items dialog box:</span></span>

- <span data-ttu-id="ba060-106">将控件程序集安装到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="ba060-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="ba060-107">有关详细信息，请参阅 [如何：将程序集安装到全局程序集缓存中](/dotnet/framework/app-domains/install-assembly-into-gac)。</span><span class="sxs-lookup"><span data-stu-id="ba060-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](/dotnet/framework/app-domains/install-assembly-into-gac).</span></span>

  <span data-ttu-id="ba060-108">-或-</span><span class="sxs-lookup"><span data-stu-id="ba060-108">-or-</span></span>

- <span data-ttu-id="ba060-109">使用 AssemblyFoldersEx 注册过程注册控件及其关联的设计时程序集。</span><span class="sxs-lookup"><span data-stu-id="ba060-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="ba060-110">AssemblyFoldersEx 是一个注册表位置，其中第三方供应商为其支持的每个框架版本存储路径。</span><span class="sxs-lookup"><span data-stu-id="ba060-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="ba060-111">设计时解决方案可以在此注册表位置查找引用程序集。</span><span class="sxs-lookup"><span data-stu-id="ba060-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="ba060-112">注册表脚本可以指定想要在 "工具箱" 中显示的控件。</span><span class="sxs-lookup"><span data-stu-id="ba060-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba060-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba060-113">See also</span></span>

- [<span data-ttu-id="ba060-114">设计时开发 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="ba060-114">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="ba060-115">如何：将程序集安装到全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="ba060-115">How to: Install an Assembly into the Global Assembly Cache</span></span>](/dotnet/framework/app-domains/install-assembly-into-gac)
- [<span data-ttu-id="ba060-116">演练：使用自定义组件自动填充工具箱</span><span class="sxs-lookup"><span data-stu-id="ba060-116">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
