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
ms.custom: seo-marvel-apr2020
description: Die Postfachüberwachungsprotokollierung ist in Microsoft 365 standardmäßig aktiviert (standardmäßig auch als Standardpostfachüberwachung oder Postfachüberwachung bezeichnet). Dies bedeutet, dass bestimmte Aktionen, die von Postfachbesitzern, Stellvertretern und Administratoren ausgeführt werden, automatisch in einem Postfach-Überwachungsprotokoll protokolliert werden, in dem Sie nach Aktivitäten suchen können, die für das Postfach ausgeführt werden.
ms.openlocfilehash: 4b2016b4eee68d336cc2f77f2eb6fef6f3ee2fd9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927855"
---
# <a name="manage-mailbox-auditing"></a>Verwalten der Postfächern

Ab Januar 2019 aktiviert Microsoft die Postfach-Überwachungsprotokollierung standardmäßig für alle Organisationen. Dies bedeutet, dass bestimmte Aktionen, die von Postfachbesitzern, Stellvertretern und Administratoren ausgeführt werden, automatisch protokolliert werden, und die entsprechenden Postfach-Überwachungsdatensätze sind verfügbar, wenn Sie im Postfach-Überwachungsprotokoll nach diesen suchen. Bevor die Postfachüberwachung standardmäßig aktiviert wurde, musste sie für jedes Benutzerpostfach in Ihrer Organisation manuell aktiviert werden.

Hier sind einige Vorteile der Postfachüberwachung standardmäßig:

- Die Überwachung wird automatisch aktiviert, wenn Sie ein neues Postfach erstellen. Sie müssen sie nicht manuell für neue Benutzer aktivieren.

- Sie müssen die überwachten Postfachaktionen nicht verwalten. Ein vordefinierter Satz von Postfachaktionen wird standardmäßig für jeden Anmeldetyp (Administrator, Stellvertreter und Besitzer) überwacht.

- Wenn Microsoft eine neue Postfachaktion veröffentlicht, wird die Aktion möglicherweise automatisch der Liste der Postfachaktionen hinzugefügt, die standardmäßig überwacht werden (abhängig davon, dass der Benutzer die entsprechende Lizenz besitzt). Dies bedeutet, dass Sie keine neuen Aktionen für Postfächer überwachen müssen.

- Sie verfügen über eine konsistente Postfachüberwachungsrichtlinie in Ihrer gesamten Organisation (da Sie dieselben Aktionen für alle Postfächer überwachen).

> [!NOTE]
>* Wichtig bei der standardmäßigen Veröffentlichung der Postfachüberwachung ist: Sie müssen nichts tun, um die Postfachüberwachung zu verwalten. Um jedoch weitere Informationen zu erhalten, die Postfachüberwachung von den Standardeinstellungen anzupassen oder sie vollständig zu deaktivieren, hilft Ihnen dieses Thema.
>- Standardmäßig sind nur Postfach-Überwachungsereignisse für E5-Benutzer in Überwachungsprotokollsuchen im Security & Compliance Center oder über die Office 365 Management Activity API verfügbar. Weitere Informationen finden Sie im [Abschnitt Weitere Informationen](#more-information) in diesem Thema.

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>Überprüfen, ob die Postfachüberwachung standardmäßig aktiviert ist

Führen Sie den folgenden Befehl in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)aus, um zu überprüfen, ob die Postfachüberwachung für Ihre Organisation standardmäßig aktiviert ist:

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

Der Wert **False** gibt an, dass die Postfachüberwachung standardmäßig für die Organisation aktiviert ist. Durch diesen standardmäßigen Organisationswert wird die Einstellung für die Postfachüberwachung für bestimmte Postfächer überschrieben. Wenn beispielsweise die Postfachüberwachung für ein Postfach deaktiviert ist (die *AuditEnabled-Eigenschaft* ist **false** für das Postfach), werden die Standardpostfachaktionen weiterhin für das Postfach überwacht, da die Postfachüberwachung standardmäßig für die Organisation aktiviert ist.

Um die Postfachüberwachung für bestimmte Postfächer deaktiviert zu lassen, konfigurieren Sie die Postfachüberwachungsumgehung für den Postfachbesitzer und andere Benutzer, denen der Zugriff auf das Postfach delegiert wurde. Weitere Informationen finden Sie im Abschnitt [Postfach-Überwachungsprotokollierung](#bypass-mailbox-audit-logging) umgehen in diesem Thema.

> [!NOTE]
> Wenn die Postfachüberwachung für die Organisation standardmäßig aktiviert ist, wird die *AuditEnabled-Eigenschaft* für betroffene Postfächer nicht von **False** in **True geändert.** Anders ausgedrückt: Die Postfachüberwachung bei ignoriert standardmäßig die *AuditEnabled-Eigenschaft* für Postfächer.

## <a name="supported-mailbox-types"></a>Unterstützte Postfachtypen

In der folgenden Tabelle sind die Postfachtypen aufgeführt, die derzeit standardmäßig von der Postfachüberwachung unterstützt werden:

|**Postfachtyp**|**Unterstützt**|**Nicht unterstützt**|
|:---------|:---------:|:---------:|
|Benutzerpostfächer|![Häkchen](../media/checkmark.png)||
|Freigegebene Postfächer|![Häkchen](../media/checkmark.png)||
|Microsoft 365-Gruppenpostfächer|![Häkchen](../media/checkmark.png)||
|Ressourcenpostfächer||![Häkchen](../media/checkmark.png)|
|Postfächer für öffentliche Ordner||![Häkchen](../media/checkmark.png)|

## <a name="logon-types-and-mailbox-actions"></a>Anmeldetypen und Postfachaktionen

Anmeldetypen klassifizieren den Benutzer, der die überwachten Aktionen für das Postfach ausführen. In der folgenden Liste werden die Anmeldetypen beschrieben, die in der Postfach-Überwachungsprotokollierung verwendet werden:

- **Besitzer**: Der Postfachbesitzer (das Konto, das dem Postfach zugeordnet ist).

- **Delegate**:

  - Ein Benutzer, dem die Berechtigung SendAs, SendOnBehalf oder FullAccess einem anderen Postfach zugewiesen wurde.

  - Ein Administrator, dem die Berechtigung FullAccess für das Postfach eines Benutzers zugewiesen wurde.

- **Administrator**:

  - Das Postfach wird mit einem der folgenden Microsoft eDiscovery-Tools durchsucht:

    - Inhaltssuche im Compliance Center.

    - eDiscovery oder Advanced eDiscovery im Compliance Center.

    - In-Place eDiscovery in Exchange Online.

  - Der Zugriff auf das Postfach wird über den Microsoft Exchange Server-MAPI-Editors.

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>Postfachaktionen für Benutzerpostfächer und freigegebene Postfächer

In der folgenden Tabelle werden die Postfachaktionen beschrieben, die in der Postfach-Überwachungsprotokollierung für Benutzerpostfächer und freigegebene Postfächer verfügbar sind.

- Ein Häkchen ( ![Häkchen](../media/checkmark.png)) gibt an, dass die Postfachaktion für den Anmeldetyp protokolliert werden kann (nicht alle Aktionen sind für alle Anmeldetypen verfügbar).

- Ein Sternchen ( ) nach dem Häkchen gibt an, dass die Postfachaktion standardmäßig für den <sup>\*</sup> Anmeldetyp protokolliert wird.

- Denken Sie daran, dass ein Administrator mit vollzugriffsberechtigung für ein Postfach als Stellvertretung betrachtet wird.

|**Postfachaktion**|**Beschreibung**|**Administrator**|**Stellvertretung**|**Besitzer**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**AddFolderPermissions**|**Hinweis**: Obwohl dieser Wert als Postfachaktion akzeptiert wird, ist er bereits in der **UpdateFolderPermissions-Aktion** enthalten und wird nicht separat überwacht. Mit anderen Worten: Verwenden Sie diesen Wert nicht.||||
|**ApplyRecord**|Ein Element wird als Datensatz bezeichnet.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**Kopieren**|Eine Nachricht wurde in einen anderen Ordner kopiert.|![Häkchen](../media/checkmark.png)|||
|**Create**|Ein Element wurde im Ordner Kalender, Kontakte, Notizen oder Aufgaben im Postfach erstellt (z. B. wird eine neue Besprechungsanfrage erstellt). Beachten Sie, dass das Erstellen, Senden oder Empfangen einer Nachricht nicht überwacht wird. Auch das Erstellen eines Postfachordners wird nicht überwacht.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)|
|**Default**||![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|
|**FolderBind**|Auf einen Postfachordner wurde zugegriffen. Diese Aktion wird auch protokolliert, wenn der Administrator oder der delegierte Benutzer das Postfach öffnet.<br/><br/> **Hinweis:** Überwachungsdatensätze für Ordnerbindungsaktionen, die von Stellvertretern ausgeführt werden, werden konsolidiert. Ein Überwachungsdatensatz wird für den Zugriff auf einzelne Ordner innerhalb eines Zeitraums von 24 Stunden generiert.|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|**HardDelete**|Eine Nachricht wurde endgültig aus dem Ordner "Wiederherstellbare Elemente" gelöscht.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**MailItemsAccessed**|Auf E-Mail-Daten wird über E-Mail-Protokolle und -Clients zugegriffen. Dieser Wert ist nur für E5- oder E5-Compliance-Add-On-Abonnementbenutzer verfügbar. Weitere Informationen finden Sie unter [Einrichten der erweiterten Überwachung für Benutzer](advanced-audit.md#set-up-advanced-audit-for-users).|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**MailboxLogin**|Der Benutzer hat sich bei ihrem Postfach angemeldet. |||![Häkchen](../media/checkmark.png)|
|**MessageBind**|Eine Nachricht wurde im Vorschaubereich angezeigt oder von einem Administrator geöffnet. **Hinweis:** Obwohl dieser Wert als Postfachaktion akzeptiert wird, werden diese Aktionen nicht mehr protokolliert.|![Häkchen](../media/checkmark.png)|||
|**ModifyFolderPermissions**|**Hinweis**: Obwohl dieser Wert als Postfachaktion akzeptiert wird, ist er bereits in der **UpdateFolderPermissions-Aktion** enthalten und wird nicht separat überwacht. Mit anderen Worten: Verwenden Sie diesen Wert nicht.||||
|**Verschieben**|Eine Nachricht wurde in einen anderen Ordner verschoben.|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|
|**MoveToDeletedItems**|Eine Nachricht wurde gelöscht und in den Ordner „Gelöschte Objekte“ verschoben.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**RecordDelete**|Ein Element, das als Datensatz gekennzeichnet ist, wurde soft-deleted (in den Ordner "Wiederherstellbare Elemente" verschoben). Elemente, die als Datensätze bezeichnet werden, können nicht dauerhaft gelöscht werden (werden aus dem Ordner "Wiederherstellbare Elemente" gelöscht).|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|
|**RemoveFolderPermissions**|**Hinweis**: Obwohl dieser Wert als Postfachaktion akzeptiert wird, ist er bereits in der **UpdateFolderPermissions-Aktion** enthalten und wird nicht separat überwacht. Mit anderen Worten: Verwenden Sie diesen Wert nicht.||||
|**Send**|Der Benutzer sendet eine E-Mail-Nachricht, antwortet auf eine E-Mail-Nachricht oder leitet eine E-Mail-Nachricht weiter. Dieser Wert ist nur für E5- oder E5-Compliance-Add-On-Abonnementbenutzer verfügbar. Weitere Informationen finden Sie unter [Einrichten der erweiterten Überwachung für Benutzer](advanced-audit.md#set-up-advanced-audit-for-users).|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|Eine Nachricht wurde mithilfe der SendAs-Berechtigung gesendet. Das bedeutet, dass ein anderer Benutzer die Nachricht so gesendet hat, dass sie vom Postfachbesitzer zu kommen scheint.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|Eine Nachricht wurde mithilfe der SendOnBehalf-Berechtigung gesendet. Das bedeutet, dass ein anderer Benutzer die Nachricht im Namen des Postfachbesitzers gesendet hat. Für den Empfänger ist in der Nachricht angegeben, in wessen Namen die Nachricht gesendet wurde und wer die Nachricht tatsächlich gesendet hat.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|Eine Nachricht wurde dauerhaft gelöscht oder aus dem Ordner „Gelöschte Objekte“ gelöscht. Vorübergehend gelöschte Elemente werden in den Ordner „Wiederherstellbare Elemente“ verschoben.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**Update**|Eine Nachricht oder deren Eigenschaften wurden geändert.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|Einem Postfach wurde eine Kalenderdelegierung zugewiesen. Der Stellvertretungszugriff gibt anderen Personen in der gleichen Organisation die Berechtigung zum Verwalten des Kalenders des Postfachbesitzers.|![Häkchen](../media/checkmark.png)<sup>\*</sup>||![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**UpdateComplianceTag**|Auf ein E-Mail-Element wird eine andere Aufbewahrungsbezeichnung angewendet (einem Element kann nur eine Aufbewahrungsbezeichnung zugewiesen werden).|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|
|**UpdateFolderPermissions**|Eine Ordnerberechtigung wurde geändert. Ordnerberechtigungen steuern, welche Benutzer in Ihrer Organisation auf Ordner in einem Postfach zugreifen können und welche Nachrichten sich in diesen Ordnern befinden.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**UpdateInboxRules**|Eine Posteingangsregel wurde hinzugefügt, entfernt oder geändert. Posteingangsregeln werden verwendet, um Nachrichten im Posteingang des Benutzers basierend auf den angegebenen Bedingungen zu verarbeiten und Aktionen zu ergreifen, wenn die Bedingungen einer Regel erfüllt sind, z. B. verschieben einer Nachricht in einen angegebenen Ordner oder Löschen einer Nachricht.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|

> [!IMPORTANT]
> Wenn Sie die Postfachaktionen so angepasst  haben, dass sie für einen beliebigen Anmeldetyp überwacht werden, bevor die Postfachüberwachung standardmäßig in Ihrer Organisation aktiviert wurde, werden die angepassten Einstellungen für das Postfach beibehalten und nicht von den Standardpostfachaktionen überschrieben, wie in diesem Abschnitt beschrieben. Informationen zum Wiederherstellen der Überwachungspostfachaktionen auf ihre Standardwerte (die Sie jederzeit ausführen können) finden Sie im Abschnitt [Wiederherstellen](#restore-the-default-mailbox-actions) der Standardpostfachaktionen weiter in diesem Thema.

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a>Postfachaktionen für Microsoft 365-Gruppenpostfächer

Die Postfachüberwachung aktiviert standardmäßig die Postfachüberwachungsprotokollierung für Microsoft 365-Gruppenpostfächer, Sie können jedoch nicht anpassen, was protokolliert wird (Sie können keine Postfachaktionen hinzufügen oder entfernen, die für jeden Anmeldetyp protokolliert werden).

In der folgenden Tabelle werden die Postfachaktionen beschrieben, die für jeden Anmeldetyp standardmäßig in Microsoft 365-Gruppenpostfächern protokolliert werden.

Denken Sie daran, dass ein Administrator mit vollzugriffsberechtigung für ein Microsoft 365-Gruppenpostfach als Stellvertretung betrachtet wird.

|**Postfachaktion**|**Beschreibung**|**Administrator**|**Stellvertretung**|**Besitzer**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**Create**|Erstellen eines Kalenderelements. Beachten Sie, dass das Erstellen, Senden oder Empfangen einer Nachricht nicht überwacht wird.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>||
|**HardDelete**|Eine Nachricht wurde endgültig aus dem Ordner "Wiederherstellbare Elemente" gelöscht.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**MoveToDeletedItems**|Eine Nachricht wurde gelöscht und in den Ordner „Gelöschte Objekte“ verschoben.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|Eine Nachricht wurde unter Verwendung der SendAs-Berechtigung gesendet.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|Eine Nachricht wurde unter Verwendung der SendOnBehalf-Berechtigung gesendet. |![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|Eine Nachricht wurde dauerhaft gelöscht oder aus dem Ordner „Gelöschte Objekte“ gelöscht. Vorübergehend gelöschte Elemente werden in den Ordner „Wiederherstellbare Elemente“ verschoben.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**Update**|Eine Nachricht oder deren Eigenschaften wurden geändert.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>Überprüfen, ob Standardpostfachaktionen für jeden Anmeldetyp protokolliert werden

Die Standardmäßige Postfachüberwachung fügt allen Postfächern eine neue *DefaultAuditSet-Eigenschaft* hinzu. Der Wert dieser Eigenschaft gibt an, ob die Standardpostfachaktionen (verwaltet von Microsoft) für das Postfach überwacht werden.

Ersetzen Sie zum Anzeigen des Werts für Benutzerpostfächer oder freigegebene Postfächer durch den Namen, alias, die E-Mail-Adresse oder den Benutzernamen (Benutzername) des Postfachs, und führen Sie den folgenden Befehl \<MailboxIdentity\> in Exchange Online PowerShell aus:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

Ersetzen Sie zum Anzeigen des Werts in Microsoft 365-Gruppenpostfächern durch den Namen, alias oder die E-Mail-Adresse des freigegebenen Postfachs, und führen Sie den folgenden Befehl \<MailboxIdentity\> in Exchange Online PowerShell aus:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

Der Wert `Admin, Delegate, Owner` gibt an:

- Die Standardpostfachaktionen für alle drei Anmeldetypen werden überwacht. Dies ist der einzige Wert, den Sie in Microsoft 365-Gruppenpostfächern sehen.

- Ein Administrator *hat die* überwachten Postfachaktionen für jeden Anmeldetyp für ein Benutzerpostfach oder ein freigegebenes Postfach nicht geändert. Beachten Sie, dass dies der Standardzustand ist, nachdem die Postfachüberwachung standardmäßig in Ihrer Organisation aktiviert wurde.

Wenn ein Administrator die Postfachaktionen geändert hat, die für einen Anmeldetyp überwacht werden (mithilfe der *Parameter AuditAdmin,* *AuditDelegate* oder *AuditOwner* im **Cmdlet Set-Mailbox),** ist der Eigenschaftswert unterschiedlich.

Der Wert für die `Owner` *DefaultAuditSet-Eigenschaft* für ein Benutzerpostfach oder freigegebenes Postfach gibt beispielsweise folgende Werte an:

- Die Standardpostfachaktionen für den Postfachbesitzer werden überwacht.

- Die überwachten Postfachaktionen für die Typen und Anmeldetypen `Delegate` `Admin` wurden von den Standardaktionen geändert.

Ein leerer Wert für die *DefaultAuditSet-Eigenschaft* gibt an, dass die Postfachaktionen für alle drei Anmeldetypen für das Benutzerpostfach oder ein freigegebenes Postfach geändert wurden.

Weitere Informationen finden Sie im Abschnitt [Standardmäßig](#change-or-restore-mailbox-actions-logged-by-default) protokollierte Postfachaktionen ändern oder wiederherstellen in diesem Thema.

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>Anzeigen der Postfachaktionen, die in Postfächern protokolliert werden

Um die Postfachaktionen anzuzeigen, die derzeit in Benutzerpostfächern oder freigegebenen Postfächern protokolliert werden, ersetzen Sie durch den Namen, den Alias, die E-Mail-Adresse oder den Benutzernamen (Benutzername) des Postfachs, und führen Sie einen oder mehrere der folgenden Befehle \<MailboxIdentity\> in Exchange Online PowerShell aus.

> [!NOTE]
> Obwohl Sie die Option zu den folgenden `-GroupMailbox` **Get-Mailbox-Befehlen** für Microsoft 365-Gruppenpostfächer hinzufügen können, glauben Sie nicht, dass die zurückgegebenen Werte zurückgegeben werden. Die standardmäßigen und statischen Postfachaktionen, die für Microsoft 365-Gruppenpostfächer überwacht werden, werden weiter oben in diesem Thema im Abschnitt Postfachaktionen für [Microsoft 365-Gruppenpostfächer](#mailbox-actions-for-microsoft-365-group-mailboxes) beschrieben.

#### <a name="owner-actions"></a>Besitzeraktionen

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

Wie bereits erläutert, ist einer der wichtigsten Vorteile der standardmäßigen Postfachüberwachung: Sie müssen die überwachten Postfachaktionen nicht verwalten. Microsoft führt dies für Sie aus, und wir fügen automatisch neue Postfachaktionen hinzu, die standardmäßig überwacht werden, sobald sie veröffentlicht werden.

Ihre Organisation muss jedoch möglicherweise eine andere Gruppe von Postfachaktionen für Benutzerpostfächer und freigegebene Postfächer überwachen. Die Verfahren in diesem Abschnitt zeigen, wie Sie die Postfachaktionen ändern, die für jeden Anmeldetyp überwacht werden, und wie Sie zu den von Microsoft verwalteten Standardaktionen zurückkehren.

> [!IMPORTANT]
> Wenn Sie die folgenden Verfahren verwenden, um die Postfachaktionen anzupassen, die in Benutzerpostfächern oder freigegebenen Postfächern protokolliert werden, werden neue von Microsoft freigegebene Standardpostfachaktionen nicht automatisch für diese Postfächer überwacht. Sie müssen der benutzerdefinierten Liste der Aktionen manuell neue Postfachaktionen hinzufügen.

### <a name="change-the-mailbox-actions-to-audit"></a>Ändern der Postfachaktionen zur Überwachung

Sie können die *Parameter AuditAdmin,* *AuditDelegate* oder *AuditOwner* im **Cmdlet Set-Mailbox** verwenden, um die Postfachaktionen zu ändern, die für Benutzerpostfächer und freigegebene Postfächer überwacht werden (überwachte Aktionen für Microsoft 365-Gruppenpostfächer können nicht angepasst werden).

Sie können zwei verschiedene Methoden verwenden, um die Postfachaktionen anzugeben:

- *Ersetzen* (überschreiben) Sie die vorhandenen Postfachaktionen mit der folgenden Syntax: `action1,action2,...actionN` .

- *Hinzufügen oder Entfernen von* Postfachaktionen ohne Auswirkungen auf andere vorhandene Werte mithilfe dieser Syntax: `@{Add="action1","action2",..."actionN"}` oder `@{Remove="action1","action2",..."actionN"}` .

In diesem Beispiel werden die Administratorpostfachaktionen für das Postfach mit dem Namen "Gabriela Laureano" geändert, indem die Standardaktionen mit SoftDelete und HardDelete überschreiben.

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

In diesem Beispiel wird der Postfachdatenbank die Postfachlogin-Besitzeraktion laura@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

In diesem Beispiel wird die Stellvertretungsaktion MoveToDeletedItems für das Teamdiskussionspostfach entfernt.

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

Unabhängig von der verwendeten Methode hat das Anpassen der überwachten Postfachaktionen für Benutzerpostfächer oder freigegebene Postfächer die folgenden Ergebnisse:

- Für den von Ihnen angepassten Anmeldetyp werden die überwachten Postfachaktionen nicht mehr von Microsoft verwaltet.

- Der angepasste Anmeldetyp wird nicht mehr im Wert der *DefaultAuditSet-Eigenschaft* für das Postfach wie [zuvor beschrieben angezeigt.](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)

### <a name="restore-the-default-mailbox-actions"></a>Wiederherstellen der Standardpostfachaktionen

Wenn Sie die Postfachaktionen angepasst haben, die für ein Benutzerpostfach oder ein freigegebenes Postfach überwacht werden, können Sie die Standardpostfachaktionen für einen oder alle Anmeldetypen mithilfe der folgenden Syntax wiederherstellen:

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

Sie können mehrere *DefaultAuditSet-Werte* durch Kommas getrennt angeben.

**Hinweis**: Die folgenden Verfahren gelten nicht für Microsoft 365-Gruppenpostfächer (sie sind auf die Standardaktionen beschränkt, wie hier [beschrieben).](#mailbox-actions-for-microsoft-365-group-mailboxes)

In diesem Beispiel werden die standardmäßigen überwachten Postfachaktionen für alle Anmeldetypen auf dem Postfachserver mark@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

In diesem Beispiel werden die standardmäßigen überwachten Postfachaktionen für den Administratoranmeldetyp für das Postfach chris@contoso.onmicrosoft.com wiederhergestellt, die benutzerdefinierten überwachten Postfachaktionen bleiben jedoch für die Anmeldetypen Delegate und Owner.

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

Das Wiederherstellen der standardmäßig überwachten Postfachaktionen für einen Anmeldetyp hat die folgenden Ergebnisse:

- Die aktuelle Liste der Postfachaktionen wird durch die Standardpostfachaktionen für den Anmeldetyp ersetzt.

- Alle neuen Postfachaktionen, die von Microsoft freigegeben werden, werden automatisch der Liste der überwachten Aktionen für den Anmeldetyp hinzugefügt.

- Der *Wert der DefaultAuditSet-Eigenschaft* für das Postfach wird so aktualisiert, dass er den wiederhergestellten Anmeldetyp enthält.

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>Deaktivieren der Postfachüberwachung standardmäßig für Ihre Organisation

Sie können die Postfachüberwachung standardmäßig für Ihre gesamte Organisation deaktivieren, indem Sie den folgenden Befehl in Exchange Online PowerShell ausführen:

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

Das standardmäßige Deaktivieren der Postfachüberwachung hat die folgenden Ergebnisse:

- Die Postfachüberwachung ist für Ihre Organisation deaktiviert.

- Ab dem Zeitpunkt, zu dem Sie die Postfachüberwachung standardmäßig deaktiviert haben, werden keine Postfachaktionen überwacht, auch wenn die Überwachung für ein Postfach aktiviert ist (die *AuditEnabled-Eigenschaft* für das Postfach ist **True**).

- Die Postfachüberwachung ist für neue Postfächer nicht aktiviert, und das Festlegen der *AuditEnabled-Eigenschaft* für ein neues oder vorhandenes Postfach auf **True** wird ignoriert.

- Alle Zuordnungseinstellungen für die Postfachprüfungsumgehung (konfiguriert mit dem **Cmdlet Set-MailboxAuditBypassAssociation)** werden ignoriert.

- Vorhandene Postfach-Überwachungsdatensätze werden aufbewahrt, bis die Altersgrenze für überwachungsprotokolle für den Datensatz abläuft.

### <a name="turn-on-mailbox-auditing-on-by-default"></a>Aktivieren der Postfachüberwachung standardmäßig

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um die Postfachüberwachung für Ihre Organisation wieder zu aktivieren:

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>Umgehen der Postfachüberwachungsprotokollierung

Derzeit können Sie die Postfachüberwachung nicht für bestimmte Postfächer deaktivieren, wenn die Postfachüberwachung in Ihrer Organisation standardmäßig aktiviert ist. Beispielsweise wird das Festlegen der *AuditEnabled-Postfacheigenschaft* auf **False** ignoriert.

Sie können jedoch weiterhin das **Cmdlet Set-MailboxAuditBypassAssociation** in Exchange  Online PowerShell verwenden, um zu verhindern, dass alle Postfachaktionen der angegebenen Benutzer protokolliert werden, unabhängig davon, wo die Aktionen ausgeführt werden. Beispiel:

- Postfachbesitzeraktionen, die von den umgangenen Benutzern ausgeführt werden, werden nicht protokolliert.

- Stellvertretungsaktionen, die von den umgangenen Benutzern in den Postfächern anderer Benutzer (einschließlich freigegebener Postfächer) ausgeführt werden, werden nicht protokolliert.

- Administratoraktionen, die von den umgangenen Benutzern ausgeführt werden, werden nicht protokolliert.

Ersetzen Sie zum Umgehen der Postfach-Überwachungsprotokollierung für einen bestimmten Benutzer durch den Namen, die E-Mail-Adresse, den Alias oder den Benutzernamen (Benutzername) des Benutzers, und führen Sie den \<MailboxIdentity\> folgenden Befehl aus:

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

Um zu überprüfen, ob die Überwachung für den angegebenen Benutzer umgangen wird, führen Sie den folgenden Befehl aus:

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

Der Wert **True** gibt an, dass die Postfach-Überwachungsprotokollierung für den Benutzer umgangen wird.

## <a name="more-information"></a>Weitere Informationen

- Obwohl die Postfach-Überwachungsprotokollierung standardmäßig für alle Organisationen aktiviert ist, geben nur Benutzer mit E5-Lizenzen Postfach-Überwachungsprotokollereignisse in Überwachungsprotokollsuchen im [Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md) oder über die Office [365 Management Activity API](/office/office-365-management-api/office-365-management-activity-api-reference) standardmäßig **zurück.**

  Zum Abrufen von Postfach-Überwachungsprotokolleinträgen für Benutzer ohne E5-Lizenzen können Sie:

  - Manuelles Aktivieren der Postfachüberwachung für einzelne Postfächer (Führen Sie den Befehl aus, `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` ). Anschließend können Sie Überwachungsprotokollsuchen im Security & Compliance Center oder über die Office 365 Management Activity API verwenden.
  
    > [!NOTE]
    > Wenn die Postfachüberwachung bereits für das Postfach aktiviert zu sein scheint, ihre Suchen jedoch keine Ergebnisse zurückgeben, ändern Sie den Wert des _Parameters AuditEnabled_ in und dann `$false` wieder in `$true` .
  
  - Verwenden Sie die folgenden Cmdlets in Exchange Online PowerShell:

    - [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) zum Durchsuchen des Postfach-Überwachungsprotokolls nach bestimmten Benutzern.

    - [New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) zum Durchsuchen des Postfach-Überwachungsprotokolls nach bestimmten Benutzern und zum Senden der Ergebnisse per E-Mail an angegebene Empfänger.

  - Verwenden Sie das Exchange Admin Center (EAC) in Exchange Online, um die folgenden Aktionen zu ausführen:

    - [Exportieren von Postfachüberwachungsprotokollen](/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)

    - [Ausführen eines Berichts zum Postfachzugriff durch Nicht-Besitzer](/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- Standardmäßig werden Postfach-Überwachungsprotokolleinträge 90 Tage lang aufbewahrt, bevor sie gelöscht werden. Sie können die Altersgrenze für Überwachungsprotokolleinträge mithilfe des *Parameters AuditLogAgeLimit* im **Cmdlet Set-Mailbox** in Exchange Online PowerShell ändern. Wenn Sie diesen Wert erhöhen, können Sie jedoch nicht nach Ereignissen suchen, die älter als 90 Tage im Überwachungsprotokoll sind.

  Wenn Sie die Altersgrenze erhöhen, müssen Sie das [Cmdlet Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) in Exchange Online PowerShell verwenden, um das Postfach-Überwachungsprotokoll des Benutzers nach Datensätzen zu durchsuchen, die älter als 90 Tage sind.

- Wenn Sie die *AuditLogAgeLimit-Eigenschaft* für ein Postfach geändert haben, bevor die Postfachüberwachung standardmäßig für die Organisation aktiviert ist, wird das vorhandene Alterslimit für Überwachungsprotokolle des Postfachs nicht geändert. Anders ausgedrückt: Die Standardmäßige Postfachüberwachung wirkt sich nicht auf die aktuelle Altersgrenze für Postfachüberwachungseinträge aus.

- Um den *AuditLogAgeLimit-Wert* für ein Microsoft 365-Gruppenpostfach zu ändern, müssen Sie die Option in den `-GroupMailbox` Befehl **Set-Mailbox** verwenden.

- Postfach-Überwachungsprotokolleinträge werden in einem Unterordner (namens *"Audits")* im Ordner "Wiederherstellbare Elemente" im Postfach jedes Benutzers gespeichert. Beachten Sie die folgenden Punkte zu Postfach-Überwachungsdatensätzen und dem Ordner "Wiederherstellbare Elemente":

  - Postfach-Überwachungsdatensätze werden mit dem Speicherkontingent des Ordners "Wiederherstellbare Elemente" gezählt, der standardmäßig 30 GB beträgt (das Warnungskontingent beträgt 20 GB). Das Speicherkontingent wird automatisch auf 100 GB (mit einem 90 GB-Warnungskontingent) erhöht, wenn:

    - Ein Halteraum wird für ein Postfach platziert.

    - Das Postfach wird einer Aufbewahrungsrichtlinie im Compliance Center zugewiesen.

  - Postfach-Überwachungsdatensätze zählen auch für [den Ordnergrenzwert für den Ordner "Wiederherstellbare Elemente".](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits) Maximal 3 Millionen Elemente (Überwachungsdatensätze) können im Unterordner Überwachungen gespeichert werden.

    > [!NOTE]
    > Es ist unwahrscheinlich, dass sich die Postfachüberwachung standardmäßig auf das Speicherkontingent oder die Ordnerbeschränkung für den Ordner "Wiederherstellbare Elemente" auswirken wird.

    - Sie können den folgenden Befehl in Exchange Online PowerShell ausführen, um die Größe und Anzahl der Elemente im Unterordner Überwachungen im Ordner "Wiederherstellbare Elemente" anzeigen zu können:

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - Sie können nicht direkt auf einen Überwachungsprotokolldatensatz im Ordner "Wiederherstellbare Elemente" zugreifen. Verwenden Sie stattdessen das **Cmdlet Search-MailboxAuditLog,** oder durchsuchen Sie das Überwachungsprotokoll, um Postfach-Überwachungsdatensätze zu suchen und zu sehen.

- Wenn ein Postfach im Compliance Center in der Aufbewahrungsrichtlinie gespeichert oder einer Aufbewahrungsrichtlinie zugewiesen ist, werden Überwachungsprotokolleinträge weiterhin für die Dauer aufbewahrt, die durch die *AuditLogAgeLimit-Eigenschaft* des Postfachs definiert ist (standardmäßig 90 Tage). Um Überwachungsprotokolleinträge länger für Postfächer im Archiv zu behalten, müssen Sie den *AuditLogAgeLimit-Wert des Postfachs* erhöhen.

- In einer Multi-Geo-Umgebung wird die Geo-übergreifende Postfachüberwachung nicht unterstützt. Wenn beispielsweise einem Benutzer Berechtigungen für den Zugriff auf ein freigegebenes Postfach an einem anderen Geo-Speicherort zugewiesen wurden, werden die von diesem Benutzer ausgeführten Postfachaktionen im Postfachüberwachungsprotokoll des freigegebenen Postfachs nicht protokolliert.