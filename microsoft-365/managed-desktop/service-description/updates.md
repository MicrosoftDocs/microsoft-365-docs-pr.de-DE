---
title: Umgang mit Updates in Microsoft Managed Desktop
description: Microsoft Managed Desktop auf dem neuesten Stand zu halten, ist ein Gleichgewicht aus Geschwindigkeit und Stabilität.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6d93bf492f7cfea5a1ff863205085d853c4bbadb
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925431"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Umgang mit Updates in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop verbindet alle Geräte mit einer modernen cloudbasierten Infrastruktur. Die Aktualisierung von Windows, Office, Treibern, Firmware und Microsoft Store für Unternehmen Anwendungen ist ein Gleichgewicht aus Geschwindigkeit und Stabilität. Bereitstellungsgruppen werden verwendet, um sicherzustellen, dass Betriebssystemupdates und -richtlinien auf sichere Weise bereitgestellt werden. Weitere Informationen finden Sie im Video [Microsoft Managed Desktop Änderungs- und Veröffentlichungsprozess.](https://www.microsoft.com/videoplayer/embed/RE4mWqP)

Von Microsoft veröffentlichte Updates sind kumulativ und werden als Qualitäts- oder Funktionsupdates kategorisiert.
Weitere Informationen finden Sie unter [Windows Update for Business: Updatetypen.](/windows/deployment/update/waas-manage-updates-wufb#update-types) 

## <a name="update-groups"></a>Gruppen aktualisieren

Microsoft Managed Desktop verwendet vier Azure AD-Gruppen zum Verwalten von Updates:

- **Test:** Wird verwendet, um Microsoft Managed Desktop Richtlinienänderungen, Betriebssystemupdates, Funktionsupdates und andere Änderungen zu überprüfen, die an den Mandanten übertragen werden. Es sollten keine Benutzer in der Testgruppe platziert werden. Die Testgruppe ist von allen vereinbarungen zum Servicelevel und vom Benutzersupport ausgenommen. Diese Gruppe kann verwendet werden, um die Kompatibilität von Anwendungen mit neuen Richtlinien oder Betriebssystemänderungen zu überprüfen.  
- **Erstens:** Enthält early software adopters and devices that could be subject to pre-release updates. Für Geräte in dieser Gruppe können Ausfälle auftreten, wenn es Szenarien gibt, die während der Tests im Testring nicht behandelt wurden.
- **Schnell:** Priorisiert Geschwindigkeit gegenüber Stabilität. Nützlich zum Erkennen von Qualitätsproblemen, bevor sie der Gruppe "Allgemein" angeboten werden. Diese Gruppe dient als nächste Überprüfungsebene, ist aber in der Regel stabiler als die Gruppen "Test" und "First". 
- **Allgemein:** Letzte Gruppe, für die Funktions- und Qualitätsupdates verfügbar sind. Diese Gruppe enthält die meisten Benutzer im Mandanten und bevorzugt daher Stabilität gegenüber der Geschwindigkeit bei der Bereitstellung. Das Testen von Apps sollte hier erfolgen, da die Umgebung am stabilsten ist. 

### <a name="moving-devices-between-update-groups"></a>Verschieben von Geräten zwischen Updategruppen
Möglicherweise möchten Sie, dass einige Geräte zuletzt Updates erhalten, und andere Geräte, die Sie zuerst verwenden möchten. Um diese Geräte in die entsprechende Updategruppe zu verschieben, [senden Sie eine Administrator-Supportanfrage,](../working-with-managed-desktop/admin-support.md) und wir verschieben die Geräte für Sie. 

> [!NOTE]
> Wenn Sie einen Benutzer in eine andere Updategruppe verschieben müssen, senden Sie eine Supportanfrage. Verschieben Sie Geräte nicht selbst zwischen Updategruppen. Es gibt schwerwiegende Folgen, wenn ein Gerät falsch verschoben wird. Das Gerät könnte unerwartet aktualisiert werden, und Richtlinien können in Konflikt geraten und die Gerätekonfiguration ändern.

Weitere Informationen zu Rollen und Zuständigkeiten innerhalb dieser Bereitstellungsgruppen finden Sie unter [Microsoft Managed Desktop Rollen und Zuständigkeiten](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>Verwenden von Microsoft Managed Desktop Aktualisieren von Gruppen 
Es gibt Teile des Diensts, die Sie verwalten, z. B. die App-Bereitstellung, in denen es erforderlich sein kann, alle verwalteten Geräte als Ziel zu verwenden. In diesen Fällen ist es sinnvoll, Aktualisierungsgruppen zu verwenden, um diese Benutzer mit dem Verständnis zu erreichen, dass Sie die Mitgliedschaft dieser Gruppen nicht hinzufügen, entfernen oder ändern können. 

## <a name="how-update-deployment-works"></a>Funktionsweise der Updatebereitstellung:
1. Microsoft Managed Desktop stellt ein neues Feature oder Qualitätsupdate gemäß dem in der folgenden Tabelle angegebenen Zeitplan bereit.
2. Während der Bereitstellung überwacht Microsoft Managed Desktop auf Fehler- oder Unterbrechungszeichen basierend auf Diagnosedaten und dem Benutzersupportsystem. Wenn solche erkannt werden, wird die Bereitstellung für alle aktuellen und zukünftigen Gruppen sofort angehalten.
    - Beispiel: Wenn beim Bereitstellen eines Qualitätsupdates für die erste Gruppe ein Problem erkannt wird, werden alle Bereitstellungen auf "First", "Fast" und "Broad" aktualisiert, bis das Problem behoben ist.
    - Sie können Kompatibilitätsprobleme melden, indem Sie ein Ticket im Microsoft Managed Desktop Admin-Portal einreichen.
    - Funktions- und Qualitätsupdates werden unabhängig voneinander angehalten. Die Unterbrechung ist standardmäßig 35 Tage gültig, kann jedoch je nachdem, ob das Problem behoben wird, reduziert oder verlängert werden.
3. Sobald die Gruppen angehalten wurden, wird die Bereitstellung gemäß dem Zeitplan in der Tabelle fortgesetzt.

Dieser Bereitstellungsprozess gilt sowohl für Funktions- als auch für Qualitätsupdates, die Zeitachse variiert jedoch für jeden.




<table>
    <tr><th colspan="5">Aktualisieren der Bereitstellungseinstellungen</th></tr>
    <tr><th>Updatetyp</th><th>Testen</th><th>Erster</th><th>Schnell</th><th>Allgemein</th></tr>
    <tr><td>Qualitätsupdates für das Betriebssystem</td><td>0 Tage</td><td>0 Tage</td><td>0 Tage</td><td>3 Tage</td></tr>
    <tr><td>Featureupdates für das Betriebssystem</td><td>0 Tage</td><td>30 Tage</td><td>60 Tage</td><td>90 Tage</td></tr>
    <tr><td>Treiber/Firmware</td><td colspan="4">Folgt dem Zeitplan für Qualitätsupdates</td></tr>
    <tr><td>Antivirendefinition</td><td colspan="4">Bei jeder Überprüfung aktualisiert</td></tr>
    <tr><td>Microsoft 365 Apps for Enterprise</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">Weitere Informationen</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">Weitere Informationen</a></td></tr>
    <tr><td>Microsoft Teams</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/teams#updates">Weitere Informationen</a></td></tr>
</table>

>[!NOTE]
>Diese Zurückstellungszeiträume sind absichtlich darauf ausgelegt, hohe Sicherheits- und Leistungsstandards für alle Benutzer sicherzustellen. Darüber hinaus behält sich Microsoft Managed Desktop basierend auf Denkdaten, die auf allen Microsoft Managed Desktop Geräten gesammelt wurden, sowie dem variierenden Umfang und den Auswirkungen von Updates Flexibilität bei, um die Länge der oben genannten Zurückstellungszeiträume für alle Bereitstellungsgruppen ad hoc zu ändern.
>
>Microsoft Managed Desktop führt eine unabhängige Bewertung jeder Windows Featureversion durch, um deren Notwendigkeit und Nützlichkeit für die verwalteten Mandanten zu bewerten. Daher stellen Microsoft Managed Desktop möglicherweise alle Windows Featureupdates bereit. 

## <a name="windows-insider-program"></a>Windows-Insider-Programm

Microsoft Managed Desktop unterstützt keine Geräte, die Teil des Windows-Insider-Programms sind. Das Windows-Insider-Programm wird verwendet, um Vorabversionen Windows Software zu überprüfen, und ist für Geräte vorgesehen, die nicht unternehmenskritisch sind. Obwohl es sich um eine wichtige Microsoft-Initiative handelt, ist sie nicht für die allgemeine Bereitstellung in Produktionsumgebungen vorgesehen. 

Alle Geräte, die mit Windows Insider-Builds gefunden wurden, werden möglicherweise in die Testgruppe aufgenommen und von Vereinbarungen zum Servicelevel und vom Benutzersupport von Microsoft Managed Desktop ausgenommen.

## <a name="bandwidth-management"></a>Bandbreitenverwaltung

Wir verwenden [die Übermittlungsoptimierung](/windows/deployment/update/waas-delivery-optimization) für alle Betriebssystem- und Treiberupdates. Dadurch wird die Downloadgröße des Windows Updatediensts minimiert, indem Updates von Peers innerhalb des Unternehmensnetzwerks gesucht werden.