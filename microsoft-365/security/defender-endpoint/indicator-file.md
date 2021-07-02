---
title: Erstellen von Indikatoren für Dateien
ms.reviewer: ''
description: Erstellen Sie Indikatoren für einen Dateihash, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren.
keywords: Datei, Hash, verwalten, zulässig, blockiert, blockieren, sauber, bösartig, Dateihash, IP-Adresse, URLs, Domäne
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
ms.openlocfilehash: b56a18e1b35b65629318ab29f2189ef1f73373f5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256915"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="eafe6-104">Erstellen von Indikatoren für Dateien</span><span class="sxs-lookup"><span data-stu-id="eafe6-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eafe6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="eafe6-105">**Applies to:**</span></span>
- [<span data-ttu-id="eafe6-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="eafe6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eafe6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eafe6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="eafe6-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="eafe6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="eafe6-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="eafe6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="eafe6-110">Verhindern Sie die weitere Verbreitung eines Angriffs in Ihrer Organisation, indem Sie potenziell schädliche Dateien oder verdächtige Schadsoftware verbieten.</span><span class="sxs-lookup"><span data-stu-id="eafe6-110">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="eafe6-111">Wenn Sie eine potenziell schädliche portierbare ausführbare Datei (PE) kennen, können Sie sie blockieren.</span><span class="sxs-lookup"><span data-stu-id="eafe6-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="eafe6-112">Dieser Vorgang verhindert, dass er auf Geräten in Ihrer Organisation gelesen, geschrieben oder ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eafe6-112">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="eafe6-113">Es gibt drei Möglichkeiten, Indikatoren für Dateien zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="eafe6-113">There are three ways you can create indicators for files:</span></span>

- <span data-ttu-id="eafe6-114">Durch Erstellen eines Indikators über die Einstellungsseite</span><span class="sxs-lookup"><span data-stu-id="eafe6-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="eafe6-115">Durch Erstellen eines Kontextindikators mithilfe der Schaltfläche "Indikator hinzufügen" auf der Dateidetailseite</span><span class="sxs-lookup"><span data-stu-id="eafe6-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>
- <span data-ttu-id="eafe6-116">Durch Erstellen eines Indikators über die [Indikator-API](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="eafe6-116">By creating an indicator through the [Indicator API](ti-indicator.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="eafe6-117">Vorabinformationen</span><span class="sxs-lookup"><span data-stu-id="eafe6-117">Before you begin</span></span>

<span data-ttu-id="eafe6-118">Es ist wichtig, die folgenden Voraussetzungen zu verstehen, bevor Sie Indikatoren für Dateien erstellen:</span><span class="sxs-lookup"><span data-stu-id="eafe6-118">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="eafe6-119">Dieses Feature ist verfügbar, wenn Ihre Organisation **Microsoft Defender Antivirus (im aktiven Modus)** verwendet und **der cloudbasierte Schutz aktiviert ist.**</span><span class="sxs-lookup"><span data-stu-id="eafe6-119">This feature is available if your organization uses **Microsoft Defender Antivirus (in active mode)** and **Cloud-based protection is enabled**.</span></span> <span data-ttu-id="eafe6-120">Weitere Informationen finden Sie unter [Verwalten des cloudbasierten Schutzes.](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="eafe6-120">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>

- <span data-ttu-id="eafe6-121">Die Antischadsoftware-Clientversion muss 4.18.1901.x oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="eafe6-121">The Antimalware client version must be 4.18.1901.x or later.</span></span> <span data-ttu-id="eafe6-122">Siehe [monatliche Plattform- und Modulversionen](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span><span class="sxs-lookup"><span data-stu-id="eafe6-122">See [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span></span>

- <span data-ttu-id="eafe6-123">Unterstützt auf Geräten mit Windows 10, Version 1703 oder höher, Windows Server 2016 und 2019.</span><span class="sxs-lookup"><span data-stu-id="eafe6-123">Supported on devices with Windows 10, version 1703 or later, Windows Server 2016 and 2019.</span></span>

- <span data-ttu-id="eafe6-124">Um mit dem Blockieren von Dateien zu beginnen, müssen Sie zuerst [das Feature "Blockieren oder Zulassen"](advanced-features.md) in Einstellungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="eafe6-124">To start blocking files, you first need to [turn on the "block or allow" feature](advanced-features.md) in Settings.</span></span>

<span data-ttu-id="eafe6-125">Dieses Feature soll verhindern, dass verdächtige Schadsoftware (oder potenziell schädliche Dateien) aus dem Web heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="eafe6-125">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="eafe6-126">Derzeit werden portierbare ausführbare Dateien (PORTABLE Executable, PE) unterstützt, einschließlich .exe- und .dll dateien.</span><span class="sxs-lookup"><span data-stu-id="eafe6-126">It currently supports portable executable (PE) files, including .exe and .dll files.</span></span> <span data-ttu-id="eafe6-127">Die Abdeckung wird im Laufe der Zeit erweitert.</span><span class="sxs-lookup"><span data-stu-id="eafe6-127">The coverage will be extended over time.</span></span>

## <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="eafe6-128">Erstellen eines Indikators für Dateien auf der Einstellungsseite</span><span class="sxs-lookup"><span data-stu-id="eafe6-128">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="eafe6-129">Wählen Sie im Navigationsbereich **Einstellungen > Indikatoren** aus.</span><span class="sxs-lookup"><span data-stu-id="eafe6-129">In the navigation pane, select **Settings > Indicators**.</span></span>

2. <span data-ttu-id="eafe6-130">Wählen Sie die Registerkarte **"Dateihash"**   aus.</span><span class="sxs-lookup"><span data-stu-id="eafe6-130">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="eafe6-131">Wählen Sie **"Indikator hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="eafe6-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="eafe6-132">Geben Sie die folgenden Details an:</span><span class="sxs-lookup"><span data-stu-id="eafe6-132">Specify the following details:</span></span>
    - <span data-ttu-id="eafe6-133">Indikator – Geben Sie die Entitätsdetails an, und definieren Sie den Ablauf des Indikators.</span><span class="sxs-lookup"><span data-stu-id="eafe6-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
    - <span data-ttu-id="eafe6-134">Aktion – Geben Sie die auszuführende Aktion an, und geben Sie eine Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="eafe6-134">Action - Specify the action to be taken and provide a description.</span></span>
    - <span data-ttu-id="eafe6-135">Bereich – Definieren Sie den Bereich der Gerätegruppe.</span><span class="sxs-lookup"><span data-stu-id="eafe6-135">Scope - Define the scope of the device group.</span></span>

5. <span data-ttu-id="eafe6-136">Überprüfen Sie die Details auf der Registerkarte "Zusammenfassung", und wählen Sie dann **"Speichern"** aus.</span><span class="sxs-lookup"><span data-stu-id="eafe6-136">Review the details in the Summary tab, then select **Save**.</span></span>

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="eafe6-137">Erstellen eines Kontextindikators auf der Dateidetailseite</span><span class="sxs-lookup"><span data-stu-id="eafe6-137">Create a contextual indicator from the file details page</span></span>

<span data-ttu-id="eafe6-138">Eine der Optionen beim Ausführen von [Antwortaktionen für eine Datei](respond-file-alerts.md)ist das   Hinzufügen eines Indikators für die Datei.</span><span class="sxs-lookup"><span data-stu-id="eafe6-138">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> <span data-ttu-id="eafe6-139">Wenn Sie einen Indikatorhash für eine Datei hinzufügen, können Sie eine Warnung auslösen und die Datei blockieren, wenn ein Gerät in Ihrer Organisation versucht, sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="eafe6-139">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="eafe6-140">Dateien, die automatisch durch einen Indikator blockiert werden, werden nicht im Info-Center der Datei angezeigt, aber die Warnungen werden weiterhin in der Warnungswarteschlange angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eafe6-140">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="eafe6-141">Dateiblöcke werden in der Regel innerhalb weniger Minuten erzwungen und entfernt, können jedoch bis zu 30 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="eafe6-141">Typically, file blocks are enforced and removed within a couple of minutes, but can take upwards of 30 minutes.</span></span>
> 
>- <span data-ttu-id="eafe6-142">Wenn es widersprüchliche Datei-IoC-Richtlinien mit demselben Erzwingungstyp und Ziel gibt, wird die Richtlinie des sichereren Hash angewendet.</span><span class="sxs-lookup"><span data-stu-id="eafe6-142">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure hash will be applied.</span></span> <span data-ttu-id="eafe6-143">Eine SHA-256-Dateihash-IoC-Richtlinie hat Vorrang vor einer SHA-1-Dateihash-IoC-Richtlinie, die eine MD5-Dateihash-IoC-Richtlinie gewinnen wird, wenn die Hashtypen dieselbe Datei definieren.</span><span class="sxs-lookup"><span data-stu-id="eafe6-143">An SHA-256 file hash IoC policy will win over an SHA-1 file hash IoC policy, which will win over an MD5 file hash IoC policy if the hash types define the same file.</span></span> <span data-ttu-id="eafe6-144">Dies gilt unabhängig von der Gerätegruppe.</span><span class="sxs-lookup"><span data-stu-id="eafe6-144">This is always true regardless of the device group.</span></span> 
>   <span data-ttu-id="eafe6-145">Wenn in allen anderen Fällen in Konflikt stehende Datei-IoC-Richtlinien mit demselben Erzwingungsziel auf alle Geräte und auf die Gruppe des Geräts angewendet werden, wird für ein Gerät die Richtlinie in der Gerätegruppe gewonnen.</span><span class="sxs-lookup"><span data-stu-id="eafe6-145">In all other cases, if conflicting file IoC policies with the same enforcement target are applied to all devices and to the device’s group, then for a device, the policy in the device group will win.</span></span> 
>   
>- <span data-ttu-id="eafe6-146">Wenn die EnableFileHashComputation-Gruppenrichtlinie deaktiviert ist, wird die Blockiergenauigkeit der Datei IoC verringert.</span><span class="sxs-lookup"><span data-stu-id="eafe6-146">If the EnableFileHashComputation group policy is disabled, the blocking accuracy of the file IoC is reduced.</span></span> <span data-ttu-id="eafe6-147">Die Aktivierung kann sich jedoch `EnableFileHashComputation` auf die Geräteleistung auswirken.</span><span class="sxs-lookup"><span data-stu-id="eafe6-147">However, enabling `EnableFileHashComputation` may impact device performance.</span></span> <span data-ttu-id="eafe6-148">Das Kopieren großer Dateien von einer Netzwerkfreigabe auf Ihr lokales Gerät, insbesondere über eine VPN-Verbindung, kann sich beispielsweise auf die Geräteleistung auswirken.</span><span class="sxs-lookup"><span data-stu-id="eafe6-148">For example, copying large files from a network share onto your local device, especially over a VPN connection, might have an effect on device performance.</span></span>
>
>   <span data-ttu-id="eafe6-149">Weitere Informationen zur Gruppenrichtlinie "EnableFileHashComputation" finden Sie unter [Defender CSP.](/windows/client-management/mdm/defender-csp)</span><span class="sxs-lookup"><span data-stu-id="eafe6-149">For more information about the EnableFileHashComputation group policy, see [Defender CSP](/windows/client-management/mdm/defender-csp)</span></span>

## <a name="policy-conflict-handling"></a><span data-ttu-id="eafe6-150">Behandlung von Richtlinienkonflikten</span><span class="sxs-lookup"><span data-stu-id="eafe6-150">Policy conflict handling</span></span>  

<span data-ttu-id="eafe6-151">Der Konflikt bei der Behandlung von Zertifikat- und Datei-IoC-Richtlinien folgt der folgenden Reihenfolge:</span><span class="sxs-lookup"><span data-stu-id="eafe6-151">Cert and File IoC policy handling conflict will follow the below order:</span></span>

- <span data-ttu-id="eafe6-152">Wenn die Datei von Windows Defender Anwendungssteuerung und AppLocker-Richtlinie/Richtlinien für den Erzwingungsmodus nicht zulässig ist, blockieren **Sie**</span><span class="sxs-lookup"><span data-stu-id="eafe6-152">If the file is not allowed by Windows Defender Application Control and AppLocker enforce mode policy/policies, then **Block**</span></span>

- <span data-ttu-id="eafe6-153">Andernfalls, wenn die Datei durch den Microsoft Defender Antivirus Ausschluss zulässig ist, dann **zulassen**</span><span class="sxs-lookup"><span data-stu-id="eafe6-153">Else if the file is allowed by the Microsoft Defender Antivirus exclusion, then **Allow**</span></span>

- <span data-ttu-id="eafe6-154">Andernfalls, wenn die Datei blockiert oder durch eine Blockierung oder warnungsdatei IoC gewarnt wird, dann **blockieren/warnen**</span><span class="sxs-lookup"><span data-stu-id="eafe6-154">Else if the file is blocked or warned by a block or warn file IoC, then **Block/Warn**</span></span>

- <span data-ttu-id="eafe6-155">Andernfalls, wenn die Datei durch eine Allow-Datei-IoC-Richtlinie zulässig ist, dann **zulassen**</span><span class="sxs-lookup"><span data-stu-id="eafe6-155">Else if the file is allowed by an allow file IoC policy, then **Allow**</span></span>

- <span data-ttu-id="eafe6-156">Andernfalls, wenn die Datei durch ASR-Regeln blockiert wird, CFA, AV, SmartScreen, dann **blockieren**</span><span class="sxs-lookup"><span data-stu-id="eafe6-156">Else if the file is blocked by ASR rules, CFA, AV, SmartScreen, then **Block**</span></span>  

- <span data-ttu-id="eafe6-157">Else **Allow** (übergibt Windows Defender Anwendungssteuerung & AppLocker-Richtlinie, es gelten keine IoC-Regeln)</span><span class="sxs-lookup"><span data-stu-id="eafe6-157">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span></span>

<span data-ttu-id="eafe6-158">Wenn es widersprüchliche Datei-IoC-Richtlinien mit demselben Erzwingungstyp und Ziel gibt, wird die Richtlinie des sichereren (d. h. längeren) Hash angewendet.</span><span class="sxs-lookup"><span data-stu-id="eafe6-158">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure (meaning longer) hash will be applied.</span></span> <span data-ttu-id="eafe6-159">Beispielsweise wird eine IOC-Richtlinie mit SHA-256-Dateihash eine MD5-Dateihash-IoC-Richtlinie gewinnen, wenn beide Hashtypen dieselbe Datei definieren.</span><span class="sxs-lookup"><span data-stu-id="eafe6-159">For example, an SHA-256 file hash IoC policy will win over an MD5 file hash IoC policy if both hash types define the same file.</span></span>

<span data-ttu-id="eafe6-160">Die Features von Bedrohungen und Sicherheitsrisikomanagement blockieren anfällige Anwendungen verwenden die Datei-IoCs für die Erzwingung und folgen der oben genannten Konfliktbehandlungsreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="eafe6-160">Threat and vulnerability management's block vulnerable application features uses the file IoCs for enforcement and will follow the above conflict handling order.</span></span>

### <a name="examples"></a><span data-ttu-id="eafe6-161">Beispiele</span><span class="sxs-lookup"><span data-stu-id="eafe6-161">Examples</span></span>

|<span data-ttu-id="eafe6-162">Komponente</span><span class="sxs-lookup"><span data-stu-id="eafe6-162">Component</span></span> |<span data-ttu-id="eafe6-163">Erzwingung von Komponenten</span><span class="sxs-lookup"><span data-stu-id="eafe6-163">Component enforcement</span></span> |<span data-ttu-id="eafe6-164">Dateiindikatoraktion</span><span class="sxs-lookup"><span data-stu-id="eafe6-164">File indicator Action</span></span> |<span data-ttu-id="eafe6-165">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="eafe6-165">Result</span></span>
|--|--|--|--|
|<span data-ttu-id="eafe6-166">Ausschluss des Dateipfads zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="eafe6-166">Attack surface reduction file path exclusion</span></span> |<span data-ttu-id="eafe6-167">Zulassen</span><span class="sxs-lookup"><span data-stu-id="eafe6-167">Allow</span></span> |<span data-ttu-id="eafe6-168">Blockieren</span><span class="sxs-lookup"><span data-stu-id="eafe6-168">Block</span></span> |<span data-ttu-id="eafe6-169">Blockieren</span><span class="sxs-lookup"><span data-stu-id="eafe6-169">Block</span></span>
|<span data-ttu-id="eafe6-170">Regel zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="eafe6-170">Attack surface reduction rule</span></span> |<span data-ttu-id="eafe6-171">Blockieren</span><span class="sxs-lookup"><span data-stu-id="eafe6-171">Block</span></span> |<span data-ttu-id="eafe6-172">Zulassen</span><span class="sxs-lookup"><span data-stu-id="eafe6-172">Allow</span></span> |<span data-ttu-id="eafe6-173">Zulassen</span><span class="sxs-lookup"><span data-stu-id="eafe6-173">Allow</span></span>
|<span data-ttu-id="eafe6-174">Windows Defender Application Control</span><span class="sxs-lookup"><span data-stu-id="eafe6-174">Windows Defender Application Control</span></span> |<span data-ttu-id="eafe6-175">Zulassen</span><span class="sxs-lookup"><span data-stu-id="eafe6-175">Allow</span></span> |<span data-ttu-id="eafe6-176">Blockieren</span><span class="sxs-lookup"><span data-stu-id="eafe6-176">Block</span></span> |<span data-ttu-id="eafe6-177">Zulassen</span><span class="sxs-lookup"><span data-stu-id="eafe6-177">Allow</span></span> |
|<span data-ttu-id="eafe6-178">Windows Defender Application Control</span><span class="sxs-lookup"><span data-stu-id="eafe6-178">Windows Defender Application Control</span></span> |<span data-ttu-id="eafe6-179">Blockieren</span><span class="sxs-lookup"><span data-stu-id="eafe6-179">Block</span></span> |<span data-ttu-id="eafe6-180">Zulassen</span><span class="sxs-lookup"><span data-stu-id="eafe6-180">Allow</span></span> |<span data-ttu-id="eafe6-181">Blockieren</span><span class="sxs-lookup"><span data-stu-id="eafe6-181">Block</span></span>
|<span data-ttu-id="eafe6-182">Microsoft Defender Antivirus Ausschluss</span><span class="sxs-lookup"><span data-stu-id="eafe6-182">Microsoft Defender Antivirus exclusion</span></span> |<span data-ttu-id="eafe6-183">Zulassen</span><span class="sxs-lookup"><span data-stu-id="eafe6-183">Allow</span></span> |<span data-ttu-id="eafe6-184">Blockieren</span><span class="sxs-lookup"><span data-stu-id="eafe6-184">Block</span></span> |<span data-ttu-id="eafe6-185">Zulassen</span><span class="sxs-lookup"><span data-stu-id="eafe6-185">Allow</span></span>

## <a name="see-also"></a><span data-ttu-id="eafe6-186">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eafe6-186">See also</span></span>

- [<span data-ttu-id="eafe6-187">Indikatoren erstellen</span><span class="sxs-lookup"><span data-stu-id="eafe6-187">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="eafe6-188">Erstellen von Indikatoren für IPs und URLs/Domänen</span><span class="sxs-lookup"><span data-stu-id="eafe6-188">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="eafe6-189">Erstellen von Indikatoren basierend auf Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="eafe6-189">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="eafe6-190">Indikatoren verwalten</span><span class="sxs-lookup"><span data-stu-id="eafe6-190">Manage indicators</span></span>](indicator-manage.md)
