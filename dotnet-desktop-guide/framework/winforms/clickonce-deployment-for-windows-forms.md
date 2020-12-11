---
title: ClickOnce 部署
ms.date: 03/30/2017
helpviewer_keywords:
- ClickOnce deployment [Windows Forms]
- Windows Forms, ClickOnce deployment
- walkthroughs [Windows Forms], ClickOnce deployment
ms.assetid: 1451fce9-1965-4a03-b4d3-831b5fe4ad66
ms.openlocfilehash: 13b65173e8aff81a554350942d2559cf2b5395ea
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971347"
---
# <a name="clickonce-deployment-for-windows-forms"></a><span data-ttu-id="81c75-102">Windows 窗体的 ClickOnce 部署</span><span class="sxs-lookup"><span data-stu-id="81c75-102">ClickOnce Deployment for Windows Forms</span></span>
<span data-ttu-id="81c75-103">以下主题描述了 ClickOnce，这是一个用于轻松地将 Windows 窗体应用程序部署到客户端计算机的技术。</span><span class="sxs-lookup"><span data-stu-id="81c75-103">The following topics describe ClickOnce, a technology used for easily deploying Windows Forms applications to client computers.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="81c75-104">相关章节</span><span class="sxs-lookup"><span data-stu-id="81c75-104">Related Sections</span></span>  
 [<span data-ttu-id="81c75-105">选择 ClickOnce 部署策略</span><span class="sxs-lookup"><span data-stu-id="81c75-105">Choosing a ClickOnce Deployment Strategy</span></span>](/visualstudio/deployment/choosing-a-clickonce-deployment-strategy)  
 <span data-ttu-id="81c75-106">提供了用于部署 ClickOnce 应用程序的多个选项。</span><span class="sxs-lookup"><span data-stu-id="81c75-106">Presents several options for deploying ClickOnce applications.</span></span>  
  
 [<span data-ttu-id="81c75-107">选择 ClickOnce 更新策略</span><span class="sxs-lookup"><span data-stu-id="81c75-107">Choosing a ClickOnce Update Strategy</span></span>](/visualstudio/deployment/choosing-a-clickonce-update-strategy)  
 <span data-ttu-id="81c75-108">显示用于更新 ClickOnce 应用程序的多个选项。</span><span class="sxs-lookup"><span data-stu-id="81c75-108">Presents several options for updating ClickOnce applications.</span></span>  
  
 [<span data-ttu-id="81c75-109">保护 ClickOnce 应用程序</span><span class="sxs-lookup"><span data-stu-id="81c75-109">Securing ClickOnce Applications</span></span>](/visualstudio/deployment/securing-clickonce-applications)  
 <span data-ttu-id="81c75-110">说明 ClickOnce 部署的安全含义。</span><span class="sxs-lookup"><span data-stu-id="81c75-110">Explains the security implications of ClickOnce deployment.</span></span>  
  
 [<span data-ttu-id="81c75-111">ClickOnce 部署疑难解答</span><span class="sxs-lookup"><span data-stu-id="81c75-111">Troubleshooting ClickOnce Deployments</span></span>](/visualstudio/deployment/troubleshooting-clickonce-deployments)  
 <span data-ttu-id="81c75-112">描述在部署 ClickOnce 应用程序时可能发生的各种问题，并记录 ClickOnce 可能生成的顶级错误消息。</span><span class="sxs-lookup"><span data-stu-id="81c75-112">Describes various problems that can occur when deploying ClickOnce applications, and documents the top-level error messages that ClickOnce might generate.</span></span>  
  
 [<span data-ttu-id="81c75-113">ClickOnce 和应用程序设置</span><span class="sxs-lookup"><span data-stu-id="81c75-113">ClickOnce and Application Settings</span></span>](/visualstudio/deployment/clickonce-and-application-settings)  
 <span data-ttu-id="81c75-114">描述 ClickOnce 部署如何与应用程序设置一起工作，应用程序设置用于存储应用程序和用户设置以供将来检索。</span><span class="sxs-lookup"><span data-stu-id="81c75-114">Describes how ClickOnce deployment works with application settings, which stores application and user settings for future retrieval.</span></span>  
  
 [<span data-ttu-id="81c75-115">受信任的应用程序部署概述</span><span class="sxs-lookup"><span data-stu-id="81c75-115">Trusted Application Deployment Overview</span></span>](/visualstudio/deployment/trusted-application-deployment-overview)  
 <span data-ttu-id="81c75-116">描述一个 ClickOnce 功能，该功能允许受信任的应用程序在客户端计算机上以更高的权限级别运行。</span><span class="sxs-lookup"><span data-stu-id="81c75-116">Describes a ClickOnce feature that allows trusted applications to run with a higher level of permission on client computers.</span></span>  
  
 [<span data-ttu-id="81c75-117">ClickOnce 和 Authenticode</span><span class="sxs-lookup"><span data-stu-id="81c75-117">ClickOnce and Authenticode</span></span>](/visualstudio/deployment/clickonce-and-authenticode)  
 <span data-ttu-id="81c75-118">描述如何在受信任的应用程序部署中使用验证码技术。</span><span class="sxs-lookup"><span data-stu-id="81c75-118">Describes how Authenticode technology is used in trusted application deployment.</span></span>  
  
 [<span data-ttu-id="81c75-119">演练：手动部署 ClickOnce 应用程序</span><span class="sxs-lookup"><span data-stu-id="81c75-119">Walkthrough: Manually Deploying a ClickOnce Application</span></span>](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)  
 <span data-ttu-id="81c75-120">演示如何使用命令行和 SDK 工具在不使用 Visual Studio 的情况下部署 ClickOnce 应用程序。</span><span class="sxs-lookup"><span data-stu-id="81c75-120">Demonstrates using command-line and SDK tools to deploy a ClickOnce application without using Visual Studio.</span></span>  
  
 [<span data-ttu-id="81c75-121">如何：为 ClickOnce 应用程序向客户端计算机添加一个受信任的发布者</span><span class="sxs-lookup"><span data-stu-id="81c75-121">How to: Add a Trusted Publisher to a Client Computer for ClickOnce Applications</span></span>](/visualstudio/deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications)  
 <span data-ttu-id="81c75-122">演示如何一次性配置受信任的应用程序部署所需要的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="81c75-122">Demonstrates the one-time configuration of client computers required for trusted application deployment.</span></span>  
  
 [<span data-ttu-id="81c75-123">如何：指定部署更新的其他位置</span><span class="sxs-lookup"><span data-stu-id="81c75-123">How to: Specify an Alternate Location for Deployment Updates</span></span>](/visualstudio/deployment/how-to-specify-an-alternate-location-for-deployment-updates)  
 <span data-ttu-id="81c75-124">演示如何使用 SDK 工具配置 ClickOnce 应用程序，以检查新版本的应用程序的不同位置。</span><span class="sxs-lookup"><span data-stu-id="81c75-124">Demonstrates configuring a ClickOnce application, using SDK tools, to check a different location for new versions of an application.</span></span>  
  
 [<span data-ttu-id="81c75-125">演练：使用 ClickOnce 部署 API 按需下载程序集</span><span class="sxs-lookup"><span data-stu-id="81c75-125">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api)  
 <span data-ttu-id="81c75-126">演示如何在应用程序第一次尝试加载程序集时使用 API 调用来检索程序集。</span><span class="sxs-lookup"><span data-stu-id="81c75-126">Demonstrates using API calls to retrieve an assembly the first time your application attempts to load it.</span></span>  
  
 [<span data-ttu-id="81c75-127">如何：在联机 ClickOnce 应用程序中检索查询字符串信息</span><span class="sxs-lookup"><span data-stu-id="81c75-127">How to: Retrieve Query String Information in an Online ClickOnce Application</span></span>](/visualstudio/deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application)  
 <span data-ttu-id="81c75-128">演示如何从用于运行 ClickOnce 应用程序的 URL 中检索参数。</span><span class="sxs-lookup"><span data-stu-id="81c75-128">Demonstrates retrieving parameters from the URL used to run a ClickOnce application.</span></span>  
  
 [<span data-ttu-id="81c75-129">ClickOnce 缓存概述</span><span class="sxs-lookup"><span data-stu-id="81c75-129">ClickOnce Cache Overview</span></span>](/visualstudio/deployment/clickonce-cache-overview)  
 <span data-ttu-id="81c75-130">描述用于在本地计算机上存储 ClickOnce 应用程序的缓存。</span><span class="sxs-lookup"><span data-stu-id="81c75-130">Describes the cache used to store ClickOnce applications on the local computer.</span></span>  
  
 [<span data-ttu-id="81c75-131">在 ClickOnce 应用程序中访问本地数据和远程数据</span><span class="sxs-lookup"><span data-stu-id="81c75-131">Accessing Local and Remote Data in ClickOnce Applications</span></span>](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications)  
 <span data-ttu-id="81c75-132">介绍如何从 ClickOnce 应用程序访问本地数据文件和远程数据源。</span><span class="sxs-lookup"><span data-stu-id="81c75-132">Describes how to access local data files and remote data sources from a ClickOnce application.</span></span>  
  
 [<span data-ttu-id="81c75-133">How to: Include a Data File in a ClickOnce Application</span><span class="sxs-lookup"><span data-stu-id="81c75-133">How to: Include a Data File in a ClickOnce Application</span></span>](/visualstudio/deployment/how-to-include-a-data-file-in-a-clickonce-application)  
 <span data-ttu-id="81c75-134">演示如何标记文件以使其在 ClickOnce 数据目录中可用。</span><span class="sxs-lookup"><span data-stu-id="81c75-134">Demonstrates how to mark a file so that it is available in the ClickOnce data directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c75-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81c75-135">See also</span></span>

- [<span data-ttu-id="81c75-136">应用程序设置概述</span><span class="sxs-lookup"><span data-stu-id="81c75-136">Application Settings Overview</span></span>](./advanced/application-settings-overview.md)
- [<span data-ttu-id="81c75-137">发布 ClickOnce 应用程序</span><span class="sxs-lookup"><span data-stu-id="81c75-137">Publishing ClickOnce Applications</span></span>](/visualstudio/deployment/publishing-clickonce-applications)
- [<span data-ttu-id="81c75-138">从命令行生成 ClickOnce 应用程序</span><span class="sxs-lookup"><span data-stu-id="81c75-138">Building ClickOnce Applications from the Command Line</span></span>](/visualstudio/deployment/building-clickonce-applications-from-the-command-line)
- [<span data-ttu-id="81c75-139">调试使用 System.Deployment.Application 的 ClickOnce 应用程序</span><span class="sxs-lookup"><span data-stu-id="81c75-139">Debugging ClickOnce Applications That Use System.Deployment.Application</span></span>](/visualstudio/deployment/debugging-clickonce-applications-that-use-system-deployment-application)
- [<span data-ttu-id="81c75-140">使用 ClickOnce 部署 COM 组件</span><span class="sxs-lookup"><span data-stu-id="81c75-140">Deploying COM Components with ClickOnce</span></span>](/visualstudio/deployment/deploying-com-components-with-clickonce)
- [<span data-ttu-id="81c75-141">如何：使用发布向导发布 ClickOnce 应用程序</span><span class="sxs-lookup"><span data-stu-id="81c75-141">How to: Publish a ClickOnce Application using the Publish Wizard</span></span>](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)
