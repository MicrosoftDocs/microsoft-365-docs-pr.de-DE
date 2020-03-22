---
title: Verwalten der Postfächern
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: Die postfachüberwachungsprotokollierung ist in Office 365 standardmäßig aktiviert (wird standardmäßig auch als standardmäßige postfachüberwachung oder postfachüberwachung bezeichnet). Dies bedeutet, dass bestimmte Aktionen, die von Postfachbesitzern, Stellvertretern und Administratoren ausgeführt werden, automatisch in einem postfachüberwachungsprotokoll protokolliert werden, in dem Sie nach Aktivitäten für das Postfach suchen können.
ms.openlocfilehash: 2b69d63e63e049566c9827f08d2ead592b918684
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894920"
---
# <a name="manage-mailbox-auditing"></a>Verwalten der Postfächern

Ab Januar 2019 wird Microsoft die postfachüberwachungsprotokollierung standardmäßig für alle Office 365 Organisationen aktivieren. Dies bedeutet, dass bestimmte Aktionen, die von Postfachbesitzern, Stellvertretern und Administratoren ausgeführt werden, automatisch protokolliert werden und dass die entsprechenden Post Fach Überwachungseinträge verfügbar sind, wenn Sie im postfachüberwachungsprotokoll nach diesen suchen. Bevor die postfachüberwachung standardmäßig aktiviert wurde, muss Sie für jedes Benutzerpostfach in Ihrer Organisation manuell aktiviert werden.

Hier sind einige Vorteile der postfachüberwachung standardmäßig aktiviert:

- Die Überwachung wird automatisch aktiviert, wenn Sie ein neues Postfach erstellen. Sie müssen Sie nicht manuell für neue Benutzer aktivieren.

- Sie müssen die überwachten Postfachaktionen nicht verwalten. Eine vordefinierte Gruppe von Postfachaktionen wird standardmäßig für jeden Anmeldetyp (Administrator, Stellvertreter und Besitzer) überwacht.

- Wenn Microsoft eine neue Post Fach Aktion (insbesondere Aktionen, die zum Schutz Ihrer Organisation und zur Unterstützung bei forensischen Untersuchungen beitragen) veröffentlicht, wird die Aktion automatisch der Liste der Postfachaktionen hinzugefügt, die standardmäßig überwacht werden. Dies bedeutet, dass Sie keine Überwachung Hinzufügen neuer Aktionen für Postfächer benötigen.

- Sie verfügen über eine konsistente Überwachungsrichtlinie für Postfächer in Ihrer Organisation (da Sie die gleichen Aktionen für alle Postfächerüber Wachen).

> [!NOTE]
>* Das wichtigste, was Sie über die Veröffentlichung der postfachüberwachung in der Standardeinstellung wissen sollten, ist: Sie müssen nichts Unternehmen, um die postfachüberwachung zu verwalten. Um weitere Informationen zu erhalten, die postfachüberwachung von den Standardeinstellungen anzupassen oder Sie ganz zu deaktivieren, kann Ihnen dieses Thema helfen. <br><br>* Standardmäßig sind nur Post Fach Überwachungsereignisse für E5-Benutzer in Überwachungsprotokoll suchen im Security & Compliance Center oder über die Office 365-Verwaltungs Aktivitäts-API verfügbar. Weitere Informationen finden Sie im Abschnitt [Weitere Informationen](#more-information) in diesem Thema.

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>Überprüfen, ob die postfachüberwachung standardmäßig aktiviert ist

Um zu überprüfen, ob die postfachüberwachung für Ihre Organisation standardmäßig aktiviert ist, führen Sie den folgenden Befehl in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)aus:

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

Der Wert **false** gibt an, dass die postfachüberwachung standardmäßig für die Organisation aktiviert ist. Dieser Wert wird standardmäßig auf die Einstellung für die postfachüberwachung für bestimmte Postfächerüber schrieben. Wenn beispielsweise die postfachüberwachung für ein Postfach deaktiviert ist (die *AuditEnabled* -Eigenschaft ist für das Postfach **false** ), werden die standardmäßigen Postfachaktionen weiterhin für das Postfach überwacht, da die postfachüberwachung standardmäßig für die Organisation aktiviert ist.

Damit die postfachüberwachung für bestimmte Postfächer deaktiviert bleibt, konfigurieren Sie die Post Fach Überwachungsumgehung für den Postfachbesitzer und andere Benutzer, denen der Zugriff auf das Postfach delegiert wurde. Weitere Informationen finden Sie im Abschnitt [umgehen der postfachüberwachungsprotokollierung](#bypass-mailbox-audit-logging) in diesem Thema.

> [!NOTE]
> Wenn die postfachüberwachung für die Organisation standardmäßig aktiviert ist, wird die *AuditEnabled* -Eigenschaft für betroffene Postfächer nicht von **false** in **true**geändert. In anderen Worten: bei der postfachüberwachung wird standardmäßig die *AuditEnabled* -Eigenschaft für Postfächer ignoriert.

## <a name="supported-mailbox-types"></a>Unterstützte Postfachtypen

In der folgenden Tabelle sind die Postfachtypen aufgeführt, die derzeit standardmäßig von der postfachüberwachung unterstützt werden:

|**Postfachtyp**|**Unterstützt**|**Nicht unterstützt**|
|:---------|:---------:|:---------:|
|Benutzerpostfächer|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|Freigegebene Postfächer|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|Office 365 Gruppen Postfächer|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|Ressourcenpostfächer||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Postfächer für öffentliche Ordner||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|

## <a name="logon-types-and-mailbox-actions"></a>Anmeldetypen und Postfachaktionen

Anmeldetypen klassifizieren Sie den Benutzer, der die überwachten Aktionen für das Postfach ausgeführt hat. In der folgenden Liste werden die Anmeldetypen beschrieben, die in der postfachüberwachungsprotokollierung verwendet werden:

- **Besitzer**: der Postfachbesitzer (das Konto, das dem Postfach zugeordnet ist).

- **Delegate**:

  - Ein Benutzer, dem die Berechtigung "Sends", "SendOnBehalf" oder "FullAccess" für ein anderes Postfach zugewiesen wurde.

  - Ein Administrator, dem die Berechtigung FullAccess für das Postfach eines Benutzers zugewiesen wurde.

- **Admin**:

  - Das Postfach wird mit einem der folgenden Microsoft eDiscovery-Tools durchsucht:

    - Inhaltssuche im Compliance Center.

    - eDiscovery oder erweiterte eDiscovery im Compliance Center.

    - In-Place-eDiscovery in Exchange Online.

  - Auf das Postfach wird mithilfe des Exchange Server MAPI-Editors zugegriffen.

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>Postfachaktionen für Benutzerpostfächer und freigegebene Postfächer

In der folgenden Tabelle werden die Postfachaktionen beschrieben, die in der postfachüberwachungsprotokollierung für Benutzerpostfächer und freigegebene Postfächer zur Verfügung stehen.

- Ein Häkchen ( ![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)) gibt an, dass die Post Fach Aktion für den Anmeldetyp protokolliert werden kann (nicht alle Aktionen stehen für alle Anmeldetypen zur Verfügung).

- Ein Sternchen ( <sup>\*</sup> ) nach dem Häkchen gibt an, dass die Post Fach Aktion für den Anmeldetyp standardmäßig protokolliert wird.

- Denken Sie daran, dass ein Administrator mit der Berechtigung "Vollzugriff" für ein Postfach als Stellvertreter betrachtet wird.

|**Post Fach Aktion**|**Beschreibung**|**Administrator**|**Stellvertretung**|**Besitzer**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**AddFolderPermissions**|**Hinweis**: Obwohl dieser Wert als Post Fach Aktion akzeptiert wird, ist er bereits in der **UpdateFolderPermissions** -Aktion enthalten und wird nicht separat überwacht. Mit anderen Worten: Verwenden Sie diesen Wert nicht.||||
|**ApplyRecord**|Ein Element wird als Datensatz gekennzeichnet.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Kopieren**|Eine Nachricht wurde in einen anderen Ordner kopiert.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|**Create**|Ein Element wurde im Ordner "Kalender", "Kontakte", "Notizen" oder "Aufgaben" im Postfach erstellt (beispielsweise wird eine neue Besprechungsanfrage erstellt). Beachten Sie, dass das Erstellen, Senden oder Empfangen einer Nachricht nicht überwacht wird. Auch das Erstellen eines Postfachordners wird nicht überwacht.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Standard**||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**FolderBind**|Auf einen Postfachordner wurde zugegriffen. Diese Aktion wird auch protokolliert, wenn der Administrator oder der delegierte Benutzer das Postfach öffnet.<br/><br/> **Hinweis**: Überwachungseinträge für von Delegaten ausgeführte Ordner Bindungs Aktionen werden konsolidiert. Für den Zugriff auf einzelne Ordner innerhalb eines Zeitraums von 24 Stunden wird ein Überwachungseintrag generiert.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|**HardDelete**|Eine Nachricht wurde endgültig aus dem Ordner "Wiederherstellbare Elemente" gelöscht.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MailItemsAccessed**|Auf e-Mail-Daten wird über e-Mail-Protokolle und-Clients zugegriffen. Dieser Wert steht nur für Benutzer von E5-oder E5-Konformitäts Abonnements zur Verfügung. Ausführliche Informationen finden Sie unter [Access to wichtige Events for Investigations](advanced-audit.md#access-to-crucial-events-for-investigations).|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MailboxLogin**|Der Benutzer hat sich bei seinem Postfach angemeldet. |||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**MessageBind**|Eine Nachricht wurde im Vorschaubereich angezeigt oder von einem Administrator geöffnet. **Hinweis**: Obwohl dieser Wert als Post Fach Aktion akzeptiert wird, werden diese Aktionen nicht mehr protokolliert.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|**ModifyFolderPermissions**|**Hinweis**: Obwohl dieser Wert als Post Fach Aktion akzeptiert wird, ist er bereits in der **UpdateFolderPermissions** -Aktion enthalten und wird nicht separat überwacht. Mit anderen Worten: Verwenden Sie diesen Wert nicht.||||
|**Verschieben**|Eine Nachricht wurde in einen anderen Ordner verschoben.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**MoveToDeletedItems**|Eine Nachricht wurde gelöscht und in den Ordner „Gelöschte Objekte“ verschoben.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**RecordDelete**|Ein Element, das als Datensatz gekennzeichnet ist, wurde vorläufig gelöscht (in den Ordner "refundable Items" verschoben). Elemente, die als Datensätze bezeichnet werden, können nicht dauerhaft gelöscht werden (bereinigt aus dem Ordner "Wiederherstellbare Elemente").|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**RemoveFolderPermissions**|**Hinweis**: Obwohl dieser Wert als Post Fach Aktion akzeptiert wird, ist er bereits in der **UpdateFolderPermissions** -Aktion enthalten und wird nicht separat überwacht. Mit anderen Worten: Verwenden Sie diesen Wert nicht.||||
|**SendAs**|Eine Nachricht wurde mithilfe der SendAs-Berechtigung gesendet. Das bedeutet, dass ein anderer Benutzer die Nachricht so gesendet hat, dass sie vom Postfachbesitzer zu kommen scheint.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SendOnBehalf**|Eine Nachricht wurde mithilfe der SendOnBehalf-Berechtigung gesendet. Das bedeutet, dass ein anderer Benutzer die Nachricht im Namen des Postfachbesitzers gesendet hat. Für den Empfänger ist in der Nachricht angegeben, in wessen Namen die Nachricht gesendet wurde und wer die Nachricht tatsächlich gesendet hat.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SoftDelete**|Eine Nachricht wurde dauerhaft gelöscht oder aus dem Ordner „Gelöschte Objekte“ gelöscht. Vorübergehend gelöschte Elemente werden in den Ordner „Wiederherstellbare Elemente“ verschoben.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**Update**|Eine Nachricht oder deren Eigenschaften wurden geändert.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|Eine Kalender Delegierung wurde einem Postfach zugewiesen. Der Stellvertretungszugriff gibt anderen Personen in der gleichen Organisation die Berechtigung zum Verwalten des Kalenders des Postfachbesitzers.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateComplianceTag**|Eine andere Aufbewahrungs Bezeichnung wird auf ein e-Mail-Element angewendet (einem Element kann nur eine Aufbewahrungs Bezeichnung zugewiesen werden).|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**UpdateFolderPermissions**|Eine Ordnerberechtigung wurde geändert. Ordnerberechtigungen steuern, welche Benutzer in Ihrer Organisation auf Ordner in einem Postfach zugreifen können und welche Nachrichten sich in diesen Ordnern befinden.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateInboxRules**|Eine Posteingangsregel wurde hinzugefügt, entfernt oder geändert. Posteingangsregeln werden verwendet, um Nachrichten im Posteingang des Benutzers basierend auf den angegebenen Bedingungen zu verarbeiten und Aktionen zu ergreifen, wenn die Bedingungen einer Regel erfüllt sind, beispielsweise das Verschieben einer Nachricht in einen angegebenen Ordner oder das Löschen einer Nachricht.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|

> [!IMPORTANT]
> Wenn Sie die Postfachaktionen zur Überwachung für einen beliebigen Anmeldetyp angepasst haben, *bevor* die postfachüberwachung in Ihrer Organisation standardmäßig aktiviert wurde, werden die benutzerdefinierten Einstellungen im Postfach beibehalten und von den standardmäßigen Postfachaktionen nicht überschrieben, wie in diesem Abschnitt beschrieben. Wenn Sie die Überwachungs Postfachaktionen auf ihre Standardwerte zurücksetzen möchten (was Sie jederzeit tun können), lesen Sie den Abschnitt [Wiederherstellen der standardmäßigen Postfachaktionen](#restore-the-default-mailbox-actions) weiter unten in diesem Thema.

### <a name="mailbox-actions-for-office-365-group-mailboxes"></a>Postfachaktionen für Office 365 Gruppen Postfächer

Die postfachüberwachung aktiviert standardmäßig die postfachüberwachungsprotokollierung in Office 365 Gruppen Postfächer, aber Sie können nicht anpassen, was protokolliert wird (Sie können keine Postfachaktionen hinzufügen oder entfernen, die für einen beliebigen Anmeldetyp protokolliert werden).

In der folgenden Tabelle werden die Postfachaktionen beschrieben, die standardmäßig in Office 365 Gruppen Postfächern für die einzelnen Anmeldetypen protokolliert werden.

Denken Sie daran, dass ein Administrator mit der Berechtigung "Vollzugriff" für ein Office 365 Gruppenpostfach als Stellvertreter betrachtet wird.

|**Post Fach Aktion**|**Beschreibung**|**Administrator**|**Stellvertretung**|**Besitzer**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**Create**|Erstellen eines Kalenderelements. Beachten Sie, dass das Erstellen, Senden oder Empfangen einer Nachricht nicht überwacht wird.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**HardDelete**|Eine Nachricht wurde endgültig aus dem Ordner "Wiederherstellbare Elemente" gelöscht.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MoveToDeletedItems**|Eine Nachricht wurde gelöscht und in den Ordner „Gelöschte Objekte“ verschoben.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**SendAs**|Eine Nachricht wurde unter Verwendung der SendAs-Berechtigung gesendet.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SendOnBehalf**|Eine Nachricht wurde unter Verwendung der SendOnBehalf-Berechtigung gesendet. |![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SoftDelete**|Eine Nachricht wurde dauerhaft gelöscht oder aus dem Ordner „Gelöschte Objekte“ gelöscht. Vorübergehend gelöschte Elemente werden in den Ordner „Wiederherstellbare Elemente“ verschoben.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**Update**|Eine Nachricht oder deren Eigenschaften wurden geändert.|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>Überprüfen, ob standardmäßige Postfachaktionen für jeden Anmeldetyp protokolliert werden

Durch Standardeinstellungen für die postfachüberwachung wird allen Postfächern eine neue *DefaultAuditSet* -Eigenschaft hinzugefügt. Der Wert dieser Eigenschaft gibt an, ob die standardmäßigen Postfachaktionen (verwaltet von Microsoft) für das Postfach überwacht werden.

Um den Wert für Benutzerpostfächer oder freigegebene Post \<Fächer\> anzuzeigen, ersetzen Sie Mailbox Identity durch den Namen, den Alias, die e-Mail-Adresse oder den Benutzerprinzipalnamen (username) des Postfachs, und führen Sie den folgenden Befehl in Exchange Online PowerShell aus:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

Wenn Sie den Wert für Office 365 Gruppen Postfächer anzeigen möchten \<,\> ersetzen Sie Mailbox Identity durch den Namen, den Alias oder die e-Mail-Adresse des freigegebenen Postfachs, und führen Sie den folgenden Befehl in Exchange Online PowerShell aus:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

Der Wert `Admin, Delegate, Owner` gibt an:

- Die standardmäßigen Postfachaktionen für alle drei Anmeldetypen werden überwacht. Dies ist der einzige Wert, den Sie für Office 365 Gruppen Postfächer sehen.

- Ein Administrator *hat* die überwachten Postfachaktionen für keinen Anmeldetyp in einem Benutzerpostfach oder einem freigegebenen Postfach geändert. Hinweis Dies ist der Standardzustand, wenn die postfachüberwachung für standardmäßig anfänglich in Ihrer Organisation aktiviert ist.

Wenn ein Administrator die Postfachaktionen geändert hat, die für einen Anmeldetyp überwacht werden (mithilfe der Parameter *AuditAdmin*, *AuditDelegate*oder *AuditOwner* für das Cmdlet " **Satz-Postfach** "), ist der Eigenschaftswert unterschiedlich.

Beispielsweise gibt der Wert `Owner` für die *DefaultAuditSet* -Eigenschaft für ein Benutzerpostfach oder ein freigegebenes Postfach Folgendes an:

- Die standardmäßigen Postfachaktionen für den Postfachbesitzer werden überwacht.

- Die überwachten Postfachaktionen `Delegate` für `Admin` die-und-Anmeldetypen wurden von den Standardaktionen geändert.

Ein leerer Wert für die *DefaultAuditSet* -Eigenschaft gibt an, dass die Postfachaktionen für alle drei Anmeldetypen für das Benutzerpostfach oder ein freigegebenes Postfach geändert wurden.

Weitere Informationen finden Sie im Abschnitt [ändern oder Wiederherstellen von Postfachaktionen, die standardmäßig](#change-or-restore-mailbox-actions-logged-by-default) in diesem Thema protokolliert werden.

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>Anzeigen der Postfachaktionen, die für Postfächer angemeldet sind

Wenn Sie die Postfachaktionen anzeigen möchten, die derzeit für Benutzerpostfächer oder freigegebene Postfächer angemeldet sind, ersetzen \<Sie Mailbox Identity\> durch den Namen, den Alias, die e-Mail-Adresse oder den Benutzerprinzipalnamen (username) des Postfachs, und führen Sie einen oder mehrere der folgenden Befehle in Exchange Online PowerShell aus.

> [!NOTE]
> Obwohl Sie den `-GroupMailbox` Schalter den folgenden **Get-Mailbox-** Befehlen für Office 365 Gruppen Postfächer hinzufügen können, glauben Sie nicht, welche Werte zurückgegeben werden. Die standardmäßigen und statischen Postfachaktionen, die für Office 365 Gruppen Postfächern überwacht werden, werden im Abschnitt [Postfachaktionen für Office 365 Gruppen Postfächer](#mailbox-actions-for-office-365-group-mailboxes) weiter oben in diesem Thema beschrieben.

#### <a name="owner-actions"></a>Besitzer Aktionen

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>Delegieren von Aktionen

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>Administratoraktionen

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>Standardmäßig protokollierte Postfachaktionen ändern oder wiederherstellen

Wie bereits erläutert, ist einer der wichtigsten Vorteile der standardmäßigen Überwachung von Postfächern: Sie müssen die überwachten Postfachaktionen nicht verwalten. Dies wird von Microsoft für Sie ausgeführt, und es werden automatisch neue Postfachaktionen hinzugefügt, die standardmäßig überwacht werden, wenn Sie veröffentlicht werden.

Möglicherweise muss Ihre Organisation jedoch eine andere Gruppe von Postfachaktionen für Benutzerpostfächer und freigegebene Postfächerüber wachen. In den Verfahren in diesem Abschnitt erfahren Sie, wie Sie die Postfachaktionen ändern, die für jeden Anmeldetyp überwacht werden, und wie Sie wieder zu den von Microsoft verwalteten Standardaktionen zurückkehren.

> [!IMPORTANT]
> Wenn Sie die folgenden Verfahren zum Anpassen der Postfachaktionen verwenden, die für Benutzerpostfächer oder freigegebene Postfächer angemeldet sind, werden alle neuen Standard Postfachaktionen, die von Microsoft freigegeben werden, nicht automatisch für diese Postfächer überwacht. Sie müssen der angepassten Liste der Aktionen manuell neue Postfachaktionen hinzufügen.

### <a name="change-the-mailbox-actions-to-audit"></a>Ändern der Postfachaktionen in "Überwachung"

Sie können die *AuditAdmin*-, *AuditDelegate*-oder *AuditOwner* -Parameter im CmdletSet **-Mailbox** verwenden, um die Postfachaktionen zu ändern, die für Benutzerpostfächer und freigegebene Postfächer überwacht werden (überwachte Aktionen für Office 365 Gruppen Postfächer nicht angepasst werden können).

Sie können zwei verschiedene Methoden verwenden, um die Postfachaktionen anzugeben:

- *Ersetzen* (überschreiben) der vorhandenen Postfachaktionen mithilfe dieser Syntax `action1,action2,...actionN`:.

- *Hinzufügen oder entfernen* von Postfachaktionen ohne Beeinträchtigung anderer vorhandener Werte mithilfe dieser Syntax `@{Add="action1","action2",..."actionN"}` : `@{Remove="action1","action2",..."actionN"}`oder.

In diesem Beispiel werden die Aktionen des Administratorpostfachs für das Postfach mit dem Namen "Gabriela Laureano zugewiesen" geändert, indem die Standardaktionen mit SoftDelete und HardDelete überschrieben werden.

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

In diesem Beispiel wird die Mailbox Login:-Besitzer Aktion dem Postfach Laura@contoso.onmicrosoft.com hinzugefügt.

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

In diesem Beispiel wird die MoveToDeletedItems-Stellvertretungs Aktion für das Team Diskussions Postfach entfernt.

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

Unabhängig von der verwendeten Methode hat das Anpassen der überwachten Postfachaktionen für Benutzerpostfächer oder freigegebene Postfächer die folgenden Ergebnisse:

- Für den von Ihnen angepassten Anmeldetyp werden die überwachten Postfachaktionen nicht mehr von Microsoft verwaltet.

- Der Anmeldetyp, den Sie angepasst haben, wird nicht mehr im *DefaultAuditSet* -Eigenschaftswert für das Postfach angezeigt, wie [zuvor beschrieben](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).

### <a name="restore-the-default-mailbox-actions"></a>Wiederherstellen der standardmäßigen Postfachaktionen

Wenn Sie die Postfachaktionen angepasst haben, die für ein Benutzerpostfach oder ein freigegebenes Postfach überwacht werden, können Sie die Standard Postfachaktionen für einen oder alle Anmeldetypen mithilfe dieser Syntax wiederherstellen:

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

Sie können mehrere *DefaultAuditSet* -Werte durch Kommas getrennt angeben.

**Hinweis**: die folgenden Verfahren gelten nicht für Office 365 Gruppen Postfächer (Sie sind auf die Standardaktionen, wie [hier](#mailbox-actions-for-office-365-group-mailboxes)beschrieben), limitiert.

In diesem Beispiel werden die Standardaktionen für überwachte Postfächer für alle Anmeldetypen im Postfach Mark@contoso.onmicrosoft.com wiederhergestellt.

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

In diesem Beispiel werden die standardmäßigen überwachten Postfachaktionen für den Administrator Anmeldetyp im Post Fach Chris@contoso.onmicrosoft.com wiederhergestellt, aber die benutzerdefinierten überwachten Postfachaktionen für die Anmeldetypen "Delegate" und "Owner" bleiben erhalten.

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

Das Wiederherstellen der standardmäßig überwachten Postfachaktionen für einen Anmeldetyp hat die folgenden Ergebnisse:

- Die aktuelle Liste der Postfachaktionen wird durch die standardmäßigen Postfachaktionen für den Anmeldetyp ersetzt.

- Alle neuen Postfachaktionen, die von Microsoft freigegeben werden, werden automatisch der Liste der überwachten Aktionen für den Anmeldetyp hinzugefügt.

- Der Wert der *DefaultAuditSet* -Eigenschaft für das Postfach wird aktualisiert und enthält den wiederhergestellten Anmeldetyp.

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>Deaktivieren der postfachüberwachung für Ihre Organisation standardmäßig

Sie können die postfachüberwachung für die gesamte Organisation standardmäßig deaktivieren, indem Sie den folgenden Befehl in Exchange Online PowerShell ausführen:

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

Das Deaktivieren der postfachüberwachung für standardmäßig hat die folgenden Ergebnisse:

- Die postfachüberwachung ist für Ihre Organisation deaktiviert.

- Ab dem Zeitpunkt, zu dem Sie die postfachüberwachung standardmäßig deaktiviert haben, werden keine Postfachaktionen überwacht, selbst wenn die Überwachung für ein Postfach aktiviert ist (die *AuditEnabled* -Eigenschaft für das Postfach ist **true**).

- Die postfachüberwachung ist für neue Postfächer nicht aktiviert, und das Festlegen der *AuditEnabled* -Eigenschaft für ein neues oder vorhandenes Postfach auf " **true** " wird ignoriert.

- Alle Post Fach Überwachungs Umgehungs Zuordnungseinstellungen (mit dem Cmdlet " **MailboxAuditBypassAssociation** " konfiguriert) werden ignoriert.

- Vorhandene Post Fach Überwachungseinträge werden beibehalten, bis die Verfallszeit für das Überwachungsprotokoll für den Datensatz abläuft.

### <a name="turn-on-mailbox-auditing-on-by-default"></a>Aktivieren der postfachüberwachung standardmäßig

Wenn Sie die postfachüberwachung für Ihre Organisation wieder aktivieren möchten, führen Sie den folgenden Befehl in Exchange Online PowerShell aus:

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>Umgehen der postfachüberwachungsprotokollierung

Derzeit können Sie die postfachüberwachung für bestimmte Postfächer nicht deaktivieren, wenn die postfachüberwachung standardmäßig in Ihrer Organisation aktiviert ist. Beispielsweise wird das Festlegen der *AuditEnabled* -Postfacheigenschaft auf **false** ignoriert.

Sie können jedoch weiterhin das Cmdlet " **MailboxAuditBypassAssociation** " in Exchange Online PowerShell verwenden, um zu verhindern *, dass alle Post Fach* Aktionen durch die angegebenen Benutzer protokolliert werden, unabhängig davon, wo die Aktionen ausgeführt werden. Zum Beispiel:

- Postfachbesitzer Aktionen, die von den umgangenen Benutzern ausgeführt werden, werden nicht protokolliert.

- Stellvertretungs Aktionen, die von den umgangenen Benutzern in den Postfächern anderer Benutzer ausgeführt werden (einschließlich freigegebener Postfächer) werden nicht protokolliert.

- Von den umgangenen Benutzern ausgeführte Administratoraktionen werden nicht protokolliert.

Wenn Sie die postfachüberwachungsprotokollierung für einen bestimmten Benutzer \<umgehen\> möchten, ersetzen Sie Mailbox Identity durch den Namen, die e-Mail-Adresse, den Alias oder den Benutzerprinzipalnamen (username) des Benutzers, und führen Sie den folgenden Befehl aus:

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

Führen Sie den folgenden Befehl aus, um zu überprüfen, ob die Überwachung für den angegebenen Benutzer umgangen wird:

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

Der Wert **true** gibt an, dass die postfachüberwachungsprotokollierung für den Benutzer umgangen wird.

## <a name="more-information"></a>Weitere Informationen

- Obwohl die postfachüberwachungsprotokollierung standardmäßig für alle Organisationen aktiviert ist, werden nur Benutzer mit E5-Lizenzen postfachüberwachungsprotokoll Ereignisse in [Überwachungsprotokoll suchen im Sicherheits & Compliance Center](search-the-audit-log-in-security-and-compliance.md) oder über die API für die [Office 365-Verwaltungsaktivität](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) **standardmäßig**zurückgeben.

  Zum Abrufen von postfachüberwachungsprotokoll Einträgen für Benutzer ohne E5-Lizenzen haben Sie folgende Möglichkeiten:

  - Aktivieren Sie die postfachüberwachung für einzelne Postfächer manuell ( `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true`führen Sie den Befehl aus). Anschließend können Sie Überwachungsprotokoll suchen im Security & Compliance Center oder über die API für die Office 365-Verwaltungsaktivität verwenden.
  
    > [!NOTE]
    > Wenn die postfachüberwachung für das Postfach bereits aktiviert ist, Ihre Suche jedoch keine Ergebnisse zurückgibt, ändern Sie den Wert des Parameters _AuditEnabled_ in `$false` und `$true`dann zurück zu.
  
  - Verwenden Sie die folgenden Cmdlets in Exchange Online PowerShell:

    - [Search-Mailbox auditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) , um das postfachüberwachungsprotokoll für bestimmte Benutzer zu durchsuchen.

    - [New-MailboxAuditLogSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-mailboxauditlogsearch) , um das postfachüberwachungsprotokoll für bestimmte Benutzer zu durchsuchen und die Ergebnisse per e-Mail an angegebene Empfänger zu senden.

  - Verwenden Sie das Exchange Admin Center (EAC) in Exchange Online, um folgende Aktionen auszuführen:

    - [Exportieren von Postfachüberwachungsprotokollen](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)

    - [Ausführen eines Berichts zum Postfachzugriff durch Nicht-Besitzer](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- Standardmäßig werden postfachüberwachungsprotokoll-Datensätze für 90 Tage aufbewahrt, bevor Sie gelöscht werden. Sie können die Verfallszeit für Überwachungsprotokolldatensätze mithilfe des *AuditLogAgeLimit* -Parameters im Cmdlet " **Satz-Postfach** " in Exchange Online PowerShell ändern. Durch Erhöhen dieses Werts können Sie jedoch nicht nach Ereignissen suchen, die älter als 90 Tage im Office 365 Überwachungsprotokoll sind.

  Wenn Sie die Verfallszeit verlängern, müssen Sie das Cmdlet [Search-Mailbox auditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) in Exchange Online PowerShell verwenden, um das postfachüberwachungsprotokoll des Benutzers nach Datensätzen zu durchsuchen, die älter als 90 Tage sind.

- Wenn Sie die *AuditLogAgeLimit* -Eigenschaft für ein Postfach vor dem Aktivieren der postfachüberwachung für die Organisation standardmäßig geändert haben, wird die Verfallszeit des Postfachs des vorhandenen Überwachungsprotokolls nicht geändert. Das bedeutet, dass die postfachüberwachung standardmäßig keine Auswirkung auf die aktuelle Altersgrenze für Post Fach Überwachungseinträge hat.

- Um den *AuditLogAgeLimit* -Wert für ein Office 365 Gruppenpostfach zu ändern, müssen Sie den `-GroupMailbox` Switch in den Befehl " **Postfach festlegen** " einschließen.

- Postfachüberwachungsprotokoll-Datensätze werden in einem Unterordner (benannte *Überwachungen*) im Ordner "refundable Items" im Postfach jedes Benutzers gespeichert. Beachten Sie die folgenden Aspekte hinsichtlich der Post Fach Überwachungseinträge und des Ordners "Wiederherstellbare Elemente":

  - Die Post Fach Überwachungsdatensätze gelten für das Speicherkontingent des Ordners "refundable Items", bei dem es sich standardmäßig um 30 GB handelt (das Warn Kontingent beträgt 20 GB). Das Speicherkontingent wird bei folgenden Schritten automatisch auf 100 GB (mit einem Warn Kontingent von 90 GB) erhöht:

    - Ein Haltebereich wird in einem Postfach gespeichert.

    - Das Postfach wird einer Aufbewahrungsrichtlinie im Compliance Center zugewiesen.

  - Post Fach Überwachungseinträge werden auch [für den Ordner Grenzwert für den Ordner "refundable Items](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)" gezählt. Im Unterordner Audits können maximal 3 Millionen Elemente (Überwachungseinträge) gespeichert werden.

    > [!NOTE]
    > Es ist unwahrscheinlich, dass sich die postfachüberwachung standardmäßig auf das Speicherkontingent oder den Ordner Grenzwert für den Ordner "Wiederherstellbare Elemente" auswirkt.

    - Sie können den folgenden Befehl in Exchange Online PowerShell ausführen, um die Größe und Anzahl der Elemente im Ordner "Überwachungs Unterordner" im Ordner "refundable Items" anzuzeigen:

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - Sie können nicht direkt auf einen Überwachungsprotokolleintrag im Ordner "refundable Items" zugreifen; Verwenden Sie stattdessen das Cmdlet **Search-Mailbox auditlog** , oder Durchsuchen Sie das Office 365 Überwachungsprotokoll, um nach Post Fach Überwachungseinträgen zu suchen und anzuzeigen.

- Wenn ein Postfach im Compliance Center aufbewahrt oder einer Aufbewahrungsrichtlinie zugewiesen wird, werden Überwachungsprotokolldatensätze weiterhin für die Dauer beibehalten, die von der *AuditLogAgeLimit* -Eigenschaft des Postfachs definiert ist (standardmäßig 90 Tage). Um Überwachungsprotokolldatensätze für Postfächer, die in der Warteschleife aufbewahrt werden, länger aufzubewahren, müssen Sie den *AuditLogAgeLimit* -Wert des Postfachs erweitern.

- In einer Multi-Geo-Umgebung wird die übergreifende geografische postfachüberwachung nicht unterstützt. Wenn ein Benutzer beispielsweise Berechtigungen für den Zugriff auf ein freigegebenes Postfach an einem anderen geografischen Standort erhält, werden Postfachaktionen, die von diesem Benutzer ausgeführt werden, nicht im postfachüberwachungsprotokoll des freigegebenen Postfachs protokolliert.
