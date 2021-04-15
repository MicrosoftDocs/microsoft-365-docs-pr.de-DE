---
title: Microsoft Defender Offline in Windows 10
description: Sie können Microsoft Defender Offline direkt über die Windows Defender Antivirus-App verwenden. Sie können auch verwalten, wie sie in Ihrem Netzwerk bereitgestellt wird.
keywords: scan, defender, offline
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b1e7e70c6ca217d3ad8859c1493598d71054f84
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765335"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a><span data-ttu-id="5eef0-105">Ausführen und Überprüfen der Ergebnisse einer Microsoft Defender Offline-Überprüfung</span><span class="sxs-lookup"><span data-stu-id="5eef0-105">Run and review the results of a Microsoft Defender Offline scan</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5eef0-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5eef0-106">**Applies to:**</span></span>

- [<span data-ttu-id="5eef0-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="5eef0-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="5eef0-108">Microsoft Defender Offline ist ein Antischadsoftwarescantool, mit dem Sie eine Überprüfung aus einer vertrauenswürdigen Umgebung starten und ausführen können.</span><span class="sxs-lookup"><span data-stu-id="5eef0-108">Microsoft Defender Offline is an antimalware scanning tool that lets you boot and run a scan from a trusted environment.</span></span> <span data-ttu-id="5eef0-109">Der Scan wird außerhalb des normalen Windows-Kernels ausgeführt, sodass er auf Schadsoftware zielen kann, die versucht, die Windows-Shell zu umgehen, z. B. Viren und Rootkits, die den Hauptstartdatensatz (Master Boot Record, MBR) infizieren oder überschreiben.</span><span class="sxs-lookup"><span data-stu-id="5eef0-109">The scan runs from outside the normal Windows kernel so it can target malware that attempts to bypass the Windows shell, such as viruses and rootkits that infect or overwrite the master boot record (MBR).</span></span>

<span data-ttu-id="5eef0-110">Sie können Microsoft Defender Offline verwenden, wenn Sie eine Schadsoftwareinfektion vermuten oder eine sorgfältige Bereinigung des Endpunkts nach einem Schadsoftwareausbruch bestätigen möchten.</span><span class="sxs-lookup"><span data-stu-id="5eef0-110">You can use Microsoft Defender Offline if you suspect a malware infection, or you want to confirm a thorough clean of the endpoint after a malware outbreak.</span></span>

<span data-ttu-id="5eef0-111">In Windows 10 kann Microsoft Defender Offline mit einem Klick direkt über die [Windows Security App ausgeführt werden.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="5eef0-111">In Windows 10, Microsoft Defender Offline can be run with one click directly from the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="5eef0-112">In früheren Versionen von Windows musste ein Benutzer Microsoft Defender Offline zum Starten von Medien installieren, den Endpunkt neu starten und die startbaren Medien laden.</span><span class="sxs-lookup"><span data-stu-id="5eef0-112">In previous versions of Windows, a user had to install Microsoft Defender Offline to bootable media, restart the endpoint, and load the bootable media.</span></span>

## <a name="prerequisites-and-requirements"></a><span data-ttu-id="5eef0-113">Voraussetzungen und Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5eef0-113">prerequisites and requirements</span></span>

<span data-ttu-id="5eef0-114">Microsoft Defender Offline in Windows 10 hat die gleichen Hardwareanforderungen wie Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5eef0-114">Microsoft Defender Offline in Windows 10 has the same hardware requirements as Windows 10.</span></span> 

<span data-ttu-id="5eef0-115">Weitere Informationen zu Windows 10-Anforderungen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="5eef0-115">For more information about Windows 10 requirements, see the following topics:</span></span>

- [<span data-ttu-id="5eef0-116">Mindesthardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="5eef0-116">Minimum hardware requirements</span></span>](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [<span data-ttu-id="5eef0-117">Richtlinien für Hardwarekomponenten</span><span class="sxs-lookup"><span data-stu-id="5eef0-117">Hardware component guidelines</span></span>](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> <span data-ttu-id="5eef0-118">Microsoft Defender Offline wird nicht auf Computern mit ARM Oder auf Windows Server Stock Keeping Units unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5eef0-118">Microsoft Defender Offline is not supported on machines with ARM processors, or on Windows Server Stock Keeping Units.</span></span>

<span data-ttu-id="5eef0-119">Um Microsoft Defender Offline vom Endpunkt aus ausführen zu können, muss der Benutzer mit Administratorrechten angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="5eef0-119">To run Microsoft Defender Offline from the endpoint, the user must be logged in with administrator privileges.</span></span>
 
## <a name="microsoft-defender-offline-updates"></a><span data-ttu-id="5eef0-120">Microsoft Defender Offline-Updates</span><span class="sxs-lookup"><span data-stu-id="5eef0-120">Microsoft Defender Offline updates</span></span>

<span data-ttu-id="5eef0-121">Microsoft Defender Offline verwendet die neuesten auf dem Endpunkt verfügbaren Schutzupdates. es wird immer dann aktualisiert, Windows Defender Antivirus aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="5eef0-121">Microsoft Defender Offline uses the most recent protection updates available on the endpoint; it's updated whenever Windows Defender Antivirus is updated.</span></span> 

> [!NOTE]
> <span data-ttu-id="5eef0-122">Bevor Sie einen Offlinescan ausführen, sollten Sie versuchen, den Microsoft Defender AV-Schutz zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5eef0-122">Before running an offline scan, you should attempt to update Microsoft Defender AV protection.</span></span> <span data-ttu-id="5eef0-123">Sie können entweder ein Update mit Gruppenrichtlinien erzwingen oder aber normalerweise Updates auf Endpunkten [bereitstellen,](https://www.microsoft.com/security/portal/definitions/adl.aspx)oder Sie können die neuesten Schutzupdates manuell aus dem Microsoft Center zum Schutz vor Malware.</span><span class="sxs-lookup"><span data-stu-id="5eef0-123">You can either force an update with Group Policy or however you normally deploy updates to endpoints, or you can manually download and install the latest protection updates from the [Microsoft Malware Protection Center](https://www.microsoft.com/security/portal/definitions/adl.aspx).</span></span>

<span data-ttu-id="5eef0-124">Weitere Informationen finden Sie im Thema Verwalten von [Microsoft Defender Antivirus Security Intelligence-Updates.](manage-protection-updates-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="5eef0-124">See the [Manage Microsoft Defender Antivirus Security intelligence  updates](manage-protection-updates-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="usage-scenarios"></a><span data-ttu-id="5eef0-125">Verwendungsszenarien</span><span class="sxs-lookup"><span data-stu-id="5eef0-125">Usage scenarios</span></span>

<span data-ttu-id="5eef0-126">In Windows 10, Version 1607, können Sie einen Offlinescan manuell erzwingen.</span><span class="sxs-lookup"><span data-stu-id="5eef0-126">In Windows 10, version 1607, you can manually force an offline scan.</span></span> <span data-ttu-id="5eef0-127">Wenn sie Windows Defender, dass Microsoft Defender Offline ausgeführt werden muss, wird der Benutzer auf dem Endpunkt aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="5eef0-127">Alternatively, if Windows Defender determines that Microsoft Defender Offline needs to run, it will prompt the user on the endpoint.</span></span> 

<span data-ttu-id="5eef0-128">Die Notwendigkeit, eine Offlinescan durchzuführen, wird auch im Microsoft Endpoint Manager angezeigt, wenn Sie ihn zum Verwalten Ihrer Endpunkte verwenden.</span><span class="sxs-lookup"><span data-stu-id="5eef0-128">The need to perform an offline scan will also be revealed in Microsoft Endpoint Manager if you're using it to manage your endpoints.</span></span>

<span data-ttu-id="5eef0-129">Die Eingabeaufforderung kann über eine Benachrichtigung erfolgen, ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="5eef0-129">The prompt can occur via a notification, similar to the following:</span></span>

![Windows-Benachrichtigung mit der Anforderung zum Ausführen von Microsoft Defender Offline](images/defender/notification.png)

<span data-ttu-id="5eef0-131">Der Benutzer wird auch innerhalb des Windows Defender benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="5eef0-131">The user will also be notified within the Windows Defender client.</span></span>

<span data-ttu-id="5eef0-132">In Configuration Manager können Sie den Status von Endpunkten identifizieren, indem Sie zu **Monitoring > Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status navigieren.**</span><span class="sxs-lookup"><span data-stu-id="5eef0-132">In Configuration Manager, you can identify the status of endpoints by navigating to **Monitoring > Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status**.</span></span> 

<span data-ttu-id="5eef0-133">Microsoft Defender Offline scans are indicated under **Malware remediation status** as **Offline scan required**.</span><span class="sxs-lookup"><span data-stu-id="5eef0-133">Microsoft Defender Offline scans are indicated under **Malware remediation status** as **Offline scan required**.</span></span>

![Microsoft Endpoint Manager gibt an, dass eine Microsoft Defender Offline-Überprüfung erforderlich ist](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a><span data-ttu-id="5eef0-135">Konfigurieren von Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="5eef0-135">Configure notifications</span></span>

<span data-ttu-id="5eef0-136">Microsoft Defender Offline-Benachrichtigungen werden in derselben Richtlinieneinstellung wie andere Microsoft Defender AV-Benachrichtigungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5eef0-136">Microsoft Defender Offline notifications are configured in the same policy setting as other Microsoft Defender AV notifications.</span></span>

<span data-ttu-id="5eef0-137">Weitere Informationen zu Benachrichtigungen in Windows Defender finden Sie im Thema Konfigurieren der Benachrichtigungen, [die auf Endpunkten angezeigt](configure-notifications-microsoft-defender-antivirus.md) werden.</span><span class="sxs-lookup"><span data-stu-id="5eef0-137">For more information about notifications in Windows Defender, see the [Configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md) topic.</span></span>

## <a name="run-a-scan"></a><span data-ttu-id="5eef0-138">Ausführen eines Scanvorgangs</span><span class="sxs-lookup"><span data-stu-id="5eef0-138">Run a scan</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="5eef0-139">Bevor Sie Microsoft Defender Offline verwenden, stellen Sie sicher, dass Sie alle Dateien speichern und ausgeführte Programme herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="5eef0-139">Before you use Microsoft Defender Offline, make sure you save any files and shut down running programs.</span></span> <span data-ttu-id="5eef0-140">Die Ausführung der Microsoft Defender Offline-Überprüfung dauert ca. 15 Minuten.</span><span class="sxs-lookup"><span data-stu-id="5eef0-140">The Microsoft Defender Offline scan takes about 15 minutes to run.</span></span> <span data-ttu-id="5eef0-141">Der Endpunkt wird neu gestartet, wenn die Überprüfung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5eef0-141">It will restart the endpoint when the scan is complete.</span></span> <span data-ttu-id="5eef0-142">Die Überprüfung wird außerhalb der üblichen Windows-Betriebsumgebung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="5eef0-142">The scan is performed outside of the usual Windows operating environment.</span></span> <span data-ttu-id="5eef0-143">Die Benutzeroberfläche wird von einer normalen Überprüfung durch den Benutzer Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="5eef0-143">The user interface will appear different to a normal scan performed by Windows Defender.</span></span> <span data-ttu-id="5eef0-144">Nach Abschluss der Überprüfung wird der Endpunkt neu gestartet, und Windows wird normal geladen.</span><span class="sxs-lookup"><span data-stu-id="5eef0-144">After the scan is completed, the endpoint will be restarted and Windows will load normally.</span></span>

<span data-ttu-id="5eef0-145">Sie können eine Microsoft Defender Offline-Überprüfung wie folgt ausführen:</span><span class="sxs-lookup"><span data-stu-id="5eef0-145">You can run a Microsoft Defender Offline scan with the following:</span></span>

- <span data-ttu-id="5eef0-146">PowerShell</span><span class="sxs-lookup"><span data-stu-id="5eef0-146">PowerShell</span></span>
- <span data-ttu-id="5eef0-147">Windows-Verwaltungsinstrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="5eef0-147">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="5eef0-148">Die Windows Security-App</span><span class="sxs-lookup"><span data-stu-id="5eef0-148">The Windows Security app</span></span>



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a><span data-ttu-id="5eef0-149">Verwenden von PowerShell-Cmdlets zum Ausführen einer Offlinescan</span><span class="sxs-lookup"><span data-stu-id="5eef0-149">Use PowerShell cmdlets to run an offline scan</span></span>

<span data-ttu-id="5eef0-150">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="5eef0-150">Use the following cmdlets:</span></span>

```PowerShell
Start-MpWDOScan
```

<span data-ttu-id="5eef0-151">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter Verwenden von [PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus- und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="5eef0-151">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a><span data-ttu-id="5eef0-152">Ausführen eines Offlinescans mithilfe der Windows-Verwaltungsanweisung (WMI)</span><span class="sxs-lookup"><span data-stu-id="5eef0-152">Use Windows Management Instruction (WMI) to run an offline scan</span></span>

<span data-ttu-id="5eef0-153">Verwenden [](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) Sie die MSFT_MpWDOScan-Klasse, um eine Offlinescan ausführen.</span><span class="sxs-lookup"><span data-stu-id="5eef0-153">Use the [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class to run an offline scan.</span></span>

<span data-ttu-id="5eef0-154">Im folgenden WMI-Skriptausschnitt wird sofort eine Microsoft Defender Offline-Überprüfung ausgeführt, die dazu führen wird, dass der Endpunkt neu gestartet wird, der Offlinescan ausgeführt wird und dann neu gestartet und in Windows gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="5eef0-154">The following WMI script snippet will immediately run a Microsoft Defender Offline scan, which will cause the endpoint to restart, run the offline scan, and then restart and boot into Windows.</span></span>

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

<span data-ttu-id="5eef0-155">Weitere Informationen finden Sie im Folgenden:</span><span class="sxs-lookup"><span data-stu-id="5eef0-155">See the following for more information:</span></span>
- [<span data-ttu-id="5eef0-156">Windows Defender WMIv2-APIs</span><span class="sxs-lookup"><span data-stu-id="5eef0-156">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a><span data-ttu-id="5eef0-157">Verwenden der Windows Defender-Sicherheits-App zum Ausführen einer Offlinescan</span><span class="sxs-lookup"><span data-stu-id="5eef0-157">Use the Windows Defender Security app to run an offline scan</span></span>

1. <span data-ttu-id="5eef0-158">Öffnen Sie die Windows Security-App, indem Sie auf das Schildsymbol in der Aufgabenleiste klicken oder im Startmenü nach **Defender suchen.**</span><span class="sxs-lookup"><span data-stu-id="5eef0-158">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="5eef0-159">Klicken Sie **auf &** Kachel "Virenschutz" (oder auf das Schildsymbol auf der linken Menüleiste) und dann auf die **Bezeichnung Erweiterte** Überprüfung:</span><span class="sxs-lookup"><span data-stu-id="5eef0-159">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Advanced scan** label:</span></span>
    
3. <span data-ttu-id="5eef0-160">Wählen **Sie Microsoft Defender Offlinescan aus,** und klicken Sie auf Jetzt **überprüfen.**</span><span class="sxs-lookup"><span data-stu-id="5eef0-160">Select **Microsoft Defender Offline scan** and click **Scan now**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5eef0-161">In Windows 10, Version 1607, kann der Offlinescan unter **Windows Settings** Update & security Windows Defender oder vom Windows Defender  >    >   ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5eef0-161">In Windows 10, version 1607, the offline scan could be run from under **Windows Settings** > **Update & security** > **Windows Defender** or from the Windows Defender client.</span></span>


## <a name="review-scan-results"></a><span data-ttu-id="5eef0-162">Überprüfen der Scanergebnisse</span><span class="sxs-lookup"><span data-stu-id="5eef0-162">Review scan results</span></span>

<span data-ttu-id="5eef0-163">Microsoft Defender Offline-Scanergebnisse werden im Abschnitt [Scanverlauf der Windows Security App aufgeführt.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="5eef0-163">Microsoft Defender Offline scan results will be listed in the [Scan history section of the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> 


## <a name="related-articles"></a><span data-ttu-id="5eef0-164">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="5eef0-164">Related articles</span></span>

- [<span data-ttu-id="5eef0-165">Anpassen, Initiieren und Überprüfen der Ergebnisse von Scans und Korrekturen</span><span class="sxs-lookup"><span data-stu-id="5eef0-165">Customize, initiate, and review the results of scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5eef0-166">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="5eef0-166">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)