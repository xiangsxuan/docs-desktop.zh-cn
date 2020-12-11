---
title: 如何：检测是否安装了 .NET Framework 3.0
ms.date: 03/30/2017
helpviewer_keywords:
- WinFX Runtime user-agent string
- presence of WPT [WPF], detecting
- detecting WPF presence [WPF]
ms.assetid: 7f71d652-1749-4379-945a-aa2e3994cb43
ms.openlocfilehash: 7c943b73c45f8b55aa04bc477f2de5c42794d947
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973893"
---
# <a name="how-to-detect-whether-the-net-framework-30-is-installed"></a><span data-ttu-id="e53b9-102">如何：检测是否安装了 .NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="e53b9-102">How to: Detect Whether the .NET Framework 3.0 Is Installed</span></span>

<span data-ttu-id="e53b9-103">在管理员可以在系统上部署 Microsoft .NET Framework 应用程序之前，必须先确认 .NET Framework 运行时存在。</span><span class="sxs-lookup"><span data-stu-id="e53b9-103">Before administrators can deploy Microsoft .NET Framework applications on a system, they must first confirm that the .NET Framework runtime is present.</span></span> <span data-ttu-id="e53b9-104">本主题提供以 HTML/JavaScript 编写的脚本，管理员可以使用该脚本来确定系统中是否存在 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="e53b9-104">This topic provides a script written in HTML/JavaScript that administrators can use to determine whether the .NET Framework is present on a system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e53b9-105">有关安装、部署和检测 Microsoft .NET 框架的详细信息，请参阅 [部署 Microsoft .NET Framework 版本 3.0](/previous-versions/dotnet/articles/aa480198(v=msdn.10))中的讨论。</span><span class="sxs-lookup"><span data-stu-id="e53b9-105">For more detailed information on installing, deploying, and detecting the Microsoft .NET Framework, see the discussion in [Deploying Microsoft .NET Framework Version 3.0](/previous-versions/dotnet/articles/aa480198(v=msdn.10)).</span></span>  
  
<a name="content_expiration"></a>

## <a name="detect-the-net-clr-user-agent-string"></a><span data-ttu-id="e53b9-106">检测 ".NET CLR" User-Agent 字符串</span><span class="sxs-lookup"><span data-stu-id="e53b9-106">Detect the ".NET CLR" User-Agent String</span></span>  

 <span data-ttu-id="e53b9-107">安装 .NET Framework 后，MSI 会将 ".NET CLR" 和版本号添加到 UserAgent 字符串。</span><span class="sxs-lookup"><span data-stu-id="e53b9-107">When .NET Framework is installed, the MSI adds ".NET CLR" and the version number to the UserAgent string.</span></span> <span data-ttu-id="e53b9-108">下面的示例演示了一个嵌入到简单 HTML 页面中的脚本。</span><span class="sxs-lookup"><span data-stu-id="e53b9-108">The following example shows a script embedded in a simple HTML page.</span></span> <span data-ttu-id="e53b9-109">此脚本搜索 UserAgent 字符串，以确定是否安装了 .NET Framework，并在搜索结果中显示状态消息。</span><span class="sxs-lookup"><span data-stu-id="e53b9-109">The script searches the UserAgent string to determine whether .NET Framework is installed, and displays a status message on the results of the search.</span></span>  
  
```html  
<HTML>  
  <HEAD>  
    <TITLE>Test for the .NET Framework 3.0</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT LANGUAGE="JavaScript">  
    <!--  
    var dotNETRuntimeVersion = "3.0.04425.00";  
  
    function window::onload()  
    {  
      if (HasRuntimeVersion(dotNETRuntimeVersion))  
      {  
        result.innerText =   
          "This machine has the correct version of the .NET Framework 3.0: "   
          + dotNETRuntimeVersion  
      }   
      else  
      {  
        result.innerText =   
          "This machine does not have the correct version of the .NET Framework 3.0."  
      }  
      result.innerText += "\n\nThis machine's userAgent string is: " +   
        navigator.userAgent + ".";  
    }  
  
    //  
    // Retrieve the version from the user agent string and   
    // compare with the specified version.  
    //  
    function HasRuntimeVersion(versionToCheck)  
    {  
      var userAgentString =   
        navigator.userAgent.match(/.NET CLR [0-9.]+/g);  
  
      if (userAgentString != null)  
      {  
        var i;  
  
        for (i = 0; i < userAgentString.length; ++i)  
        {  
          if (CompareVersions(GetVersion(versionToCheck),   
            GetVersion(userAgentString[i])) <= 0)  
            return true;  
        }  
      }  
  
      return false;  
    }  
  
    //  
    // Extract the numeric part of the version string.  
    //  
    function GetVersion(versionString)  
    {  
      var numericString =   
        versionString.match(/([0-9]+)\.([0-9]+)\.([0-9]+)/i);  
      return numericString.slice(1);  
    }  
  
    //  
    // Compare the 2 version strings by converting them to numeric format.  
    //  
    function CompareVersions(version1, version2)  
    {  
      for (i = 0; i < version1.length; ++i)  
      {  
        var number1 = new Number(version1[i]);  
        var number2 = new Number(version2[i]);  
  
        if (number1 < number2)  
          return -1;  
  
        if (number1 > number2)  
          return 1;  
      }  
  
      return 0;  
    }  
  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY>  
    <div id="result" />  
  </BODY>  
</HTML>  
```  
  
 <span data-ttu-id="e53b9-110">如果搜索 ".NET CLR" 版本成功，将显示以下类型的状态消息：</span><span class="sxs-lookup"><span data-stu-id="e53b9-110">If the search for the ".NET CLR " version is successful, the following type of status message appears:</span></span>  
  
 `This machine has the correct version of the .NET Framework 3.0: 3.0.04425.00`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; .NET CLR 1.1.4322; InfoPath.1; .NET CLR 2.0.50727; .NET CLR 3.0.04425.00).`  
  
 <span data-ttu-id="e53b9-111">否则，会显示以下类型的状态消息：</span><span class="sxs-lookup"><span data-stu-id="e53b9-111">Otherwise, the following type of status message appears:</span></span>  
  
 `This machine does not have correct version of the .NET Framework 3.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; .NET CLR 1.1.4322; InfoPath.1; .NET CLR 2.0.50727).`
