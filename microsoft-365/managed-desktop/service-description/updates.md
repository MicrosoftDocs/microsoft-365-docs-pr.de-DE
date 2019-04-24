---
title: Behandlung von Updates in Microsoft Managed Desktop
description: Microsoft Managed Desktop auf dem neuesten Stand zu halten, ist ein Gleichgewichtzwischen Geschwindigkeit und Stabilität.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0dad909ce9e17f993de64ba39b08f388c71abb89
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278644"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Behandlung von Updates in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop verbindet alle Geräte mit einer modernen Cloud-basierten Infrastruktur. Die Aktualität von Windows, Office, Treibern, Firmware und Microsoft Store for Business-Anwendungen ist ein Gleichgewichtzwischen Geschwindigkeit und Stabilität. Bereitstellungsgruppen werden verwendet, um sicherzustellen, dass Betriebssystem und Richtlinien auf sichere Weise eingeführt werden. 

Von Microsoft veröffentlichte Updates sind kumulativ und können als Qualitäts-oder Feature-Updates kategorisiert werden.
Weitere Informationen finden Sie unter [Windows Update for Business: Update Types](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types). 

## <a name="update-groups"></a>Gruppen aktualisieren

Microsoft Managed Desktop verwendet vier Azure AD-Gruppen zum Verwalten von Updates:

- **Test**: wird verwendet, um Änderungen an Microsoft Managed Desktop-Richtlinien, Betriebssystemupdates, Funktions Aktualisierungen und andere Änderungen an den Mandanten zu überprüfen. In der Testgruppe dürfen sich keine Endbenutzer befinden. Die Testgruppe ist von allen gängigen SLAs und Endbenutzer Unterstützung ausgenommen. Diese Gruppe kann verwendet werden, um die Kompatibilität von Anwendungen mit neuen Richtlinien-oder Betriebssystemänderungen zu überprüfen.  
- **Erstens**: enthält frühe Software Adopters und Geräte, die möglicherweise vorab Updates unterliegen. Geräte in dieser Gruppe können Ausfällen auftreten, wenn es Szenarien gibt, die während der Tests im testring nicht behandelt wurden.
- **Fast**: priorisiert die Geschwindigkeit der Stabilität. Hilfreich, um Qualitätsprobleme zu erfassen, bevor Sie für die allgemeine Gruppe angeboten werden. Diese Gruppe dient als nächste Überprüfungsebene, ist aber im allgemeinen stabiler als die Test-und First-Gruppen. 
- **Allgemein**: in der letzten Gruppe stehen Feature-und Qualitäts Updates zur Verfügung. Diese Gruppe enthält die Mehrzahl der Benutzer im Mandanten und begünstigt daher die Stabilität bei der Bereitstellung. Das Testen von apps sollte hier ausgeführt werden, da die Umgebung am stabilsten ist. 

Weitere Informationen zu Rollen und Verantwortlichkeiten bei diesen Bereitstellungsgruppen finden Sie unter [Microsoft Managed Desktop Roles and Responsibilities](../intro/roles-and-responsibilities.md)

FunktionsWeise der Updatebereitstellung:
- Microsoft Managed Desktop stellt ein neues Feature oder Qualitäts Update gemäß dem unten angegebenen Zeitplan bereit.
- Während der Bereitstellung überwacht Microsoft Managed Desktop nach Anzeichen des Fehlers oder der Unterbrechung (basierend auf Diagnosedaten und Endbenutzer-Support System). Wenn alle erkannt werden, wird die Bereitstellung für alle aktuellen und zukünftigen Gruppen sofort angehalten.
    - Beispiel: Wenn bei der Bereitstellungeines Qualitäts Updates für die erste Gruppe ein Problem erkannt wird, werden die Bereitstellungen zunächst auf "zuerst", "schnell" und "Allgemein" angehalten, bis das Problem behoben ist.
    - Kompatibilitätsprobleme können gemeldet werden, indem Sie ein Ticket im Microsoft Managed Desktop IT Admin-Portal einreichen.
- Feature-und Quality-Updates werden unabhängig voneinander angehalten. Die Pause ist in der Standardeinstellung für 35 Tage aktiviert, kann jedoch reduziert oder erweitert werden, je nachdem, ob das Problem behoben wurde.
- Sobald die Gruppen UN-angehalten sind, wird die Bereitstellung gemäß dem unten aufgeführten Zeitplan fortgesetzt.
- Dieser Bereitstellungsprozess gilt sowohl für Feature-als auch für Qualitäts Updates, obwohl die Zeitachse für jeden unterschiedlich ist.

<table>
<tr><th colspan="5">Bereitstellungseinstellungen aktualisieren</th></tr>
<tr><th>Aktualisierungstyp</th><th>Testen</th><th>Erster</th><th>Schnell</th><th>Allgemein</th></tr>
<tr><td>Qualitäts Updates für das Betriebssystem</td><td>0 Tage</td><td>0 Tage</td><td>0 Tage</td><td>3 Tage</td></tr>
<tr><td>Funktions Aktualisierungen für das Betriebssystem</td><td>0 Tage</td><td>30 Tage</td><td>60 Tage</td><td>90 Tage</td></tr>
<tr><td>Treiber/Firmware</td><td colspan="4">Folgt dem Zeitplan für Qualitäts Updates</td></tr>
<tr><td>Antiviren-Definition</td><td colspan="4">Bei jeder Überprüfung aktualisiert</td></tr>
</table>

Diese Verzögerungszeiträume sind absichtlich darauf ausgelegt, hohe Sicherheits-und Leistungsstandards für alle Benutzer sicherzustellen. Darüber hinaus behält sich Microsoft Managed Desktop aufgrund der Daten, die auf allen Microsoft-Desktopgeräten und dem unterschiedlichen Umfang und der Auswirkung von Updates erfasst werden, die Flexibilität, die Länge der obigen Zeiträume für alle Bereitstellungsgruppen in einer AD zu ändern. hoc-Basis.

## <a name="windows-insider-program"></a>Windows Insider-Programm

Microsoft Managed Desktop unterstützt keine Geräte, die Teil des Windows Insider-Programms sind. Das Windows Insider-Programm dient zur Überprüfung der Vorabversionen von Windows-Software und ist für nicht-missionskritische Geräte vorgesehen. Obwohl dies eine wichtige Microsoft-Initiative ist, ist Sie nicht für eine allgemeine Bereitstellung in Produktionsumgebungen vorgesehen. 

Alle Geräte, die mit Windows-Insider-Builds gefunden werden, werden in die Test Gruppe aufgenommen und nicht für SLAs (Service Level Agreements) aktualisiert.

## <a name="bandwidth-management"></a>Bandbreitenverwaltung

Die Bereitstellungsoptimierung wird für alle Betriebssystem-und Treiberupdates verwendet. Es minimiert die Downloadgröße vom Windows Update (WU)-Dienst, indem Aktualisierungen von Peers innerhalb des Unternehmensnetzwerks gesucht werden.


