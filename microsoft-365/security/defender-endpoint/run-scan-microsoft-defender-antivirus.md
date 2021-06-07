---
title: Ausführen und Anpassen von Scans bei Bedarf in Microsoft Defender Antivirus
description: Ausführen und Konfigurieren von Scans auf Anforderung mithilfe von PowerShell, Windows Verwaltungsinstrumentation oder einzeln auf Endpunkten mit der Windows-Sicherheit-App
keywords: scan, on-demand, dos, intune, instant scan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: fdca059633ab0993e07b5b1be0c6f33cfe327fcf
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789171"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="fd0af-104">Konfigurieren und Ausführen von bedarfsgesteuerten Scans durch Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="fd0af-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="fd0af-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="fd0af-105">**Applies to:**</span></span>

- [<span data-ttu-id="fd0af-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="fd0af-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="fd0af-107">Sie können einen On-Demand-Scan auf einzelnen Endpunkten ausführen.</span><span class="sxs-lookup"><span data-stu-id="fd0af-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="fd0af-108">Diese Scans werden sofort gestartet, und Sie können Parameter für die Überprüfung definieren, z. B. den Standort oder Typ.</span><span class="sxs-lookup"><span data-stu-id="fd0af-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="fd0af-109">Schnellscan im Vergleich zum vollständigen Scan</span><span class="sxs-lookup"><span data-stu-id="fd0af-109">Quick scan versus full scan</span></span>

<span data-ttu-id="fd0af-110">Der Schnellscan überprüft alle Speicherorte, an denen Schadsoftware registriert werden könnte, um mit dem System zu beginnen, z. B. Registrierungsschlüssel und bekannte Windows Startordner.</span><span class="sxs-lookup"><span data-stu-id="fd0af-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd0af-111">Microsoft Defender Antivirus wird im Kontext des [LocalSystem-Kontos](/windows/win32/services/localsystem-account) ausgeführt, wenn eine lokale Überprüfung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fd0af-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="fd0af-112">Für Netzwerkscans wird der Kontext des Gerätekontos verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd0af-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="fd0af-113">Wenn das Domänengerätekonto nicht über die entsprechenden Berechtigungen für den Zugriff auf die Freigabe verfügt, funktioniert die Überprüfung nicht.</span><span class="sxs-lookup"><span data-stu-id="fd0af-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="fd0af-114">Stellen Sie sicher, dass das Gerät über Berechtigungen für die Zugriffsnetzwerkfreigabe verfügt.</span><span class="sxs-lookup"><span data-stu-id="fd0af-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="fd0af-115">In Kombination mit [der Immer-On-Echtzeitschutzfunktion](configure-real-time-protection-microsoft-defender-antivirus.md)bietet ein Schnellscan eine starke Abdeckung sowohl für Schadsoftware, die mit Schadsoftware auf System- als auch Kernelebene beginnt.</span><span class="sxs-lookup"><span data-stu-id="fd0af-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="fd0af-116">Immer aktivierter Echtzeitschutz überprüft Dateien, wenn sie geöffnet und geschlossen werden und wenn ein Benutzer zu einem Ordner navigiert.</span><span class="sxs-lookup"><span data-stu-id="fd0af-116">Always-on, real-time protection reviews files when they're opened and closed, and whenever a user navigates to a folder.</span></span> <span data-ttu-id="fd0af-117">Standardmäßig werden Schnellscans auf bereitgestellten Wechselmedien wie USB-Laufwerken ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fd0af-117">By default, quick scans run on mounted removable devices, such as USB drives.</span></span> <span data-ttu-id="fd0af-118">In den meisten Fällen ist ein Schnellscan ausreichend, um Schadsoftware zu finden, die nicht vom Echtzeitschutz erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="fd0af-118">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="fd0af-119">Eine vollständige Überprüfung kann nützlich sein, wenn eine Schadsoftware-Bedrohung auf einem Endpunkt gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="fd0af-119">A full scan can be useful when a malware threat is reported on an endpoint.</span></span> <span data-ttu-id="fd0af-120">Die Überprüfung kann ermitteln, ob es inaktive Komponenten gibt, die eine gründlicheere Bereinigung erfordern.</span><span class="sxs-lookup"><span data-stu-id="fd0af-120">The scan can identify whether there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="fd0af-121">Microsoft empfiehlt jedoch in der Regel die Verwendung von Schnellscans anstelle von vollständigen Scans.</span><span class="sxs-lookup"><span data-stu-id="fd0af-121">However, Microsoft generally recommends using quick scans instead of full scans.</span></span> <span data-ttu-id="fd0af-122">Ein vollständiger Scan kann einige Stunden oder Tage dauern, abhängig von der Menge und dem Typ der Daten, die gescannt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="fd0af-122">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span> 

> [!TIP]
> <span data-ttu-id="fd0af-123">Weitere Informationen zu den Unterschieden zwischen schnellen und vollständigen Scans finden Sie unter ["Schnellscan" im Vergleich zum vollständigen Scan und benutzerdefiniertem Scan.](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan)</span><span class="sxs-lookup"><span data-stu-id="fd0af-123">To learn more about the differences between quick and full scans, see [Quick scan versus full scan and custom scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan).</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="fd0af-124">Verwenden von Microsoft Endpoint Manager zum Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="fd0af-124">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="fd0af-125">Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="fd0af-125">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="fd0af-126">Wählen Sie **Endpunktsicherheits-Antivirus**  >  aus.</span><span class="sxs-lookup"><span data-stu-id="fd0af-126">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="fd0af-127">Wählen Sie in der Liste der Registerkarten **Windows 10 fehlerhafte Endpunkte aus.**</span><span class="sxs-lookup"><span data-stu-id="fd0af-127">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="fd0af-128">Wählen Sie in der Liste der bereitgestellten Aktionen **"Schnellscan"** oder **"Vollständiger Scan"** aus.</span><span class="sxs-lookup"><span data-stu-id="fd0af-128">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="fd0af-129">[![BILD ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="fd0af-129">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="fd0af-130">Weitere Informationen zur Verwendung von Microsoft Endpoint Manager zum Ausführen einer Überprüfung finden Sie unter [Antischadsoftware- und Firewallaufgaben: So führen](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)Sie eine Überprüfung nach Bedarf durch.</span><span class="sxs-lookup"><span data-stu-id="fd0af-130">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="fd0af-131">Verwenden sie das Befehlszeilenprogramm mpcmdrun.exe, um eine Überprüfung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fd0af-131">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="fd0af-132">Verwenden Sie den folgenden `-scan` Parameter:</span><span class="sxs-lookup"><span data-stu-id="fd0af-132">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="fd0af-133">Weitere Informationen zur Verwendung des Tools und zu zusätzlichen Parametern, z. B. starten einer vollständigen Überprüfung oder Definieren von Pfaden, finden Sie unter [Verwenden des mpcmdrun.exe Befehlszeilentools zum Konfigurieren und Verwalten Microsoft Defender Antivirus.](command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="fd0af-133">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="fd0af-134">Verwenden von Microsoft Intune zum Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="fd0af-134">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="fd0af-135">Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="fd0af-135">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="fd0af-136">Wählen Sie in der Seitenleiste **"Geräte > Alle Geräte"** aus, und wählen Sie das Gerät aus, das Sie scannen möchten.</span><span class="sxs-lookup"><span data-stu-id="fd0af-136">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="fd0af-137">Wählen Sie **... Weitere**.</span><span class="sxs-lookup"><span data-stu-id="fd0af-137">Select **...More**.</span></span> <span data-ttu-id="fd0af-138">Wählen Sie in den Optionen **"Schnellscan"** oder **"Vollständiger Scan"** aus.</span><span class="sxs-lookup"><span data-stu-id="fd0af-138">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="fd0af-139">Verwenden der Windows-Sicherheit-App zum Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="fd0af-139">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="fd0af-140">Anweisungen zum Ausführen einer Überprüfung auf einzelnen Endpunkten finden Sie [unter Ausführen eines Scans in der Windows-Sicherheit-App.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="fd0af-140">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="fd0af-141">Verwenden von PowerShell-Cmdlets zum Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="fd0af-141">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="fd0af-142">Verwenden Sie das folgende Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fd0af-142">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="fd0af-143">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="fd0af-143">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="fd0af-144">Verwenden Windows Management Instruction (WMI) zum Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="fd0af-144">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="fd0af-145">Verwenden Sie die [ **Start-Methode**](/previous-versions/windows/desktop/defender/start-msft-mpscan) der **MSFT_MpScan-Klasse.**</span><span class="sxs-lookup"><span data-stu-id="fd0af-145">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="fd0af-146">Weitere Informationen dazu, welche Parameter zulässig sind, finden Sie unter [Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="fd0af-146">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="fd0af-147">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="fd0af-147">Related articles</span></span>

- [<span data-ttu-id="fd0af-148">Konfigurieren der Scanoptionen von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="fd0af-148">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="fd0af-149">Konfigurieren von geplanten Microsoft Defender Antivirus Scans</span><span class="sxs-lookup"><span data-stu-id="fd0af-149">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="fd0af-150">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="fd0af-150">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)