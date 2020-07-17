---
title: Informationen zur Aufbewahrung für Teams
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
description: Erfahren Sie Näheres über Aufbewahrungsrichtlinien, die für Microsoft Teams gelten.
ms.openlocfilehash: 11e374dac4e1e0a13d3bdbc642922dca1b8954f4
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127382"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>Informationen zur Aufbewahrung für Microsoft Teams

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Die Informationen in diesem Artikel ergänzen den Beitrag [Informationen zur Aufbewahrung](retention.md) um spezifische Angaben für Microsoft Teams.

## <a name="how-retention-works-with-microsoft-teams"></a>Funktionsweise der Aufbewahrung mit Microsoft Teams

Sie können eine Aufbewahrungsrichtlinie für Chats und Kanalnachrichten in Microsoft Teams verwenden. Microsoft Teams-Chats werden in einem verborgenen Ordner im Postfach jedes Benutzers gespeichert, der am Chat teilnimmt, und Microsoft Teams-Kanalnachrichten werden in einem ähnlichen verborgenen Ordner im Gruppenpostfach für das Team gespeichert. 

Es ist wichtig zu verstehen, dass Microsoft Teams einen Azure-Chatdienst verwendet, der diese Daten ebenfalls speichert, und standardmäßig werden die Daten von diesem Dienst unbefristet gespeichert. Aus diesem Grund empfehlen wir, dass Sie eine Aufbewahrungsrichtlinie erstellen, die die Teams-Speicherorte zur Aufbewahrung und Löschung dieser Teams-Daten verwendet. Diese Aufbewahrungsrichtlinie kann die Daten sowohl aus den Exchange-Postfächern als auch aus dem zugrunde liegenden Azure-Chatdienst endgültig löschen. Weitere Informationen hierzu finden Sie unter [Sicherheit und Compliance in Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258), insbesondere im Abschnitt [Information Protection-Architektur](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture).

Aufbewahrungsrichtlinien, die für Benutzer- oder Gruppenpostfächer konfiguriert sind, wirken sich nicht auf Microsoft Teams-Chats und -Kanalnachrichten aus. Obwohl Microsoft Teams-Chats und -Kanalnachrichten in Exchange gespeichert sind, werden diese Microsoft Teams-Daten nur von einer Aufbewahrungsrichtlinie eingeschlossen, die für die Speicherorte von **Microsoft Teams-Kanalnachrichten** und **Microsoft Teams-Chats** konfiguriert ist.

> [!NOTE]
> Wenn eine aktive Aufbewahrungsrichtlinie, durch die Microsoft Teams-Daten aufbewahrt werden, Benutzer einbezieht, und Sie ein Postfach eines in diese Richtlinie einbezogenen Benutzers löschen, wird es in ein [inaktives Postfach](inactive-mailboxes-in-office-365.md) konvertiert, damit die Teams-Daten aufbewahrt werden. Wenn diese Microsoft Teams-Daten für den Benutzer nicht aufbewahrt werden müssen, schließen Sie das Benutzerkonto aus der Aufbewahrungsrichtlinie aus, bevor Sie das Postfach löschen.

Nachdem eine Aufbewahrungsrichtlinie für Chat- oder Kanalnachrichten konfiguriert wurde, sind die Inhaltspfade davon abhängig, ob die Aufbewahrungsrichtlinie der Aufbewahrung und dem Löschen, der reinen Aufbewahrung oder dem reinen Löschen dient.

Wenn die Aufbewahrungsrichtlinie dem Aufbewahren und Löschen dient:

![Diagramm des Aufbewahrungsflusses für Microsoft Teams-Chat- und Kanalnachrichten](../media/TeamsRetentionLifecycle.png)

1. **Wenn eine Chat- oder Kanalnachricht während des Aufbewahrungszeitraums vom Benutzer geändert oder gelöscht wird**, wird die Nachricht in den Ordner "SubstrateHolds" (ein ausgeblendeter Ordner in jedem Benutzer- oder Gruppenpostfach) verschoben bzw. bei Änderungen kopiert und bis zum Ablauf des Aufbewahrungszeitraums dort gespeichert. Nachrichten werden am Tag des Ablaufs des Aufbewahrungszeitraums dauerhaft gelöscht.

2. **Wenn eine Chat- oder Kanalnachricht während des Aufbewahrungszeitraums nicht gelöscht wird**, wird die Nachricht innerhalb eines Tages nach Ablauf des Aufbewahrungszeitraums in den Ordner "SubstrateHolds" verschoben (dies erfolgt innerhalb 0 bis 24 Stunden). Die Nachricht wird einen Tag, nachdem sie in den Ordner "SubstrateHolds" verschoben wurde, dauerhaft gelöscht. 

> [!NOTE]
> Nachrichten im Ordner "SubstrateHolds" können mit eDiscovery-Tools durchsucht werden. Nachdem eine Nachricht dauerhaft gelöscht wurde, wird sie nicht mehr in eDiscovery-Suchen zurückgegeben.

Wenn die Aufbewahrungsrichtlinie dem reinen Aufbewahren oder dem reinen Löschen dient, stellen die Inhaltspfade Varianten von Aufbewahren und Löschen dar.

### <a name="content-paths-for-retain-only-retention-policy"></a>Inhaltspfade für rein aufbewahrende Aufbewahrungsrichtlinien

1. **Wenn eine Chat- oder Kanalnachricht während des Aufbewahrungszeitraums geändert oder gelöscht wird**: Eine Kopie der ursprünglichen Nachricht wird im Ordner "SubstrateHolds" erstellt und bis zum Ende des Aufbewahrungszeitraums aufbewahrt, wo dann die Kopie im Ordner "SubstrateHolds" einen Tag nach Ablauf des Elements endgültig gelöscht wird. 

2. **Wenn das Element während des Aufbewahrungszeitraums nicht geändert oder gelöscht wird**: Weder vor noch nach dem Aufbewahrungszeitraum passiert etwas. Die Nachricht verbleibt an ihrem Ursprungsort.

### <a name="content-paths-for-delete-only-retention-policy"></a>Inhaltspfade für Aufbewahrungsrichtlinien für reines Löschen

1. **Wenn die Nachricht während des Aufbewahrungszeitraums nicht gelöscht wird**: Die Nachricht wird am Ende des Aufbewahrungszeitraums in den Ordner "SubstrateHolds" verschoben. 

2. **Wenn das Element während des Aufbewahrungszeitraums vom Benutzer gelöscht wird**, wird das Element sofort in den Ordner "SubstrateHolds" verschoben. Wenn ein Benutzer die Nachricht dort löscht oder den Ordner "SubstrateHolds" leert, wird sie endgültig gelöscht. Andernfalls wird die Nachricht einen Tag, nachdem sie sich im Ordner "SubstrateHolds" befindet, dauerhaft gelöscht.


## <a name="skype-for-business-and-teams-interop-chats"></a>Interop-Chats in Skype for Business und Microsoft Teams

Wenn ein Skype for Business Online-Chat in Microsoft Teams eintrifft, wird er zu einer Nachricht in einem Teams-Chatthread und in das entsprechende Postfach aufgenommen. Aufbewahrungsrichtlinien werden auf diese Nachrichten aus dem Microsoft Teams-Thread angewendet. 

Wenn jedoch der Unterhaltungsverlauf für Skype for Business Online aktiviert ist, und dieser Verlauf von der Skype for Business Online-Clientseite aus in einem Postfach gespeichert wird, werden diese Chatdaten nicht von einer Aufbewahrungsrichtlinie für Microsoft Teams verarbeitet. Verwenden Sie für diesen Inhalt eine für Skype for Business konfigurierte Aufbewahrungsrichtlinie.

## <a name="meetings-and-external-users"></a>Besprechungen und externe Benutzer

Kanal-Besprechungsnachrichten werden auf die gleiche Weise wie Kanalnachrichten gespeichert, wählen Sie für diese Daten also den Speicherort **Teams-Kanalnachrichten** aus, wenn Sie Ihre Aufbewahrungsrichtlinie konfigurieren.

Spontane Besprechungsnachrichten werden auf die gleiche Weise wie Gruppenchatnachrichten gespeichert, wählen Sie für diese Daten also den Speicherort **Teams-Chats** aus, wenn Sie Ihre Aufbewahrungsrichtlinie konfigurieren.

Wenn externe Benutzer in eine von Ihrer Organisation gehosteten Besprechung einbezogen werden:

- Wenn ein externer Benutzer über ein Gastkonto in Ihrem Mandanten beitritt, verfügt er über ein Schattenpostfach, das u. U. der Aufbewahrungsrichtlinie Ihrer Organisation für Microsoft Teams unterliegt. Alle Nachrichten aus der Besprechung werden sowohl im Postfach der Benutzer als auch im Schattenpostfach gespeichert. 

- Wenn ein externer Benutzer über ein Konto einer anderen Microsoft 365-Organisation beitritt, können Ihre Aufbewahrungsrichtlinien keine Nachrichten für diesen Benutzer löschen, weil sie im Postfach dieses Benutzers in einem anderen Mandanten gespeichert sind. Hinsichtlich der selben Besprechung können Ihre Aufbewahrungsrichtlinien jedoch Nachrichten für Ihre Benutzer löschen.

## <a name="when-a-user-leaves-the-organization"></a>Wenn ein Benutzer die Organisation verlässt 

Wenn ein Benutzer Ihre Organisation verlässt und das Microsoft 365-Konto gelöscht wird, werden Ihre Chatnachrichten, die der Aufbewahrung unterliegen, in einem inaktiven Postfach gespeichert. Die Chatnachrichten unterliegenweiterhin der Aufbewahrungsrichtlinie, die dem Benutzer zugewiesen wurde, bevor sein Postfach inaktiv wurde, und die Inhalte sind für eine eDiscovery-Suche verfügbar. Weitere Informationen finden Sie unter [Inaktive Postfächer in Exchange Online](inactive-mailboxes-in-office-365.md). 

Wenn der Benutzer Dateien in Teams gespeichert hat, lesen Sie den Abschnitt [Äquivalent](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) für SharePoint und OneDrive.

## <a name="limitations"></a>Einschränkungen

Wir arbeiten kontinuierlich an der Verbesserung der Aufbewahrungsfunktionen in Microsoft Teams. Es gibt einige Einschränkungen, die Sie beachten sollten, wenn Sie die Aufbewahrung von Nachrichten und Chats für Teams-Kanäle verwenden:
  
- **Microsoft Teams erfordert eine separate Aufbewahrungsrichtlinie**. Wenn Sie eine Aufbewahrungsrichtlinie erstellen und den Microsoft Teams-Speicherort aktivieren, werden alle anderen Speicherorte deaktiviert. Eine Aufbewahrungsrichtlinie, die Microsoft Teams umfasst, darf nur Microsoft Teams und keine anderen Speicherorte betreffen.

- **Microsoft Teams ist nicht in einer organisationsweiten Richtlinie eingeschlossen**. Wenn Sie eine organisationsweite Richtlinie erstellen, sind Teams-Kanal-Nachrichten und Teams-Chats nicht enthalten, da diese eine separate Aufbewahrungsrichtlinie erfordern.

- **Microsoft Teams unterstützt nicht die erweiterte Archivierung**. Wenn Sie beim Erstellen einer Aufbewahrungsrichtlinie die [erweiterten Einstellungen zum Ermitteln von Inhalten, die bestimmte Bedingungen erfüllen](create-retention-policies.md#advanced-settings-to-identify-content-that-meets-specific-conditions), auswählen, sind die Microsoft Teams-Speicherorte nicht verfügbar. Derzeit gilt die Aufbewahrung in Microsoft Teams für alle Chat- und Kanalnachrichteninhalte, wenn Sie diese Speicherorte auswählen.

- **Wenn Sie eine Aufbewahrungsrichtlinie für Microsoft Teams-Kanalnachrichten konfigurieren, werden Microsoft Teams-Nachrichten in privaten Kanälen nicht einbezogen**. Zurzeit werden private Kanäle von Aufbewahrungsrichtlinien nicht unterstützt. 

- **Es kann bis zu sieben Tage dauern, bis abgelaufene Nachrichten in Microsoft Teams gelöscht sind**. Eine auf Microsoft Teams angewendete Aufbewahrungsrichtlinie löscht Chat- und Kanalnachrichten, wenn der entsprechende Aufbewahrungszeitraum abgelaufen ist. Es kann jedoch zwischen drei und sieben Tage dauern, bis diese Nachrichten bereinigt und dauerhaft gelöscht sind. Außerdem können Chat- und Kanalnachrichten mit eDiscovery-Tools nach Ablauf des Aufbewahrungszeitraums und nach deren dauerhafter Löschung durchsucht werden.
    
    > [!NOTE]
    > Es stimmte zwar, dass eine Aufbewahrungsrichtlinie keine Microsoft Teams-Inhalte löschen konnte, die weniger als 30 Tage alt waren, wir haben diese Einschränkung jedoch aufgehoben. Jetzt kann der Aufbewahrungszeitraum für Microsoft Teams-Inhalte eine beliebige Anzahl von Tagen umfassen, auch nur einen einzigen Tag. Bei einem Aufbewahrungszeitraum von nur einem Tag dauert es bis zu sieben Tage nach Ablauf dieses Zeitraums, bevor Nachrichten endgültig gelöscht werden.

- **Falsche Anzeige in Outlook**. Wenn Sie Aufbewahrungsrichtlinien für Skype- oder Microsoft Teams-Speicherorte erstellen, wird eine dieser Richtlinien als Standard-Ordnerrichtlinie angezeigt, wenn ein Benutzer die Eigenschaften eines Postfachordners im Outlook Desktop-Client einsieht. Hierbei handelt es sich um ein Anzeigeproblem in Outlook und [ein bekanntes Problem](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies). Als Standard-Ordnerrichtlinie sollte die Aufbewahrungsrichtlinie für Postfächer, die für den Ordner gilt, angezeigt werden. Die Aufbewahrungsrichtlinie für Skype oder Microsoft Teams wird nicht auf das Postfach des Benutzers angewendet.

- **Konfigurationsprobleme**: 
    - Wenn Sie die Option **Teams auswählen** für den Speicherort **Microsoft Teams-Kanalnachrichten** auswählen, werden möglicherweise Microsoft 365-Gruppen angezeigt, die nicht auch Teams sind. Wählen Sie diese Gruppen nicht aus.
    
    - Wenn Sie **Benutzer auswählen** für den Speicherort ** Teams-Chats** auswählen, werden möglicherweise Gäste und Nicht Postfachbenutzer angezeigt. Aufbewahrungsrichtlinien sind nicht auf diese Benutzer ausgerichtet, deshalb sollten Sie sie nicht auswählen.

## <a name="configuration-guidance"></a>Konfigurationsleitfaden

Wenn Sie die Aufbewahrung in Microsoft 365 konfigurieren möchten, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezecihnungen](get-started-with-retention.md).
