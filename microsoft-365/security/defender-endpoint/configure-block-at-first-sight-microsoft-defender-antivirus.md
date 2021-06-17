---
title: Aktivieren von „Beim ersten Sichten blockieren“ zum Erkennen von Schadsoftware innerhalb von Sekunden
description: Aktivieren Sie das Feature „Beim ersten Sichten blockieren“, um Schadsoftware innert Sekunden zu erkennen und zu blockieren.
keywords: scannen, beim ersten Sichten blockieren, Schadsoftware, erstes Erkennen, Cloud, Defender, Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 06/15/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 3a5f766e21afcb29d3503345a49637061b5f0e38
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964700"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="cee7d-104">Aktivieren von „Beim ersten Sichten blockieren“</span><span class="sxs-lookup"><span data-stu-id="cee7d-104">Turn on block at first sight</span></span>

<span data-ttu-id="cee7d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cee7d-105">**Applies to:**</span></span>

- [<span data-ttu-id="cee7d-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cee7d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="cee7d-107">Dieser Artikel beschreibt ein Antivirus-/Antimalware-Feature, die als „Beim ersten Sichten blockieren“ bekannt ist, und er beschreibt, wie Sie „Beim ersten Sichten blockieren“ für Ihre Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cee7d-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="cee7d-108">Dieser Artikel ist für Unternehmensadministratoren und IT-Profis gedacht, welche die Sicherheitseinstellungen für Organisationen verwalten.</span><span class="sxs-lookup"><span data-stu-id="cee7d-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="cee7d-109">Wenn Sie kein Unternehmensadministrator oder IT-Profi sind, aber Fragen bezüglich „Beim ersten Sichten blockieren“ haben, lesen Sie den Abschnitt [Kein Unternehmensadministrator oder IT-Profi?](#not-an-enterprise-admin-or-it-pro).</span><span class="sxs-lookup"><span data-stu-id="cee7d-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see the [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro) section.</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="cee7d-110">Was ist „Beim ersten Sichten blockieren“?</span><span class="sxs-lookup"><span data-stu-id="cee7d-110">What is "block at first sight"?</span></span>

<span data-ttu-id="cee7d-111">„Beim ersten Sichten blockieren“ ist ein Bedrohungsschutzfeature der nächsten Generation, das neue Malware erkennt und sie innerhalb von Sekunden blockiert.</span><span class="sxs-lookup"><span data-stu-id="cee7d-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="cee7d-112">„Beim ersten Sichten blockieren“ ist aktiviert, wenn gewisse Sicherheitseinstellungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="cee7d-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="cee7d-113">Dazu zählen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="cee7d-113">These settings include:</span></span>

- <span data-ttu-id="cee7d-114">Aus der Cloud bereitgestellter Schutz;</span><span class="sxs-lookup"><span data-stu-id="cee7d-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="cee7d-115">Ein angegebenes Zeitlimit für die Stichprobenübermittlung (z. B. 50 Sekunden); und</span><span class="sxs-lookup"><span data-stu-id="cee7d-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="cee7d-116">Eine Dateiblockierungsstufe von „hoch“.</span><span class="sxs-lookup"><span data-stu-id="cee7d-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="cee7d-117">In den meisten Unternehmensorganisationen werden die Einstellungen, die für das Aktivieren von „Beim ersten Sichten blockieren“ benötigt werden, mit Microsoft Defender Antivirus-Bereitstellungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="cee7d-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="cee7d-118">So funktioniert es</span><span class="sxs-lookup"><span data-stu-id="cee7d-118">How it works</span></span>

<span data-ttu-id="cee7d-119">Wenn Microsoft Defender Antivirus eine verdächtige, aber nicht erkannte Datei findet, wird unser Back-End für Cloudschutz abgefragt.</span><span class="sxs-lookup"><span data-stu-id="cee7d-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="cee7d-120">Das Cloud-Back-End wendet Heuristiken, maschinelles Lernen und automatisiertes Analysieren der Datei an, um festzustellen, ob die Dateien bösartig oder keine Bedrohung sind.</span><span class="sxs-lookup"><span data-stu-id="cee7d-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="cee7d-121">Microsoft Defender Antivirus verwendet mehrere Erkennungs- und Präventionstechnologien, um präzisen, intelligenten und Echtzeit-Schutz zu bieten.</span><span class="sxs-lookup"><span data-stu-id="cee7d-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Liste der Microsoft Defender Antiviren-Module](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="cee7d-123">Weitere Informationen finden Sie unter [(Blog) Lernen Sie die fortschrittlichen Technologien kennen, die den Kern des Schutzes der nächsten Generation für Microsoft Defender für Endpunkt bilden](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span><span class="sxs-lookup"><span data-stu-id="cee7d-123">To learn more, see [(Blog) Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="cee7d-124">Einige Dinge, die man über „Beim ersten Sichten blockieren“ wissen sollte</span><span class="sxs-lookup"><span data-stu-id="cee7d-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="cee7d-125">In Windows 10, Version 1803, können mit „Beim ersten Sichten blockieren“ nicht portable ausführbare Dateien (wie JS, VBS oder Makros) und ausführbare Dateien blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="cee7d-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="cee7d-126">Das Feature „Beim ersten Sichten blockieren“ nutzt das Back-End für Cloudschutz nur für ausführbare und nicht portable ausführbare Dateien, die aus dem Internet heruntergeladen wurden oder aus der Internetzone stammen.</span><span class="sxs-lookup"><span data-stu-id="cee7d-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="cee7d-127">Ein Hashwert der EXE-Datei wird über das Cloud-Back-End überprüft, um zu ermitteln, ob es sich um eine zuvor nicht erkannte Datei handelt.</span><span class="sxs-lookup"><span data-stu-id="cee7d-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="cee7d-128">Wenn das Cloud-Back-End keinen Entscheid fällen kann, sperrt Microsoft Defender Antivirus die Datei und lädt eine Kopie in die Cloud hoch.</span><span class="sxs-lookup"><span data-stu-id="cee7d-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="cee7d-129">Die Cloud führt weitere Analysen durch, um zu einer Entscheidung zu kommen, bevor entweder die Datei ausgeführt werden darf, oder bei jedem zukünftigen Auftreten blockiert wird, je nachdem, ob die Datei als bösartig oder als keine Bedrohung eingestuft wurde.</span><span class="sxs-lookup"><span data-stu-id="cee7d-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="cee7d-130">In vielen Fällen kann dieser Prozess die Reaktionszeit auf neue Schadsoftware von Stunden auf Sekunden reduzieren.</span><span class="sxs-lookup"><span data-stu-id="cee7d-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="cee7d-131">Sie können [angeben, wie lange die Ausführung einer Datei verhindert werden soll](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md), während der cloudbasierte Schutzdienst die Datei analysiert.</span><span class="sxs-lookup"><span data-stu-id="cee7d-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="cee7d-132">Sie können auch [die Nachricht auf den Desktops des Benutzers anpassen](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md), wenn eine Datei blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="cee7d-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="cee7d-133">Sie können den Firmennamen, die Kontaktinformationen und die Nachrichten-URL ändern.</span><span class="sxs-lookup"><span data-stu-id="cee7d-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="cee7d-134">Aktivieren von „Beim ersten Sichten blockieren“ mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="cee7d-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="cee7d-135">Microsoft Intune ist jetzt Bestandteil von Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="cee7d-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="cee7d-136">Navigieren Sie im Microsoft Endpoint Manager-Admin Center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) zu **Geräte** > **Konfigurationsprofile**.</span><span class="sxs-lookup"><span data-stu-id="cee7d-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="cee7d-137">Wählen oder erstellen Sie ein Profil mit dem Profiltyp **Geräteeinschränkungen**.</span><span class="sxs-lookup"><span data-stu-id="cee7d-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="cee7d-138">Setzen oder bestätigen Sie in den **Konfigurationseinstellungen** des Profils für die Geräteeinschränkungen die folgenden Einstellungen unter **Microsoft Defender Antivirus**:</span><span class="sxs-lookup"><span data-stu-id="cee7d-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="cee7d-139">**Aus der Cloud bereitgestellter Schutz**: Aktiviert</span><span class="sxs-lookup"><span data-stu-id="cee7d-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="cee7d-140">**Dateiblockierungsstufe**: Hoch</span><span class="sxs-lookup"><span data-stu-id="cee7d-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="cee7d-141">**Zeitverlängerung für Dateiüberprüfung durch die Cloud**: 50</span><span class="sxs-lookup"><span data-stu-id="cee7d-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="cee7d-142">**Benutzer vor Stichprobenübermittlung auffordern**: Alle Daten ohne Aufforderung senden</span><span class="sxs-lookup"><span data-stu-id="cee7d-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Intune-Konfiguration](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="cee7d-144">Speichern Sie Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="cee7d-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="cee7d-145">Das Festlegen der Dateiblockierungsstufe auf **Hoch** wendet eine starke Erkennungsleistung an.</span><span class="sxs-lookup"><span data-stu-id="cee7d-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="cee7d-146">Im unwahrscheinlichen Fall, dass die Dateisperrung zu einer falsch positiven Erkennung legitimer Dateien führt, kann Ihr Sicherheitsteam [in Quarantäne gestellten Dateien wiederherstellen](./restore-quarantined-files-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="cee7d-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="cee7d-147">Weitere Informationen zum Konfigurieren von Microsoft Defender Antivirus-Geräteeinschränkungen in Intune finden Sie unter [Konfigurieren von Einstellungen für Geräteeinschränkungen in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="cee7d-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="cee7d-148">Eine Liste der Microsoft Defender Antivirus-Geräteeinschränkungen in Intune finden Sie unter [Einstellungen für Geräteeinschränkungen für Windows 10 (und neuer) in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="cee7d-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="cee7d-149">Aktivieren von „Beim ersten Sichten blockieren“ mit Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="cee7d-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="cee7d-150">Wenn Sie den Microsoft Endpoint Configuration Manager suchen, finden Sie ihn jetzt als Teil von Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="cee7d-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="cee7d-151">Im Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) gehen sie zu **Endpunktsicherheit** > **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="cee7d-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="cee7d-152">Wählen Sie eine bestehende Richtlinie aus, oder erstellen Sie eine neue Richtlinie mit dem Profiltyp **Microsoft Defender Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="cee7d-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="cee7d-153">Legen Sie die folgenden Konfigurationseinstellungen fest, oder bestätigen Sie diese:</span><span class="sxs-lookup"><span data-stu-id="cee7d-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="cee7d-154">**Aus der Cloud bereitgestellten Schutz aktivieren**: Ja</span><span class="sxs-lookup"><span data-stu-id="cee7d-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="cee7d-155">**Aus der Cloud bereitgestellte Schutzstufe**: Hoch</span><span class="sxs-lookup"><span data-stu-id="cee7d-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="cee7d-156">**Defender Cloud – erweitertes Zeitlimit in Sekunden**: 50</span><span class="sxs-lookup"><span data-stu-id="cee7d-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="„Beim ersten Sichten blockieren“ in Endpoint Manager":::

4. <span data-ttu-id="cee7d-158">Wenden Sie das Microsoft Defender Antivirus-Profil auf eine Gruppe an, wie z. B. **Alle Benutzer**, **Alle Geräte** oder **Alle Benutzer und Geräte**.</span><span class="sxs-lookup"><span data-stu-id="cee7d-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="cee7d-159">Aktivieren von „Beim ersten Sichten blockieren“ mit der Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="cee7d-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="cee7d-160">Wir empfehlen, Intune oder Microsoft Endpoint Manager zu verwenden, um „Beim ersten Sichten blockieren“ zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cee7d-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="cee7d-161">Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="cee7d-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="cee7d-162">Gehen Sie mithilfe des **Gruppenrichtlinien-Verwaltungseditors** zu **Computer-Konfiguration** > **Administrative Vorlagen** > **Windows-Komponenten** > **Microsoft Defender Antivirus** > **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="cee7d-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="cee7d-163">Doppelklicken Sie im Abschnitt MAPS auf **Konfigurieren des Features „Beim ersten Sichten blockieren“**, legen Sie es auf **Aktiviert** fest, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="cee7d-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cee7d-164">Das Festlegen auf **Immer auffordern (0)** wird den Schutzzustand des Geräts verringern.</span><span class="sxs-lookup"><span data-stu-id="cee7d-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="cee7d-165">Das Festlegen auf **Niemals senden (2)** bedeutet, dass „Beim ersten Sichten blockieren“ nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="cee7d-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="cee7d-166">Doppelklicken Sie im Abschnitt MAPS auf **Dateistichproben senden, wenn eine weitere Analyse erforderlich ist**, und legen Sie dies auf **Aktiviert** fest.</span><span class="sxs-lookup"><span data-stu-id="cee7d-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="cee7d-167">Wählen Sie unter **Dateistichproben senden, wenn eine weitere Analyse erforderlich ist** die Option **Alle Stichproben senden** aus und dann **OK**.</span><span class="sxs-lookup"><span data-stu-id="cee7d-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="cee7d-168">Stellen Sie Ihr Gruppenrichtlinien-Objekt erneut in Ihrem Netzwerk bereit, so wie Sie dies normalerweise tun.</span><span class="sxs-lookup"><span data-stu-id="cee7d-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="cee7d-169">Bestätigen der Aktivierung von „Beim ersten Sichten blockieren“ auf einzelnen Clientgeräten</span><span class="sxs-lookup"><span data-stu-id="cee7d-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="cee7d-170">Mit der Windows-Sicherheit-App können Sie überprüfen, ob „Beim ersten Sichten blockieren“ auf einzelnen Clientgeräten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="cee7d-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="cee7d-171">Die Option „Beim ersten Sichten blockieren“ wird automatisch aktiviert, solange **Aus der Cloud bereitgestellter Schutz** und **Automatische Übermittlung von Stichproben** beide aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="cee7d-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="cee7d-172">Öffnen Sie die Windows-Sicherheit-App.</span><span class="sxs-lookup"><span data-stu-id="cee7d-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="cee7d-173">Wählen Sie **Viren- & Bedrohungsschutz** und dann unter **Einstellungen für Viren- & Bedrohungsschutz** die Option **Einstellungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="cee7d-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Screenshot der Bezeichnung für die Einstellungen des Viren- und Bedrohungsschutzes in der Windows-Sicherheit-App](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="cee7d-175">Bestätigen Sie, dass **Aus der Cloud bereitgestellter Schutz** und **Automatische Übermittlung von Stichproben** beide aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="cee7d-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="cee7d-176">Wenn die erforderlichen Einstellungen konfiguriert sind und mithilfe von Gruppenrichtlinien bereitgestellt werden, sind die Einstellungen in diesem Abschnitt grau hinterlegt und stehen auf einzelnen Endpunkten nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cee7d-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="cee7d-177">Änderungen, die über ein Gruppenrichtlinienobjekt vorgenommen wurden, müssen zunächst auf einzelnen Endpunkten bereitgestellt werden, bevor die Einstellung in den Windows-Einstellungen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="cee7d-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="cee7d-178">Validieren, dass „Beim ersten Sichten blockieren“ funktioniert</span><span class="sxs-lookup"><span data-stu-id="cee7d-178">Validate block at first sight is working</span></span>

<span data-ttu-id="cee7d-179">Um zu validieren, ob das Feature funktioniert, laden Sie die [Beispieldatei „Beim ersten Sichten blockieren“](https://demo.wd.microsoft.com/Page/BAFS) herunter.</span><span class="sxs-lookup"><span data-stu-id="cee7d-179">To validate that the feature is working, download the [Block at first sight sample file](https://demo.wd.microsoft.com/Page/BAFS).</span></span> <span data-ttu-id="cee7d-180">Zum Herunterladen der Datei benötigen Sie ein Konto in Azure AD, dem entweder die Rolle „Sicherheitsadministrator“ oder „Globaler Administrator“ zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="cee7d-180">To download the file, you will need an account in Azure AD that has either the Security Administrator or Global Administrator role assigned.</span></span>

<span data-ttu-id="cee7d-181">Um zu validieren, ob der Cloud-aktivierte Schutz funktioniert, folgen Sie der Anleitung in [Validieren der Verbindungen zwischen Ihrem Netzwerk und der Cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span><span class="sxs-lookup"><span data-stu-id="cee7d-181">To validate that cloud-enabled protection is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span> 

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="cee7d-182">Deaktivieren von „Beim ersten Sichten blockieren“</span><span class="sxs-lookup"><span data-stu-id="cee7d-182">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="cee7d-183">Das Deaktivieren der Option „Beim ersten Sichten blockieren“ wird den Schutzstatus Ihres Geräts / Ihrer Geräte und Ihres Netzwerks verringern.</span><span class="sxs-lookup"><span data-stu-id="cee7d-183">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="cee7d-184">Sie könnten „Beim ersten Sichten blockieren“ deaktivieren, wenn Sie die erforderlichen Einstellungen beibehalten möchten, ohne die Schutzeinstellung „Beim ersten Sichten blockieren“ tatsächlich zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cee7d-184">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="cee7d-185">Sie könnten „Beim ersten Sichten blockieren“ temporär deaktivieren, um zu sehen, wie sich dieses Feature auf Ihr Netzwerk auswirkt.</span><span class="sxs-lookup"><span data-stu-id="cee7d-185">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="cee7d-186">Wir empfehlen jedoch nicht, den Schutz von „Beim ersten Sichten blockieren“ permanent zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="cee7d-186">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="cee7d-187">Deaktivieren von „Beim ersten Sichten blockieren“ mit Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="cee7d-187">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="cee7d-188">Gehen Sie zum Microsoft Endpoint Manager Admin Center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="cee7d-188">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="cee7d-189">Gehen Sie zu **Endpunktsicherheit** > **Antivirus**, und wählen Sie dann Ihre Microsoft Defender Antivirus-Richtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="cee7d-189">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="cee7d-190">Wählen Sie unter **Verwalten** die Option **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="cee7d-190">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="cee7d-191">Wählen Sie direkt neben **Konfigurationseinstellungen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="cee7d-191">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="cee7d-192">Ändern Sie eine oder mehrere der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="cee7d-192">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="cee7d-193">Legen Sie **Aus der Cloud bereitgestellter Schutz aktivieren** auf **Nein** oder **Nicht konfiguriert** fest.</span><span class="sxs-lookup"><span data-stu-id="cee7d-193">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="cee7d-194">Legen Sie **Aus der Cloud bereitgestellte Schutzebene** auf **Nicht konfiguriert** fest.</span><span class="sxs-lookup"><span data-stu-id="cee7d-194">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="cee7d-195">Deaktivieren Sie das Kontrollkästchen **Defender Cloud – erweitertes Zeitlimit in Sekunden**.</span><span class="sxs-lookup"><span data-stu-id="cee7d-195">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="cee7d-196">Überprüfen und Speichern Sie Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="cee7d-196">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="cee7d-197">Deaktivieren von „Beim ersten Sichten blockieren“ mit der Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="cee7d-197">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="cee7d-198">Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="cee7d-198">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="cee7d-199">Gehen Sie mithilfe des **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computerkonfiguration**, und wählen Sie **Administrative Vorlagen** aus.</span><span class="sxs-lookup"><span data-stu-id="cee7d-199">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="cee7d-200">Erweitern Sie die Struktur bis zu **Windows-Komponenten** > **Microsoft Defender Antivirus** > **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="cee7d-200">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="cee7d-201">Doppelklicken Sie auf **Konfigurieren des Features „Beim ersten Sichten blockieren“**, und legen Sie die Option auf **Deaktiviert** fest.</span><span class="sxs-lookup"><span data-stu-id="cee7d-201">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cee7d-202">Das Deaktivieren von „Beim ersten Sichten blockieren“ deaktiviert oder verändert die erforderlichen Gruppenrichtlinien nicht.</span><span class="sxs-lookup"><span data-stu-id="cee7d-202">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="cee7d-203">Kein Unternehmensadministrator oder IT-Profi?</span><span class="sxs-lookup"><span data-stu-id="cee7d-203">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="cee7d-204">Wenn Sie kein Unternehmensadministrator oder IT-Profi sind, aber Fragen bezüglich „Beim ersten Sichten blockieren“ haben, dann ist dieser Abschnitt für Sie.</span><span class="sxs-lookup"><span data-stu-id="cee7d-204">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="cee7d-205">„Beim ersten Sichten blockieren“ ist ein Bedrohungsschutzfeature, das neue Malware erkennt und sie innerhalb von Sekunden blockiert.</span><span class="sxs-lookup"><span data-stu-id="cee7d-205">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="cee7d-206">Obwohl es keine spezifische Einstellung gibt, die „Beim ersten Sichten blockieren“ genannt wird, wird das Feature aktiviert, wenn gewisse Einstellungen auf Ihrem Gerät konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="cee7d-206">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="cee7d-207">So aktivieren oder deaktivieren Sie „Beim ersten Sichten blockieren“ auf Ihrem eigenen Gerät</span><span class="sxs-lookup"><span data-stu-id="cee7d-207">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="cee7d-208">Wenn Sie ein persönliches Gerät haben, das nicht von einer Organisation verwaltet wird, dann fragen Sie sich möglicherweise, wie Sie „Beim ersten Sichten blockieren“ aktivieren oder deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="cee7d-208">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="cee7d-209">Sie können die Windows-Sicherheit-App verwenden, um „Beim ersten Sichten blockieren“ zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="cee7d-209">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="cee7d-210">Öffnen Sie auf Ihrem Windows 10-Computer die Windows-Sicherheit-App.</span><span class="sxs-lookup"><span data-stu-id="cee7d-210">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="cee7d-211">Wählen Sie **Viren- und Bedrohungsschutz** aus.</span><span class="sxs-lookup"><span data-stu-id="cee7d-211">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="cee7d-212">Wählen Sie unter **Einstellungen für Viren- & Bedrohungsschutz** die Option **Einstellungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="cee7d-212">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="cee7d-213">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="cee7d-213">Take one of the following steps:</span></span>

   - <span data-ttu-id="cee7d-214">Um „Beim ersten Sichten blockieren“ zu aktivieren, stellen Sie sicher, dass sowohl **Aus der Cloud bereitgestellter Schutz** wie auch **Automatische Übermittlung von Stichproben** aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="cee7d-214">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="cee7d-215">Um „Beim ersten Sichten blockieren“ zu deaktivieren, deaktivieren Sie **Aus der Cloud bereitgestellter Schutz** oder **Automatische Übermittlung von Stichproben**.</span><span class="sxs-lookup"><span data-stu-id="cee7d-215">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="cee7d-216">Das Deaktivieren von „Beim ersten Sichten blockieren“ verringert die Schutzebene für Ihr Gerät.</span><span class="sxs-lookup"><span data-stu-id="cee7d-216">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="cee7d-217">Wir empfehlen nicht, „Beim ersten Sichten blockieren“ permanent zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="cee7d-217">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="cee7d-218">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cee7d-218">See also</span></span>

- [<span data-ttu-id="cee7d-219">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="cee7d-219">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="cee7d-220">Aus der Cloud bereitgestellten Schutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="cee7d-220">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cee7d-221">Mit Windows-Sicherheit geschützt bleiben</span><span class="sxs-lookup"><span data-stu-id="cee7d-221">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)
