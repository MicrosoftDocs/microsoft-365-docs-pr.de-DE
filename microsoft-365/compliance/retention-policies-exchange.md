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
description: Erfahren Sie mehr über das Aufbewahrungsverhalten, das speziell für Exchange-E-Mails und öffentliche Exchange-Ordner gilt.
ms.openlocfilehash: db39ab0f1eca1cc03dd0bbb5ffb500658695247a
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292533"
---
# <a name="learn-about-retention-policies-for-exchange"></a>Informationen zu Aufbewahrungsrichtlinien für Exchange

Die Informationen in diesem Artikel ergänzen den Beitrag [Informationen zu Aufbewahrungsrichtlinien](retention-policies.md) um spezifische Angaben für Exchange.

## <a name="how-a-retention-policy-works-with-exchange-locations"></a>Funktionsweise einer Aufbewahrungsrichtlinie mit Exchange-Speicherorten

Für die E-Mails, den Kalender und andere Elemente eines Benutzers wird eine Aufbewahrungsrichtlinie auf Postfachebene angewendet.

Für einen öffentlichen Ordner wird eine Aufbewahrungsrichtlinie auf Ordnerebene angewendet, nicht auf Postfachebene. 

Sowohl Postfächer als auch öffentliche Ordner verwenden den Ordner "Wiederherstellbare Elemente" zum Aufbewahren von Elementen. Nur Personen, denen eDiscovery-Berechtigungen zugewiesen wurden, können Elemente im Ordner "Wiederherstellbare Elemente" eines anderen Benutzers anzeigen.
  
Standardmäßig wird eine Nachricht, die von einem Benutzer aus einem anderen Ordner als dem Ordner "Gelöschte Elemente" gelöscht wird, in den Ordner "Gelöschte Elemente" verschoben. Wenn ein Benutzer ein Element im Ordner "Gelöschte Elemente" löscht, wird es in den Ordner "Wiederherstellbare Elemente" verschoben. Ein Benutzer kann ein Element jedoch auch mittels UMSCHALT+ENTF aus einem Ordner löschen. Dadurch wird der Ordner "Gelöschte Elemente" umgangen und das Element direkt in den Ordner "Wiederherstellbare Elemente" verschoben.
  
Wenn Sie eine Aufbewahrungsrichtlinie auf einen Exchange-Speicherort anwenden, wertet ein Zeitgeberauftrag regelmäßig die Elemente im Ordner "Wiederherstellbare Elemente" aus. Wenn ein Element nicht mindestens die Regeln einer Aufbewahrungsrichtlinie erfüllt, wird es dauerhaft (endgültig) aus dem Ordner "Wiederherstellbare Elemente" gelöscht.

Der Zeitgeberauftrag kann bis zu sieben Tage für die Ausführung benötigen, und der Exchange-Speicherort muss mindestens 10 MB umfassen.
  
Wenn ein Benutzer versucht, Eigenschaften eines Postfachelements zu ändern – zum Beispiel Betreff, Text, Anhänge, Sender und Empfänger oder Sende- bzw. Empfangsdatum einer Nachricht – wird eine Kopie des ursprünglichen Elements im Ordner "Wiederherstellbare Elemente" gespeichert, bevor die Änderung übernommen wird. Diese Aktion findet für alle nachfolgenden Änderungen statt. Am Ende des Aufbewahrungszeitraums werden Kopien im Ordner "Wiederherstellbare Elemente" endgültig gelöscht.

Nachdem einem Postfach oder einem öffentlichen Ordner eine Aufbewahrungsrichtlinie zugewiesen wurde, sind die Inhaltspfade davon abhängig, ob die Aufbewahrungseinstellungen die Aufbewahrung und das Löschen, die reine Aufbewahrung oder das reine Löschen vorgeben.

Wenn die Aufbewahrungseinstellungen das Aufbewahren und Löschen vorgeben:

![Diagramm des Aufbewahrungsverlaufs bei E-Mails und öffentlichen Ordnern](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. **Wenn das Element während des Aufbewahrungszeitraums vom Benutzer geändert oder dauerhaft gelöscht wird** (entweder UMSCHALT+ENTF oder aus "Gelöschte Elemente" gelöscht), wird es in den Ordner "Wiederherstellbare Elemente" verschoben (oder im Fall der Bearbeitung kopiert). Dort wird in regelmäßigen Abständen ein Zeitgeberauftrag ausgeführt, der Elemente identifiziert, deren Aufbewahrungszeitraum abgelaufen ist. Diese Elemente werden innerhalb von vierzehn Tagen nach Ende des Aufbewahrungszeitraums dauerhaft gelöscht. Beachten Sie, dass 14 Tage die Standardeinstellung ist, die aber auf bis zu 30 Tage festgelegt werden kann.
    
2. **Wenn das Element während des Aufbewahrungszeitraums nicht geändert oder gelöscht wird**, wird derselbe Prozess in regelmäßigen Abständen für alle Ordner im Postfach ausgeführt, und es werden Elemente identifiziert, deren Aufbewahrungszeitraum abgelaufen ist. Diese Elemente werden innerhalb von 14 Tagen nach Ende des Aufbewahrungszeitraums dauerhaft gelöscht. Beachten Sie, dass 14 Tage die Standardeinstellung ist, die aber auf bis zu 30 Tage festgelegt werden kann. 

Wenn die Aufbewahrungseinstellungen das reine Aufbewahren oder das reine Löschen vorgeben, stellen die Inhaltspfade Varianten von "Aufbewahren und Löschen" dar:

### <a name="content-paths-for-retain-only-retention-settings"></a>Inhaltspfade für Aufbewahrungseinstellungen für reine Aufbewahrung

1. **Wenn das Element während des Aufbewahrungszeitraums geändert oder gelöscht wird**: Eine Kopie des ursprünglichen Elements wird im Ordner „Wiederherstellbare Elemente“ erstellt und bis zum Ende des Aufbewahrungszeitraums aufbewahrt, wo dann die Kopie im Ordner „Wiederherstellbare Elemente“ innerhalb von 14 Tagen nach Ablauf des Elements endgültig gelöscht wird. 

2. **Wenn das Element während des Aufbewahrungszeitraums nicht geändert oder gelöscht wird**: Weder vor noch nach dem Aufbewahrungszeitraum passiert etwas. Das Element verbleibt an seinem Ursprungsort.

### <a name="content-paths-for-delete-only-retention-settings"></a>Inhaltspfade für Aufbewahrungseinstellungen für reines Löschen

1. **Wenn das Element während des festgelegte Zeitraums nicht gelöscht wird**, wird es am Ende des in der Aufbewahrungsrichtlinie festgelegten Zeitraums in den Ordner "Wiederherstellbare Elemente" verschoben. 

2. **Wenn das Element während des festgelegten Zeitraums gelöscht wird**, wird es sofort in den Ordner "Wiederherstellbare Elemente" verschoben. Wenn ein Benutzer das Element dort löscht oder den Ordner „Wiederherstellbare Elemente“ leert, wird das Element endgültig gelöscht. Andernfalls wird das Element endgültig gelöscht, nachdem es 14 Tage im Ordner „Wiederherstellbare Elemente“ aufbewahrt wurde. 

## <a name="excluding-specific-types-of-exchange-items-from-a-retention-policy"></a>Ausschließen von bestimmten Typen von Exchange-Elementen aus einer Aufbewahrungsrichtlinie

Unter Verwendung von PowerShell können Sie bestimmte Exchange-Elementtypen aus einer Aufbewahrungsrichtlinie ausschließen. Sie können z. B. Voicemailnachrichten, Chatunterhaltungen und andere Skype for Business Online-Inhalte in Postfächern ausschließen. Sie können auch Kalender-, Notiz- und Aufgabenelemente ausschließen. Diese Funktion steht nur über PowerShell zur Verfügung. Sie ist nicht verfügbar, wenn Sie eine Aufbewahrungsrichtlinie mithilfe des Assistenten im Microsoft 365 Compliance Center erstellen.
  
Wenn Sie die ausgewählten Typen für Exchange-Elemente in einer Aufbewahrungsrichtlinie ausschließen möchten, verwenden Sie den Parameter `ExcludedItemClasses` mit den Cmdlets `New-RetentionComplianceRule` und `Set-RetentionComplianceRule`.


### <a name="when-a-user-leaves-the-organization"></a>Wenn ein Benutzer die Organisation verlässt 

Wenn ein Benutzer Ihre Organisation verlässt und sein Postfach in einer Aufbewahrungsrichtlinie enthalten ist, wird das Postfach zu einem inaktiven Postfach, wenn das Office 365-Konto des Benutzers gelöscht wird. Die Inhalte eines inaktiven Postfachs unterliegen weiterhin jeglicher Aufbewahrungsrichtlinie, die dem Postfach zugewiesen wurde, bevor es inaktiv wurde, und die Inhalte sind für eDiscovery-Suchen verfügbar. Weitere Informationen finden Sie unter [Inaktive Postfächer in Exchange Online](inactive-mailboxes-in-office-365.md). 

## <a name="how-to-configure-a-retention-policy-for-exchange"></a>Konfigurieren einer Aufbewahrungsrichtlinie für Exchange

Siehe [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](create-retention-policies.md).

Wählen Sie auf der Seite **Speicherorte auswählen** des Assistenten eine der folgenden Optionen aus:

- **Richtlinie nur auf Inhalte in Exchange-E-Mails, öffentlichen Ordnern, Office 365-Gruppen, OneDrive und SharePoint-Dokumenten anwenden**

- **Bestimmte Speicherorte auswählen** > **Exchange-E-Mail** und **Öffentliche Exchange-Ordner**

