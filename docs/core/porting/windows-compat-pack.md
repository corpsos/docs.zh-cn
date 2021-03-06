---
title: 移植到 .NET Core - 使用 Windows 兼容性包
description: 了解有关 Windows 兼容性包以及如何使用它将现有 .NET Framework 代码移植到 .NET Core 的信息
author: terrajobst
ms.author: mairaw
ms.date: 11/13/2017
ms.openlocfilehash: 51b96d7828285964c1b0cbb835b8eb5ed92c47d6
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34566168"
---
# <a name="using-the-windows-compatibility-pack"></a>使用 Windows 兼容性包

开发人员在将其现有代码移植到 .NET Core 时遇到的最常见问题之一是他们依赖于仅存在于 .NET Framework 中的 API 和技术。 Windows 兼容性包将提供其中许多技术，使针对现有代码生成 .NET Core 应用程序以及 .NET Standard 库变得更为可行。

此包是 [.NET Standard 2.0 的逻辑扩展](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support)，显著增加了 API 集和现有代码编译，而几乎无需进行任何修改。 但为了信守 .NET Standard 的承诺（“它是一组所有 .NET 实现都提供的 API”），这不包括无法跨所有平台工作的技术，如注册表、Windows Management Instrumentation (WMI) 或反射发出 API。

Windows 兼容性包 位于 .NET Standard 顶部，提供对仅用于 Windows 的技术的访问权限。 它对于第一步想要移动到 .NET Core 但仍计划停留在 Windows 上的客户尤其有用。 在这种情况下，无法使用仅限 Windows 的技术只会造成迁移障碍，没有任何体系结构优势。

## <a name="package-contents"></a>包内容

Windows 兼容性包通过 NuGet 包 [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) 提供，可从面向 .NET Core 或 .NET Standard 的项目引用。

它提供了约 20,000 个 API，包括仅 Windows API 以及以下技术领域中的跨平台 API：

* 代码页
* CodeDom
* 配置
* 目录服务
* 绘图
* ODBC
* 权限
* 端口
* Windows 访问控制列表 (ACL)
* Windows Communication Foundation (WCF)
* Windows 加密
* Windows 事件日志
* Windows Management Instrumentation (WMI)
* Windows 性能计数器
* Windows 注册表
* Windows 运行时缓存
* Windows 服务

有关详细信息，请参阅[兼容性包规范](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md)。

## <a name="get-started"></a>入门

1. 移植之前，请确保查看[移植过程](index.md)。

2. 将现有代码移植到 .NET Core 或 .NET Standard 时，请安装 NuGet 包 [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility)。

3. 如果要停留在 Windows 上，则已准备完毕。

4. 如果要在 Linux 或 macOS 上运行 .NET Core 应用程序或 .NET Standard 库，请使用 [API 分析器](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/)查找不会跨平台工作的 API 的使用情况。

5. 删除这些 API 的使用情况、将其替换为跨平台替代项，或使用平台检查对其实施保护，例如：

    ```csharp
    private static string GetLoggingPath()
    {
        // Verify the code is running on Windows.
        if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
        {
            using (var key = Registry.CurrentUser.OpenSubKey(@"Software\Fabrikam\AssetManagement"))
            {
                if (key?.GetValue("LoggingDirectoryPath") is string configuredPath)
                    return configuredPath;
            }
        }

        // This is either not running on Windows or no logging path was configured,
        // so just use the path for non-roaming user-specific data files.
        var appDataPath = Environment.GetFolderPath(Environment.SpecialFolder.LocalApplicationData);
        return Path.Combine(appDataPath, "Fabrikam", "AssetManagement", "Logging");
    }
    ```

有关演示，请查看 [Windows 兼容性包的第 9 频道视频](https://channel9.msdn.com/Events/Connect/2017/T123)。

