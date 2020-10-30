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
ms.openlocfilehash: 3e4cfd5c9e5ef8c28ecd069f3474764b966d6c9a
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2020
ms.locfileid: "48795000"
---
# <a name="learn-about-retention-for-yammer"></a>Informationen zur Aufbewahrung für Yammer

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Die Informationen in diesem Artikel ergänzen den Beitrag [Informationen zu Aufbewahrungsrichtlinien](retention.md), da er spezifische Angaben für Yammer beinhaltet.

Informationen zu anderen Arbeitsbereichen finden Sie unter:

- [Informationen zur Aufbewahrung für SharePoint und OneDrive](retention-policies-sharepoint.md)
- [Informationen zur Aufbewahrung für Microsoft Teams](retention-policies-teams.md)
- [Informationen zur Aufbewahrung für Exchange](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>Lieferumfang für Aufbewahrung und Löschung

Die folgenden Yammer-Elemente können mithilfe von Aufbewahrungsrichtlinien für Yammer beibehalten oder gelöscht werden: Community-Nachrichten und private Nachrichten.

Reaktionen von anderen Personen in der Form von Emoticons sind in diesen Nachrichten nicht enthalten.

## <a name="how-retention-works-with-yammer"></a>Funktionsweise einer Aufbewahrungsrichtlinie mit Yammer

Sie können eine Aufbewahrungsrichtlinie zum Aufbewahren und Löschen von Communitynachrichten und privaten Nachrichten in Yammer verwenden. Private Nachrichten werden in einem verborgenen Ordner im Postfach jedes Benutzers gespeichert, der in die Nachricht eingebunden ist, und Communitynachrichten werden in einem ähnlichen verborgenen Ordner im Gruppenpostfach für die Community gespeichert.

Aufbewahrungsrichtlinien, die für Benutzer- oder Gruppenpostfächer konfiguriert sind, wirken sich nicht auf Yammer-Nachrichten aus. Obwohl Yammer-Nachrichten in Exchange gespeichert sind, werden diese Yammer-Daten nur von einer Aufbewahrungsrichtlinie eingeschlossen, die für die Speicherorte **Yammer-Communitynachrichten** und **Private Yammer-Nachrichten** konfiguriert ist.

> [!NOTE]
> Wenn eine aktive Aufbewahrungsrichtlinie, durch die Yammer-Daten aufbewahrt werden, Benutzer einbezieht, und Sie ein Postfach eines in diese Richtlinie einbezogenen Benutzers löschen, wird es in ein [inaktives Postfach](inactive-mailboxes-in-office-365.md) konvertiert, damit die Yammer-Daten aufbewahrt werden. Wenn diese Yammer-Daten für den Benutzer nicht aufbewahrt werden müssen, schließen Sie das Benutzerkonto aus der Aufbewahrungsrichtlinie aus, bevor Sie das Postfach löschen.

Nachdem eine Aufbewahrungsrichtlinie für Yammer-Nachrichten konfiguriert wurde, wertet ein Zeitgeberauftrag des Exchange-Dienstes regelmäßig Elemente im verborgenen Ordner aus, in dem diese Yammer-Nachrichten gespeichert sind. Die Ausführung des Zeitgeberauftrags dauert bis zu sieben Tage. Wenn die Aufbewahrungszeit für die Elemente abgelaufen ist, werden sie in den Ordner "SubstrateHolds" verschoben, einen versteckten Ordner, der sich in jedem Benutzer- oder Gruppenpostfach befindet, um "vorläufig gelöschte" Elemente zu speichern, bevor sie endgültig gelöscht werden.

Nachdem eine Aufbewahrungsrichtlinie für Yammer-Nachrichten konfiguriert wurde, sind die Inhaltspfade davon abhängig, ob die Aufbewahrungsrichtlinie das Aufbewahren und dann Löschen, nur das Aufbewahren oder nur das Löschen vorsieht.

Wenn die Aufbewahrungsrichtlinie dem Aufbewahren und dann Löschen dient:

![Darstellung des Aufbewahrungsablaufs für Yammer-Nachrichten](../media/yammerretentionlifecycle.png)

Zu den zwei Pfaden im Diagramm:

1. **Wenn eine Yammer-Nachricht während des Aufbewahrungszeitraums vom Benutzer bearbeitet oder gelöscht wird** , wird die Originalnachricht sofort in den Ordner "SubstrateHolds" kopiert (falls bearbeitet) oder verschoben (falls gelöscht). Die Nachricht wird dort bis zum Ablauf des Aufbewahrungszeitraums gespeichert und dann sofort endgültig gelöscht.

2. **Wenn eine Yammer-Nachricht nicht gelöscht wird** und für aktuelle Nachrichten nach der Bearbeitung: Die Nachrichten werden nach Ablauf des Aufbewahrungszeitraums in den Ordner "SubstrateHolds" verschoben. Dieser Vorgang dauert bis zu sieben Tage ab dem Ablaufdatum. Wenn sich die Nachricht im Ordner "SubstrateHolds" befindet, wird sie sofort endgültig gelöscht. 

> [!NOTE]
> Nachrichten im Ordner SubstrateHolds können mit eDiscovery-Tools durchsucht werden. Solange Nachrichten nicht endgültig gelöscht sind (im Ordner SubstrateHolds), bleiben sie mit eDiscovery-Tools durchsuchbar.

Wenn die Aufbewahrungsrichtlinie dem reinen Aufbewahren oder dem reinen Löschen dient, stellen die Inhaltspfade Varianten von Aufbewahren und Löschen dar.

### <a name="content-paths-for-retain-only-retention-policy"></a>Inhaltspfade für rein aufbewahrende Aufbewahrungsrichtlinien

1. **Wenn eine Yammer-Nachricht bearbeitet oder gelöscht wird** : Wird eine Kopie der Originalnachricht sofort im Ordner "SubstrateHolds" erstellt und dort bis zum Ablauf des Aufbewahrungszeitraums aufbewahrt. Anschließend wird die Nachricht sofort dauerhaft aus dem Ordner "SubstrateHolds" gelöscht.

2. **Wenn die Yammer-Nachricht nicht geändert oder gelöscht wird** und für aktuelle Nachrichten nach der Bearbeitung während des Aufbewahrungszeitraums: Vor und nach dem Aufbewahrungszeitraum geschieht nichts; die Nachricht wird an ihrem ursprünglichen Ort belassen.

### <a name="content-paths-for-delete-only-retention-policy"></a>Inhaltspfade für Aufbewahrungsrichtlinien für reines Löschen

1. **Wenn die Yammer-Nachricht während des Aufbewahrungszeitraums nicht gelöscht wird** : Die Nachricht wird am Ende des Aufbewahrungszeitraums in den Ordner "SubstrateHolds" verschoben. Dieser Vorgang dauert bis zu sieben Tage ab dem Ablaufdatum. Anschließend wird die Nachricht sofort dauerhaft aus dem Ordner "SubstrateHolds" gelöscht.

2. **Wenn die Yammer-Nachricht während des Zeitraums vom Benutzer gelöscht wird** , wird das Element sofort in den Ordner "SubstrateHolds" verschoben, wo es sofort endgültig gelöscht wird.


## <a name="messages-and-external-users"></a>Nachrichten und externe Benutzer

Standardmäßig gilt eine Aufbewahrungsrichtlinie für private Yammer-Nachrichten für alle Benutzer in Ihrer Organisation, jedoch nicht für externe Benutzer. Sie können eine Aufbewahrungsrichtlinie auf externe Benutzer anwenden, indem Sie die Option **Benutzer auswählen** verwenden und die fraglichen Konten angeben. 

Zurzeit werden Azure-B2B-Gastbenutzer nicht unterstützt.

## <a name="when-a-user-leaves-the-organization"></a>Wenn ein Benutzer die Organisation verlässt 

Wenn ein Benutzer Ihre Organisation verlässt und sein Microsoft 365-Konto gelöscht wird, werden seine privaten Yammer-Nachrichten, die der Aufbewahrung unterliegen, in einem inaktiven Postfach gespeichert. Die Nachrichten unterliegen weiterhin jeder Aufbewahrungsrichtlinie, die dem Benutzer zugewiesen wurde, bevor sein Postfach inaktiv wurde, und die Inhalte sind für eine eDiscovery-Suche verfügbar. Weitere Informationen finden Sie unter [Inaktive Postfächer in Exchange Online](inactive-mailboxes-in-office-365.md). 

Wenn der Benutzer Dateien in Yammer gespeichert hat, lesen Sie den [entsprechenden Abschnitt](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) für SharePoint und OneDrive.

## <a name="limitations"></a>Einschränkungen

Yammer-Aufbewahrungsrichtlinien befinden sich derzeit in der Vorschau, und wir arbeiten kontinuierlich an der Optimierung der Aufbewahrungsfunktionen. Es gibt folgende Einschränkungen, die Sie bei der Aufbewahrung von Yammer-Community-Nachrichten und privaten Nachrichten beachten sollten:

- Wenn Sie **Benutzer auswählen** für den Speicherort **Private Yammer-Nachrichten** auswählen, werden möglicherweise Gäste und Nicht-Postfachbenutzer angezeigt. Aufbewahrungsrichtlinien sind nicht auf diese Benutzer ausgerichtet, deshalb sollten Sie sie nicht auswählen.

## <a name="configuration-guidance"></a>Konfigurationsleitfaden

Wenn Sie die Konfiguration der Datenaufbewahrung in Microsoft 365 zum ersten Mal durchführen möchten, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).

Wenn Sie startklar für die Erstellung einer Aufbewahrungsrichtlinie für Yammer sind, lesen Sie [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](create-retention-policies.md).
