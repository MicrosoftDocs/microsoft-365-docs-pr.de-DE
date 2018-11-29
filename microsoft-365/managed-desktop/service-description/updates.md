---
title: Handhabung von Updates in Microsoft Managed Desktop
description: Microsoft verwalteter Desktop auf dem neuesten Stand ist ein Gleichgewicht Geschwindigkeit und Stabilität.
keywords: Dokumentation Microsoft verwalteter Desktop, Microsoft-365-Dienst
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 513e03b7d703e0a9f78281ddac764d8a29ed5c8f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867665"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Handhabung von Updates in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft verwalteter Desktop verbindet auf allen Geräten mit einer modernen Cloud-basierte Infrastruktur. Nachhaltiger Schutz von Windows, Office, Treibern, Firmware und Microsoft Store für Business Application Updates auf dem aktuellen Stand ist ein Gleichgewicht Geschwindigkeit und Stabilität. Um sicherzustellen, dass OS klingelt Bereitstellung verwendet werden und Richtlinien auf sichere Weise eingeführt. 

## <a name="update-rings"></a>Aktualisieren von eingehenden Anrufen

Microsoft verwaltete Desktops werden vier Azure Active Directory-Gruppen zum Verwalten von Updates verwendet:

- Test: Der Test Ring dient nur zur Test und Überprüfung der Änderungen im Mandanten Kunden.  
- Erste: Zuerst soll eine frühe Test anrufen mit begrenzten Tech Benutzer sein, die zu einem frühen Zeitpunkt installieren von Software und einige Vorabversionen unterliegen bereit sind.
- Fast: Der fast Ring ist, in dem wir eine große Gruppe von Benutzern erwarten.  Das Ziel für diese Option ist, Geräte aktualisierte und mit quick müsse Software Zustellung sicher zu halten.  
- Umfassende: Das langsame Klingeln ist eine balanced konservativ Verteilung von Updates für die Qualität und Feature.  Qualität Updates sind weiterhin sehr übermittelt Tempo, aber nicht sofort. 

Die Updates im Ringsystem als Qualität kategorisiert werden, oder feature Updates:
- Qualität Updates umfassen sicherheitskritisch, und die Treiber-Updates.  Dies sind in der Regel monatlichen Updates. 
- Feature-Updates enthalten nicht nur Sicherheit und Qualität Überarbeitungen, aber auch beträchtliche Leistungsmerkmale und Änderungen an. Sie werden Semikolons jährlich freigegeben. 

Funktionsweise von Anrufen Promotion:
- Microsoft verwalteten Desktops wird ein neues Feature oder Qualität Update gemäß den unten angegebenen Zeitplan bereitgestellt.
- Während der Bereitstellung überwacht Microsoft verwalteter Desktop auf Anzeichen für Fehler oder andere Unterbrechung (über Telemetrie Signale und unsere Unterstützung der Endbenutzer vom System). Wenn alle erkannt werden, ist die Bereitstellung auf alle aktuellen und zukünftigen Klingeltöne sofort angehalten.
    - Beispiel: Wenn ein Problem beim Bereitstellen einer Qualität Update auf der ersten anrufen ermittelt werden, werden klicken Sie dann zunächst Fast und umfassende alle angehalten, bis das Problem behoben wurde.
    - Kompatibilitätsprobleme können durch Ablegen ein Ticket in verwalteten Desktops IT Verwaltungsportal von Microsoft gemeldet werden.
- Feature und QoE-Updates werden unabhängig voneinander angehalten.  Pause kann für 35 Tage standardmäßig gültig ist, aber reduziert oder erweitert, je nachdem, ob das Problem behoben ist.
- Nachdem das klingelt nicht angehalten werden, werden nach dem folgenden Zeitplan Bereitstellung fortgesetzt.
- Dieser Prozess Promotion gilt für Features und Qualität Updates, obwohl die Zeitachse für die einzelnen variiert.

<table>
<tr><th colspan="5">Ringe und Verzögerungen Einstellungen</th></tr>
<tr><th>Updatetyp</th><th>Test-ring</th><th>Erste</th><th>Schnelle</th><th>Umfassende</th></tr>
<tr><td>Qualität Updates für Betriebssystem</td><td>0 Tagen</td><td>0 Tagen</td><td>1 Tag</td><td>5 Tage</td></tr>
<tr><td>Feature-Updates für Betriebssystem</td><td>Bei jährlichen DDE-Kanal (Ziel) + 0 Tagen</td><td>Bei jährlichen DDE-Kanal (Ziel) + 30 Tage</td><td>Bei jährlichen DDE-Kanal (Ziel) + 60 Tage</td><td>Bei jährlichen Channel + 30 Tage</td></tr>
<tr><td>Treiber-firmware</td><td colspan="4">Folgt den Zeitplan für die Qualität updates</td></tr>
<tr><td>Antivirus-definition</td><td colspan="4">Mit jedem Scan aktualisiert</td></tr>
<tr><td>Office pro Plus klicken Sie auf Ausführen</td><td colspan="4">Bei jährlichen Channel ausgerichtet</td></tr>
</table>


## <a name="windows-insider-program"></a>Windows-Insider-Programm

Microsoft verwalteter Desktop unterstützt keine Geräte, die Teil des Windows-Insider-Programms sind. Dieses Programm wird verwendet, um die Vorabversion der Software Windows überprüfen und ist für Geräte nicht geschäftskritischen vorgesehen. Dies ist zwar eine wichtige Microsoft-Initiative, ist es nicht für die Bereitstellung in produktionsumgebungen vorgesehen. 

Alle Geräte mit Windows-Insider Builds gefunden werden auf dem Test-Ring versetzt werden und nicht für die Aktualisierung SLAs enthalten sein.

## <a name="bandwidth-management"></a>Bandbreitenverwaltung

Delivery-Optimierung wird für alle operating System und Treiber-Updates verwendet. Es wird die Download-Größe aus dem Dienst Windows Update (WU) von Updates von Kollegen innerhalb des Unternehmensnetzwerks Suchvorgänge minimiert.


