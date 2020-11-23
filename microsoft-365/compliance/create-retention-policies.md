---
title: Erstellen und Konfigurieren von Aufbewahrungsrichtlinien zum automatischen Aufbewahren oder Löschen von Inhalten
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
description: Mithilfe einer Aufbewahrungsrichtlinie können Sie sehr effizient die Kontrolle über den Inhalt behalten, den Benutzer mit E-Mails, Dokumenten und Konversationen generieren. Behalten Sie, was Sie wollen, und entfernen Sie das, was Sie nicht wollen.
ms.openlocfilehash: bcf0ef5aa76113102013bc20fca02e6d516c3203
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376578"
---
# <a name="create-and-configure-retention-policies"></a>Erstellen und Konfigurieren von Aufbewahrungsrichtlinien

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Mithilfe einer Aufbewahrungsrichtlinie können Sie proaktiv entscheiden, ob Inhalte aufbewahrt, gelöscht oder beides (also aufbewahrt und dann gelöscht) werden sollen.

Mit einer Aufbewahrungsrichtlinie können Sie dies sehr effizient tun, indem Sie dieselben Aufbewahrungseinstellungen für Inhalte nach Speicherort, auf Website- oder Postfachebene zuweisen. Wenn Sie nicht sicher sind, ob Sie eine Aufbewahrungsrichtlinie oder eine Aufbewahrungsbezeichnung verwenden sollen, lesen Sie [Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](retention.md#retention-policies-and-retention-labels).

Näheres über Aufbewahrungsrichtlinien und wie die Aufbewahrung funktioniert erfahren Sie unter [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](retention.md).

## <a name="before-you-begin"></a>Vorbereitung

Der globale Administrator Ihrer Organisation verfügt über die vollständigen Berechtigungen zum Erstellen und Bearbeiten von Aufbewahrungsrichtlinien. Wenn Sie sich nicht als globaler Administrator anmelden, lesen Sie [Erforderlichen Berechtigungen zum Erstellen und Verwalten von Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen.](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).

## <a name="create-and-configure-a-retention-policy"></a>Erstellen und Konfigurieren einer Aufbewahrungsrichtlinie

Obwohl eine Aufbewahrungsrichtlinie mehrere Speicherorte unterstützt, können Sie keine einzelne Aufbewahrungsrichtlinie erstellen, die alle unterstützten Speicherorte umfasst:

- Exchange-E-Mail
- SharePoint-Website
- OneDrive-Konten
- Microsoft 365-Gruppen
- Skype for Business
- Öffentliche Exchange-Ordner
- Teams-Kanalnachrichten
- Teams-Chats
- Nachrichten in der Yammer-Community
- Private Nachrichten in Yammer

Wenn Sie beim Erstellen einer Aufbewahrungsrichtlinie die Teams- oder Yammer-Speicherorte auswählen, werden die anderen Speicherorte automatisch ausgeschlossen. Welche Anweisungen zu befolgen sind, hängt daher davon ab, ob Sie die Teams- oder Yammer-Speicherorte einschließen müssen:

- [Anweisungen für eine Aufbewahrungsrichtlinie für Teams-Speicherorte](#retention-policy-for-teams-locations)
- [Anweisungen für eine Aufbewahrungsrichtlinie für Yammer-Speicherorte](#retention-policy-for-yammer-locations)
- [Anweisungen für eine Aufbewahrungsrichtlinie für andere Speicherorte als Teams und Yammer ](#retention-policy-for-locations-other-than-teams-and-yammer)

Wenn Sie über mehr als eine Aufbewahrungsrichtlinie verfügen und außerdem Aufbewahrungsbezeichnungen verwenden, lesen Sie [Grundsätze der Aufbewahrung, oder was hat Vorrang?](retention.md#the-principles-of-retention-or-what-takes-precedence), um das Ergebnis zu verstehen, wenn mehrere Aufbewahrungseinstellungen für dieselben Inhalte gelten.

### <a name="retention-policy-for-teams-locations"></a>Aufbewahrungsrichtlinie für Teams-Speicherorte

1. Wählen Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) die Option **Richtlinien** > **Aufbewahrung** aus.

2. Wählen Sie **Neue Aufbewahrungsrichtlinie** aus, um den Assistenten zum Erstellen einer Aufbewahrungsrichtlinie zu starten, und benennen Sie die neue Aufbewahrungsrichtlinie.

3. Wählen Sie auf der Seite **Speicherorte für die Anwendung der Richtlinie auswählen** einen oder beide Speicherorte für Teams aus: **Teams Kanalnachricht** und **Teams Chats**.

   Bei **Teams Kanalnachrichten** sind Nachrichten von Standardkanälen enthalten, aber nicht von [privaten Kanälen](https://docs.microsoft.com/microsoftteams/private-channels). Derzeit werden private Kanäle nicht durch Aufbewahrungsrichtlinien unterstützt.

   Standardmäßig werden [alle Teams und alle Benutzer ausgewählt](#a-policy-that-applies-to-entire-locations), aber Sie können dies verfeinern, indem Sie die Optionen [**Auswählen** und **Ausschließen** verwenden](#a-policy-with-specific-inclusions-or-exclusions).

4. Geben Sie auf der Assistentenseite **Entscheiden, ob Inhalte aufbewahrt werden, gelöscht werden oder beides** die Konfigurationsoptionen für das Aufbewahren und Löschen von Inhalten an.

   Sie können eine Aufbewahrungsrichtlinie erstellen, die Inhalte nur aufbewahrt, ohne sie zu löschen, Inhalte aufbewahrt und nach einem bestimmten Zeitraum löscht oder Inhalte nach einem bestimmten Zeitraum einfach löscht. Weitere Informationen finden Sie unter [Einstellungen zum Aufbewahren und Löschen von Inhalten](#settings-for-retaining-and-deleting-content) auf dieser Seite.

5. Schließen Sie den Assistenten ab, damit Ihre Einstellungen gespeichert werden.

Weitere Informationen zu Aufbewahrungsrichtlinien für Teams finden Sie unter [Aufbewahrungsrichtlinien in Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies) in der Teams-Dokumentation.

#### <a name="additional-retention-policy-needed-to-support-teams"></a>Zusätzliche für die Unterstützung von Teams benötigte Aufbewahrungsrichtlinie

Teams sind mehr als nur Chats und Kanalnachrichten. Wenn Sie Teams haben, die aus einer Microsoft 365-Gruppe (früher Office 365-Gruppe) erstellt wurden, sollten Sie zusätzlich eine Aufbewahrungsrichtlinie konfigurieren, die diese Microsoft 365-Gruppe enthält, indem Sie den Speicherort der **Microsoft 365-Gruppen** verwenden. Diese Aufbewahrungsrichtlinie gilt für Inhalte im Postfach, in der Website und in den Dateien der Gruppe.

Wenn Sie Teamwebsites haben, die mit keiner Microsoft 365-Gruppe verbunden sind, benötigen Sie eine Aufbewahrungsrichtlinie, welche die Speicherorte für **SharePoint-Websites** oder **OneDrive-Konten** einschließt, um Dateien in Teams aufzubewahren und zu löschen:

- In einem Chat freigegebene Dateien werden im OneDrive-Konto des Benutzers gespeichert, der sie freigegeben hat.

- In Kanäle hochgeladene Dateien werden auf der SharePoint-Website für das Team gespeichert.

> [!TIP]
> Sie können eine Aufbewahrungsrichtlinie auf die Dateien eines bestimmten Teams anwenden, wenn dieses mit keiner Microsoft 365-Gruppe verbunden ist, indem Sie die SharePoint-Website für das Team und die OneDrive-Konten der Benutzer im Team auswählen.

Es ist möglich, dass eine Aufbewahrungsrichtlinie, die auf Microsoft 365-Gruppen, SharePoint-Websites oder OneDrive-Konten angewendet wird, eine Datei löscht, auf die in einem Team-Chat oder einer Kanalnachricht verwiesen wird, bevor diese Nachrichten gelöscht werden. In diesem Szenario wird die Datei weiterhin in der Team-Nachricht angezeigt, aber wenn Benutzer die Datei auswählen, wird die Fehlermeldung „Datei nicht gefunden“ angezeigt. Dieses Verhalten gilt nicht nur für Aufbewahrungsrichtlinien, sondern kann auch auftreten, wenn ein Benutzer eine Datei manuell aus SharePoint oder OneDrive löscht.

### <a name="retention-policy-for-yammer-locations"></a>Aufbewahrungsrichtlinie für Yammer-Speicherorte

> [!NOTE]
> Die Aufbewahrungsrichtlinien für Yammer werden in Kürze eingeführt. Wenn Sie die neuen Standorte für Yammer noch nicht sehen, versuchen Sie es in ein paar Wochen noch einmal.
>
> Um diese Funktion nutzen zu können, muss Ihr Yammer-Netzwerk im [nativen Modus](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) und nicht im Hybridmodus arbeiten.

1. Wählen Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) die Option **Richtlinien** > **Aufbewahrung** aus.

2. Wählen Sie **Neue Aufbewahrungsrichtlinie**, um eine neue Aufbewahrungsrichtlinie zu erstellen.

3. Geben Sie auf der Assistentenseite **Entscheiden, ob Inhalte aufbewahrt werden, gelöscht werden oder beides** die Konfigurationsoptionen für das Aufbewahren und Löschen von Inhalten an. 
    
    Sie können eine Aufbewahrungsrichtlinie erstellen, die Inhalte nur aufbewahrt, ohne sie zu löschen, Inhalte aufbewahrt und nach einem bestimmten Zeitraum löscht oder Inhalte nach einem bestimmten Zeitraum einfach löscht. Weitere Informationen finden Sie unter [Einstellungen zum Aufbewahren und Löschen von Inhalten](#settings-for-retaining-and-deleting-content) auf dieser Seite.
    
    Wählen Sie nicht **Erweiterte Aufbewahrungseinstellungen verwenden**, da diese Option für Yammer-Speicherorte nicht unterstützt wird. 

4. Wählen Sie auf der Seite **Speicherorte wählen** die Option **Bestimmte Speicherorte auswählen**. Dann aktivieren Sie einen oder beide Speicherorte für Yammer: **Yammer Community-Nachrichten** und **Yammer private Nachrichten**.
    
    Standardmäßig sind alle Communitys und Benutzer ausgewählt, aber Sie können dies verfeinern, indem Sie Communitys und Benutzer angeben, die ein- oder -ausgeschlossen werden sollen.
    
    Für private Yammer-Nachrichten: 
    - Wenn Sie den Standard auf **Alle** belassen, werden Azure B2B-Gastbenutzer nicht berücksichtigt. 
    - Durch Wählen von **Benutzer auswählen** können Sie eine Aufbewahrungsrichtlinie auf externe Benutzer anwenden, wenn Sie deren Konto kennen.

5. Schließen Sie den Assistenten ab, um Ihre Einstellungen zu speichern.

Weitere Informationen darüber, wie die Aufbewahrungsrichtlinien bei Yammer funktionieren, finden Sie unter [Informationen zur Aufbewahrung bei Yammer](retention-policies-yammer.md).

#### <a name="additional-retention-policies-needed-to-support-yammer"></a>Zusätzliche für die Unterstützung von Yammer benötigte Aufbewahrungsrichtlinien

Yammer ist mehr als nur Community-Nachrichten und private Nachrichten. Konfigurieren Sie zum Aufbewahren und Löschen von E-Mail-Nachrichten für Ihr Yammer-Netzwerk eine zusätzliche Aufbewahrungsrichtlinie, die alle für Yammer verwendeten Microsoft 365-Gruppen enthält, indem Sie den Speicherort der **Microsoft 365-Gruppen** verwenden. 

Um Dateien, die in Yammer gespeichert sind, aufzubewahren und zu löschen, benötigen Sie eine Aufbewahrungsrichtlinie, welche die **SharePoint-Websites** oder die Speicherorte der **OneDrive-Konten** umfasst:

- Dateien, die in privaten Nachrichten gemeinsam genutzt werden, werden im OneDrive-Konto des Benutzers gespeichert, der die Datei freigegeben hat. 

- Dateien, die in Communitys hochgeladen werden, werden auf der SharePoint-Website für die Yammer-Community gespeichert.

Es ist möglich, dass eine Aufbewahrungsrichtlinie, die auf SharePoint-Websites oder OneDrive-Konten angewendet wird, eine Datei löscht, auf die in einer Yammer-Nachricht verwiesen wird, bevor diese Nachrichten gelöscht werden. In diesem Szenario wird die Datei weiterhin in der Yammer-Nachricht angezeigt, aber wenn Benutzer die Datei auswählen, wird die Fehlermeldung „Datei nicht gefunden“ angezeigt. Dieses Verhalten gilt nicht nur für Aufbewahrungsrichtlinien, sondern kann auch auftreten, wenn ein Benutzer eine Datei manuell aus SharePoint oder OneDrive löscht.

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a>Aufbewahrungsrichtlinie für andere Speicherorte als Teams oder Yammer

Verwenden Sie die folgenden Anweisungen für Aufbewahrungsrichtlinien, die für alle diese Dienste gelten:

- Exchange: E-Mail und öffentliche Ordner
- SharePoint: Websites
- OneDrive: Konten
- Microsoft 365-Gruppen
- Skype for Business

1. Wählen Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) die Option **Richtlinien** > **Aufbewahrung** aus.

2. Wählen Sie **Neue Aufbewahrungsrichtlinie** aus, um den Assistenten zum Erstellen einer Aufbewahrungsrichtlinie zu starten, und benennen Sie die neue Aufbewahrungsrichtlinie.

3. Schalten Sie auf der Seite **Speicherorte wählen** die einzelnen Speicherorte ein oder aus, außer den Speicherorten für Teams. Sie können für jeden Speicherort die Standardeinstellung beibehalten, und die [Richtlinie auf den gesamten Speicherort anwenden](#a-policy-that-applies-to-entire-locations) oder [Ein- und Ausschlüsse angeben](#a-policy-with-specific-inclusions-or-exclusions).

    Spezifische Informationen zu Speicherorten:
    - [Exchange-E-Mail und öffentliche Exchange-Ordner](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [SharePoint-Websites und OneDrive-Konten](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [Microsoft 365-Gruppen](#configuration-information-for-microsoft-365-groups)
    - [Skype for Business](#configuration-information-for-skype-for-business)

4. Geben Sie auf der Assistentenseite **Entscheiden, ob Inhalte aufbewahrt werden, gelöscht werden oder beides** die Konfigurationsoptionen für das Aufbewahren und Löschen von Inhalten an.

    Sie können eine Aufbewahrungsrichtlinie erstellen, die Inhalte nur aufbewahrt, ohne sie zu löschen, Inhalte aufbewahrt und nach einem bestimmten Zeitraum löscht oder Inhalte nach einem bestimmten Zeitraum einfach löscht. Weitere Informationen finden Sie unter [Einstellungen zum Aufbewahren und Löschen von Inhalten](#settings-for-retaining-and-deleting-content) auf dieser Seite.

5. Schließen Sie den Assistenten ab, damit Ihre Einstellungen gespeichert werden.

#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a>Konfigurationsinformationen für Exchange-E-Mail und öffentliche Exchange-Ordner

Der Speicherort von **Exchange-E-Mail** unterstützt die Aufbewahrung von E-Mail-, Kalender- und anderen Postfachelementen der Benutzer, indem die Aufbewahrungseinstellungen auf Postfachebene angewendet werden.

Ausführliche Informationen zu den Elementen, die beim Konfigurieren von Aufbewahrungseinstellungen für Exchange eingeschlossen oder ausgeschlossen werden, finden Sie unter [Umfang für Aufbewahrung und Löschung](retention-policies-exchange.md#whats-included-for-retention-and-deletion).

Beachten Sie, dass eine Aufbewahrungsrichtlinie für den gesamten **Exchange-E-Mail**-Speicherort keine Inhalte vom Microsoft 365-Gruppenpostfächern enthält, auch wenn die Microsoft 365-Gruppe über ein Exchange-Postfach verfügt. Wählen Sie den Speicherort für **Microsoft 365-Gruppen** aus, um Inhalte in diesen Postfächern aufzubewahren.

Der Speicherort für **öffentliche Exchange-Ordner** wendet die Aufbewahrungseinstellungen auf alle öffentlichen Ordner an und kann nicht auf der Ordner- oder Postfachebene angewendet werden.

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a>Konfigurationsinformationen für SharePoint-Websites und OneDrive-Konten

Wenn Sie den Speicherort für **SharePoint-Websites** auswählen, kann die Aufbewahrungsrichtlinie Dokumente in SharePoint-Kommunikationswebsites, in nicht durch Microsoft 365-Gruppen verbundenen Teamwebsites und in klassischen Websites aufbewahren und löschen. Über Microsoft 365-Gruppen verbundene Teamwebsites werden mit dieser Option nicht unterstützt. Verwenden Sie stattdessen den Speicherort für **Microsoft 365-Gruppen**, der für Inhalte im Postfach, in der Website und in den Dateien der Gruppe gilt.

Obwohl die Aufbewahrungsrichtlinie auf Website-Ebene angewendet wird, werden nur Dokumente mit Aufbewahrungseinstellungen versehen. Ausführliche Informationen dazu, welche Elemente beim Konfigurieren der Aufbewahrungseinstellungen für SharePoint und OneDrive enthalten und ausgeschlossen sind, finden Sie unter [Umfang für Aufbewahrung und Löschung](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion). 

Wenn Sie Ihre Speicherorte für SharePoint-Websites oder OneDrive-Konten angeben, benötigen Sie keine Berechtigungen für den Zugriff auf die Websites, und zum Zeitpunkt der Angabe der URL auf der Seite **Speicherorte bearbeiten** erfolgt keine Überprüfung. Bei den von Ihnen angegebenen SharePoint-Websites wird jedoch beim Abschluss des Assistenten überprüft, ob sie vorhanden sind. Wenn diese Prüfung fehlschlägt, wird die Meldung angezeigt, dass die Überprüfung für die von Ihnen eingegebene URL fehlgeschlagen ist. Der Assistent erstellt die Aufbewahrungsrichtlinie erst dann, wenn die Validierung erfolgreich abgeschlossen wurde. Wenn diese Meldung angezeigt wird, kehren Sie zum Assistenten zurück, um die URL zu ändern oder die Website aus der Aufbewahrungsrichtlinie zu entfernen.

Wenn Sie einzelne OneDrive-Konten angeben möchten, die ein- oder ausgeschlossen werden sollen, hat die URL das folgende Format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`

Beispielsweise bei einem Benutzer im Mandanten „Contoso“, der den Benutzernamen „rsimone“ hat: `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`

Informationen zum Überprüfen der Syntax für Ihren Mandanten und zum Identifizieren von URLs für Benutzer finden Sie unter [Abrufen einer Liste aller Benutzer OneDrive-URLs in Ihrer Organisation](https://docs.microsoft.com/onedrive/list-onedrive-urls).

### <a name="configuration-information-for-microsoft-365-groups"></a>Konfigurationsinformationen für Microsoft 365-Gruppen

Um Inhalte für eine Microsoft 365-Gruppe (früher Office 365-Gruppe) aufzubewahren oder zu löschen verwenden Sie den Speicherort für **Microsoft 365-Gruppen**. Auch wenn eine Microsoft 365-Gruppe über ein Exchange-Postfach verfügt, enthält eine Aufbewahrungsrichtlinie, die den gesamten Speicherort für **Exchange-E-Mail** enthält, keinen Inhalt von Microsoft 365-Gruppenpostfächern. Obwohl Sie am Speicherort für **Exchange-E-Mail** anfänglich festlegen können, ob ein Gruppenpostfach eingeschlossen oder ausgeschlossen werden soll, wird beim Speichern der Aufbewahrungsrichtlinie die Fehlermeldung angezeigt, dass „RemoteGroupMailbox“ keine gültige Auswahl für den Exchange-Speicherort ist.

Eine Aufbewahrungsrichtlinie, die auf eine Microsoft 365-Gruppe angewendet wird, umfasst das Gruppenpostfach und die SharePoint-Teamwebsite. Auf der SharePoint-Teamwebsite gespeicherte Dateien sind von diesem Speicherort abgedeckt, nicht jedoch Teams-Chats oder Teams-Kanalnachrichten, deren Speicherorten mit eigenen Aufbewahrungsrichtlinien abgedeckt sind.

### <a name="configuration-information-for-skype-for-business"></a>Konfigurationsinformationen für Skype for Business

Im Gegensatz zu Exchange-E-Mails kann der Status des Skype-Speicherorts nicht einfach aktiviert werden, um alle Benutzer automatisch einzuschließen. Wenn Sie diesen Speicherort jedoch aktivieren, müssen Sie anschließend manuell die Benutzer auswählen, deren Unterhaltungen Sie aufbewahren möchten:

![Auswählen des Skype-Speicherorts für Aufbewahrungsrichtlinien](../media/skype-location-retention-policies.png)

Wenn Sie auf **Benutzer auswählen** klicken, können Sie schnell alle Benutzer einschließen, indem Sie das Kontrollkästchen **Alle auswählen** aktivieren. Es ist jedoch wichtig zu verstehen, dass jeder Benutzer als eine einzelne Aufnahme in die Richtlinie gilt. Wenn Sie also über das Aktivieren des Kontrollkästchens **Alle auswählen** 1 000 Benutzer einschließen, entspricht dies der manuellen Auswahl von 1 000 einzuschließenden Benutzern. Dies ist die maximale Anzahl unterstützter Benutzer für Skype for Business.

Beachten Sie, dass der Outlook-Ordner **Konversationsverlauf** eine Funktion ist, die nichts mit der Skype-Archivierung zu tun hat. Der **Konversationsverlauf** kann vom Endbenutzer deaktiviert werden. Die Archivierung für Skype erfolgt jedoch durch Speichern einer Kopie der Skype-Konversationen in einem versteckten Ordner, auf den der Benutzer nicht zugreifen kann, der aber für eDiscovery verfügbar ist.

## <a name="settings-for-retaining-and-deleting-content"></a>Einstellungen für die Aufbewahrung und Löschung von Inhalten

Wenn Sie die Einstellungen für die Aufbewahrung und Löschung von Inhalten in Ihrer Aufbewahrungsrichtlinie festlegen, wird für Ihre Aufbewahrungsrichtlinie eine der folgenden Konfigurationen für einen bestimmten Zeitraum gelten:

- Nur aufbewahren

    Wählen Sie für diese Konfiguration **Elemente für einen bestimmten Zeitraum aufbewahren** und **Am Ende des Aufbewahrungszeitraums: Nichts unternehmen**. Oder wählen Sie **Elemente für immer aufbewahren**.

- Aufbewahren und dann löschen

    Wählen Sie für diese Konfiguration **Elemente für einen bestimmten Zeitraum aufbewahren** und **Am Ende des Aufbewahrungszeitraums: Elemente automatisch löschen**.

- Nur löschen

    Wählen Sie für diese Konfiguration **Elemente erst löschen, wenn sie ein bestimmtes Alter erreichen** aus.

### <a name="retaining-content-for-a-specific-period-of-time"></a>Aufbewahren von Inhalten für einen bestimmten Zeitraum

Beim Konfigurieren einer Aufbewahrungsrichtlinie können Sie festlegen, ob Elemente für eine bestimmte Anzahl von Tagen, Monaten oder Jahren oder alternativ sogar für immer aufbewahrt werden sollen.

Beim Konfigurieren einer Aufbewahrungsrichtlinie können Sie festlegen, ob Inhalte auf unbestimmte Zeit oder für eine bestimmte Anzahl von Tagen, Monaten oder Jahren aufbewahrt werden sollen. Die Aufbewahrungsfrist wird anhand des Alters des Inhalts berechnet und nicht ab dem Zeitpunkt, an dem die Aufbewahrungsrichtlinie angewendet wird.

Als Beginn des Aufbewahrungszeitraums können Sie entweder auswählen, wann der Inhalt erstellt wurde oder – nur unterstützt für Dateien und die SharePoint-, OneDrive-und Office 365-Speicherorte – wann der Inhalt zuletzt geändert wurde.

Beispiele:

- SharePoint: Wenn Sie Elemente in einer Websitesammlung nach der letzten Änderung ihres Inhalts während sieben Jahren aufbewahren möchten und ein Dokument in dieser Websitesammlung seit sechs Jahren nicht mehr geändert wurde, wird dieses Dokument nur ein weiteres Jahr aufbewahrt, wenn es nicht geändert wird. Wenn das Dokument nun erneut bearbeitet wird, dann wird das Alter des Dokuments ab dem neuen Datum der letzten Änderung berechnet und für weitere sieben Jahre aufbewahrt.

- Exchange: Wenn Sie Elemente in einem Postfach während sieben Jahren aufbewahren möchten und eine Nachricht vor sechs Jahren gesendet wurde, wird die Nachricht nur noch ein Jahr lang aufbewahrt. Bei Exchange-Elementen basiert das Alter auf dem Eingangsdatum für eingehende E-Mails oder dem Sendedatum für ausgehenden E-Mails. Das Aufbewahren von Elementen basierend auf dem Zeitpunkt der letzten Änderung gilt nur für Websiteinhalte in OneDrive und SharePoint.

Am Ende des Aufbewahrungszeitraums können Sie wählen, ob der Inhalt dauerhaft gelöscht werden soll:

![Ordneraufbewahrungseinstellungen](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)

### <a name="deleting-content-thats-older-than-a-specific-age"></a>Löschen von Inhalten, die ein bestimmtes Alter überschritten haben

Eine Aufbewahrungsrichtlinie kann Elemente sowohl aufbewahren und dann löschen, oder alte Elemente löschen, ohne sie aufzubewahren.

In beiden Fällen ist es wichtig zu wissen, dass der für eine Aufbewahrungsrichtlinie festgelegte Zeitraum für die Löschung von Elementen jedes Mal ab dem Zeitpunkt berechnet wird, als das betreffende Element erstellt oder geändert wurde und nicht ab dem Zeitpunkt, als die Richtlinie zugewiesen wurde.

Bevor Sie also eine Aufbewahrungsrichtlinie zum ersten Mal zuweisen, insbesondere wenn diese Richtlinie Elemente löscht, sollten Sie zunächst das Alter des vorhandenen Inhalts und die möglichen Auswirkungen der Richtlinie auf diesen Inhalt berücksichtigen. Sie sollten Ihre Benutzer auch über die neue Richtlinie informieren, bevor Sie diese zuweisen, um so den Benutzern Zeit für die Beurteilung möglicher Auswirkungen zu geben.

### <a name="a-policy-that-applies-to-entire-locations"></a>Eine Richtlinie, die für ganze Speicherorte gilt

Wenn Sie Speicherorte auswählen – mit Ausnahme von Skype for Business – lautet die Standardeinstellung **Alle**, wenn der Status des Speicherorts auf **An** gesetzt ist.

Wenn eine Aufbewahrungsrichtlinie auf eine beliebige Kombination ganzer Speicherorte zutrifft, gibt es keine Beschränkung für die Anzahl der Empfänger, Websites, Konten, Gruppen usw., die diese Richtlinie umfassen kann.

Wenn eine Richtlinie beispielsweise alle Exchange-E-Mails und alle SharePoint-Websites enthält, werden alle Websites und Empfänger eingeschlossen, unabhängig von der Anzahl. Bei Exchange erbt jedes neue Postfach, das nach dem Anwenden der Richtlinie erstellt wird, automatisch die Richtlinie.

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>Richtlinien, die bestimmte Elemente einschließen oder ausschließen

Nur wenn Sie die optionale Konfiguration verwenden, um Ihre Aufbewahrungseinstellungen auf bestimmte Benutzer, bestimmte Microsoft 365-Gruppen oder bestimmte Websites auszudehnen, gibt es einige Einschränkungen, die zu beachten sind: 

- Maximale Anzahl für eine Aufbewahrungsrichtlinie:
  - 1.000 Postfächer
  - 1.000 Microsoft 365-Gruppen
  - 1.000 Benutzer für private Teams-Chats
  - 100 Websites (OneDrive oder SharePoint)

Es gibt auch eine maximale Anzahl von Richtlinien, die für einen Mandanten unterstützt werden: 10 000. Diese Elemente umfassen Aufbewahrungsrichtlinien, Richtlinien für die Aufbewahrungsbezeichnung und automatische Aufbewahrungsrichtlinien.

Wenn Ihre Aufbewahrungsrichtlinien wahrscheinlich diesen Beschränkungen unterliegen, verwenden Sie die Standardkonfiguration, die für den gesamten Speicherort gilt, da diese Richtlinien keine Einschränkungen aufweisen.

Wenn Sie die optionale Konfiguration zum Festlegen des Bereichs der Aufbewahrungseinstellungen verwenden möchten, stellen Sie sicher, dass der **Status** dieses Speicherorts **Ein** ist. Verwenden Sie dann die Links, um bestimmte Benutzer, Microsoft 365-Gruppen oder Websites ein- oder auszuschließen.

> [!WARNING]
> Wenn Sie Einschlüsse konfigurieren und dann den letzten Einschluss entfernen, wird die Konfiguration für den Speicherort auf **Alle** zurückgesetzt. Vergewissern Sie sich, dass dies die von Ihnen beabsichtigte Konfiguration ist, bevor Sie die Richtlinie speichern.
>
> Wenn Sie beispielsweise eine einzelne SharePoint-Website in Ihre Aufbewahrungsrichtlinie einschließen, die zum Löschen von Daten konfiguriert ist, und dann diese Website entfernen, unterliegen standardmäßig alle SharePoint-Websites der Aufbewahrungsrichtlinie, mit der Daten dauerhaft gelöscht werden. Gleiches gilt für Einschlüsse für Exchange-Empfänger, OneDrive-Konten, Teams-Chat-Benutzer usw.
>
> Schalten Sie in diesem Szenario den Speicherort aus, wenn die Einstellung **Alle** für den Speicherort nicht der Aufbewahrungsrichtlinie unterliegen soll. Alternativ können Sie Ausschlüsse angeben, die von der Richtlinie ausgenommen werden.

## <a name="updating-retention-policies"></a>Aktualisieren von Aufbewahrungsrichtlinien

Wenn Sie eine Aufbewahrungsrichtlinie bearbeiten und Elemente bereits den ursprünglichen Einstellungen in Ihrer Aufbewahrungsrichtlinie unterliegen, werden die aktualisierten Einstellungen automatisch auf diese Elemente sowie zusätzlich auf neu identifizierte Elemente angewendet.

Normalerweise ist diese Aktualisierung ziemlich schnell, kann aber auch mehrere Tage dauern. Wenn die Richtlinienreplikation über Ihre Microsoft 365-Speicherorte abgeschlossen ist, wird der Status der Aufbewahrungsrichtlinie im Microsoft 365 Compliance Center von **Ein (Ausstehend)** in **Ein (Erfolgreich)** geändert.

## <a name="locking-the-policy-to-prevent-changes"></a>Sperren der Richtlinie, um Änderungen vorzubeugen

Wenn Sie sicherstellen müssen, das niemand die Richtlinie deaktivieren, löschen oder weniger restriktiv machen kann, lesen Sie [Verwenden der Erhaltungssperre zum Einschränken von Änderungen an Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien](retention-preservation-lock.md).
