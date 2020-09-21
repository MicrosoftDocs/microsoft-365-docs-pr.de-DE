---
title: Behandlung von Updates in Microsoft Managed Desktop
description: Das Aktualisieren von Microsoft Managed Desktop auf dem neuesten Stand ist ein Gleichgewichtzwischen Geschwindigkeit und Stabilität.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 03a9b19a5b8ba957419e23c2bb12748c9c57e80d
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104618"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Behandlung von Updates in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop verbindet alle Geräte mit einer modernen Cloud-basierten Infrastruktur. Windows, Office, Treiber, Firmware und Microsoft Store for Business-Anwendungen auf dem neuesten Stand zu halten ist ein Gleichgewichtzwischen Geschwindigkeit und Stabilität. Bereitstellungsgruppen werden verwendet, um sicherzustellen, dass Betriebssystemupdates und-Richtlinien auf sichere Weise ausgeführt werden. Weitere Informationen hierzu finden Sie unter Video [Microsoft Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP).

Von Microsoft veröffentlichte Updates sind kumulativ und werden als Qualitäts-oder Feature-Updates kategorisiert.
Weitere Informationen finden Sie unter [Windows Update für Unternehmen: Updatetypen](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types). 

## <a name="update-groups"></a>Gruppen aktualisieren

Microsoft Managed Desktop verwendet vier Azure Ad Gruppen zum Verwalten von Updates:

- **Test**: wird zum Validieren von Änderungen an Microsoft Managed Desktop-Richtlinien, Betriebssystemupdates, Feature-Updates und anderen an den Mandanten verschobenen Änderungen verwendet. Es dürfen keine Benutzer in der Testgruppe vorhanden sein. Die Testgruppe ist von allen etablierten Vereinbarungen zum Service Level und von der Benutzerunterstützung ausgenommen. Diese Gruppe kann verwendet werden, um die Kompatibilität von Anwendungen mit neuen Richtlinien oder Betriebssystemänderungen zu überprüfen.  
- **Erstens**: enthält frühe Software Benutzer und Geräte, die vorab Updates unterliegen könnten. Geräte in dieser Gruppe können Ausfälle auftreten, wenn es Szenarien gibt, die während der Tests im testring nicht berücksichtigt wurden.
- **Fast**: priorisiert die Geschwindigkeit über die Stabilität. Nützlich, um Qualitätsprobleme zu erkennen, bevor Sie für die breite Gruppe angeboten werden. Diese Gruppe dient als nächste Überprüfungsebene, ist jedoch im allgemeinen stabiler als der Test und die ersten Gruppen. 
- **Allgemein**: letzte Gruppe, für die Feature-und Qualitäts Updates verfügbar sind. Diese Gruppe enthält die Mehrzahl der Benutzer im Mandanten und begünstigt daher die Stabilität über die Geschwindigkeit bei der Bereitstellung. Das Testen von apps sollte hier vorgenommen werden, da die Umgebung am stabilsten ist. 

> [!NOTE]
> Wenn Sie einen Benutzer in eine andere Updategruppe migrieren müssen, senden Sie eine Supportanfrage. Weitere Informationen zum Senden von Supportanforderungen finden Sie unter [Support für Microsoft Managed Desktop](support.md) . Wenn Sie einen Benutzer selbst migrieren, wird der Wechsel wiederhergestellt.

Weitere Informationen zu Rollen und Verantwortlichkeiten bei diesen Bereitstellungsgruppen finden Sie unter [Microsoft Managed Desktop Roles and Responsibilities](../intro/roles-and-responsibilities.md) .

Funktionsweise der Updatebereitstellung:
- Microsoft Managed Desktop stellt ein neues Feature oder Qualitäts Update entsprechend dem unten angegebenen Zeitplan bereit.
- Während der Bereitstellung überwacht Microsoft Managed Desktop auf Anzeichen von Fehlern oder Unterbrechungen (basierend auf Diagnosedaten und dem Benutzer Unterstützungssystem). Wenn eine solche erkannt wird, wird die Bereitstellung für alle aktuellen und zukünftigen Gruppen sofort angehalten.
    - Beispiel: Wenn beim Bereitstelleneiner Qualitäts Aktualisierung für die erste Gruppe ein Problem erkannt wird, werden die Bereitstellungen auf First, fast und Broad angehalten, bis das Problem behoben ist.
    - Kompatibilitätsprobleme können gemeldet werden, indem Sie ein Ticket im Verwaltungsportal von Microsoft Managed Desktop hinterlegen.
- Feature-und Qualitäts Updates werden unabhängig voneinander angehalten. Pause ist in der Standardeinstellung für 35 Tage aktiv, kann jedoch je nachdem, ob das Problem behoben wurde, reduziert oder erweitert werden.
- Nachdem die Gruppen nicht angehalten wurden, wird die Bereitstellung entsprechend dem unten aufgeführten Zeitplan fortgesetzt.
- Dieser Bereitstellungsprozess gilt sowohl für Feature-als auch für Qualitäts Updates, obwohl die Zeitachse jeweils variiert.




<table>
    <tr><th colspan="5">Aktualisieren der Bereitstellungseinstellungen</th></tr>
    <tr><th>Update-Typ</th><th>Testen</th><th>Erster</th><th>Schnell</th><th>Allgemein</th></tr>
    <tr><td>Qualitäts Updates für das Betriebssystem</td><td>0 Tage</td><td>0 Tage</td><td>0 Tage</td><td>3 Tage</td></tr>
    <tr><td>Funktionsupdates für das Betriebssystem</td><td>0 Tage</td><td>30 Tage</td><td>60 Tage</td><td>90 Tage</td></tr>
    <tr><td>Treiber/Firmware</td><td colspan="4">Folgt dem Zeitplan für Qualitäts Updates</td></tr>
    <tr><td>Virenschutz Definition</td><td colspan="4">Mit jeder Überprüfung aktualisiert</td></tr>
    <tr><td>Microsoft 365 Apps for Enterprise</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">Weitere Informationen</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">Weitere Informationen</a></td></tr>
</table>

>[!NOTE]
>Diese Zeiträume wurden absichtlich so konzipiert, dass Sie für alle Benutzer hohe Sicherheits-und Leistungsstandards gewährleisten. Darüber hinaus behält sich Microsoft Managed Desktop aufgrund der Daten, die auf allen verwalteten Desktopgeräten von Microsoft gesammelt wurden, sowie unterschiedlichen Umfangs und Auswirkungen von Updates die Flexibilität zur Veränderung der Länge der oben genannten Zeiträume für alle Bereitstellungsgruppen auf Ad-hoc-Basis vor.
>
>Microsoft Managed Desktop führt eine unabhängige Bewertung der einzelnen Windows-Feature-Release durch, um die Notwendigkeit und den Nutzen für die verwalteten Mandanten auszuwerten. Folglich kann Microsoft Managed Desktop möglicherweise nicht alle Windows-Feature-Updates bereitstellen. 

## <a name="windows-insider-program"></a>Windows-Insider-Programm

Microsoft Managed Desktop unterstützt keine Geräte, die Teil des Windows Insider-Programms sind. Das Windows Insider-Programm wird verwendet, um die Vorabversion der Windows-Software zu validieren, und ist für Geräte vorgesehen, die nicht unternehmenskritisch sind. Dies ist zwar eine wichtige Microsoft-Initiative, aber Sie ist nicht für eine umfassende Bereitstellung in Produktionsumgebungen vorgesehen. 

Alle Geräte, die mit Windows Insider-Builds gefunden wurden, werden möglicherweise in die Test Gruppe aufgenommen und sind von den Update Service Level Agreements und der Benutzerunterstützung von Microsoft Managed Desktop ausgenommen.

## <a name="bandwidth-management"></a>Bandbreitenverwaltung

Wir verwenden die [Zustellungsoptimierung](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) für alle Betriebssystem-und Treiberupdates. Dadurch wird die Downloadgröße des Windows Update-Diensts minimiert, indem nach Updates von Kollegen innerhalb des Unternehmensnetzwerks gesucht wird.


