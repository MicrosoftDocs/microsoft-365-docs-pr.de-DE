---
title: So werden Updates in Microsoft Managed Desktop behandelt
description: Microsoft Managed Desktop auf dem neuesten Stand zu halten, ist ein Gleichgewicht aus Geschwindigkeit und Stabilität.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4d8de363cc9111fade719fdf5384519d1236f431
ms.sourcegitcommit: 05657b39eaafc0503b01c6adcc5d8a5e615dc02c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50031339"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>So werden Updates in Microsoft Managed Desktop behandelt


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop verbindet alle Geräte mit einer modernen cloudbasierten Infrastruktur. Windows- und Office-Anwendungen, Treiber, Firmware und Microsoft Store für Unternehmen auf dem neuesten Stand zu halten, ist ein Gleichgewicht aus Geschwindigkeit und Stabilität. Bereitstellungsgruppen werden verwendet, um sicherzustellen, dass Betriebssystemupdates und -richtlinien auf sichere Weise veröffentlicht werden. Weitere Informationen finden Sie im Video ["Microsoft Managed Desktop Change and Release Process".](https://www.microsoft.com/videoplayer/embed/RE4mWqP)

Von Microsoft veröffentlichte Updates sind kumulativ und werden als Qualitäts- oder Featureupdates kategorisiert.
Weitere Informationen finden Sie unter [Windows Update for Business: Updatetypen](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types). 

## <a name="update-groups"></a>Gruppen aktualisieren

Microsoft Managed Desktop verwendet vier Azure AD-Gruppen zum Verwalten von Updates:

- **Test:** Wird verwendet, um Änderungen an Microsoft Managed Desktop-Richtlinien, Betriebssystemupdates, Featureupdates und anderen Änderungen zu überprüfen, die an den Mandanten gesendet werden. In der Testgruppe sollten keine Benutzer platziert werden. Die Testgruppe ist von allen etablierten Vereinbarungen zum Servicelevel und vom Benutzersupport ausgenommen. Diese Gruppe kann verwendet werden, um die Kompatibilität von Anwendungen mit neuen Richtlinien- oder Betriebssystemänderungen zu überprüfen.  
- **First:** Enthält Early Software Adopters und Geräte, die Vorabupdates unterliegen können. Bei Geräten in dieser Gruppe können Ausfälle auftreten, wenn es Szenarien gibt, die während der Tests im Testring nicht behandelt wurden.
- **Schnell:** Priorisiert die Geschwindigkeit gegenüber der Stabilität. Hilfreich zum Erkennen von Qualitätsproblemen, bevor sie der Gruppe "Broad" angeboten werden. Diese Gruppe dient als nächste Überprüfungsebene, ist aber in der Regel stabiler als die Test- und die Erste Gruppe. 
- **Broad:** Last group to have feature and quality updates available. Diese Gruppe enthält die meisten Benutzer im Mandanten und bevorzugt daher Stabilität gegenüber der Geschwindigkeit bei der Bereitstellung. Das Testen von Apps sollte hier durchgeführt werden, da die Umgebung am stabilsten ist. 

### <a name="moving-devices-between-update-groups"></a>Verschieben von Geräten zwischen Updategruppen
Möglicherweise möchten Sie, dass einige Geräte updates zuletzt empfangen, andere, die Sie zuerst verwenden möchten. Um diese Geräte in die entsprechende Updategruppe zu verschieben, [übermitteln](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/admin-support?view=o365-worldwide) Sie eine Supportanfrage des Administrators, und wir verschieben die Geräte für Sie. 

> [!NOTE]
> Wenn Sie einen Benutzer in eine andere Updategruppe verschieben müssen, senden Sie eine Supportanfrage. Verschieben Sie Geräte nicht selbst zwischen Updategruppen. Wenn ein Gerät falsch verschoben wird, kann dies schwerwiegende Folgen haben. Das Gerät könnte unerwartet aktualisiert werden, und Richtlinien können konfliktesieren, indem die Gerätekonfiguration geändert wird.

Weitere Informationen zu Rollen und Zuständigkeiten innerhalb dieser Bereitstellungsgruppen finden Sie unter [Microsoft Managed Desktop Roles and responsibilities](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>Verwenden von Microsoft Managed Desktop-Updategruppen 
Es gibt Teile des Diensts, die Sie verwalten, z. B. die App-Bereitstellung, in denen es möglicherweise erforderlich ist, alle verwalteten Geräte als Ziel zu verwenden. In diesen Fällen ist es sinnvoll, Aktualisierungsgruppen zu verwenden, um diese Benutzer mit dem Verständnis zu erreichen, dass Sie die Mitgliedschaft dieser Gruppen nicht hinzufügen, entfernen oder ändern können. 

## <a name="how-update-deployment-works"></a>Funktionsweise der Updatebereitstellung:
1. Microsoft Managed Desktop stellt ein neues Feature- oder Qualitätsupdate gemäß dem in der folgenden Tabelle angegebenen Zeitplan zur Bereitstellung.
2. Während der Bereitstellung überwacht Microsoft Managed Desktop auf Fehler- oder Unterbrechungszeichen basierend auf Diagnosedaten und dem Benutzersupportsystem. Wenn Eins erkannt wird, wird die Bereitstellung sofort für alle aktuellen und zukünftigen Gruppen angehalten.
    - Beispiel: Wenn beim Bereitstellen eines Qualitätsupdates für die erste Gruppe ein Problem erkannt wird, werden alle Bereitstellungen auf "First", "Fast" und "Broad" angehalten, bis das Problem behoben ist.
    - Sie können Kompatibilitätsprobleme melden, indem Sie ein Ticket im Microsoft Managed Desktop Admin Portal einreichen.
    - Funktions- und Qualitätsupdates werden unabhängig voneinander angehalten. Die Pause ist standardmäßig für 35 Tage in Kraft, kann jedoch reduziert oder verlängert werden, je nachdem, ob das Problem behoben wurde.
3. Sobald die Gruppen angehalten wurden, wird die Bereitstellung gemäß dem Zeitplan in der Tabelle fortgesetzt.

Dieser Bereitstellungsprozess gilt sowohl für Funktionsupdates als auch für Qualitätsupdates, wobei die Zeitachse je nach Zeitachse variiert.




<table>
    <tr><th colspan="5">Aktualisieren von Bereitstellungseinstellungen</th></tr>
    <tr><th>Updatetyp</th><th>Testen</th><th>Erster</th><th>Schnell</th><th>Allgemein</th></tr>
    <tr><td>Qualitätsupdates für das Betriebssystem</td><td>0 Tage</td><td>0 Tage</td><td>0 Tage</td><td>3 Tage</td></tr>
    <tr><td>Funktionsupdates für das Betriebssystem</td><td>0 Tage</td><td>30 Tage</td><td>60 Tage</td><td>90 Tage</td></tr>
    <tr><td>Treiber/Firmware</td><td colspan="4">Folgt dem Zeitplan für Qualitätsupdates</td></tr>
    <tr><td>Virenschutzdefinition</td><td colspan="4">Mit jeder Überprüfung aktualisiert</td></tr>
    <tr><td>Microsoft 365 Apps for Enterprise</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">Weitere Informationen</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">Weitere Informationen</a></td></tr>
    <tr><td>Microsoft Teams</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/teams#updates">Weitere Informationen</a></td></tr>
</table>

>[!NOTE]
>Diese Zeiträume wurden absichtlich so konzipiert, dass hohe Sicherheits- und Leistungsstandards für alle Benutzer sichergestellt werden. Darüber hinaus behält sich Microsoft Managed Desktop basierend auf den auf allen Microsoft Managed Desktop-Geräten gesammelten Daten sowie dem variierenden Umfang und den Auswirkungen von Updates die Flexibilität vor, die Länge der oben genannten Rückstellungszeiträume für alle Bereitstellungsgruppen ad hoc zu ändern.
>
>Microsoft Managed Desktop führt eine unabhängige Bewertung der einzelnen Windows-Feature-Versionen durch, um deren Notwendigkeit und Nutzen für die verwalteten Mandanten zu bewerten. Daher stellt Microsoft Managed Desktop möglicherweise alle Windows-Featureupdates zur Verfügung. 

## <a name="windows-insider-program"></a>Windows-Insider-Programm

Microsoft Managed Desktop unterstützt keine Geräte, die Teil des Windows-Insider-Programms sind. Das Windows-Insider-Programm wird zur Überprüfung von Vorabversions-Windows-Software verwendet und ist für Geräte vorgesehen, die nicht unternehmenskritisch sind. Es ist zwar eine wichtige Microsoft-Initiative, aber nicht für die umfassende Bereitstellung in Produktionsumgebungen vorgesehen. 

Alle Geräte, die mit Windows-Insider-Builds gefunden werden, werden möglicherweise in die Testgruppe gestellt und sind von den Vereinbarungen zum Servicelevel und dem Benutzersupport von Microsoft Managed Desktop ausgenommen.

## <a name="bandwidth-management"></a>Bandbreitenverwaltung

Wir verwenden [die Übermittlungsoptimierung](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) für alle Betriebssystem- und Treiberupdates. Dadurch wird die Downloadgröße des Windows Update-Diensts minimiert, indem Updates von Gleichgesinnten im Unternehmensnetzwerk gesucht werden.

