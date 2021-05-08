---
title: Ausführen und Anpassen von Bedarfsscans in Microsoft Defender Antivirus
description: Ausführen und Konfigurieren von Bedarfsscans mithilfe von PowerShell, Windows Management Instrumentation oder einzeln auf Endpunkten mit der Windows-Sicherheit App
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
ms.date: 05/05/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 124ebde48c008743a486a4454e7772fd93f9eca7
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275360"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="52cc2-104">Konfigurieren und Ausführen von bedarfsgesteuerten Scans durch Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="52cc2-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="52cc2-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="52cc2-105">**Applies to:**</span></span>

- [<span data-ttu-id="52cc2-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="52cc2-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="52cc2-107">Sie können eine Bedarfsscan auf einzelnen Endpunkten ausführen.</span><span class="sxs-lookup"><span data-stu-id="52cc2-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="52cc2-108">Diese Überprüfungen werden sofort gestartet, und Sie können Parameter für die Überprüfung definieren, z. B. den Speicherort oder Typ.</span><span class="sxs-lookup"><span data-stu-id="52cc2-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="52cc2-109">Schnellscan im Vergleich zum vollständigen Scan</span><span class="sxs-lookup"><span data-stu-id="52cc2-109">Quick scan versus full scan</span></span>

<span data-ttu-id="52cc2-110">Die Schnellscans sehen sich alle Speicherorte an, an denen Schadsoftware registriert werden könnte, um mit dem System zu beginnen, z. B. Registrierungsschlüssel und bekannte Windows Startordner.</span><span class="sxs-lookup"><span data-stu-id="52cc2-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52cc2-111">Microsoft Defender Antivirus wird beim Ausführen einer lokalen Überprüfung im Kontext des [LocalSystem-Kontos](/windows/win32/services/localsystem-account) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="52cc2-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="52cc2-112">Für Netzwerkscans verwendet es den Kontext des Gerätekontos.</span><span class="sxs-lookup"><span data-stu-id="52cc2-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="52cc2-113">Wenn das Domänengerätekonto nicht über die entsprechenden Berechtigungen für den Zugriff auf die Freigabe verfügt, funktioniert die Überprüfung nicht.</span><span class="sxs-lookup"><span data-stu-id="52cc2-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="52cc2-114">Stellen Sie sicher, dass das Gerät über Berechtigungen für die Zugriffsnetzwerkfreigabe verfügt.</span><span class="sxs-lookup"><span data-stu-id="52cc2-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="52cc2-115">In Kombination mit der [Immer-on-Echtzeitschutzfunktion](configure-real-time-protection-microsoft-defender-antivirus.md), die Dateien überprüft, wenn sie geöffnet und geschlossen werden, und wenn ein Benutzer zu einem Ordner navigiert, bietet ein Schnellscan eine starke Abdeckung sowohl für Schadsoftware, die mit dem System beginnt, als auch für Schadsoftware auf Kernelebene.</span><span class="sxs-lookup"><span data-stu-id="52cc2-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md)--which reviews files when they're opened and closed, and whenever a user navigates to a folder--a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="52cc2-116">In den meisten Fällen ist eine schnelle Überprüfung ausreichend, um Schadsoftware zu finden, die nicht vom Echtzeitschutz aufgegriffen wurde.</span><span class="sxs-lookup"><span data-stu-id="52cc2-116">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="52cc2-117">Eine vollständige Überprüfung kann für Endpunkte nützlich sein, die eine Schadsoftwarebedrohung gemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="52cc2-117">A full scan can be useful on endpoints that have reported a malware threat.</span></span> <span data-ttu-id="52cc2-118">Bei der Überprüfung kann ermittelt werden, ob inaktive Komponenten enthalten sind, die eine gründlichere Bereinigung erfordern.</span><span class="sxs-lookup"><span data-stu-id="52cc2-118">The scan can identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="52cc2-119">Dies ist ideal, wenn In-Demand-Scans in Ihrer Organisation ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="52cc2-119">This is  ideal if your organization is running on-demand scans.</span></span>

> [!NOTE]
> <span data-ttu-id="52cc2-120">Standardmäßig werden Schnellscans auf angeschlossenen Wechselmedien ausgeführt, z. B. USB-Laufwerken.</span><span class="sxs-lookup"><span data-stu-id="52cc2-120">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="52cc2-121">Verwenden Microsoft Endpoint Manager zum Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="52cc2-121">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="52cc2-122">Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="52cc2-122">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="52cc2-123">Wählen **Sie Endpoint security**  >  **Antivirus** aus.</span><span class="sxs-lookup"><span data-stu-id="52cc2-123">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="52cc2-124">Wählen Sie in der Liste der Registerkarten **Windows 10 fehlerhafte Endpunkte aus.**</span><span class="sxs-lookup"><span data-stu-id="52cc2-124">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="52cc2-125">Wählen Sie in der Liste der bereitgestellten Aktionen **Schnellscan** oder **Vollständige Überprüfung aus.**</span><span class="sxs-lookup"><span data-stu-id="52cc2-125">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="52cc2-126">[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="52cc2-126">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="52cc2-127">Weitere Informationen zur Verwendung von Microsoft Endpoint Manager zum Ausführen einer Überprüfung finden Sie unter [Antischalware-](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)und Firewallaufgaben: Ausführen einer Anforderungsscan.</span><span class="sxs-lookup"><span data-stu-id="52cc2-127">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="52cc2-128">Verwenden des mpcmdrun.exe Befehlszeilenprogramms zum Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="52cc2-128">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="52cc2-129">Verwenden Sie den folgenden `-scan` Parameter:</span><span class="sxs-lookup"><span data-stu-id="52cc2-129">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="52cc2-130">Weitere Informationen zur Verwendung des Tools und zu zusätzlichen Parametern, z. B. zum Starten einer vollständigen Überprüfung oder zum Definieren von Pfaden, finden Sie unter Verwenden des [Befehlszeilentools mpcmdrun.exe](command-line-arguments-microsoft-defender-antivirus.md)zum Konfigurieren und Verwalten Microsoft Defender Antivirus .</span><span class="sxs-lookup"><span data-stu-id="52cc2-130">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="52cc2-131">Verwenden Microsoft Intune zum Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="52cc2-131">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="52cc2-132">Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="52cc2-132">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="52cc2-133">Wählen Sie auf der Seitenleiste **Geräte > Alle Geräte aus,** und wählen Sie das Gerät aus, das Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="52cc2-133">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="52cc2-134">Wählen Sie **... aus. Weitere .**</span><span class="sxs-lookup"><span data-stu-id="52cc2-134">Select **...More**.</span></span> <span data-ttu-id="52cc2-135">Wählen Sie in den Optionen **Schnellscan oder** **Vollständige Überprüfung aus.**</span><span class="sxs-lookup"><span data-stu-id="52cc2-135">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="52cc2-136">Verwenden der Windows-Sicherheit-App zum Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="52cc2-136">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="52cc2-137">Anweisungen zum Ausführen einer Überprüfung auf einzelnen [Endpunkten finden](microsoft-defender-security-center-antivirus.md) Sie unter Ausführen einer Überprüfung in der Windows-Sicherheit-App.</span><span class="sxs-lookup"><span data-stu-id="52cc2-137">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="52cc2-138">Verwenden von PowerShell-Cmdlets zum Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="52cc2-138">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="52cc2-139">Verwenden Sie das folgende Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="52cc2-139">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="52cc2-140">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Use PowerShell cmdlets to configure](use-powershell-cmdlets-microsoft-defender-antivirus.md) and run Microsoft Defender Antivirus and Defender [cmdlets](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="52cc2-140">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="52cc2-141">Verwenden Windows Management Instruction (WMI) zum Ausführen einer Überprüfung</span><span class="sxs-lookup"><span data-stu-id="52cc2-141">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="52cc2-142">Verwenden Sie [ **die Start-Methode**](/previous-versions/windows/desktop/defender/start-msft-mpscan) der **MSFT_MpScan** Klasse.</span><span class="sxs-lookup"><span data-stu-id="52cc2-142">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="52cc2-143">Weitere Informationen zu den zulässigen Parametern finden Sie [unter Windows Defender WMIv2-APIs.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="52cc2-143">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="52cc2-144">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="52cc2-144">Related articles</span></span>

- [<span data-ttu-id="52cc2-145">Konfigurieren der Scanoptionen von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="52cc2-145">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="52cc2-146">Konfigurieren geplanter Microsoft Defender Antivirus Scans</span><span class="sxs-lookup"><span data-stu-id="52cc2-146">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="52cc2-147">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="52cc2-147">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)