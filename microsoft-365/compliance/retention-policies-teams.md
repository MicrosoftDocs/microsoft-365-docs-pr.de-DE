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
ms.openlocfilehash: cc17f89da743afce0d64b45f96493c050e61e343
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408360"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>Informationen zur Aufbewahrung für Microsoft Teams

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Wenn Sie in Teams eine Nachricht angezeigt wird, die besagt, dass Ihre Chats oder Nachrichten durch eine Aufbewahrungsrichtlinie gelöscht wurden, lesen Sie [Teamnachrichten zu Aufbewahrungsrichtlinien](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).
> 
> Die Informationen auf dieser Seite richten sich an IT-Administratoren, die diese Aufbewahrungsrichtlinien verwalten.

Die Informationen in diesem Artikel ergänzen den Beitrag [Informationen zur Aufbewahrung](retention.md), da es sich um spezifische Informationen für Microsoft Teams-Nachrichten handelt.

Informationen zu anderen Arbeitsbereichen finden Sie unter:

- [Informationen zur Aufbewahrung für SharePoint und OneDrive](retention-policies-sharepoint.md)
- [Informationen zur Aufbewahrung für Yammer](retention-policies-yammer.md)
- [Informationen zur Aufbewahrung für Exchange](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>Lieferumfang für Aufbewahrung und Löschung

Team-Chat-Nachrichten und Kanalnachrichten können mithilfe von Aufbewahrungsrichtlinien für Teams gelöscht werden. Zusätzlich zum Text in den Nachrichten können die folgenden Elemente aus Compliance-Gründen beibehalten werden: Eingebettete Bilder, Tabellen, Hypertext-Links und Links zu anderen Teams-Nachrichten und Dateien und [Karteninhalt](/microsoftteams/platform/task-modules-and-cards/what-are-cards). Chatnachrichten umfassen alle Namen der Personen im Chat, und Kanalmeldungen umfassen den Teamnamen und den Nachrichtentitel (sofern vorhanden). 

> [!NOTE]
> Die Einbindung von Karteninhalten ist eine neue Funktion, die Mandanten nun vollständig zur Verfügung gestellt ist. Weitere Informationen finden Sie unter [Microsoft 365 Compliance-Funktionen für adaptive Karteninhalte über Apps in Teams jetzt verfügbar](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869).

Teams-Nachrichten in privaten Kanälen werden für Aufbewahrungsrichtlinien derzeit nicht unterstützt. Codeausschnitte, aufgezeichnete Sprachnotizen vom Mobile Microsoft Teams-Clients, Miniaturansichten, Ankündigungsbilder und Reaktionen anderer in Form von Emoticons sind nicht beibehalten, wenn Sie Aufbewahrungsrichtlinien für Teams verwenden.

E-Mails und Dateien, die Sie mit Teams verwenden, sind in den Aufbewahrungsrichtlinien für Teams nicht beinhaltet. Diese Elemente haben ihre eigenen Aufbewahrungsrichtlinien.

## <a name="how-retention-works-with-microsoft-teams"></a>Funktionsweise der Aufbewahrung mit Microsoft Teams

Sie können eine Aufbewahrungsrichtlinie verwenden, um Daten aus Chats und Kanalnachrichten in Teams zu speichern und diese Chats und Nachrichten zu löschen. Hinter den Kulissen werden Exchange-Postfächer verwendet, um Daten aus diesen Nachrichten zu speichern. Daten von Teams-Chats werden in einem verborgenen Ordner im Postfach jedes Benutzers gespeichert, der am Chat teilnimmt. Ein ähnlicher verborgener Ordner im Gruppenpostfach wird für Teams-Kanalnachrichten genutzt.

Diese Postfächer sind nach ihrem Attribut "RecipientTypeDetails" aufgelistet:

- **MailUser**: In diesen Postfächern werden Nachrichtendaten für Cloud-basierte Teambenutzer gespeichert.
- **UserMailbox**: In diesen Postfächern werden Nachrichtendaten für [lokale Teams-Benutzer](search-cloud-based-mailboxes-for-on-premises-users.md) gespeichert.
- **GroupMailbox**: In diesen Postfächern werden Nachrichtendaten für Teams-Kanäle gespeichert.

Andere Postfachtypen, z. B. RoomMailbox, die für Teams-Konferenzräume verwendet werden, werden für Teams-Aufbewahrungsrichtlinien nicht unterstützt.

Es ist wichtig zu verstehen, dass Teams einen Azure-basierten Chat-Dienst als primären Speicher für alle Nachrichten (Chats und Kanalnachrichten) verwendet. Standardmäßig speichert dieser Dienst die Daten auf unbestimmte Zeit. Wenn Sie aus Compliance-Gründen Teams-Nachrichten löschen müssen, empfehlen wir aus diesem Grund, Aufbewahrungsrichtlinien für Teams zu verwenden, die Nachrichten nach einem bestimmten Zeitraum löschen können, je nachdem, wann sie erstellt wurden. Nachrichten werden dann dauerhaft sowohl aus den Exchange-Postfächern als auch aus dem zugrunde liegenden Chat-Dienst mit Azure-Unterstützung gelöscht. Weitere Informationen über die zugrunde liegende Architektur finden Sie unter [Sicherheit und Compliance in Microsoft Teams](/MicrosoftTeams/security-compliance-overview), insbesondere im Abschnitt [Information Protection-Architektur](/MicrosoftTeams/security-compliance-overview#information-protection-architecture).

Obwohl Daten aus Teams-Chats und -Kanalnachrichten in Postfächern gespeichert sind, werden diese Daten nur von einer Aufbewahrungsrichtlinie eingeschlossen, die für die Speicherorte von **Teams-Kanalnachrichten** und **Teams-Chats** konfiguriert ist. Aufbewahrungsrichtlinien, die für Postfächer von Exchange-Benutzern oder Gruppen konfiguriert sind, wirken sich nicht auf Teams-Chats und -Kanalnachrichten aus.

> [!NOTE]
> Wenn ein Benutzer in einer aktiven Aufbewahrungsrichtlinie enthalten ist, in der Teams-Nachrichten gespeichert sind, und Sie ein Postfach eines Benutzers löschen, der in dieser Richtlinie enthalten ist, wird das Postfach in ein [inaktives Postfach](inactive-mailboxes-in-office-365.md) konvertiert, um die Teams-Daten beizubehalten. Wenn diese Microsoft Teams-Daten für den Benutzer nicht aufbewahrt werden müssen, schließen Sie das Benutzerkonto aus der Aufbewahrungsrichtlinie aus, bevor Sie das Postfach löschen.

Nachdem eine Aufbewahrungsrichtlinie für Chat- und Kanalnachrichten konfiguriert wurde, wertet ein Timer-Job des Exchange-Dienstes regelmäßig Elemente im verborgenen Ordner aus, in dem diese Teams-Nachrichten gespeichert sind. Die Ausführung des Timer-Jobs dauert bis zu sieben Tage. Wenn die Aufbewahrungszeit für die Elemente abgelaufen ist, werden sie in den Ordner SubstrateHolds verschoben – einen weiteren versteckten Ordner, der sich im Postfach von Benutzenden oder Gruppen befindet, um "vorläufig gelöschte" Elemente zu speichern, bevor sie endgültig gelöscht werden.

Nachdem eine Aufbewahrungsrichtlinie für Chat- oder Kanalnachrichten konfiguriert wurde, sind die Inhaltspfade davon abhängig, ob die Aufbewahrungsrichtlinie beibehalten und dann gelöscht, nur beibehalten oder nur gelöscht werden soll.

Wenn die Aufbewahrungsrichtlinie lautet beibehalten und dann löschen:

![Diagramm des Aufbewahrungsflusses für Microsoft Teams-Chat- und Kanalnachrichten](../media/teamsretentionlifecycle.png)

Zu den zwei Pfaden im Diagramm:

1. **Wenn eine Chat- oder Kanalnachricht während der Aufbewahrungsfrist vom Benutzer bearbeitet oder gelöscht wird**, wird die Originalnachricht innerhalb von 21 Tagen in den Ordner SubstrateHolds kopiert (falls bearbeitet) oder verschoben (falls gelöscht). Die Nachricht wird dort bis zum Ablauf der Aufbewahrungsfrist gespeichert und dann innerhalb von 24 Stunden endgültig gelöscht.

2. **Wenn eine Chat- oder Kanalnachricht nicht gelöscht wird** und aktuelle Nachrichten nach der Bearbeitung, wird die Nachricht nach Ablauf der Aufbewahrungsfrist in den Ordner SubstrateHolds verschoben. Diese Aktion dauert bis zu sieben Tage ab dem Ablaufdatum. Wenn sich die Nachricht im Ordner SubstrateHolds befindet, wird sie innerhalb von 24 Stunden endgültig gelöscht. 

> [!NOTE]
> Nachrichten im Ordner SubstrateHolds können mit eDiscovery-Tools durchsucht werden. Solange Nachrichten nicht endgültig aus diesem SubstrateHolds-Ordner gelöscht sind, bleiben sie mit eDiscovery-Tools durchsuchbar.

Wenn die Aufbewahrungsrichtlinie dem reinen Aufbewahren oder dem reinen Löschen dient, stellen die Inhaltspfade Varianten von Aufbewahren und Löschen dar.

### <a name="content-paths-for-retain-only-retention-policy"></a>Inhaltspfade für rein aufbewahrende Aufbewahrungsrichtlinien

1. **Wenn eine Chat- oder Kanalnachricht bearbeitet oder gelöscht wird**: Eine Kopie der Originalnachricht wird innerhalb von 21 Tagen im Ordner SubstrateHolds erstellt und dort bis zum Ablauf der Aufbewahrungsfrist aufbewahrt. Die Nachricht wird innerhalb von 24 Stunden dauerhaft aus dem Ordner SubstrateHolds gelöscht.

2. **Wenn das Element nicht geändert oder gelöscht wird** und aktuelle Nachrichten nach der Bearbeitung während der Aufbewahrungsfrist: Vor und nach der Aufbewahrungsfrist geschieht nichts; die Nachricht bleibt an ihrem ursprünglichen Ort.

### <a name="content-paths-for-delete-only-retention-policy"></a>Inhaltspfade für Aufbewahrungsrichtlinien für reines Löschen

1. **Wenn die Nachricht während des Aufbewahrungszeitraums nicht gelöscht wird**: Die Nachricht wird am Ende des Aufbewahrungszeitraums in den Ordner "SubstrateHolds" verschoben. Diese Aktion dauert bis zu sieben Tage ab dem Ablaufdatum. Die Nachricht wird innerhalb von 24 Stunden dauerhaft aus dem Ordner SubstrateHolds gelöscht.

2. **Wenn das Element während des Zeitraums vom Benutzer gelöscht wird**, wird das Element innerhalb von 21 Tagen in den Ordner SubstrateHolds verschoben, wo es dann innerhalb von 24 Stunden endgültig gelöscht wird.


## <a name="skype-for-business-and-teams-interop-chats"></a>Interop-Chats in Skype for Business und Microsoft Teams

Wenn ein Skype for Business Online-Chat in Microsoft Teams eintrifft, wird er zu einer Nachricht in einem Teams-Chatthread und in das entsprechende Postfach aufgenommen. Aufbewahrungsrichtlinien werden auf diese Nachrichten aus dem Microsoft Teams-Thread angewendet. 

Wenn jedoch der Unterhaltungsverlauf für Skype for Business Online aktiviert ist, und dieser Verlauf von der Skype for Business Online-Clientseite aus in einem Postfach gespeichert wird, werden diese Chatdaten nicht von einer Aufbewahrungsrichtlinie für Microsoft Teams verarbeitet. Verwenden Sie für diesen Inhalt eine für Skype for Business konfigurierte Aufbewahrungsrichtlinie.

## <a name="meetings-and-external-users"></a>Besprechungen und externe Benutzer

Kanal-Besprechungsnachrichten werden auf die gleiche Weise wie Kanalnachrichten gespeichert, wählen Sie für diese Daten also den Speicherort **Teams-Kanalnachrichten** aus, wenn Sie Ihre Aufbewahrungsrichtlinie konfigurieren.

Nachrichten spontaner und geplanter Besprechungen werden auf die gleiche Weise wie Gruppenchatnachrichten gespeichert. Wählen Sie für diese Daten also den Speicherort **Teams-Chats** aus, wenn Sie Ihre Aufbewahrungsrichtlinie konfigurieren.

Wenn externe Benutzer in eine von Ihrer Organisation gehosteten Besprechung einbezogen werden:

- Wenn ein externer Benutzer über ein Gastkonto in Ihrem Mandanten beitritt, verfügt er über ein Schattenpostfach, das u. U. der Aufbewahrungsrichtlinie Ihrer Organisation für Microsoft Teams unterliegt. Alle Nachrichten aus der Besprechung werden sowohl im Postfach der Benutzer als auch im Schattenpostfach gespeichert. 

- Wenn ein externer Benutzer über ein Konto einer anderen Microsoft 365-Organisation beitritt, können Ihre Aufbewahrungsrichtlinien keine Nachrichten für diesen Benutzer löschen, weil sie im Postfach dieses Benutzers in einem anderen Mandanten gespeichert sind. Hinsichtlich der selben Besprechung können Ihre Aufbewahrungsrichtlinien jedoch Nachrichten für Ihre Benutzer löschen.

## <a name="when-a-user-leaves-the-organization"></a>Wenn ein Benutzer die Organisation verlässt 

Wenn ein Benutzer, der ein Postfach in Exchange Online hat, Ihre Organisation verlässt und das Microsoft 365-Konto gelöscht wird, werden die Chatnachrichten, die der Aufbewahrung unterliegen, in einem inaktiven Postfach gespeichert. Die Chatnachrichten unterliegenweiterhin der Aufbewahrungsrichtlinie, die dem Benutzer zugewiesen wurde, bevor sein Postfach inaktiv wurde, und die Inhalte sind für eine eDiscovery-Suche verfügbar. Weitere Informationen finden Sie unter [Inaktive Postfächer in Exchange Online](inactive-mailboxes-in-office-365.md). 

Wenn der Benutzer Dateien in Teams gespeichert hat, lesen Sie den Abschnitt [Äquivalent](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) für SharePoint und OneDrive.

## <a name="limitations"></a>Einschränkungen

Wir arbeiten kontinuierlich an der Verbesserung der Aufbewahrungsfunktionen in Microsoft Teams. Es gibt einige Einschränkungen, die Sie beachten sollten, wenn Sie die Aufbewahrung von Nachrichten und Chats für Teams-Kanäle verwenden:

- **Falsche Anzeige in Outlook**. Wenn Sie Aufbewahrungsrichtlinien für Skype- oder Microsoft Teams-Speicherorte erstellen, wird eine dieser Richtlinien als Standard-Ordnerrichtlinie angezeigt, wenn ein Benutzer die Eigenschaften eines Postfachordners im Outlook Desktop-Client einsieht. Hierbei handelt es sich um ein Anzeigeproblem in Outlook und [ein bekanntes Problem](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies). Als Standard-Ordnerrichtlinie sollte die Aufbewahrungsrichtlinie für Postfächer, die für den Ordner gilt, angezeigt werden. Die Aufbewahrungsrichtlinie für Skype oder Microsoft Teams wird nicht auf das Postfach des Benutzers angewendet.

- **Konfigurationsprobleme**: 
    - Wenn Sie die Option **Teams auswählen** für den Speicherort **Microsoft Teams-Kanalnachrichten** auswählen, werden möglicherweise Microsoft 365-Gruppen angezeigt, die nicht auch Teams sind. Wählen Sie diese Gruppen nicht aus.
    
    - Wenn Sie **Benutzer auswählen** für den Speicherort **Teams-Chats** auswählen, werden möglicherweise Gäste und Nicht Postfachbenutzer angezeigt. Aufbewahrungsrichtlinien sind nicht auf diese Benutzer ausgerichtet, deshalb sollten Sie sie nicht auswählen.

## <a name="configuration-guidance"></a>Konfigurationsleitfaden

Wenn Sie die Konfiguration der Datenaufbewahrung in Microsoft 365 zum ersten Mal durchführen möchten, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).

Wenn Sie bereit sind, eine Aufbewahrungsrichtlinie für Teams zu erstellen, lesen Sie [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](create-retention-policies.md).