---
title: Aktivieren von "Bei erster Sicht blockieren", um Schadsoftware in Sekunden zu erkennen
description: Aktivieren Sie das Feature "Beim ersten Blick blockieren", um Schadsoftware innerhalb von Sekunden zu erkennen und zu blockieren.
keywords: scan, BAFS, Malware, first seen, first sight, cloud, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.date: 10/22/2020
ms.technology: mde
ms.openlocfilehash: 1baa770da677ec755bd56db9b92c071680efae7b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765755"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="2237c-104">Aktivieren von Block bei erster Sicht</span><span class="sxs-lookup"><span data-stu-id="2237c-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2237c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2237c-105">**Applies to:**</span></span>

- [<span data-ttu-id="2237c-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2237c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2237c-107">Beim ersten Blick blockieren bietet eine Möglichkeit, neue Schadsoftware innerhalb von Sekunden zu erkennen und zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="2237c-107">Block at first sight provides a way to detect and block new malware within seconds.</span></span> <span data-ttu-id="2237c-108">Dieser Schutz ist standardmäßig aktiviert, wenn bestimmte erforderliche Einstellungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="2237c-108">This protection is enabled by default when certain prerequisite settings are enabled.</span></span> <span data-ttu-id="2237c-109">Zu diesen Einstellungen gehören der von der Cloud zugestellte Schutz, ein angegebenes Zeitlimit für die Beispielübermittlung (z. B. 50 Sekunden) und eine hohe Dateiblockierstufe.</span><span class="sxs-lookup"><span data-stu-id="2237c-109">These settings include cloud-delivered protection, a specified sample submission timeout (such as 50 seconds), and a file-blocking level of high.</span></span> <span data-ttu-id="2237c-110">In den meisten Unternehmensorganisationen sind diese Einstellungen standardmäßig mit Microsoft Defender Antivirus-Bereitstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2237c-110">In most enterprise organizations, these settings are enabled by default with Microsoft Defender Antivirus deployments.</span></span> 

<span data-ttu-id="2237c-111">Sie können [angeben, wie lange](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) die Ausführung einer Datei verhindert werden soll, während der cloudbasierte Schutzdienst die Datei analysiert.</span><span class="sxs-lookup"><span data-stu-id="2237c-111">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="2237c-112">Außerdem können Sie [die Nachricht anpassen,](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) die auf den Desktops der Benutzer angezeigt wird, wenn eine Datei blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="2237c-112">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="2237c-113">Sie können den Firmennamen, die Kontaktinformationen und die Nachrichten-URL ändern.</span><span class="sxs-lookup"><span data-stu-id="2237c-113">You can change the company name, contact information, and message URL.</span></span>

>[!TIP]
><span data-ttu-id="2237c-114">Besuchen Sie die Microsoft Defender for Endpoint-Demowebsite unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu bestätigen, dass die Features funktionieren und wie sie funktionieren.</span><span class="sxs-lookup"><span data-stu-id="2237c-114">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="2237c-115">Funktionsweise</span><span class="sxs-lookup"><span data-stu-id="2237c-115">How it works</span></span>

<span data-ttu-id="2237c-116">Wenn Microsoft Defender Antivirus auf eine verdächtige, aber nicht erkannte Datei trifft, fragt es unser Cloud protection-Back-End ab.</span><span class="sxs-lookup"><span data-stu-id="2237c-116">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="2237c-117">Das Cloud-Back-End wendet Heuristik, maschinelles Lernen und eine automatisierte Analyse der Datei an, um zu bestimmen, ob die Dateien schädlich sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="2237c-117">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="2237c-118">Microsoft Defender Antivirus verwendet mehrere Erkennungs- und Verhinderungstechnologien, um präzisen, intelligenten und Echtzeitschutz zu bieten.</span><span class="sxs-lookup"><span data-stu-id="2237c-118">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> <span data-ttu-id="2237c-119">Weitere Informationen finden Sie in diesem Blog: Erfahren Sie mehr über die erweiterten Technologien im Kern des [Microsoft Defender for Endpoint-Schutzes der nächsten Generation.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="2237c-119">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="2237c-120">![Liste der Microsoft Defender AV-Engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="2237c-120">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="2237c-121">In Windows 10, Version 1803 oder höher, kann block at first sight nicht tragbare ausführbare Dateien (z. B. JS, VBS oder Makros) sowie ausführbare Dateien blockieren.</span><span class="sxs-lookup"><span data-stu-id="2237c-121">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) as well as executable files.</span></span>

<span data-ttu-id="2237c-122">Block at first sight verwendet nur das Cloud protection-Back-End für ausführbare Dateien und nicht tragbare ausführbare Dateien, die aus dem Internet heruntergeladen werden oder aus der Internetzone stammen.</span><span class="sxs-lookup"><span data-stu-id="2237c-122">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="2237c-123">Ein Hashwert der #A0 wird über das Cloud-Back-End überprüft, um zu ermitteln, ob es sich bei der Datei um eine zuvor nicht erkannte Datei handelt.</span><span class="sxs-lookup"><span data-stu-id="2237c-123">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

<span data-ttu-id="2237c-124">Wenn das Cloud-Back-End keine Bestimmung treffen kann, sperrt Microsoft Defender Antivirus die Datei und lädt eine Kopie in die Cloud hoch.</span><span class="sxs-lookup"><span data-stu-id="2237c-124">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="2237c-125">Die Cloud führt eine zusätzliche Analyse durch, um eine Bestimmung zu erreichen, bevor die Datei ausgeführt werden kann, oder blockiert sie in allen zukünftigen Zusammentreffen, je nachdem, ob sie bestimmt, dass die Datei schädlich oder sicher ist.</span><span class="sxs-lookup"><span data-stu-id="2237c-125">The cloud performs additional analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or safe.</span></span>

<span data-ttu-id="2237c-126">In vielen Fällen kann dieser Prozess die Reaktionszeit für neue Schadsoftware von Stunden auf Sekunden reduzieren.</span><span class="sxs-lookup"><span data-stu-id="2237c-126">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="2237c-127">Aktivieren von "Bei erster Sicht blockieren" mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2237c-127">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="2237c-128">Microsoft Intune ist jetzt Teil von Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="2237c-128">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="2237c-129">Navigieren Sie im Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) zu   >  **Gerätekonfigurationsprofile**.</span><span class="sxs-lookup"><span data-stu-id="2237c-129">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="2237c-130">Wählen Oder erstellen Sie ein Profil mithilfe des **Profiltyps Geräteeinschränkungen.**</span><span class="sxs-lookup"><span data-stu-id="2237c-130">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="2237c-131">Legen Sie **in den Konfigurationseinstellungen** für das Profil Geräteeinschränkungen die folgenden Einstellungen unter Microsoft Defender Antivirus ein oder **bestätigen Sie sie:**</span><span class="sxs-lookup"><span data-stu-id="2237c-131">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="2237c-132">**In der Cloud zugestellter Schutz:** Aktiviert</span><span class="sxs-lookup"><span data-stu-id="2237c-132">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="2237c-133">**Dateiblockierstufe**: Hoch</span><span class="sxs-lookup"><span data-stu-id="2237c-133">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="2237c-134">**Zeiterweiterung für die Dateiprüfung in der Cloud**: 50</span><span class="sxs-lookup"><span data-stu-id="2237c-134">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="2237c-135">**Benutzer vor der Beispielübermittlung anforderen:** Alle Daten ohne Aufforderung senden</span><span class="sxs-lookup"><span data-stu-id="2237c-135">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Intune-Konfiguration](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="2237c-137">Speichern Sie Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="2237c-137">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="2237c-138">Wenn Sie die Dateiblockierstufe auf **Hoch festlegen,** wird eine starke Erkennungsstufe angewendet.</span><span class="sxs-lookup"><span data-stu-id="2237c-138">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="2237c-139">In dem unwahrscheinlichen Fall, dass das Blockieren von Dateien zu einer falsch positiven Erkennung legitimer Dateien führt, können Sie [isolierte Dateien wiederherstellen.](./restore-quarantined-files-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="2237c-139">In the unlikely event that file blocking causes a false positive detection of legitimate files, you can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="2237c-140">Weitere Informationen zum Konfigurieren von Microsoft Defender Antivirus-Geräteeinschränkungen in Intune finden Sie unter [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="2237c-140">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="2237c-141">Eine Liste der Microsoft Defender Antivirus-Geräteeinschränkungen in Intune finden Sie unter Geräteeinschränkung für [Windows 10 (und neuere)](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)Einstellungen in Intune .</span><span class="sxs-lookup"><span data-stu-id="2237c-141">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="2237c-142">Aktivieren von "Bei erster Sicht blockieren" mit Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="2237c-142">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="2237c-143">Wenn Sie nach Microsoft Endpoint Configuration Manager suchen, ist er jetzt Teil von Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="2237c-143">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="2237c-144">Wechseln Sie in Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) zu Endpoint **security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="2237c-144">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="2237c-145">Wählen Sie eine vorhandene Richtlinie aus, oder erstellen Sie eine neue Richtlinie mithilfe des Microsoft Defender Antivirus-Profiltyps. </span><span class="sxs-lookup"><span data-stu-id="2237c-145">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="2237c-146">Legen Sie die folgenden Konfigurationseinstellungen ein oder bestätigen Sie sie:</span><span class="sxs-lookup"><span data-stu-id="2237c-146">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="2237c-147">**Aktivieren des in der Cloud zugestellten Schutzes**: Ja</span><span class="sxs-lookup"><span data-stu-id="2237c-147">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="2237c-148">**In der Cloud zugestellte Schutzstufe**: Hoch</span><span class="sxs-lookup"><span data-stu-id="2237c-148">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="2237c-149">**Erweitertes Timeout der Defender Cloud in Sekunden**: 50</span><span class="sxs-lookup"><span data-stu-id="2237c-149">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Blockieren von Einstellungen beim ersten Blick im Endpoint Manager":::

4. <span data-ttu-id="2237c-151">Wenden Sie das Microsoft Defender Antivirus-Profil auf eine Gruppe an, z. B. **Alle** Benutzer , **Alle Geräte** oder **Alle Benutzer und Geräte.**</span><span class="sxs-lookup"><span data-stu-id="2237c-151">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="2237c-152">Aktivieren von "Bei erster Sicht blockieren" mit Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="2237c-152">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="2237c-153">Es wird empfohlen, Intune oder Microsoft Endpoint Manager zu verwenden, um block bei erster Sicht zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2237c-153">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="2237c-154">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie Bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="2237c-154">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="2237c-155">Wechseln Sie **mithilfe des Gruppenrichtlinienverwaltungs-Editors** zu **Computerkonfiguration**  >  **Administrative Vorlagen**  >  **Windows-Komponenten** Microsoft Defender  >  **Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="2237c-155">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="2237c-156">Doppelklicken Sie im Abschnitt MAPS auf Konfigurieren des Features **"Bei** erster Sicht blockieren", und legen Sie es auf **Aktiviert**, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="2237c-156">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2237c-157">Wenn Sie **auf Immer-Eingabeaufforderung (0)** festlegen, wird der Schutzstatus des Geräts gesenkt.</span><span class="sxs-lookup"><span data-stu-id="2237c-157">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="2237c-158">Das Festlegen auf **Nie senden (2)** bedeutet, dass block at first sight nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="2237c-158">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="2237c-159">Doppelklicken Sie im Abschnitt MAPS auf Dateibeispiele senden, wenn eine weitere Analyse erforderlich **ist,** und legen Sie sie auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="2237c-159">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="2237c-160">Wählen **Sie unter Senden von Dateibeispielen, wenn eine weitere** Analyse erforderlich ist, Die Option Alle Beispiele **senden** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2237c-160">Under **Send file samples when further analysis is required**, select **Send all samples**, and then click **OK**.</span></span>

5. <span data-ttu-id="2237c-161">Wenn Sie Einstellungen geändert haben, stellen Sie das Gruppenrichtlinienobjekt in Ihrem Netzwerk erneut zur Sicherstellung der Abgedecktheit aller Endpunkte zur 2.</span><span class="sxs-lookup"><span data-stu-id="2237c-161">If you changed any settings, redeploy the Group Policy Object across your network to ensure all endpoints are covered.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-clients"></a><span data-ttu-id="2237c-162">Bestätigen, dass block at first sight auf einzelnen Clients aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="2237c-162">Confirm block at first sight is enabled on individual clients</span></span>

<span data-ttu-id="2237c-163">Sie können mithilfe von Windows-Sicherheitseinstellungen bestätigen, dass das Blockieren beim ersten Blick auf einzelnen Clients aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2237c-163">You can confirm that block at first sight is enabled on individual clients using Windows security settings.</span></span>

<span data-ttu-id="2237c-164">Beim ersten Blick blockieren wird automatisch aktiviert, solange **der von der Cloud** übermittelte Schutz und die automatische **Beispielübermittlung** aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="2237c-164">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="2237c-165">Öffnen Sie die Windows Security-App.</span><span class="sxs-lookup"><span data-stu-id="2237c-165">Open the Windows Security app.</span></span>

2. <span data-ttu-id="2237c-166">Wählen **Sie viren & Bedrohungsschutz** aus, und wählen Sie dann unter Einstellungen **&** Virenschutz die Option Einstellungen **verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="2237c-166">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Screenshot der Bezeichnung & Virenschutzeinstellungen in der Windows Security App](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="2237c-168">Vergewissern Sie sich, dass der von **der Cloud übermittelte Schutz** und die automatische **Beispielübermittlung** aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="2237c-168">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="2237c-169">Wenn die erforderlichen Einstellungen mithilfe von Gruppenrichtlinien konfiguriert und bereitgestellt werden, sind die in diesem Abschnitt beschriebenen Einstellungen ausgegraut und für die Verwendung auf einzelnen Endpunkten nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2237c-169">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="2237c-170">Änderungen, die über ein Gruppenrichtlinienobjekt vorgenommen werden, müssen zuerst auf einzelnen Endpunkten bereitgestellt werden, bevor die Einstellung in den Windows-Einstellungen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="2237c-170">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="2237c-171">Überprüfen, ob block at first sight funktioniert</span><span class="sxs-lookup"><span data-stu-id="2237c-171">Validate block at first sight is working</span></span>

<span data-ttu-id="2237c-172">Um zu überprüfen, ob das Feature funktioniert, befolgen Sie die Anweisungen unter Überprüfen von Verbindungen [zwischen Ihrem Netzwerk und der Cloud.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="2237c-172">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="2237c-173">Deaktivieren des Blocks bei erster Sicht</span><span class="sxs-lookup"><span data-stu-id="2237c-173">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="2237c-174">Wenn Sie die Sperre beim ersten Blick deaktivieren, wird der Schutzstatus Ihrer Geräte und Ihres Netzwerks gesenkt.</span><span class="sxs-lookup"><span data-stu-id="2237c-174">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="2237c-175">Wenn Sie die erforderlichen Einstellungen beibehalten möchten, ohne den Schutz beim ersten Blick tatsächlich zu verwenden, können Sie die Blockierung auf den ersten Blick deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2237c-175">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="2237c-176">Sie können die Sperre bei erster Sicht vorübergehend deaktivieren, wenn Latenzprobleme auftreten oder Sie die Auswirkungen des Features auf Ihr Netzwerk testen möchten.</span><span class="sxs-lookup"><span data-stu-id="2237c-176">You might do temporarily turn block at first sight off if you are experiencing latency issues or you want to test the feature's impact on your network.</span></span> <span data-ttu-id="2237c-177">Es wird jedoch nicht empfohlen, den Sperrungsschutz beim ersten Blick dauerhaft zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2237c-177">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="2237c-178">Deaktivieren der Sperre beim ersten Blick mit Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="2237c-178">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="2237c-179">Wechseln Sie zu Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="2237c-179">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="2237c-180">Wechseln Sie **zu Endpoint Security**  >  **Antivirus,** und wählen Sie dann Ihre Microsoft Defender Antivirus-Richtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="2237c-180">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="2237c-181">Wählen **Sie unter Verwalten** die Option Eigenschaften **aus.**</span><span class="sxs-lookup"><span data-stu-id="2237c-181">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="2237c-182">Wählen Sie **neben Konfigurationseinstellungen** bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="2237c-182">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="2237c-183">Ändern Sie eine oder mehrere der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="2237c-183">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="2237c-184">Legen **Sie Den in der Cloud übermittelten Schutz auf** **Nein** oder Nicht **konfiguriert ein.**</span><span class="sxs-lookup"><span data-stu-id="2237c-184">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="2237c-185">Legen **Sie in der Cloud zugestellte Schutzstufe** auf Nicht **konfiguriert.**</span><span class="sxs-lookup"><span data-stu-id="2237c-185">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="2237c-186">Löschen Sie das **Feld Erweitertes Timeout in Sekunden in** der Defender Cloud.</span><span class="sxs-lookup"><span data-stu-id="2237c-186">Clear the **Defender Cloud Extended Timeout In Seconds** box.</span></span>

6. <span data-ttu-id="2237c-187">Überprüfen und speichern Sie Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="2237c-187">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="2237c-188">Deaktivieren der Sperre bei erster Sicht mit Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="2237c-188">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="2237c-189">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="2237c-189">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="2237c-190">Wechseln Sie **mit dem Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und klicken Sie auf **Administrative Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="2237c-190">Using the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="2237c-191">Erweitern Sie die Struktur über **die Windows-Komponenten**  >  **Microsoft Defender Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="2237c-191">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="2237c-192">Doppelklicken Sie **auf Konfigurieren des Features "Bei** erster Sicht blockieren", und legen Sie die Option auf **Deaktiviert .**</span><span class="sxs-lookup"><span data-stu-id="2237c-192">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2237c-193">Durch das Deaktivieren von Block beim ersten Blick werden die erforderlichen Gruppenrichtlinien nicht deaktiviert oder geändert.</span><span class="sxs-lookup"><span data-stu-id="2237c-193">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="2237c-194">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2237c-194">See also</span></span>

- [<span data-ttu-id="2237c-195">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="2237c-195">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="2237c-196">Aktivieren des in der Cloud übermittelten Schutzes</span><span class="sxs-lookup"><span data-stu-id="2237c-196">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)