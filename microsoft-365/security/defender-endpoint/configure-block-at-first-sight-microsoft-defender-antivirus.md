---
title: Aktivieren von "Bei erster Sicht blockieren", um Schadsoftware in Sekunden zu erkennen
description: Aktivieren Sie das Feature "Beim ersten Blick blockieren", um Schadsoftware innerhalb von Sekunden zu erkennen und zu blockieren.
keywords: Scannen, Beim ersten Blick blockieren, Schadsoftware, erster Blick, Cloud, Verteidiger, Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.openlocfilehash: d4db3549d04e5883f02ba263c06371371d385022
ms.sourcegitcommit: 8c89bc1d106b4716b07a1977d57e4d9ef98aecb3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2021
ms.locfileid: "52079203"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="9d803-104">Aktivieren von „Bei erster Anzeige blockieren“</span><span class="sxs-lookup"><span data-stu-id="9d803-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9d803-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9d803-105">**Applies to:**</span></span>

- [<span data-ttu-id="9d803-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9d803-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9d803-107">In diesem Artikel wird ein Antiviren-/Antischalwarefeature beschrieben, das als "Bei erster Augen blockieren" bezeichnet wird, und es wird beschrieben, wie Sie die Sperre beim ersten Blick für Ihre Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9d803-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="9d803-108">Dieser Artikel richtet sich an Unternehmensadministratoren und IT-Profis, die Sicherheitseinstellungen für Organisationen verwalten.</span><span class="sxs-lookup"><span data-stu-id="9d803-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="9d803-109">Wenn Sie kein Enteprise-Administrator oder IT-Pro sind, aber Fragen zum Blockieren auf den ersten Blick haben, finden Sie weitere Informationen unter [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro).</span><span class="sxs-lookup"><span data-stu-id="9d803-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro).</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="9d803-110">Was ist "Beim ersten Blick blockieren"?</span><span class="sxs-lookup"><span data-stu-id="9d803-110">What is "block at first sight"?</span></span>

<span data-ttu-id="9d803-111">Beim ersten Blick blockieren ist ein Bedrohungsschutzfeature des Schutzes der nächsten Generation, das neue Schadsoftware erkennt und innerhalb von Sekunden blockiert.</span><span class="sxs-lookup"><span data-stu-id="9d803-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="9d803-112">Beim ersten Blick blockieren ist aktiviert, wenn bestimmte Sicherheitseinstellungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="9d803-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="9d803-113">Zu diesen Einstellungen gehören:</span><span class="sxs-lookup"><span data-stu-id="9d803-113">These settings include:</span></span>

- <span data-ttu-id="9d803-114">In der Cloud zugestellter Schutz;</span><span class="sxs-lookup"><span data-stu-id="9d803-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="9d803-115">Ein angegebenes Zeitlimit für die Beispielübermittlung (z. B. 50 Sekunden); und</span><span class="sxs-lookup"><span data-stu-id="9d803-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="9d803-116">Eine Hohe Dateiblockierungsstufe.</span><span class="sxs-lookup"><span data-stu-id="9d803-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="9d803-117">In den meisten Unternehmensorganisationen sind die Einstellungen, die zum Aktivieren von "Block at first sight" erforderlich sind, mit Microsoft Defender Antivirus-Bereitstellungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9d803-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="9d803-118">Funktionsweise</span><span class="sxs-lookup"><span data-stu-id="9d803-118">How it works</span></span>

<span data-ttu-id="9d803-119">Wenn Microsoft Defender Antivirus auf eine verdächtige, aber nicht erkannte Datei trifft, fragt es unser Cloud protection-Back-End ab.</span><span class="sxs-lookup"><span data-stu-id="9d803-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="9d803-120">Das Cloud-Back-End wendet Heuristik, maschinelles Lernen und eine automatisierte Analyse der Datei an, um zu bestimmen, ob die Dateien schädlich sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="9d803-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="9d803-121">Microsoft Defender Antivirus verwendet mehrere Erkennungs- und Verhinderungstechnologien, um präzisen, intelligenten und Echtzeitschutz zu bieten.</span><span class="sxs-lookup"><span data-stu-id="9d803-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Liste der Microsoft Defender AV-Engines](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="9d803-123">Weitere Informationen finden Sie in diesem Blog: Erfahren Sie mehr über die erweiterten Technologien im Kern des [Microsoft Defender for Endpoint-Schutzes der nächsten Generation.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="9d803-123">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="9d803-124">Einige Dinge, die Sie beim ersten Blick zu blockieren wissen sollten</span><span class="sxs-lookup"><span data-stu-id="9d803-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="9d803-125">In Windows 10, Version 1803 oder höher, kann block at first sight nicht tragbare ausführbare Dateien (z. B. JS, VBS oder Makros) und ausführbare Dateien blockieren.</span><span class="sxs-lookup"><span data-stu-id="9d803-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="9d803-126">Block at first sight verwendet nur das Cloud protection-Back-End für ausführbare Dateien und nicht tragbare ausführbare Dateien, die aus dem Internet heruntergeladen werden oder aus der Internetzone stammen.</span><span class="sxs-lookup"><span data-stu-id="9d803-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="9d803-127">Ein Hashwert der #A0 wird über das Cloud-Back-End überprüft, um zu ermitteln, ob es sich bei der Datei um eine zuvor nicht erkannte Datei handelt.</span><span class="sxs-lookup"><span data-stu-id="9d803-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="9d803-128">Wenn das Cloud-Back-End keine Bestimmung treffen kann, sperrt Microsoft Defender Antivirus die Datei und lädt eine Kopie in die Cloud hoch.</span><span class="sxs-lookup"><span data-stu-id="9d803-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="9d803-129">Die Cloud führt mehr Analysen durch, um eine Bestimmung zu erreichen, bevor die Datei ausgeführt werden kann, oder blockiert sie in allen zukünftigen Zusammentreffen, je nachdem, ob die Datei als schädlich oder nicht als Bedrohung ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="9d803-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="9d803-130">In vielen Fällen kann dieser Prozess die Reaktionszeit für neue Schadsoftware von Stunden auf Sekunden reduzieren.</span><span class="sxs-lookup"><span data-stu-id="9d803-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="9d803-131">Sie können [angeben, wie lange](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) die Ausführung einer Datei verhindert werden soll, während der cloudbasierte Schutzdienst die Datei analysiert.</span><span class="sxs-lookup"><span data-stu-id="9d803-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="9d803-132">Außerdem können Sie [die Nachricht anpassen,](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) die auf den Desktops der Benutzer angezeigt wird, wenn eine Datei blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="9d803-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="9d803-133">Sie können den Firmennamen, die Kontaktinformationen und die Nachrichten-URL ändern.</span><span class="sxs-lookup"><span data-stu-id="9d803-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="9d803-134">Aktivieren von "Bei erster Sicht blockieren" mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9d803-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="9d803-135">Microsoft Intune ist jetzt Teil von Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="9d803-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="9d803-136">Navigieren Sie im Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) zu   >  **Gerätekonfigurationsprofile**.</span><span class="sxs-lookup"><span data-stu-id="9d803-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="9d803-137">Wählen Oder erstellen Sie ein Profil mithilfe des **Profiltyps Geräteeinschränkungen.**</span><span class="sxs-lookup"><span data-stu-id="9d803-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="9d803-138">Legen Sie **in den Konfigurationseinstellungen** für das Profil Geräteeinschränkungen die folgenden Einstellungen unter Microsoft Defender Antivirus ein oder **bestätigen Sie sie:**</span><span class="sxs-lookup"><span data-stu-id="9d803-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="9d803-139">**In der Cloud zugestellter Schutz:** Aktiviert</span><span class="sxs-lookup"><span data-stu-id="9d803-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="9d803-140">**Dateiblockierstufe**: Hoch</span><span class="sxs-lookup"><span data-stu-id="9d803-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="9d803-141">**Zeiterweiterung für die Dateiprüfung in der Cloud**: 50</span><span class="sxs-lookup"><span data-stu-id="9d803-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="9d803-142">**Benutzer vor der Beispielübermittlung anforderen:** Alle Daten ohne Aufforderung senden</span><span class="sxs-lookup"><span data-stu-id="9d803-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Intune-Konfiguration](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="9d803-144">Speichern Sie Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="9d803-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="9d803-145">Wenn Sie die Dateiblockierstufe auf **Hoch festlegen,** wird eine starke Erkennungsstufe angewendet.</span><span class="sxs-lookup"><span data-stu-id="9d803-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="9d803-146">In dem unwahrscheinlichen Fall, dass das Blockieren von Dateien zu einer falsch positiven Erkennung legitimer Dateien führt, kann Ihr Sicherheitsteam [isolierte Dateien wiederherstellen.](./restore-quarantined-files-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9d803-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="9d803-147">Weitere Informationen zum Konfigurieren von Microsoft Defender Antivirus-Geräteeinschränkungen in Intune finden Sie unter [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="9d803-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="9d803-148">Eine Liste der Microsoft Defender Antivirus-Geräteeinschränkungen in Intune finden Sie unter Geräteeinschränkung für [Windows 10 (und neuere)](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)Einstellungen in Intune .</span><span class="sxs-lookup"><span data-stu-id="9d803-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="9d803-149">Aktivieren von "Bei erster Sicht blockieren" mit Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="9d803-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="9d803-150">Wenn Sie nach Microsoft Endpoint Configuration Manager suchen, ist er jetzt Teil von Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="9d803-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="9d803-151">Wechseln Sie in Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) zu Endpoint **security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="9d803-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="9d803-152">Wählen Sie eine vorhandene Richtlinie aus, oder erstellen Sie eine neue Richtlinie mithilfe des Microsoft Defender Antivirus-Profiltyps. </span><span class="sxs-lookup"><span data-stu-id="9d803-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="9d803-153">Legen Sie die folgenden Konfigurationseinstellungen ein oder bestätigen Sie sie:</span><span class="sxs-lookup"><span data-stu-id="9d803-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="9d803-154">**Aktivieren des in der Cloud zugestellten Schutzes**: Ja</span><span class="sxs-lookup"><span data-stu-id="9d803-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="9d803-155">**In der Cloud zugestellte Schutzstufe**: Hoch</span><span class="sxs-lookup"><span data-stu-id="9d803-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="9d803-156">**Erweitertes Timeout der Defender Cloud in Sekunden**: 50</span><span class="sxs-lookup"><span data-stu-id="9d803-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Blockieren von Einstellungen beim ersten Blick im Endpoint Manager":::

4. <span data-ttu-id="9d803-158">Wenden Sie das Microsoft Defender Antivirus-Profil auf eine Gruppe an, z. B. **Alle** Benutzer , **Alle Geräte** oder **Alle Benutzer und Geräte.**</span><span class="sxs-lookup"><span data-stu-id="9d803-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="9d803-159">Aktivieren von "Bei erster Sicht blockieren" mit Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="9d803-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="9d803-160">Es wird empfohlen, Intune oder Microsoft Endpoint Manager zu verwenden, um block bei erster Sicht zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9d803-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="9d803-161">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie Bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="9d803-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="9d803-162">Wechseln Sie **mithilfe des Gruppenrichtlinienverwaltungs-Editors** zu **Computerkonfiguration**  >  **Administrative Vorlagen**  >  **Windows-Komponenten** Microsoft Defender  >  **Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="9d803-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="9d803-163">Doppelklicken Sie im Abschnitt MAPS auf Konfigurieren des Features **"Bei** erster Sicht blockieren", und legen Sie es auf **Aktiviert**, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="9d803-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9d803-164">Wenn Sie **auf Immer-Eingabeaufforderung (0)** festlegen, wird der Schutzstatus des Geräts gesenkt.</span><span class="sxs-lookup"><span data-stu-id="9d803-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="9d803-165">Das Festlegen auf **Nie senden (2)** bedeutet, dass block at first sight nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9d803-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="9d803-166">Doppelklicken Sie im Abschnitt MAPS auf Dateibeispiele senden, wenn eine weitere Analyse erforderlich **ist,** und legen Sie sie auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="9d803-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="9d803-167">Wählen **Sie unter Senden von Dateibeispielen, wenn eine weitere** Analyse erforderlich ist, Die Option Alle Beispiele **senden** aus, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="9d803-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="9d803-168">Stellen Sie Ihr Gruppenrichtlinienobjekt wie üblich in Ihrem Netzwerk erneut zur Bereitstellung ein.</span><span class="sxs-lookup"><span data-stu-id="9d803-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="9d803-169">Bestätigen, dass auf einzelnen Clientgeräten die Option "Beim ersten Blick blockieren" aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="9d803-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="9d803-170">Sie können mithilfe der Windows Security-App bestätigen, dass die Sperre beim ersten Blick auf einzelnen Clientgeräten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9d803-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="9d803-171">Beim ersten Blick blockieren wird automatisch aktiviert, solange **der von der Cloud** übermittelte Schutz und die automatische **Beispielübermittlung** aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="9d803-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="9d803-172">Öffnen Sie die Windows Security-App.</span><span class="sxs-lookup"><span data-stu-id="9d803-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="9d803-173">Wählen **Sie viren & Bedrohungsschutz** aus, und wählen Sie dann unter Einstellungen **&** Virenschutz die Option Einstellungen **verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="9d803-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Screenshot der Bezeichnung & Virenschutzeinstellungen in der Windows Security App](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="9d803-175">Vergewissern Sie sich, dass der von **der Cloud übermittelte Schutz** und die automatische **Beispielübermittlung** aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="9d803-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="9d803-176">Wenn die erforderlichen Einstellungen mithilfe von Gruppenrichtlinien konfiguriert und bereitgestellt werden, sind die in diesem Abschnitt beschriebenen Einstellungen ausgegraut und für die Verwendung auf einzelnen Endpunkten nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9d803-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="9d803-177">Änderungen, die über ein Gruppenrichtlinienobjekt vorgenommen werden, müssen zuerst auf einzelnen Endpunkten bereitgestellt werden, bevor die Einstellung in den Windows-Einstellungen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="9d803-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="9d803-178">Überprüfen, ob block at first sight funktioniert</span><span class="sxs-lookup"><span data-stu-id="9d803-178">Validate block at first sight is working</span></span>

<span data-ttu-id="9d803-179">Um zu überprüfen, ob das Feature funktioniert, befolgen Sie die Anweisungen unter Überprüfen von Verbindungen [zwischen Ihrem Netzwerk und der Cloud.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="9d803-179">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="9d803-180">Deaktivieren des Blocks bei erster Sicht</span><span class="sxs-lookup"><span data-stu-id="9d803-180">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="9d803-181">Wenn Sie die Sperre beim ersten Blick deaktivieren, wird der Schutzstatus Ihrer Geräte und Ihres Netzwerks gesenkt.</span><span class="sxs-lookup"><span data-stu-id="9d803-181">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="9d803-182">Wenn Sie die erforderlichen Einstellungen beibehalten möchten, ohne den Schutz beim ersten Blick tatsächlich zu verwenden, können Sie die Blockierung auf den ersten Blick deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9d803-182">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="9d803-183">Sie können die Sperre bei erster Sicht vorübergehend deaktivieren, um zu sehen, wie sich dieses Feature auf Ihr Netzwerk auswirkt.</span><span class="sxs-lookup"><span data-stu-id="9d803-183">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="9d803-184">Es wird jedoch nicht empfohlen, den Sperrungsschutz beim ersten Blick dauerhaft zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9d803-184">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="9d803-185">Deaktivieren der Sperre beim ersten Blick mit Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="9d803-185">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="9d803-186">Wechseln Sie zu Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="9d803-186">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="9d803-187">Wechseln Sie **zu Endpoint Security**  >  **Antivirus,** und wählen Sie dann Ihre Microsoft Defender Antivirus-Richtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="9d803-187">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="9d803-188">Wählen **Sie unter Verwalten** die Option Eigenschaften **aus.**</span><span class="sxs-lookup"><span data-stu-id="9d803-188">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="9d803-189">Wählen Sie **neben Konfigurationseinstellungen** bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="9d803-189">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="9d803-190">Ändern Sie eine oder mehrere der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="9d803-190">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="9d803-191">Legen **Sie Den in der Cloud übermittelten Schutz auf** **Nein** oder Nicht **konfiguriert ein.**</span><span class="sxs-lookup"><span data-stu-id="9d803-191">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="9d803-192">Legen **Sie in der Cloud zugestellte Schutzstufe** auf Nicht **konfiguriert.**</span><span class="sxs-lookup"><span data-stu-id="9d803-192">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="9d803-193">Aktivieren Sie das Kontrollkästchen für **erweitertes Defender Cloud-Timeout in Sekunden**.</span><span class="sxs-lookup"><span data-stu-id="9d803-193">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="9d803-194">Überprüfen und speichern Sie Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="9d803-194">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="9d803-195">Deaktivieren der Sperre bei erster Sicht mit Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="9d803-195">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="9d803-196">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann Bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="9d803-196">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="9d803-197">Wechseln Sie **mit dem Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen aus.**</span><span class="sxs-lookup"><span data-stu-id="9d803-197">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="9d803-198">Erweitern Sie die Struktur über **die Windows-Komponenten**  >  **Microsoft Defender Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="9d803-198">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="9d803-199">Doppelklicken Sie **auf Konfigurieren des Features "Bei** erster Sicht blockieren", und legen Sie die Option auf **Deaktiviert .**</span><span class="sxs-lookup"><span data-stu-id="9d803-199">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9d803-200">Durch das Deaktivieren von Block beim ersten Blick werden die erforderlichen Gruppenrichtlinien nicht deaktiviert oder geändert.</span><span class="sxs-lookup"><span data-stu-id="9d803-200">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="9d803-201">Kein Unternehmensadministrator oder IT-Pro?</span><span class="sxs-lookup"><span data-stu-id="9d803-201">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="9d803-202">Wenn Sie kein Unternehmensadministrator oder IT-Pro sind, aber Fragen zum Blockieren auf den ersten Blick haben, ist dieser Abschnitt für Sie da.</span><span class="sxs-lookup"><span data-stu-id="9d803-202">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="9d803-203">Beim ersten Blick blockieren ist ein Feature zum Schutz vor Bedrohungen, das Schadsoftware innerhalb von Sekunden erkennt und blockiert.</span><span class="sxs-lookup"><span data-stu-id="9d803-203">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="9d803-204">Obwohl es keine bestimmte Einstellung namens "Bei erster Sicht blockieren" gibt, ist das Feature aktiviert, wenn bestimmte Einstellungen auf Ihrem Gerät konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="9d803-204">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="9d803-205">So verwalten Sie block at first sight on or off auf Ihrem eigenen Gerät</span><span class="sxs-lookup"><span data-stu-id="9d803-205">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="9d803-206">Wenn Sie über ein persönliches Gerät verfügen, das nicht von einer Organisation verwaltet wird, fragen Sie sich möglicherweise, wie Sie die Sperre beim ersten Blick ein- oder ausschalten.</span><span class="sxs-lookup"><span data-stu-id="9d803-206">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="9d803-207">Sie können die Windows Security-App verwenden, um den Block auf den ersten Blick zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="9d803-207">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="9d803-208">Öffnen Sie auf Ihrem Windows 10-Computer die Windows Security-App.</span><span class="sxs-lookup"><span data-stu-id="9d803-208">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="9d803-209">Wählen **Sie Virenschutz & Bedrohungsschutz aus.**</span><span class="sxs-lookup"><span data-stu-id="9d803-209">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="9d803-210">Wählen **Sie unter & Bedrohungsschutzeinstellungen** die Option Einstellungen verwalten **aus.**</span><span class="sxs-lookup"><span data-stu-id="9d803-210">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="9d803-211">Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="9d803-211">Take one of the following steps:</span></span>

   - <span data-ttu-id="9d803-212">Stellen Sie sicher, dass sowohl der in der  **Cloud** zugestellte Schutz als auch die automatische Beispielübermittlung aktiviert sind, um das Blockieren beim ersten Blick zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9d803-212">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="9d803-213">Deaktivieren Sie den Cloud-zugestellten Schutz oder die **automatische** Beispielübermittlung, um das Blockieren beim ersten Blick **zu deaktivieren.**</span><span class="sxs-lookup"><span data-stu-id="9d803-213">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="9d803-214">Wenn Sie den Block auf den ersten Blick deaktivieren, wird das Schutzniveau für Ihr Gerät gesenkt.</span><span class="sxs-lookup"><span data-stu-id="9d803-214">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="9d803-215">Es wird nicht empfohlen, den Block beim ersten Blick dauerhaft zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9d803-215">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="9d803-216">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d803-216">See also</span></span>

- [<span data-ttu-id="9d803-217">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="9d803-217">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="9d803-218">Aktivieren des in der Cloud übermittelten Schutzes</span><span class="sxs-lookup"><span data-stu-id="9d803-218">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9d803-219">Bleiben Sie mit Windows Security geschützt</span><span class="sxs-lookup"><span data-stu-id="9d803-219">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)