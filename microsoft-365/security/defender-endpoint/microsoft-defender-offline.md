---
title: Microsoft Defender Offline in Windows 10
description: Sie können Microsoft Defender Offline direkt aus der Windows Defender Antivirus-App verwenden. Sie können auch verwalten, wie es in Ihrem Netzwerk bereitgestellt wird.
keywords: Scannen, Defender, offline
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: b2a6ee7c3f3ea2fb31b31d2f1db178bfd9847fbc
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007475"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a><span data-ttu-id="6274c-105">Ausführen und Überprüfen der Ergebnisse eines Microsoft Defender Offline-Scans</span><span class="sxs-lookup"><span data-stu-id="6274c-105">Run and review the results of a Microsoft Defender Offline scan</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6274c-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6274c-106">**Applies to:**</span></span>

- [<span data-ttu-id="6274c-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6274c-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="6274c-108">Microsoft Defender Offline ist ein Antischadsoftware-Scantool, mit dem Sie eine Überprüfung aus einer vertrauenswürdigen Umgebung starten und ausführen können.</span><span class="sxs-lookup"><span data-stu-id="6274c-108">Microsoft Defender Offline is an antimalware scanning tool that lets you boot and run a scan from a trusted environment.</span></span> <span data-ttu-id="6274c-109">Die Überprüfung wird von außerhalb des normalen Windows Kernels ausgeführt, sodass sie auf Schadsoftware abzielen kann, die versucht, die Windows Shell zu umgehen, z. B. Viren und Rootkits, die den Master Boot Record (MBR) infizieren oder überschreiben.</span><span class="sxs-lookup"><span data-stu-id="6274c-109">The scan runs from outside the normal Windows kernel so it can target malware that attempts to bypass the Windows shell, such as viruses and rootkits that infect or overwrite the master boot record (MBR).</span></span>

<span data-ttu-id="6274c-110">Sie können Microsoft Defender Offline verwenden, wenn Sie eine Schadsoftware-Infektion vermuten oder eine gründliche Bereinigung des Endpunkts nach einem Schadsoftwareausbruch bestätigen möchten.</span><span class="sxs-lookup"><span data-stu-id="6274c-110">You can use Microsoft Defender Offline if you suspect a malware infection, or you want to confirm a thorough clean of the endpoint after a malware outbreak.</span></span>

<span data-ttu-id="6274c-111">In Windows 10 können Microsoft Defender Offline mit einem Klick direkt aus der [Windows-Sicherheit App](microsoft-defender-security-center-antivirus.md)ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6274c-111">In Windows 10, Microsoft Defender Offline can be run with one click directly from the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="6274c-112">In früheren Versionen von Windows musste ein Benutzer Microsoft Defender Offline für startbare Medien installieren, den Endpunkt neu starten und das startbare Medium laden.</span><span class="sxs-lookup"><span data-stu-id="6274c-112">In previous versions of Windows, a user had to install Microsoft Defender Offline to bootable media, restart the endpoint, and load the bootable media.</span></span>

## <a name="prerequisites-and-requirements"></a><span data-ttu-id="6274c-113">Voraussetzungen und Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6274c-113">prerequisites and requirements</span></span>

<span data-ttu-id="6274c-114">Microsoft Defender Offline in Windows 10 hat die gleichen Hardwareanforderungen wie Windows 10.</span><span class="sxs-lookup"><span data-stu-id="6274c-114">Microsoft Defender Offline in Windows 10 has the same hardware requirements as Windows 10.</span></span> 

<span data-ttu-id="6274c-115">Weitere Informationen zu Windows 10 Anforderungen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="6274c-115">For more information about Windows 10 requirements, see the following topics:</span></span>

- [<span data-ttu-id="6274c-116">Hardware-Mindestanforderungen</span><span class="sxs-lookup"><span data-stu-id="6274c-116">Minimum hardware requirements</span></span>](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [<span data-ttu-id="6274c-117">Hardwarekomponenten-Anleitungen</span><span class="sxs-lookup"><span data-stu-id="6274c-117">Hardware component guidelines</span></span>](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> <span data-ttu-id="6274c-118">Microsoft Defender Offline wird auf Computern mit ARM-Prozessoren oder auf Windows Server Stock Keeping Units nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6274c-118">Microsoft Defender Offline is not supported on machines with ARM processors, or on Windows Server Stock Keeping Units.</span></span>

<span data-ttu-id="6274c-119">Um Microsoft Defender Offline vom Endpunkt aus auszuführen, muss der Benutzer mit Administratorrechten angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="6274c-119">To run Microsoft Defender Offline from the endpoint, the user must be logged in with administrator privileges.</span></span>
 
## <a name="microsoft-defender-offline-updates"></a><span data-ttu-id="6274c-120">Microsoft Defender Offline Updates</span><span class="sxs-lookup"><span data-stu-id="6274c-120">Microsoft Defender Offline updates</span></span>

<span data-ttu-id="6274c-121">Microsoft Defender Offline verwendet die neuesten Schutzupdates, die auf dem Endpunkt verfügbar sind; es wird immer aktualisiert, wenn Windows Defender Antivirus aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="6274c-121">Microsoft Defender Offline uses the most recent protection updates available on the endpoint; it's updated whenever Windows Defender Antivirus is updated.</span></span> 

> [!NOTE]
> <span data-ttu-id="6274c-122">Vor dem Ausführen eines Offlinescans sollten Sie versuchen, den Microsoft Defender AV-Schutz zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6274c-122">Before running an offline scan, you should attempt to update Microsoft Defender AV protection.</span></span> <span data-ttu-id="6274c-123">Sie können entweder ein Update mit einer Gruppenrichtlinie erzwingen oder updates normalerweise auf Endpunkten bereitstellen, oder Sie können die neuesten Schutzupdates aus dem [Microsoft-Center für den Schutz vor schädlicher Software](https://www.microsoft.com/security/portal/definitions/adl.aspx)manuell herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="6274c-123">You can either force an update with Group Policy or however you normally deploy updates to endpoints, or you can manually download and install the latest protection updates from the [Microsoft Malware Protection Center](https://www.microsoft.com/security/portal/definitions/adl.aspx).</span></span>

<span data-ttu-id="6274c-124">Weitere Informationen finden Sie im Thema ["Verwalten Microsoft Defender Antivirus Sicherheitsupdates](manage-protection-updates-microsoft-defender-antivirus.md) für Sicherheitsinformationen".</span><span class="sxs-lookup"><span data-stu-id="6274c-124">See the [Manage Microsoft Defender Antivirus Security intelligence  updates](manage-protection-updates-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="usage-scenarios"></a><span data-ttu-id="6274c-125">Verwendungsszenarien</span><span class="sxs-lookup"><span data-stu-id="6274c-125">Usage scenarios</span></span>

<span data-ttu-id="6274c-126">In Windows 10 Version 1607 können Sie einen Offlinescan manuell erzwingen.</span><span class="sxs-lookup"><span data-stu-id="6274c-126">In Windows 10, version 1607, you can manually force an offline scan.</span></span> <span data-ttu-id="6274c-127">Wenn Windows Defender bestimmt, dass Microsoft Defender Offline ausgeführt werden muss, fordert es den Benutzer auf dem Endpunkt auf.</span><span class="sxs-lookup"><span data-stu-id="6274c-127">Alternatively, if Windows Defender determines that Microsoft Defender Offline needs to run, it will prompt the user on the endpoint.</span></span> 

<span data-ttu-id="6274c-128">Die Notwendigkeit, einen Offlinescan durchzuführen, wird auch in Microsoft Endpoint Manager angezeigt, wenn Sie ihn zum Verwalten Ihrer Endpunkte verwenden.</span><span class="sxs-lookup"><span data-stu-id="6274c-128">The need to perform an offline scan will also be revealed in Microsoft Endpoint Manager if you're using it to manage your endpoints.</span></span>

<span data-ttu-id="6274c-129">Die Eingabeaufforderung kann über eine Benachrichtigung erfolgen, ähnlich wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="6274c-129">The prompt can occur via a notification, similar to the following:</span></span>

:::image type="content" source="../../media/notification.png" alt-text="Benachrichtigung zum Ausführen Microsoft Defender Offline":::

<span data-ttu-id="6274c-131">Der Benutzer wird auch innerhalb des Windows Defender-Clients benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="6274c-131">The user will also be notified within the Windows Defender client.</span></span>

<span data-ttu-id="6274c-132">In Configuration Manager können Sie den Status von Endpunkten ermitteln, indem Sie zu **"Monitoring > Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status"** navigieren.</span><span class="sxs-lookup"><span data-stu-id="6274c-132">In Configuration Manager, you can identify the status of endpoints by navigating to **Monitoring > Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status**.</span></span> 

<span data-ttu-id="6274c-133">Microsoft Defender Offline Scans werden unter dem Status zur **Schadsoftwarebehebung** als **Offlinescan angegeben.**</span><span class="sxs-lookup"><span data-stu-id="6274c-133">Microsoft Defender Offline scans are indicated under **Malware remediation status** as **Offline scan required**.</span></span>

:::image type="content" source="../../media/sccm-wdo.png" alt-text="Microsoft Defender Offline Überprüfung erforderlich ist":::

## <a name="configure-notifications"></a><span data-ttu-id="6274c-135">Konfigurieren von Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="6274c-135">Configure notifications</span></span>

<span data-ttu-id="6274c-136">Microsoft Defender Offline Benachrichtigungen werden in derselben Richtlinieneinstellung wie andere Microsoft Defender AV-Benachrichtigungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="6274c-136">Microsoft Defender Offline notifications are configured in the same policy setting as other Microsoft Defender AV notifications.</span></span>

<span data-ttu-id="6274c-137">Weitere Informationen zu Benachrichtigungen in Windows Defender finden Sie im Thema ["Konfigurieren der Benachrichtigungen, die auf Endpunkten angezeigt werden".](configure-notifications-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="6274c-137">For more information about notifications in Windows Defender, see the [Configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md) topic.</span></span>

## <a name="run-a-scan"></a><span data-ttu-id="6274c-138">Ausführen eines Scanvorgangs</span><span class="sxs-lookup"><span data-stu-id="6274c-138">Run a scan</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="6274c-139">Bevor Sie Microsoft Defender Offline verwenden, stellen Sie sicher, dass Sie alle Dateien speichern und ausgeführte Programme herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="6274c-139">Before you use Microsoft Defender Offline, make sure you save any files and shut down running programs.</span></span> <span data-ttu-id="6274c-140">Der Microsoft Defender Offline Scan dauert ca. 15 Minuten.</span><span class="sxs-lookup"><span data-stu-id="6274c-140">The Microsoft Defender Offline scan takes about 15 minutes to run.</span></span> <span data-ttu-id="6274c-141">Der Endpunkt wird neu gestartet, wenn der Scan abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="6274c-141">It will restart the endpoint when the scan is complete.</span></span> <span data-ttu-id="6274c-142">Die Überprüfung erfolgt außerhalb der üblichen Windows Betriebsumgebung.</span><span class="sxs-lookup"><span data-stu-id="6274c-142">The scan is performed outside of the usual Windows operating environment.</span></span> <span data-ttu-id="6274c-143">Die Benutzeroberfläche unterscheidet sich von einer normalen Überprüfung, die von Windows Defender ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6274c-143">The user interface will appear different to a normal scan performed by Windows Defender.</span></span> <span data-ttu-id="6274c-144">Nach Abschluss der Überprüfung wird der Endpunkt neu gestartet, und Windows wird normal geladen.</span><span class="sxs-lookup"><span data-stu-id="6274c-144">After the scan is completed, the endpoint will be restarted and Windows will load normally.</span></span>

<span data-ttu-id="6274c-145">Sie können einen Microsoft Defender Offline-Scan mit folgendem Code ausführen:</span><span class="sxs-lookup"><span data-stu-id="6274c-145">You can run a Microsoft Defender Offline scan with the following:</span></span>

- <span data-ttu-id="6274c-146">PowerShell</span><span class="sxs-lookup"><span data-stu-id="6274c-146">PowerShell</span></span>
- <span data-ttu-id="6274c-147">Windows-Verwaltungsinstrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="6274c-147">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="6274c-148">Die Windows-Sicherheit-App</span><span class="sxs-lookup"><span data-stu-id="6274c-148">The Windows Security app</span></span>



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a><span data-ttu-id="6274c-149">Verwenden von PowerShell-Cmdlets zum Ausführen eines Offlinescans</span><span class="sxs-lookup"><span data-stu-id="6274c-149">Use PowerShell cmdlets to run an offline scan</span></span>

<span data-ttu-id="6274c-150">Verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6274c-150">Use the following cmdlets:</span></span>

```PowerShell
Start-MpWDOScan
```

<span data-ttu-id="6274c-151">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) zum Konfigurieren und Ausführen von Microsoft Defender Antivirus und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="6274c-151">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a><span data-ttu-id="6274c-152">Verwenden Windows Management Instruction (WMI) zum Ausführen eines Offlinescans</span><span class="sxs-lookup"><span data-stu-id="6274c-152">Use Windows Management Instruction (WMI) to run an offline scan</span></span>

<span data-ttu-id="6274c-153">Verwenden Sie die [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) Klasse, um einen Offlinescan auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6274c-153">Use the [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class to run an offline scan.</span></span>

<span data-ttu-id="6274c-154">Der folgende WMI-Skriptausschnitt führt sofort eine Microsoft Defender Offline Überprüfung aus, wodurch der Endpunkt neu gestartet wird, der Offlinescan ausgeführt und dann neu gestartet und in Windows gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="6274c-154">The following WMI script snippet will immediately run a Microsoft Defender Offline scan, which will cause the endpoint to restart, run the offline scan, and then restart and boot into Windows.</span></span>

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

<span data-ttu-id="6274c-155">Weitere Informationen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="6274c-155">See the following for more information:</span></span>
- [<span data-ttu-id="6274c-156">Windows Defender WMIv2-APIs</span><span class="sxs-lookup"><span data-stu-id="6274c-156">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a><span data-ttu-id="6274c-157">Verwenden der Windows Defender Security-App zum Ausführen eines Offlinescans</span><span class="sxs-lookup"><span data-stu-id="6274c-157">Use the Windows Defender Security app to run an offline scan</span></span>

1. <span data-ttu-id="6274c-158">Öffnen Sie die Windows-Sicherheit App, indem Sie auf das Schildsymbol in der Taskleiste klicken oder das Startmenü nach **Defender** durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="6274c-158">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="6274c-159">Klicken Sie auf die Kachel **"Viren- & Bedrohungsschutz"** (oder auf das Schildsymbol auf der linken Menüleiste) und dann auf die Bezeichnung **"Erweiterter Scan":**</span><span class="sxs-lookup"><span data-stu-id="6274c-159">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Advanced scan** label:</span></span>
    
3. <span data-ttu-id="6274c-160">Wählen Sie **Microsoft Defender Offline scannen** aus, und klicken Sie auf **"Jetzt scannen".**</span><span class="sxs-lookup"><span data-stu-id="6274c-160">Select **Microsoft Defender Offline scan** and click **Scan now**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6274c-161">In Windows 10, Version 1607, kann der Offlinescan unter **Windows Einstellungen**  >  **Update & Security**  >  **Windows Defender** oder vom Windows Defender-Client ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6274c-161">In Windows 10, version 1607, the offline scan could be run from under **Windows Settings** > **Update & security** > **Windows Defender** or from the Windows Defender client.</span></span>


## <a name="review-scan-results"></a><span data-ttu-id="6274c-162">Überprüfen der Scanergebnisse</span><span class="sxs-lookup"><span data-stu-id="6274c-162">Review scan results</span></span>

<span data-ttu-id="6274c-163">Microsoft Defender Offline Scanergebnisse werden im Abschnitt ["Scanverlauf" der Windows-Sicherheit-App](microsoft-defender-security-center-antivirus.md)aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6274c-163">Microsoft Defender Offline scan results will be listed in the [Scan history section of the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> 


## <a name="related-articles"></a><span data-ttu-id="6274c-164">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="6274c-164">Related articles</span></span>

- [<span data-ttu-id="6274c-165">Anpassen, Initiieren und Überprüfen der Ergebnisse von Scans und Korrekturen</span><span class="sxs-lookup"><span data-stu-id="6274c-165">Customize, initiate, and review the results of scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6274c-166">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="6274c-166">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)