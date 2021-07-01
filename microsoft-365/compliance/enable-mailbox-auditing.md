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
description: Die Postfachüberwachungsprotokollierung ist in Microsoft 365 standardmäßig aktiviert (auch standardmäßig als Postfachüberwachung oder Postfachüberwachung bezeichnet). Dies bedeutet, dass bestimmte Aktionen, die von Postfachbesitzern, Stellvertretungen und Administratoren ausgeführt werden, automatisch in einem Postfachüberwachungsprotokoll protokolliert werden, in dem Sie nach Aktivitäten suchen können, die für das Postfach ausgeführt werden.
ms.openlocfilehash: 56207a21d9a13edb04a07234764257d3c27f2d0f
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226779"
---
# <a name="manage-mailbox-auditing"></a>Verwalten der Postfächern

Ab Januar 2019 aktiviert Microsoft standardmäßig die Postfachüberwachungsprotokollierung für alle Organisationen. Dies bedeutet, dass bestimmte Aktionen, die von Postfachbesitzern, Stellvertretungen und Administratoren ausgeführt werden, automatisch protokolliert werden und die entsprechenden Postfachüberwachungseinträge verfügbar sind, wenn Sie im Postfachüberwachungsprotokoll danach suchen. Bevor die Postfachüberwachung standardmäßig aktiviert wurde, mussten Sie sie manuell für jedes Benutzerpostfach in Ihrer Organisation aktivieren.

Nachfolgend sind einige Vorteile der Postfachüberwachung standardmäßig aufgeführt:

- Die Überwachung wird automatisch aktiviert, wenn Sie ein neues Postfach erstellen. Sie müssen es nicht manuell für neue Benutzer aktivieren.
- Sie müssen die Postfachaktionen, die überwacht werden, nicht verwalten. Ein vordefinierter Satz von Postfachaktionen wird standardmäßig für jeden Anmeldetyp (Administrator, Stellvertreter und Besitzer) überwacht.
- Wenn Microsoft eine neue Postfachaktion freigibt, wird die Aktion möglicherweise automatisch der Liste der Postfachaktionen hinzugefügt, die standardmäßig überwacht werden (sofern der Benutzer über die entsprechende Lizenz verfügt). Dies bedeutet, dass Sie das Hinzufügen neuer Aktionen für Postfächer nicht überwachen müssen.
- Sie verfügen über eine konsistente Postfachüberwachungsrichtlinie in Ihrer organisationweiten Organisation (da Sie die gleichen Aktionen für alle Postfächer überwachen).

> [!NOTE]
>
> - Das Wichtige, was Sie sich über die standardmäßige Veröffentlichung der Postfachüberwachung merken sollten, ist: Sie müssen nichts tun, um die Postfachüberwachung zu verwalten. Um jedoch mehr zu erfahren, die Postfachüberwachung aus den Standardeinstellungen anzupassen oder vollständig zu deaktivieren, kann dieser Artikel Ihnen helfen.
> - Standardmäßig sind nur Postfachüberwachungsereignisse für E5-Benutzer in Überwachungsprotokollsuchen im Security & Compliance Center oder über die Office 365-Verwaltungsaktivitäts-API verfügbar. Weitere Informationen finden Sie im Abschnitt ["Weitere Informationen"](#more-information) in diesem Artikel.

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>Überprüfen, ob die Postfachüberwachung standardmäßig aktiviert ist

Um zu überprüfen, ob die Postfachüberwachung für Ihre Organisation standardmäßig aktiviert ist, führen Sie den folgenden Befehl in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)aus:

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

Der Wert **False** gibt an, dass die Postfachüberwachung standardmäßig für die Organisation aktiviert ist. Dieser standardmäßige Organisationswert setzt die Postfachüberwachungseinstellung für bestimmte Postfächer außer Kraft. Wenn beispielsweise die Postfachüberwachung für ein Postfach deaktiviert ist (die *AuditEnabled-Eigenschaft* **ist** für das Postfach falsch), werden die Standardpostfachaktionen weiterhin für das Postfach überwacht, da die Postfachüberwachung standardmäßig für die Organisation aktiviert ist.

Um die Postfachüberwachung für bestimmte Postfächer deaktiviert zu lassen, konfigurieren Sie die Postfachüberwachungsumgehung für den Postfachbesitzer und andere Benutzer, denen der Zugriff auf das Postfach delegiert wurde. Weitere Informationen finden Sie im Abschnitt ["Postfachüberwachungsprotokollierung umgehen"](#bypass-mailbox-audit-logging) in diesem Artikel.

> [!NOTE]
> Wenn die Postfachüberwachung für die Organisation standardmäßig aktiviert ist, wird die *AuditEnabled-Eigenschaft* für betroffene Postfächer nicht von **"False"** in **"True"** geändert. Anders ausgedrückt ignoriert die Postfachüberwachung standardmäßig die *AuditEnabled-Eigenschaft* für Postfächer.

## <a name="supported-mailbox-types"></a>Unterstützte Postfachtypen

In der folgenden Tabelle sind die Postfachtypen aufgeführt, die derzeit standardmäßig von der Postfachüberwachung unterstützt werden:

<br>

****

|Postfachtyp|Unterstützt|
|---|:---:|
|Benutzerpostfächer|![Häkchen](../media/checkmark.png)|
|Freigegebene Postfächer|![Häkchen](../media/checkmark.png)|
|Microsoft 365 Gruppenpostfächer|![Häkchen](../media/checkmark.png)|
|Ressourcenpostfächer||
|Postfächer für öffentliche Ordner||
|

## <a name="logon-types-and-mailbox-actions"></a>Anmeldetypen und Postfachaktionen

Anmeldetypen klassifizieren den Benutzer, der die überwachten Aktionen für das Postfach ausgeführt hat. In der folgenden Liste werden die Anmeldetypen beschrieben, die in der Postfachüberwachungsprotokollierung verwendet werden:

- **Besitzer:** Der Postfachbesitzer (das Konto, das dem Postfach zugeordnet ist).
- **Stellvertretung**:
  - Ein Benutzer, dem die Berechtigung "SendAs", "SendOnBehalf" oder "FullAccess" für ein anderes Postfach zugewiesen wurde.
  - Ein Administrator, dem die Berechtigung "FullAccess" für das Postfach eines Benutzers zugewiesen wurde.
- **Administrator**:
  - Das Postfach wird mit einem der folgenden Microsoft eDiscovery-Tools durchsucht:
    - Inhaltssuche im Compliance Center.
    - eDiscovery oder Advanced eDiscovery im Compliance Center.
    - In-Place eDiscovery in Exchange Online.
  - Der Zugriff auf das Postfach erfolgt über den Microsoft Exchange Server MAPI-Editor.

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>Postfachaktionen für Benutzerpostfächer und freigegebene Postfächer

In der folgenden Tabelle werden die Postfachaktionen beschrieben, die in der Postfachüberwachungsprotokollierung für Benutzerpostfächer und freigegebene Postfächer verfügbar sind.

- Ein Häkchen (![Häkchen](../media/checkmark.png)) gibt an, dass die Postfachaktion für den Anmeldetyp protokolliert werden kann (nicht alle Aktionen sind für alle Anmeldetypen verfügbar).
- Ein Sternchen ( <sup>\*</sup> ) nach dem Häkchen gibt an, dass die Postfachaktion standardmäßig für den Anmeldetyp protokolliert wird.
- Denken Sie daran, dass ein Administrator mit vollzugriffsberechtigung für ein Postfach als Stellvertretung betrachtet wird.

<br>

****

|Postfachaktion|Beschreibung|Administrator|Stellvertretung|Besitzer|
|---|---|:---:|:---:|:---:|
|**AddFolderPermissions**|Obwohl dieser Wert als Postfachaktion akzeptiert wird, ist er bereits in der **UpdateFolderPermissions-Aktion** enthalten und wird nicht separat überwacht. Verwenden Sie diesen Wert also nicht.||||
|**ApplyRecord**|Ein Element wird als Datensatz bezeichnet.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**Kopieren**|Eine Nachricht wurde in einen anderen Ordner kopiert.|![Häkchen](../media/checkmark.png)|||
|**Create**|Ein Element wurde im Ordner "Kalender", "Kontakte", "Notizen" oder "Aufgaben" im Postfach erstellt (z. B. wird eine neue Besprechungsanfrage erstellt). Beachten Sie, dass das Erstellen, Senden oder Empfangen einer Nachricht nicht überwacht wird. Auch das Erstellen eines Postfachordners wird nicht überwacht.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)|
|**FolderBind**|Auf einen Postfachordner wurde zugegriffen. Diese Aktion wird auch protokolliert, wenn der Administrator oder der delegierte Benutzer das Postfach öffnet.<br/><br/> **Hinweis:** Überwachungsdatensätze für Ordnerbindungsaktionen, die von Delegaten ausgeführt werden, werden konsolidiert. Ein Überwachungsdatensatz wird innerhalb eines 24-Stunden-Zeitraums für den Zugriff auf einzelne Ordner generiert.|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)||
|**HardDelete**|Eine Nachricht wurde endgültig aus dem Ordner "Wiederherstellbare Elemente" gelöscht.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**MailboxLogin**|Der Benutzer hat sich bei dessen Postfach angemeldet.|||![Häkchen](../media/checkmark.png)|
|**MailItemsAccessed**|**Hinweis:** Dieser Wert ist nur für Benutzer von E5- oder E5 Compliance-Add-On-Abonnements verfügbar. Weitere Informationen finden Sie unter [Einrichten der erweiterten Überwachung in Microsoft 365.](set-up-advanced-audit.md) <p> E-Mail-Daten werden von E-Mail-Protokollen und -Clients aufgerufen.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**MessageBind**|**Hinweis:** Dieser Wert ist nur für E3-Benutzer (Benutzer ohne E5- oder E5 Compliance-Add-On-Abonnements) verfügbar. <p> Eine Nachricht wurde im Vorschaubereich angezeigt oder von einem Administrator geöffnet.|![Häkchen](../media/checkmark.png)|||
|**ModifyFolderPermissions**|Obwohl dieser Wert als Postfachaktion akzeptiert wird, ist er bereits in der **UpdateFolderPermissions-Aktion** enthalten und wird nicht separat überwacht. Verwenden Sie diesen Wert also nicht.|||||
|**Verschieben**|Eine Nachricht wurde in einen anderen Ordner verschoben.|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|
|**MoveToDeletedItems**|Eine Nachricht wurde gelöscht und in den Ordner „Gelöschte Objekte“ verschoben.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**RecordDelete**|Ein Als Datensatz bezeichnetes Element wurde vorläufig gelöscht (in den Ordner "Wiederherstellbare Elemente" verschoben). Elemente, die als Datensätze bezeichnet werden, können nicht dauerhaft gelöscht werden (aus dem Ordner "Wiederherstellbare Elemente" gelöscht).|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|
|**RemoveFolderPermissions**|Obwohl dieser Wert als Postfachaktion akzeptiert wird, ist er bereits in der **UpdateFolderPermissions-Aktion** enthalten und wird nicht separat überwacht. Verwenden Sie diesen Wert also nicht.||||
|**SearchQueryInitiated**|**Hinweis:** Dieser Wert ist nur für Benutzer von E5- oder E5 Compliance-Add-On-Abonnements verfügbar. Weitere Informationen finden Sie unter [Einrichten der erweiterten Überwachung in Microsoft 365.](set-up-advanced-audit.md) <p> Eine Person verwendet Outlook (Windows, Mac, iOS, Android oder Outlook im Web) oder die Mail-App für Windows 10, um nach Elementen in einem Postfach zu suchen.|||![Häkchen](../media/checkmark.png)|
|**Send**|**Hinweis:** Dieser Wert ist nur für Benutzer von E5- oder E5 Compliance-Add-On-Abonnements verfügbar. Weitere Informationen finden Sie unter [Einrichten der erweiterten Überwachung in Microsoft 365.](set-up-advanced-audit.md) <p> Der Benutzer sendet eine E-Mail-Nachricht, antwortet auf eine E-Mail-Nachricht oder leitet eine E-Mail-Nachricht weiter.|![Häkchen](../media/checkmark.png)<sup>\*</sup>||![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|Eine Nachricht wurde mithilfe der SendAs-Berechtigung gesendet. Das bedeutet, dass ein anderer Benutzer die Nachricht so gesendet hat, dass sie vom Postfachbesitzer zu kommen scheint.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|Eine Nachricht wurde mithilfe der SendOnBehalf-Berechtigung gesendet. Das bedeutet, dass ein anderer Benutzer die Nachricht im Namen des Postfachbesitzers gesendet hat. Für den Empfänger ist in der Nachricht angegeben, in wessen Namen die Nachricht gesendet wurde und wer die Nachricht tatsächlich gesendet hat.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|Eine Nachricht wurde dauerhaft gelöscht oder aus dem Ordner „Gelöschte Objekte“ gelöscht. Vorübergehend gelöschte Elemente werden in den Ordner „Wiederherstellbare Elemente“ verschoben.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**Update**|Eine Nachricht oder eine der zugehörigen Eigenschaften wurde geändert.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|Einem Postfach wurde eine Kalenderdelegierung zugewiesen. Der Stellvertretungszugriff gibt anderen Personen in der gleichen Organisation die Berechtigung zum Verwalten des Kalenders des Postfachbesitzers.|![Häkchen](../media/checkmark.png)<sup>\*</sup>||![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**UpdateComplianceTag**|Eine andere Aufbewahrungsbezeichnung wird auf ein E-Mail-Element angewendet (einem Element kann nur eine Aufbewahrungsbezeichnung zugewiesen sein).|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|![Häkchen](../media/checkmark.png)|
|**UpdateFolderPermissions**|Eine Ordnerberechtigung wurde geändert. Ordnerberechtigungen steuern, welche Benutzer in Ihrer Organisation auf Ordner in einem Postfach zugreifen können und welche Nachrichten sich in diesen Ordnern befinden.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**UpdateInboxRules**|Eine Posteingangsregel wurde hinzugefügt, entfernt oder geändert. Posteingangsregeln werden verwendet, um Nachrichten im Posteingang des Benutzers basierend auf den angegebenen Bedingungen zu verarbeiten und Aktionen auszuführen, wenn die Bedingungen einer Regel erfüllt sind, z. B. verschieben einer Nachricht in einen angegebenen Ordner oder Löschen einer Nachricht.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|

> [!IMPORTANT]
> Wenn Sie die Postfachaktionen so angepasst haben, dass sie auf einen beliebigen Anmeldetyp überwacht werden, *bevor* die Postfachüberwachung in Ihrer Organisation standardmäßig aktiviert wurde, bleiben die angepassten Einstellungen für das Postfach erhalten und werden nicht von den Standardpostfachaktionen überschrieben, wie in diesem Abschnitt beschrieben. Informationen zum Wiederherstellen der Postfachüberwachungsaktionen auf ihre Standardwerte (die Sie jederzeit ausführen können) finden Sie im Abschnitt ["Wiederherstellen der Standardpostfachaktionen"](#restore-the-default-mailbox-actions) weiter unten in diesem Artikel.

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a>Postfachaktionen für Microsoft 365 Gruppenpostfächer

Die Postfachüberwachung ist standardmäßig aktiviert, führt die Postfachüberwachungsprotokollierung zu Microsoft 365 Gruppenpostfächern, Aber Sie können nicht anpassen, was protokolliert wird (Sie können keine Postfachaktionen hinzufügen oder entfernen, die für jeden Anmeldetyp protokolliert werden).

In der folgenden Tabelle werden die Postfachaktionen beschrieben, die standardmäßig für Microsoft 365 Gruppenpostfächer für jeden Anmeldetyp protokolliert werden.

Denken Sie daran, dass ein Administrator mit vollzugriffsberechtigung für ein Microsoft 365 Gruppenpostfach als Stellvertretung betrachtet wird.

<br>

****

|Postfachaktion|Beschreibung|Administrator|Stellvertretung|Besitzer|
|---|---|:---:|:---:|:---:|
|**Create**|Erstellen eines Kalenderelements. Beachten Sie, dass das Erstellen, Senden oder Empfangen einer Nachricht nicht überwacht wird.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>||
|**HardDelete**|Eine Nachricht wurde endgültig aus dem Ordner "Wiederherstellbare Elemente" gelöscht.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**MoveToDeletedItems**|Eine Nachricht wurde gelöscht und in den Ordner „Gelöschte Objekte“ verschoben.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|Eine Nachricht wurde unter Verwendung der SendAs-Berechtigung gesendet.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|Eine Nachricht wurde unter Verwendung der SendOnBehalf-Berechtigung gesendet.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|Eine Nachricht wurde dauerhaft gelöscht oder aus dem Ordner „Gelöschte Objekte“ gelöscht. Vorübergehend gelöschte Elemente werden in den Ordner „Wiederherstellbare Elemente“ verschoben.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|**Update**|Eine Nachricht oder eine der zugehörigen Eigenschaften wurde geändert.|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|![Häkchen](../media/checkmark.png)<sup>\*</sup>|
|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>Stellen Sie sicher, dass für jeden Anmeldetyp Standardpostfachaktionen protokolliert werden.

Die Postfachüberwachung wird standardmäßig allen Postfächern eine neue *DefaultAuditSet-Eigenschaft* hinzugefügt. Der Wert dieser Eigenschaft gibt an, ob die Standardpostfachaktionen (von Microsoft verwaltet) für das Postfach überwacht werden.

Um den Wert in Benutzerpostfächern oder freigegebenen Postfächern anzuzeigen, ersetzen Sie \<MailboxIdentity\> ihn durch den Namen, alias, die E-Mail-Adresse oder den Benutzerprinzipalnamen (Benutzernamen) des Postfachs, und führen Sie den folgenden Befehl in Exchange Online PowerShell aus:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

Um den Wert für Microsoft 365 Gruppenpostfächer anzuzeigen, ersetzen Sie \<MailboxIdentity\> ihn durch den Namen, den Alias oder die E-Mail-Adresse des freigegebenen Postfachs, und führen Sie den folgenden Befehl in Exchange Online PowerShell aus:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

Der Wert `Admin, Delegate, Owner` gibt Folgendes an:

- Die Standardpostfachaktionen für alle drei Anmeldetypen werden überwacht. Dies ist der einzige Wert, der in Microsoft 365 Gruppenpostfächern angezeigt wird.
- Ein Administrator hat die überwachten Postfachaktionen für jeden Anmeldetyp für ein Benutzerpostfach oder ein freigegebenes Postfach *nicht* geändert. Beachten Sie, dass dies der Standardstatus ist, nachdem die Postfachüberwachung standardmäßig in Ihrer Organisation aktiviert wurde.

Wenn ein Administrator die Postfachaktionen geändert hat, die für einen Anmeldetyp überwacht werden (mithilfe der Parameter *"AuditAdmin",* *"AuditDelegate"* oder *"AuditOwner"* im Cmdlet **"Set-Mailbox"),** ist der Eigenschaftswert unterschiedlich.

Der Wert `Owner` für die *DefaultAuditSet-Eigenschaft* eines Benutzerpostfachs oder freigegebenen Postfachs gibt beispielsweise Folgendes an:

- Die Standardpostfachaktionen für den Postfachbesitzer werden überwacht.
- Die überwachten Postfachaktionen für die `Delegate` Typen und `Admin` Anmeldetypen wurden von den Standardaktionen geändert.

Ein leerer Wert für die *DefaultAuditSet-Eigenschaft* gibt an, dass die Postfachaktionen für alle drei Anmeldetypen für das Benutzerpostfach oder ein freigegebenes Postfach geändert wurden.

Weitere Informationen finden Sie im Abschnitt [zum Ändern oder Wiederherstellen von Postfachaktionen,](#change-or-restore-mailbox-actions-logged-by-default) die standardmäßig in diesem Artikel protokolliert werden.

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>Anzeigen der Postfachaktionen, die bei Postfächern angemeldet sind

Um die Postfachaktionen anzuzeigen, die derzeit bei Benutzerpostfächern oder freigegebenen Postfächern angemeldet sind, ersetzen Sie \<MailboxIdentity\> den Namen, alias, die E-Mail-Adresse oder den Benutzerprinzipalnamen (Benutzernamen) des Postfachs, und führen Sie einen oder mehrere der folgenden Befehle in Exchange Online PowerShell aus.

> [!NOTE]
> Obwohl Sie die `-GroupMailbox` Option zu den folgenden **Get-Mailbox-Befehlen** für Microsoft 365 Gruppenpostfächer hinzufügen können, glauben Sie nicht, dass die zurückgegebenen Werte zurückgegeben werden. Die standard- und statischen Postfachaktionen, die für Microsoft 365 Gruppenpostfächer überwacht werden, werden im Abschnitt ["Postfachaktionen für Microsoft 365 Gruppenpostfächer"](#mailbox-actions-for-microsoft-365-group-mailboxes) weiter oben in diesem Artikel beschrieben.

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

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>Ändern oder Wiederherstellen von Postfachaktionen, die standardmäßig protokolliert werden

Wie zuvor erläutert, ist einer der wichtigsten Vorteile der standardmäßigen Postfachüberwachung: Sie müssen die Postfachaktionen, die überwacht werden, nicht verwalten. Microsoft erledigt dies für Sie, und wir fügen automatisch neue Postfachaktionen hinzu, die bei ihrer Veröffentlichung standardmäßig überwacht werden.

Möglicherweise muss Ihre Organisation jedoch einen anderen Satz von Postfachaktionen für Benutzerpostfächer und freigegebene Postfächer überwachen. Die Verfahren in diesem Abschnitt zeigen Ihnen, wie Sie die Postfachaktionen ändern, die für jeden Anmeldetyp überwacht werden, und wie Sie zu den von Microsoft verwalteten Standardaktionen zurückkehren.

> [!IMPORTANT]
> Wenn Sie die folgenden Verfahren verwenden, um die Postfachaktionen anzupassen, die in Benutzerpostfächern oder freigegebenen Postfächern angemeldet sind, werden alle neuen, von Microsoft veröffentlichten Standardpostfachaktionen nicht automatisch für diese Postfächer überwacht. Sie müssen ihrer benutzerdefinierten Liste von Aktionen manuell alle neuen Postfachaktionen hinzufügen.

### <a name="change-the-mailbox-actions-to-audit"></a>Ändern der Postfachaktionen, die überwacht werden sollen

Sie können die Parameter *"AuditAdmin",* *"AuditDelegate"* oder *"AuditOwner"* für das Cmdlet **"Set-Mailbox"** verwenden, um die Postfachaktionen zu ändern, die für Benutzerpostfächer und freigegebene Postfächer überwacht werden (überwachte Aktionen für Microsoft 365 Gruppenpostfächer können nicht angepasst werden).

Sie können zwei verschiedene Methoden verwenden, um die Postfachaktionen anzugeben:

- *Ersetzen* (überschreiben) Sie die vorhandenen Postfachaktionen mithilfe der folgenden Syntax: `action1,action2,...actionN` .
- *Hinzufügen oder Entfernen* von Postfachaktionen ohne Auswirkung auf andere vorhandene Werte mithilfe der folgenden Syntax: `@{Add="action1","action2",..."actionN"}` oder `@{Remove="action1","action2",..."actionN"}` .

In diesem Beispiel werden die Administratorpostfachaktionen für das Postfach Gabriela Laureano geändert, indem die Standardaktionen mit SoftDelete und HardDelete überschrieben werden.

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

In diesem Beispiel wird dem Postfach laura@contoso.onmicrosoft.com die Aktion "MailboxLogin-Besitzer" hinzugefügt.

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

In diesem Beispiel wird die Stellvertretungsaktion "MoveToDeletedItems" für das Postfach "Teamdiskussion" entfernt.

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

Unabhängig von der verwendeten Methode hat das Anpassen der überwachten Postfachaktionen für Benutzerpostfächer oder freigegebene Postfächer die folgenden Ergebnisse:

- Für den von Ihnen angepassten Anmeldetyp werden die überwachten Postfachaktionen nicht mehr von Microsoft verwaltet.
- Der von Ihnen angepasste Anmeldetyp wird nicht mehr im *DefaultAuditSet-Eigenschaftswert* für das Postfach angezeigt, wie [zuvor beschrieben.](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)

### <a name="restore-the-default-mailbox-actions"></a>Wiederherstellen der Standardpostfachaktionen

> [!NOTE]
> Die folgenden Verfahren gelten nicht für Microsoft 365 Gruppenpostfächer (sie sind auf die Standardaktionen beschränkt, wie [hier](#mailbox-actions-for-microsoft-365-group-mailboxes)beschrieben).

Wenn Sie die Postfachaktionen angepasst haben, die für ein Benutzerpostfach oder ein freigegebenes Postfach überwacht werden, können Sie die Standardpostfachaktionen für einen oder alle Anmeldetypen mithilfe dieser Syntax wiederherstellen:

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

Sie können mehrere *DefaultAuditSet-Werte* durch Kommas getrennt angeben.

In diesem Beispiel werden die standardmäßigen überwachten Postfachaktionen für alle Anmeldetypen für das Postfach mark@contoso.onmicrosoft.com wiederhergestellt.

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

In diesem Beispiel werden die standardmäßigen überwachten Postfachaktionen für den Administratoranmeldetyp für das Postfach chris@contoso.onmicrosoft.com wiederhergestellt, die benutzerdefinierten überwachten Postfachaktionen bleiben jedoch für die Anmeldetypen "Stellvertretung" und "Besitzer" übrig.

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

Das Wiederherstellen der standardmäßigen überwachten Postfachaktionen für einen Anmeldetyp hat die folgenden Ergebnisse:

- Die aktuelle Liste der Postfachaktionen wird durch die Standardpostfachaktionen für den Anmeldetyp ersetzt.
- Alle neuen Postfachaktionen, die von Microsoft freigegeben werden, werden automatisch der Liste der überwachten Aktionen für den Anmeldetyp hinzugefügt.
- Der *DefaultAuditSet-Eigenschaftswert* für das Postfach wird aktualisiert, um den wiederhergestellten Anmeldetyp einzuschließen.

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>Deaktivieren der Postfachüberwachung standardmäßig für Ihre Organisation

Sie können die Postfachüberwachung für Ihre gesamte Organisation standardmäßig deaktivieren, indem Sie den folgenden Befehl in Exchange Online PowerShell ausführen:

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

Wenn Sie die Postfachüberwachung standardmäßig deaktivieren, hat dies die folgenden Ergebnisse:

- Die Postfachüberwachung ist für Ihre Organisation deaktiviert.
- Ab dem Zeitpunkt, an dem Sie die Postfachüberwachung standardmäßig deaktiviert haben, werden keine Postfachaktionen überwacht, auch wenn die Überwachung für ein Postfach aktiviert ist (die *AuditEnabled-Eigenschaft* für das Postfach lautet **"True").**
- Die Postfachüberwachung ist für neue Postfächer nicht aktiviert, und das Festlegen der *AuditEnabled-Eigenschaft* für ein neues oder vorhandenes Postfach auf **"True"** wird ignoriert.
- Alle Einstellungen für die Postfachüberwachungsumgehung (konfiguriert mithilfe des Cmdlets **"Set-MailboxAuditBypassAssociation")** werden ignoriert.
- Vorhandene Postfachüberwachungseinträge werden bis zum Ablauf des Überwachungsprotokoll-Alterslimits für den Datensatz aufbewahrt.

### <a name="turn-on-mailbox-auditing-on-by-default"></a>Aktivieren der Postfachüberwachung standardmäßig

Um die Postfachüberwachung für Ihre Organisation wieder zu aktivieren, führen Sie den folgenden Befehl in Exchange Online PowerShell aus:

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>Umgehen der Postfachüberwachungsprotokollierung

Derzeit können Sie die Postfachüberwachung nicht für bestimmte Postfächer deaktivieren, wenn die Postfachüberwachung in Ihrer Organisation standardmäßig aktiviert ist. Beispielsweise wird das Festlegen der *AuditEnabled-Postfacheigenschaft* auf **"False"** ignoriert.

Sie können jedoch weiterhin das Cmdlet **"Set-MailboxAuditBypassAssociation"** in Exchange Online PowerShell verwenden, um zu verhindern, dass *alle* Postfachaktionen der angegebenen Benutzer protokolliert werden, unabhängig davon, wo die Aktionen ausgeführt werden. Beispiel:

- Postfachbesitzeraktionen, die von den umgangenen Benutzern ausgeführt werden, werden nicht protokolliert.
- Stellvertretungsaktionen, die von den umgangenen Benutzern in den Postfächern anderer Benutzer (einschließlich freigegebener Postfächer) ausgeführt werden, werden nicht protokolliert.
- Von den umgangenen Benutzern ausgeführte Administratoraktionen werden nicht protokolliert.

Um die Postfachüberwachungsprotokollierung für einen bestimmten Benutzer zu umgehen, ersetzen Sie \<MailboxIdentity\> den Namen, die E-Mail-Adresse, den Alias oder den Benutzerprinzipalnamen (Benutzernamen) des Benutzers, und führen Sie den folgenden Befehl aus:

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

Um zu überprüfen, ob die Überwachung für den angegebenen Benutzer umgangen wird, führen Sie den folgenden Befehl aus:

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

Der Wert **"True"** gibt an, dass die Postfachüberwachungsprotokollierung für den Benutzer umgangen wird.

## <a name="more-information"></a>Weitere Informationen

- Obwohl die Postfachüberwachungsprotokollierung standardmäßig für alle Organisationen aktiviert ist, geben nur Benutzer mit E5-Lizenzen Postfachüberwachungsprotokollereignisse in [Überwachungsprotokollsuchen im Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md) oder **standardmäßig** über die [Office 365-Verwaltungsaktivitäts-API](/office/office-365-management-api/office-365-management-activity-api-reference) zurück.

  Um Postfachüberwachungsprotokolleinträge für Benutzer ohne E5-Lizenzen abzurufen, können Sie Folgendes ausführen:

  - Aktivieren Sie die Postfachüberwachung manuell für einzelne Postfächer (führen Sie den Befehl `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` aus. Danach können Sie Überwachungsprotokollsuchen im Security & Compliance Center oder über die Office 365-Verwaltungsaktivitäts-API verwenden.
  
    > [!NOTE]
    > Wenn die Postfachüberwachung für das Postfach bereits aktiviert zu sein scheint, ihre Suchvorgänge jedoch keine Ergebnisse zurückgeben, ändern Sie den Wert des _Parameters AuditEnabled_ in `$false` und dann zurück zu `$true` .
  
  - Verwenden Sie die folgenden Cmdlets in Exchange Online PowerShell:
    - [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) zum Durchsuchen des Postfachüberwachungsprotokolls nach bestimmten Benutzern.
    - [New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) zum Durchsuchen des Postfachüberwachungsprotokolls nach bestimmten Benutzern und zum Senden der Ergebnisse per E-Mail an angegebene Empfänger.

  - Verwenden Sie das Exchange Admin Center (EAC) in Exchange Online, um die folgenden Aktionen auszuführen:
    - [Exportieren von Postfachüberwachungsprotokollen](/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)
    - [Ausführen eines Berichts zum Postfachzugriff durch Nicht-Besitzer](/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- Standardmäßig werden Postfachüberwachungsprotokolleinträge 90 Tage lang aufbewahrt, bevor sie gelöscht werden. Sie können die Altersbeschränkung für Überwachungsprotokolldatensätze mithilfe des *Parameters AuditLogAgeLimit* im Cmdlet **"Set-Mailbox"** in Exchange Online PowerShell ändern. Wenn Sie diesen Wert erhöhen, können Sie jedoch nicht nach Ereignissen suchen, die älter als 90 Tage im Überwachungsprotokoll sind.

  Wenn Sie die Altersgrenze erhöhen, müssen Sie das Cmdlet ["Search-MailboxAuditLog"](/powershell/module/exchange/search-mailboxauditlog) in Exchange Online PowerShell verwenden, um das Postfachüberwachungsprotokoll des Benutzers nach Datensätzen zu durchsuchen, die älter als 90 Tage sind.

- Wenn Sie die *AuditLogAgeLimit-Eigenschaft* für ein Postfach geändert haben, bevor die Postfachüberwachung standardmäßig für die Organisation aktiviert ist, wird das vorhandene Überwachungsprotokollalterslimit des Postfachs nicht geändert. Anders ausgedrückt wirkt sich die Standardmäßige Postfachüberwachung nicht auf das aktuelle Alter für Postfachüberwachungsdatensätze aus.

- Um den *Wert AuditLogAgeLimit* für ein Microsoft 365 Gruppenpostfach zu ändern, müssen Sie die `-GroupMailbox` Option in den Befehl **"Set-Mailbox"** einschließen.

- Postfachüberwachungsprotokolleinträge werden in einem Unterordner (namens *"Audits")* im Ordner "Wiederherstellbare Elemente" im Postfach jedes Benutzers gespeichert. Beachten Sie die folgenden Punkte in Bezug auf Postfachüberwachungsdatensätze und den Ordner "Wiederherstellbare Elemente":

  - Postfachüberwachungsdatensätze zählen für das Speicherkontingent des Ordners "Wiederherstellbare Elemente", der standardmäßig 30 GB beträgt (das Warnungskontingent beträgt 20 GB). Das Speicherkontingent wird automatisch auf 100 GB (mit einem Warnkontingent von 90 GB) erhöht, wenn:
    - Ein Haltebereich wird für ein Postfach platziert.
    - Das Postfach wird einer Aufbewahrungsrichtlinie im Compliance Center zugewiesen.

  - Postfachüberwachungseinträge zählen auch mit dem [Ordnerlimit für den Ordner "Wiederherstellbare Elemente".](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits) Im Unterordner "Überwachungen" können maximal 3 Millionen Elemente (Überwachungsdatensätze) gespeichert werden.

    > [!NOTE]
    > Es ist unwahrscheinlich, dass sich die Postfachüberwachung standardmäßig auf das Speicherkontingent oder das Ordnerlimit für den Ordner "Wiederherstellbare Elemente" auswirkt.

    - Sie können den folgenden Befehl in Exchange Online PowerShell ausführen, um die Größe und Anzahl der Elemente im Unterordner "Überwachungen" im Ordner "Wiederherstellbare Elemente" anzuzeigen:

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - Sie können nicht direkt auf einen Überwachungsprotokolleintrag im Ordner "Wiederherstellbare Elemente" zugreifen. Verwenden Sie stattdessen das Cmdlet **"Search-MailboxAuditLog",** oder durchsuchen Sie das Überwachungsprotokoll, um Postfachüberwachungseinträge zu suchen und anzuzeigen.

- Wenn ein Postfach im Compliance Center aufbewahrt oder einer Aufbewahrungsrichtlinie zugewiesen wird, werden Überwachungsprotokolleinträge weiterhin für die Dauer aufbewahrt, die durch die *AuditLogAgeLimit-Eigenschaft* des Postfachs definiert ist (standardmäßig 90 Tage). Um Überwachungsprotokolldatensätze länger für Postfächer aufzubewahren, müssen Sie den *AuditLogAgeLimit-Wert* des Postfachs erhöhen.

- In einer Multi-Geo-Umgebung wird die Geo-übergreifende Postfachüberwachung nicht unterstützt. Wenn beispielsweise einem Benutzer Berechtigungen für den Zugriff auf ein freigegebenes Postfach an einem anderen Geo-Speicherort zugewiesen wurden, werden die von diesem Benutzer ausgeführten Postfachaktionen im Postfachüberwachungsprotokoll des freigegebenen Postfachs nicht protokolliert.
