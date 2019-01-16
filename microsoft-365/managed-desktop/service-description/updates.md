---
title: Handhabung von Updates in Microsoft Managed Desktop
description: Microsoft verwalteter Desktop auf dem neuesten Stand ist ein Gleichgewicht Geschwindigkeit und Stabilität.
keywords: Dokumentation Microsoft verwalteter Desktop, Microsoft-365-Dienst
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.openlocfilehash: bee6381b0f2b7b1e2d929329c3cf628ab7657678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867665"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Handhabung von Updates in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft verwalteter Desktop verbindet auf allen Geräten mit einer modernen Cloud-basierte Infrastruktur. Nachhaltiger Schutz von Windows, Office, Treibern, Firmware und Microsoft Store für Business Application Updates auf dem aktuellen Stand ist ein Gleichgewicht Geschwindigkeit und Stabilität. Um sicherzustellen, dass OS klingelt Bereitstellung verwendet werden und Richtlinien auf sichere Weise eingeführt. 

## <a name="update-groups"></a>Aktualisieren von Gruppen

Microsoft verwaltete Desktops werden vier Azure Active Directory-Gruppen zum Verwalten von Updates verwendet:

- Test: Nicht in der Produktion Geräte für die direkte Verwendung Änderungen vor dem Bereitstellen von Änderungen auf den Rest des Mandanten zu überprüfen. In diesem Ring Geräte sind außerhalb des Gültigkeitsbereichs für dokumentierte Endbenutzersupport. 
- Erste: Anfangsphase an Software und enthält und Geräte Vorabversionen werden.
- Fast: Priorisiert Geschwindigkeit über Stabilität. Nützlich für die Qualitätsprobleme erkennen, bevor sie die umfassende Gruppe angeboten werden. 
- Umfassende: Letzte Gruppe sein, um Features und QoE-Updates verfügen. Diese Gruppe enthält die Mehrzahl der Benutzer in den Mandanten und aus diesem Grund bevorzugt Stabilität gegenüber Geschwindigkeit bei der Bereitstellung.

Updates von Microsoft sind kumulativ und als Qualität oder Feature Updates kategorisiert werden können. Weitere Informationen finden Sie unter [Windows Update: häufig gestellte Fragen zu](https://support.microsoft.com/help/12373/windows-update-faq). 

Wie aktualisieren Ablauf der inhaltsbereitstellung:
- Microsoft verwalteten Desktops wird ein neues Feature oder Qualität Update gemäß den unten angegebenen Zeitplan bereitgestellt.
- Während der Bereitstellung verwalteter Microsoft-Desktop-Monitore auf Anzeichen für Fehler oder Unterbrechung (basierend auf Telemetrie Signale und Unterstützung der Endbenutzer vom System). Wenn alle erkannt werden, ist die Bereitstellung für alle aktuellen und zukünftigen Gruppen sofort angehalten.
    - Beispiel: Wenn ein Problem beim Bereitstellen eines Updates für die Qualität der ersten Gruppe ermittelt werden, werden klicken Sie dann Update-Bereitstellungen zur, umfassende und Fast alle angehalten, bis das Problem behoben wurde.
    - Kompatibilitätsprobleme können durch Ablegen ein Ticket in verwalteten Desktops IT Verwaltungsportal von Microsoft gemeldet werden.
- Feature und QoE-Updates werden unabhängig voneinander angehalten. Pause kann für 35 Tagen in der Standardeinstellung ist jedoch reduziert oder erweitert, je nachdem, ob das Problem behoben ist.
- Nachdem die Gruppen nicht angehalten werden, werden nach dem folgenden Zeitplan Bereitstellung fortgesetzt.
- Dieser Bereitstellungsprozess gilt für Features und Qualität Updates, obwohl die Zeitachse für die einzelnen variiert.

<table>
<tr><th colspan="5">Einstellungen für die Bereitstellung von Updates</th></tr>
<tr><th>Updatetyp</th><th>Testen</th><th>Erste</th><th>Schnelle</th><th>Umfassende</th></tr>
<tr><td>Qualität Updates für Betriebssystem</td><td>0 Tagen</td><td>0 Tagen</td><td>0 Tagen</td><td>3 Tage</td></tr>
<tr><td>Feature-Updates für Betriebssystem</td><td>0 Tagen</td><td>30 Tage</td><td>60 Tage</td><td>90 Tage</td></tr>
<tr><td>Treiber-firmware</td><td colspan="4">Folgt den Zeitplan für die Qualität updates</td></tr>
<tr><td>Antivirus-definition</td><td colspan="4">Mit jedem Scan aktualisiert</td></tr>
</table>

Diese Rückstellung Perioden dienen absichtlich hohe Sicherheit und Leistungsstandards für alle Benutzer zu gewährleisten. Darüber hinaus behält sich basierend auf Daten über alle Microsoft verwalteter Desktop-Geräte und die unterschiedlichem Umfang und die Auswirkungen von Updates gesammelt, Microsoft verwalteter Desktop Flexibilität, um die Länge der oben genannten Verzögerungen Perioden für einige oder alle Bereitstellungsgruppen auf eine Anzeige ändern hoc-Basis.

## <a name="windows-insider-program"></a>Windows-Insider-Programm

Microsoft verwalteter Desktop unterstützt keine Geräte, die Teil des Windows-Insider-Programms sind. Die Windows-Insider-Anwendung wird verwendet, um die Vorabversion der Software Windows überprüfen und ist für Geräte nicht geschäftskritischen vorgesehen. Dies ist zwar eine wichtige Microsoft-Initiative, ist es nicht für die Bereitstellung in produktionsumgebungen vorgesehen. 

Alle Geräte mit Windows-Insider Builds gefunden werden in der Testgruppe gebracht werden und nicht für Update Service Level Agreements (SLAs.

## <a name="bandwidth-management"></a>Bandbreitenverwaltung

Delivery-Optimierung wird für alle operating System und Treiber-Updates verwendet. Es wird die Download-Größe aus dem Dienst Windows Update (WU) von Updates von Kollegen innerhalb des Unternehmensnetzwerks Suchvorgänge minimiert.


