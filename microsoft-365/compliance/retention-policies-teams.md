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
ms.openlocfilehash: 04ca027b9ce8ad1b36e0d4e60c4e10308a822a63
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816738"
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

Nachdem eine Aufbewahrungsrichtlinie für Chat- und Kanalnachrichten konfiguriert wurde, wertet ein Timer-Job des Exchange-Dienstes regelmäßig Elemente im verborgenen Ordner aus, in dem diese Teams-Nachrichten gespeichert sind. Die Ausführung des Timer-Jobs dauert bis zu sieben Tage. Wenn die Aufbewahrungszeit für die Elemente abgelaufen ist, werden sie in den Ordner SubstrateHolds verschoben – einen weiteren versteckten Ordner, der sich im Postfach von Benutzenden oder Gruppen befindet, um "vorläufig gelöschte" Elemente zu speichern, bevor sie endgültig gelöscht werden.

Nachdem eine Aufbewahrungsrichtlinie für Chat- oder Kanalnachrichten konfiguriert wurde, sind die Inhaltspfade davon abhängig, ob die Aufbewahrungsrichtlinie beibehalten und dann gelöscht, nur beibehalten oder nur gelöscht werden soll.

Wenn die Aufbewahrungsrichtlinie lautet beibehalten und dann löschen:

![Diagramm des Aufbewahrungsflusses für Microsoft Teams-Chat- und Kanalnachrichten](../media/teamsretentionlifecycle.png)

Für die zwei Pfade im Diagramm:

1. **Wenn eine Chat- oder Kanalnachricht während der Aufbewahrungsfrist vom Benutzer bearbeitet oder gelöscht wird**, wird die Originalnachricht sofort in den Ordner SubstrateHolds kopiert (falls bearbeitet) oder verschoben (falls gelöscht). Die Nachricht wird dort bis zum Ablauf der Aufbewahrungsfrist gespeichert und dann innerhalb von 24 Stunden endgültig gelöscht.

2. **Wenn eine Chat- oder Kanalnachricht nicht gelöscht wird** und aktuelle Nachrichten nach der Bearbeitung, wird die Nachricht nach Ablauf der Aufbewahrungsfrist in den Ordner SubstrateHolds verschoben. Diese Aktion dauert bis zu sieben Tage ab dem Ablaufdatum. Wenn sich die Nachricht im Ordner SubstrateHolds befindet, wird sie innerhalb von 24 Stunden endgültig gelöscht. 

> [!NOTE]
> Nachrichten im Ordner SubstrateHolds können mit eDiscovery-Tools durchsucht werden. Solange Nachrichten nicht endgültig gelöscht sind (im Ordner SubstrateHolds), bleiben sie mit eDiscovery-Tools durchsuchbar.

Wenn die Aufbewahrungsrichtlinie dem reinen Aufbewahren oder dem reinen Löschen dient, stellen die Inhaltspfade Varianten von Aufbewahren und Löschen dar.

### <a name="content-paths-for-retain-only-retention-policy"></a>Inhaltspfade für rein aufbewahrende Aufbewahrungsrichtlinien

1. **Wenn eine Chat- oder Kanalnachricht bearbeitet oder gelöscht wird**: Eine Kopie der Originalnachricht wird sofort im Ordner SubstrateHolds erstellt und dort bis zum Ablauf der Aufbewahrungsfrist aufbewahrt. Die Nachricht wird innerhalb von 24 Stunden dauerhaft aus dem Ordner SubstrateHolds gelöscht.

2. **Wenn das Element nicht geändert oder gelöscht wird** und aktuelle Nachrichten nach der Bearbeitung während der Aufbewahrungsfrist: Vor und nach der Aufbewahrungsfrist geschieht nichts; die Nachricht bleibt an ihrem ursprünglichen Ort.

### <a name="content-paths-for-delete-only-retention-policy"></a>Inhaltspfade für Aufbewahrungsrichtlinien für reines Löschen

1. **Wenn die Nachricht während des Aufbewahrungszeitraums nicht gelöscht wird**: Die Nachricht wird am Ende des Aufbewahrungszeitraums in den Ordner "SubstrateHolds" verschoben. Diese Aktion dauert bis zu sieben Tage ab dem Ablaufdatum. Die Nachricht wird innerhalb von 24 Stunden dauerhaft aus dem Ordner SubstrateHolds gelöscht.

2. **Wenn das Element während des Zeitraums vom Benutzer gelöscht wird**, wird das Element sofort in den Ordner SubstrateHolds verschoben, wo es innerhalb von 24 Stunden endgültig gelöscht wird.


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

- **Wenn Sie eine Aufbewahrungsrichtlinie für Microsoft Teams-Kanalnachrichten konfigurieren, werden Microsoft Teams-Nachrichten in privaten Kanälen nicht einbezogen**. Zurzeit werden private Kanäle von Aufbewahrungsrichtlinien nicht unterstützt. 

- **Für Teams Chat- und Kanalnachrichten werden „gefällt mir“-Angaben und andere Reaktionen nicht gespeichert**. Reaktionen von anderen in Form von Emoticons werden durch Aufbewahrungsrichtlinien nicht unterstützt.

- **Falsche Anzeige in Outlook**. Wenn Sie Aufbewahrungsrichtlinien für Skype- oder Microsoft Teams-Speicherorte erstellen, wird eine dieser Richtlinien als Standard-Ordnerrichtlinie angezeigt, wenn ein Benutzer die Eigenschaften eines Postfachordners im Outlook Desktop-Client einsieht. Hierbei handelt es sich um ein Anzeigeproblem in Outlook und [ein bekanntes Problem](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies). Als Standard-Ordnerrichtlinie sollte die Aufbewahrungsrichtlinie für Postfächer, die für den Ordner gilt, angezeigt werden. Die Aufbewahrungsrichtlinie für Skype oder Microsoft Teams wird nicht auf das Postfach des Benutzers angewendet.

- **Konfigurationsprobleme**: 
    - Wenn Sie die Option **Teams auswählen** für den Speicherort **Microsoft Teams-Kanalnachrichten** auswählen, werden möglicherweise Microsoft 365-Gruppen angezeigt, die nicht auch Teams sind. Wählen Sie diese Gruppen nicht aus.
    
    - Wenn Sie **Benutzer auswählen** für den Speicherort ** Teams-Chats** auswählen, werden möglicherweise Gäste und Nicht Postfachbenutzer angezeigt. Aufbewahrungsrichtlinien sind nicht auf diese Benutzer ausgerichtet, deshalb sollten Sie sie nicht auswählen.

## <a name="configuration-guidance"></a>Konfigurationsleitfaden

Wenn Sie die Konfiguration der Datenaufbewahrung in Microsoft 365 zum ersten Mal durchführen möchten, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).

Wenn Sie bereit sind, eine Aufbewahrungsrichtlinie für Teams zu erstellen, lesen Sie [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](create-retention-policies.md).
