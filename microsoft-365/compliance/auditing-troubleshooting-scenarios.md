---
title: Durchsuchen des Überwachungsprotokolls zur Problembehandlung bei allgemeinen Szenarien
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
description: Sie können das Überwachungsprotokoll-Such Tool verwenden, um häufige Probleme wie das Untersuchen eines kompromittierten Kontos zu beheben, herauszufinden, wer die e-Mail-Weiterleitung für ein Postfach eingerichtet hat, oder zu ermitteln, warum sich ein externer Benutzer erfolgreich bei Ihrer Organisation angemeldet hat.
ms.openlocfilehash: 8eaff1fa3eea6a0fa60edcfd43f4f2aedb5a5ffc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636383"
---
# <a name="search-the-audit-log-to-investigate-common-support-issues"></a>Durchsuchen des Überwachungsprotokolls zur Untersuchung allgemeiner Supportprobleme

In diesem Artikel wird beschrieben, wie Sie mithilfe des Überwachungsprotokoll-Such Tools häufige Supportprobleme untersuchen können. Dies umfasst die Verwendung des Überwachungsprotokolls für Folgendes:

- Suchen der IP-Adresse des Computers, der für den Zugriff auf ein kompromittiertes Konto verwendet wurde
- Bestimmen, wer die e-Mail-Weiterleitung für ein Postfach eingerichtet hat
- Ermitteln, ob ein Benutzer e-Mail-Elemente in seinem Postfach gelöscht hat
- Ermitteln, ob ein Benutzer eine Posteingangsregel erstellt hat
- Untersuchen der Gründe für eine erfolgreiche Anmeldung durch einen Benutzer außerhalb Ihrer Organisation

## <a name="using-the-audit-log-search-tool"></a>Verwenden des Überwachungsprotokoll-Such Tools

Jedes der in diesem Artikel beschriebenen Problembehandlungsszenarien basiert auf der Verwendung des Überwachungsprotokoll-Such Tools im Security & Compliance Center. In diesem Abschnitt werden die Berechtigungen aufgelistet, die zum Durchsuchen des Überwachungsprotokolls erforderlich sind, und es werden die Schritte zum Zugreifen auf und Ausführen von Überwachungsprotokoll suchen beschrieben. In jedem Szenario-Abschnitt wird erklärt, wie Sie eine Überwachungsprotokoll-Suchabfrage konfigurieren und worauf Sie in den detaillierten Informationen in den Überwachungsdatensätzen achten, die den Suchkriterien entsprechen.

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a>Erforderliche Berechtigungen für die Verwendung des Überwachungsprotokoll-Such Tools

Sie müssen in Exchange Online die Rolle "nur Ansichts Überwachungsprotokolle" oder "Überwachungsprotokolle" zugewiesen sein, um das Überwachungsprotokoll durchsuchen zu können. Standardmäßig sind diese Rollen im Exchange Admin Center zugewiesen den Rollengruppen „Complianceverwaltung“ und „Organisationsverwaltung“ auf der Seite **Berechtigungen**. Globale Administratoren in Office 365 und Microsoft 365 werden automatisch als Mitglieder der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzugefügt. Weitere Informationen finden Sie unter [Verwalten von Rollengruppen in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688).

### <a name="running-audit-log-searches"></a>Ausführung von Überwachungsprotokoll suchen

In diesem Abschnitt werden die Grundlagen für die Erstellung und Ausführung von Überwachungsprotokoll suchen beschrieben. Verwenden Sie diese Anweisungen als Ausgangspunkt für jedes Problembehandlungsszenario in diesem Artikel. Ausführlichere Schritt-für-Schritt-Anweisungen finden Sie unter durch [Suchen des Überwachungsprotokolls](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search).

1. Wechseln Sie [https://protection.office.com/unifiedauditlog](https://protection.office.com/unifiedauditlog) zu, und melden Sie sich mit ihrem geschäftlichen oder Schulkonto an.
    
    Die Seite **Überwachungsprotokollsuche** wird angezeigt. 
    
    ![Konfigurieren Sie Kriterien, und wählen Sie dann suchen aus, um die Suche auszuführen.](../media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
4. Sie können die folgenden Suchkriterien konfigurieren. Jedes Problembehandlungsszenario in diesem Artikel empfiehlt spezielle Anleitungen zum Konfigurieren dieser Felder.
    
    a. **Aktivitäten:** Wählen Sie die Dropdownliste aus, um die Aktivitäten anzuzeigen, nach denen Sie suchen können. Nachdem Sie die Suche ausgeführt haben, werden nur die Überwachungseinträge für die ausgewählten Aktivitäten angezeigt. Wenn Sie **Ergebnisse für alle Aktivitäten anzeigen** auswählen, werden die Ergebnisse für alle Aktivitäten angezeigt, die den anderen Suchkriterien entsprechen. Außerdem müssen Sie dieses Feld in einigen der Problembehandlungsszenarien leer lassen.
    
    b. **Start Datum** und **Enddatum:** wählen Sie einen Datums-und Zeitbereich aus, um die Ereignisse anzuzeigen, die innerhalb dieses Zeitraums aufgetreten sind. Die letzten sieben Tage sind standardmäßig ausgewählt. Das Datum und die Uhrzeit werden im UTC-Format (Coordinated Universal Time) angezeigt. Der maximale Datumsbereich, den Sie angeben können, umfasst 90 Tage.

    c. **Benutzer:** Klicken Sie in dieses Feld, und wählen Sie einen oder mehrere Benutzer aus, für die Suchergebnisse angezeigt werden sollen. Überwachungsdatensätze für die ausgewählte Aktivität, die von den Benutzern ausgeführt werden, die Sie in diesem Feld ausgewählt haben, werden in der Ergebnisliste angezeigt. Lassen Sie dieses Feld leer, um die Einträge für alle Benutzer (und Dienstkonten) in Ihrer Organisation zurückzugeben.
    
    d. **Datei, Ordner oder Website:** Geben Sie einen oder alle Datei-oder Ordnernamen ein, um nach Aktivitäten im Zusammenhang mit der Datei des Ordners zu suchen, die das angegebene Schlüsselwort enthält. Sie können auch die URL einer Datei oder eines Ordners verwenden. Wenn Sie eine URL verwenden, stellen Sie sicher, dass Sie den vollständigen URL-Pfad eingeben oder wenn Sie nur einen Teil der URL eingeben, keine Sonderzeichen oder Leerzeichen enthalten. Lassen Sie dieses Feld leer, um Einträge für alle Dateien und Ordner in Ihrer Organisation zurückzugeben. Dieses Feld bleibt in allen Problembehandlungsszenarien in diesem Artikel leer.
    
5. Wählen Sie **Suchen** aus, um die Suche mit Ihren Suchkriterien auszuführen. 
    
    Die Suchergebnisse werden geladen, und nach ein paar Momenten werden Sie unter **Ergebnisse** auf der Seite **Überwachungsprotokoll Suche** angezeigt. Jeder Abschnitt in diesem Artikel enthält Anleitungen zu den Dingen, die im Kontext des spezifischen Problembehandlungsszenarios gesucht werden sollen.

    Weitere Informationen zum Anzeigen, Filtern oder Exportieren von Überwachungsprotokoll-Suchergebnissen finden Sie unter:

    - [Anzeigen von Suchergebnissen](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [Filtern von Suchergebnissen](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [Exportieren der Suchergebnisse](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="find-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a>Suchen der IP-Adresse des Computers, der für den Zugriff auf ein kompromittiertes Konto verwendet wurde

Die IP-Adresse, die einer von einem beliebigen Benutzer ausgeführten Aktivität entspricht, ist in den meisten Überwachungsdatensätzen enthalten. Informationen zum verwendeten Client sind ebenfalls im Überwachungsprotokoll enthalten.

Hier erfahren Sie, wie Sie eine Überwachungsprotokoll-Suchabfrage für dieses Szenario konfigurieren:

**Aktivitäten:** Wenn relevant für Ihren Fall, wählen Sie eine bestimmte Aktivität aus, nach der gesucht werden soll. Für die Problembehandlung in kompromittierten Konten sollten **Sie die Option Benutzer bei Post** Fach **Aktivitäten unter Exchange-Postfachaktivitäten**Anmelden auswählen. Dadurch werden Überwachungseinträge zurückgegeben, die die IP-Adresse anzeigen, die bei der Anmeldung beim Postfach verwendet wurde. Lassen Sie andernfalls dieses Feld leer, um Überwachungseinträge für alle Aktivitäten zurückzugeben. 

> [!TIP]
> Wenn Sie dieses Feld leer lassen, werden **UserLoggedIn** -Aktivitäten zurückgegeben, bei denen es sich um eine Azure-Active Directory Aktivität handelt, die angibt, dass sich jemand bei einem Benutzerkonto angemeldet hat. Verwenden Sie die Filterung in den Suchergebnissen, um die **UserLoggedIn** -Überwachungseinträge anzuzeigen.

**Start Datum** und **Enddatum:** wählen Sie einen Datumsbereich aus, der für Ihre Untersuchung gilt.

**Benutzer:** Wenn Sie ein kompromittiertes Konto untersuchen, wählen Sie den Benutzer aus, dessen Konto kompromittiert wurde. Dadurch werden Überwachungsdatensätze für Aktivitäten zurückgegeben, die von diesem Benutzerkonto ausgeführt werden.

**Datei, Ordner oder Website:** Lassen Sie dieses Feld leer.

Nachdem Sie die Suche ausgeführt haben, wird die IP-Adresse für jede Aktivität in der Spalte **IP-Adresse** in den Suchergebnissen angezeigt. Wählen Sie den Datensatz in den Suchergebnissen aus, um ausführlichere Informationen auf der Flyout-Seite anzuzeigen.

## <a name="determine-who-set-up-email-forwarding-for-a-mailbox"></a>Bestimmen, wer die e-Mail-Weiterleitung für ein Postfach eingerichtet hat

Wenn die e-Mail-Weiterleitung für ein Postfach konfiguriert ist, werden e-Mail-Nachrichten, die an das Postfach gesendet werden, an ein anderes Postfach weitergeleitet. Nachrichten können an Benutzer innerhalb oder außerhalb Ihrer Organisation weitergeleitet werden. Wenn die e-Mail-Weiterleitung für ein Postfach eingerichtet wurde, ist das zugrunde liegende Exchange Online Cmdlet, das verwendet wird, " **festgelegt-Postfach**".

Hier erfahren Sie, wie Sie eine Überwachungsprotokoll-Suchabfrage für dieses Szenario konfigurieren:

**Aktivitäten:** Lassen Sie dieses Feld leer, damit die Suche Überwachungsdatensätze für alle Aktivitäten zurückgibt. Dies ist erforderlich, um alle Überwachungseinträge im Zusammenhang mit dem Cmdlet " **Satz-Postfach** " zurückzugeben.

**Start Datum** und **Enddatum:** wählen Sie einen Datumsbereich aus, der für Ihre Untersuchung gilt.

**Benutzer:** Lassen Sie dieses Feld leer, wenn Sie ein e-Mail-Weiterleitungs Problem für einen bestimmten Benutzer nicht untersuchen. Auf diese Weise können Sie ermitteln, ob die e-Mail-Weiterleitung für einen beliebigen Benutzer eingerichtet wurde.

**Datei, Ordner oder Website:** Lassen Sie dieses Feld leer.

Nachdem Sie die Suche ausgeführt haben, wählen Sie auf der Suchergebnisseite **Filter Ergebnisse** aus. Geben Sie in das Feld unter **Aktivitäts** Spaltenkopf die **Option Satz-Postfach** ein, sodass nur Überwachungseinträge im Zusammenhang mit dem CmdletSet **-Mailbox** angezeigt werden.

![Filtern der Ergebnisse einer Überwachungsprotokoll Suche](../media/emailforwarding1.png)

An dieser Stelle müssen Sie sich die Details jedes Überwachungsdatensatzes ansehen, um zu ermitteln, ob die Aktivität mit der e-Mail-Weiterleitung zusammenhängt. Wählen Sie den Überwachungseintrag aus, um die **Detail** Flyout-Seite anzuzeigen, und wählen Sie dann **Weitere Informationen**aus. Im folgenden Screenshot und den Beschreibungen werden die Informationen hervorgehoben, die angeben, dass die e-Mail-Weiterleitung im Postfach festgelegt wurde.

![Ausführliche Informationen aus dem Überwachungsprotokoll](../media/emailforwarding2.png)

a. Im Feld **objectID** wird der Alias des Postfachs, auf dem die e-Mail-Weiterleitung festgelegt wurde, angezeigt. Dieses Postfach wird auch in der Spalte **Element** auf der Suchergebnisseite angezeigt.

b. Im Feld **Parameter** gibt der Wert *ForwardingSmtpAddress* an, dass die e-Mail-Weiterleitung für das Postfach festgelegt wurde. In diesem Beispiel wird e-Mail an die e-Mail-Adresse Mike@contoso.com weitergeleitet, die sich außerhalb der alpinehouse.onmicrosoft.com-Organisation befindet.

c. Der Wert *true* für den Parameter *DeliverToMailboxAndForward* gibt an, dass eine Kopie der Nachricht an Sarad@alpinehouse.onmicrosoft.com zugestellt *und* an die durch den *ForwardingSmtpAddress* -Parameter angegebene e-Mail-Adresse weitergeleitet wird, die in diesem Beispiel Mike@contoso.com ist. Wenn der Wert für den *DeliverToMailboxAndForward* -Parameter auf *false*festgelegt ist, wird e-Mail nur an die durch den *ForwardingSmtpAddress* -Parameter angegebene Adresse weitergeleitet. Sie wird nicht an das im Feld **objectID** angegebene Postfach übermittelt.

d. Das **UserID** -Feld gibt den Benutzer an, der die e-Mail-Weiterleitung für das im Feld **objectID** angegebene Postfach festgelegt hat. Dieser Benutzer wird auch in der Spalte **Benutzer** auf der Suchergebnisseite angezeigt. In diesem Fall scheint es, dass der Besitzer des Postfachs die e-Mail-Weiterleitung für Ihr Postfach festgelegt hat.

Wenn Sie feststellen, dass die e-Mail-Weiterleitung nicht für das Postfach festgelegt werden sollte, können Sie Sie entfernen, indem Sie den folgenden Befehl in Exchange Online PowerShell ausführen:

```powershell
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

Weitere Informationen zu den Parametern im Zusammenhang mit der e-Mail-Weiterleitung finden Sie im Artikel zum [Festlegen von Postfächern](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) .

## <a name="determine-if-a-user-deleted-email-items"></a>Ermitteln, ob ein Benutzer e-Mail-Elemente gelöscht hat

Ab Januar 2019 wird Microsoft die postfachüberwachungsprotokollierung standardmäßig für alle Office 365 und Microsoft-Organisationen aktivieren. Dies bedeutet, dass bestimmte von Postfachbesitzern ausgeführte Aktionen automatisch protokolliert werden und dass die entsprechenden Post Fach Überwachungseinträge zur Verfügung stehen, wenn Sie im postfachüberwachungsprotokoll nach diesen suchen. Bevor die postfachüberwachung standardmäßig aktiviert wurde, muss Sie für jedes Benutzerpostfach in Ihrer Organisation manuell aktiviert werden. 

Die standardmäßig protokollierten Postfachaktionen umfassen die SoftDelete-und HardDelete-Postfachaktionen, die von Postfachbesitzern ausgeführt werden. Dies bedeutet, dass Sie die folgenden Schritte zum Durchsuchen des Überwachungsprotokolls für Ereignisse im Zusammenhang mit gelöschten e-Mail-Elementen verwenden können. Weitere Informationen zur postfachüberwachung für standardmäßig finden Sie unter [Verwalten der postfachüberwachung](enable-mailbox-auditing.md).

Hier erfahren Sie, wie Sie eine Überwachungsprotokoll-Suchabfrage für dieses Szenario konfigurieren:

**Aktivitäten:** Wählen Sie unter **Exchange-Postfachaktivitäten**eine oder beide der folgenden Aktionen aus:

- **Gelöschte Nachrichten aus dem Ordner "Gelöschte Elemente":** Diese Aktivität entspricht der **SoftDelete** -Post Fach Überwachungsaktion. Diese Aktivität wird auch protokolliert, wenn ein Benutzer ein Element dauerhaft löscht, indem es ihn auswählt und **UMSCHALT + ENTF**drückt. Nachdem ein Element endgültig gelöscht wurde, kann es vom Benutzer wiederhergestellt werden, bis der Aufbewahrungszeitraum für gelöschte Elemente abläuft.

- **Bereinigte Nachrichten aus dem Postfach:** Diese Aktivität entspricht der **HardDelete** -Post Fach Überwachungsaktion. Dies wird protokolliert, wenn ein Benutzer ein Element aus dem Ordner "refundable Items" löscht. Administratoren können das Inhalts Such Tool im Security and Compliance Center verwenden, um bereinigte Elemente zu suchen und wiederherzustellen, bis der Aufbewahrungszeitraum für gelöschte Elemente abläuft oder länger ist, wenn das Postfach des Benutzers in der Warteschleife steht.

**Start Datum** und **Enddatum:** wählen Sie einen Datumsbereich aus, der für Ihre Untersuchung gilt.

**Benutzer:** Wenn Sie einen Benutzer in diesem Feld auswählen, gibt das Überwachungsprotokoll-Such Tool Überwachungsdatensätze für gelöschte e-Mail-Elemente zurück, die von dem von Ihnen angegebenen Benutzer (SoftDeleted oder HardDeleted) gelöscht wurden. Manchmal ist der Benutzer, der eine e-Mail löscht, möglicherweise nicht der Postfachbesitzer.

**Datei, Ordner oder Website:** Lassen Sie dieses Feld leer.

Nachdem Sie die Suche ausgeführt haben, können Sie die Suchergebnisse filtern, um die Überwachungsdatensätze für vorläufig gelöschte Elemente oder für hart gelöschte Elemente anzuzeigen. Wählen Sie den Überwachungseintrag aus, um die **Detail** Flyout-Seite anzuzeigen, und wählen Sie dann **Weitere Informationen**aus. Zusätzliche Informationen zu dem gelöschten Element, beispielsweise die Betreffzeile und den Speicherort des Elements, wenn es gelöscht wurde, werden im Feld **AffectedItems** angezeigt. Die folgenden Screenshots zeigen ein Beispiel für das **AffectedItems** -Feld aus einem vorläufig gelöschten Element und einem hart gelöschten Element.

**Beispiel für ein AffectedItems-Feld für vorläufig gelöschtes Element**

![Überwachungseintrag für vorläufig gelöschtes Element](../media/softdeleteditem.png)

**Beispiel für ein AffectedItems-Feld für das hart gelöschte Element**

![Überwachungseintrag für das hart gelöschte e-Mail-Element](../media/harddeleteditem.png)

### <a name="recover-deleted-email-items"></a>Wiederherstellen gelöschter e-Mail-Elemente

Benutzer können vorläufig gelöschte Elemente wiederherstellen, wenn der Aufbewahrungszeitraum für gelöschte Elemente nicht abgelaufen ist. In Exchange Online ist der Aufbewahrungszeitraum für gelöschte Elemente standardmäßig 14 Tage, Administratoren können diese Einstellung jedoch auf maximal 30 Tage vergrössern. Zeigen Sie die Benutzer auf die [Wiederherstellung gelöschter Elemente oder e-Mails in Outlook](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4) im Artikel, um Anweisungen zur Wiederherstellung gelöschter Elemente zu erhalten.

Wie bereits erläutert, können Administratoren möglicherweise gelöschte Elemente wiederherstellen, wenn der Aufbewahrungszeitraum für gelöschte Elemente nicht abgelaufen ist oder wenn das Postfach in der Warteschleife aufbewahrt wird, sodass die Elemente bis zum Ablauf der Haltedauer beibehalten werden. Wenn Sie eine Inhaltssuche ausführen, werden im Ordner "Wiederherstellbare Elemente" vorläufig gelöschte und hart gelöschte Elemente in den Suchergebnissen zurückgegeben, wenn Sie mit der Suchabfrage übereinstimmen. Weitere Informationen zum Durchführen von Inhalts suchen finden Sie unter [Inhaltssuche in Office 365](content-search.md).

> [!TIP]
> Um nach gelöschten e-Mail-Elementen zu suchen, suchen Sie nach der Betreffzeile, die im **AffectedItems** -Feld des Überwachungsdatensatzes angezeigt wird, oder in einem Teil der Betreffzeile.

## <a name="determine-if-a-user-created-an-inbox-rule"></a>Ermitteln, ob ein Benutzer eine Posteingangsregel erstellt hat

Wenn Benutzer eine Posteingangsregel für Ihr Exchange Online Postfach erstellen, wird ein entsprechender Überwachungseintrag im Überwachungsprotokoll gespeichert. Weitere Informationen zu Posteingangsregeln finden Sie unter:

- [Verwenden von Posteingangsregeln in Outlook im Internet](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [Verwalten von e-Mail-Nachrichten in Outlook mithilfe von Regeln](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

Hier erfahren Sie, wie Sie eine Überwachungsprotokoll-Suchabfrage für dieses Szenario konfigurieren:

**Aktivitäten:** Wählen Sie unter **Exchange-Postfachaktivitäten**die Option **Posteingangsregel neu-InboxRule erstellen/ändern/aktivieren/deaktivieren**aus.

**Start Datum** und **Enddatum:** wählen Sie einen Datumsbereich aus, der für Ihre Untersuchung gilt.

**Benutzer:** Lassen Sie dieses Feld leer, es sei denn, Sie untersuchen einen bestimmten Benutzer. Auf diese Weise können Sie neue Posteingangsregeln ermitteln, die von jedem Benutzer eingerichtet wurden.

**Datei, Ordner oder Website:** Lassen Sie dieses Feld leer.

Nachdem Sie die Suche ausgeführt haben, werden alle Überwachungseinträge für diese Aktivität in den Suchergebnissen angezeigt. Wählen Sie einen Überwachungseintrag aus, um die **Detail** Flyout-Seite anzuzeigen, und wählen Sie dann **Weitere Informationen**aus. Im Feld **Parameter** werden Informationen zu den Einstellungen für Posteingangsregeln angezeigt. Im folgenden Screenshot und den Beschreibungen werden die Informationen zu Posteingangsregeln hervorgehoben.

![Überwachungseintrag für neue Posteingangsregel](../media/NewInboxRuleRecord.png)

a. Im Feld **objectID** wird der vollständige Name der Posteingangsregel angezeigt. Dieser Name enthält den Alias des Postfachs des Benutzers (beispielsweise "Sarad") und den Namen der Posteingangsregel (beispielsweise "Nachrichten von Administrator verschieben").

b. Im Feld **Parameter** wird die Bedingung der Posteingangsregel angezeigt. In diesem Beispiel wird die Bedingung durch den *from* -Parameter angegeben. Der für den Parameter *from* definierte Wert gibt an, dass die Posteingangsregel auf von admin@alpinehouse.onmicrosoft.com gesendeten e-Mails agiert. Eine vollständige Liste der Parameter, die zum Definieren von Bedingungen für Posteingangsregeln verwendet werden können, finden Sie im Artikel [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule) .

c. Der Parameter *MoveToFolder* gibt die Aktion für die Posteingangsregel an. In diesem Beispiel werden Nachrichten, die von admin@alpinehouse.onmicrosoft.com empfangen werden, in den Ordner " *AdminSearch*" verschoben. Eine vollständige Liste der Parameter, die zum Definieren der Aktion einer Posteingangsregel verwendet werden können, finden Sie auch im Artikel [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule) .

d. Das **UserID** -Feld gibt den Benutzer an, der die im Feld **objectID** angegebene Posteingangsregel erstellt hat. Dieser Benutzer wird auch in der Spalte **Benutzer** auf der Suchergebnisseite angezeigt.

## <a name="investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization"></a>Untersuchen der Gründe für eine erfolgreiche Anmeldung durch einen Benutzer außerhalb Ihrer Organisation

Wenn Sie Überwachungseinträge im Überwachungsprotokoll überprüfen, werden möglicherweise Datensätze angezeigt, die angeben, dass ein externer Benutzer von Azure Active Directory authentifiziert wurde und sich erfolgreich bei Ihrer Organisation angemeldet hat. Beispielsweise kann ein Administrator in contoso.onmicrosoft.com einen Überwachungseintrag sehen, der anzeigt, dass ein Benutzer aus einer anderen Organisation (beispielsweise fabrikam.onmicrosoft.com) sich erfolgreich bei Contoso.onmicrosoft.com angemeldet hat. Ebenso werden möglicherweise Überwachungseinträge angezeigt, die Benutzer mit einem Microsoft-Konto (MSA) anzeigen, beispielsweise eine Outlook.com-oder Live.com, die sich erfolgreich bei Ihrer Organisation angemeldet haben. In diesen Situationen ist die überwachte Aktivität **Benutzer angemeldet**. 

Dieses Verhalten ist so beabsichtigt. Azure Active Directory (Azure AD), der Verzeichnisdienst, ermöglicht die so genannte *Pass-Through-Authentifizierung* , wenn ein externer Benutzer versucht, auf eine SharePoint-Website oder einen OneDrive-Standort in Ihrer Organisation zuzugreifen. Wenn der externe Benutzer versucht, dies zu tun, werden Sie aufgefordert, Ihre Anmeldeinformationen einzugeben. Azure AD verwendet die Anmeldeinformationen, um den Benutzer zu authentifizieren, was bedeutet, dass nur Azure AD überprüft, ob der Benutzer derjenige ist, der er sagt. Die Angabe der erfolgreichen Anmeldung im Überwachungsdatensatz ist das Ergebnis Azure AD Authentifizierung des Benutzers. Die erfolgreiche Anmeldung bedeutet nicht, dass der Benutzer in der Lage war, auf Ressourcen zuzugreifen oder andere Aktionen in Ihrer Organisation auszuführen. Er gibt nur an, dass der Benutzer von Azure AD authentifiziert wurde. Damit ein Pass-Through-Benutzer auf SharePoint-oder OneDrive-Ressourcen zugreifen kann, muss ein Benutzer in Ihrer Organisation eine Ressource explizit für den externen Benutzer freigeben, indem er Ihnen eine Freigabeeinladung oder einen anonymen Freigabe Link sendet. 

> [!NOTE]
> Azure AD ermöglicht die Pass-Through-Authentifizierung nur für *Anwendungen von Erstanbietern*wie SharePoint Online und OneDrive für Unternehmen. Sie ist für andere Drittanbieteranwendungen nicht zulässig.

Im folgenden finden Sie ein Beispiel und Beschreibungen relevanter Eigenschaften in einem Überwachungseintrag für einen **angemeldeten Benutzer** , der ein Ergebnis der Pass-Through-Authentifizierung ist. Wählen Sie den Überwachungseintrag aus, um die **Detail** Flyout-Seite anzuzeigen, und wählen Sie dann **Weitere Informationen**aus.

![Beispiel für einen Überwachungseintrag für die erfolgreiche Pass-Through-Authentifizierung](../media/PassThroughAuth1.png)

   a. Dieses Feld gibt an, dass der Benutzer, der versucht hat, auf eine Ressource in Ihrer Organisation zuzugreifen, nicht im Azure AD Ihrer Organisation gefunden wurde.

   b. In diesem Feld wird der UPN des externen Benutzers angezeigt, der versucht hat, auf eine Ressource in Ihrer Organisation zuzugreifen. Diese Benutzer-ID wird auch in den Eigenschaften **User** und **UserID** im Überwachungseintrag identifiziert.

   c. Die **ApplicationId** -Eigenschaft gibt die Anwendung an, die die Anmeldeanforderung ausgelöst hat. Der Wert von 00000003-0000-0ff1-ce00-000000000000, der in der ApplicationId-Eigenschaft in diesem Überwachungseintrag angezeigt wird, gibt SharePoint Online. OneDrive für Unternehmen hat auch dieselbe ApplicationId.

   d. Dies deutet darauf hin, dass die Pass-Through-Authentifizierung erfolgreich war. Mit anderen Worten: der Benutzer wurde erfolgreich von Azure AD authentifiziert. 

   e. Der **RecordType** -Wert **15** gibt an, dass es sich bei der überwachten Aktivität (UserLoggedIn) um ein Sicherheitstokendienst-Anmeldeereignis (Secure Token Service, STS) in Azure AD handelt.

Weitere Informationen zu den anderen Eigenschaften, die in einem UserLoggedIn-Überwachungseintrag angezeigt werden, finden Sie in den Azure AD bezogenen Schemainformationen im [API-Schema Office 365 Verwaltungsaktivität](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#azure-active-directory-base-schema).

Im folgenden finden Sie zwei Beispiele für Szenarien, die aufgrund der Pass-Through-Authentifizierung dazu führen, dass ein erfolgreicher **Benutzer in** der Überwachungsaktivität angemeldet ist: 

  - Ein Benutzer mit einem Microsoft-Konto (beispielsweise SaraD@Outlook.com) hat versucht, auf ein Dokument in einem OneDrive für Unternehmen-Konto in fourthcoffee.onmicrosoft.com zuzugreifen, und es gibt kein entsprechendes Gastbenutzerkonto für SaraD@Outlook.com in fourthcoffee.onmicrosoft.com.

  - Ein Benutzer mit einem Arbeits-oder Schulkonto in einer Organisation (beispielsweise pilarp@fabrikam.onmicrosoft.com) hat versucht, auf eine SharePoint-Website in contoso.onmicrosoft.com zuzugreifen, und es gibt kein entsprechendes Gastbenutzerkonto für pilarp@fabrikam.com in contoso.onmicrosoft.com.


### <a name="tips-for-investigating-successful-logins-resulting-from-pass-through-authentication"></a>Tipps für die Untersuchung erfolgreicher Anmeldungen, die sich aus der Pass-Through-Authentifizierung ergeben

- Durchsuchen Sie das Überwachungsprotokoll nach Aktivitäten, die von dem externen Benutzer ausgeführt werden, der im Überwachungseintrag für **angemeldete Benutzer** angegeben ist. Geben Sie den UPN für den externen Benutzer in das Feld **Benutzer** ein, und verwenden Sie einen Datumsbereich, falls relevant für Ihr Szenario. Sie können beispielsweise eine Suche mit den folgenden Suchkriterien erstellen:

   ![Suchen nach allen Aktivitäten, die vom externen Benutzer ausgeführt werden](../media/PassThroughAuth2.png)

    Zusätzlich zu den **in Aktivitäten angemeldeten Benutzern** werden möglicherweise andere Überwachungseinträge zurückgegeben, die angeben, dass ein Benutzer in Ihrer Organisation Ressourcen mit dem externen Benutzer freigegeben hat und ob der externe Benutzer ein Dokument, das für Sie freigegeben wurde, aufgerufen, geändert oder heruntergeladen hat.

- Suche nach SharePoint-freigabeaktivitäten, die darauf hindeuten, dass eine Datei für den externen Benutzer freigegeben wurde, der von einem im Überwachungsprotokoll **angemeldeten Benutzer** identifiziert wurde. Weitere Informationen finden Sie unter [Use Sharing Auditing in the Audit Log](use-sharing-auditing.md).

- Exportieren Sie die Überwachungsprotokoll-Suchergebnisse, die Datensätze enthalten, die für Ihre Untersuchung relevant sind, damit Sie Excel für die Suche nach anderen Aktivitäten im Zusammenhang mit dem externen Benutzer verwenden können. Weitere Informationen finden Sie unter [exportieren, konfigurieren und Anzeigen von Überwachungsprotokolldaten Sätzen](export-view-audit-log-records.md).
