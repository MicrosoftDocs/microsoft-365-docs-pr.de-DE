---
title: Behandeln fehlender Ereignisse oder Warnungen für Microsoft Defender ATP für Linux
description: Behandeln fehlender Ereignisse oder Warnungen in Microsoft Defender ATP für Linux.
keywords: microsoft, defender, atp, linux, events
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e489d5bece292065ad2e82a7eb9011747733b4f6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065704"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="56aa9-104">Behandeln fehlender Ereignisse oder Warnungen für Microsoft Defender for Endpoint für Linux</span><span class="sxs-lookup"><span data-stu-id="56aa9-104">Troubleshoot missing events or alerts issues for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="56aa9-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="56aa9-105">**Applies to:**</span></span>

- [<span data-ttu-id="56aa9-106">Microsoft Defender for Endpoint for Linux</span><span class="sxs-lookup"><span data-stu-id="56aa9-106">Microsoft Defender for Endpoint for Linux</span></span>](microsoft-defender-endpoint-linux.md)

<span data-ttu-id="56aa9-107">Dieser Artikel enthält einige allgemeine Schritte zum Verringern fehlender Ereignisse oder Warnungen im [Security Center-Portal.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="56aa9-107">This article provides some general steps to mitigate missing events or alerts in the [security center](https://securitycenter.windows.com/) portal.</span></span>

<span data-ttu-id="56aa9-108">Sobald **Microsoft Defender for Endpoint** ordnungsgemäß auf  einem Gerät installiert wurde, wird im Portal eine Geräteseite generiert.</span><span class="sxs-lookup"><span data-stu-id="56aa9-108">Once **Microsoft Defender for Endpoint** has been installed properly on a device, a _device page_ will be generated in the portal.</span></span> <span data-ttu-id="56aa9-109">Sie können alle aufgezeichneten Ereignisse auf der Registerkarte Zeitachse auf der Geräteseite oder auf der Erweiterten Suche überprüfen.</span><span class="sxs-lookup"><span data-stu-id="56aa9-109">You can review all recorded events in the timeline tab in the device page, or in advanced hunting page.</span></span> <span data-ttu-id="56aa9-110">In diesem Abschnitt wird der Fall behoben, dass einige oder alle erwarteten Ereignisse fehlen.</span><span class="sxs-lookup"><span data-stu-id="56aa9-110">This section troubleshoots the case of some or all expected events are missing.</span></span>
<span data-ttu-id="56aa9-111">Wenn beispielsweise alle _CreatedFile-Ereignisse_ fehlen.</span><span class="sxs-lookup"><span data-stu-id="56aa9-111">For instance, if all _CreatedFile_ events are missing.</span></span>

## <a name="missing-network-and-login-events"></a><span data-ttu-id="56aa9-112">Fehlende Netzwerk- und Anmeldeereignisse</span><span class="sxs-lookup"><span data-stu-id="56aa9-112">Missing network and login events</span></span>

<span data-ttu-id="56aa9-113">Microsoft Defender for Endpoint nutzte `audit` framework from linux, um Netzwerk- und Anmeldeaktivitäten nachverfolgt zu werden.</span><span class="sxs-lookup"><span data-stu-id="56aa9-113">Microsoft Defender for Endpoint utilized `audit` framework from linux to track network and login activity.</span></span>

1. <span data-ttu-id="56aa9-114">Stellen Sie sicher, dass das Überwachungsframework funktioniert.</span><span class="sxs-lookup"><span data-stu-id="56aa9-114">Make sure audit framework is working.</span></span>

    ```bash
    service auditd status
    ```

    <span data-ttu-id="56aa9-115">Erwartete Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="56aa9-115">expected output:</span></span>

    ```output
    ● auditd.service - Security Auditing Service
    Loaded: loaded (/usr/lib/systemd/system/auditd.service; enabled; vendor preset: enabled)
    Active: active (running) since Mon 2020-12-21 10:48:02 IST; 2 weeks 0 days ago
        Docs: man:auditd(8)
            https://github.com/linux-audit/audit-documentation
    Process: 16689 ExecStartPost=/sbin/augenrules --load (code=exited, status=1/FAILURE)
    Process: 16665 ExecStart=/sbin/auditd (code=exited, status=0/SUCCESS)
    Main PID: 16666 (auditd)
        Tasks: 25
    CGroup: /system.slice/auditd.service
            ├─16666 /sbin/auditd
            ├─16668 /sbin/audispd
            ├─16670 /usr/sbin/sedispatch
            └─16671 /opt/microsoft/mdatp/sbin/mdatp_audisp_plugin -d
    ```

2. <span data-ttu-id="56aa9-116">Wenn `auditd` als beendet markiert ist, starten Sie es.</span><span class="sxs-lookup"><span data-stu-id="56aa9-116">If `auditd` is marked as stopped, start it.</span></span>

    ```bash
    service auditd start
    ```

<span data-ttu-id="56aa9-117">**Auf SLES-Systemen** ist die SYSCALL-Überwachung in möglicherweise standardmäßig deaktiviert und kann für `auditd` fehlende Ereignisse berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="56aa9-117">**On SLES** systems, SYSCALL auditing in `auditd` might be disabled by default and can be accounted for missing events.</span></span>

1. <span data-ttu-id="56aa9-118">Um zu überprüfen, ob die SYSCALL-Überwachung nicht deaktiviert ist, listen Sie die aktuellen Überwachungsregeln auf:</span><span class="sxs-lookup"><span data-stu-id="56aa9-118">To validate that SYSCALL auditing is not disabled, list the current audit rules:</span></span>

    ```bash
    sudo auditctl -l
    ```

    <span data-ttu-id="56aa9-119">Wenn die folgende Zeile vorhanden ist, entfernen Oder bearbeiten Sie sie, damit Microsoft Defender for Endpoint bestimmte SYSCALLs nachverfolgen kann.</span><span class="sxs-lookup"><span data-stu-id="56aa9-119">if the following line is present, remove it or edit it to enable Microsoft Defender for Endpoint to track specific SYSCALLs.</span></span>

    ```output
    -a task, never
    ```

    <span data-ttu-id="56aa9-120">Überwachungsregeln befinden sich unter `/etc/audit/rules.d/audit.rules` .</span><span class="sxs-lookup"><span data-stu-id="56aa9-120">audit rules are located at `/etc/audit/rules.d/audit.rules`.</span></span>

## <a name="missing-file-events"></a><span data-ttu-id="56aa9-121">Fehlende Dateiereignisse</span><span class="sxs-lookup"><span data-stu-id="56aa9-121">Missing file events</span></span>

<span data-ttu-id="56aa9-122">Dateiereignisse werden mit framework `fanotify` erfasst.</span><span class="sxs-lookup"><span data-stu-id="56aa9-122">File events are collected with `fanotify` framework.</span></span> <span data-ttu-id="56aa9-123">Falls einige oder alle Dateiereignisse fehlen, stellen Sie sicher, dass auf dem Gerät aktiviert ist und das `fanotify` Dateisystem [unterstützt wird.](microsoft-defender-endpoint-linux.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="56aa9-123">In case some or all file events are missing, make sure `fanotify` is enabled on the device and that the file system is [supported](microsoft-defender-endpoint-linux.md#system-requirements).</span></span>

<span data-ttu-id="56aa9-124">Listet die Dateisysteme auf dem Computer auf mit:</span><span class="sxs-lookup"><span data-stu-id="56aa9-124">List the filesystems on the machine with:</span></span>

```bash
df -Th
```
