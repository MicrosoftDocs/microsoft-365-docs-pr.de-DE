---
title: Ausführen und Anpassen von Scans bei Bedarf in Microsoft Defender Antivirus
description: Ausführen und Konfigurieren von Scans bei Bedarf mithilfe von PowerShell, Windows Verwaltungsinstrumentation oder einzeln auf Endpunkten mit der Windows-Sicherheit-App
keywords: scan, on-demand, dos, intune, instant scan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b2910f9fe1c49178b8696d1a421248156b0fc4c2
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925731"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="74247-104">Konfigurieren und Ausführen von bedarfsgesteuerten Scans durch Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="74247-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="74247-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="74247-105">**Applies to:**</span></span>

- [<span data-ttu-id="74247-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="74247-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="74247-107">Sie können einen On-Demand-Scan auf einzelnen Endpunkten ausführen.</span><span class="sxs-lookup"><span data-stu-id="74247-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="74247-108">Diese Scans werden sofort gestartet, und Sie können Parameter für die Überprüfung definieren, z. B. den Standort oder Typ.</span><span class="sxs-lookup"><span data-stu-id="74247-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span> <span data-ttu-id="74247-109">Wenn Sie einen Scan ausführen, können Sie zwischen drei Typen auswählen: Schnellscan, vollständiger Scan und benutzerdefinierter Scan.</span><span class="sxs-lookup"><span data-stu-id="74247-109">When you run a scan, you can choose from among three types: Quick scan, full scan, and custom scan.</span></span> <span data-ttu-id="74247-110">Verwenden Sie in den meisten Fällen einen Schnellscan.</span><span class="sxs-lookup"><span data-stu-id="74247-110">In most cases, use a quick scan.</span></span> <span data-ttu-id="74247-111">Ein Schnellscan überprüft alle Speicherorte, an denen Schadsoftware registriert werden könnte, um mit dem System zu beginnen, z. B. Registrierungsschlüssel und bekannte Windows Startordner.</span><span class="sxs-lookup"><span data-stu-id="74247-111">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="74247-112">In Kombination mit always-on-Echtzeitschutz, der Dateien überprüft, wenn sie geöffnet und geschlossen werden, und wenn ein Benutzer zu einem Ordner navigiert, bietet ein Schnellscan starken Schutz vor Schadsoftware, die mit dem System und Schadsoftware auf Kernelebene beginnt.</span><span class="sxs-lookup"><span data-stu-id="74247-112">Combined with always-on, real-time protection, which reviews files when they are opened and closed, and whenever a user navigates to a folder, a quick scan helps provide strong protection against malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="74247-113">In den meisten Fällen ist ein Schnellscan ausreichend und die empfohlene Option für geplante oder bedarfsgesteuerte Scans.</span><span class="sxs-lookup"><span data-stu-id="74247-113">In most cases, a quick scan is sufficient and is the recommended option for scheduled or on-demand scans.</span></span>  <span data-ttu-id="74247-114">[Weitere Informationen zu Scantypen.](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan)</span><span class="sxs-lookup"><span data-stu-id="74247-114">[Learn more about scan types](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74247-115">Microsoft Defender Antivirus wird im Kontext des [LocalSystem-Kontos](/windows/win32/services/localsystem-account) ausgeführt, wenn eine lokale Überprüfung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="74247-115">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="74247-116">Für Netzwerkscans wird der Kontext des Gerätekontos verwendet.</span><span class="sxs-lookup"><span data-stu-id="74247-116">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="74247-117">Wenn das Domänengerätekonto nicht über die entsprechenden Berechtigungen für den Zugriff auf die Freigabe verfügt, funktioniert die Überprüfung nicht.</span><span class="sxs-lookup"><span data-stu-id="74247-117">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="74247-118">Stellen Sie sicher, dass das Gerät über Berechtigungen für die Zugriffsnetzwerkfreigabe verfügt.</span><span class="sxs-lookup"><span data-stu-id="74247-118">Ensure that the device has permissions to the access network share.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="74247-119">Verwenden von Microsoft Endpoint Manager zum Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="74247-119">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="74247-120">Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="74247-120">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="74247-121">Wählen Sie **Endpunktsicherheits-Antivirus**  >  aus.</span><span class="sxs-lookup"><span data-stu-id="74247-121">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="74247-122">Wählen Sie in der Liste der Registerkarten **Windows 10 fehlerhafte Endpunkte aus.**</span><span class="sxs-lookup"><span data-stu-id="74247-122">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>

4. <span data-ttu-id="74247-123">Wählen Sie in der Liste der bereitgestellten Aktionen **den Schnellscan** (empfohlen) oder **den vollständigen Scan** aus.</span><span class="sxs-lookup"><span data-stu-id="74247-123">From the list of actions provided, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

<span data-ttu-id="74247-124">[![BILD ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="74247-124">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="74247-125">Weitere Informationen zur Verwendung von Microsoft Endpoint Manager zum Ausführen einer Überprüfung finden Sie unter [Antischadsoftware- und Firewallaufgaben: So führen](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)Sie eine Überprüfung nach Bedarf durch.</span><span class="sxs-lookup"><span data-stu-id="74247-125">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="74247-126">Verwenden sie das Befehlszeilenprogramm mpcmdrun.exe, um eine Überprüfung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="74247-126">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="74247-127">Verwenden Sie den folgenden `-scan` Parameter:</span><span class="sxs-lookup"><span data-stu-id="74247-127">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="74247-128">Weitere Informationen zur Verwendung des Tools und zu zusätzlichen Parametern, z. B. zum Starten einer vollständigen Überprüfung oder zum Definieren von Pfaden, finden Sie unter [Verwenden des mpcmdrun.exe Befehlszeilentools zum Konfigurieren und Verwalten Microsoft Defender Antivirus.](command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="74247-128">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="74247-129">Verwenden von Microsoft Intune zum Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="74247-129">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="74247-130">Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="74247-130">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="74247-131">Wählen Sie in der Randleiste **"Geräte**  >  **alle Geräte"** aus, und wählen Sie das Gerät aus, das Sie scannen möchten.</span><span class="sxs-lookup"><span data-stu-id="74247-131">From the sidebar, select **Devices** > **All Devices** and choose the device you want to scan.</span></span>

3. <span data-ttu-id="74247-132">Wählen Sie **... Weitere**.</span><span class="sxs-lookup"><span data-stu-id="74247-132">Select **...More**.</span></span> <span data-ttu-id="74247-133">Wählen Sie in den Optionen **"Schnellscan** " (empfohlen) oder **"Vollständiger Scan"** aus.</span><span class="sxs-lookup"><span data-stu-id="74247-133">From the options, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="74247-134">Verwenden der Windows-Sicherheit-App zum Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="74247-134">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="74247-135">Anweisungen zum Ausführen einer Überprüfung auf einzelnen Endpunkten finden Sie [unter "Ausführen eines Scans in der Windows-Sicherheit-App".](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="74247-135">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="74247-136">Verwenden von PowerShell-Cmdlets zum Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="74247-136">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="74247-137">Verwenden Sie das folgende Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="74247-137">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="74247-138">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="74247-138">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="74247-139">Verwenden Windows Management Instruction (WMI) zum Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="74247-139">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="74247-140">Verwenden Sie die [ **Start-Methode**](/previous-versions/windows/desktop/defender/start-msft-mpscan) der **MSFT_MpScan-Klasse.**</span><span class="sxs-lookup"><span data-stu-id="74247-140">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="74247-141">Weitere Informationen dazu, welche Parameter zulässig sind, finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="74247-141">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

