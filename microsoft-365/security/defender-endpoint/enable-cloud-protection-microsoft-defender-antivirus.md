---
title: Aktivieren des über die Cloud bereitgestellten Schutzes in Microsoft Defender Antivirus
description: Aktivieren Sie den über die Cloud bereitgestellten Schutz, um von schnellen und erweiterten Schutzfunktionen zu profitieren.
keywords: Microsoft Defender Antivirus, Antischadsoftware, Sicherheit, Cloud, bei erster Anzeige blockieren
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: e7b7a0ba5c301829633c27f3add8f7f7daa70dfd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924707"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="a3192-104">Über die Cloud bereitgestellten Netzwerkschutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="a3192-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a3192-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a3192-105">**Applies to:**</span></span>

- [<span data-ttu-id="a3192-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a3192-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="a3192-107">Der Microsoft Defender Antivirus Clouddienst ist ein Mechanismus für die Bereitstellung eines aktualisierten Schutzes für Ihr Netzwerk und Ihre Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="a3192-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="a3192-108">Obwohl er als Clouddienst bezeichnet wird, ist er nicht nur Schutz für Dateien, die in der Cloud gespeichert sind. Stattdessen werden verteilte Ressourcen und maschinelles Lernen verwendet, um Schutz für Ihre Endpunkte in einer Geschwindigkeit bereitzustellen, die viel schneller als herkömmliche Security Intelligence-Updates ist.</span><span class="sxs-lookup"><span data-stu-id="a3192-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="a3192-109">Microsoft Defender Antivirus verwendet mehrere Erkennungs- und Verhinderungstechnologien, um präzisen, echtzeitbasierten und intelligenten Schutz zu bieten.</span><span class="sxs-lookup"><span data-stu-id="a3192-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="a3192-110">[Lernen Sie die fortschrittlichen Technologien](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)kennen, die den Kern des Schutzes der nächsten Generation von Microsoft Defender für Endpunkt darstellen.</span><span class="sxs-lookup"><span data-stu-id="a3192-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

<span data-ttu-id="a3192-111">Sie können Microsoft Defender Antivirus über die Cloud bereitgestellten Schutz auf verschiedene Arten aktivieren oder deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="a3192-111">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="a3192-112">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a3192-112">Microsoft Intune</span></span>
- <span data-ttu-id="a3192-113">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="a3192-113">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="a3192-114">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a3192-114">Group Policy</span></span>
- <span data-ttu-id="a3192-115">PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a3192-115">PowerShell cmdlets.</span></span>

 <span data-ttu-id="a3192-116">Sie können sie auch in einzelnen Clients mit der Windows-Sicherheit-App aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a3192-116">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="a3192-117">Eine Übersicht über Microsoft Defender Antivirus über die Cloud bereitgestellten Schutz finden Sie unter Verwenden des über die Cloud bereitgestellten Schutzes von [Microsoft.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a3192-117">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="a3192-118">Weitere Informationen zu den spezifischen Anforderungen an die Netzwerkkonnektivität, um sicherzustellen, dass Ihre Endpunkte eine Verbindung mit dem über die Cloud bereitgestellten Schutzdienst herstellen können, finden Sie unter [Konfigurieren und Überprüfen von Netzwerkverbindungen.](configure-network-connections-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a3192-118">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a3192-119">In Windows 10 gibt es keinen Unterschied zwischen **den** in diesem Thema beschriebenen grundlegenden und **erweiterten** Berichtsoptionen.</span><span class="sxs-lookup"><span data-stu-id="a3192-119">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="a3192-120">Dies ist eine veraltete Unterscheidung, und die Auswahl einer der beiden Einstellungen führt zu dem gleichen Maß an über die Cloud bereitgestelltem Schutz.</span><span class="sxs-lookup"><span data-stu-id="a3192-120">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="a3192-121">Es gibt keinen Unterschied hinsichtlich des Typs oder der Menge der informationen, die freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a3192-121">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="a3192-122">Weitere Informationen dazu, was wir sammeln, finden Sie in den [Microsoft-Datenschutzbestimmungen.](https://go.microsoft.com/fwlink/?linkid=521839)</span><span class="sxs-lookup"><span data-stu-id="a3192-122">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="a3192-123">Verwenden von Intune zum Aktivieren des über die Cloud bereitgestellten Schutzes</span><span class="sxs-lookup"><span data-stu-id="a3192-123">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="a3192-124">Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="a3192-124">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="a3192-125">Wählen Sie im **Bereich "Start"** die Option **"Gerätekonfiguration > Profile" aus.**</span><span class="sxs-lookup"><span data-stu-id="a3192-125">On the **Home** pane, select **Device configuration > Profiles**.</span></span>

3. <span data-ttu-id="a3192-126">Wählen Sie den **Profiltyp "Geräteeinschränkungen"** aus, den Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a3192-126">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="a3192-127">Wenn Sie einen neuen Profiltyp für **Geräteeinschränkungen** erstellen müssen, lesen Sie die Informationen unter [Konfigurieren von Einstellungen für Geräteeinschränkungen in Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="a3192-127">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="a3192-128">Wählen Sie  >  **Eigenschaftenkonfigurationseinstellungen aus: Bearbeiten**  >  **Microsoft Defender Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="a3192-128">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="a3192-129">Wählen Sie im switch **"Cloud-delivered protection"** die Option **"Aktivieren"** aus.</span><span class="sxs-lookup"><span data-stu-id="a3192-129">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>

6. <span data-ttu-id="a3192-130">Wählen Sie in der **Dropdownliste "Benutzer vor Beispielübermittlung auffordern"** die Option **"Alle Daten automatisch senden"** aus.</span><span class="sxs-lookup"><span data-stu-id="a3192-130">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="a3192-131">Weitere Informationen zu Intune-Geräteprofilen, einschließlich der Erstellung und Konfiguration ihrer Einstellungen, finden Sie unter [Was sind Microsoft Intune Geräteprofile?](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="a3192-131">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="a3192-132">Verwenden von Microsoft Endpoint Manager zum Aktivieren des über die Cloud bereitgestellten Schutzes</span><span class="sxs-lookup"><span data-stu-id="a3192-132">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="a3192-133">Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="a3192-133">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="a3192-134">Wählen Sie **Endpunktsicherheits-Antivirus**  >  aus.</span><span class="sxs-lookup"><span data-stu-id="a3192-134">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="a3192-135">Wählen Sie ein Antivirusprofil aus.</span><span class="sxs-lookup"><span data-stu-id="a3192-135">Select an antivirus profile.</span></span> <span data-ttu-id="a3192-136">(Wenn Sie noch kein Profil haben oder ein neues Profil erstellen möchten, lesen Sie die Informationen unter [Konfigurieren von Einstellungen für Geräteeinschränkungen in Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="a3192-136">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="a3192-137">Wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="a3192-137">Select **Properties**.</span></span> <span data-ttu-id="a3192-138">Wählen Sie dann neben den **Konfigurationseinstellungen** **"Bearbeiten"** aus.</span><span class="sxs-lookup"><span data-stu-id="a3192-138">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="a3192-139">Erweitern Sie den **Cloudschutz,** und wählen Sie dann in der Liste der über die **Cloud bereitgestellten Schutzebene** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="a3192-139">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
   - <span data-ttu-id="a3192-140">**Hoch:** Wendet eine starke Erkennungsstufe an.</span><span class="sxs-lookup"><span data-stu-id="a3192-140">**High**: Applies a strong level of detection.</span></span>
   - <span data-ttu-id="a3192-141">**Hoch plus:** Verwendet die **Stufe "High"** und wendet zusätzliche Schutzmaßnahmen an (kann sich auf die Clientleistung auswirken).</span><span class="sxs-lookup"><span data-stu-id="a3192-141">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
   - <span data-ttu-id="a3192-142">**Nulltoleranz:** Blockiert alle unbekannten ausführbaren Dateien.</span><span class="sxs-lookup"><span data-stu-id="a3192-142">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="a3192-143">Wählen Sie **"Überprüfen" + "Speichern"** und dann **"Speichern"** aus.</span><span class="sxs-lookup"><span data-stu-id="a3192-143">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="a3192-144">Weitere Informationen zum Konfigurieren von Microsoft Endpoint Configuration Manager finden Sie unter [Erstellen und Bereitstellen von Antischadsoftwarerichtlinien: Cloud-Schutzdienst.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)</span><span class="sxs-lookup"><span data-stu-id="a3192-144">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="a3192-145">Verwenden von Gruppenrichtlinien zum Aktivieren des über die Cloud bereitgestellten Schutzes</span><span class="sxs-lookup"><span data-stu-id="a3192-145">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="a3192-146">Öffnen Sie auf Ihrem Gerät für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="a3192-146">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="a3192-147">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="a3192-147">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="a3192-148">Wählen Sie **Administrative Vorlagen** aus.</span><span class="sxs-lookup"><span data-stu-id="a3192-148">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="a3192-149">Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus > MAPS**</span><span class="sxs-lookup"><span data-stu-id="a3192-149">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="a3192-150">Doppelklicken Sie auf **"Microsoft MAPS beitreten".**</span><span class="sxs-lookup"><span data-stu-id="a3192-150">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="a3192-151">Stellen Sie sicher, dass die Option aktiviert ist, und legen Sie sie auf **Basic MAPS** oder **Advanced MAPS** fest.</span><span class="sxs-lookup"><span data-stu-id="a3192-151">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="a3192-152">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="a3192-152">Select **OK**.</span></span>

6. <span data-ttu-id="a3192-153">Doppelklicken Sie auf **Dateibeispiele senden, wenn eine weitere Analyse erforderlich ist.**</span><span class="sxs-lookup"><span data-stu-id="a3192-153">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="a3192-154">Stellen Sie sicher, dass die erste Option auf "Aktiviert" und die anderen Optionen auf **"Aktiviert"** festgelegt sind:</span><span class="sxs-lookup"><span data-stu-id="a3192-154">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="a3192-155">**Sichere Beispiele senden** (1)</span><span class="sxs-lookup"><span data-stu-id="a3192-155">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="a3192-156">**Senden aller Beispiele** (3)</span><span class="sxs-lookup"><span data-stu-id="a3192-156">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="a3192-157">Die Option **"Sichere Beispiele** senden" (1) bedeutet, dass die meisten Beispiele automatisch gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="a3192-157">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="a3192-158">Dateien, die wahrscheinlich persönliche Informationen enthalten, werden weiterhin aufgefordert und erfordern eine zusätzliche Bestätigung.</span><span class="sxs-lookup"><span data-stu-id="a3192-158">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>
        > <span data-ttu-id="a3192-159">Wenn Sie die Option auf **"Immer auffordern"** (0) festlegen, wird der Schutzstatus des Geräts verringert.</span><span class="sxs-lookup"><span data-stu-id="a3192-159">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="a3192-160">Das Festlegen auf **"Nie senden"** (2) bedeutet, dass das Feature ["Bei erster Anzeige blockieren"](configure-block-at-first-sight-microsoft-defender-antivirus.md) von Microsoft Defender für Endpunkt nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a3192-160">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="a3192-161">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="a3192-161">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="a3192-162">Verwenden von PowerShell-Cmdlets zum Aktivieren des über die Cloud bereitgestellten Schutzes</span><span class="sxs-lookup"><span data-stu-id="a3192-162">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="a3192-163">Die folgenden Cmdlets können den über die Cloud bereitgestellten Schutz aktivieren:</span><span class="sxs-lookup"><span data-stu-id="a3192-163">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="a3192-164">Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="a3192-164">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="a3192-165">[Policy CSP – Defender](/windows/client-management/mdm/policy-csp-defender) verfügt auch über weitere Informationen speziell zu [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span><span class="sxs-lookup"><span data-stu-id="a3192-165">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="a3192-166">Sie können auch **"-SubmitSamplesConsent"** `SendSafeSamples` (Standardeinstellung) `NeverSend` oder `AlwaysPrompt` festlegen.</span><span class="sxs-lookup"><span data-stu-id="a3192-166">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="a3192-167">Die `SendSafeSamples` Einstellung bedeutet, dass die meisten Beispiele automatisch gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="a3192-167">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="a3192-168">Dateien, die wahrscheinlich persönliche Informationen enthalten, werden weiterhin aufgefordert und erfordern eine zusätzliche Bestätigung.</span><span class="sxs-lookup"><span data-stu-id="a3192-168">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="a3192-169">Setting **-SubmitSamplesConsent** to `NeverSend` or will lower the protection level of the `AlwaysPrompt` device.</span><span class="sxs-lookup"><span data-stu-id="a3192-169">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="a3192-170">Darüber hinaus bedeutet das Festlegen, `NeverSend` dass das Feature ["Bei erster Anzeige blockieren"](configure-block-at-first-sight-microsoft-defender-antivirus.md) von Microsoft Defender für Endpunkt nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a3192-170">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="a3192-171">Verwenden Windows Management Instruction (WMI) zum Aktivieren des über die Cloud bereitgestellten Schutzes</span><span class="sxs-lookup"><span data-stu-id="a3192-171">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="a3192-172">Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/defender/set-msft-mppreference) für die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="a3192-172">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="a3192-173">Weitere Informationen zu zulässigen Parametern finden Sie unter [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="a3192-173">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="a3192-174">Aktivieren des über die Cloud bereitgestellten Schutzes auf einzelnen Clients mit der Windows-Sicherheit-App</span><span class="sxs-lookup"><span data-stu-id="a3192-174">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="a3192-175">Wenn die **Außerkraftsetzung** der lokalen Einstellung konfigurieren für die Meldung der Gruppenrichtlinieneinstellung von Microsoft MAPS auf **"Deaktiviert"** festgelegt ist, ist die **cloudbasierte Schutzeinstellung** in Windows Einstellungen abgeblendet und nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a3192-175">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="a3192-176">Änderungen, die über ein Gruppenrichtlinienobjekt vorgenommen wurden, müssen zunächst auf einzelnen Endpunkten bereitgestellt werden, bevor die Einstellung in den Windows-Einstellungen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="a3192-176">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="a3192-177">Öffnen Sie die Windows-Sicherheit App, indem Sie das Schildsymbol in der Taskleiste auswählen oder das Startmenü nach **Defender** durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="a3192-177">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="a3192-178">Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) und dann die Bezeichnung **"Viren & Bedrohungsschutzeinstellungen"** aus:</span><span class="sxs-lookup"><span data-stu-id="a3192-178">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Screenshot der Bezeichnung für die Einstellungen des Viren- und Bedrohungsschutzes in der Windows-Sicherheit-App](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="a3192-180">Vergewissern Sie sich, dass **cloudbasierter Schutz** und **automatische Beispielübermittlung** auf **"Ein"** umgestellt sind.</span><span class="sxs-lookup"><span data-stu-id="a3192-180">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="a3192-181">Wenn die automatische Beispielübermittlung mit der Gruppenrichtlinie konfiguriert wurde, ist die Einstellung abgeblendet und nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a3192-181">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a3192-182">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="a3192-182">Related articles</span></span>

- [<span data-ttu-id="a3192-183">Konfigurieren des Timeoutzeitraums für Cloudblockierung</span><span class="sxs-lookup"><span data-stu-id="a3192-183">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a3192-184">Konfigurieren von "Bei erster Anzeige blockieren"</span><span class="sxs-lookup"><span data-stu-id="a3192-184">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a3192-185">Verwenden von PowerShell-Cmdlets zum Verwalten von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="a3192-185">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="a3192-186">[Schützen Windows PCs mit Endpoint Protection für Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span><span class="sxs-lookup"><span data-stu-id="a3192-186">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="a3192-187">Defender-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a3192-187">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="a3192-188">Verwenden des über die Cloud bereitgestellten Microsoft-Schutzes in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="a3192-188">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a3192-189">Erstellen und Bereitstellen von Antischadsoftwarerichtlinien: Cloud-Schutzdienst</span><span class="sxs-lookup"><span data-stu-id="a3192-189">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="a3192-190">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="a3192-190">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
