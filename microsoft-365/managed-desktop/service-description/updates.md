---
title: Behandlung von Updates in Microsoft Managed Desktop
description: Das Aktualisieren von Microsoft Managed Desktop auf dem neuesten Stand ist ein Gleichgewichtzwischen Geschwindigkeit und Stabilität.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: c2ab48c87f1239c21e6620ea00640bb3dabbdd45
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981636"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Behandlung von Updates in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop verbindet alle Geräte mit einer modernen Cloud-basierten Infrastruktur. Windows, Office, Treiber, Firmware und Microsoft Store for Business-Anwendungen auf dem neuesten Stand zu halten ist ein Gleichgewichtzwischen Geschwindigkeit und Stabilität. Bereitstellungsgruppen werden verwendet, um sicherzustellen, dass Betriebssystemupdates und-Richtlinien auf sichere Weise ausgeführt werden. 

Von Microsoft veröffentlichte Updates sind kumulativ und werden als Qualitäts-oder Feature-Updates kategorisiert.
Weitere Informationen finden Sie unter [Windows Update für Unternehmen: Updatetypen](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types). 

## <a name="update-groups"></a>Gruppen aktualisieren

Microsoft Managed Desktop verwendet vier Azure Ad Gruppen zum Verwalten von Updates:

- **Test**: wird zum Validieren von Änderungen an Microsoft Managed Desktop-Richtlinien, Betriebssystemupdates, Feature-Updates und anderen an den Mandanten verschobenen Änderungen verwendet. Es dürfen keine Endbenutzer in der Testgruppe vorhanden sein. Die Testgruppe ist von allen etablierten Vereinbarungen zum Service Level und Endbenutzer Unterstützung ausgenommen. Diese Gruppe kann verwendet werden, um die Kompatibilität von Anwendungen mit neuen Richtlinien oder Betriebssystem hängen zu überprüfen.  
- **Erstens**: enthält frühe Software Benutzer und Geräte, die vorab Updates unterliegen könnten. Geräte in dieser Gruppe können Ausfälle auftreten, wenn es Szenarien gibt, die während der Tests im testring nicht berücksichtigt wurden.
- **Fast**: priorisiert die Geschwindigkeit über die Stabilität. Nützlich, um Qualitätsprobleme zu erkennen, bevor Sie für die breite Gruppe angeboten werden. Diese Gruppe dient als nächste Überprüfungsebene, ist jedoch im allgemeinen stabiler als der Test und die ersten Gruppen. 
- **Allgemein**: letzte Gruppe, für die Feature-und Qualitäts Updates verfügbar sind. Diese Gruppe enthält die Mehrzahl der Benutzer im Mandanten und begünstigt daher die Stabilität über die Geschwindigkeit bei der Bereitstellung. Das Testen von apps sollte hier vorgenommen werden, da die Umgebung am stabilsten ist. 

> [!NOTE]
> Wenn Sie einen Benutzer in eine andere Updategruppe migrieren müssen, senden Sie eine Supportanfrage. Weitere Informationen zum Senden von Supportanforderungen finden Sie unter [Support für Microsoft Managed Desktop](support.md) . Wenn Sie einen Benutzer selbst migrieren, wird der Wechsel wiederhergestellt.

Weitere Informationen zu Rollen und Verantwortlichkeiten bei diesen Bereitstellungsgruppen finden Sie unter [Microsoft Managed Desktop Roles and Responsibilities](../intro/roles-and-responsibilities.md) .

Funktionsweise der Updatebereitstellung:
- Microsoft Managed Desktop stellt ein neues Feature oder Qualitäts Update entsprechend dem unten angegebenen Zeitplan bereit.
- Während der Bereitstellung überwacht Microsoft Managed Desktop auf Anzeichen von Fehlern oder Unterbrechungen (basierend auf Diagnosedaten und dem Endbenutzer-Support System). Wenn eine solche erkannt wird, wird die Bereitstellung für alle aktuellen und zukünftigen Gruppen sofort angehalten.
    - Beispiel: Wenn beim Bereitstelleneiner Qualitäts Aktualisierung für die erste Gruppe ein Problem erkannt wird, werden die Bereitstellungen auf First, fast und Broad angehalten, bis das Problem behoben ist.
    - Kompatibilitätsprobleme können gemeldet werden, indem Sie ein Ticket im Verwaltungsportal von Microsoft Managed Desktop hinterlegen.
- Feature-und Qualitäts Updates werden unabhängig voneinander angehalten. Pause ist in der Standardeinstellung für 35 Tage aktiv, kann jedoch je nachdem, ob das Problem behoben wurde, reduziert oder erweitert werden.
- Nachdem die Gruppen nicht angehalten wurden, wird die Bereitstellung entsprechend dem unten aufgeführten Zeitplan fortgesetzt.
- Dieser Bereitstellungsprozess gilt sowohl für Feature-als auch für Qualitäts Updates, obwohl die Zeitachse jeweils variiert.




<table>
<tr><th colspan="5">Aktualisieren der Bereitstellungseinstellungen</th></tr>
<tr><th>Update-Typ</th><th>Test</th><th>Erster</th><th>Schnell</th><th>Allgemein</th></tr>
<tr><td>Qualitäts Updates für das Betriebssystem</td><td>0 Tage</td><td>0 Tage</td><td>0 Tage</td><td>3 Tage</td></tr>
<tr><td>Funktionsupdates für das Betriebssystem</td><td>0 Tage</td><td>30 Tage</td><td>60 Tage</td><td>90 Tage</td></tr>
<tr><td>Treiber/Firmware</td><td colspan="4">Folgt dem Zeitplan für Qualitäts Updates</td></tr>
<tr><td>Virenschutz Definition</td><td colspan="4">Mit jeder Überprüfung aktualisiert</td></tr>
<tr><td>Office 365 ProPlus</td><td colspan="4">Folgt dem monatlichen Office-Kanal
</table>

Weitere Informationen zum monatlichen Kanal für Office 365 ProPlus finden Sie unter [Overview of Update Channels for Office 365 ProPlus](https://docs.microsoft.com/deployoffice/overview-of-update-channels-for-office-365-proplus).

>[!NOTE]
>Diese Zeiträume wurden absichtlich so konzipiert, dass Sie für alle Benutzer hohe Sicherheits-und Leistungsstandards gewährleisten. Darüber hinaus behält sich Microsoft Managed Desktop aufgrund von Daten, die auf allen verwalteten Desktopgeräten von Microsoft gesammelt wurden, sowie unterschiedlichen Umfangs und Auswirkungen von Updates die Flexibilität zur Änderung der Länge der oben genannten Zeiträume für alle Bereitstellungsgruppen in einem AD vor. hoc-Basis.
>
>Microsoft Managed Desktop führt eine unabhängige Bewertung der einzelnen Windows-Feature-Release durch, um die Notwendigkeit und den Nutzen für die verwalteten Mandanten auszuwerten. Folglich kann Microsoft Managed Desktop möglicherweise nicht alle Windows-Feature-Updates bereitstellen. 

## <a name="windows-insider-program"></a>Windows-Insider-Programm

Microsoft Managed Desktop unterstützt keine Geräte, die Teil des Windows Insider-Programms sind. Das Windows Insider-Programm wird verwendet, um die Vorabversion der Windows-Software zu validieren, und ist für Geräte vorgesehen, die nicht unternehmenskritisch sind. Dies ist zwar eine wichtige Microsoft-Initiative, aber Sie ist nicht für eine umfassende Bereitstellung in Produktionsumgebungen vorgesehen. 

Alle Geräte, die mit Windows Insider-Builds gefunden wurden, werden möglicherweise in die Test Gruppe aufgenommen und sind von der Aktualisierung von Service Level Agreements und der Unterstützung durch Endbenutzer von Microsoft Managed Desktop ausgenommen.

## <a name="bandwidth-management"></a>Bandbreitenverwaltung

Wir verwenden die [Zustellungsoptimierung](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) für alle Betriebssystem-und Treiberupdates. Dadurch wird die Downloadgröße des Windows Update-Diensts minimiert, indem nach Updates von Kollegen innerhalb des Unternehmensnetzwerks gesucht wird.


