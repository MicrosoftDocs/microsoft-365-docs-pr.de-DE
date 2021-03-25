---
title: Schützen wichtiger Ordner vor Ransomware vor der Verschlüsselung Ihrer Dateien mit kontrolliertem Ordnerzugriff
description: Dateien in Standardordnern können vor der Änderung durch schädliche Apps geschützt werden. Verhindern, dass Ransomware Ihre Dateien verschlüsselt.
keywords: Kontrollierter Ordnerzugriff, Windows 10, Windows Defender, Ransomware, Protect, Dateien, Ordner
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 02/03/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: b937dd41f0296f2cf4102f41f8ab10bd55e1c35d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51200281"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a><span data-ttu-id="79f94-105">Schützen wichtiger Ordner mit kontrolliertem Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="79f94-105">Protect important folders with controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="79f94-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="79f94-106">**Applies to:**</span></span>
- [<span data-ttu-id="79f94-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="79f94-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="79f94-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79f94-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="79f94-109">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="79f94-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="79f94-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="79f94-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a><span data-ttu-id="79f94-111">Was ist kontrollierter Ordnerzugriff?</span><span class="sxs-lookup"><span data-stu-id="79f94-111">What is controlled folder access?</span></span>

<span data-ttu-id="79f94-112">Der kontrollierte Ordnerzugriff schützt Ihre wertvollen Daten vor schädlichen Apps und Bedrohungen, z. B. Ransomware.</span><span class="sxs-lookup"><span data-stu-id="79f94-112">Controlled folder access helps protect your valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="79f94-113">Der kontrollierte Ordnerzugriff schützt Ihre Daten, indem Apps mit einer Liste bekannter, vertrauenswürdiger Apps überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="79f94-113">Controlled folder access protects your data by checking apps against a list of known, trusted apps.</span></span> <span data-ttu-id="79f94-114">Unterstützt auf Windows Server 2019- und Windows 10-Clients kann der kontrollierte Ordnerzugriff mit der Windows Security App, Microsoft Endpoint Configuration Manager oder Intune (für verwaltete Geräte) aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="79f94-114">Supported on Windows Server 2019 and Windows 10 clients, controlled folder access can be turned on using the Windows Security App, Microsoft Endpoint Configuration Manager, or Intune (for managed devices).</span></span> 

> [!NOTE]
> <span data-ttu-id="79f94-115">Skriptmodule sind nicht vertrauenswürdig, und Sie können ihnen keinen Zugriff auf kontrollierte geschützte Ordner erlauben.</span><span class="sxs-lookup"><span data-stu-id="79f94-115">Scripting engines are not trusted and you cannot allow them access to controlled protected folders.</span></span>  <span data-ttu-id="79f94-116">Beispielsweise wird PowerShell nicht durch kontrollierten Ordnerzugriff vertrauenswürdig, auch wenn Sie dies mit Zertifikat- und [Dateiindikatoren zulassen.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)</span><span class="sxs-lookup"><span data-stu-id="79f94-116">For example, PowerShell is not trusted by controlled folder access, even if you allow with [certificate and file indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span> 

<span data-ttu-id="79f94-117">Der kontrollierte Ordnerzugriff funktioniert am besten mit [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), mit dem Sie detaillierte Berichte zu Ereignissen und Blöcken für den kontrollierten Ordnerzugriff im Rahmen der üblichen Warnungsuntersuchungsszenarien erstellen [können.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="79f94-117">Controlled folder access works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into controlled folder access events and blocks as part of the usual [alert investigation scenarios](investigate-alerts.md).</span></span>

> [!TIP]
> <span data-ttu-id="79f94-118">Kontrollierte Ordnerzugriffsblöcke generieren keine Warnungen in der [Warnungswarteschlange.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="79f94-118">Controlled folder access blocks don't generate alerts in the [Alerts queue](alerts-queue.md).</span></span> <span data-ttu-id="79f94-119">Sie können jedoch Informationen zu zugriffsgesteuerten Ordnerblöcken in [](advanced-hunting-overview.md)der Gerätezeitachsenansicht [anzeigen,](investigate-machines.md)während Sie erweiterte Suche oder benutzerdefinierte [Erkennungsregeln verwenden.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="79f94-119">However, you can view information about controlled folder access blocks in the [device timeline view](investigate-machines.md), while using [advanced hunting](advanced-hunting-overview.md), or with [custom detection rules](custom-detection-rules.md).</span></span>

## <a name="how-does-controlled-folder-access-work"></a><span data-ttu-id="79f94-120">Wie funktioniert der kontrollierte Ordnerzugriff?</span><span class="sxs-lookup"><span data-stu-id="79f94-120">How does controlled folder access work?</span></span>

<span data-ttu-id="79f94-121">Der kontrollierte Ordnerzugriff funktioniert, indem nur vertrauenswürdige Apps auf geschützte Ordner zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="79f94-121">Controlled folder access works by only allowing trusted apps to access protected folders.</span></span> <span data-ttu-id="79f94-122">Geschützte Ordner werden angegeben, wenn der kontrollierte Ordnerzugriff konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="79f94-122">Protected folders are specified when controlled folder access is configured.</span></span> <span data-ttu-id="79f94-123">In der Regel werden häufig verwendete Ordner, z. B. für Dokumente, Bilder, Downloads und so weiter, in die Liste der kontrollierten Ordner aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="79f94-123">Typically, commonly used folders, such as those used for documents, pictures, downloads, and so on, are included in the list of controlled folders.</span></span> 

<span data-ttu-id="79f94-124">Der kontrollierte Ordnerzugriff funktioniert mit einer Liste vertrauenswürdiger Apps.</span><span class="sxs-lookup"><span data-stu-id="79f94-124">Controlled folder access works with a list of trusted apps.</span></span> <span data-ttu-id="79f94-125">Apps, die in der Liste der vertrauenswürdigen Software enthalten sind, funktionieren wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="79f94-125">Apps that are included in the list of trusted software work as expected.</span></span> <span data-ttu-id="79f94-126">Apps, die nicht in der Liste enthalten sind, können keine Änderungen an Dateien in geschützten Ordnern vornehmen.</span><span class="sxs-lookup"><span data-stu-id="79f94-126">Apps that are not included in the list are prevented from making any changes to files inside protected folders.</span></span> 

<span data-ttu-id="79f94-127">Apps werden der Liste basierend auf ihrer Verbreitung und Reputation hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="79f94-127">Apps are added to the list based upon their prevalence and reputation.</span></span> <span data-ttu-id="79f94-128">Apps, die in Ihrer gesamten Organisation stark verbreitet sind und niemals ein als schädlich eingestuftes Verhalten angezeigt haben, gelten als vertrauenswürdig.</span><span class="sxs-lookup"><span data-stu-id="79f94-128">Apps that are highly prevalent throughout your organization and that have never displayed any behavior deemed malicious are considered trustworthy.</span></span> <span data-ttu-id="79f94-129">Diese Apps werden der Liste automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="79f94-129">Those apps are added to the list automatically.</span></span>

<span data-ttu-id="79f94-130">Apps können auch manuell mithilfe von Configuration Manager oder Intune zur vertrauenswürdigen Liste hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="79f94-130">Apps can also be added manually to the trusted list by using Configuration Manager or Intune.</span></span> <span data-ttu-id="79f94-131">Zusätzliche Aktionen, z. [B. das Hinzufügen eines Dateiindikators](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) für eine App, können über die Security Center Console ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="79f94-131">Additional actions, such as [adding a file indicator](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) for an app, can be performed from the Security Center Console.</span></span>

## <a name="why-controlled-folder-access-is-important"></a><span data-ttu-id="79f94-132">Warum der kontrollierte Ordnerzugriff wichtig ist</span><span class="sxs-lookup"><span data-stu-id="79f94-132">Why controlled folder access is important</span></span>

<span data-ttu-id="79f94-133">Der kontrollierte Ordnerzugriff ist besonders hilfreich, um Ihre Dokumente und Informationen vor Ransomware [zu schützen.](https://www.microsoft.com/wdsi/threats/ransomware)</span><span class="sxs-lookup"><span data-stu-id="79f94-133">Controlled folder access is especially useful in helping to protect your documents and information from [ransomware](https://www.microsoft.com/wdsi/threats/ransomware).</span></span> <span data-ttu-id="79f94-134">Bei einem Ransomware-Angriff können Ihre Dateien verschlüsselt und als Host gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="79f94-134">In a ransomware attack, your files can get encrypted and held hostage.</span></span> <span data-ttu-id="79f94-135">Bei kontrolliertem Ordnerzugriff wird eine Benachrichtigung auf dem Computer angezeigt, auf dem eine App versucht hat, Änderungen an einer Datei in einem geschützten Ordner vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="79f94-135">With controlled folder access in place, a notification appears on the computer where an app attempted to make changes to a file in a protected folder.</span></span> <span data-ttu-id="79f94-136">Sie können [die Benachrichtigung mit](customize-attack-surface-reduction.md#customize-the-notification) Ihren Unternehmensdetails und Kontaktinformationen anpassen.</span><span class="sxs-lookup"><span data-stu-id="79f94-136">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span> <span data-ttu-id="79f94-137">Sie können die Regeln auch einzeln aktivieren, um anzupassen, welche Techniken das Feature überwacht.</span><span class="sxs-lookup"><span data-stu-id="79f94-137">You can also enable the rules individually to customize what techniques the feature monitors.</span></span>

<span data-ttu-id="79f94-138">Die [geschützten Ordner](#review-controlled-folder-access-events-in-windows-event-viewer) enthalten allgemeine Systemordner (einschließlich Startsektoren), und Sie können [weitere Ordner hinzufügen.](customize-controlled-folders.md#protect-additional-folders)</span><span class="sxs-lookup"><span data-stu-id="79f94-138">The [protected folders](#review-controlled-folder-access-events-in-windows-event-viewer) include common system folders (including boot sectors), and you can [add more folders](customize-controlled-folders.md#protect-additional-folders).</span></span> <span data-ttu-id="79f94-139">Sie können Apps [auch den](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) Zugriff auf die geschützten Ordner ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="79f94-139">You can also [allow apps](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) to give them access to the protected folders.</span></span>

<span data-ttu-id="79f94-140">Sie können den [Überwachungsmodus verwenden,](audit-windows-defender.md) um zu bewerten, wie sich der kontrollierte Ordnerzugriff auf Ihre Organisation auswirken würde, wenn er aktiviert wäre.</span><span class="sxs-lookup"><span data-stu-id="79f94-140">You can use [audit mode](audit-windows-defender.md) to evaluate how controlled folder access would impact your organization if it were enabled.</span></span> <span data-ttu-id="79f94-141">Sie können auch die Windows Defender test ground website unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass das Feature funktioniert und wie es funktioniert.</span><span class="sxs-lookup"><span data-stu-id="79f94-141">You can also visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

<span data-ttu-id="79f94-142">Der kontrollierte Ordnerzugriff wird unter den folgenden Versionen von Windows unterstützt:</span><span class="sxs-lookup"><span data-stu-id="79f94-142">Controlled folder access is supported on the following versions of Windows:</span></span>
- <span data-ttu-id="79f94-143">[Windows 10, Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) und höher</span><span class="sxs-lookup"><span data-stu-id="79f94-143">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) and later</span></span>
- [<span data-ttu-id="79f94-144">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="79f94-144">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a><span data-ttu-id="79f94-145">Windows-Systemordner sind standardmäßig geschützt</span><span class="sxs-lookup"><span data-stu-id="79f94-145">Windows system folders are protected by default</span></span>

<span data-ttu-id="79f94-146">Windows-Systemordner sind zusammen mit mehreren anderen Ordnern standardmäßig geschützt:</span><span class="sxs-lookup"><span data-stu-id="79f94-146">Windows system folders are protected by default, along with several other folders:</span></span> 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> <span data-ttu-id="79f94-147">Sie können zusätzliche Ordner als geschützt konfigurieren, aber sie können die standardmäßig geschützten Windows-Systemordner nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="79f94-147">You can configure additional folders as protected, but you cannot remove the Windows system folders that are protected by default.</span></span>

## <a name="requirements-for-controlled-folder-access"></a><span data-ttu-id="79f94-148">Anforderungen für den kontrollierten Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="79f94-148">Requirements for controlled folder access</span></span>

<span data-ttu-id="79f94-149">Der kontrollierte Ordnerzugriff erfordert die [Aktivierung des Microsoft Defender Antivirus-Echtzeitschutzes.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="79f94-149">Controlled folder access requires enabling [Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

## <a name="review-controlled-folder-access-events-in-the-microsoft-defender-security-center"></a><span data-ttu-id="79f94-150">Überprüfen von Ereignissen für den kontrollierten Ordnerzugriff im Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="79f94-150">Review controlled folder access events in the Microsoft Defender Security Center</span></span>

<span data-ttu-id="79f94-151">Defender for Endpoint bietet detaillierte Berichte zu Ereignissen und Blöcken im Rahmen seiner [Warnungsuntersuchungsszenarien.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="79f94-151">Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="79f94-152">Sie können Microsoft Defender for Endpoint-Daten mithilfe der erweiterten [Suche abfragen.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="79f94-152">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="79f94-153">Wenn Sie den Überwachungsmodus [verwenden,](audit-windows-defender.md)können Sie die erweiterte Suche verwenden, um zu sehen, wie sich die Einstellungen für den kontrollierten Ordnerzugriff auf Ihre Umgebung auswirken würden, wenn sie aktiviert wären. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="79f94-153">If you're using [audit mode](audit-windows-defender.md), you can use [advanced hunting](advanced-hunting-overview.md) to see how controlled folder access settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="79f94-154">Beispielabfrage:</span><span class="sxs-lookup"><span data-stu-id="79f94-154">Example query:</span></span>

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="79f94-155">Überprüfen von Ereignissen für den kontrollierten Ordnerzugriff in der Windows-Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="79f94-155">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="79f94-156">Sie können das Windows-Ereignisprotokoll überprüfen, um Ereignisse zu sehen, die erstellt werden, wenn kontrollierte Ordnerzugriffsblöcke (oder Überwachungen) einer App ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="79f94-156">You can review the Windows event log to see events that are created when controlled folder access blocks (or audits) an app:</span></span>

1. <span data-ttu-id="79f94-157">Laden Sie [das Evaluierungspaket](https://aka.ms/mp7z2w) herunter, und *extrahierencfa-events.xml* an einen leicht zugänglichen Speicherort auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="79f94-157">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>
2. <span data-ttu-id="79f94-158">Geben **Sie die Ereignisanzeige** im Menü Start ein, um die Windows-Ereignisanzeige zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="79f94-158">Type **Event viewer** in the Start menu to open the Windows Event Viewer.</span></span>
3. <span data-ttu-id="79f94-159">Wählen Sie im linken Bereich unter **Aktionen** die Option **Benutzerdefinierte Ansicht importieren... aus.**</span><span class="sxs-lookup"><span data-stu-id="79f94-159">On the left panel, under **Actions**, select **Import custom view...**.</span></span>
4. <span data-ttu-id="79f94-160">Navigieren Sie zu dem Ort, an *demcfa-events.xml* extrahiert haben, und wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="79f94-160">Navigate to where you extracted *cfa-events.xml* and select it.</span></span> <span data-ttu-id="79f94-161">Alternativ können [Sie die XML direkt kopieren.](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="79f94-161">Alternatively, [copy the XML directly](event-views.md).</span></span>
5. <span data-ttu-id="79f94-162">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="79f94-162">Select **OK**.</span></span>

<span data-ttu-id="79f94-163">In der folgenden Tabelle sind Ereignisse im Zusammenhang mit dem kontrollierten Ordnerzugriff aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="79f94-163">The following table shows events related to controlled folder access:</span></span>

|<span data-ttu-id="79f94-164">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="79f94-164">Event ID</span></span> | <span data-ttu-id="79f94-165">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79f94-165">Description</span></span> |
|:---|:---|
|<span data-ttu-id="79f94-166">5007</span><span class="sxs-lookup"><span data-stu-id="79f94-166">5007</span></span> | <span data-ttu-id="79f94-167">Ereignis, wenn Einstellungen geändert werden</span><span class="sxs-lookup"><span data-stu-id="79f94-167">Event when settings are changed</span></span> |
|<span data-ttu-id="79f94-168">1124</span><span class="sxs-lookup"><span data-stu-id="79f94-168">1124</span></span> | <span data-ttu-id="79f94-169">Überwachtes kontrolliertes Ordnerzugriffsereignis</span><span class="sxs-lookup"><span data-stu-id="79f94-169">Audited controlled folder access event</span></span> | 
|<span data-ttu-id="79f94-170">1123</span><span class="sxs-lookup"><span data-stu-id="79f94-170">1123</span></span> | <span data-ttu-id="79f94-171">Blockiertes Ereignis für den kontrollierten Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="79f94-171">Blocked controlled folder access event</span></span> |

## <a name="view-or-change-the-list-of-protected-folders"></a><span data-ttu-id="79f94-172">Anzeigen oder Ändern der Liste geschützter Ordner</span><span class="sxs-lookup"><span data-stu-id="79f94-172">View or change the list of protected folders</span></span>

<span data-ttu-id="79f94-173">Mit der Windows Security-App können Sie die Liste der Ordner anzeigen, die durch den kontrollierten Ordnerzugriff geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="79f94-173">You can use the Windows Security app to view the list of folders that are protected by controlled folder access.</span></span> 

1. <span data-ttu-id="79f94-174">Öffnen Sie auf Ihrem Windows 10-Gerät die Windows Security-App.</span><span class="sxs-lookup"><span data-stu-id="79f94-174">On your Windows 10 device, open the Windows Security app.</span></span>
2. <span data-ttu-id="79f94-175">Wählen **Sie Virenschutz & Bedrohungsschutz aus.**</span><span class="sxs-lookup"><span data-stu-id="79f94-175">Select **Virus & threat protection**.</span></span>
3. <span data-ttu-id="79f94-176">Wählen **Sie unter Ransomware-Schutz** die Option **Ransomware-Schutz verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="79f94-176">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>
4. <span data-ttu-id="79f94-177">Wenn der kontrollierte Ordnerzugriff deaktiviert ist, müssen Sie ihn aktivieren.</span><span class="sxs-lookup"><span data-stu-id="79f94-177">If controlled folder access is turned off, you'll need to turn it on.</span></span> <span data-ttu-id="79f94-178">Wählen **Sie geschützte Ordner aus.**</span><span class="sxs-lookup"><span data-stu-id="79f94-178">Select **protected folders**.</span></span>
5. <span data-ttu-id="79f94-179">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="79f94-179">Do one of the following steps:</span></span>
   - <span data-ttu-id="79f94-180">Wählen Sie + Einen geschützten Ordner hinzufügen aus, **um einen Ordner hinzuzufügen.**</span><span class="sxs-lookup"><span data-stu-id="79f94-180">To add a folder, select **+ Add a protected folder**.</span></span>
   - <span data-ttu-id="79f94-181">Um einen Ordner zu entfernen, wählen Sie ihn aus, und wählen Sie dann **Entfernen aus.**</span><span class="sxs-lookup"><span data-stu-id="79f94-181">To remove a folder, select it, and then select **Remove**.</span></span> 

> [!NOTE]
> <span data-ttu-id="79f94-182">[Windows-Systemordner](#windows-system-folders-are-protected-by-default) sind standardmäßig geschützt, und Sie können sie nicht aus der Liste entfernen.</span><span class="sxs-lookup"><span data-stu-id="79f94-182">[Windows system folders](#windows-system-folders-are-protected-by-default) are protected by default, and you cannot remove them from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="79f94-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79f94-183">See also</span></span>

- [<span data-ttu-id="79f94-184">Bewerten des kontrollierten Ordnerzugriffs</span><span class="sxs-lookup"><span data-stu-id="79f94-184">Evaluate controlled folder access</span></span>](evaluate-controlled-folder-access.md)
- [<span data-ttu-id="79f94-185">Anpassen des kontrollierten Ordnerzugriffs</span><span class="sxs-lookup"><span data-stu-id="79f94-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
- [<span data-ttu-id="79f94-186">Weitere Ordner schützen</span><span class="sxs-lookup"><span data-stu-id="79f94-186">Protect more folders</span></span>](customize-controlled-folders.md#protect-additional-folders)
