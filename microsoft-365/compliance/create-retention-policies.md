---
title: Erstellen und Konfigurieren von Aufbewahrungsrichtlinien zum automatischen Beibehalten oder Löschen von Inhalten
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
description: Mithilfe einer Aufbewahrungsrichtlinie können Sie die Inhalte, die Benutzer mit E-Mails, Dokumenten und Unterhaltungen generieren, sehr effizient verwalten. Bewahren Sie auf, was Sie wollen, und werden Sie los, was Sie nicht mehr wollen.
ms.openlocfilehash: b992452cffbe7fa2df5e7ad02726ca337fbe0f45
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816843"
---
# <a name="create-and-configure-retention-policies"></a>Erstellen und Konfigurieren von Aufbewahrungsrichtlinien

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Mithilfe einer Aufbewahrungsrichtlinie können Sie proaktiv entscheiden, ob Inhalte aufbewahrt, gelöscht oder beides, also aufbewahrt und dann gelöscht werden sollen. 

Mit einer Aufbewahrungsrichtlinie können Sie dies sehr effizient erledigen, indem Sie identische Aufbewahrungseinstellungen für Inhalte nach Speicherort, auf Website- oder Postfachebene zuweisen. Wenn Sie nicht sicher sind, ob Sie eine Aufbewahrungsrichtlinie oder eine Aufbewahrungsbezeichnung verwenden, lesen Sie [Aufbewahrungsrichtlinien und Aufbewahrungsbeschriftungen](retention.md#retention-policies-and-retention-labels).

Näheres über Aufbewahrungsrichtlinien und wie sie funktionieren erfahren Sie unter [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](retention.md).

## <a name="before-you-begin"></a>Bevor Sie beginnen:

Der globale Administrator Ihrer Organisation verfügt über umfassende Berechtigungen zum Erstellen und Bearbeiten von Aufbewahrungsrichtlinien. Wenn Sie sich nicht als globaler Administrator anmelden, lesen Sie [Notwendige Berechtigungen zum Erstellen und Verwalten von Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).

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

Wenn Sie beim Erstellen einer Aufbewahrungsrichtlinie einen der Teams-Speicherorte auswählen, werden die anderen Speicherorte automatisch ausgeschlossen. Die folgenden Anweisungen sind daher davon abhängig, ob Sie die Teams-Speicherorte einschließen müssen:

- [Anweisungen für eine Aufbewahrungsrichtlinie für Teams-Speicherorte](#retention-policy-for-teams-locations)
- [Anweisungen für eine Aufbewahrungsrichtlinie für andere Speicherorte als Teams](#retention-policy-for-locations-other-than-teams)

Wenn Sie über mehr als eine Aufbewahrungsrichtlinie verfügen und außerdem Aufbewahrungsbezeichnungen verwenden, lesen Sie [Grundsätze der Aufbewahrung, oder was hat Vorrang?](retention.md#the-principles-of-retention-or-what-takes-precedence), um das Ergebnis zu verstehen, wenn mehrere Aufbewahrungseinstellungen für dieselben Inhalte gelten.

### <a name="retention-policy-for-teams-locations"></a>Aufbewahrungsrichtlinie für Teams-Speicherorte

1. Wählen Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) die Option **Richtlinien** > **Aufbewahrung** aus.

2. Wählen Sie **Neue Aufbewahrungsrichtlinie** aus, um den Assistenten zum Erstellen einer Aufbewahrungsrichtlinie zu starten, und benennen Sie die neue Aufbewahrungsrichtlinie.

3. Wählen Sie für die Seite **Speicherorte für die Anwendung der Richtlinie auswählen** einen oder beide Speicherorte für Teams aus: **Teams Kanalnachricht** und **Teams Chats**.
     
    Bei **Teams-Kanalnachrichten** sind Nachrichten von Standardkanälen, jedoch nicht von [privaten Kanälen](https://docs.microsoft.com/microsoftteams/private-channels) eingeschlossen. Zurzeit werden private Kanäle von Aufbewahrungsrichtlinien nicht unterstützt.
    
    Standardmäßig sind [alle Teams und alle Benutzer ausgewählt](#a-policy-that-applies-to-entire-locations), aber Sie können dies verfeinern, indem Sie die Optionen [**Auswählen** und **Ausschließen** auswählen](#a-policy-with-specific-inclusions-or-exclusions).

4. Geben Sie auf der Assistentenseite **Entscheiden, ob Inhalte beibehalten werden, gelöscht werden oder beides** die Konfigurationsoptionen für das Beibehalten und Löschen von Inhalten an.
    
    Sie können eine Aufbewahrungsrichtlinie erstellen, die Inhalte nur aufbewahrt, ohne sie zu löschen, die sie aufbewahrt und nach einem festgelegten Zeitraum löscht, oder Inhalte nur nach einem bestimmten Zeitraum löscht. Weitere Informationen finden Sie unter [Einstellungen für die Aufbewahrung und Löschung von Inhalten](#settings-for-retaining-and-deleting-content) auf dieser Seite.
    
5. Schließen Sie den Assistenten ab, damit Ihre Einstellungen gespeichert werden.

Weitere Informationen zu Aufbewahrungsrichtlinien für Teams finden Sie unter [Aufbewahrungsrichtlinien in Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies) in der Teams-Dokumentation.

#### <a name="additional-retention-policy-needed-to-support-teams"></a>Weitere für die Unterstützung von Teams benötigte Aufbewahrungsrichtlinie

Teams bietet mehr als nur Chats und Kanalnachrichten. Wenn Sie Teams verwenden, die aus einer Microsoft 365-Gruppe (früher Office 365-Gruppe) erstellt wurden, sollten Sie zusätzlich eine Aufbewahrungsrichtlinie konfigurieren, die diese Microsoft 365-Gruppe einschließt, indem Sie den Speicherort **Office 365-Gruppen** verwenden. Diese Aufbewahrungsrichtlinie gilt für Inhalte in Postfach, Website und Dateien der Gruppe.

Wenn Sie Teamwebsites haben, die mit keiner Microsoft 365-Gruppe verbunden sind, benötigen Sie eine Aufbewahrungsrichtlinie, die die Speicherorte **SharePoint-Websites** oder **OneDrive-Konten** einschließt, um Dateien in Teams aufzubewahren und zu löschen:

- In einem Chat freigegebene Dateien werden im OneDrive-Konto des Benutzers gespeichert, der sie freigegeben hat. 

- In Kanäle hochgeladene Dateien werden auf der SharePoint-Website für das Team gespeichert.

> [!TIP]
> Sie können eine Aufbewahrungsrichtlinie nur auf die Dateien eines bestimmten Teams anwenden, wenn dieses mit keiner Microsoft 365-Gruppe verbunden ist, indem Sie die SharePoint-Website für das Team und die OneDrive-Konten der Benutzer im Team auswählen.

Es kann vorkommen, dass eine Aufbewahrungsrichtlinie, die auf Microsoft 365-Gruppen, SharePoint-Websites oder OneDrive-Konten angewendet wird, eine Datei löscht, die in einer Teams Chat- oder Kanalnachricht erwähnt wird, bevor diese Nachrichten gelöscht werden. In diesem Szenario wird die Datei in der Microsoft Teams-Nachricht weiterhin angezeigt, aber wenn Benutzer die Datei auswählen, wird der Fehler "Datei nicht gefunden" angezeigt. Dieses Verhalten gilt nicht für Aufbewahrungsrichtlinien. Dies kann auch passieren, wenn ein Benutzer eine Datei aus SharePoint oder OneDrive manuell löscht.


### <a name="retention-policy-for-locations-other-than-teams"></a>Aufbewahrungsrichtlinie für andere Speicherorte als Teams

1. Wählen Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) die Option **Richtlinien** > **Aufbewahrung** aus.

2. Wählen Sie **Neue Aufbewahrungsrichtlinie** aus, um den Assistenten zum Erstellen einer Aufbewahrungsrichtlinie zu starten, und benennen Sie die neue Aufbewahrungsrichtlinie.

3. Auf der Seite **Speicherorte auswählen** können Sie jeden Speicherort mit Ausnahme der Speicherorte für Teams ein- oder ausschalten. Sie können die Richtlinie für jeden Speicherort bei der Standardeinstellung belassen, um [die Richtlinie auf den gesamten Speicherort anzuwenden ](#a-policy-that-applies-to-entire-locations), oder [Ein- und Ausschlüsse angeben](#a-policy-with-specific-inclusions-or-exclusions). 
    
    Spezifische Informationen zu Speicherorten:
    - [Exchange-E-Mail und öffentliche Exchange-Ordner](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [SharePoint-Websites und OneDrive-Konten](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [Office 365-Gruppen](#configuration-information-for-microsoft-365-groups)
    - [Skype for Business](#configuration-information-for-skype-for-business)

4. Geben Sie auf der Assistentenseite **Entscheiden, ob Inhalte beibehalten werden, gelöscht werden oder beides** die Konfigurationsoptionen für das Beibehalten und Löschen von Inhalten an.
    
    Sie können eine Aufbewahrungsrichtlinie erstellen, die Inhalte nur aufbewahrt, ohne sie zu löschen, die sie aufbewahrt und nach einem festgelegten Zeitraum löscht, oder Inhalte nur nach einem bestimmten Zeitraum löscht. Weitere Informationen finden Sie unter [Einstellungen für die Aufbewahrung und Löschung von Inhalten](#settings-for-retaining-and-deleting-content) auf dieser Seite.

5. Schließen Sie den Assistenten ab, damit Ihre Einstellungen gespeichert werden.


#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a>Konfigurationsinformationen für Exchange-E-Mail und öffentliche Exchange-Ordner

Der Speicherort von **Exchange-E-Mail** unterstützt die Aufbewahrung von E-Mail-, Kalender- und anderen Postfachelementen der Benutzer, indem die Aufbewahrungseinstellungen auf Postfachebene angewendet werden.

Folgende E-Mail-Elemente werden einbezogen: E-Mail-Nachrichten (einschließlich Entwürfe) mit beliebigen Anlagen, Aufgaben und Kalendereinträge, wenn sie ein Enddatum haben, sowie Notizen. Kontakte und alle Aufgaben und Kalenderelemente, die kein Enddatum aufweisen, werden nicht einbezogen. Andere in einem Postfach gespeicherte Elemente, z. B. gespeicherte Skype- und Teams-Nachrichten, werden mit diesem Speicherort nicht einbezogen. Diese Elemente haben eigene Aufbewahrungsorte.

Obwohl eine Microsoft 365-Gruppe über ein Exchange-Postfach verfügt, bezieht eine Aufbewahrungsrichtlinie, die den gesamten **Exchange-E-Mail-Speicherort** umfasst, keine Inhalte in Microsoft 365-Gruppenpostfächern mit ein. Wenn Sie Inhalte in diesen Postfächern beibehalten möchten, wählen Sie den **Office 365-Gruppen**-Speicherort aus.

Der Speicherort von **öffentlichen Exchange-Ordnern** wendet die Aufbewahrungseinstellungen auf alle öffentlichen Ordner an und kann nicht auf der Ordner- oder Postfachebene angewendet werden.

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a>Konfigurationsinformationen für SharePoint-Websites und OneDrive-Konten

Wenn Sie den Speicherort Ihrer **SharePoint-Websites** auswählen, kann Ihre Aufbewahrungsrichtlinie Inhalte auf SharePoint-Kommunikationswebsites, auf Teamwebsites, die nicht über Office 365-Gruppen verbunden sind, und auf klassischen Websites beibehalten und löschen. Teamwebsites, die über Office 365-Gruppen verbunden sind, werden bei dieser Option nicht unterstützt. Verwenden Sie stattdessen die **Office 365-Gruppen**-Speicherorte, die sich auf das Postfach der Gruppe, deren Website und Dateien auswirken.

Obwohl die Aufbewahrungsrichtlinie auf Websiteebene angewendet wird, werden Aufbewahrungseinstellungen nur auf Dokumente angewendet. Aufbewahrungseinstellungen gelten nicht für Organisationsstrukturen, die Bibliotheken, Listen und Ordner innerhalb der Website umfassen. 

Wenn Sie Ihre Speicherorte für SharePoint-Websites oder OneDrive-Konten angeben, benötigen Sie keine Berechtigungen für den Zugriff auf die Websites und es erfolgt keine Validierung, wenn Sie die URL auf der Seite **Speicherorte bearbeiten** angeben. Die SharePoint-Websites müssen jedoch indiziert werden, und die von Ihnen angegebenen Websites werden vom Assistenten dahingehend überprüft, ob sie existieren.

Wenn die Überprüfung fehlschlägt, wird eine Meldung angezeigt, die besagt, dass die Überprüfung für die eingegebene URL fehlgeschlagen ist. Der Assistent erstellt die Aufbewahrungsrichtlinie erst, wenn die Überprüfung erfolgreich war. Wenn diese Meldung angezeigt wird, wechseln Sie zurück in den Assistenten, um die URL zu ändern oder die Website aus der Aufbewahrungsrichtlinie zu entfernen.

Wenn Sie einzelne OneDrive-Konten angeben möchten, die ein- oder ausgeschlossen werden sollen, hat die URL das folgende Format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`

Beispielsweise bei einem Benutzer im Mandanten „Contoso“, der den Benutzernamen „rsimone“ hat: `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`

Informationen zum Überprüfen der Syntax für Ihren Mandanten und zum Identifizieren von URLs für Benutzer finden Sie unter [Abrufen einer Liste aller Benutzer OneDrive-URLs in Ihrer Organisation](https://docs.microsoft.com/onedrive/list-onedrive-urls).

### <a name="configuration-information-for-microsoft-365-groups"></a>Konfigurationsinformationen für Microsoft 365-Gruppen

Wenn Sie Inhalte für eine Microsoft 365-Gruppe (vormals Office 365-Gruppe) aufbewahren oder löschen möchten, verwenden Sie den **Office 365-Gruppen**-Speicherort. Obwohl eine Microsoft 365-Gruppe über ein Exchange-Postfach verfügt, bezieht eine Aufbewahrungsrichtlinie, die den gesamten **Exchange-E-Mail-Speicherort** umfasst, keine Inhalte in Microsoft 365-Gruppenpostfächern mit ein. Obwohl der **Exchange-E-Mail-Speicherort** zunächst die Angabe eines Gruppenpostfachs zum Einschließen oder Ausschließen zulässt, erhalten Sie beim Versuch, die Aufbewahrungsrichtlinie zu speichern, die Fehlermeldung, dass "RemoteGroupMailbox" keine gültige Auswahl für den Exchange-Speicherort ist.

Eine auf eine Microsoft 365-Gruppe angewandte Aufbewahrungsrichtlinie umfasst das Gruppenpostfach und die Teams-Website, wenn eine Teams-Website bei der Erstellung der Gruppe ausgewählt oder später der Gruppe hinzugefügt wurde. Dateien, die auf der Teams-Website gespeichert sind, werden mit diesem Standort abgedeckt. Nicht jedoch Teams-Chats oder Nachrichten im Teams-Channel, die ihre eigenen Standorte für Aufbewahrungsrichtlinien haben.

### <a name="configuration-information-for-skype-for-business"></a>Konfigurationsinformationen für Skype for Business

Im Gegensatz zu Exchange-E-Mails kann der Status des Skype-Speicherorts nicht einfach aktiviert werden, um alle Benutzer automatisch einzuschließen. Wenn Sie diesen Speicherort jedoch aktivieren, müssen Sie anschließend manuell die Benutzer auswählen, deren Unterhaltungen Sie aufbewahren möchten:

![Auswählen des Skype-Speicherorts für Aufbewahrungsrichtlinien](../media/skype-location-retention-policies.png)
  
Bei Auswahl von **Benutzer auswählen** können Sie schnell alle Benutzer hinzufügen, indem Sie das Kontrollkästchen **Alle auswählen** aktivieren. Es ist jedoch wichtig zu wissen, dass jeder Benutzer als ein bestimmtes eingeschlossenes Element in der Richtlinie zählt. Wenn Sie also 1.000-Benutzer hinzufügen, indem Sie das Kontrollkästchen **Alle auswählen** aktivieren, entspricht das dem manuellen Auswählen von 1.000 einzuschließenden Benutzern. Dies ist die maximale unterstützte Anzahl von Skype for Business-Benutzern.

Achtung: **Aufgezeichnete Unterhaltungen**, ein Ordner in Outlook, ist eine Funktion, die nichts mit der Skype-Archivierung zu tun hat. Die Option **Aufgezeichnete Unterhaltungen** kann vom Endbenutzer deaktiviert werden, die Archivierung für Skype erfolgt jedoch durch das Speichern einer Kopie von Skype-Unterhaltungen in einem ausgeblendeten Ordner, auf den die Benutzer nicht zugreifen können, der aber für eDiscovery verfügbar ist.

## <a name="settings-for-retaining-and-deleting-content"></a>Einstellungen für die Aufbewahrung und Löschung von Inhalten

Wenn Sie die Einstellungen für die Aufbewahrung und Löschung von Inhalten in Ihrer Aufbewahrungsrichtlinie festlegen, wird für Ihre Aufbewahrungsrichtlinie eine der folgenden Konfigurationen für einen bestimmten Zeitraum gelten:

- Nur aufbewahren
    
    Wählen Sie für diese Konfiguration **Elemente für einen bestimmten Zeitraum aufbewahren** und **Am Ende des Aufbewahrungszeitraums: Nichts unternehmen**. Oder wählen Sie **Elemente für immer aufbewahren**aus.

- Aufbewahren und dann löschen
    
    Wählen Sie für diese Konfiguration **Elemente für einen bestimmten Zeitraum aufbewahren** und **Am Ende des Aufbewahrungszeitraums: Elemente automatisch löschen**.

- Nur löschen
    
    Wählen Sie für diese Konfiguration **Elemente erst löschen, wenn sie ein bestimmtes Alter erreichen** aus.

### <a name="retaining-content-for-a-specific-period-of-time"></a>Aufbewahren von Inhalten für einen bestimmten Zeitraum

Beim Konfigurieren einer Aufbewahrungsrichtlinie können Sie festlegen, ob Elemente für eine bestimmte Anzahl von Tagen, Monaten oder Jahren aufbewahrt werden sollen. Alternativ können Sie die Elemente für immer aufbewahren.

Beim Konfigurieren einer Aufbewahrungsrichtlinie können Sie festlegen, ob Inhalte zeitlich unbegrenzt oder für eine bestimmte Anzahl von Tagen, Monaten oder Jahren aufbewahrt werden sollen. Der Aufbewahrungszeitraum wird anhand des Alters der Inhalte und nicht anhand des Anwendungsdatums der Aufbewahrungsrichtlinie berechnet. 

Als Beginn des Aufbewahrungszeitraums können Sie auch auswählen, wann der Inhalt erstellt wurde oder – nur unterstützt für Dateien und die SharePoint-, OneDrive-und Office 365-Speicherorte – wann der Inhalt zuletzt geändert wurde.

Beispiele:
  
- SharePoint: Wenn Elemente einer Websitesammlung sieben Jahre lang nach der letzten Änderung des Inhalts aufbewahrt werden sollen, und ein Dokument in dieser Websitesammlung seit sechs Jahren nicht geändert wurde, wird es nur noch ein weiteres Jahr aufbewahrt, sofern es in diesem Zeitraum nicht geändert wird. Falls das Dokument wieder geändert wird, wird das Alter des Dokuments ab dem neuen Datum der letzten Änderung berechnet und weitere sieben Jahre lang aufbewahrt.
  
- Exchange: Wenn Elemente in einem Postfach für sieben Jahre aufbewahrt werden sollen und eine Nachricht vor sechs Jahren gesendet wurde, wird sie nur noch ein Jahr aufbewahrt. Bei Exchange-Elementen basiert das Alter auf dem Empfangsdatum für eingehende E-Mails oder dem Sendedatum für ausgehende E-Mails. Die Aufbewahrung von Elementen basierend auf der letzten Änderung gilt nur für Websiteinhalte in OneDrive und SharePoint.
  
Am Ende des Aufbewahrungszeitraums können Sie wählen, ob der Inhalt dauerhaft gelöscht werden soll:
  
![Ordneraufbewahrungseinstellungen](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
### <a name="deleting-content-thats-older-than-a-specific-age"></a>Löschen von Inhalten, die ein bestimmtes Alter überschritten haben

Eine Aufbewahrungsrichtlinie kann Elemente sowohl aufbewahren und dann löschen, oder alte Elemente löschen, ohne sie aufzubewahren.
  
In beiden Fällen ist es wichtig zu wissen, dass wenn Ihre Aufbewahrungsrichtlinie Elemente löscht, der für eine Aufbewahrungsrichtlinie festgelegte Zeitraum jedes Mal ab dem Zeitpunkt berechnet wird, als das betreffende Element erstellt oder geändert wurde und nicht ab dem Zeitpunkt, als die die Richtlinie zugewiesen wurde.

Sie sollten also vor dem erstmaligen Zuweisen einer Aufbewahrungsrichtlinie, und vor allem wenn diese Richtlinie Elemente löscht, zunächst das Alter des vorhandenen Inhalts und die möglichen Auswirkungen der Richtlinie auf diesen vorhandenen Inhalt bedenken. Sie könnten außerdem vor dem Zuweisen Ihre Benutzer über die neue Richtlinie informieren, um ihnen Zeit zur Auswertung der möglichen Auswirkungen zu geben.

### <a name="a-policy-that-applies-to-entire-locations"></a>Eine Richtlinie, die für ganze Speicherorte gilt

Wenn Sie Speicherorte auswählen – mit Ausnahme von Skype for Business – lautet die Standardeinstellung **Alle**, wenn der Status des Speicherorts auf **An** gesetzt ist.
  
Wenn eine Aufbewahrungsrichtlinie auf eine beliebige Kombination ganzer Speicherorte zutrifft, gibt es keine Beschränkung für die Anzahl der Empfänger, Websites, Konton, Gruppen, etc., die diese Richtlinie umfassen kann. 

Wenn eine Richtlinie beispielsweise alle Exchange-E-Mails und alle SharePoint-Websites umfasst, werden alle Websites und Empfänger einbezogen, ganz gleich, wie viele es sind. Bei Exchange erben alle neuen Postfächer, die nach der Anwendung der Richtlinie erstellt werden, die Richtlinie automatisch.

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>Richtlinien, die bestimmte Elemente einschließen oder ausschließen

Sie können eine Aufbewahrungsrichtlinie auch nur auf bestimmte Benutzer, bestimmte Microsoft 365-Gruppen oder bestimmte Websites anwenden. Stellen Sie dafür sicher, dass der **Status** des entsprechenden Speicherorts **An** ist, und verwenden Sie dann die Links, um bestimmte Benutzer, Microsoft 365-Gruppen oder Websites ein- oder auszuschließen. 
  
Allerdings gibt es bei der Verwendung dieser Konfiguration einige Einschränkungen, wenn Ihre Aufbewahrungsrichtlinie mehr als 1.000 bestimmte Objekte einschließt oder ausschließt:
  
- Maximale Anzahl für die Aufbewahrungsrichtlinie:
    - 1.000 Postfächer
    - 1.000 Microsoft 365-Gruppen
    - 1.000 Benutzer für private Teams-Chats
    - 100 Websites (OneDrive oder SharePoint)

Für einen Mandanten wird eine maximale Anzahl von 10.000 Richtlinien unterstützt. Hierzu zählen Aufbewahrungsrichtlinien, Aufbewahrungsbezeichnungsrichtlinien und automatisch angewendete Aufbewahrungsrichtlinien.

Sollten Ihre Aufbewahrungsrichtlinien voraussichtlich von diesen Beschränkungen betroffen sein, wählen Sie die Konfigurationsoptionen aus, die für ganze Speicherorte gelten.

> [!WARNING]
> Wenn Sie Einschlüsse konfigurieren und dann den letzten entfernen, wird die Konfiguration für den Speicherort auf **Alle** zurückgesetzt.  Vergewissern Sie sich, dass dies die von Ihnen beabsichtigte Konfiguration ist, bevor Sie die Richtlinie speichern.
> 
> Wenn Sie beispielsweise eine einzelne SharePoint-Website für den Einschluss in Ihre Aufbewahrungsrichtlinie angeben, die für das Löschen von Daten konfiguriert ist, und dann die einzelne Website entfernen, unterliegen standardmäßig alle SharePoint-Websites der Aufbewahrungsrichtlinie, die Daten endgültig löscht. Gleiches gilt für Einschlüsse für Exchange-Empfänger, OneDrive-Konten, Teams Chat-Benutzer usw.
> 
> In diesem Szenario können Sie den Speicherort deaktivieren, wenn Sie nicht möchten, dass die Einstellung **Alle** für den Speicherort der Aufbewahrungsrichtlinie unterliegt. Alternativ können Sie Ausschlüsse angeben, die von der Richtlinie ausgenommen werden sollen.

## <a name="updating-retention-policies"></a>Aktualisieren von Aufbewahrungsrichtlinien

Wenn Sie eine Aufbewahrungsrichtlinie bearbeiten und Elemente bereits den ursprünglichen Einstellungen in Ihrer Aufbewahrungsrichtlinie unterliegen, werden die aktualisierten Einstellungen automatisch zusätzlich auf diese sowie auf neu ermittelte Elemente angewendet.

Diese Aktualisierung erfolgt normalerweise ziemlich schnell, kann aber mehrere Tage dauern. Wenn die Richtlinienreplikation auf Ihre Microsoft 365-Speicherorte abgeschlossen ist, ändert sich der Status der Aufbewahrungsrichtlinie im Microsoft 365 Compliance Center von **Ein (ausstehend)** zu **Ein (erfolgreich)**.

## <a name="lock-a-retention-policy-by-using-powershell"></a>Sperren einer Aufbewahrungsrichtlinie mit PowerShell

Sie müssen PowerShell verwenden, wenn Sie eine [Aufbewahrungssperre](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements) zur Einhaltung gesetzlicher Vorschriften benötigen. Weil Administratoren nach dem Anwenden einer Aufbewahrungssperre eine Aufbewahrungsrichtlinie nicht deaktivieren oder löschen können, kann dieses Feature in der Benutzeroberfläche nicht aktiviert werden, um eine unbeabsichtigte Konfiguration zu verhindern.

Alle Aufbewahrungsrichtlinien mit beliebiger Konfiguration unterstützen die Aufbewahrungssperre. Wenn Sie aber die folgenden PowerShell-Befehle verwenden, werden Sie feststellen, dass der Parameter **Workload** immer **Exchange, SharePoint, OneDriveForBusines, Skype, ModernGroup** statt der in der Richtlinie konfigurierten tatsächlichen Arbeitslasten anzeigt. Dies ist lediglich ein Anzeigeproblem.

1. [Stellen Sie eine Verbindung mit der Security & Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Führen Sie zum Anzeigen einer Liste Ihrer Aufbewahrungsrichtlinien und zum Suchen nach dem Namen der Richtlinie, die Sie sperren möchten, den Befehl [Get-RetentionCompliancePolicy](https://powershell/module/exchange/get-retentioncompliancepolicy) aus. Zum Beispiel:
    
   ![Liste der Aufbewahrungsrichtlinien in PowerShell](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)
    
3. Wenn Sie eine Aufbewahrungssperre auf eine Aufbewahrungsrichtlinie anwenden möchten, führen Sie das Cmdlet [Set-RetentionCompliancePolicy]( ) mit dem Namen der Aufbewahrungsrichtlinie aus, und legen Sie den Parameter *RestrictiveRetention* auf „true“ fest:
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    Zum Beispiel:
    
    ![RestrictiveRetention-Parameter in PowerShell](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     Wenn Sie dazu aufgefordert werden, lesen und bestätigen Sie die Einschränkungen, die in dieser Konfiguration enthalten sind, indem Sie **J** eingeben:
    
   ![Aufforderung zur Bestätigung der Sperre einer Aufbewahrungsrichtlinie in PowerShell](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

Eine Aufbewahrungssperre wird jetzt zur Aufbewahrungsrichtlinie hinzugefügt. Führen Sie `Get-RetentionCompliancePolicy` zur Bestätigung erneut aus, geben Sie aber den Namen der Aufbewahrungsrichtlinie an, und zeigen Sie die Richtlinienparameter an:

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

Sie sollten sehen, dass **RestrictiveRetention** auf **True** festgelegt wurde. Zum Beispiel:

![Gesperrte Richtlinie mit allen Parametern in PowerShell](../media/retention-policy-preservation-lock-locked-policy.PNG)
  

