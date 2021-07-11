---
title: Informationen zur Aufbewahrung für Yammer
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Erfahren Sie Näheres über Aufbewahrungsrichtlinien, die für Yammer gelten.
ms.openlocfilehash: 1398bf385631967d92de760924ef94e2b3c16441
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362294"
---
# <a name="learn-about-retention-for-yammer"></a>Informationen zur Aufbewahrung für Yammer

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Dieses Feature ist derzeit in der Vorschau und kann jederzeit geändert werden.

Die Informationen in diesem Artikel ergänzen den Beitrag [Informationen zu Aufbewahrungsrichtlinien](retention.md), da er spezifische Angaben für Yammer beinhaltet.

Informationen zu anderen Arbeitsbereichen finden Sie unter:

- [Informationen zur Aufbewahrung für SharePoint und OneDrive](retention-policies-sharepoint.md)
- [Informationen zur Aufbewahrung für Microsoft Teams](retention-policies-teams.md)
- [Informationen zur Aufbewahrung für Exchange](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>Lieferumfang für Aufbewahrung und Löschung

Die folgenden Yammer-Elemente können mithilfe von Aufbewahrungsrichtlinien für Yammer beibehalten oder gelöscht werden: Community-Nachrichten und Benutzernachrichten.

Reaktionen von anderen Personen in der Form von Emoticons sind in diesen Nachrichten nicht enthalten.

## <a name="how-retention-works-with-yammer"></a>Funktionsweise einer Aufbewahrungsrichtlinie mit Yammer

Verwenden Sie diesen Abschnitt, um zu verstehen, wie Compliance-Anforderungen durch Back-End-Speicher und -Prozesse erfüllt und durch eDiscovery-Tools anstelle von Nachrichten überprüft werden sollten, die aktuell in der Yammer-App angezeigt werden.

Sie können eine Aufbewahrungsrichtlinie verwenden, um Daten aus Community-Nachrichten und Benutzernachrichten in Yammer aufzubewahren, und diese Nachrichten zu löschen. Hinter den Kulissen werden Exchange-Postfächer verwendet, um die aus diesen Nachrichten kopierten Daten zu speichern. Daten aus Yammer-Benutzernachrichten werden in einem ausgeblendeten Ordner im Postfach jedes Benutzers gespeichert, der in der Benutzernachricht eingeschlossen ist, und für Community-Nachrichten wird ein ähnlicher ausgeblendeter Ordner in einem Gruppenpostfach verwendet.

Kopien von Community-Nachrichten können auch im ausgeblendeten Ordner von Benutzerpostfächern gespeichert werden, wenn sie Benutzer @erwähnen, oder den Benutzer über eine Antwort benachrichtigen. Obwohl diese Nachrichten als Community-Nachricht entstanden sind, wird eine Aufbewahrungsrichtlinie für Yammer-Benutzernachrichten oft auch Kopien von Community-Nachrichten enthalten.

Diese ausgeblendeten Ordner sind nicht für den direkten Zugriff von Benutzern oder Administratoren gedacht, sondern zum Speichern von Daten, die Complianceadministratoren mit eDiscovery-Tools durchsuchen können.

> [!IMPORTANT]
> Da Kopien von Community-Nachrichten auch in Benutzerpostfächern gespeichert werden können, kann eine Aufbewahrungsrichtlinie mit einer Löschaktion für Yammer-Benutzernachrichten dazu führen, dass die ursprüngliche Community-Nachricht in der Yammer-App für Benutzer nicht mehr sichtbar ist.
> 
> Eine Kopie der ursprünglichen Nachricht ist jedoch weiterhin im ausgeblendeten Ordner des Community-Gruppenpostfachs verfügbar und ist mit eDiscovery-Suchen für Compliance-Zwecke abrufbar.

Yammer-Nachrichten sind nicht von Aufbewahrungsrichtlinien betroffen, die für Exchange-Postfächer konfiguriert sind. Obwohl Yammer-Nachrichten in Exchange gespeichert sind, sind diese Yammer-Daten nur in einer Aufbewahrungsrichtlinie enthalten, die für die Speicherorte von **Yammer-Communitynachrichten** und **Benutzernachrichten in Yammer** konfiguriert ist.

> [!NOTE]
> Wenn eine aktive Aufbewahrungsrichtlinie, durch die Yammer-Daten aufbewahrt werden, Benutzer einbezieht, und Sie ein Postfach eines in diese Richtlinie einbezogenen Benutzers löschen, wird es in ein [inaktives Postfach](inactive-mailboxes-in-office-365.md) konvertiert, damit die Yammer-Daten aufbewahrt werden. Wenn diese Yammer-Daten für den Benutzer nicht aufbewahrt werden müssen, schließen Sie das Benutzerkonto aus der Aufbewahrungsrichtlinie aus, bevor Sie das Postfach löschen.

Nachdem eine Aufbewahrungsrichtlinie für Yammer-Nachrichten konfiguriert wurde, wertet ein Zeitgeberauftrag des Exchange-Dienstes regelmäßig Elemente im verborgenen Ordner aus, in dem diese Yammer-Nachrichten gespeichert sind. Die Ausführung des Zeitgeberauftrags dauert bis zu sieben Tage. Wenn die Aufbewahrungszeit für die Elemente abgelaufen ist, werden sie in den Ordner "SubstrateHolds" verschoben, einen versteckten Ordner, der sich in jedem Benutzer- oder Gruppenpostfach befindet, um "vorläufig gelöschte" Elemente zu speichern, bevor sie endgültig gelöscht werden.

> [!NOTE]
> Aufgrund des [ ersten Aufbewahrungsprinzips](retention.md#the-principles-of-retention-or-what-takes-precedence) wird die endgültige Löschung immer ausgesetzt, wenn dasselbe Element aufgrund von einer anderen Aufbewahrungsrichtlinie aufbewahrt werden muss oder sich aus rechtlichen oder juristischen Gründen in eDiscovery-Aufbewahrungspflichten befindet.

Nachdem eine Aufbewahrungsrichtlinie für Yammer-Nachrichten konfiguriert wurde, sind die Inhaltspfade davon abhängig, ob die Aufbewahrungsrichtlinie das Aufbewahren und dann Löschen, nur das Aufbewahren oder nur das Löschen vorsieht.

Wenn die Aufbewahrungsrichtlinie dem Aufbewahren und dann Löschen dient:

![Darstellung des Aufbewahrungsablaufs für Yammer-Nachrichten](../media/yammerretentionlifecycle.png)

Zu den zwei Pfaden im Diagramm:

1. **Wenn eine Yammer-Nachricht während des Aufbewahrungszeitraums vom Benutzer bearbeitet oder gelöscht wird**, wird die Originalnachricht sofort in den Ordner "SubstrateHolds" kopiert (falls bearbeitet) oder verschoben (falls gelöscht). Die Nachricht wird dort bis zum Ablauf des Aufbewahrungszeitraums gespeichert und dann sofort endgültig gelöscht.

2. **Wenn eine Yammer-Nachricht nicht gelöscht wird** und für aktuelle Nachrichten nach der Bearbeitung: Die Nachrichten werden nach Ablauf des Aufbewahrungszeitraums in den Ordner "SubstrateHolds" verschoben. Dieser Vorgang dauert bis zu sieben Tage ab dem Ablaufdatum. Wenn sich die Nachricht im Ordner "SubstrateHolds" befindet, wird sie sofort endgültig gelöscht. 

> [!NOTE]
> Nachrichten im Ordner SubstrateHolds können mit eDiscovery-Tools durchsucht werden. Solange Nachrichten nicht endgültig gelöscht sind (im Ordner SubstrateHolds), bleiben sie mit eDiscovery-Tools durchsuchbar.

Wenn die Aufbewahrungsrichtlinie dem reinen Aufbewahren oder dem reinen Löschen dient, stellen die Inhaltspfade Varianten von Aufbewahren und Löschen dar.

### <a name="content-paths-for-retain-only-retention-policy"></a>Inhaltspfade für rein aufbewahrende Aufbewahrungsrichtlinien

1. **Wenn Yammer-Nachricht bearbeitet oder gelöscht wird**: Eine Kopie der Originalnachricht wird sofort im Ordner "SubstrateHolds" erstellt und dort bis zum Ablauf des Aufbewahrungszeitraums aufbewahrt. Anschließend wird die Nachricht sofort dauerhaft aus dem Ordner "SubstrateHolds" gelöscht.

2. **Wenn die Yammer-Nachricht nicht geändert oder gelöscht wird** und für aktuelle Nachrichten nach der Bearbeitung während des Aufbewahrungszeitraums: Vor und nach dem Aufbewahrungszeitraum geschieht nichts; die Nachricht wird an ihrem ursprünglichen Ort belassen.

### <a name="content-paths-for-delete-only-retention-policy"></a>Inhaltspfade für Aufbewahrungsrichtlinien für reines Löschen

1. **Wenn die Yammer-Nachricht während des Aufbewahrungszeitraums nicht gelöscht wird**: Die Nachricht wird am Ende des Aufbewahrungszeitraums in den Ordner "SubstrateHolds" verschoben. Dieser Vorgang dauert bis zu sieben Tage ab dem Ablaufdatum. Anschließend wird die Nachricht sofort dauerhaft aus dem Ordner "SubstrateHolds" gelöscht.

2. **Wenn die Yammer-Nachricht während des Zeitraums vom Benutzer gelöscht wird**, wird das Element sofort in den Ordner "SubstrateHolds" verschoben, wo es sofort endgültig gelöscht wird.


## <a name="messages-and-external-users"></a>Nachrichten und externe Benutzer

Standardmäßig gilt eine Aufbewahrungsrichtlinie für Benutzernachrichten in Yammer für alle Benutzer in Ihrer Organisation, jedoch nicht für externe Benutzer. Sie können eine Aufbewahrungsrichtlinie auf externe Benutzer anwenden, wenn Sie die Option **Bearbeiten** für eingeschlossene Benutzer verwenden und deren Konto angeben.

Zurzeit werden Azure-B2B-Gastbenutzer nicht unterstützt.

## <a name="when-a-user-leaves-the-organization"></a>Wenn ein Benutzer die Organisation verlässt 

Wenn ein Benutzer Ihre Organisation verlässt und sein Microsoft 365-Konto gelöscht wird, werden seine Benutzernachrichten in Yammer, die der Aufbewahrung unterliegen, in einem inaktiven Postfach gespeichert. Die Nachrichten unterliegen weiterhin jeder Aufbewahrungsrichtlinie, die dem Benutzer zugewiesen wurde, bevor sein Postfach inaktiv wurde, und die Inhalte sind für eine eDiscovery-Suche verfügbar. Weitere Informationen finden Sie unter [Inaktive Postfächer in Exchange Online](inactive-mailboxes-in-office-365.md). 

Wenn der Benutzer Dateien in Yammer gespeichert hat, lesen Sie den [entsprechenden Abschnitt](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) für SharePoint und OneDrive.

## <a name="limitations"></a>Einschränkungen

Yammer-Aufbewahrungsrichtlinien befinden sich derzeit in der Vorschau, und wir arbeiten kontinuierlich an der Optimierung der Aufbewahrungsfunktionen. In der Zwischenzeit sollten Sie die folgende Einschränkung beachten, wenn Sie die Aufbewahrung von Yammer-Community-Nachrichten und Benutzernachrichten verwenden:

- Wenn Sie die Option **Bearbeiten** für den Speicherort **Yammer-Benutzernachrichten** auswählen, werden möglicherweise Gäste und Nicht-Postfachbenutzer angezeigt. Aufbewahrungsrichtlinien sind nicht auf diese Benutzer ausgerichtet, deshalb sollten Sie sie nicht auswählen.

## <a name="configuration-guidance"></a>Konfigurationsleitfaden

Wenn Sie die Konfiguration der Datenaufbewahrung in Microsoft 365 zum ersten Mal durchführen möchten, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).

Wenn Sie startklar für die Erstellung einer Aufbewahrungsrichtlinie für Yammer sind, lesen Sie [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](create-retention-policies.md).