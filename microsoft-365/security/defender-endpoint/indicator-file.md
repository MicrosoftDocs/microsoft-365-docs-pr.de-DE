---
title: Erstellen von Indikatoren für Dateien
ms.reviewer: ''
description: Erstellen Sie Indikatoren für einen Dateihash, der die Erkennung, Verhinderung und den Ausschluss von Entitäten definiert.
keywords: datei, hash, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6d92cbacba72210c6accbbb1e5ecf25de660fc3c
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730534"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="9bf28-104">Erstellen von Indikatoren für Dateien</span><span class="sxs-lookup"><span data-stu-id="9bf28-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9bf28-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9bf28-105">**Applies to:**</span></span>
- [<span data-ttu-id="9bf28-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9bf28-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9bf28-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bf28-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="9bf28-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="9bf28-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9bf28-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9bf28-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="9bf28-110">Verhindern Sie die weitere Verbreitung eines Angriffs in Ihrer Organisation, indem Sie potenziell schädliche Dateien oder mutmaßliche Schadsoftware verbieten.</span><span class="sxs-lookup"><span data-stu-id="9bf28-110">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="9bf28-111">Wenn Sie eine potenziell schädliche ausführbare Datei (PE) kennen, können Sie sie blockieren.</span><span class="sxs-lookup"><span data-stu-id="9bf28-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="9bf28-112">Dieser Vorgang verhindert, dass er auf Geräten in Ihrer Organisation gelesen, geschrieben oder ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9bf28-112">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="9bf28-113">Es gibt drei Möglichkeiten zum Erstellen von Indikatoren für Dateien:</span><span class="sxs-lookup"><span data-stu-id="9bf28-113">There are three ways you can create indicators for files:</span></span>

- <span data-ttu-id="9bf28-114">Durch Erstellen eines Indikators über die Einstellungsseite</span><span class="sxs-lookup"><span data-stu-id="9bf28-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="9bf28-115">Durch Erstellen eines kontextbezogenen Indikators mithilfe der Schaltfläche "Indikator hinzufügen" auf der Seite "Dateidetails"</span><span class="sxs-lookup"><span data-stu-id="9bf28-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>
- <span data-ttu-id="9bf28-116">Durch Erstellen eines Indikators über die [Indikator-API](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="9bf28-116">By creating an indicator through the [Indicator API](ti-indicator.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9bf28-117">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="9bf28-117">Before you begin</span></span>

<span data-ttu-id="9bf28-118">Es ist wichtig, die folgenden Voraussetzungen zu kennen, bevor Sie Indikatoren für Dateien erstellen:</span><span class="sxs-lookup"><span data-stu-id="9bf28-118">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="9bf28-119">Dieses Feature ist verfügbar, wenn Ihre Organisation **Microsoft Defender Antivirus (im** aktiven Modus) verwendet und **der cloudbasierte Schutz aktiviert ist.**</span><span class="sxs-lookup"><span data-stu-id="9bf28-119">This feature is available if your organization uses **Microsoft Defender Antivirus (in active mode)** and **Cloud-based protection is enabled**.</span></span> <span data-ttu-id="9bf28-120">Weitere Informationen finden Sie unter [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="9bf28-120">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>

- <span data-ttu-id="9bf28-121">Die Antischalwareclientversion muss 4.18.1901.x oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="9bf28-121">The Antimalware client version must be 4.18.1901.x or later.</span></span> <span data-ttu-id="9bf28-122">Siehe [Monatliche Plattform- und Modulversionen](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span><span class="sxs-lookup"><span data-stu-id="9bf28-122">See [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span></span>

- <span data-ttu-id="9bf28-123">Unterstützt auf Geräten mit Windows 10 Version 1703 oder höher, Windows Server 2016 und 2019.</span><span class="sxs-lookup"><span data-stu-id="9bf28-123">Supported on devices with Windows 10, version 1703 or later, Windows Server 2016 and 2019.</span></span>

- <span data-ttu-id="9bf28-124">Um mit dem Blockieren von Dateien zu beginnen, müssen Sie zuerst das Feature ["Blockieren oder zulassen"](advanced-features.md) in der Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="9bf28-124">To start blocking files, you first need to [turn on the "block or allow" feature](advanced-features.md) in Settings.</span></span>

<span data-ttu-id="9bf28-125">Dieses Feature soll verhindern, dass mutmaßliche Schadsoftware (oder potenziell schädliche Dateien) aus dem Web heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="9bf28-125">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="9bf28-126">Derzeit werden portable ausführbare Dateien (PE) unterstützt, einschließlich .exe und .dll Dateien.</span><span class="sxs-lookup"><span data-stu-id="9bf28-126">It currently supports portable executable (PE) files, including .exe and .dll files.</span></span> <span data-ttu-id="9bf28-127">Die Abdeckung wird im Laufe der Zeit erweitert.</span><span class="sxs-lookup"><span data-stu-id="9bf28-127">The coverage will be extended over time.</span></span>

## <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="9bf28-128">Erstellen eines Indikators für Dateien auf der Einstellungsseite</span><span class="sxs-lookup"><span data-stu-id="9bf28-128">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="9bf28-129">Wählen Sie im Navigationsbereich Einstellungen > **Indikatoren aus.**</span><span class="sxs-lookup"><span data-stu-id="9bf28-129">In the navigation pane, select **Settings > Indicators**.</span></span>

2. <span data-ttu-id="9bf28-130">Wählen Sie die **Registerkarte Dateihash**   aus.</span><span class="sxs-lookup"><span data-stu-id="9bf28-130">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="9bf28-131">Wählen **Sie Indikator hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="9bf28-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="9bf28-132">Geben Sie die folgenden Details an:</span><span class="sxs-lookup"><span data-stu-id="9bf28-132">Specify the following details:</span></span>
    - <span data-ttu-id="9bf28-133">Indikator – Geben Sie die Entitätsdetails an, und definieren Sie den Ablauf des Indikators.</span><span class="sxs-lookup"><span data-stu-id="9bf28-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
    - <span data-ttu-id="9bf28-134">Aktion – Geben Sie die zu ergreifende Aktion an, und geben Sie eine Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="9bf28-134">Action - Specify the action to be taken and provide a description.</span></span>
    - <span data-ttu-id="9bf28-135">Bereich : Definieren Sie den Bereich der Gerätegruppe.</span><span class="sxs-lookup"><span data-stu-id="9bf28-135">Scope - Define the scope of the device group.</span></span>

5. <span data-ttu-id="9bf28-136">Überprüfen Sie die Details auf der Registerkarte Zusammenfassung, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="9bf28-136">Review the details in the Summary tab, then select **Save**.</span></span>

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="9bf28-137">Erstellen eines Kontextindikators auf der Seite mit den Dateidetails</span><span class="sxs-lookup"><span data-stu-id="9bf28-137">Create a contextual indicator from the file details page</span></span>

<span data-ttu-id="9bf28-138">Eine der Optionen beim Ausführen von [Reaktionsaktionen für eine](respond-file-alerts.md)Datei ist das   Hinzufügen eines Indikators für die Datei.</span><span class="sxs-lookup"><span data-stu-id="9bf28-138">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> <span data-ttu-id="9bf28-139">Wenn Sie einen Indikatorhash für eine Datei hinzufügen, können Sie eine Warnung ausgelöst und die Datei blockieren, wenn ein Gerät in Ihrer Organisation versucht, sie zu ausführen.</span><span class="sxs-lookup"><span data-stu-id="9bf28-139">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="9bf28-140">Dateien, die automatisch von einem Indikator blockiert werden, werden nicht im Aktionscenter der Datei angezeigt, aber die Warnungen werden weiterhin in der Warnungswarteschlange angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9bf28-140">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="9bf28-141">In der Regel werden Dateiblöcke innerhalb weniger Minuten erzwungen und entfernt, können jedoch bis zu 30 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="9bf28-141">Typically, file blocks are enforced and removed within a couple of minutes, but can take upwards of 30 minutes.</span></span>
>- <span data-ttu-id="9bf28-142">Wenn Richtlinien für Dateiindikator in Konflikt stehen, wird die Erzwingungsrichtlinie der sichereren Richtlinie angewendet.</span><span class="sxs-lookup"><span data-stu-id="9bf28-142">If there are conflicting file indicator policies, the enforcement policy of the more secure policy is applied.</span></span> <span data-ttu-id="9bf28-143">Beispielsweise hat eine SHA-256-Dateihashindikatorrichtlinie Vorrang vor einer MD5-Dateihashindikatorrichtlinie, wenn beide Hashtypen dieselbe Datei definieren.</span><span class="sxs-lookup"><span data-stu-id="9bf28-143">For example, a SHA-256 file hash indicator policy takes precedence over an MD5 file hash indicator policy if both hash types define the same file.</span></span>
>- <span data-ttu-id="9bf28-144">Wenn die Gruppenrichtlinie EnableFileHashComputation deaktiviert ist, wird die Sperrgenauigkeit der Datei IoC reduziert.</span><span class="sxs-lookup"><span data-stu-id="9bf28-144">If EnableFileHashComputation group policy is disabled, the blocking accuracy of the file IoC is reduced.</span></span> <span data-ttu-id="9bf28-145">Das Aktivieren von EnableFileHashComputation kann sich jedoch auf die Geräteleistung auswirken.</span><span class="sxs-lookup"><span data-stu-id="9bf28-145">However, enabling EnableFileHashComputation may impact device performance.</span></span>
>    - <span data-ttu-id="9bf28-146">Das Kopieren großer Dateien aus einer Netzwerkfreigabe auf Ihr lokales Gerät, insbesondere über eine VPN-Verbindung, kann sich beispielsweise auf die Geräteleistung auswirken.</span><span class="sxs-lookup"><span data-stu-id="9bf28-146">For example, copying large files from a network share onto your local device, especially over a VPN connection, may have an effect on device performance.</span></span>
>    - <span data-ttu-id="9bf28-147">Weitere Informationen zur Gruppenrichtlinie EnableFileHashComputation finden Sie unter [Defender CSP](/windows/client-management/mdm/defender-csp)</span><span class="sxs-lookup"><span data-stu-id="9bf28-147">For more information about the EnableFileHashComputation group policy, see [Defender CSP](/windows/client-management/mdm/defender-csp)</span></span>

## <a name="policy-conflict-handling"></a><span data-ttu-id="9bf28-148">Behandlung von Richtlinienkonflikten</span><span class="sxs-lookup"><span data-stu-id="9bf28-148">Policy conflict handling</span></span>  

<span data-ttu-id="9bf28-149">Die Behandlung von Konflikten zwischen Cert- und File IoC-Richtlinien folgt der folgenden Reihenfolge:</span><span class="sxs-lookup"><span data-stu-id="9bf28-149">Cert and File IoC policy handling conflict will follow the below order:</span></span>

- <span data-ttu-id="9bf28-150">Wenn die Datei nicht von der Anwendungskontrolle Windows Defender appLocker richtlinien/richtlinien für den Erzwungenen Modus zulässig ist, dann **Blockieren**</span><span class="sxs-lookup"><span data-stu-id="9bf28-150">If the file is not allowed by Windows Defender Application Control and AppLocker enforce mode policy/policies, then **Block**</span></span>

- <span data-ttu-id="9bf28-151">Andern falls die Datei durch den Microsoft Defender Antivirus zulässig ist, dann **Zulassen**</span><span class="sxs-lookup"><span data-stu-id="9bf28-151">Else if the file is allowed by the Microsoft Defender Antivirus exclusion, then **Allow**</span></span>

- <span data-ttu-id="9bf28-152">Andern falls die Datei durch einen Block oder eine Warndatei blockiert oder gewarnt wird, dann **Blockieren/Warnen**</span><span class="sxs-lookup"><span data-stu-id="9bf28-152">Else if the file is blocked or warned by a block or warn file IoC, then **Block/Warn**</span></span>

- <span data-ttu-id="9bf28-153">Andern falls die Datei von einer IoC-Richtlinie für zugelassene Dateien zulässig ist, dann **Zulassen**</span><span class="sxs-lookup"><span data-stu-id="9bf28-153">Else if the file is allowed by an allow file IoC policy, then **Allow**</span></span>

- <span data-ttu-id="9bf28-154">Andern falls die Datei durch #A0 blockiert wird, CFA, AV, SmartScreen und **dann Blockieren**</span><span class="sxs-lookup"><span data-stu-id="9bf28-154">Else if the file is blocked by ASR rules, CFA, AV, SmartScreen, then **Block**</span></span>  

- <span data-ttu-id="9bf28-155">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span><span class="sxs-lookup"><span data-stu-id="9bf28-155">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span></span>

<span data-ttu-id="9bf28-156">Wenn #A0 in Konflikt stehen, die denselben Erzwingungstyp und dasselbe Ziel haben, wird die Richtlinie des sichereren (d. h. längeren) Hashs angewendet.</span><span class="sxs-lookup"><span data-stu-id="9bf28-156">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure (meaning longer) hash will be applied.</span></span> <span data-ttu-id="9bf28-157">Eine SHA-256-Dateihash-IoC-Richtlinie z. B. gewinnt eine #A0 für MD5-Dateihash, wenn beide Hashtypen dieselbe Datei definieren.</span><span class="sxs-lookup"><span data-stu-id="9bf28-157">For example, a SHA-256 file hash IoC policy will win over a MD5 file hash IoC policy if both hash types define the same file.</span></span>

<span data-ttu-id="9bf28-158">Beachten Sie, Bedrohungs- und Sicherheitsrisikomanagement für die blockverwundbaren Anwendungsfeatures die Datei-IoCs für die Erzwingung verwenden und die oben aufgeführte Reihenfolge für die Konfliktbehandlung befolgen.</span><span class="sxs-lookup"><span data-stu-id="9bf28-158">Note that threat and vulnerability management's block vulnerable application features uses the file IoCs for enforcement and will follow the above conflict handling order.</span></span>

### <a name="examples"></a><span data-ttu-id="9bf28-159">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9bf28-159">Examples</span></span>

|<span data-ttu-id="9bf28-160">Komponente</span><span class="sxs-lookup"><span data-stu-id="9bf28-160">Component</span></span> |<span data-ttu-id="9bf28-161">Komponentenersetzung</span><span class="sxs-lookup"><span data-stu-id="9bf28-161">Component enforcement</span></span> |<span data-ttu-id="9bf28-162">Dateiindikatoraktion</span><span class="sxs-lookup"><span data-stu-id="9bf28-162">File indicator Action</span></span> |<span data-ttu-id="9bf28-163">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="9bf28-163">Result</span></span>
|--|--|--|--|
|<span data-ttu-id="9bf28-164">Dateipfadausschluss zur Attack Surface Reduction</span><span class="sxs-lookup"><span data-stu-id="9bf28-164">Attack surface reduction file path exclusion</span></span> |<span data-ttu-id="9bf28-165">Zulassen</span><span class="sxs-lookup"><span data-stu-id="9bf28-165">Allow</span></span> |<span data-ttu-id="9bf28-166">Blockieren</span><span class="sxs-lookup"><span data-stu-id="9bf28-166">Block</span></span> |<span data-ttu-id="9bf28-167">Blockieren</span><span class="sxs-lookup"><span data-stu-id="9bf28-167">Block</span></span>
|<span data-ttu-id="9bf28-168">Regel zur Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="9bf28-168">Attack surface reduction rule</span></span> |<span data-ttu-id="9bf28-169">Blockieren</span><span class="sxs-lookup"><span data-stu-id="9bf28-169">Block</span></span> |<span data-ttu-id="9bf28-170">Zulassen</span><span class="sxs-lookup"><span data-stu-id="9bf28-170">Allow</span></span> |<span data-ttu-id="9bf28-171">Zulassen</span><span class="sxs-lookup"><span data-stu-id="9bf28-171">Allow</span></span>
|<span data-ttu-id="9bf28-172">Windows Defender Application Control</span><span class="sxs-lookup"><span data-stu-id="9bf28-172">Windows Defender Application Control</span></span> |<span data-ttu-id="9bf28-173">Zulassen</span><span class="sxs-lookup"><span data-stu-id="9bf28-173">Allow</span></span> |<span data-ttu-id="9bf28-174">Blockieren</span><span class="sxs-lookup"><span data-stu-id="9bf28-174">Block</span></span> |<span data-ttu-id="9bf28-175">Zulassen</span><span class="sxs-lookup"><span data-stu-id="9bf28-175">Allow</span></span> |
|<span data-ttu-id="9bf28-176">Windows Defender Application Control</span><span class="sxs-lookup"><span data-stu-id="9bf28-176">Windows Defender Application Control</span></span> |<span data-ttu-id="9bf28-177">Blockieren</span><span class="sxs-lookup"><span data-stu-id="9bf28-177">Block</span></span> |<span data-ttu-id="9bf28-178">Zulassen</span><span class="sxs-lookup"><span data-stu-id="9bf28-178">Allow</span></span> |<span data-ttu-id="9bf28-179">Blockieren</span><span class="sxs-lookup"><span data-stu-id="9bf28-179">Block</span></span>
|<span data-ttu-id="9bf28-180">Microsoft Defender Antivirus Ausschluss</span><span class="sxs-lookup"><span data-stu-id="9bf28-180">Microsoft Defender Antivirus exclusion</span></span> |<span data-ttu-id="9bf28-181">Zulassen</span><span class="sxs-lookup"><span data-stu-id="9bf28-181">Allow</span></span> |<span data-ttu-id="9bf28-182">Blockieren</span><span class="sxs-lookup"><span data-stu-id="9bf28-182">Block</span></span> |<span data-ttu-id="9bf28-183">Zulassen</span><span class="sxs-lookup"><span data-stu-id="9bf28-183">Allow</span></span>

## <a name="see-also"></a><span data-ttu-id="9bf28-184">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9bf28-184">See also</span></span>

- [<span data-ttu-id="9bf28-185">Indikatoren erstellen</span><span class="sxs-lookup"><span data-stu-id="9bf28-185">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="9bf28-186">Erstellen von Indikatoren für IPs und URLs/Domänen</span><span class="sxs-lookup"><span data-stu-id="9bf28-186">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="9bf28-187">Erstellen von Indikatoren basierend auf Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="9bf28-187">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="9bf28-188">Indikatoren verwalten</span><span class="sxs-lookup"><span data-stu-id="9bf28-188">Manage indicators</span></span>](indicator-manage.md)
