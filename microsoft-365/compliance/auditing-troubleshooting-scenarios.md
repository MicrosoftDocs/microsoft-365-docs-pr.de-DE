---
title: Durchsuchen des Überwachungsprotokolls zur Problembehandlung gängiger Szenarien
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie das Microsoft 365-Überwachungsprotokollsuchtool verwenden, um häufige Supportprobleme für E-Mail-Konten zu beheben.
ms.openlocfilehash: 5f753163b5d4d6c04c121a7ce3fae970690a57b0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906093"
---
# <a name="search-the-audit-log-to-investigate-common-support-issues"></a>Durchsuchen des Überwachungsprotokolls, um häufige Supportprobleme zu untersuchen

In diesem Artikel wird beschrieben, wie Sie das Suchtool für Überwachungsprotokolle verwenden, um häufige Supportprobleme zu untersuchen. Dazu gehört die Verwendung des Überwachungsprotokolls für:

- Suchen der IP-Adresse des Computers, der für den Zugriff auf ein gefährdetes Konto verwendet wird
- Bestimmen, wer die E-Mail-Weiterleitung für ein Postfach eingerichtet hat
- Ermitteln, ob ein Benutzer E-Mail-Elemente in ihrem Postfach gelöscht hat
- Ermitteln, ob ein Benutzer eine Posteingangsregel erstellt hat
- Untersuchen, warum es eine erfolgreiche Anmeldung durch einen Benutzer außerhalb Ihrer Organisation gab
- Suchen nach Postfachaktivitäten, die von Benutzern mit Nicht-E5-Lizenzen ausgeführt werden
- Suchen nach Postfachaktivitäten, die von stellvertretungsbenutzern ausgeführt werden

## <a name="using-the-audit-log-search-tool"></a>Verwenden des Überwachungsprotokollsuchtools

Jedes der in diesem Artikel beschriebenen Problembehandlungsszenarien basiert auf der Verwendung des Überwachungsprotokollsuchtools im Security & Compliance Center. In diesem Abschnitt werden die berechtigungen aufgeführt, die zum Durchsuchen des Überwachungsprotokolls erforderlich sind, und die Schritte zum Zugreifen auf und Ausführen von Überwachungsprotokollsuchen beschrieben. In jedem Szenarioabschnitt wird erläutert, wie Sie eine Überwachungsprotokollsuchabfrage konfigurieren und wie Sie in den detaillierten Informationen in den Überwachungsdatensätzen suchen, die den Suchkriterien entsprechen.

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a>Erforderliche Berechtigungen für die Verwendung des Überwachungsprotokollsuchtools

Ihnen muss die Rolle View-Only Überwachungsprotokolle oder Überwachungsprotokolle in Exchange Online zugewiesen werden, um das Überwachungsprotokoll zu durchsuchen. Standardmäßig sind diese Rollen im Exchange Admin Center zugewiesen den Rollengruppen „Complianceverwaltung“ und „Organisationsverwaltung“ auf der Seite **Berechtigungen**. Globale Administratoren in Office 365 und Microsoft 365 werden automatisch als Mitglieder der Rollengruppe Organisationsverwaltung in Exchange Online hinzugefügt. Weitere Informationen finden Sie unter [Verwalten von Rollengruppen in Exchange Online](/Exchange/permissions-exo/role-groups).

### <a name="running-audit-log-searches"></a>Ausführen von Überwachungsprotokollsuchen

In diesem Abschnitt werden die Grundlagen zum Erstellen und Ausführen von Überwachungsprotokollsuchen beschrieben. Verwenden Sie diese Anweisungen als Ausgangspunkt für jedes Problembehandlungsszenario in diesem Artikel. Ausführlichere Schritt-für-Schritt-Anweisungen finden Sie unter [Durchsuchen des Überwachungsprotokolls](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search).

1. Wechseln Sie [https://protection.office.com/unifiedauditlog](https://protection.office.com/unifiedauditlog) zu, und melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.
    
    Die Seite **Überwachungsprotokollsuche** wird angezeigt. 
    
    ![Konfigurieren sie Kriterien, und wählen Sie dann Suchen aus, um die Suche ausführen zu können.](../media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
4. Sie können die folgenden Suchkriterien konfigurieren. Jedes Problembehandlungsszenario in diesem Artikel empfiehlt spezifische Anleitungen zum Konfigurieren dieser Felder.
    
    a. **Aktivitäten:** Wählen Sie die Dropdownliste aus, um die Aktivitäten anzeigen zu können, nach der Sie suchen können. Nachdem Sie die Suche ausgeführt haben, werden nur die Überwachungsdatensätze für die ausgewählten Aktivitäten angezeigt. Wenn **Sie Ergebnisse für alle Aktivitäten anzeigen auswählen,** werden Ergebnisse für alle Aktivitäten angezeigt, die die anderen Suchkriterien erfüllen. Sie müssen dieses Feld auch in einigen Problembehandlungsszenarien leer lassen.
    
    b. **Startdatum** und **Enddatum: Wählen** Sie einen Datums- und Uhrzeitbereich aus, um die Ereignisse zu anzeigen, die innerhalb dieses Zeitraums aufgetreten sind. Die letzten sieben Tage sind standardmäßig ausgewählt. Das Datum und die Uhrzeit werden im UTC-Format (Coordinated Universal Time) angezeigt. Der maximale Datumsbereich, den Sie angeben können, umfasst 90 Tage.

    c. **Benutzer:** Klicken Sie in dieses Feld, und wählen Sie dann einen oder mehrere Benutzer aus, für die Suchergebnisse angezeigt werden sollen. Überwachungsdatensätze für die ausgewählte Aktivität, die von den in diesem Feld ausgewählten Benutzern ausgeführt werden, werden in der Liste der Ergebnisse angezeigt. Lassen Sie dieses Feld leer, um die Einträge für alle Benutzer (und Dienstkonten) in Ihrer Organisation zurückzugeben.
    
    d. **Datei, Ordner oder Website:** Geben Sie einen oder alle Datei- oder Ordnernamen ein, um nach Aktivitäten im Zusammenhang mit der Ordnerdatei zu suchen, die das angegebene Schlüsselwort enthält. Sie können auch die URL einer Datei oder eines Ordners verwenden. Wenn Sie eine URL verwenden, stellen Sie sicher, dass Sie den vollständigen URL-Pfad eingeben oder wenn Sie nur einen Teil der URL eingeben, keine Sonderzeichen oder Leerzeichen enthalten. Lassen Sie dieses Feld leer, um Einträge für alle Dateien und Ordner in Ihrer Organisation zurückzugeben. Dieses Feld wird in allen Problembehandlungsszenarien in diesem Artikel leer gelassen.
    
5. Wählen **Sie Suchen** aus, um die Suche mithilfe Ihrer Suchkriterien ausführen zu können. 
    
    Die Suchergebnisse werden geladen und nach einigen Momenten unter **Ergebnisse** auf der Seite **Überwachungsprotokollsuche** angezeigt. Jeder abschnitt in diesem Artikel enthält Anleitungen zu Denkhilfen, die im Kontext des jeweiligen Problembehandlungsszenarios zu suchen sind.

    Weitere Informationen zum Anzeigen, Filtern oder Exportieren von Überwachungsprotokollsuchergebnissen finden Sie unter:

    - [Anzeigen von Suchergebnissen](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [Filtern von Suchergebnissen](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [Exportieren der Suchergebnisse](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="find-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a>Suchen der IP-Adresse des Computers, der für den Zugriff auf ein gefährdetes Konto verwendet wird

Die IP-Adresse, die einer Aktivität eines beliebigen Benutzers entspricht, ist in den meisten Überwachungsdatensätzen enthalten. Informationen zum verwendeten Client sind auch im Überwachungsdatensatz enthalten.

So konfigurieren Sie eine Überwachungsprotokollsuchabfrage für dieses Szenario:

**Aktivitäten:** Wählen Sie bei Relevanz für Ihren Fall eine bestimmte Aktivität aus, nach der gesucht werden soll. Zur Problembehandlung bei gefährdeten Konten sollten Sie die Option Benutzer, der sich **bei Postfachaktivitäten** unter **Exchange-Postfachaktivitäten angemeldet hat, auswählen.** Dadurch werden Überwachungsdatensätze zurückgegeben, die die BEI der Anmeldung beim Postfach verwendete IP-Adresse anzeigen. Lassen Sie andernfalls dieses Feld leer, um Überwachungsdatensätze für alle Aktivitäten zurück zu geben. 

> [!TIP]
> Wenn Sie dieses Feld leer lassen, werden **UserLoggedIn-Aktivitäten** zurückgeben, bei denen es sich um eine Azure Active Directory-Aktivität handelt, die angibt, dass sich jemand bei einem Benutzerkonto angemeldet hat. Verwenden Sie die Filterung in den Suchergebnissen, um die **UserLoggedIn-Überwachungsdatensätze** anzeigen.

**Startdatum** und **Enddatum: Wählen** Sie einen Datumsbereich aus, der für Ihre Untersuchung gilt.

**Benutzer:** Wenn Sie ein gefährdetes Konto untersuchen, wählen Sie den Benutzer aus, dessen Konto gefährdet wurde. Dadurch werden Überwachungsdatensätze für Aktivitäten zurückgegeben, die von diesem Benutzerkonto ausgeführt werden.

**Datei, Ordner oder Website:** Lassen Sie dieses Feld leer.

Nachdem Sie die Suche ausgeführt haben, wird die IP-Adresse für jede Aktivität in der Spalte **IP-Adresse** in den Suchergebnissen angezeigt. Wählen Sie den Datensatz in den Suchergebnissen aus, um detailliertere Informationen auf der Flyoutseite anzeigen zu können.

## <a name="determine-who-set-up-email-forwarding-for-a-mailbox"></a>Bestimmen, wer die E-Mail-Weiterleitung für ein Postfach eingerichtet hat

Wenn die E-Mail-Weiterleitung für ein Postfach konfiguriert ist, werden E-Mail-Nachrichten, die an das Postfach gesendet werden, an ein anderes Postfach weitergeleitet. Nachrichten können an Benutzer innerhalb oder außerhalb Ihrer Organisation weitergeleitet werden. Wenn die E-Mail-Weiterleitung für ein Postfach eingerichtet ist, ist das zugrunde liegende Exchange **Online-Cmdlet Set-Mailbox**.

So konfigurieren Sie eine Überwachungsprotokollsuchabfrage für dieses Szenario:

**Aktivitäten:** Lassen Sie dieses Feld leer, sodass die Suche Überwachungsdatensätze für alle Aktivitäten zurückgibt. Dies ist erforderlich, um Überwachungsdatensätze im Zusammenhang mit dem **Cmdlet Set-Mailbox** zurücksennen.

**Startdatum** und **Enddatum: Wählen** Sie einen Datumsbereich aus, der für Ihre Untersuchung gilt.

**Benutzer:** Lassen Sie dieses Feld leer, es sei denn, Sie untersuchen ein E-Mail-Weiterleitungsproblem für einen bestimmten Benutzer. Auf diese Weise können Sie ermitteln, ob die E-Mail-Weiterleitung für jeden Benutzer eingerichtet wurde.

**Datei, Ordner oder Website:** Lassen Sie dieses Feld leer.

Nachdem Sie die Suche ausgeführt haben, wählen Sie **Auf der** Suchergebnissenseite Ergebnisse filtern aus. Geben Sie im Feld unter **Spaltenüberschrift** Aktivität **Set-Mailbox** ein, damit nur Überwachungsdatensätze im Zusammenhang mit dem **Cmdlet Set-Mailbox** angezeigt werden.

![Filtern der Ergebnisse einer Überwachungsprotokollsuche](../media/emailforwarding1.png)

An diesem Punkt müssen Sie sich die Details der einzelnen Überwachungsdatensatze anschauen, um festzustellen, ob die Aktivität im Zusammenhang mit der E-Mail-Weiterleitung steht. Wählen Sie den Überwachungsdatensatz aus, um die **Flyoutseite Details** anzuzeigen, und wählen Sie dann **Weitere Informationen aus.** Im folgenden Screenshot und in den Beschreibungen werden die Informationen hervorgehoben, die darauf hinweisen, dass die E-Mail-Weiterleitung für das Postfach festgelegt wurde.

![Detaillierte Informationen aus dem Überwachungsdatensatz](../media/emailforwarding2.png)

a. Im Feld **ObjectId** wird der Alias des Postfachs angezeigt, für das die E-Mail-Weiterleitung festgelegt wurde. Dieses Postfach wird auch in der Spalte **Element** auf der Suchergebnissetseite angezeigt.

b. Im Feld **Parameter gibt** der Wert *ForwardingSmtpAddress* an, dass die E-Mail-Weiterleitung für das Postfach festgelegt wurde. In diesem Beispiel wird E-Mail an die E-Mail-Adresse mike@contoso.com weitergeleitet, die sich außerhalb der alpinehouse.onmicrosoft.com befindet.

c. Der *True-Wert* für den *Parameter DeliverToMailboxAndForward* gibt an, dass eine  Kopie der Nachricht an sarad@alpinehouse.onmicrosoft.com übermittelt und an die E-Mail-Adresse weitergeleitet wird, die durch den *Parameter ForwardingSmtpAddress* angegeben wird, der in diesem Beispiel mike@contoso.com. Wenn der Wert für den *Parameter DeliverToMailboxAndForward* auf *False* festgelegt ist, wird die E-Mail nur an die adresse weitergeleitet, die durch den *Parameter ForwardingSmtpAddress angegeben* wird. Es wird nicht an das postfach übermittelt, das im **Feld ObjectId angegeben** ist.

d. Das **Feld UserId** gibt den Benutzer an, der die E-Mail-Weiterleitung für das im Feld **ObjectId** angegebene Postfach festgelegt hat. Dieser Benutzer wird auch in der **Spalte Benutzer** auf der Suchergebnissetseite angezeigt. In diesem Fall scheint der Besitzer des Postfachs die E-Mail-Weiterleitung für ihr Postfach festgelegt zu haben.

Wenn Sie feststellen, dass die E-Mail-Weiterleitung nicht für das Postfach festgelegt werden soll, können Sie sie entfernen, indem Sie den folgenden Befehl in Exchange Online PowerShell ausführen:

```powershell
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

Weitere Informationen zu den Parametern im Zusammenhang mit der [E-Mail-Weiterleitung](/powershell/module/exchange/set-mailbox) finden Sie im Artikel Set-Mailbox.

## <a name="determine-if-a-user-deleted-email-items"></a>Ermitteln, ob ein Benutzer E-Mail-Elemente gelöscht hat

Ab Januar 2019 aktiviert Microsoft die Postfach-Überwachungsprotokollierung standardmäßig für alle Office 365- und Microsoft-Organisationen. Dies bedeutet, dass bestimmte Aktionen, die von Postfachbesitzern ausgeführt werden, automatisch protokolliert werden, und die entsprechenden Postfach-Überwachungsdatensätze sind verfügbar, wenn Sie im Postfach-Überwachungsprotokoll nach diesen suchen. Bevor die Postfachüberwachung standardmäßig aktiviert wurde, musste sie für jedes Benutzerpostfach in Ihrer Organisation manuell aktiviert werden. 

Die standardmäßig protokollierten Postfachaktionen umfassen die Postfachaktionen SoftDelete und HardDelete, die von Postfachbesitzern ausgeführt werden. Dies bedeutet, dass Sie die folgenden Schritte ausführen können, um das Überwachungsprotokoll nach Ereignissen im Zusammenhang mit gelöschten E-Mail-Elementen zu durchsuchen. Weitere Informationen zur Postfachüberwachung standardmäßig finden Sie unter [Verwalten der Postfachüberwachung](enable-mailbox-auditing.md).

So konfigurieren Sie eine Überwachungsprotokollsuchabfrage für dieses Szenario:

**Aktivitäten:** Wählen **Sie unter Exchange-Postfachaktivitäten** eine oder beide der folgenden Aktivitäten aus:

- **Gelöschte Nachrichten aus dem Ordner "Gelöschte Elemente":** Diese Aktivität entspricht der **SoftDelete-Postfachüberwachungsaktion.** Diese Aktivität wird auch protokolliert, wenn ein Benutzer ein Element durch Auswahl und Drücken von **Umschalt+Löschen** endgültig löscht. Nachdem ein Element endgültig gelöscht wurde, kann der Benutzer es wiederherstellen, bis der Aufbewahrungszeitraum für gelöschte Elemente abläuft.

- **Gelöschte Nachrichten aus dem Postfach:** Diese Aktivität entspricht der Aktion zur Überwachung des **HardDelete-Postfachs.** Dies wird protokolliert, wenn ein Benutzer ein Element aus dem Ordner "Wiederherstellbare Elemente" entfernt. Administratoren können das Tool für die Inhaltssuche im Security and Compliance Center verwenden, um gelöschte Elemente zu suchen und wiederherstellungen, bis der Aufbewahrungszeitraum für gelöschte Elemente abläuft oder länger, wenn sich das Postfach des Benutzers im Haltebereich befindet.

**Startdatum** und **Enddatum: Wählen** Sie einen Datumsbereich aus, der für Ihre Untersuchung gilt.

**Benutzer:** Wenn Sie einen Benutzer in diesem Feld auswählen, gibt das Überwachungsprotokollsuchtool Überwachungsdatensätze für E-Mail-Elemente zurück, die vom angegebenen Benutzer gelöscht wurden (SoftDeleted oder HardDeleted). Manchmal ist der Benutzer, der eine E-Mail löscht, möglicherweise nicht der Postfachbesitzer.

**Datei, Ordner oder Website:** Lassen Sie dieses Feld leer.

Nachdem Sie die Suche ausgeführt haben, können Sie die Suchergebnisse filtern, um die Überwachungsdatensätze für elemente mit soft-deleted oder für hart gelöschte Elemente anzeigen zu können. Wählen Sie den Überwachungsdatensatz aus, um die **Flyoutseite Details** anzuzeigen, und wählen Sie dann **Weitere Informationen aus.** Zusätzliche Informationen zum gelöschten Element, z. B. die Betreffzeile und der Speicherort des Elements, wenn es gelöscht wurde, werden im **Feld AffectedItems** angezeigt. Die folgenden Screenshots zeigen ein Beispiel für das **Feld AffectedItems** aus einem soft-deleted-Element und einem hart gelöschten Element.

**Beispiel für das Feld "AffectedItems" für "Soft-Deleted"-Element**

![Überwachungsdatensatz für soft-deleted-Element](../media/softdeleteditem.png)

**Beispiel für das Feld "AffectedItems" für ein fest gelöschtes Element**

![Überwachungsdatensatz für fest gelöschtes E-Mail-Element](../media/harddeleteditem.png)

### <a name="recover-deleted-email-items"></a>Wiederherstellen gelöschter E-Mail-Elemente

Benutzer können elemente mit soft-deleted wiederherstellen, wenn der Aufbewahrungszeitraum für gelöschte Elemente nicht abgelaufen ist. In Exchange Online beträgt der Standardaufbewahrungszeitraum für gelöschte Elemente 14 Tage, administratoren können diese Einstellung jedoch auf maximal 30 Tage erhöhen. Verweisen Sie Benutzer auf den [Artikel Wiederherstellen gelöschter Elemente](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4) oder E-Mails in Outlook im Web, um Anweisungen zum Wiederherstellen gelöschter Elemente zu erhalten.

Wie bereits erläutert, können Administratoren hart gelöschte Elemente möglicherweise wiederherstellen, wenn der Aufbewahrungszeitraum für gelöschte Elemente nicht abgelaufen ist oder das Postfach in der Warteschleife ist. In diesem Fall werden Elemente bis zum Ablauf der Aufbewahrungsdauer aufbewahrt. Wenn Sie eine Inhaltssuche ausführen, werden soft-deleted- und hard-deleted-Elemente im Ordner "Wiederherstellbare Elemente" in den Suchergebnissen zurückgegeben, wenn sie mit der Suchabfrage übereinstimmen. Weitere Informationen zum Ausführen von Inhaltssuchen finden Sie unter [Inhaltssuche in Office 365](content-search.md).

> [!TIP]
> Um nach gelöschten E-Mail-Elementen zu suchen, suchen Sie nach der Betreffzeile, die im **Feld AffectedItems** im Überwachungsdatensatz angezeigt wird.

## <a name="determine-if-a-user-created-an-inbox-rule"></a>Ermitteln, ob ein Benutzer eine Posteingangsregel erstellt hat

Wenn Benutzer eine Posteingangsregel für ihr Exchange Online-Postfach erstellen, wird ein entsprechender Überwachungsdatensatz im Überwachungsprotokoll gespeichert. Weitere Informationen zu Posteingangsregeln finden Sie unter:

- [Verwenden von Posteingangsregeln in Outlook im Web](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [Verwalten von E-Mail-Nachrichten in Outlook mithilfe von Regeln](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

So konfigurieren Sie eine Überwachungsprotokollsuchabfrage für dieses Szenario:

**Aktivitäten:** Wählen **Sie unter Exchange-Postfachaktivitäten** **die Option New-InboxRule Posteingangsregel erstellen/ändern/aktivieren/deaktivieren aus.**

**Startdatum** und **Enddatum: Wählen** Sie einen Datumsbereich aus, der für Ihre Untersuchung gilt.

**Benutzer:** Lassen Sie dieses Feld leer, es sei denn, Sie untersuchen einen bestimmten Benutzer. Auf diese Weise können Sie neue Posteingangsregeln identifizieren, die von jedem Benutzer eingerichtet wurden.

**Datei, Ordner oder Website:** Lassen Sie dieses Feld leer.

Nachdem Sie die Suche ausgeführt haben, werden alle Überwachungsdatensätze für diese Aktivität in den Suchergebnissen angezeigt. Wählen Sie einen Überwachungsdatensatz aus, um die **Flyoutseite Details** anzuzeigen, und wählen Sie dann **Weitere Informationen aus.** Informationen zu den Posteingangsregeleinstellungen werden im Feld **Parameter** angezeigt. Im folgenden Screenshot und in den Beschreibungen werden die Informationen zu Posteingangsregeln hervorgehoben.

![Überwachungsdatensatz für neue Posteingangsregel](../media/NewInboxRuleRecord.png)

a. Im **Feld ObjectId** wird der vollständige Name der Posteingangsregel angezeigt. Dieser Name enthält den Alias des Postfachs des Benutzers (z. B. SaraD) und den Namen der Posteingangsregel (z. B. "Nachrichten vom Administrator verschieben").

b. Im Feld **Parameter** wird die Bedingung der Posteingangsregel angezeigt. In diesem Beispiel wird die Bedingung durch den *Parameter From* angegeben. Der für den *Parameter From* definierte Wert gibt an, dass die Posteingangsregel auf E-Mails wirkt, die von einem admin@alpinehouse.onmicrosoft.com. Eine vollständige Liste der Parameter, die zum Definieren von Bedingungen von Posteingangsregeln verwendet werden können, finden Sie im [Artikel New-InboxRule.](/powershell/module/exchange/new-inboxrule)

c. Der *Parameter MoveToFolder* gibt die Aktion für die Posteingangsregel an. In diesem Beispiel werden nachrichten, die von admin@alpinehouse.onmicrosoft.com empfangen werden, in den Ordner *"AdminSearch" verschoben.* Eine vollständige Liste der Parameter, die zum Definieren der Aktion einer Posteingangsregel verwendet werden können, finden Sie im Artikel [New-InboxRule.](/powershell/module/exchange/new-inboxrule)

d. Das **Feld UserId** gibt den Benutzer an, der die im Feld **ObjectId** angegebene Posteingangsregel erstellt hat. Dieser Benutzer wird auch in der **Spalte Benutzer** auf der Suchergebnissetseite angezeigt.

## <a name="investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization"></a>Untersuchen, warum es eine erfolgreiche Anmeldung durch einen Benutzer außerhalb Ihrer Organisation gab

Beim Überprüfen von Überwachungsdatensätzen im Überwachungsprotokoll werden möglicherweise Datensätze angezeigt, die darauf hinweisen, dass ein externer Benutzer von Azure Active Directory authentifiziert und erfolgreich bei Ihrer Organisation angemeldet wurde. Beispielsweise wird einem Administrator in contoso.onmicrosoft.com möglicherweise ein Überwachungsdatensatz angezeigt, der zeigt, dass ein Benutzer aus einer anderen Organisation (z. B. fabrikam.onmicrosoft.com) erfolgreich bei einem contoso.onmicrosoft.com. Auf ähnliche Weise werden Möglicherweise Überwachungsdatensätze angezeigt, die darauf hinweisen, dass Benutzer mit einem Microsoft-Konto (MSA), z. B. Outlook.com oder Live.com, erfolgreich bei Ihrer Organisation angemeldet sind. In diesen Situationen ist die überwachte Aktivität **Benutzer angemeldet.** 

Es handelt sich hierbei um ein beabsichtigtes Verhalten. Azure Active Directory (Azure AD), der Verzeichnisdienst, ermöglicht eine so genannte *Pass-Through-Authentifizierung,* wenn ein externer Benutzer versucht, auf eine #A0 oder einen #A1 in Ihrer Organisation zu zugreifen. Wenn der externe Benutzer versucht, dies zu tun, wird er zur Eingabe seiner Anmeldeinformationen aufgefordert. Azure AD verwendet die Anmeldeinformationen, um den Benutzer zu authentifizieren, was bedeutet, dass nur Azure AD überprüft, ob der Benutzer der Benutzer ist, von dem er sagt, dass er es ist. Der Hinweis auf die erfolgreiche Anmeldung im Überwachungsdatensatz ist das Ergebnis der Authentifizierung des Benutzers durch Azure AD. Die erfolgreiche Anmeldung bedeutet nicht, dass der Benutzer auf Ressourcen zugreifen oder andere Aktionen in Ihrer Organisation ausführen konnte. Es gibt nur an, dass der Benutzer von Azure AD authentifiziert wurde. Damit ein Pass-Through-Benutzer auf SharePoint- oder #A0 zugreifen kann, müsste ein Benutzer in Ihrer Organisation eine Ressource explizit für den externen Benutzer freigeben, indem er ihm eine Freigabeeinladung oder einen anonymen Freigabelink sendet. 

> [!NOTE]
> Azure AD ermöglicht die Pass-Through-Authentifizierung nur für *Erstanwendungen,* z. B. SharePoint Online und OneDrive for Business. Es ist für andere Drittanbieteranwendungen nicht zulässig.

Im Folgenden finden Sie ein Beispiel und Beschreibungen der relevanten Eigenschaften in einem Überwachungsdatensatz für einen angemeldeten **Benutzer,** der ein Ergebnis der Pass-Through-Authentifizierung ist. Wählen Sie den Überwachungsdatensatz aus, um die **Flyoutseite Details** anzuzeigen, und wählen Sie dann **Weitere Informationen aus.**

![Beispiel für einen Überwachungsdatensatz für eine erfolgreiche Pass-Thru-Authentifizierung](../media/PassThroughAuth1.png)

   a. Dieses Feld gibt an, dass der Benutzer, der versucht hat, auf eine Ressource in Ihrer Organisation zu zugreifen, nicht in Azure AD Ihrer Organisation gefunden wurde.

   b. In diesem Feld wird der UPN des externen Benutzers angezeigt, der versucht hat, auf eine Ressource in Ihrer Organisation zu zugreifen. Diese Benutzer-ID wird auch in den **Eigenschaften User** und **UserId** im Überwachungsdatensatz identifiziert.

   c. Die **ApplicationId-Eigenschaft** identifiziert die Anwendung, die die Anmeldeanforderung ausgelöst hat. Der Wert 00000003-0000-0ff1-ce00-00000000000000, der in der ApplicationId-Eigenschaft in diesem Überwachungsdatensatz angezeigt wird, gibt SharePoint Online an. OneDrive for Business verfügt auch über dieselbe ApplicationId.

   d. Dies weist darauf hin, dass die Pass-Through-Authentifizierung erfolgreich war. Anders ausgedrückt: Der Benutzer wurde erfolgreich von Azure AD authentifiziert. 

   e. Der **RecordType-Wert** **von 15** gibt an, dass es sich bei der überwachten Aktivität (UserLoggedIn) um ein Secure Token Service (STS)-Anmeldeereignis in Azure AD handelt.

Weitere Informationen zu den anderen Eigenschaften, die in einem UserLoggedIn-Überwachungsdatensatz angezeigt werden, finden Sie in den Azure AD-bezogenen Schemainformationen im [Office 365-Verwaltungsaktivitäts-API-Schema](/office/office-365-management-api/office-365-management-activity-api-schema#azure-active-directory-base-schema).

Im Folgenden finden Sie zwei Beispielszenarien, die aufgrund der Pass-Through-Authentifizierung zu einer erfolgreichen Benutzer-angemeldeten Überwachungsaktivität führen würden:  

  - Ein Benutzer mit einem #A0 (z. B. SaraD@outlook.com) hat versucht, auf ein Dokument in einem OneDrive for #A1 in fourthcoffee.onmicrosoft.com zu zugreifen, und es gibt kein entsprechendes Gastbenutzerkonto für SaraD@outlook.com in fourthcoffee.onmicrosoft.com.

  - Ein Benutzer mit einem Arbeits- oder Schulkonto in einer Organisation (z. B. pilarp@fabrikam.onmicrosoft.com) hat versucht, auf eine SharePoint-Website in contoso.onmicrosoft.com zu zugreifen, und es gibt kein entsprechendes Gastbenutzerkonto für pilarp@fabrikam.com in contoso.onmicrosoft.com.

### <a name="tips-for-investigating-successful-logins-resulting-from-pass-through-authentication"></a>Tipps zum Untersuchen erfolgreicher Anmeldungen, die sich aus der Pass-Through-Authentifizierung ergeben

- Durchsuchen Sie das Überwachungsprotokoll nach Aktivitäten, die von dem externen Benutzer ausgeführt werden, der im **Überwachungsdatensatz "Angemeldeter Benutzer"** identifiziert ist. Geben Sie den UPN für den externen Benutzer in das Feld **Benutzer** ein, und verwenden Sie einen Datumsbereich, sofern dies für Ihr Szenario relevant ist. Sie können z. B. eine Suche mit den folgenden Suchkriterien erstellen:

   ![Suchen nach allen Aktivitäten, die vom externen Benutzer ausgeführt werden](../media/PassThroughAuth2.png)

    Zusätzlich zu  den angemeldeten Aktivitäten des Benutzers können andere Überwachungsdatensätze zurückgegeben werden, z. B. solche, die angeben, dass ein Benutzer in Ihrer Organisation Ressourcen für den externen Benutzer freigegeben hat und ob der externe Benutzer auf ein dokument zugegriffen, geändert oder heruntergeladen hat, das für sie freigegeben wurde.

- Suchen Sie nach SharePoint-Freigabeaktivitäten, die darauf hinweisen, dass eine Datei für den externen Benutzer freigegeben wurde, der durch einen **angemeldeten Überwachungsdatensatz** des Benutzers identifiziert wurde. Weitere Informationen finden Sie unter [Verwenden der Freigabeüberwachung im Überwachungsprotokoll](use-sharing-auditing.md).

- Exportieren Sie die Suchergebnisse des Überwachungsprotokolls, die datensätze enthalten, die für Ihre Untersuchung relevant sind, sodass Sie excel verwenden können, um nach anderen Aktivitäten im Zusammenhang mit dem externen Benutzer zu suchen. Weitere Informationen finden Sie unter Exportieren, Konfigurieren und Anzeigen  [von Überwachungsprotokolleinträgen](export-view-audit-log-records.md).

## <a name="search-for-mailbox-activities-performed-by-users-with-non-e5-licenses"></a>Suchen nach Postfachaktivitäten, die von Benutzern mit Nicht-E5-Lizenzen ausgeführt werden

Selbst [](enable-mailbox-auditing.md) wenn die Postfachüberwachung für Ihre Organisation standardmäßig aktiviert ist, können Sie feststellen, dass Postfachüberwachungsereignisse für einige Benutzer nicht in Überwachungsprotokollsuchen mithilfe des Compliance Centers, des **Cmdlets Search-UnifiedAuditLog** oder der Office 365-Verwaltungsaktivitäts-API gefunden werden. Der Grund dafür ist, dass Postfach-Überwachungsereignisse nur für Benutzer mit E5-Lizenzen zurückgegeben werden, wenn Sie eine der vorherigen Methoden zum Durchsuchen des einheitlichen Überwachungsprotokolls verwenden.

Zum Abrufen von Postfach-Überwachungsprotokolleinträgen für Nicht-E5-Benutzer können Sie eine der folgenden Problemumgehungen ausführen:

- Manuelles Aktivieren der Postfachüberwachung für einzelne Postfächer (Führen Sie den `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` Befehl in Exchange Online PowerShell aus). Suchen Sie anschließend mithilfe des Compliance Centers, des **Cmdlets Search-UnifiedAuditLog** oder der Office 365-Verwaltungsaktivitäts-API nach Postfach-Überwachungsaktivitäten.
  
  > [!NOTE]
  > Wenn die Postfachüberwachung bereits für das Postfach aktiviert zu sein scheint, ihre Suchen jedoch keine Ergebnisse zurückgeben, ändern Sie den Wert des _Parameters AuditEnabled_ in und dann `$false` wieder in `$true` .
  
- Verwenden Sie die folgenden Cmdlets in Exchange Online PowerShell:

  - [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) zum Durchsuchen des Postfach-Überwachungsprotokolls nach bestimmten Benutzern.

  - [New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) zum Durchsuchen des Postfach-Überwachungsprotokolls nach bestimmten Benutzern und zum Senden der Ergebnisse per E-Mail an angegebene Empfänger.

## <a name="search-for-mailbox-activities-performed-in-a-specific-mailbox-including-shared-mailboxes"></a>Suchen nach Postfachaktivitäten, die in einem bestimmten Postfach ausgeführt werden (einschließlich freigegebener Postfächer)

Wenn Sie  die Dropdownliste Benutzer im Überwachungsprotokollsuchtool im Compliance Center oder den **Befehl Search-UnifiedAuditLog -UserIds** in Exchange Online PowerShell verwenden, können Sie nach Aktivitäten suchen, die von einem bestimmten Benutzer ausgeführt werden. Bei Postfach-Überwachungsaktivitäten sucht diese Art von Suche nach Aktivitäten, die vom angegebenen Benutzer ausgeführt werden. Es garantiert nicht, dass alle Aktivitäten, die im gleichen Postfach ausgeführt werden, in den Suchergebnissen zurückgegeben werden. Beispielsweise gibt eine Überwachungsprotokollsuche keine Überwachungsdatensätze für Aktivitäten zurück, die von einem Stellvertretungsbenutzer ausgeführt werden, da die Suche nach Postfachaktivitäten, die von einem bestimmten Benutzer ausgeführt werden, keine Aktivitäten zurücksendet, die von einem Stellvertretungsbenutzer ausgeführt werden, dem Berechtigungen für den Zugriff auf das Postfach eines anderen Benutzers zugewiesen wurden. (Ein Stellvertretungsbenutzer ist eine Person, der die Postfachberechtigung SendAs, SendOnBehalf oder FullAccess für das Postfach eines anderen Benutzers zugewiesen wurde.)

Darüber hinaus gibt die Verwendung der **Dropdownliste** Benutzer im Suchtool für Überwachungsprotokolle oder **search-UnifiedAuditLog -UserIds** keine Ergebnisse für Aktivitäten zurück, die in einem freigegebenen Postfach ausgeführt werden.

Verwenden Sie beim Ausführen des **Cmdlets Search-UnifiedAuditLog** die folgende Syntax, um nach den Aktivitäten zu suchen, die in einem bestimmten Postfach ausgeführt werden, oder um nach Aktivitäten zu suchen, die in einem freigegebenen Postfach ausgeführt werden:

```powershell
Search-UnifiedAuditLog  -StartDate <date> -EndDate <date> -FreeText (Get-Mailbox <mailbox identity).ExchangeGuid
```

Der folgende Befehl gibt beispielsweise Überwachungsdatensätze für Aktivitäten zurück, die zwischen August 2020 und Oktober 2020 im freigegebenen Postfach des Contoso Compliance Teams ausgeführt wurden:

```powershell
Search-UnifiedAuditLog  -StartDate 08/01/2020 -EndDate 10/31/2020 -FreeText (Get-Mailbox complianceteam@contoso.onmicrosoft.com).ExchangeGuid
```

Alternativ können Sie das **Cmdlet Search-MailboxAuditLog** verwenden, um nach Überwachungsdatensätzen für Aktivitäten zu suchen, die in einem bestimmten Postfach ausgeführt werden. Dies umfasst die Suche nach Aktivitäten, die in einem freigegebenen Postfach ausgeführt werden.

Im folgenden Beispiel werden Postfach-Überwachungsprotokolleinträge für Aktivitäten zurückgegeben, die im freigegebenen Postfach des Contoso Compliance Teams ausgeführt werden:

```powershell
Search-MailboxAuditLog -Identity complianceteam@contoso.onmicrosoft.com -StartDate 08/01/2020 -EndDate 10/31/2020 -ShowDetails
```

Im folgenden Beispiel werden Postfach-Überwachungsprotokolleinträge für Aktivitäten zurückgegeben, die im angegebenen Postfach von Stellvertretungsbenutzern ausgeführt werden:

```powershell
Search-MailboxAuditLog -Identity <mailbox identity> -StartDate <date> -EndDate <date> -LogonTypes Delegate -ShowDetails
```

Sie können auch das **Cmdlet New-MailboxAuditLogSearch** verwenden, um das Überwachungsprotokoll nach einem bestimmten Postfach zu durchsuchen und die Ergebnisse per E-Mail an angegebene Empfänger zu senden.