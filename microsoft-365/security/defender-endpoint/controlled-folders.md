---
title: Schützen wichtiger Ordner vor Ransomware vor dem Verschlüsseln Ihrer Dateien mit kontrollierten Ordnerzugriff
description: Dateien in Standardordnern können davor geschützt werden, von schädlichen Apps geändert zu werden. Verhindern, dass Ransomware Ihre Dateien verschlüsselt.
keywords: Kontrollierter Ordnerzugriff, Windows 10, Windows Defender, Ransomware, schützen, Dateien, Ordner
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 06/10/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: c60620d2a589c8473764b810d1fcb0e24f674451
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904056"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a><span data-ttu-id="f1044-105">Schützen wichtiger Ordner mit kontrollierten Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="f1044-105">Protect important folders with controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f1044-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f1044-106">**Applies to:**</span></span>
- [<span data-ttu-id="f1044-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f1044-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f1044-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1044-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f1044-109">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="f1044-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f1044-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f1044-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a><span data-ttu-id="f1044-111">Was ist kontrollierter Ordnerzugriff?</span><span class="sxs-lookup"><span data-stu-id="f1044-111">What is controlled folder access?</span></span>

<span data-ttu-id="f1044-112">Der kontrollierte Ordnerzugriff schützt Ihre wertvollen Daten vor schädlichen Apps und Bedrohungen wie Ransomware.</span><span class="sxs-lookup"><span data-stu-id="f1044-112">Controlled folder access helps protect your valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="f1044-113">Der kontrollierte Ordnerzugriff schützt Ihre Daten, indem Apps anhand einer Liste bekannter, vertrauenswürdiger Apps überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="f1044-113">Controlled folder access protects your data by checking apps against a list of known, trusted apps.</span></span> <span data-ttu-id="f1044-114">Auf Windows Server 2019- und Windows 10-Clients unterstützt, kann der kontrollierte Ordnerzugriff mithilfe der Windows-Sicherheit App, Microsoft Endpoint Configuration Manager oder Intune (für verwaltete Geräte) aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f1044-114">Supported on Windows Server 2019 and Windows 10 clients, controlled folder access can be turned on using the Windows Security App, Microsoft Endpoint Configuration Manager, or Intune (for managed devices).</span></span> 

> [!NOTE]
> <span data-ttu-id="f1044-115">Skriptmodule sind nicht vertrauenswürdig, und Sie können ihnen keinen Zugriff auf kontrollierte geschützte Ordner gewähren.</span><span class="sxs-lookup"><span data-stu-id="f1044-115">Scripting engines are not trusted and you cannot allow them access to controlled protected folders.</span></span>  <span data-ttu-id="f1044-116">Beispielsweise wird PowerShell nicht durch kontrollierten Ordnerzugriff vertrauenswürdig, auch wenn Sie dies mit [Zertifikat- und Dateiindikatoren](/microsoft-365/security/defender-endpoint/indicator-certificates)zulassen.</span><span class="sxs-lookup"><span data-stu-id="f1044-116">For example, PowerShell is not trusted by controlled folder access, even if you allow with [certificate and file indicators](/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span> 

<span data-ttu-id="f1044-117">Der kontrollierte Ordnerzugriff funktioniert am besten mit [Microsoft Defender für Endpunkt.](microsoft-defender-endpoint.md)Dadurch erhalten Sie detaillierte Berichte zu Ereignissen und Blockierungen des kontrollierten Ordnerzugriffs im Rahmen der üblichen Szenarien zur Untersuchung von [Warnungen.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="f1044-117">Controlled folder access works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into controlled folder access events and blocks as part of the usual [alert investigation scenarios](investigate-alerts.md).</span></span>

> [!TIP]
> <span data-ttu-id="f1044-118">Kontrollierte Ordnerzugriffsblöcke generieren keine Warnungen in der [Warnungswarteschlange.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="f1044-118">Controlled folder access blocks don't generate alerts in the [Alerts queue](alerts-queue.md).</span></span> <span data-ttu-id="f1044-119">Sie können jedoch Informationen zu kontrollierten Ordnerzugriffsblöcken in der [Zeitachsenansicht](investigate-machines.md)des Geräts anzeigen, während Sie [die erweiterte Suche](advanced-hunting-overview.md)verwenden oder [benutzerdefinierte Erkennungsregeln verwenden.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="f1044-119">However, you can view information about controlled folder access blocks in the [device timeline view](investigate-machines.md), while using [advanced hunting](advanced-hunting-overview.md), or with [custom detection rules](custom-detection-rules.md).</span></span>

## <a name="how-does-controlled-folder-access-work"></a><span data-ttu-id="f1044-120">Wie funktioniert der kontrollierte Ordnerzugriff?</span><span class="sxs-lookup"><span data-stu-id="f1044-120">How does controlled folder access work?</span></span>

<span data-ttu-id="f1044-121">Der kontrollierte Ordnerzugriff funktioniert nur, indem vertrauenswürdigen Apps der Zugriff auf geschützte Ordner gestattet wird.</span><span class="sxs-lookup"><span data-stu-id="f1044-121">Controlled folder access works by only allowing trusted apps to access protected folders.</span></span> <span data-ttu-id="f1044-122">Geschützte Ordner werden angegeben, wenn der kontrollierte Ordnerzugriff konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="f1044-122">Protected folders are specified when controlled folder access is configured.</span></span> <span data-ttu-id="f1044-123">In der Regel sind häufig verwendete Ordner, z. B. für Dokumente, Bilder, Downloads usw., in der Liste der gesteuerten Ordner enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1044-123">Typically, commonly used folders, such as those used for documents, pictures, downloads, and so on, are included in the list of controlled folders.</span></span> 

<span data-ttu-id="f1044-124">Der kontrollierte Ordnerzugriff funktioniert mit einer Liste vertrauenswürdiger Apps.</span><span class="sxs-lookup"><span data-stu-id="f1044-124">Controlled folder access works with a list of trusted apps.</span></span> <span data-ttu-id="f1044-125">Apps, die in der Liste der vertrauenswürdigen Software enthalten sind, funktionieren erwartungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="f1044-125">Apps that are included in the list of trusted software work as expected.</span></span> <span data-ttu-id="f1044-126">Apps, die nicht in der Liste enthalten sind, werden daran gehindert, Änderungen an Dateien in geschützten Ordnern vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f1044-126">Apps that are not included in the list are prevented from making any changes to files inside protected folders.</span></span> 

<span data-ttu-id="f1044-127">Apps werden der Liste basierend auf ihrer Verbreitung und Ihrem Ruf hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f1044-127">Apps are added to the list based upon their prevalence and reputation.</span></span> <span data-ttu-id="f1044-128">Apps, die in Ihrer Gesamten Organisation sehr weit verbreitet sind und nie ein als bösartig eingestuftes Verhalten angezeigt haben, gelten als vertrauenswürdig.</span><span class="sxs-lookup"><span data-stu-id="f1044-128">Apps that are highly prevalent throughout your organization and that have never displayed any behavior deemed malicious are considered trustworthy.</span></span> <span data-ttu-id="f1044-129">Diese Apps werden automatisch zur Liste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f1044-129">Those apps are added to the list automatically.</span></span>

<span data-ttu-id="f1044-130">Apps können der vertrauenswürdigen Liste auch manuell mithilfe von Configuration Manager oder Intune hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f1044-130">Apps can also be added manually to the trusted list by using Configuration Manager or Intune.</span></span> <span data-ttu-id="f1044-131">Zusätzliche Aktionen, z. [B. das Hinzufügen eines Dateiindikators](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) für eine App, können über die Security Center-Konsole ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f1044-131">Additional actions, such as [adding a file indicator](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) for an app, can be performed from the Security Center Console.</span></span>

## <a name="why-controlled-folder-access-is-important"></a><span data-ttu-id="f1044-132">Warum der kontrollierte Ordnerzugriff wichtig ist</span><span class="sxs-lookup"><span data-stu-id="f1044-132">Why controlled folder access is important</span></span>

<span data-ttu-id="f1044-133">Der kontrollierte Ordnerzugriff ist besonders nützlich, um Ihre Dokumente und Informationen vor [Ransomware](https://www.microsoft.com/wdsi/threats/ransomware)zu schützen.</span><span class="sxs-lookup"><span data-stu-id="f1044-133">Controlled folder access is especially useful in helping to protect your documents and information from [ransomware](https://www.microsoft.com/wdsi/threats/ransomware).</span></span> <span data-ttu-id="f1044-134">Bei einem Ransomware-Angriff können Ihre Dateien verschlüsselt und als Host gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="f1044-134">In a ransomware attack, your files can get encrypted and held hostage.</span></span> <span data-ttu-id="f1044-135">Wenn der kontrollierte Ordnerzugriff aktiviert ist, wird eine Benachrichtigung auf dem Computer angezeigt, auf dem eine App versucht hat, Änderungen an einer Datei in einem geschützten Ordner vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f1044-135">With controlled folder access in place, a notification appears on the computer where an app attempted to make changes to a file in a protected folder.</span></span> <span data-ttu-id="f1044-136">Sie können [die Benachrichtigung](customize-attack-surface-reduction.md#customize-the-notification) mit Ihren Unternehmensdetails und Kontaktinformationen anpassen.</span><span class="sxs-lookup"><span data-stu-id="f1044-136">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span> <span data-ttu-id="f1044-137">Sie können die Regeln auch einzeln aktivieren, um anzupassen, welche Techniken vom Feature überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="f1044-137">You can also enable the rules individually to customize what techniques the feature monitors.</span></span>

<span data-ttu-id="f1044-138">Zu den [geschützten Ordnern](#review-controlled-folder-access-events-in-windows-event-viewer) gehören allgemeine Systemordner (einschließlich Startbereichen), und Sie können [weitere Ordner hinzufügen.](customize-controlled-folders.md#protect-additional-folders)</span><span class="sxs-lookup"><span data-stu-id="f1044-138">The [protected folders](#review-controlled-folder-access-events-in-windows-event-viewer) include common system folders (including boot sectors), and you can [add more folders](customize-controlled-folders.md#protect-additional-folders).</span></span> <span data-ttu-id="f1044-139">Sie können Apps auch den Zugriff auf die geschützten Ordner [gestatten.](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders)</span><span class="sxs-lookup"><span data-stu-id="f1044-139">You can also [allow apps](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) to give them access to the protected folders.</span></span>

<span data-ttu-id="f1044-140">Sie können den [Überwachungsmodus](audit-windows-defender.md) verwenden, um zu bewerten, wie sich der kontrollierte Ordnerzugriff auf Ihre Organisation auswirken würde, wenn er aktiviert wäre.</span><span class="sxs-lookup"><span data-stu-id="f1044-140">You can use [audit mode](audit-windows-defender.md) to evaluate how controlled folder access would impact your organization if it were enabled.</span></span> <span data-ttu-id="f1044-141">Sie können auch die Website Windows Defender Testwebsite unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass das Feature funktioniert und wie es funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f1044-141">You can also visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

<span data-ttu-id="f1044-142">Der kontrollierte Ordnerzugriff wird in den folgenden Versionen von Windows unterstützt:</span><span class="sxs-lookup"><span data-stu-id="f1044-142">Controlled folder access is supported on the following versions of Windows:</span></span>
- <span data-ttu-id="f1044-143">[Windows 10, Version 1709](/windows/whats-new/whats-new-windows-10-version-1709) und höher</span><span class="sxs-lookup"><span data-stu-id="f1044-143">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) and later</span></span>
- [<span data-ttu-id="f1044-144">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="f1044-144">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a><span data-ttu-id="f1044-145">Windows Systemordner sind standardmäßig geschützt</span><span class="sxs-lookup"><span data-stu-id="f1044-145">Windows system folders are protected by default</span></span>

<span data-ttu-id="f1044-146">Windows Systemordner sind standardmäßig zusammen mit mehreren anderen Ordnern geschützt:</span><span class="sxs-lookup"><span data-stu-id="f1044-146">Windows system folders are protected by default, along with several other folders:</span></span> 

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
> <span data-ttu-id="f1044-147">Sie können zusätzliche Ordner als geschützt konfigurieren, aber Sie können die Windows Systemordner nicht entfernen, die standardmäßig geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="f1044-147">You can configure additional folders as protected, but you cannot remove the Windows system folders that are protected by default.</span></span>

## <a name="requirements-for-controlled-folder-access"></a><span data-ttu-id="f1044-148">Anforderungen für den kontrollierten Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="f1044-148">Requirements for controlled folder access</span></span>

<span data-ttu-id="f1044-149">Für den kontrollierten Ordnerzugriff muss [Microsoft Defender Antivirus Echtzeitschutz](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f1044-149">Controlled folder access requires enabling [Microsoft Defender Antivirus real-time protection](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

## <a name="review-controlled-folder-access-events-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="f1044-150">Überprüfen der Ereignisse des kontrollierten Ordnerzugriffs im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="f1044-150">Review controlled folder access events in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="f1044-151">Defender für Endpunkt bietet detaillierte Berichte zu Ereignissen und Blöcken als Teil seiner [Warnungsuntersuchungsszenarien](investigate-alerts.md) im Microsoft 365 Defender-Portal.</span><span class="sxs-lookup"><span data-stu-id="f1044-151">Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md) in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="f1044-152">(Siehe [Microsoft Defender für Endpunkt in Microsoft 365 Defender.)](../defender/microsoft-365-security-center-mde.md)</span><span class="sxs-lookup"><span data-stu-id="f1044-152">(See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).)</span></span>

<span data-ttu-id="f1044-153">Sie können Microsoft Defender für Endpunktdaten mithilfe der [erweiterten Suche](/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection)abfragen.</span><span class="sxs-lookup"><span data-stu-id="f1044-153">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="f1044-154">Wenn Sie den [Überwachungsmodus](audit-windows-defender.md)verwenden, können Sie die [erweiterte Suche](advanced-hunting-overview.md) verwenden, um zu sehen, wie sich die Einstellungen für den kontrollierten Ordnerzugriff auf Ihre Umgebung auswirken würden, wenn sie aktiviert würden.</span><span class="sxs-lookup"><span data-stu-id="f1044-154">If you're using [audit mode](audit-windows-defender.md), you can use [advanced hunting](advanced-hunting-overview.md) to see how controlled folder access settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="f1044-155">Beispielabfrage:</span><span class="sxs-lookup"><span data-stu-id="f1044-155">Example query:</span></span>

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="f1044-156">Überprüfen der Ereignisse des kontrollierten Ordnerzugriffs in Windows Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="f1044-156">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="f1044-157">Sie können das Windows Ereignisprotokoll überprüfen, um Ereignisse anzuzeigen, die erstellt werden, wenn der kontrollierte Ordnerzugriff eine App blockiert (oder überwacht):</span><span class="sxs-lookup"><span data-stu-id="f1044-157">You can review the Windows event log to see events that are created when controlled folder access blocks (or audits) an app:</span></span>

1. <span data-ttu-id="f1044-158">Laden Sie das [Evaluierungspaket herunter,](https://aka.ms/mp7z2w) und extrahieren Sie die Datei *cfa-events.xml* an einen leicht zugänglichen Speicherort auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="f1044-158">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>
2. <span data-ttu-id="f1044-159">Geben Sie die **Ereignisanzeige** im Startmenü ein, um die Windows Ereignisanzeige zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f1044-159">Type **Event viewer** in the Start menu to open the Windows Event Viewer.</span></span>
3. <span data-ttu-id="f1044-160">Wählen Sie im linken Bereich unter **"Aktionen"** die Option **"Benutzerdefinierte Ansicht importieren" aus...**.</span><span class="sxs-lookup"><span data-stu-id="f1044-160">On the left panel, under **Actions**, select **Import custom view...**.</span></span>
4. <span data-ttu-id="f1044-161">Navigieren Sie zu der Extrahierten *cfa-events.xml,* und wählen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="f1044-161">Navigate to where you extracted *cfa-events.xml* and select it.</span></span> <span data-ttu-id="f1044-162">Alternativ können [Sie den XML-Code direkt kopieren.](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="f1044-162">Alternatively, [copy the XML directly](event-views.md).</span></span>
5. <span data-ttu-id="f1044-163">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="f1044-163">Select **OK**.</span></span>

<span data-ttu-id="f1044-164">In der folgenden Tabelle sind Ereignisse im Zusammenhang mit dem kontrollierten Ordnerzugriff aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="f1044-164">The following table shows events related to controlled folder access:</span></span>

|<span data-ttu-id="f1044-165">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f1044-165">Event ID</span></span> | <span data-ttu-id="f1044-166">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1044-166">Description</span></span> |
|:---|:---|
|<span data-ttu-id="f1044-167">5007</span><span class="sxs-lookup"><span data-stu-id="f1044-167">5007</span></span> | <span data-ttu-id="f1044-168">Ereignis, wenn Einstellungen geändert werden</span><span class="sxs-lookup"><span data-stu-id="f1044-168">Event when settings are changed</span></span> |
|<span data-ttu-id="f1044-169">1124</span><span class="sxs-lookup"><span data-stu-id="f1044-169">1124</span></span> | <span data-ttu-id="f1044-170">Überwachtes Ereignis für den kontrollierten Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="f1044-170">Audited controlled folder access event</span></span> | 
|<span data-ttu-id="f1044-171">1123</span><span class="sxs-lookup"><span data-stu-id="f1044-171">1123</span></span> | <span data-ttu-id="f1044-172">Blockiertes Ereignis für den kontrollierten Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="f1044-172">Blocked controlled folder access event</span></span> |

## <a name="view-or-change-the-list-of-protected-folders"></a><span data-ttu-id="f1044-173">Anzeigen oder Ändern der Liste der geschützten Ordner</span><span class="sxs-lookup"><span data-stu-id="f1044-173">View or change the list of protected folders</span></span>

<span data-ttu-id="f1044-174">Sie können die Windows-Sicherheit-App verwenden, um die Liste der Ordner anzuzeigen, die durch den kontrollierten Ordnerzugriff geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="f1044-174">You can use the Windows Security app to view the list of folders that are protected by controlled folder access.</span></span> 

1. <span data-ttu-id="f1044-175">Öffnen Sie auf Ihrem Windows 10 Gerät die Windows-Sicherheit-App.</span><span class="sxs-lookup"><span data-stu-id="f1044-175">On your Windows 10 device, open the Windows Security app.</span></span>
2. <span data-ttu-id="f1044-176">Wählen Sie **Viren- und Bedrohungsschutz** aus.</span><span class="sxs-lookup"><span data-stu-id="f1044-176">Select **Virus & threat protection**.</span></span>
3. <span data-ttu-id="f1044-177">Wählen Sie unter **Ransomware-Schutz** Den **Ransomware-Schutz verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="f1044-177">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>
4. <span data-ttu-id="f1044-178">Wenn der kontrollierte Ordnerzugriff deaktiviert ist, müssen Sie ihn aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f1044-178">If controlled folder access is turned off, you'll need to turn it on.</span></span> <span data-ttu-id="f1044-179">Wählen Sie **geschützte Ordner aus.**</span><span class="sxs-lookup"><span data-stu-id="f1044-179">Select **protected folders**.</span></span>
5. <span data-ttu-id="f1044-180">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f1044-180">Do one of the following steps:</span></span>
   - <span data-ttu-id="f1044-181">Um einen Ordner hinzuzufügen, wählen Sie **+ Geschützten Ordner hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="f1044-181">To add a folder, select **+ Add a protected folder**.</span></span>
   - <span data-ttu-id="f1044-182">Um einen Ordner zu entfernen, wählen Sie ihn aus, und wählen Sie dann **Entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="f1044-182">To remove a folder, select it, and then select **Remove**.</span></span> 

> [!NOTE]
> <span data-ttu-id="f1044-183">[Windows Systemordner](#windows-system-folders-are-protected-by-default) sind standardmäßig geschützt, und Sie können sie nicht aus der Liste entfernen.</span><span class="sxs-lookup"><span data-stu-id="f1044-183">[Windows system folders](#windows-system-folders-are-protected-by-default) are protected by default, and you cannot remove them from the list.</span></span>


