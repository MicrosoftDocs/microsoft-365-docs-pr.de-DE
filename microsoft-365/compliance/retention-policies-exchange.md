---
title: Informationen zur Aufbewahrung für Exchange
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
description: Informationen zur Funktionsweise einer Aufbewahrungsrichtlinien für Exchange.
ms.openlocfilehash: 4e8a536aaa81b0117f40b0ce330491fa8430f97c
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754435"
---
# <a name="learn-about-retention-for-exchange"></a>Informationen zu Aufbewahrungsrichtlinien für Exchange

Die Informationen in diesem Artikel ergänzen den Beitrag [Informationen zu Aufbewahrungsrichtlinien](retention.md), da er spezifische Angaben für Exchange beinhaltet.  Informationen zu anderen Arbeitsbereichen finden Sie unter:

- [Informationen zur Aufbewahrung für SharePoint und OneDrive](retention-policies-sharepoint.md)
- [Informationen zur Aufbewahrung für Microsoft Teams](retention-policies-teams.md)
- [Informationen zur Aufbewahrung für Yammer](retention-policies-yammer.md)

## <a name="whats-included-for-retention-and-deletion"></a>Lieferumfang für Aufbewahrung und Löschung

Die folgenden Exchange-Elemente können mithilfe von Aufbewahrungsrichtlinien und Aufbewahrungskennzeichnungen beibehalten oder gelöscht werden: E-Mail-Nachrichten (einschließlich Entwürfe) mit sämtlichen Anlagen, Aufgaben mit einem Enddatum, sowie Notizen. 

Kalenderelemente mit einem Enddatum werden in Aufbewahrungsrichtlinien unterstützt, aber nicht in Aufbewahrungskennzeichnungen.

Kontakte und alle Aufgaben und Kalenderelemente, die kein Enddatum aufweisen, werden nicht unterstützt.

Andere in einem Postfach gespeicherte Elemente, z. B. gespeicherte Skype- und Teams-Nachrichten, werden in Aufbewahrungsrichtlinien und Aufbewahrungskennzeichnungen für Exchange nicht einbezogen. Diese Elemente haben ihre eigenen Aufbewahrungsrichtlinien.

## <a name="how-retention-works-for-exchange"></a>Funktionsweise einer Aufbewahrungsrichtlinie mit Exchange

Sowohl Postfächer als auch öffentliche Ordner verwenden den [Ordner „Wiederherstellbare Elemente“](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) zum Aufbewahren von Elementen. Nur Personen, denen eDiscovery-Berechtigungen zugewiesen wurden, können Elemente im Ordner "Wiederherstellbare Elemente" eines anderen Benutzers anzeigen.
  
Standardmäßig wird eine Nachricht, die von einem Benutzer aus einem anderen Ordner als dem Ordner "Gelöschte Elemente" gelöscht wird, in den Ordner "Gelöschte Elemente" verschoben. Wenn ein Benutzer ein Element im Ordner "Gelöschte Elemente" löscht, wird es in den Ordner "Wiederherstellbare Elemente" verschoben. Ein Benutzer kann ein Element jedoch auch mittels UMSCHALT+ENTF aus einem Ordner löschen. Dadurch wird der Ordner „Gelöschte Elemente“ umgangen und das Element direkt in den Ordner „Wiederherstellbare Elemente“ verschoben.
  
Wenn Sie eine Aufbewahrungsrichtlinie auf einen Exchange-Speicherort anwenden, wertet ein Zeitgeberauftrag regelmäßig die Elemente im Ordner „Wiederherstellbare Elemente“ aus.  Wenn ein Element nicht mindestens die Regeln einer Aufbewahrungsrichtlinie oder Aufbewahrungsbezeichnung erfüllt, wird es dauerhaft (endgültig) aus dem Ordner „Wiederherstellbare Elemente“ gelöscht.

Der Zeitgeberauftrag kann bis zu sieben Tage für die Ausführung benötigen, und der Exchange-Speicherort muss mindestens 10 MB umfassen.
  
Wenn ein Benutzer versucht, Eigenschaften eines Postfachelements zu ändern – zum Beispiel Betreff, Text, Anhänge, Sender und Empfänger oder Sende- bzw. Empfangsdatum einer Nachricht – wird eine Kopie des ursprünglichen Elements im Ordner "Wiederherstellbare Elemente" gespeichert, bevor die Änderung übernommen wird. Diese Aktion findet für alle nachfolgenden Änderungen statt. Am Ende des Aufbewahrungszeitraums werden Kopien im Ordner "Wiederherstellbare Elemente" endgültig gelöscht.

Nachdem Exchange-Inhalten eine Aufbewahrungsrichtlinie zugewiesen wurde, sind die Inhaltspfade davon abhängig, ob die Aufbewahrungseinstellungen die Aufbewahrung und das Löschen, die reine Aufbewahrung oder das reine Löschen vorgeben.

Wenn die Aufbewahrungseinstellungen das Aufbewahren und Löschen vorgeben:

![Diagramm des Aufbewahrungsverlaufs bei E-Mails und öffentlichen Ordnern](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. **Wenn das Element während des Aufbewahrungszeitraums vom Benutzer geändert oder dauerhaft gelöscht wird** (entweder UMSCHALT+ENTF oder aus "Gelöschte Elemente" gelöscht), wird es in den Ordner "Wiederherstellbare Elemente" verschoben (oder im Fall der Bearbeitung kopiert). Dort wird in regelmäßigen Abständen ein Zeitgeberauftrag ausgeführt, der Elemente identifiziert, deren Aufbewahrungszeitraum abgelaufen ist. Diese Elemente werden innerhalb von vierzehn Tagen nach Ende des Aufbewahrungszeitraums dauerhaft gelöscht. Beachten Sie, dass 14 Tage die Standardeinstellung ist, die aber auf bis zu 30 Tage festgelegt werden kann.

2. **Wenn das Element während des Aufbewahrungszeitraums nicht geändert oder gelöscht wird** , wird derselbe Prozess in regelmäßigen Abständen für alle Ordner im Postfach ausgeführt, und es werden Elemente identifiziert, deren Aufbewahrungszeitraum abgelaufen ist. Diese Elemente werden innerhalb von 14 Tagen nach Ende des Aufbewahrungszeitraums dauerhaft gelöscht. Beachten Sie, dass 14 Tage die Standardeinstellung ist, die aber auf bis zu 30 Tage festgelegt werden kann. 

Wenn die Aufbewahrungseinstellungen das reine Aufbewahren oder das reine Löschen vorgeben, stellen die Inhaltspfade Varianten von "Aufbewahren und Löschen" dar:

### <a name="content-paths-for-retain-only-retention-settings"></a>Inhaltspfade für Aufbewahrungseinstellungen für reine Aufbewahrung

1. **Wenn das Element während des Aufbewahrungszeitraums geändert oder gelöscht wird** : Eine Kopie des ursprünglichen Elements wird im Ordner „Wiederherstellbare Elemente“ erstellt und bis zum Ende des Aufbewahrungszeitraums aufbewahrt, wo dann die Kopie im Ordner „Wiederherstellbare Elemente“ innerhalb von 14 Tagen nach Ablauf des Elements endgültig gelöscht wird. 

2. **Wenn das Element während des Aufbewahrungszeitraums nicht geändert oder gelöscht wird** : Weder vor noch nach dem Aufbewahrungszeitraum passiert etwas. Das Element verbleibt an seinem Ursprungsort.

### <a name="content-paths-for-delete-only-retention-settings"></a>Inhaltspfade für Aufbewahrungseinstellungen für reines Löschen

1. **Wenn das Element während des festgelegte Zeitraums nicht gelöscht wird** , wird es am Ende des in der Aufbewahrungsrichtlinie festgelegten Zeitraums in den Ordner "Wiederherstellbare Elemente" verschoben. 

2. **Wenn das Element während des festgelegten Zeitraums gelöscht wird** , wird es sofort in den Ordner "Wiederherstellbare Elemente" verschoben. Wenn ein Benutzer das Element dort löscht oder den Ordner „Wiederherstellbare Elemente“ leert, wird das Element endgültig gelöscht. Andernfalls wird das Element endgültig gelöscht, nachdem es 14 Tage im Ordner „Wiederherstellbare Elemente“ aufbewahrt wurde. 

## <a name="when-a-user-leaves-the-organization"></a>Wenn ein Benutzer die Organisation verlässt 

Wenn ein Benutzer Ihre Organisation verlässt und sein Postfach in einer Aufbewahrungsrichtlinie enthalten ist, wird das Postfach zu einem inaktiven Postfach, wenn das Microsoft 365-Konto des Benutzers gelöscht wird. Die Inhalte eines inaktiven Postfachs unterliegen weiterhin jeglicher Aufbewahrungsrichtlinie, die dem Postfach zugewiesen wurde, bevor es inaktiv wurde, und die Inhalte sind für eDiscovery-Suchen verfügbar. Weitere Informationen finden Sie unter [Inaktive Postfächer in Exchange Online](inactive-mailboxes-in-office-365.md).

## <a name="configuration-guidance"></a>Konfigurationsleitfaden

Wenn Sie die Konfiguration der Datenaufbewahrung in Microsoft 365 zum ersten Mal durchführen möchten, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).

Wenn Sie eine Aufbewahrungsrichtlinie oder Aufbewahrungsbezeichnung für Exchange konfigurieren möchten, lesen Sie die folgenden Anweisungen:
- [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](create-retention-policies.md)
- [Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)
- [Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte](apply-retention-labels-automatically.md)