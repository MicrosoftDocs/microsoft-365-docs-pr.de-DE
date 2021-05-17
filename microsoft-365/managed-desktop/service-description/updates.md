---
title: Umgang mit Updates in Microsoft Managed Desktop
description: Microsoft Managed Desktop auf dem neuesten Stand zu halten, ist eine Balance aus Geschwindigkeit und Stabilität.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5961ac4eb16928754849f5f32ecd06d4d2e4650d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917716"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Umgang mit Updates in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop verbindet alle Geräte mit einer modernen cloudbasierten Infrastruktur. Windows- und Office-Anwendungen, Treiber, Firmware und Microsoft Store für Unternehmen auf dem neuesten Stand zu halten, ist eine Balance aus Geschwindigkeit und Stabilität. Bereitstellungsgruppen werden verwendet, um sicherzustellen, dass Betriebssystemupdates und -richtlinien auf sichere Weise ausgeführt werden. Weitere Informationen finden Sie im Video [Microsoft Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP).

Von Microsoft veröffentlichte Updates sind kumulativ und werden als Qualitäts- oder Featureupdates kategorisiert.
Weitere Informationen finden Sie unter [Windows Update for Business: Update types](/windows/deployment/update/waas-manage-updates-wufb#update-types). 

## <a name="update-groups"></a>Gruppen aktualisieren

Microsoft Managed Desktop verwendet vier Azure AD-Gruppen zum Verwalten von Updates:

- **Test**: Wird verwendet, um Änderungen an Microsoft Managed Desktop-Richtlinien, Betriebssystemupdates, Featureupdates und andere Änderungen zu überprüfen, die an den Mandanten gesendet werden. In der Testgruppe sollten keine Benutzer platziert werden. Die Testgruppe ist von allen etablierten Vereinbarungen zum Servicelevel und vom Benutzersupport ausgenommen. Diese Gruppe kann verwendet werden, um die Kompatibilität von Anwendungen mit neuen Richtlinien- oder Betriebssystemänderungen zu überprüfen.  
- **First**: Enthält frühe Software-Adopter und Geräte, die Vorabupdates unterliegen könnten. Bei Geräten in dieser Gruppe kann es zu Ausfällen kommen, wenn szenarien auftreten, die während der Tests im Testring nicht behandelt wurden.
- **Schnell**: Priorisiert die Geschwindigkeit gegenüber der Stabilität. Nützlich zum Erkennen von Qualitätsproblemen, bevor sie der Gruppe "Broad" angeboten werden. Diese Gruppe dient als nächste Überprüfungsebene, ist aber in der Regel stabiler als die Gruppen Test und First. 
- **Broad**: Last group to have feature and quality updates available. Diese Gruppe enthält die meisten Benutzer im Mandanten und bevorzugt daher Stabilität gegenüber der Geschwindigkeit bei der Bereitstellung. Tests von Apps sollten hier durchgeführt werden, da die Umgebung am stabilsten ist. 

### <a name="moving-devices-between-update-groups"></a>Verschieben von Geräten zwischen Updategruppen
Möglicherweise möchten Sie, dass einige Geräte zuletzt Updates erhalten, andere, die Sie zuerst verwenden möchten. Um diese Geräte in die entsprechende Updategruppe zu verschieben, [senden](../working-with-managed-desktop/admin-support.md?view=o365-worldwide) Sie eine Administratorunterstützungsanfrage, und wir verschieben die Geräte für Sie. 

> [!NOTE]
> Wenn Sie einen Benutzer in eine andere Updategruppe verschieben müssen, senden Sie eine Supportanfrage. Verschieben Sie Geräte nicht selbst zwischen Updategruppen. Es gibt schwerwiegende Folgen, wenn ein Gerät falsch verschoben wird. Das Gerät könnte unerwartet aktualisiert werden, und Richtlinien können konflikte und die Gerätekonfiguration ändern.

Weitere Informationen zu Rollen und Verantwortlichkeiten innerhalb dieser Bereitstellungsgruppen finden Sie unter [Microsoft Managed Desktop Roles and responsibilities](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>Verwenden von Microsoft Managed Desktop-Updategruppen 
Es gibt Teile des Diensts, die Sie verwalten, z. B. die App-Bereitstellung, in denen es möglicherweise erforderlich ist, auf alle verwalteten Geräte zu zielen. In diesen Fällen ist es sinnvoll, Updategruppen zu verwenden, um diese Benutzer mit dem Verständnis zu erreichen, dass Sie die Mitgliedschaft dieser Gruppen nicht hinzufügen, entfernen oder ändern können. 

## <a name="how-update-deployment-works"></a>Funktionsweise der Updatebereitstellung:
1. Microsoft Managed Desktop stellt ein neues Feature oder Qualitätsupdate gemäß dem in der folgenden Tabelle angegebenen Zeitplan zur Bereitstellung.
2. Während der Bereitstellung überwacht Microsoft Managed Desktop auf Anzeichen von Fehlern oder Unterbrechungen basierend auf Diagnosedaten und dem Benutzerunterstützungssystem. Wenn eine dieser Gruppen erkannt wird, wird die Bereitstellung sofort für alle aktuellen und zukünftigen Gruppen angehalten.
    - Beispiel: Wenn beim Bereitstellen eines Qualitätsupdates für die Erste Gruppe ein Problem erkannt wird, werden Die Bereitstellungen auf First, Fast und Broad aktualisiert, bis das Problem behoben ist.
    - Sie können Kompatibilitätsprobleme melden, indem Sie ein Ticket im Microsoft Managed Desktop Admin-Portal ablegen.
    - Feature- und Qualitätsupdates werden unabhängig voneinander angehalten. Pause ist standardmäßig für 35 Tage wirksam, kann jedoch reduziert oder verlängert werden, je nachdem, ob das Problem behoben wurde.
3. Sobald die Gruppen angehalten wurden, wird die Bereitstellung gemäß dem Zeitplan in der Tabelle fortgesetzt.

Dieser Bereitstellungsprozess gilt sowohl für Feature- als auch für Qualitätsupdates, wobei die Zeitachse je nach Zeitachse variiert.




<table>
    <tr><th colspan="5">Aktualisieren der Bereitstellungseinstellungen</th></tr>
    <tr><th>Updatetyp</th><th>Testen</th><th>Erster</th><th>Schnell</th><th>Allgemein</th></tr>
    <tr><td>Qualitätsupdates für das Betriebssystem</td><td>0 Tage</td><td>0 Tage</td><td>0 Tage</td><td>3 Tage</td></tr>
    <tr><td>Featureupdates für das Betriebssystem</td><td>0 Tage</td><td>30 Tage</td><td>60 Tage</td><td>90 Tage</td></tr>
    <tr><td>Treiber/Firmware</td><td colspan="4">Folgt dem Zeitplan für Qualitätsupdates</td></tr>
    <tr><td>Virenschutzdefinition</td><td colspan="4">Mit jedem Scan aktualisiert</td></tr>
    <tr><td>Microsoft 365 Apps for Enterprise</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">Weitere Informationen</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">Weitere Informationen</a></td></tr>
    <tr><td>Microsoft Teams</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/teams#updates">Weitere Informationen</a></td></tr>
</table>

>[!NOTE]
>Diese Wartezeiten sind absichtlich so konzipiert, dass hohe Sicherheits- und Leistungsstandards für alle Benutzer gewährleistet werden. Darüber hinaus behält sich Microsoft Managed Desktop basierend auf daten, die auf allen Microsoft Managed Desktop-Geräten gesammelt wurden, sowie dem unterschiedlichen Umfang und den Auswirkungen von Updates Flexibilität vor, um die Länge der oben genannten Rückstellungszeiträume für alle Bereitstellungsgruppen ad hoc zu ändern.
>
>Microsoft Managed Desktop führt eine unabhängige Bewertung der einzelnen Windows-Featurefreigaben durch, um deren Notwendigkeit und Nutzen für die verwalteten Mandanten zu bewerten. Daher stellt Microsoft Managed Desktop möglicherweise nicht alle Windows-Featureupdates zur Verfügung. 

## <a name="windows-insider-program"></a>Windows-Insider-Programm

Microsoft Managed Desktop unterstützt keine Geräte, die Teil des Windows-Insider-Programms sind. Das Windows-Insider-Programm dient zum Überprüfen der Vorabversion von Windows-Software und ist für Geräte vorgesehen, die nicht unternehmenskritisch sind. Es ist zwar eine wichtige Microsoft-Initiative, aber nicht für eine umfassende Bereitstellung in Produktionsumgebungen vorgesehen. 

Alle Geräte, die mit Windows-Insider-Builds gefunden werden, werden möglicherweise in die Testgruppe gestellt und von Vereinbarungen zum Updatedienstlevel und von der Benutzerunterstützung von Microsoft Managed Desktop ausgenommen.

## <a name="bandwidth-management"></a>Bandbreitenverwaltung

Wir verwenden [die Übermittlungsoptimierung](/windows/deployment/update/waas-delivery-optimization) für alle Betriebssystem- und Treiberupdates. Dadurch wird die Downloadgröße des Windows Update-Diensts minimiert, indem Updates von Peers innerhalb des Unternehmensnetzwerks gesucht werden.