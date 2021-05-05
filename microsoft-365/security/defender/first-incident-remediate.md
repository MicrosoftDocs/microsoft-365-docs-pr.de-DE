---
title: 'Schritt 2: Behebung Des ersten Vorfalls'
description: Erste Schritte bei der Behebung Ihres ersten Vorfalls in Microsoft 365 Defender.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, microsoft, m365, Reaktion auf Vorfälle, Cyberangriff
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2fe6c5b1b0feea2163c0a2bcc871921a885abb85
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114988"
---
# <a name="step-2-remediate-your-first-incident"></a><span data-ttu-id="5d410-105">Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="5d410-105">Step 2.</span></span> <span data-ttu-id="5d410-106">Behebung Des ersten Vorfalls</span><span class="sxs-lookup"><span data-stu-id="5d410-106">Remediate your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5d410-107">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5d410-107">**Applies to:**</span></span>
- <span data-ttu-id="5d410-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d410-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="5d410-109">Microsoft 365 Defender bietet nicht nur Erkennungs- und Analysefunktionen, sondern bietet auch Eindämmung und Beseitigung von Schadsoftware.</span><span class="sxs-lookup"><span data-stu-id="5d410-109">Microsoft 365 Defender not only provides detection and analysis capabilities but also provides containment and eradication of malware.</span></span> <span data-ttu-id="5d410-110">Containment umfasst Schritte, um die Auswirkungen des Angriffs zu reduzieren, während die Auslöschung sicherstellt, dass alle Spuren von Angreiferaktivitäten aus dem Netzwerk entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="5d410-110">Containment includes steps to reduce the impact of the attack while eradication ensures all traces of attacker activity are removed from the network.</span></span>  <span data-ttu-id="5d410-111">Microsoft 365 Defender bietet verschiedene Korrekturaktionen, die je nach Betriebssystem und Angriffstyp für die automatische Behebung konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="5d410-111">Microsoft 365 Defender offers several remediation actions which can be configured to auto-remediate depending on your operating system and the attack type.</span></span>

<span data-ttu-id="5d410-112">Microsoft 365 Defender bietet mehrere Korrekturaktionen, die Analysten manuell initiieren können.</span><span class="sxs-lookup"><span data-stu-id="5d410-112">Microsoft 365 Defender offers several remediation actions that analysts can manually initiate.</span></span> <span data-ttu-id="5d410-113">Aktionen sind in zwei Kategorien unterteilt: Aktionen auf Geräten und Aktionen für Dateien.</span><span class="sxs-lookup"><span data-stu-id="5d410-113">Actions are separated into two categories, Actions on devices and Actions on files.</span></span> <span data-ttu-id="5d410-114">Einige Aktionen können verwendet werden, um die Bedrohung sofort zu beenden, während andere Aktionen bei der weiteren forensischen Analyse helfen.</span><span class="sxs-lookup"><span data-stu-id="5d410-114">Some actions can be used to immediately stop the threat while other actions assist in further forensic analysis.</span></span>

## <a name="actions-on-devices"></a><span data-ttu-id="5d410-115">Aktionen auf Geräten</span><span class="sxs-lookup"><span data-stu-id="5d410-115">Actions on devices</span></span>

- <span data-ttu-id="5d410-116">**Gerät** isolieren – Diese Aktivität blockiert sofort den ganzen Netzwerkdatenverkehr (Internet und intern), um die Verbreitung von Schadsoftware zu minimieren und Analysten die Fortsetzung der Analyse zu ermöglichen, ohne dass ein böswilliger Akteur einen Angriff fortsetzen kann.</span><span class="sxs-lookup"><span data-stu-id="5d410-116">**Isolate the device** - This activity immediately blocks all network traffic (internet and internal) to minimize the spread of malware and allow analysts to continue analysis without a malicious actor being able to continue an attack.</span></span> <span data-ttu-id="5d410-117">Die einzige zulässige Verbindung ist die Microsoft Defender for Identity -Dienst-Cloud, damit Microsoft Defender for Identity das Gerät weiterhin überwachen kann.</span><span class="sxs-lookup"><span data-stu-id="5d410-117">The only connection allowed is to the Microsoft Defender for Identity service cloud so Microsoft Defender for Identity can continue to monitor the device.</span></span> 
- <span data-ttu-id="5d410-118">**Einschränken der** App-Ausführung: Um die Ausführung einer Anwendung einzuschränken, wird eine Codeintegritätsrichtlinie angewendet, die nur die Ausführung von Dateien zulässt, wenn sie von einem von Microsoft ausgestellten Zertifikat signiert sind.</span><span class="sxs-lookup"><span data-stu-id="5d410-118">**Restrict app execution** - To restrict an application from running, a code integrity policy is applied that only allows files to run if they are signed by a Microsoft-issued certificate.</span></span> <span data-ttu-id="5d410-119">Diese Einschränkungsmethode kann verhindern, dass ein Angreifer gefährdete Geräte steuert und weitere schädliche Aktivitäten ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="5d410-119">This method of restriction can help prevent an attacker from controlling compromised devices and performing further malicious activities.</span></span>
- <span data-ttu-id="5d410-120">**Antivirusscan ausführen** – Eine Microsoft Defender Antivirus kann zusammen mit anderen Antivirenlösungen ausgeführt werden, unabhängig davon, ob Defender Antivirus die aktive Antivirenlösung ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="5d410-120">**Run Antivirus scan** - A Microsoft Defender Antivirus scan can run alongside other antivirus solutions, whether Defender Antivirus is the active antivirus solution or not.</span></span> <span data-ttu-id="5d410-121">Wenn ein anderes Antivirenprodukt die primäre Endpunktschutzlösung ist, können Sie Defender Antivirus im passiven Modus ausführen.</span><span class="sxs-lookup"><span data-stu-id="5d410-121">If another antivirus vendor product is the primary endpoint protection solution, you can run Defender Antivirus in Passive mode.</span></span>
- <span data-ttu-id="5d410-122">**Initiieren einer automatisierten** Untersuchung – Sie können eine neue allgemeine automatisierte Untersuchung auf dem Gerät starten.</span><span class="sxs-lookup"><span data-stu-id="5d410-122">**Initiate automated investigation** - You can start a new general purpose automated investigation on the device.</span></span> <span data-ttu-id="5d410-123">Während eine Untersuchung ausgeführt wird, werden alle anderen vom Gerät generierten Warnungen einer fortlaufenden automatisierten Untersuchung hinzugefügt, bis diese Untersuchung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5d410-123">While an investigation is running, any other alert generated from the device will be added to an ongoing automated investigation until that investigation is completed.</span></span> <span data-ttu-id="5d410-124">Wenn die gleiche Bedrohung auch auf anderen Geräten angezeigt wird, werden diese Geräte der Untersuchung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5d410-124">In addition, if the same threat is seen on other devices, those devices are added to the investigation.</span></span>
- <span data-ttu-id="5d410-125">**Liveantwort initiieren** – Liveantwort ist eine Funktion, mit der Sie über eine Remoteshellverbindung sofort auf ein Gerät zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="5d410-125">**Initiate live response** - Live response is a capability that gives you instantaneous access to a device by using a remote shell connection.</span></span> <span data-ttu-id="5d410-126">Dadurch können Sie eingehende Ermittlungen durchführen und sofort Maßnahmen ergreifen, um identifizierte Bedrohungen zeitnah in Echtzeit zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="5d410-126">This gives you the ability to do in-depth investigative work and take immediate response actions to promptly contain identified threats in real time.</span></span> <span data-ttu-id="5d410-127">Die Liveantwort dient der Verbesserung der Untersuchungen, indem Sie forensische Daten sammeln, Skripts ausführen, verdächtige Entitäten zur Analyse senden, Bedrohungen behebt und proaktiv nach neuen Bedrohungen fahnen kann.</span><span class="sxs-lookup"><span data-stu-id="5d410-127">Live response is designed to enhance investigations by enabling you to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span>
- <span data-ttu-id="5d410-128">**Untersuchungspaket sammeln** – Im Rahmen des Untersuchungs- oder Reaktionsprozesses können Sie ein Untersuchungspaket von einem Gerät erfassen.</span><span class="sxs-lookup"><span data-stu-id="5d410-128">**Collect investigation package** - As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="5d410-129">Durch das Sammeln des Untersuchungspakets können Sie den aktuellen Zustand des Geräts identifizieren und die vom Angreifer verwendeten Tools und Techniken besser verstehen.</span><span class="sxs-lookup"><span data-stu-id="5d410-129">By collecting the investigation package, you can identify the current state of the device and further understand the tools and techniques used by the attacker.</span></span> 
- <span data-ttu-id="5d410-130">**Konsultieren Sie einen** Bedrohungsexperten (verfügbar in Aktionen auf Geräten und Dateien) – Sie können einen Microsoft-Bedrohungsexperten konsultieren, um weitere Informationen zu potenziell gefährdeten Geräten oder Geräten zu erhalten, die bereits gefährdet sind.</span><span class="sxs-lookup"><span data-stu-id="5d410-130">**Consult a threat expert** (available in both Actions on devices and files) - You can consult a Microsoft threat expert for more insights regarding potentially compromised devices or devices that are already compromised.</span></span> <span data-ttu-id="5d410-131">Microsoft-Bedrohungsexperten können direkt innerhalb des Microsoft Defender Security Center eine zeitnahe und genaue Antwort erhalten.</span><span class="sxs-lookup"><span data-stu-id="5d410-131">Microsoft threat experts can be engaged directly from within the Microsoft Defender Security Center for a timely and accurate response.</span></span> 

## <a name="actions-on-files"></a><span data-ttu-id="5d410-132">Aktionen für Dateien</span><span class="sxs-lookup"><span data-stu-id="5d410-132">Actions on files</span></span>

- <span data-ttu-id="5d410-133">**Datei beenden und isolieren** – Diese Aktion umfasst das Beenden von ausgeführten Prozessen, das Quarantinieren von Dateien und das Löschen persistenter Daten, z. B. aller Registrierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="5d410-133">**Stop and quarantine file** - This action includes stopping running processes, quarantining files, and deleting persistent data, such as any registry keys.</span></span> <span data-ttu-id="5d410-134">Diese Aktion wird auf Geräten mit Windows 10 Version 1703 oder höher wirksam, auf denen die Datei in den letzten 30 Tagen beobachtet wurde.</span><span class="sxs-lookup"><span data-stu-id="5d410-134">This action takes effect on devices with Windows 10, version 1703 or later, where the file was observed in the last 30 days.</span></span> 
- <span data-ttu-id="5d410-135">**Hinzufügen von Indikatoren zum Blockieren** oder Zulassen von Dateien – Verhindern Sie die weitere Verbreitung eines Angriffs in Ihrer Organisation, indem Sie potenziell schädliche Dateien oder mutmaßliche Schadsoftware verbieten.</span><span class="sxs-lookup"><span data-stu-id="5d410-135">**Add indicators to block or allow file** - Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="5d410-136">Dieser Vorgang verhindert, dass die Datei auf Geräten in Ihrer Organisation gelesen, geschrieben oder ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5d410-136">This operation will prevent the file from being read, written, or executed on devices in your organization.</span></span>
- <span data-ttu-id="5d410-137">**Datei herunterladen** oder sammeln – Mit dieser Aktion können Analysten eine Datei in einer kennwortgeschützten .zip Archivdatei für die weitere Analyse durch die Organisation herunterladen.</span><span class="sxs-lookup"><span data-stu-id="5d410-137">**Download or collect file** – This action allows analysts to download a file in a password protected .zip archive file for further analysis by the organization.</span></span>
- <span data-ttu-id="5d410-138">**Tiefe Analyse** – Mit dieser Aktion wird eine Datei in einer sicheren, vollständig instrumentierten Cloudumgebung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5d410-138">**Deep analysis** – This action executes a file in a secure, fully instrumented cloud environment.</span></span> <span data-ttu-id="5d410-139">Tiefe Analyseergebnisse zeigen die Aktivitäten der Datei, beobachtete Verhaltensweisen und zugehörige Artefakte, z. B. gelöschte Dateien, Registrierungsänderungen und die Kommunikation mit IP-Adressen.</span><span class="sxs-lookup"><span data-stu-id="5d410-139">Deep analysis results show the file's activities, observed behaviors, and associated artifacts, such as dropped files, registry modifications, and communication with IP addresses.</span></span> 

<span data-ttu-id="5d410-140">Wenn Sie das Beispiel in [Detect, triage, and analyze incidents](first-incident-analyze.md#analyze-your-first-incident)fortsetzen, kann ein Analytiker diesen Vorfall mit folgenden Aktionen beklagen:</span><span class="sxs-lookup"><span data-stu-id="5d410-140">Continuing the example in [Detect, triage, and analyze incidents](first-incident-analyze.md#analyze-your-first-incident), an analyst can remediate this incident with these actions:</span></span>

1. <span data-ttu-id="5d410-141">Sofortiges Zurücksetzen des Benutzerkontokennworts</span><span class="sxs-lookup"><span data-stu-id="5d410-141">Immediately reset the user account password</span></span>
2. <span data-ttu-id="5d410-142">Isolieren des Geräts in Microsoft 365 Defender, bis die umfassende Analyse abgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="5d410-142">Isolate the device in Microsoft 365 Defender until deep analysis is complete</span></span>
3. <span data-ttu-id="5d410-143">Stellen Sie sicher, dass die schädliche Datei in Quarantäne SharePoint</span><span class="sxs-lookup"><span data-stu-id="5d410-143">Ensure the malicious file was quarantined from SharePoint</span></span>
4. <span data-ttu-id="5d410-144">Überprüfen, welche Endpunkte von Schadsoftware betroffen waren</span><span class="sxs-lookup"><span data-stu-id="5d410-144">Check which endpoints were affected by malware</span></span>
5. <span data-ttu-id="5d410-145">Neuerstellen von Systemen</span><span class="sxs-lookup"><span data-stu-id="5d410-145">Rebuild systems</span></span>
6. <span data-ttu-id="5d410-146">Überprüfen auf ähnliche Microsoft Cloud App Security für andere Benutzer</span><span class="sxs-lookup"><span data-stu-id="5d410-146">Check for similar Microsoft Cloud App Security alerts for other users</span></span>
7. <span data-ttu-id="5d410-147">Erstellen eines benutzerdefinierten Indikators in Microsoft Defender for Endpoint zum Blockieren einer Tor-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="5d410-147">Create a custom indicator in Microsoft Defender for Endpoint to block a Tor IP address</span></span>
8. <span data-ttu-id="5d410-148">Erstellen Sie eine Steuerungsaktion in Microsoft Cloud App Security für diese Art von Warnung, z. B. die in der folgenden Abbildung dargestellten:</span><span class="sxs-lookup"><span data-stu-id="5d410-148">Create a governance action in Microsoft Cloud App Security for this type of alert such as those shown in the following image:</span></span>

   :::image type="content" source="../../media/first-incident-remediate/first-incident-mcas-governance.png" alt-text="Beispiel für Steuerungsaktionen im Microsoft Cloud App Security Portal"::: 
 
<span data-ttu-id="5d410-150">Die meisten Korrekturaktionen können in Defender angewendet und nachverfolgt Microsoft 365 werden.</span><span class="sxs-lookup"><span data-stu-id="5d410-150">Most of the remediation actions can be applied and tracked in Microsoft 365 Defender.</span></span> 

## <a name="using-playbooks"></a><span data-ttu-id="5d410-151">Verwenden von Playbooks</span><span class="sxs-lookup"><span data-stu-id="5d410-151">Using Playbooks</span></span>

<span data-ttu-id="5d410-152">Darüber hinaus kann eine automatisierte Korrektur mithilfe von Playbooks erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5d410-152">In addition, automated remediation can be created using playbooks.</span></span> <span data-ttu-id="5d410-153">Derzeit verfügt Microsoft [über Playbook-Vorlagen auf GitHub,](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks) die Playbooks für die folgenden Szenarien bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="5d410-153">Currently, Microsoft has [Playbook templates on GitHub](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks) that provide playbooks for the following scenarios:</span></span>

- <span data-ttu-id="5d410-154">Entfernen der freigabe vertraulichen Dateien nach dem Anfordern der Benutzerüberprüfung</span><span class="sxs-lookup"><span data-stu-id="5d410-154">Remove sensitive file sharing after requesting user validation</span></span>
- <span data-ttu-id="5d410-155">Automatisches Austriagen seltener Länderwarnungen</span><span class="sxs-lookup"><span data-stu-id="5d410-155">Auto-triage infrequent country alerts</span></span>
- <span data-ttu-id="5d410-156">Anfordern einer Manageraktion vor dem Deaktivieren eines Kontos</span><span class="sxs-lookup"><span data-stu-id="5d410-156">Request for manager action before disabling an account</span></span>
- <span data-ttu-id="5d410-157">Deaktivieren bösartiger Posteingangsregeln</span><span class="sxs-lookup"><span data-stu-id="5d410-157">Disable malicious inbox rules</span></span>

<span data-ttu-id="5d410-158">Playbooks verwenden Power Automate, um benutzerdefinierte Automatisierungsabläufe für Robotikprozesse zu erstellen, um bestimmte Aktivitäten zu automatisieren, sobald bestimmte Kriterien ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="5d410-158">Playbooks use Power Automate to create custom robotic process automation flows to automate certain activities once specific criteria have been triggered.</span></span> <span data-ttu-id="5d410-159">Organisationen können Playbooks entweder aus vorhandenen Vorlagen oder von Grund auf neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5d410-159">Organizations can create playbooks either from existing templates or from scratch.</span></span> 

<span data-ttu-id="5d410-160">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="5d410-160">Here's an example.</span></span>
 
:::image type="content" source="../../media/first-incident-remediate/first-incident-power-automate.png" alt-text="Beispiel für einen Power Automate benutzerdefinierten Automatisierungsfluss für Robotikprozesse"::: 
 
<span data-ttu-id="5d410-162">Playbooks können auch [](first-incident-post.md) während der Überprüfung nach dem Vorfall erstellt werden, um Korrekturaktionen aus Vorfällen für schnellere Korrekturaktionen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5d410-162">Playbooks can also be created during [post-incident review](first-incident-post.md) to create remediation actions from incidents for faster remediation actions.</span></span> 

## <a name="next-step"></a><span data-ttu-id="5d410-163">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="5d410-163">Next step</span></span>

<span data-ttu-id="5d410-164">[![Schritt 3: Erfahren Sie, wie Sie eine Überprüfung eines Vorfalls nach einem Vorfall durchführen](../../media/first-incident-overview/first-incident-path-step3.png)](first-incident-post.md)</span><span class="sxs-lookup"><span data-stu-id="5d410-164">[![Step 3: Learn how to perform a post-incident review of an incident](../../media/first-incident-overview/first-incident-path-step3.png)](first-incident-post.md)</span></span>

<span data-ttu-id="5d410-165">Erfahren Sie, [wie Sie eine Überprüfung eines Vorfalls nach einem Vorfall durchführen.](first-incident-post.md)</span><span class="sxs-lookup"><span data-stu-id="5d410-165">Learn how to [perform a post-incident review of an incident](first-incident-post.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5d410-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d410-166">See also</span></span>

- [<span data-ttu-id="5d410-167">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="5d410-167">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="5d410-168">Analysieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="5d410-168">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="5d410-169">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="5d410-169">Manage incidents</span></span>](manage-incidents.md)