---
title: Aktivieren des in der Cloud zugestellten Schutzes in Microsoft Defender Antivirus
description: Aktivieren Sie den in der Cloud zugestellten Schutz, um von schnellen und erweiterten Schutzfunktionen zu profitieren.
keywords: Microsoft Defender Antivirus, Antischalware, Sicherheit, Cloud, beim ersten Blick blockieren
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.date: 04/30/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 5fcbd30eca3a6d0965fe65e13d2623ff54d1ff5f
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114248"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="3e322-104">Über die Cloud bereitgestellten Netzwerkschutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="3e322-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3e322-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3e322-105">**Applies to:**</span></span>

- [<span data-ttu-id="3e322-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="3e322-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="3e322-107">Der Microsoft Defender Antivirus cloud service ist ein Mechanismus für die Bereitstellung aktualisierten Schutzes für Ihr Netzwerk und Ihre Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="3e322-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="3e322-108">Obwohl er als Clouddienst bezeichnet wird, handelt es sich nicht nur um den Schutz von Dateien, die in der Cloud gespeichert sind. Stattdessen werden verteilte Ressourcen und maschinelles Lernen verwendet, um Ihren Endpunkten Schutz zu bieten, und dies mit einer Geschwindigkeit, die wesentlich schneller ist als herkömmliche Security Intelligence-Updates.</span><span class="sxs-lookup"><span data-stu-id="3e322-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="3e322-109">Microsoft Defender Antivirus verwendet mehrere Erkennungs- und Verhinderungstechnologien, um präzisen, echtzeitgenauen und intelligenten Schutz zu bieten.</span><span class="sxs-lookup"><span data-stu-id="3e322-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="3e322-110">Lernen Sie die erweiterten Technologien kennen, die im Kern des [Microsoft Defender for Endpoint-Schutzes der nächsten Generation zu finden sind.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="3e322-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="3e322-111">![Liste der Microsoft Defender AV-Engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="3e322-111">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="3e322-112">Sie können den Microsoft Defender Antivirus von der Cloud übermittelten Schutz auf verschiedene Weise aktivieren oder deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="3e322-112">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="3e322-113">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3e322-113">Microsoft Intune</span></span>
- <span data-ttu-id="3e322-114">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="3e322-114">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="3e322-115">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="3e322-115">Group Policy</span></span>
- <span data-ttu-id="3e322-116">PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="3e322-116">PowerShell cmdlets.</span></span>

 <span data-ttu-id="3e322-117">Sie können sie auch in einzelnen Clients mit der app Windows-Sicherheit aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3e322-117">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="3e322-118">Unter [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) finden Sie eine Übersicht über Microsoft Defender Antivirus von der Cloud zugestellten Schutz.</span><span class="sxs-lookup"><span data-stu-id="3e322-118">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="3e322-119">Weitere Informationen zu den spezifischen Netzwerkkonnektivitätsanforderungen, um sicherzustellen, dass Ihre Endpunkte eine Verbindung mit dem in der Cloud übermittelten Schutzdienst herstellen können, finden Sie unter [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="3e322-119">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3e322-120">In Windows 10 gibt es keinen Unterschied  zwischen den in diesem Thema beschriebenen Grundlegenden und **erweiterten** Berichtsoptionen.</span><span class="sxs-lookup"><span data-stu-id="3e322-120">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="3e322-121">Dies ist eine ältere Unterscheidung, und die Auswahl einer der Einstellungen führt zu demselben Grad an cloudbasiertem Schutz.</span><span class="sxs-lookup"><span data-stu-id="3e322-121">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="3e322-122">Es gibt keinen Unterschied in der Art oder Menge der freigegebenen Informationen.</span><span class="sxs-lookup"><span data-stu-id="3e322-122">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="3e322-123">Weitere Informationen zu den gesammelten Daten finden Sie unter [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span><span class="sxs-lookup"><span data-stu-id="3e322-123">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="3e322-124">Aktivieren des in der Cloud übermittelten Schutzes mithilfe von Intune</span><span class="sxs-lookup"><span data-stu-id="3e322-124">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="3e322-125">Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="3e322-125">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="3e322-126">Wählen Sie **im Bereich Start** die Option **Gerätekonfiguration > Profile aus.**</span><span class="sxs-lookup"><span data-stu-id="3e322-126">On the **Home** pane, select **Device configuration > Profiles**.</span></span>

3. <span data-ttu-id="3e322-127">Wählen Sie den **Profiltyp** Geräteeinschränkungen aus, den Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3e322-127">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="3e322-128">Wenn Sie einen neuen Profiltyp für Geräteeinschränkungen **erstellen** müssen, lesen Sie Konfigurieren von Geräteeinschränkungseinstellungen [in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="3e322-128">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="3e322-129">Wählen **Sie Eigenschaften**  >  **Konfigurationseinstellungen aus: Bearbeiten**  >  **Microsoft Defender Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="3e322-129">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="3e322-130">Wählen Sie **auf der Option Cloud-zugestellter Schutz** die Option Aktivieren **aus.**</span><span class="sxs-lookup"><span data-stu-id="3e322-130">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>

6. <span data-ttu-id="3e322-131">Wählen Sie **im Dropdownmenü Benutzer vor Der Beispielübermittlung** anzeigen die Option **Alle Daten automatisch senden aus.**</span><span class="sxs-lookup"><span data-stu-id="3e322-131">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="3e322-132">Weitere Informationen zu Intune-Geräteprofilen, einschließlich der Erstellung und Konfiguration ihrer Einstellungen, finden Sie unter Was [sind Microsoft Intune Geräteprofile?](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="3e322-132">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="3e322-133">Verwenden Microsoft Endpoint Manager zum Aktivieren des in der Cloud übermittelten Schutzes</span><span class="sxs-lookup"><span data-stu-id="3e322-133">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="3e322-134">Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="3e322-134">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="3e322-135">Wählen **Sie Endpoint security**  >  **Antivirus** aus.</span><span class="sxs-lookup"><span data-stu-id="3e322-135">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="3e322-136">Wählen Sie ein Antivirusprofil aus.</span><span class="sxs-lookup"><span data-stu-id="3e322-136">Select an antivirus profile.</span></span> <span data-ttu-id="3e322-137">(Wenn Sie noch kein Profil haben oder ein neues Profil erstellen möchten, lesen Sie Konfigurieren von Geräteeinschränkungseinstellungen [in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="3e322-137">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="3e322-138">Wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="3e322-138">Select **Properties**.</span></span> <span data-ttu-id="3e322-139">Wählen Sie dann neben **Konfigurationseinstellungen** bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="3e322-139">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="3e322-140">Erweitern **Sie den** Cloudschutz, und wählen Sie dann in der Liste der von der Cloud übermittelten **Schutzebenen** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="3e322-140">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
   - <span data-ttu-id="3e322-141">**High**: Wendet eine starke Erkennungsstufe an.</span><span class="sxs-lookup"><span data-stu-id="3e322-141">**High**: Applies a strong level of detection.</span></span>
   - <span data-ttu-id="3e322-142">**High plus**: Verwendet die **High-Ebene** und wendet zusätzliche Schutzmaßnahmen an (kann sich auf die Clientleistung auswirken).</span><span class="sxs-lookup"><span data-stu-id="3e322-142">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
   - <span data-ttu-id="3e322-143">**Nulltoleranz**: Blockiert alle unbekannten ausführbaren Dateien.</span><span class="sxs-lookup"><span data-stu-id="3e322-143">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="3e322-144">Wählen **Sie Überprüfen + Speichern** und dann Speichern **aus.**</span><span class="sxs-lookup"><span data-stu-id="3e322-144">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="3e322-145">Weitere Informationen zum Konfigurieren Microsoft Endpoint Configuration Manager finden Sie unter Erstellen und Bereitstellen von Antischalwarerichtlinien: [Cloud-Protection Service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span><span class="sxs-lookup"><span data-stu-id="3e322-145">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="3e322-146">Aktivieren des in der Cloud übermittelten Schutzes mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="3e322-146">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="3e322-147">Öffnen Sie auf Ihrem Gruppenrichtlinienverwaltungsgerät die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie Bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="3e322-147">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="3e322-148">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="3e322-148">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="3e322-149">Wählen Sie **Administrative Vorlagen aus.**</span><span class="sxs-lookup"><span data-stu-id="3e322-149">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="3e322-150">Erweitern der Struktur zum Windows **von > Microsoft Defender Antivirus > MAPS**</span><span class="sxs-lookup"><span data-stu-id="3e322-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="3e322-151">Doppelklicken Sie auf **Microsoft MAPS beitreten.**</span><span class="sxs-lookup"><span data-stu-id="3e322-151">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="3e322-152">Stellen Sie sicher, dass die Option aktiviert ist und auf **Basic MAPS** oder Advanced MAPS **festgelegt ist.**</span><span class="sxs-lookup"><span data-stu-id="3e322-152">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="3e322-153">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="3e322-153">Select **OK**.</span></span>

6. <span data-ttu-id="3e322-154">Doppelklicken Sie **auf Dateibeispiele senden, wenn eine weitere Analyse erforderlich ist.**</span><span class="sxs-lookup"><span data-stu-id="3e322-154">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="3e322-155">Stellen Sie sicher, dass die erste Option auf **Aktiviert festgelegt** ist und dass die anderen Optionen auf eine der folgenden Optionen festgelegt sind:</span><span class="sxs-lookup"><span data-stu-id="3e322-155">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="3e322-156">**Senden sicherer Beispiele** (1)</span><span class="sxs-lookup"><span data-stu-id="3e322-156">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="3e322-157">**Senden aller Beispiele** (3)</span><span class="sxs-lookup"><span data-stu-id="3e322-157">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="3e322-158">Die **Option Sichere Beispiele** senden (1) bedeutet, dass die meisten Beispiele automatisch gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="3e322-158">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="3e322-159">Dateien, die wahrscheinlich personenbezogene Informationen enthalten, werden weiterhin aufgefordert und erfordern eine zusätzliche Bestätigung.</span><span class="sxs-lookup"><span data-stu-id="3e322-159">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>
        > <span data-ttu-id="3e322-160">Wenn Sie die Option **auf Always Prompt** (0) festlegen, wird der Schutzstatus des Geräts gesenkt.</span><span class="sxs-lookup"><span data-stu-id="3e322-160">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="3e322-161">Das Festlegen auf **Nie senden** (2) bedeutet, dass das [Feature "Bei](configure-block-at-first-sight-microsoft-defender-antivirus.md) erster Sicht blockieren" von Microsoft Defender for Endpoint nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="3e322-161">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="3e322-162">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="3e322-162">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="3e322-163">Verwenden von PowerShell-Cmdlets zum Aktivieren des in der Cloud übermittelten Schutzes</span><span class="sxs-lookup"><span data-stu-id="3e322-163">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="3e322-164">Die folgenden Cmdlets können den in der Cloud zugestellten Schutz aktivieren:</span><span class="sxs-lookup"><span data-stu-id="3e322-164">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="3e322-165">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Use PowerShell cmdlets to configure](use-powershell-cmdlets-microsoft-defender-antivirus.md) and run Microsoft Defender Antivirus and Defender [cmdlets](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="3e322-165">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="3e322-166">[Richtlinien-CSP – Defender](/windows/client-management/mdm/policy-csp-defender) verfügt auch über weitere Informationen speziell zu [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span><span class="sxs-lookup"><span data-stu-id="3e322-166">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="3e322-167">Sie können auch **-SubmitSamplesConsent** auf `SendSafeSamples` (die Standardeinstellung) `NeverSend` oder `AlwaysPrompt` festlegen.</span><span class="sxs-lookup"><span data-stu-id="3e322-167">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="3e322-168">Die `SendSafeSamples` Einstellung bedeutet, dass die meisten Beispiele automatisch gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="3e322-168">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="3e322-169">Dateien, die wahrscheinlich personenbezogene Informationen enthalten, werden weiterhin aufgefordert und erfordern eine zusätzliche Bestätigung.</span><span class="sxs-lookup"><span data-stu-id="3e322-169">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="3e322-170">Setting **-SubmitSamplesConsent** to or `NeverSend` will lower the protection level of the `AlwaysPrompt` device.</span><span class="sxs-lookup"><span data-stu-id="3e322-170">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="3e322-171">Darüber hinaus bedeutet das Festlegen, dass das Feature "Bei erster Sicht `NeverSend` blockieren" von Microsoft Defender for Endpoint nicht funktioniert. [](configure-block-at-first-sight-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="3e322-171">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="3e322-172">Verwenden Windows Management Instruction (WMI) zum Aktivieren des in der Cloud übermittelten Schutzes</span><span class="sxs-lookup"><span data-stu-id="3e322-172">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="3e322-173">Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="3e322-173">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="3e322-174">Weitere Informationen zu zulässigen Parametern finden Sie [unter Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="3e322-174">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="3e322-175">Aktivieren des in der Cloud übermittelten Schutzes auf einzelnen Clients mit der Windows-Sicherheit App</span><span class="sxs-lookup"><span data-stu-id="3e322-175">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="3e322-176">Wenn die Einstellung Lokale Einstellung für die Berichterstellung von **Microsoft MAPS-Gruppenrichtlinien** konfigurieren auf **Deaktiviert** festgelegt ist, ist die **cloudbasierte** Schutzeinstellung in Windows Einstellungen ausgegraut und nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3e322-176">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="3e322-177">Änderungen, die über ein Gruppenrichtlinienobjekt vorgenommen werden, müssen zuerst auf einzelnen Endpunkten bereitgestellt werden, bevor die Einstellung in einem Windows Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="3e322-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="3e322-178">Öffnen Sie Windows-Sicherheit App, indem Sie das Schildsymbol in der Taskleiste auswählen oder im Startmenü nach **Defender suchen.**</span><span class="sxs-lookup"><span data-stu-id="3e322-178">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="3e322-179">Wählen Sie **die Kachel &** Bedrohungsschutz (oder das Schildsymbol auf der linken Menüleiste) und dann die Bezeichnung **Virenschutzeinstellungen &** aus:</span><span class="sxs-lookup"><span data-stu-id="3e322-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Screenshot der Bezeichnung & Virenschutzeinstellungen in der Windows-Sicherheit App](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="3e322-181">Vergewissern Sie **sich, dass cloudbasierter Schutz** und **automatische Beispielübermittlung** auf **Ein umgeschaltet werden.**</span><span class="sxs-lookup"><span data-stu-id="3e322-181">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="3e322-182">Wenn die automatische Beispielübermittlung mit Gruppenrichtlinien konfiguriert wurde, ist die Einstellung ausgegraut und nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3e322-182">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3e322-183">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="3e322-183">Related articles</span></span>

- [<span data-ttu-id="3e322-184">Konfigurieren des Timeoutzeitraums für Cloudblockierung</span><span class="sxs-lookup"><span data-stu-id="3e322-184">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3e322-185">Konfigurieren von Block bei erster Sicht</span><span class="sxs-lookup"><span data-stu-id="3e322-185">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3e322-186">Verwenden von PowerShell-Cmdlets zum Verwalten von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="3e322-186">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="3e322-187">[Schützen von Windows PCs mit Endpoint Protection für Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span><span class="sxs-lookup"><span data-stu-id="3e322-187">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="3e322-188">Defender-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3e322-188">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="3e322-189">Verwenden des von Microsoft in der Cloud übermittelten Schutzes in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="3e322-189">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3e322-190">Erstellen und Bereitstellen von Antischalwarerichtlinien: Cloudschutzdienst</span><span class="sxs-lookup"><span data-stu-id="3e322-190">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="3e322-191">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="3e322-191">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
