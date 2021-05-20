---
title: Aktivieren Sie den von der Cloud bereitgestellten Schutz in Microsoft Defender Antivirus
description: Schalten Sie den von der Cloud bereitgestellten Schutz ein, um von schnellen und erweiterten Schutzfunktionen zu profitieren.
keywords: Microsoft Defender Antivirus, Antimalware, Sicherheit, Cloud, Block auf den ersten Blick
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572057"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="0710e-104">Über die Cloud bereitgestellten Netzwerkschutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="0710e-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0710e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0710e-105">**Applies to:**</span></span>

- [<span data-ttu-id="0710e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0710e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="0710e-107">Der Microsoft Defender Antivirus Clouddienst ist ein Mechanismus, mit dem Sie aktualisierten Schutz für Ihr Netzwerk und Ihre Endpunkte bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="0710e-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="0710e-108">Obwohl es als Cloud-Dienst bezeichnet wird, ist es nicht einfach Schutz für Dateien, die in der Cloud gespeichert sind; Stattdessen werden verteilte Ressourcen und maschinelles Lernen verwendet, um Ihre Endpunkte mit einer Rate zu schützen, die viel schneller ist als herkömmliche Sicherheitsintelligenzaktualisierungen.</span><span class="sxs-lookup"><span data-stu-id="0710e-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="0710e-109">Microsoft Defender Antivirus verwendet mehrere Erkennungs- und Präventionstechnologien, um präzisen, Echtzeit- und intelligenten Schutz zu bieten.</span><span class="sxs-lookup"><span data-stu-id="0710e-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="0710e-110">[Lernen Sie die fortschrittlichen Technologien kennen, die im Kern von Microsoft Defender for Endpoint-Schutz der nächsten Generation stehen.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="0710e-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

<span data-ttu-id="0710e-111">Sie können Microsoft Defender Antivirus Cloud-geschützten Schutz auf verschiedene Arten ein- oder ausschalten:</span><span class="sxs-lookup"><span data-stu-id="0710e-111">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="0710e-112">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="0710e-112">Microsoft Intune</span></span>
- <span data-ttu-id="0710e-113">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="0710e-113">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="0710e-114">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0710e-114">Group Policy</span></span>
- <span data-ttu-id="0710e-115">PowerShell Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0710e-115">PowerShell cmdlets.</span></span>

 <span data-ttu-id="0710e-116">Sie können es auch in einzelnen Clients mit der Windows-Sicherheit App ein- oder ausschalten.</span><span class="sxs-lookup"><span data-stu-id="0710e-116">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="0710e-117">Eine Übersicht über Microsoft Defender Antivirus von der Cloud bereitgestellten Schutz finden Sie unter Verwenden des von Microsoft bereitgestellten Schutzes in [der Microsoft-Cloud.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="0710e-117">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="0710e-118">Weitere Informationen zu den spezifischen Anforderungen an die Netzwerkkonnektivität, um sicherzustellen, dass Ihre Endpunkte eine Verbindung mit dem in der Cloud bereitgestellten Schutzdienst herstellen können, finden Sie unter Konfigurieren und Überprüfen von [Netzwerkverbindungen](configure-network-connections-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="0710e-118">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0710e-119">In Windows 10 gibt es keinen Unterschied zwischen den in diesem Thema beschriebenen Optionen **für die grundlegende** und **erweiterte** Berichterstattung.</span><span class="sxs-lookup"><span data-stu-id="0710e-119">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="0710e-120">Dies ist eine ältere Unterscheidung, und die Auswahl einer der beiden Einstellungen führt zu demselben Schutzniveau, das von der Cloud bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0710e-120">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="0710e-121">Es gibt keinen Unterschied in der Art oder Menge der freigegebenen Informationen.</span><span class="sxs-lookup"><span data-stu-id="0710e-121">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="0710e-122">Weitere Informationen zu dem, was wir sammeln, finden Sie in der [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=521839).</span><span class="sxs-lookup"><span data-stu-id="0710e-122">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="0710e-123">Verwenden sie Intune, um den von der Cloud bereitgestellten Schutz zu aktivieren</span><span class="sxs-lookup"><span data-stu-id="0710e-123">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="0710e-124">Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="0710e-124">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="0710e-125">Wählen Sie im **Fenster Startseite** die Option **Gerätekonfiguration > Profile aus.**</span><span class="sxs-lookup"><span data-stu-id="0710e-125">On the **Home** pane, select **Device configuration > Profiles**.</span></span>

3. <span data-ttu-id="0710e-126">Wählen Sie den Profiltyp **"Geräteeinschränkungen" aus, den** Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="0710e-126">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="0710e-127">Wenn Sie einen neuen **Profiltyp** für Geräteeinschränkungen erstellen müssen, finden Sie weitere Informationen unter Konfigurieren der [Geräteeinschränkungseinstellungen in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="0710e-127">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="0710e-128">  >  **Eigenschaftenkonfigurationseinstellungen auswählen: Bearbeiten**  >  **Microsoft Defender Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="0710e-128">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="0710e-129">Wählen Sie auf dem Von der **Cloud bereitgestellten Schutzschalter** Aktivieren die Option **Aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="0710e-129">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>

6. <span data-ttu-id="0710e-130">Wählen Sie in der Dropdownliste **"Anfordern" vor der Beispielübermittlung** die Option **Alle Daten automatisch senden** aus.</span><span class="sxs-lookup"><span data-stu-id="0710e-130">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="0710e-131">Weitere Informationen zu Intune-Geräteprofilen, z. B. zum Erstellen und Konfigurieren ihrer Einstellungen, finden Sie unter [Was sind Microsoft Intune Geräteprofile?](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="0710e-131">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="0710e-132">Verwenden Sie Microsoft Endpoint Manager, um den von der Cloud bereitgestellten Schutz zu aktivieren</span><span class="sxs-lookup"><span data-stu-id="0710e-132">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="0710e-133">Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="0710e-133">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="0710e-134">Wählen Sie **Endpoint security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="0710e-134">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="0710e-135">Wählen Sie ein Antivirenprofil aus.</span><span class="sxs-lookup"><span data-stu-id="0710e-135">Select an antivirus profile.</span></span> <span data-ttu-id="0710e-136">(Wenn Sie noch keines haben oder ein neues Profil erstellen möchten, finden Sie weitere Informationen unter Konfigurieren der [Geräteeinschränkungseinstellungen in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="0710e-136">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="0710e-137">Wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="0710e-137">Select **Properties**.</span></span> <span data-ttu-id="0710e-138">Wählen Sie dann neben **den Konfigurationseinstellungen** **bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="0710e-138">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="0710e-139">Erweitern Sie den **Cloud-Schutz**, und wählen Sie dann in der Liste der **bereitgestellten Schutzebenen** in der Cloud bereitgestellten Option eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="0710e-139">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
   - <span data-ttu-id="0710e-140">**Hoch**: Wendet ein starkes Erkennungsniveau an.</span><span class="sxs-lookup"><span data-stu-id="0710e-140">**High**: Applies a strong level of detection.</span></span>
   - <span data-ttu-id="0710e-141">**High plus**: Verwendet das **High** Level und wendet zusätzliche Schutzmaßnahmen an (kann sich auf die Kundenleistung auswirken).</span><span class="sxs-lookup"><span data-stu-id="0710e-141">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
   - <span data-ttu-id="0710e-142">**Nulltoleranz**: Blockiert alle unbekannten ausführbaren Dateien.</span><span class="sxs-lookup"><span data-stu-id="0710e-142">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="0710e-143">Wählen Sie **Überprüfen + Speichern**, und wählen Sie **speichern**.</span><span class="sxs-lookup"><span data-stu-id="0710e-143">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="0710e-144">Weitere Informationen zum Konfigurieren von Microsoft Endpoint Configuration Manager finden Sie unter [Erstellen und Bereitstellen von Antischadsoftwarerichtlinien: Cloud-Schutzdienst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span><span class="sxs-lookup"><span data-stu-id="0710e-144">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="0710e-145">Verwenden von Gruppenrichtlinien zum Aktivieren des von der Cloud bereitgestellten Schutzes</span><span class="sxs-lookup"><span data-stu-id="0710e-145">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="0710e-146">Öffnen Sie auf Ihrem Gruppenrichtlinienverwaltungsgerät die [Gruppenrichtlinienverwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="0710e-146">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="0710e-147">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="0710e-147">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="0710e-148">Wählen Sie **Administrative Vorlagen** aus.</span><span class="sxs-lookup"><span data-stu-id="0710e-148">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="0710e-149">Erweitern Sie die Struktur, um **Komponenten > Microsoft Defender Antivirus > MAPS** zu Windows</span><span class="sxs-lookup"><span data-stu-id="0710e-149">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="0710e-150">Doppelklicken Sie auf **Microsoft MAPS beitreten**.</span><span class="sxs-lookup"><span data-stu-id="0710e-150">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="0710e-151">Stellen Sie sicher, dass die Option aktiviert ist und auf **Basic MAPS** oder **Advanced MAPS** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0710e-151">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="0710e-152">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0710e-152">Select **OK**.</span></span>

6. <span data-ttu-id="0710e-153">Doppelklicken Sie auf **Dateibeispiele senden, wenn weitere Analysen erforderlich sind**.</span><span class="sxs-lookup"><span data-stu-id="0710e-153">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="0710e-154">Stellen Sie sicher, dass die erste Option auf **Aktiviert** und die anderen Optionen auf folgende Optionen festgelegt sind:</span><span class="sxs-lookup"><span data-stu-id="0710e-154">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="0710e-155">**Sichere Proben versenden** (1)</span><span class="sxs-lookup"><span data-stu-id="0710e-155">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="0710e-156">**Senden Sie alle Proben** (3)</span><span class="sxs-lookup"><span data-stu-id="0710e-156">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="0710e-157">Die Option **Sichere Proben senden** (1) bedeutet, dass die meisten Proben automatisch gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="0710e-157">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="0710e-158">Dateien, die wahrscheinlich persönliche Informationen enthalten, werden weiterhin aufgefordert und erfordern eine zusätzliche Bestätigung.</span><span class="sxs-lookup"><span data-stu-id="0710e-158">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>
        > <span data-ttu-id="0710e-159">Wenn Sie die Option **auf Immer Eingabeaufforderung** (0) setzen, wird der Schutzstatus des Geräts verringert.</span><span class="sxs-lookup"><span data-stu-id="0710e-159">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="0710e-160">Wenn Sie es auf **Nie senden** (2) setzen, funktioniert die [Funktion "Blockieren beim ersten Blick"](configure-block-at-first-sight-microsoft-defender-antivirus.md) von Microsoft Defender for Endpoint nicht.</span><span class="sxs-lookup"><span data-stu-id="0710e-160">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="0710e-161">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0710e-161">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="0710e-162">Verwenden Von PowerShell-Cmdlets zum Aktivieren des von der Cloud bereitgestellten Schutzes</span><span class="sxs-lookup"><span data-stu-id="0710e-162">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="0710e-163">Die folgenden Cmdlets können den von der Cloud bereitgestellten Schutz aktivieren:</span><span class="sxs-lookup"><span data-stu-id="0710e-163">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="0710e-164">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen Microsoft Defender Antivirus- und](use-powershell-cmdlets-microsoft-defender-antivirus.md) [Defender-Cmdlets](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="0710e-164">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="0710e-165">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) hat auch mehr Informationen speziell auf [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span><span class="sxs-lookup"><span data-stu-id="0710e-165">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="0710e-166">Sie können auch **-SubmitSamplesConsent** auf `SendSafeSamples` (die Standardeinstellung), `NeverSend` oder `AlwaysPrompt` festlegen.</span><span class="sxs-lookup"><span data-stu-id="0710e-166">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="0710e-167">Die `SendSafeSamples` Einstellung bedeutet, dass die meisten Samples automatisch gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="0710e-167">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="0710e-168">Dateien, die wahrscheinlich persönliche Informationen enthalten, werden weiterhin aufgefordert und erfordern eine zusätzliche Bestätigung.</span><span class="sxs-lookup"><span data-stu-id="0710e-168">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="0710e-169">Einstellung **-SubmitSamplesConsent** auf `NeverSend` oder senkt die `AlwaysPrompt` Schutzstufe des Geräts.</span><span class="sxs-lookup"><span data-stu-id="0710e-169">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="0710e-170">Außerdem bedeutet das Festlegen, `NeverSend` dass die [Funktion "Blockieren beim ersten Blick"](configure-block-at-first-sight-microsoft-defender-antivirus.md) von Microsoft Defender for Endpoint nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="0710e-170">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="0710e-171">Verwenden sie Windows Management Instruction (WMI), um den von der Cloud bereitgestellten Schutz zu aktivieren</span><span class="sxs-lookup"><span data-stu-id="0710e-171">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="0710e-172">Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/defender/set-msft-mppreference) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="0710e-172">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="0710e-173">Weitere Informationen zu zulässigen Parametern finden Sie [unter Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="0710e-173">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="0710e-174">Aktivieren Sie den von der Cloud bereitgestellten Schutz für einzelne Clients mit der Windows-Sicherheit-App</span><span class="sxs-lookup"><span data-stu-id="0710e-174">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="0710e-175">Wenn die Einstellung Lokale Einstellung Konfigurieren **für den Bericht von Microsoft MAPS** Group Policy auf **Deaktiviert** festgelegt ist, ist die **Cloud-basierte Schutzeinstellung** in Windows Einstellungen ausgegraut und nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0710e-175">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="0710e-176">Änderungen, die über ein Gruppenrichtlinienobjekt vorgenommen wurden, müssen zunächst auf einzelnen Endpunkten bereitgestellt werden, bevor die Einstellung in den Windows-Einstellungen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="0710e-176">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="0710e-177">Öffnen Sie die Windows-Sicherheit App, indem Sie das Schildsymbol in der Taskleiste auswählen oder im Startmenü nach **Defender** suchen.</span><span class="sxs-lookup"><span data-stu-id="0710e-177">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="0710e-178">Wählen Sie die **Virus & Bedrohungsschutzkachel** (oder das Schildsymbol in der linken Menüleiste) und dann die Bezeichnung **Virus & Bedrohungsschutzeinstellungen** aus:</span><span class="sxs-lookup"><span data-stu-id="0710e-178">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Screenshot der Bezeichnung für die Einstellungen des Viren- und Bedrohungsschutzes in der Windows-Sicherheit-App](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="0710e-180">Vergewissern Sie sich, dass **Cloud-basierter Schutz** und **automatische Beispielübermittlung** auf **Ein** geschaltet werden.</span><span class="sxs-lookup"><span data-stu-id="0710e-180">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="0710e-181">Wenn die automatische Beispielübermittlung mit Gruppenrichtlinien konfiguriert wurde, ist die Einstellung ausgegraut und nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0710e-181">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0710e-182">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="0710e-182">Related articles</span></span>

- [<span data-ttu-id="0710e-183">Konfigurieren des Timeoutzeitraums für Cloudblockierung</span><span class="sxs-lookup"><span data-stu-id="0710e-183">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0710e-184">Block auf den ersten Blick konfigurieren</span><span class="sxs-lookup"><span data-stu-id="0710e-184">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0710e-185">Verwenden von PowerShell-Cmdlets zum Verwalten von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0710e-185">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="0710e-186">[Schützen Sie Windows PCs mit Endpoint Protection für Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span><span class="sxs-lookup"><span data-stu-id="0710e-186">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="0710e-187">Defender Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0710e-187">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="0710e-188">Verwenden sie den von Microsoft Cloud bereitgestellten Schutz in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0710e-188">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0710e-189">Erstellen und Bereitstellen von Antischadsoftware-Richtlinien: Cloud-Schutzdienst</span><span class="sxs-lookup"><span data-stu-id="0710e-189">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="0710e-190">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="0710e-190">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
