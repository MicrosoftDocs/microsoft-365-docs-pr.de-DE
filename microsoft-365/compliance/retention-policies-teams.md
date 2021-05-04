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
ms.openlocfilehash: b7bc84307f0db580995e039618cb01d25d6ecd66
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932858"
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

Teams-Chatnachrichten und -Kanalnachrichten können mithilfe von Aufbewahrungsrichtlinien für Teams gelöscht werden. Zusätzlich zum Text in den Nachrichten können die folgenden Elemente aus Compliance-Gründen beibehalten werden: Eingebettete Bilder, Tabellen, Hypertext-Links, Links zu anderen Teams-Nachrichten und Dateien und [Karteninhalt](/microsoftteams/platform/task-modules-and-cards/what-are-cards). Chatnachrichten umfassen alle Namen der Personen im Chat, und Kanalmeldungen umfassen den Teamnamen und den Nachrichtentitel (sofern vorhanden). 

> [!NOTE]
> Die Einbeziehung von Karteninhalten in eine Aufbewahrungsrichtlinie für Teams ist eine relativ neue Ergänzung. Weitere Informationen finden Sie unter [Microsoft 365 Compliance-Funktionen für adaptive Karteninhalte über Apps in Teams jetzt verfügbar](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869).

Teams-Nachrichten in privaten Kanälen werden derzeit nicht für Aufbewahrungsrichtlinien unterstützt. Codeausschnitte, aufgezeichnete Sprachnotizen vom Mobile Microsoft Teams-Clients, Miniaturansichten, Ankündigungsbilder und Reaktionen anderer in Form von Emoticons sind nicht beibehalten, wenn Sie Aufbewahrungsrichtlinien für Teams verwenden.

E-Mails und Dateien, die Sie mit Teams verwenden, sind in den Aufbewahrungsrichtlinien für Teams nicht beinhaltet. Diese Elemente haben ihre eigenen Aufbewahrungsrichtlinien.

## <a name="how-retention-works-with-microsoft-teams"></a>Funktionsweise der Aufbewahrung mit Microsoft Teams

Verwenden Sie diesen Abschnitt, um zu verstehen, wie Complianceanforderungen durch Back-End-Speicher und -Prozesse erfüllt werden, und sollten von eDiscovery-Tools anstelle von Nachrichten überprüft werden, die aktuell in der Teams-App angezeigt werden.

Sie können eine Aufbewahrungsrichtlinie verwenden, um Daten aus Chats und Kanalnachrichten in Teams zu speichern und diese Chats und Nachrichten zu löschen. Hinter den Kulissen werden Exchange-Postfächer verwendet, um die aus diesen Nachrichten kopierten Daten zu speichern. Daten von Teams-Chats werden in einem verborgenen Ordner im Postfach jedes Benutzers gespeichert, der am Chat teilnimmt. Ein ähnlicher verborgener Ordner im Gruppenpostfach wird für Teams-Kanalnachrichten genutzt. Diese ausgeblendeten Ordner sind nicht für den direkten Zugriff von Benutzern oder Administratoren gedacht, sondern zum Speichern von Daten, die Complianceadministratoren mit eDiscovery-Tools durchsuchen können.

Diese Postfächer sind nach ihrem Attribut "RecipientTypeDetails" aufgelistet:

- **UserMailbox**: In diesen Postfächern werden Nachrichtendaten für cloudbasierte Teams-Benutzer gespeichert.
- **MailUser**: In diesen Postfächern werden Nachrichtendaten für [lokale Teams-Benutzer](search-cloud-based-mailboxes-for-on-premises-users.md) gespeichert.
- **GroupMailbox**: In diesen Postfächern werden Nachrichtendaten für Teams-Kanäle gespeichert.

Andere Postfachtypen, z. B. RoomMailbox, die für Teams-Konferenzräume verwendet werden, werden für Teams-Aufbewahrungsrichtlinien nicht unterstützt.

Teams verwendet einen Azure-unterstützten Chatdienst als primären Speicher für alle Nachrichten (Chats und Kanalnachrichten). Wenn Sie aus Compliance-Gründen Teams-Nachrichten löschen müssen, können Aufbewahrungsrichtlinien für Teams die Nachrichten nach einem bestimmten Zeitraum löschen, je nachdem, wann sie erstellt wurden. Nachrichten werden dann sowohl aus den Exchange-Postfächern, in denen sie für Compliancevorgänge gespeichert wurden, als auch aus dem primären Speicher gelöscht, der vom zugrunde liegenden Azure-unterstützten Chatdienst verwendet wird. Weitere Informationen über die zugrunde liegende Architektur finden Sie unter [Sicherheit und Compliance in Microsoft Teams](/MicrosoftTeams/security-compliance-overview), insbesondere im Abschnitt [Information Protection-Architektur](/MicrosoftTeams/security-compliance-overview#information-protection-architecture).

Obwohl diese Daten aus Teams-Chats und -Kanalnachrichten in Postfächern gespeichert sind, müssen Sie eine Aufbewahrungsrichtlinie für die Speicherorte von **Teams-Kanalnachrichten** und **Teams-Chats** konfigurieren. Aufbewahrungsrichtlinien, die für Postfächer von Exchange-Benutzern oder Gruppen konfiguriert sind, sind nicht in Teams-Chats und -Kanalnachrichten enthalten.

> [!NOTE]
> Wenn ein Benutzer in einer aktiven Aufbewahrungsrichtlinie enthalten ist, in der Teams-Nachrichten gespeichert sind, und Sie ein Postfach eines Benutzers löschen, der in dieser Richtlinie enthalten ist, wird das Postfach in ein [inaktives Postfach](inactive-mailboxes-in-office-365.md) konvertiert, um die Teams-Daten beizubehalten. Wenn diese Microsoft Teams-Daten für den Benutzer nicht aufbewahrt werden müssen, schließen Sie das Benutzerkonto aus der Aufbewahrungsrichtlinie aus, bevor Sie das Postfach löschen.

Nachdem eine Aufbewahrungsrichtlinie für Chat- und Kanalnachrichten konfiguriert wurde, wertet ein Timer-Job des Exchange-Dienstes regelmäßig Elemente im verborgenen Ordner aus, in dem diese Teams-Nachrichten gespeichert sind. Die Ausführung des Timer-Jobs dauert 1–7 Tage. Wenn die Aufbewahrungszeit für die Elemente abgelaufen ist, werden sie in den Ordner SubstrateHolds verschoben – einen weiteren versteckten Ordner, der sich im Postfach von Benutzenden oder Gruppen befindet, um "vorläufig gelöschte" Elemente zu speichern, bevor sie endgültig gelöscht werden. 

Nachrichten bleiben mindestens 1 Tag lang im Ordner "SubstrateHolds". Wenn sie dann zum Löschen berechtigt sind, löscht der Timer-Job sie bei der nächsten Ausführung endgültig.

Nachdem eine Aufbewahrungsrichtlinie für Chat- oder Kanalnachrichten konfiguriert wurde, sind die Inhaltspfade davon abhängig, ob die Aufbewahrungsrichtlinie beibehalten und dann gelöscht, nur beibehalten oder nur gelöscht werden soll.

Wenn die Aufbewahrungsrichtlinie lautet beibehalten und dann löschen:

![Diagramm des Aufbewahrungsflusses für Microsoft Teams-Chat- und Kanalnachrichten](../media/teamsretentionlifecycle.png)

Zu den zwei Pfaden im Diagramm:

1. **Wenn eine Chat- oder Kanalnachricht während der Aufbewahrungsfrist von einem Benutzer bearbeitet oder gelöscht wird**, wird die Originalnachricht in den Ordner "SubstrateHolds" kopiert (falls bearbeitet) oder verschoben (falls gelöscht). Die Nachricht wird dort mindestens 1 Tag gespeichert. Wenn der Aufbewahrungszeitraum abläuft, wird die Nachricht bei der nächsten Ausführung des Timer-Jobs (in der Regel zwischen 1–7 Tagen) endgültig gelöscht.

2. **Wenn eine Chat- oder Kanalnachricht nicht von einem Benutzer gelöscht wird,** und für aktuelle Nachrichten nach der Bearbeitung wird die Nachricht nach Ablauf der Aufbewahrungsfrist in den Ordner "SubstrateHolds" verschoben. Diese Aktion dauert in der Regel zwischen 1 und 7 Tagen nach dem Ablaufdatum. Wenn sich die Nachricht im Ordner "SubstrateHolds" befindet, wird sie dort für mindestens 1 Tag gespeichert. Danach wird die Nachricht bei der nächsten Ausführung des Timer-Jobs (in der Regel zwischen 1–7 Tagen) endgültig gelöscht. 

> [!NOTE]
> In Postfächern gespeicherte Nachrichten, einschließlich der ausgeblendeten Ordner, sind mit eDiscovery-Tools durchsuchbar. Solange Nachrichten nicht endgültig aus dem Ordner "SubstrateHolds" gelöscht sind, bleiben sie mit eDiscovery-Tools durchsuchbar.

Wenn Nachrichten endgültig aus dem Ordner "SubstrateHolds" gelöscht werden, wird ein Löschvorgang an den Azure-Back-End-Chatdienst übermittelt, der dann denselben Vorgang an die Teams-Client-App weiterleitet. Verzögerungen bei dieser Kommunikation oder beim Caching können erklären, warum Benutzer für einen kurzen Zeitraum diese Nachrichten in ihrer Teams-App zwar noch sehen, die Daten aus diesen Nachrichten aber nicht mit eDiscovery-Suchvorgängen zurückgegeben werden. Nachrichten, die in der Teams-App sichtbar sind, spiegeln nicht genau wider, ob sie aus Compliance-Gründen aufbewahrt oder endgültig gelöscht werden.

Wenn die Aufbewahrungsrichtlinie dem reinen Aufbewahren oder dem reinen Löschen dient, stellen die Inhaltspfade Varianten von Aufbewahren und Löschen dar.

### <a name="content-paths-for-retain-only-retention-policy"></a>Inhaltspfade für rein aufbewahrende Aufbewahrungsrichtlinien

1. **Wenn eine Chat- oder Kanalnachricht während der Aufbewahrungsfrist von einem Benutzer bearbeitet oder gelöscht wird**, wird die Originalnachricht für mindestens 1 Tag in den Ordner "SubstrateHolds" kopiert (falls bearbeitet) oder verschoben (falls gelöscht). Wenn die Aufbewahrungsrichtlinie so konfiguriert ist, dass sie für immer aufbewahrt, bleibt das Element dort. Wenn die Aufbewahrungsrichtlinie ein Enddatum für den Aufbewahrungszeitraum hat und dieses abläuft, wird die Nachricht bei der nächsten Ausführung des Timer-Jobs (in der Regel zwischen 1–7 Tagen) endgültig gelöscht.

2. **Wenn die Chat- oder Kanalnachricht nicht von einem Benutzer geändert oder gelöscht wird** und für aktuelle Nachrichten nach der Bearbeitung während des Aufbewahrungszeitraums: Vor und nach dem Aufbewahrungszeitraum geschieht nichts; die Nachricht wird an ihrem ursprünglichen Ort belassen.

### <a name="content-paths-for-delete-only-retention-policy"></a>Inhaltspfade für Aufbewahrungsrichtlinien für reines Löschen

1. **Wenn die Chat- oder Kanalnachricht während der Aufbewahrungsfrist von einem Benutzer bearbeitet oder gelöscht wird**, wird die Originalnachricht in den Ordner "SubstrateHolds" kopiert (falls bearbeitet) oder verschoben (falls gelöscht). Die Nachricht wird dort für mindestens 1 Tag aufbewahrt und bei der nächsten Ausführung des Timer-Jobs (in der Regel zwischen 1–7 Tagen) endgültig gelöscht.

2. **Wenn eine Chat- oder Kanalnachricht während des Aufbewahrungszeitraums nicht von einem Benutzer gelöscht wird**: Die Nachricht wird am Ende des Aufbewahrungszeitraums in den Ordner "SubstrateHolds" verschoben. Diese Aktion dauert in der Regel zwischen 1 und 7 Tagen nach dem Ablaufdatum. Die Nachricht wird dort für mindestens 1 Tag aufbewahrt und dann bei der nächsten Ausführung des Timer-Jobs (in der Regel zwischen 1–7 Tagen) endgültig gelöscht.

#### <a name="example-flows-and-timings-for-retention-policies"></a>Beispielflüsse und Zeitabläufe für Aufbewahrungsrichtlinien

Verwenden Sie die folgenden Beispiele, um zu sehen, wie die in den vorherigen Abschnitten erläuterten Prozesse und Zeitabläufe auf Aufbewahrungsrichtlinien mit den folgenden Konfigurationen angewendet werden:

- [Beispiel 1: Aufbewahrung nur für 7 Jahre](#example-1-retain-only-for-7-years)
- [Beispiel 2: Aufbewahrung für 30 Tage und dann löschen](#example-2-retain-for-30-days-and-then-delete)
- [Beispiel 3: Löschung nur nach 1 Tag](#example-3-delete-only-after-1-day)

Bei allen Beispielen, die sich auf die endgültige Löschung beziehen, wird diese Aktion aufgrund der [Grundsätze der Aufbewahrung](retention.md#the-principles-of-retention-or-what-takes-precedence) ausgesetzt, wenn die Nachricht einer anderen Aufbewahrungsrichtlinie unterliegt, die das Element aufbewahrt, oder wenn sie einem eDiscovery Hold unterliegt.

##### <a name="example-1-retain-only-for-7-years"></a>Beispiel 1: Aufbewahrung nur für 7 Jahre

An Tag 1 erstellt ein Benutzer eine Chat- oder Kanalnachricht.

An Tag 5 bearbeitet der Benutzer diese Nachricht.

An Tag 30 löscht der Benutzer die aktuelle Nachricht.

Aufbewahrungsergebnisse:

- Für die ursprüngliche Nachricht:
    - An Tag 5 wird die Nachricht in den Ordner "SubstrateHolds" kopiert, wo sie noch mindestens 7 Jahre ab Tag 1 (Aufbewahrungszeitraum) mit eDiscovery-Tools durchsucht werden kann.

- Für die aktuelle (bearbeitete) Nachricht:
    - An Tag 30 wird die Nachricht in den Ordner "SubstrateHolds" verschoben, wo sie noch mindestens 7 Jahre ab Tag 1 (Aufbewahrungszeitraum) mit eDiscovery-Tools durchsucht werden kann.

Wenn der Benutzer die aktuelle Nachricht nach dem angegebenen Aufbewahrungszeitraum statt innerhalb des Aufbewahrungszeitraums gelöscht hätte, würde die Nachricht trotzdem in den Ordner "SubstrateHolds" verschoben werden. Allerdings ist jetzt der Aufbewahrungszeitraum abgelaufen. Die Nachricht wird nach mindestens 1 Tag und dann in der Regel innerhalb von 1 bis 7 Tagen endgültig gelöscht.

##### <a name="example-2-retain-for-30-days-and-then-delete"></a>Beispiel 2: Aufbewahrung für 30 Tage und dann löschen

An Tag 1 erstellt ein Benutzer eine Chat- oder Kanalnachricht.

An Tag 10 bearbeitet der Benutzer diese Nachricht.

Der Benutzer bearbeitet die Nachricht nicht weiter und löscht sie nicht.

Aufbewahrungsergebnisse:

- Für die ursprüngliche Nachricht:
    - An Tag 10 wird die Nachricht in den Ordner "SubstrateHolds" kopiert, wo sie weiterhin mit eDiscovery-Tools durchsucht werden kann.
    - Am Ende des Aufbewahrungszeitraums (30 Tage ab Tag 1) wird die Nachricht in der Regel innerhalb von 1 bis 7 Tagen nach mindestens 1 Tag endgültig gelöscht, und sie wird dann nicht mit eDiscovery-Suchvorgängen zurückgegeben.

- Für die aktuelle (bearbeitete) Nachricht:
    - Nach Ablauf des Aufbewahrungszeitraums (30 Tage ab Tag 1) wird die Nachricht in der Regel innerhalb von 1–7 Tagen in den Ordner "SubstrateHolds" verschoben, wo sie weiterhin mit eDiscovery-Tools durchsucht werden kann.
    - Die Nachricht wird dann in der Regel innerhalb von 1–7 Tagen endgültig nach mindestens 1 Tag gelöscht und wird dann nicht mehr mit eDiscovery-Suchvorgängen zurückgegeben.

##### <a name="example-3-delete-only-after-1-day"></a>Beispiel 3: Löschung nur nach 1 Tag

> [!NOTE]
> Aufgrund der kurzen eintägigen Dauer dieser Konfiguration und Aufbewahrungsprozessen, die innerhalb eines Zeitraums von 1–7 Tagen funktionieren, zeigt dieser Abschnitt Beispielzeitpunkte, die im typischen Zeitbereich liegen.

An Tag 1 erstellt ein Benutzer eine Chat- oder Kanalnachricht.

Beispiel für ein Aufbewahrungsergebnis, wenn der Benutzer die Nachricht nicht bearbeitet oder löscht:

- Tag 5 (in der Regel 1–7 Tage nach Beginn des Aufbewahrungszeitraums an Tag 3):
    - Die Nachricht wird in den Ordner "SubstrateHolds" verschoben und verbleibt dort für mindestens 1 Tag, wo sie weiterhin mit eDiscovery-Tools durchsucht werden kann.

- Tag 9 (in der Regel 1–7 Tage nach mindestens 1 Tag im Ordner "SubstrateHolds"):
    - Die Nachricht wird endgültig gelöscht und kann dann nicht mehr mit eDiscovery-Suchvorgängen zurückgegeben werden.

Wie dieses Beispiel zeigt, können Sie zwar eine Aufbewahrungsrichtlinie so konfigurieren, dass Nachrichten bereits nach einem Tag gelöscht werden, der Dienst durchläuft jedoch mehrere Prozesse, um eine konforme Löschung zu gewährleisten. Infolgedessen kann es bei einer Löschaktion nach 1 Tag 18 Tage dauern, bis die Nachricht endgültig gelöscht ist, so dass sie nicht mehr mit eDiscovery-Suchvorgängen zurückgegeben wird.

## <a name="skype-for-business-and-teams-interop-chats"></a>Interop-Chats in Skype for Business und Microsoft Teams

Wenn ein Skype for Business Online-Chat in Microsoft Teams eintrifft, wird er zu einer Nachricht in einem Teams-Chatthread und in das entsprechende Postfach aufgenommen. Aufbewahrungsrichtlinien werden auf diese Nachrichten aus dem Microsoft Teams-Thread angewendet. 

Wenn jedoch der Unterhaltungsverlauf für Skype for Business Online aktiviert ist, und dieser Verlauf von der Skype for Business Online-Clientseite aus in einem Postfach gespeichert wird, werden diese Chatdaten nicht von einer Aufbewahrungsrichtlinie für Microsoft Teams verarbeitet. Verwenden Sie für diese Inhalte eine Aufbewahrungsrichtlinie, die für Skype for Business konfiguriert ist.

## <a name="meetings-and-external-users"></a>Besprechungen und externe Benutzer

Kanal-Besprechungsnachrichten werden auf die gleiche Weise wie Kanalnachrichten gespeichert, wählen Sie für diese Daten also den Speicherort **Teams-Kanalnachrichten** aus, wenn Sie Ihre Aufbewahrungsrichtlinie konfigurieren.

Nachrichten spontaner und geplanter Besprechungen werden auf die gleiche Weise wie Gruppenchatnachrichten gespeichert. Wählen Sie für diese Daten also den Speicherort **Teams-Chats** aus, wenn Sie Ihre Aufbewahrungsrichtlinie konfigurieren.

Wenn externe Benutzer in eine von Ihrer Organisation gehosteten Besprechung einbezogen werden:

- Wenn ein externer Benutzer über ein Gastkonto in Ihrem Mandanten beitritt, verfügt er über ein Schattenpostfach, das u. U. der Aufbewahrungsrichtlinie Ihrer Organisation für Microsoft Teams unterliegt. Alle Nachrichten aus der Besprechung werden sowohl im Postfach der Benutzer als auch im Schattenpostfach gespeichert. 

- Wenn ein externer Benutzer über ein Konto einer anderen Microsoft 365-Organisation beitritt, können Ihre Aufbewahrungsrichtlinien keine Nachrichten für diesen Benutzer löschen, weil sie im Postfach dieses Benutzers in einem anderen Mandanten gespeichert sind. Für dieselbe Besprechung können Ihre Aufbewahrungsrichtlinien jedoch Nachrichten für Ihre Benutzer löschen.

## <a name="when-a-user-leaves-the-organization"></a>Wenn ein Benutzer die Organisation verlässt 

Wenn ein Benutzer, der ein Postfach in Exchange Online hat, Ihre Organisation verlässt und das Microsoft 365-Konto gelöscht wird, werden die Chatnachrichten, die der Aufbewahrung unterliegen, in einem inaktiven Postfach gespeichert. Die Chatnachrichten unterliegenweiterhin der Aufbewahrungsrichtlinie, die dem Benutzer zugewiesen wurde, bevor sein Postfach inaktiv wurde, und die Inhalte sind für eine eDiscovery-Suche verfügbar. Weitere Informationen finden Sie unter [Inaktive Postfächer in Exchange Online](inactive-mailboxes-in-office-365.md). 

Wenn der Benutzer Dateien in Teams gespeichert hat, lesen Sie den Abschnitt [Äquivalent](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) für SharePoint und OneDrive.

## <a name="limitations"></a>Einschränkungen

Wir arbeiten kontinuierlich an der Verbesserung der Aufbewahrungsfunktionen in Microsoft Teams. Es gibt folgende Einschränkungen, die Sie bei der Verwendung von Aufbewahrungsrichtlinien für Teams-Kanalnachrichten und -Chats beachten sollten:

- **Falsche Anzeige in Outlook**. Wenn Sie Aufbewahrungsrichtlinien für Skype- oder Microsoft Teams-Speicherorte erstellen, wird eine dieser Richtlinien als Standard-Ordnerrichtlinie angezeigt, wenn ein Benutzer die Eigenschaften eines Postfachordners im Outlook Desktop-Client einsieht. Hierbei handelt es sich um ein Anzeigeproblem in Outlook und [ein bekanntes Problem](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies). Stattdessen sollte die Aufbewahrungsrichtlinie für Postfächer angezeigt werden, die auf den Ordner angewendet wird. Die Aufbewahrungsrichtlinie für Skype oder Microsoft Teams wird nicht auf das Postfach des Benutzers angewendet.

## <a name="configuration-guidance"></a>Konfigurationsleitfaden

Wenn Sie die Konfiguration der Datenaufbewahrung in Microsoft 365 zum ersten Mal durchführen möchten, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).

Wenn Sie bereit sind, eine Aufbewahrungsrichtlinie für Teams zu erstellen, lesen Sie [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](create-retention-policies.md).