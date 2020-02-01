---
title: Geräteüberwachung und-Berichterstellung im Microsoft 365 Security Center
description: Beschreibt, wie Sie Ihre Geräte sicher, auf dem neuesten Stand halten und potenzielle Bedrohungen in Ihrer Organisation erkennen können.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitscenter, Überwachung, Bericht, Geräte
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: cecc84c1df3ccba3eea75d29aa5f293909d5d51f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600162"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="980dd-104">Geräteüberwachung und-Berichterstellung im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="980dd-104">Device monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="980dd-105">Halten Sie Ihre Geräte im Microsoft 365 Security Center sicher, auf dem neuesten Stand und stellen Sie potenzielle Bedrohungen vor Ort dar.</span><span class="sxs-lookup"><span data-stu-id="980dd-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="980dd-106">Anzeigen von Geräte Warnungen</span><span class="sxs-lookup"><span data-stu-id="980dd-106">View device alerts</span></span>

<span data-ttu-id="980dd-107">Erhalten Sie aktuelle Benachrichtigungen zu Sicherheitsverletzungen und anderen Bedrohungen auf Ihren Geräten von Microsoft Defender ATP (verfügbar mit einer E5-Lizenz).</span><span class="sxs-lookup"><span data-stu-id="980dd-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender ATP (available with an E5 license).</span></span> <span data-ttu-id="980dd-108">Das Microsoft 365 Security Center überwacht diese Warnungen effektiv mithilfe Ihres bevorzugten Workflows auf einer hohen Ebene.</span><span class="sxs-lookup"><span data-stu-id="980dd-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="980dd-109">Überwachen von Warnungen mit hoher Wirkung</span><span class="sxs-lookup"><span data-stu-id="980dd-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="980dd-110">Jede Microsoft Defender-ATP-Warnung weist einen entsprechenden Schweregrad (hoch, Mittel, niedrig oder ininformational) auf, der Ihre potenziellen Auswirkungen auf Ihr Netzwerk angibt, wenn Sie unbeaufsichtigt bleiben.</span><span class="sxs-lookup"><span data-stu-id="980dd-110">Each Microsoft Defender ATP alert has a corresponding severity (high, medium, low, or informational) that indicates its potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="980dd-111">Verwenden Sie die **Geräte Warnungs schwere** Karte, um sich speziell auf Warnungen zu konzentrieren, die gravierender sind und möglicherweise sofort reagieren müssen.</span><span class="sxs-lookup"><span data-stu-id="980dd-111">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="980dd-112">Auf dieser Karte können Sie weitere Informationen im Microsoft Defender-Sicherheits Center-Portal anzeigen.</span><span class="sxs-lookup"><span data-stu-id="980dd-112">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Geräte Warnungen-Schweregrad Karte](../images/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="980dd-114">Grundlegendes zu Warnungs Quellen</span><span class="sxs-lookup"><span data-stu-id="980dd-114">Understand sources of alerts</span></span>

<span data-ttu-id="980dd-115">Microsoft Defender ATP nutzt Daten aus einer breiten Palette von Sicherheitssensoren und Nachrichtenquellen, um Warnungen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="980dd-115">Microsoft Defender ATP leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="980dd-116">Beispielsweise kann es Erkennungsinformationen von Windows Defender Antivirus und Antischadsoftware von Drittanbietern sowie ihre eigenen benutzerdefinierten Bedrohungen, die über die Webdienst-API bereitgestellt werden, verwenden.</span><span class="sxs-lookup"><span data-stu-id="980dd-116">For example, it can use detection information from Windows Defender Antivirus and third-party antimalware, as well as your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="980dd-117">Die Karte für die **Erkennung von Geräte Warnungen** zeigt die Verteilung von Benachrichtigungen nach Quelle an.</span><span class="sxs-lookup"><span data-stu-id="980dd-117">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="980dd-118">Diese Karte kann Ihnen dabei helfen, Aktivitäten im Zusammenhang mit bestimmten Quellen, insbesondere ihren benutzerdefinierten Quellen, nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="980dd-118">This card can help you track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="980dd-119">Sie können dies auch verwenden, um sich auf Warnungen zu konzentrieren, die von Sensoren stammen, die nicht so konfiguriert sind, dass böswillige Aktivitäten oder Komponenten automatisch blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="980dd-119">You can also use this to focus on alerts coming from sensors that are not configured to automatically block malicious activity or components.</span></span>

![Geräte Warnungs Erkennungsquellen-Karte](../images/device-alert-detection-sources.png)

<span data-ttu-id="980dd-121">Auf dieser Karte können Sie weitere Informationen im Microsoft Defender-Sicherheits Center-Portal anzeigen.</span><span class="sxs-lookup"><span data-stu-id="980dd-121">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="980dd-122">Grundlegendes zu den Typen von Bedrohungen, die Warnungen auslösen</span><span class="sxs-lookup"><span data-stu-id="980dd-122">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="980dd-123">Microsoft Defender ATP sortiert jede Warnung in eine Kategorie, die eine bestimmte Stufe in der Angriffs Kette oder eine Art von Bedrohungs Komponente darstellt.</span><span class="sxs-lookup"><span data-stu-id="980dd-123">Microsoft Defender ATP sorts each alert into a category representing a certain stage in the attack chain or a type of threat component.</span></span> <span data-ttu-id="980dd-124">Beispielsweise kann eine erkannte Bedrohungsaktivität als "laterale Bewegung" kategorisiert werden, um anzugeben, dass versucht wurde, andere Geräte im Netzwerk zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="980dd-124">For example, a detected threat activity might be categorized as "lateral movement" to indicate that there was an attempt to reach other devices on the network.</span></span> <span data-ttu-id="980dd-125">Die Aktivität ist auch möglicherweise aufgetreten, nachdem Angreifer einen ersten Standbein erreicht haben.</span><span class="sxs-lookup"><span data-stu-id="980dd-125">The activity has also likely occurred after attackers gained an initial foothold.</span></span> <span data-ttu-id="980dd-126">Wenn eine Bedrohungs Komponente erkannt wird, kann Sie entweder weitgehend als Schadsoftware klassifiziert werden oder genauer gesagt als Ransomware, Anmeldeinformationen stehlen oder andere Arten von bösartiger oder unerwünschter Software.</span><span class="sxs-lookup"><span data-stu-id="980dd-126">When detected, a threat component might either be classified broadly as malware, or more specifically as ransomware, credential stealing, or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="980dd-127">Die Karte **Bedrohungskategorien für Geräte** zeigt die Verteilung von Warnungen in diesen Kategorien an.</span><span class="sxs-lookup"><span data-stu-id="980dd-127">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="980dd-128">Sie können diese Informationen verwenden, um Bedrohungsaktivitäten zu identifizieren, wie beispielsweise Diebstahlversuche von Anmeldeinformationen, die im Vergleich zu Social Engineering-versuchen eine höhere Auswirkung haben können.</span><span class="sxs-lookup"><span data-stu-id="980dd-128">You can use this information to identify threat activity, such as credential theft attempts, that can have higher impact compared to social engineering attempts.</span></span> <span data-ttu-id="980dd-129">Sie können diese Informationen auch verwenden, um potenziell destruktive Bedrohungen wie Ransomware zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="980dd-129">You can also use this information to monitor for potentially destructive threats like ransomware.</span></span>

![Geräte Bedrohungskategorien-Karte](../images/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="980dd-131">Überwachen aktiver Warnungen</span><span class="sxs-lookup"><span data-stu-id="980dd-131">Monitor active alerts</span></span>

<span data-ttu-id="980dd-132">Die **Geräte Warnungsstatus** Karte gibt die Anzahl der Warnungen an, die nicht aufgelöst wurden und möglicherweise beachtet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="980dd-132">The **Device alert status** card indicates the number of alerts that have not been resolved and might require attention.</span></span> <span data-ttu-id="980dd-133">Auf dieser Karte können Sie weitere Informationen im Microsoft Defender-Sicherheits Center-Portal anzeigen.</span><span class="sxs-lookup"><span data-stu-id="980dd-133">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Geräte Warnungsstatus Karte](../images/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="980dd-135">Überwachen der Klassifizierung der aufgelösten Warnungen</span><span class="sxs-lookup"><span data-stu-id="980dd-135">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="980dd-136">Beim Auflösen einer ATP-Warnung von Microsoft Defender können Ihre Sicherheitsmitarbeiter angeben, ob eine Warnung wie folgt überprüft wurde:</span><span class="sxs-lookup"><span data-stu-id="980dd-136">When resolving a Microsoft Defender ATP alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="980dd-137">Eine echte Warnung, die tatsächliche Verletzungs Aktivität oder Bedrohungs Komponenten identifiziert</span><span class="sxs-lookup"><span data-stu-id="980dd-137">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="980dd-138">Eine falsche Warnung, bei der die normale Aktivität falsch erkannt wurde</span><span class="sxs-lookup"><span data-stu-id="980dd-138">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="980dd-139">Die **Geräte Warnungs Klassifizierungs** Karte zeigt an, ob Ihre aufgelösten Warnungen als true oder false Alerts klassifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="980dd-139">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="980dd-140">Auf dieser Karte können Sie weitere Informationen im Microsoft Defender-Sicherheits Center-Portal anzeigen.</span><span class="sxs-lookup"><span data-stu-id="980dd-140">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="980dd-141">Hinweis: in einigen Fällen stehen Klassifizierungsinformationen für bestimmte Warnungen nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="980dd-141">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![Geräte Warnungs-Klassifikations Karte](../images/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="980dd-143">Überwachen der Ermittlung von aufgelösten Warnungen</span><span class="sxs-lookup"><span data-stu-id="980dd-143">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="980dd-144">Zusätzlich zur Klassifizierung, ob eine Warnung während der Lösung true oder false ist, kann Ihr Sicherheitspersonal eine Bestimmung bereitstellen, die den Typ der normalen oder böswilligen Aktivität angibt, die bei der Überprüfung der Warnung gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="980dd-144">In addition to classifying whether an alert is true or false during resolution, your security staff can provide a determination, indicating the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="980dd-145">Die Karte für die **Geräte Warnungs Ermittlung** zeigt die für jede Warnung vorgesehene Ermittlung an.</span><span class="sxs-lookup"><span data-stu-id="980dd-145">The **Device alert determination** card shows the determination provided for each alert.</span></span>

* <span data-ttu-id="980dd-146">**Apt**: Fortgeschrittene beständige Bedrohung, die darauf hinweist, dass die erkannte Aktivität oder Bedrohungs Komponente Teil einer anspruchsvollen Sicherheitslücke ist, die im betroffenen Netzwerk Fuß fassen soll</span><span class="sxs-lookup"><span data-stu-id="980dd-146">**APT**: advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="980dd-147">**Schadsoftware**: bösartige Datei oder Code</span><span class="sxs-lookup"><span data-stu-id="980dd-147">**Malware**: malicious file or code</span></span>
* <span data-ttu-id="980dd-148">**Sicherheitspersonal**: normale Aktivitäten, die von Sicherheitsmitarbeitern ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="980dd-148">**Security personnel**: normal activity performed by security staff</span></span>
* <span data-ttu-id="980dd-149">**Sicherheitstests**: Aktivitäten oder Komponenten, die zum Simulieren von tatsächlichen Bedrohungen entwickelt wurden und erwartet wurden, um Sicherheitssensoren auszulösen und Warnungen zu generieren</span><span class="sxs-lookup"><span data-stu-id="980dd-149">**Security testing**: activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="980dd-150">**Unerwünschte Software**: apps und andere Software, die nicht als bösartig eingestuft werden, andernfalls jedoch Richtlinien oder akzeptable Nutzungsstandards verletzen</span><span class="sxs-lookup"><span data-stu-id="980dd-150">**Unwanted software**: apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="980dd-151">**Sonstiges**: jede andere Bestimmung, die nicht unter die angegebenen Typen fällt</span><span class="sxs-lookup"><span data-stu-id="980dd-151">**Others**: any other determination that does not fall under the provided types</span></span>

<span data-ttu-id="980dd-152">Auf dieser Karte können Sie weitere Informationen im Microsoft Defender Security Center anzeigen.</span><span class="sxs-lookup"><span data-stu-id="980dd-152">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![Karte für die Geräte Warnungs Ermittlung](../images/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="980dd-154">Grundlegendes zu den gefährdeten Geräten</span><span class="sxs-lookup"><span data-stu-id="980dd-154">Understand which devices are at risk</span></span>

<span data-ttu-id="980dd-155">Der **Geräteschutz** zeigt die Risikostufe für Geräte an.</span><span class="sxs-lookup"><span data-stu-id="980dd-155">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="980dd-156">Die Risikostufe basiert auf Faktoren wie dem Typ und dem Schweregrad von Warnungen auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="980dd-156">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![Geräteschutz Karte](../images/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="980dd-158">Überwachen und melden des Status von InTune-verwalteten Geräten</span><span class="sxs-lookup"><span data-stu-id="980dd-158">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="980dd-159">Die folgenden Berichte enthalten Daten von Geräten, die in InTune registriert sind.</span><span class="sxs-lookup"><span data-stu-id="980dd-159">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="980dd-160">Daten von nicht registrierten Geräten sind nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="980dd-160">Data from unenrolled devices is not included.</span></span> <span data-ttu-id="980dd-161">Nur globale Administratoren können diese Karten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="980dd-161">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="980dd-162">Daten zu InTune-registrierten Geräten umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="980dd-162">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="980dd-163">Gerätekompatibilität</span><span class="sxs-lookup"><span data-stu-id="980dd-163">Device compliance</span></span>
* <span data-ttu-id="980dd-164">Geräte mit aktiver Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="980dd-164">Devices with active malware</span></span>
* <span data-ttu-id="980dd-165">Arten von Schadsoftware auf Geräten</span><span class="sxs-lookup"><span data-stu-id="980dd-165">Types of malware on devices</span></span>
* <span data-ttu-id="980dd-166">Schadsoftware auf Geräten</span><span class="sxs-lookup"><span data-stu-id="980dd-166">Malware on devices</span></span>
* <span data-ttu-id="980dd-167">Geräte mit Malware Erkennung</span><span class="sxs-lookup"><span data-stu-id="980dd-167">Devices with malware detections</span></span>
* <span data-ttu-id="980dd-168">Benutzer mit Malware Erkennung</span><span class="sxs-lookup"><span data-stu-id="980dd-168">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="980dd-169">Überwachen der Gerätekompatibilität</span><span class="sxs-lookup"><span data-stu-id="980dd-169">Monitor device compliance</span></span>

<span data-ttu-id="980dd-170">Die **Gerätekompatibilität** zeigt, wie viele Geräte, die in InTune registriert sind, den Konfigurationsrichtlinien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="980dd-170">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![Geräte Kompatibilitäts Karte](../images/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="980dd-172">Erkennen von Geräten mit Malwareerkennungen</span><span class="sxs-lookup"><span data-stu-id="980dd-172">Discover devices with malware detections</span></span>

<span data-ttu-id="980dd-173">**Erkennungen von Geräte-Schadsoftware** liefern die Anzahl von InTune-registrierten Geräten mit Schadsoftware, die nicht vollständig aufgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="980dd-173">**Device malware detections** provide the number of Intune enrolled devices with malware that have not been fully resolved.</span></span> <span data-ttu-id="980dd-174">Dies kann daran liegen, dass ausstehende Aktionen, ein Neustart, ein vollständiger Scan, manuelle Benutzeraktionen oder die Korrekturaktion nicht erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="980dd-174">This can be due to pending actions, a restart, a full scan, manual user actions, or if the remediation action did not complete successfully.</span></span>

![Karte für die Erkennung von Geräte-Schadsoftware](../images/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="980dd-176">Grundlegendes zu den erkannten Malwaretypen</span><span class="sxs-lookup"><span data-stu-id="980dd-176">Understand the types of malware detected</span></span>

<span data-ttu-id="980dd-177">**Typen von Schadsoftware auf Geräten** zeigen verschiedene Arten von Schadsoftware auf, die auf Geräten erkannt wurden, die in InTune registriert sind.</span><span class="sxs-lookup"><span data-stu-id="980dd-177">**Types of malware on devices** show different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="980dd-178">Sie können jeden Typ im Microsoft 365 Security Center untersuchen.</span><span class="sxs-lookup"><span data-stu-id="980dd-178">You can investigate each type in the Microsoft 365 security center.</span></span>

![Arten von Schadsoftware auf Geräte Karte](../images/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="980dd-180">Grundlegendes zur spezifischen auf Ihren Geräten erkannten Malware</span><span class="sxs-lookup"><span data-stu-id="980dd-180">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="980dd-181">**Malware auf Geräten** stellt eine Liste der auf Ihren Geräten erkannten spezifischen Malware zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="980dd-181">**Malware on devices** provide a list of the specific malware detected on your devices.</span></span>

![Malware auf Geräte Karte](../images/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="980dd-183">Verstehen, welche Geräte die meisten Schadsoftware aufweisen</span><span class="sxs-lookup"><span data-stu-id="980dd-183">Understand which devices have the most malware</span></span>

<span data-ttu-id="980dd-184">**Geräte mit Malwareerkennungen** zeigen, welche Geräte die meisten Malwareerkennungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="980dd-184">**Devices with malware detections** show which devices have the most malware detections.</span></span> <span data-ttu-id="980dd-185">im Microsoft 365 Security Center können Sie untersuchen, ob Schadsoftware aktiv ist, wer das Gerät verwendet und wie der Verwaltungsstatus in InTune.</span><span class="sxs-lookup"><span data-stu-id="980dd-185">in the Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![Geräte mit Schadsoftware-Erkennungskarte](../images/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="980dd-187">Verstehen, welche Benutzer Geräte mit den meisten Schadsoftware besitzen</span><span class="sxs-lookup"><span data-stu-id="980dd-187">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="980dd-188">**Benutzer mit Malwareerkennungen** zeigen Benutzern Geräte mit den meisten Malwareerkennungen.</span><span class="sxs-lookup"><span data-stu-id="980dd-188">**Users with malware detections** show users with devices that had the most malware detections.</span></span> <span data-ttu-id="980dd-189">Im Microsoft 365 Security Center können Sie sehen, wie viele Geräte jedem Benutzer zugewiesen sind, und weitere Informationen zu jedem Gerät und dem Typ der Schadsoftware.</span><span class="sxs-lookup"><span data-stu-id="980dd-189">In the Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![Benutzer mit der Malware Erkennungskarte](../images/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a><span data-ttu-id="980dd-191">Überwachen und Verwalten der Bereitstellung und Erkennung von ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="980dd-191">Monitor and manage ASR rule deployment and detections</span></span>

<span data-ttu-id="980dd-192">[Regeln für die Angriffsflächen Reduzierung (ASR)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) verhindern, dass Aktionen und apps, die in der Regel von Exploit sucht-Schadsoftware verwendet werden, Geräte infizieren.</span><span class="sxs-lookup"><span data-stu-id="980dd-192">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) help prevent actions and apps that are typically used by exploit-seeking malware to infect devices.</span></span> <span data-ttu-id="980dd-193">Mit diesen Regeln wird gesteuert, wann und wie ausführbare Dateien ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="980dd-193">These rules control when and how executables can run.</span></span> <span data-ttu-id="980dd-194">So können Sie beispielsweise verhindern, dass JavaScript oder VBScript eine heruntergeladene ausführbare Datei startet, Win32-API-Aufrufe aus Office-Makros blockiert oder Prozesse blockiert, die von USB-Laufwerken ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="980dd-194">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![Angriffsfläche reduziert Karte](../images/attack-surface-reduction-rules.png)

<span data-ttu-id="980dd-196">Die Karte **Regeln zur Verringerung der Angriffsfläche** bietet einen Überblick über die Bereitstellung von Regeln auf Ihren Geräten.</span><span class="sxs-lookup"><span data-stu-id="980dd-196">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="980dd-197">Die obere Leiste auf der Karte zeigt die Gesamtzahl der Geräte an, die sich in den folgenden Bereitstellungsmodi befinden:</span><span class="sxs-lookup"><span data-stu-id="980dd-197">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="980dd-198">**Blockmodus**: Geräte mit mindestens einer Regel, die zum Blockieren der erkannten Aktivität konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="980dd-198">**Block mode**: devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="980dd-199">**Überwachungsmodus**: Geräte, für die keine Regeln zum Blockieren der erkannten Aktivität festgelegt sind, aber mindestens eine Regel zum Überwachen der erkannten Aktivität festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="980dd-199">**Audit mode**: devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="980dd-200">**Off**: Geräte mit ausgeschalteten ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="980dd-200">**Off**: devices with all ASR rules turned off</span></span>

<span data-ttu-id="980dd-201">Der untere Teil dieser Karte zeigt die Einstellungen nach Regeln auf Ihren Geräten an.</span><span class="sxs-lookup"><span data-stu-id="980dd-201">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="980dd-202">In jeder Leiste wird die Anzahl der Geräte angegeben, die für die Blockierung oder Überwachung der Erkennung festgelegt sind, oder die Regel vollständig deaktivieren lassen.</span><span class="sxs-lookup"><span data-stu-id="980dd-202">Each bar indicates the number of devices that are set to block or audit detection or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="980dd-203">Anzeigen von ASR-Erkennungen</span><span class="sxs-lookup"><span data-stu-id="980dd-203">View ASR detections</span></span>

<span data-ttu-id="980dd-204">Wenn Sie detaillierte Informationen zu ASR-Regel Erkennungen in Ihrem Netzwerk anzeigen möchten, wählen Sie die Option **Erkennungen** auf der **Angriffsflächen Reduzierungs** Regelkarte anzeigen aus.</span><span class="sxs-lookup"><span data-stu-id="980dd-204">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="980dd-205">Die Registerkarte **Erkennungen** auf der Seite detaillierter Bericht wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="980dd-205">The **Detections** tab in the detailed report page will open.</span></span>

![Registerkarte "Erkennungen"](../images/detections-tab.png)

<span data-ttu-id="980dd-207">Im Diagramm oben auf der Seite werden Erkennungen im Laufe der Zeit angezeigt, die entweder blockiert oder überwacht wurden.</span><span class="sxs-lookup"><span data-stu-id="980dd-207">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="980dd-208">Die Tabelle am unteren Rand listet die aktuellsten Erkennungen auf.</span><span class="sxs-lookup"><span data-stu-id="980dd-208">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="980dd-209">Verwenden Sie die folgenden Informationen in der Tabelle, um die Art der Erkennungen zu verstehen:</span><span class="sxs-lookup"><span data-stu-id="980dd-209">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="980dd-210">**Erkannte Datei**: die Datei, in der Regel ein Skript oder ein Dokument, dessen Inhalt die mutmaßliche Angriffs Aktivität ausgelöst hat</span><span class="sxs-lookup"><span data-stu-id="980dd-210">**Detected file**: the file, typically a script or a document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="980dd-211">**Regel**: Name, der die Angriffsaktivitäten beschreibt, die von der Regel erfasst werden sollen.</span><span class="sxs-lookup"><span data-stu-id="980dd-211">**Rule**: name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="980dd-212">Lesen Sie mehr über vorhandene ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="980dd-212">Read about existing ASR rules</span></span>
* <span data-ttu-id="980dd-213">**Quell-App**: die Anwendung, die Inhalte geladen oder ausgeführt hat, die die mutmaßliche Angriffs Aktivität ausgelöst haben.</span><span class="sxs-lookup"><span data-stu-id="980dd-213">**Source app**: the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="980dd-214">Hierbei kann es sich um eine legitime Anwendung wie Webbrowser, eine Office-Anwendung oder ein System Tool wie PowerShell handeln.</span><span class="sxs-lookup"><span data-stu-id="980dd-214">This could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="980dd-215">**Herausgeber**: der Anbieter, der die Quell-APP freigegeben hat</span><span class="sxs-lookup"><span data-stu-id="980dd-215">**Publisher**: the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="980dd-216">Überprüfen der Einstellungen für die Geräte ASR-Regel</span><span class="sxs-lookup"><span data-stu-id="980dd-216">Review device ASR rule settings</span></span>

<span data-ttu-id="980dd-217">Navigieren Sie auf der Seite " **Regeln für Angriffsfläche verringern** " zur Registerkarte " **Konfiguration** ", um die Regeleinstellungen für einzelne Geräte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="980dd-217">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="980dd-218">Wählen Sie ein Gerät aus, um detaillierte Informationen dazu zu erhalten, ob sich jede Regel im Blockmodus, im Überwachungsmodus oder ganz deaktiviert befindet.</span><span class="sxs-lookup"><span data-stu-id="980dd-218">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![Registerkarte "Konfiguration"](../images/configuration-tab.png)

<span data-ttu-id="980dd-220">Microsoft InTune bietet Verwaltungsfunktionen für Ihre ASR-Regeln.</span><span class="sxs-lookup"><span data-stu-id="980dd-220">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="980dd-221">Wenn Sie Ihre Einstellungen aktualisieren möchten, wählen Sie unter **configure Devices** in the Tab **Erste Schritte** aus, um die Geräteverwaltung in InTune zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="980dd-221">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="980dd-222">Ausschließen von Dateien aus ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="980dd-222">Exclude files from ASR rules</span></span>

<span data-ttu-id="980dd-223">Microsoft 365 Security Center sammelt die Namen der [Dateien, die Sie möglicherweise](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) von Erkennungen nach Angriffs Oberflächen Reduzierungs Regeln ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="980dd-223">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="980dd-224">Durch das Ausschließen von Dateien können Sie falsch positive Erkennungen reduzieren und die Regeln für die Angriffs Oberflächenreduzierung im Blockmodus sicherer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="980dd-224">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="980dd-225">Die Ausschlüsse werden in Microsoft InTune verwaltet, das Microsoft 365 Security Center bietet jedoch ein Analyse Tool, mit dem Sie die Dateien besser verstehen.</span><span class="sxs-lookup"><span data-stu-id="980dd-225">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="980dd-226">Um mit dem Sammeln von Dateien für den Ausschluss zu beginnen, navigieren Sie auf der Registerkarte **Ausnahmen hinzufügen** auf der Seite **Angriffs Regel Bericht für Angriffsfläche** .</span><span class="sxs-lookup"><span data-stu-id="980dd-226">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="980dd-227">Das Tool analysiert Erkennungen nach allen Regeln für die Angriffs Oberflächenreduzierung, aber [nur einige Regeln unterstützen Ausschlüsse](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span><span class="sxs-lookup"><span data-stu-id="980dd-227">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span></span>

![Registerkarte "Ausschlüsse hinzufügen"](../images/add-exclusions-tab.png)

<span data-ttu-id="980dd-229">In der Tabelle sind alle Dateinamen aufgeführt, die von den Regeln für Angriffs Oberflächenreduzierung erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="980dd-229">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="980dd-230">Sie können Dateien auswählen, um die Auswirkungen zu überprüfen, die Sie ausschließen:</span><span class="sxs-lookup"><span data-stu-id="980dd-230">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="980dd-231">Anzahl weniger Erkennungen</span><span class="sxs-lookup"><span data-stu-id="980dd-231">How many fewer detections</span></span>
* <span data-ttu-id="980dd-232">Anzahl weniger Geräte melden die Erkennungen</span><span class="sxs-lookup"><span data-stu-id="980dd-232">How many fewer devices report the detections</span></span>

<span data-ttu-id="980dd-233">Wenn Sie eine Liste der ausgewählten Dateien mit vollständigen Pfaden für den Ausschluss erhalten möchten, wählen Sie **Ausschluss Pfade abrufen**aus.</span><span class="sxs-lookup"><span data-stu-id="980dd-233">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="980dd-234">Protokolle für den ASR-Regel **Block Anmeldeinformationen, die vom Windows Local Security Authority Subsystem (Lsass. exe) gestohlen** werden, erfassen die Quell-app " **LSASS. exe**", eine normale System Datei, als erkannte Datei.</span><span class="sxs-lookup"><span data-stu-id="980dd-234">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**, a normal system file, as the detected file.</span></span> <span data-ttu-id="980dd-235">Daher enthält die generierte Liste der Ausschluss Pfade diese Datei.</span><span class="sxs-lookup"><span data-stu-id="980dd-235">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="980dd-236">Um die Datei auszuschließen, die diese Regel anstelle von **LSASS. exe**ausgelöst hat, verwenden Sie den Pfad zur Quell-APP anstelle der erkannten Datei.</span><span class="sxs-lookup"><span data-stu-id="980dd-236">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="980dd-237">Um die Quell-APP zu finden, führen Sie die folgende [erweiterte Suchabfrage](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) für diese spezielle Regel aus (identifiziert durch die Regel-ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span><span class="sxs-lookup"><span data-stu-id="980dd-237">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="980dd-238">Dateien auf Ausschluss überprüfen</span><span class="sxs-lookup"><span data-stu-id="980dd-238">Check files for exclusion</span></span>

<span data-ttu-id="980dd-239">Bevor Sie eine Datei von ASR ausschließen, sollten Sie die Datei überprüfen, um zu ermitteln, ob es sich tatsächlich nicht um bösartige Dateien handelt.</span><span class="sxs-lookup"><span data-stu-id="980dd-239">Before excluding a file from ASR, we recommend that you inspect the file to determine if it is indeed not malicious.</span></span>

<span data-ttu-id="980dd-240">Verwenden Sie zum Überprüfen einer Datei die [Seite Dateiinformationen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) im Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="980dd-240">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="980dd-241">Die Seite enthält Informationen über die Prävalenz sowie das Erkennungs Verhältnis von VirusTotal Antivirus.</span><span class="sxs-lookup"><span data-stu-id="980dd-241">The page provides prevalence information as well as the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="980dd-242">Sie können auch die Seite verwenden, um die Datei zur tiefen Analyse zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="980dd-242">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="980dd-243">Um eine erkannte Datei im Sicherheits Center von Microsoft Defender zu finden, suchen Sie mithilfe der folgenden erweiterten Suchabfrage nach allen ASR-Erkennungen:</span><span class="sxs-lookup"><span data-stu-id="980dd-243">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="980dd-244">Verwenden Sie die **SHA1** oder **InitiatingProcessSHA1** in den Ergebnissen, um die Datei mithilfe der universellen Suchleiste im Microsoft Defender Security Center zu suchen.</span><span class="sxs-lookup"><span data-stu-id="980dd-244">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>
