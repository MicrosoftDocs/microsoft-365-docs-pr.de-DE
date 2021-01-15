---
title: Verwenden der erweiterten Überwachung zur Untersuchung kompromittierter Konten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Verwenden Sie die MailItemsAccessed-Postfachüberwachungsaktion, um forensische Untersuchungen kompromittierter Benutzerkonten auszuführen.
ms.openlocfilehash: 15379a5c24ee222cf097e94d46dc46de0e385820
ms.sourcegitcommit: c1f9a1b2a34146c51c9e33c4119a388b249ce7a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49868003"
---
# <a name="use-advanced-audit-to-investigate-compromised-accounts"></a>Verwenden der erweiterten Überwachung zur Untersuchung kompromittierter Konten

Ein kompromittiertes Benutzerkonto (auch als *Kontoübernahme* bezeichnet) ist ein Angriffstyp, bei dem ein Angreifer Zugriff auf ein Benutzerkonto erhält und als Benutzer agiert. Diese Arten von Angriffen richten manchmal mehr Schaden an, als der Angreifer möglicherweise beabsichtigt. Bei der Untersuchung von kompromittierten E-Mail-Konten müssen Sie davon ausgehen, dass mehr E-Mail-Daten kompromittiert sind, als durch Nachverfolgen der tatsächlichen Anwesenheit des Angreifers ermittelt werden kann. Abhängig vom Typ der Daten in E-Mail-Nachrichten müssen Sie davon ausgehen, dass vertrauliche Informationen kompromittiert wurden, oder es werden Geldbußen im Zusammenhang mit gesetzlichen Vorschriften fällig, wenn Sie nicht nachweisen können, dass keine vertrauliche Informationen offengelegt wurden. So können beispielsweise für HIPAA-regulierte Organisationen erhebliche Geldbußen anfallen, wenn nachgewiesen wird, dass Gesundheitsinformationen von Patienten (PHI) offengelegt wurden. In diesen Fällen ist es unwahrscheinlich, dass Angreifer sich für die PHI interessieren, doch Organisationen müssen Datenverstöße trotzdem melden, wenn sie nicht das Gegenteil beweisen können.

Um Ihnen bei der Untersuchung von kompromittierten E-Mail-Konten zu helfen, wird der Zugriff auf E-Mail-Daten nun durch E-Mail-Protokolle und -Clients mit der Postfachüberwachungsaktion *MailItemsAccessed* überwacht. Diese neue überwachte Aktion hilft Ermittlern, E-Mail-Datenverstößen besser zu verstehen und den Umfang der Manipulationen bei bestimmten E-Mail-Elementen zu ermitteln, die möglicherweise kompromittiert wurden. Ziel der Verwendung dieser neuen Überwachungsaktion ist die forensische Wehrhaftigkeit, um sicherzustellen, dass bestimmte E-Mail-Daten nicht kompromittiert wurden. Wenn ein Angreifer Zugriff auf bestimmte E-Mail-Daten erlangt hat, überprüft Exchange Online das Ereignis, selbst wenn kein Hinweis darauf vorhanden ist, dass das E-Mail-Element tatsächlich gelesen wurde.

## <a name="the-mailitemsaccessed-mailbox-auditing-action"></a>Die Postfachüberwachungsaktion "MailItemsAccessed"

Die neue MailItemsAccessed-Aktion ist Bestandteil der neuen [erweiterten Überwachungsfunktionen](advanced-audit.md). Sie ist Bestandteil der [Exchange-Postfachüberwachung](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing#mailbox-auditing-actions) und für Benutzer, denen eine Office 365- oder Microsoft 365 E5-Lizenz zugewiesen wurde, oder für Unternehmen mit einem Abonnement des Microsoft 365 E5 Compliance-Add-Ons standardmäßig aktiviert.

Die Postfachüberwachungsaktion "MailItemsAccessed" deckt alle E-Mail-Protokolle ab: POP, IMAP, MAPI, EWS, Exchange ActiveSync und REST. Außerdem werden beide Arten des Zugriffs auf E-Mails abgedeckt: *Synchronisierung* und *Bindung*.

### <a name="auditing-sync-access"></a>Überwachen des Synchronisierungszugriffs

Synchronisierungsvorgänge werden nur aufgezeichnet, wenn durch eine Desktopversion des Outlook-Clients für Windows oder Mac auf ein Postfach zugegriffen wird. Während des Synchronisierungsvorgangs laden diese Clients in der Regel eine große Menge von E-Mail-Elementen aus der Cloud auf einen lokalen Computer herunter. Das Überwachungsvolumen für Synchronisierungsvorgänge ist riesig. Statt also einen Überwachungseintrag für jedes synchronisierte E-Mail-Element zu generieren, wird lediglich ein Überwachungsereignis für den E-Mail-Ordner generiert, der die synchronisierten Elemente enthält. Damit wird angenommen, dass *alle* E-Mail-Elemente im synchronisierten Ordner kompromittiert wurden. Der Zugriffstyp wird im OperationsProperties-Feld des Überwachungsdatensatzes aufgezeichnet. 

Ein Beispiel für die Darstellung des Synchronisierungszugriffstyps in einem Überwachungsdatensatz finden Sie in Schritt 2 im Abschnitt [Verwenden von MailItemsAccessed-Überwachungsdatensätzen für forensische Untersuchungen](#use-mailitemsaccessed-audit-records-for-forensic-investigations).

### <a name="auditing-bind-access"></a>Überwachen des Bindungszugriffs

Bei einem Bindungsvorgang handelt es sich um einen individuellen Zugriff auf eine E-Mail-Nachricht. Beim Bindungszugriff wird die Internetnachrichten-ID (internet-message-id) einzelner Nachrichten im Überwachungsdatensatz aufgezeichnet. Die MailItemsAccessed-Überwachungsaktion zeichnet Bindungsvorgänge auf, und aggregiert diese dann in einem einzigen Überwachungsdatensatz. Alle Bindungsvorgänge, die innerhalb eines 2-Minuten-Intervalls auftreten, werden in einem einzelnen Überwachungsdatensatz im Ordner-Feld innerhalb der AuditData-Eigenschaft aggregiert. Jede Nachricht, auf die zugegriffen wurde, wird anhand ihres Internetnachrichten-ID-Werts identifiziert. Die Anzahl der in dem Datensatz aggregierten Bindungsvorgänge wird im Feld „OperationCount“ in der AuditData-Eigenschaft angezeigt.

Ein Beispiel für die Darstellung des Bindungszugriffstyps in einem Überwachungsdatensatz finden Sie in Schritt 4 im Abschnitt [Verwenden von MailItemsAccessed-Überwachungsdatensätzen für forensische Untersuchungen](#use-mailitemsaccessed-audit-records-for-forensic-investigations).

### <a name="throttling-of-mailitemsaccessed-audit-records"></a>Drosseln von MailItemsAccessed-Überwachungsdatensätzen

Wenn mehr als 1.000 MailItemsAccessed-Überwachungsdatensätze in weniger als 24 Stunden generiert werden, beendet Exchange Online die Generierung von Überwachungsdatensätze für MailItemsAccessed-Aktivitäten. Wenn ein Postfach gedrosselt wird, werden die MailItemsAccessed-Aktivitäten ab dem Zeitpunkt der Drosselung des Postfachs 24 Stunden lang nicht mehr protokolliert. In diesem Fall besteht das Risiko, dass das Postfach während dieses Zeitraums kompromittiert wurde. Die Aufzeichnung der MailItemsAccessed-Aktivität wird nach Ablauf des 24-Stunden-Zeitraums fortgesetzt.  

Hier einige Punkte, die Sie im Hinblick auf die Drosselung beachten sollten:

- Weniger als 1 % aller Postfächer in Exchange Online werden gedrosselt.

- Wenn ein Postfach gedrosselt wird, werden nur Überwachungsdatensätze für MailItemsAccessed-Aktivitäten nicht überwacht. Andere Postfachüberwachungsaktionen sind davon nicht betroffen.

- Postfächer werden nur für Bindungsvorgänge gedrosselt. Überwachungseinträge für Synchronisierungsvorgänge werden nicht gedrosselt.

- Wenn ein Postfach gedrosselt wird, können Sie davon ausgehen, dass es MailItemsAccessed-Aktivitäten gab, die nicht in den Überwachungsprotokollen aufgezeichnet wurden.

Ein Beispiel für die Darstellung der IsThrottled-Eigenschaft in einem Überwachungsdatensatz finden Sie in Schritt 1 im Abschnitt [Verwenden von MailItemsAccessed-Überwachungsdatensätzen für forensische Untersuchungen](#use-mailitemsaccessed-audit-records-for-forensic-investigations).

## <a name="use-mailitemsaccessed-audit-records-for-forensic-investigations"></a>Verwenden von MailItemsAccessed-Überwachungsdatensätzen für forensische Untersuchungen

Bei der Postfachüberwachung werden Überwachungseinträge für den Zugriff auf E-Mail-Nachrichten generiert, damit Sie sicher sein können, dass E-Mail-Nachrichten nicht kompromittiert wurden. Aus diesem Grund wird in Situationen, in denen nicht sicher ist, ob auf bestimmte Daten zugegriffen wurde, davon ausgegangen, dass ein Zugriff erfolgt ist, indem alle E-Mail-Access-Aktivitäten aufgezeichnet werden.

Die Verwendung von MailItemsAccessed-Überwachungsdatensätzen für forensische Zwecke erfolgt in der Regel nach dem Beheben einer Datenverletzung und dem Entfernen des Angreifers. Um mit der Untersuchung zu beginnen, sollten Sie die Gruppe von Postfächern identifizieren, die kompromittiert wurden, und den Zeitrahmen ermitteln, in dem der Angreifer auf Postfächer in Ihrer Organisation zugreifen konnte. Anschließend können Sie die Cmdlets **Search-UnifiedAuditLog** oder **Search-MailboxAuditLog** in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) verwenden, um Überwachungsdatensätze zu durchsuchen, die der Datenverletzung entsprechen. 

Sie können einen der folgenden Befehle ausführen, um nach MailItemsAccessed-Überwachungsdatensätzen zu suchen:

**Einheitliches Überwachungsprotokoll**

```powershell
Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000
```

**Postfachüberwachungsprotokoll**

```powershell
Search-MailboxAuditLog -Identity <user> -StartDate 01/06/2020 -EndDate 01/20/2020 -Operations MailItemsAccessed -ResultSize 1000 -ShowDetails
```

> [!TIP]
> Ein Hauptunterschied zwischen diesen beiden Cmdlets besteht darin, dass Sie das Cmdlet **Search-UnifiedAuditLog** verwenden können, um nach Überwachungsdatensätzen für Aktivitäten zu suchen, die von einem oder mehreren Benutzern ausgeführt wurden. Der Grund dafür ist, dass *UserIds* ein mehrwertiger Parameter ist. Das Cmdlet **Search-MailboxAuditLog** durchsucht das Postfachüberwachungsprotokoll nach einem einzelnen Benutzer.

Nachfolgend finden Sie die Schritte für die Verwendung von MailItemsAccessed-Überwachungsdatensätzen zur Untersuchung eines Angriffs durch einen kompromittierten Benutzer. In jedem Schritt wird die Befehlssyntax für die Cmdlets **Search-UnifiedAuditLog** oder **Search-MailboxAuditLog** angezeigt.

1. Überprüfen Sie, ob das Postfach gedrosselt wurde. Wenn dies der Fall ist, bedeutet dies, dass einige Postfachüberwachungseinträge nicht protokolliert wurden. Für den Fall, dass Überwachungsdatensätze für "IsThrottled" den Wert "True" aufweisen, sollten Sie davon ausgehen, dass der Zugriff auf das Postfach über einen Zeitraum von 24 Stunden nach Generierung dieses Datensatzes nicht überwacht wurde und dass alle E-Mail-Daten kompromittiert wurden.

   Führen Sie den folgenden Befehl aus, um nach MailItemsAccessed-Datensätzen zu suchen, während das Postfach gedrosselt wurde:

   **Einheitliches Überwachungsprotokoll**
 
   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"IsThrottled","Value":"True"*'} | FL
   ```

   **Postfachüberwachungsprotokoll**

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*IsThrottled:True*"} | FL
   ```

2. Suchen Sie nach Synchronisierungsaktivitäten. Wenn ein Angreifer Nachrichten in einem Postfach mithilfe eines E-Mail-Clients heruntergeladen hat, kann er den Computer vom Internet trennen und lokal auf die Nachrichten zugreifen, ohne mit dem Server interagieren zu müssen. Dies bedeutet, dass die Postfachüberwachung diese Aktivitäten nicht überwachen kann.

   Führen Sie den folgenden Befehl aus, um nach MailItemsAccessed-Datensätzen zu suchen, bei denen mittels Synchronisierungsvorgängen auf E-Mail-Elemente zugegriffen wurde:

   **Einheitliches Überwachungsprotokoll**

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 02/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"MailAccessType","Value":"Sync"*'} | FL
   ```

   **Postfachüberwachungsprotokoll**

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*MailAccessType:Sync*"} | FL
   ```

3. Überprüfen Sie die Synchronisierungsaktivitäten, um zu bestimmen, ob einzelne dieser Aktivitäten im selben Kontext aufgetreten sind, im dem der Angreifer auf das Postfach zugegriffen hat. Der Kontext wird durch die IP-Adresse des Clientcomputers identifiziert und unterschieden, der für den Zugriff auf das Postfach und das E-Mail-Protokoll verwendet wird. Weitere Informationen hierzu finden Sie im Abschnitt [Ermitteln des Zugriffskontexts verschiedener Überwachungsdatensätze](#identifying-the-access-contexts-of-different-audit-records).

   Verwenden Sie die nachstehend aufgeführten Eigenschaften für die Ermittlungen. Diese Eigenschaften befinden sich in der AuditData- oder OperationProperties-Eigenschaft. Wenn eine der Synchronisierungen im selben Kontext wie die Angreiferaktivität stattgefunden hat, gehen Sie davon aus, dass der Angreifer alle E-Mail-Elemente mit seinem Client synchronisiert hat, was wiederum bedeutet, dass das gesamte Postfach wahrscheinlich kompromittiert wurde.

   |Eigenschaft         | Beschreibung |
   |:---------------- | :----------|
   |ClientInfoString | Beschreibt Protokoll und Client (einschließlich Version)|
   |ClientIPAddress  | IP-Adresse des Clientcomputers.|
   |SessionId        | Die Sitzungs-ID trägt dazu bei, die Aktionen des Angreifers von täglichen Benutzeraktivitäten mit dem gleichen Konto (im Fall eines kompromittierten Kontos) zu unterscheiden.|
   |UserId           | UPN des Benutzers, der die Nachricht liest.|
   |||

4. Suchen Sie nach Bindungsaktivitäten. Nachdem Sie die Schritte 2 und 3 durchgeführt haben, können Sie sicher sein, dass alle anderen Zugriffe auf E-Mail-Nachrichten durch den Angreifer in den MailItemsAccessed-Überwachungsdatensätzen erfasst werden, die eine MailAccessType-Eigenschaft mit dem Wert "Bind" aufweisen.

   Führen Sie den folgenden Befehl aus, um nach MailItemsAccessed-Datensätzen zu suchen, bei denen mittels Bindungsvorgängen auf E-Mail-Elemente zugegriffen wurde.

   **Einheitliches Überwachungsprotokoll**

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"MailAccessType","Value":"Bind"*'} | FL
   ```
 
   **Postfachüberwachungsprotokoll**
   
   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*MailAccessType:Bind*"} | FL
   ```

   E-Mail-Nachrichten, auf die zugegriffen wurde, werden anhand ihrer Internetnachrichten-ID identifiziert. Sie können auch überprüfen, ob Überwachungsdatensätze den gleichen Kontext aufweisen wie bei anderen Angriffsaktivitäten. Weitere Informationen hierzu finden Sie im Abschnitt [Ermitteln des Zugriffskontexts verschiedener Überwachungsdatensätze](#identifying-the-access-contexts-of-different-audit-records).
 
   Sie können die Überwachungsdaten für Bindungsvorgänge auf zwei verschiedene Arten verwenden:

     - Zugreifen oder Sammeln aller E-Mail-Nachrichten, auf die der Angreifer zugegriffen hat, anhand der Internetnachrichten-ID (internet-message-id), um die Nachrichten zu finden und zu überprüfen, ob eine dieser Nachrichten vertrauliche Informationen enthält.

     - Verwenden Sie die Internetnachrichten-ID zum Durchsuchen von Überwachungsdatensätzen, die sich auf einen Satz potenziell vertraulicher E-Mails beziehen. Dies ist nützlich, wenn Sie nur bei einer kleinen Anzahl von Nachrichten besorgt sind.

## <a name="filtering-of-duplicate-audit-records"></a>Filtern von doppelten Überwachungsdatensätzen

Duplikate von Überwachungsdatensätzen für innerhalb einer Stunde auftretende gleiche Bindungsvorgänge werden herausgefiltert, um Stördatenverkehr bei der Überwachung zu entfernen. Synchronisierungsvorgänge werden ebenfalls in 1-Stunden-Intervallen herausgefiltert. Die Ausnahme von diesem Deduplizierungsprozess tritt auf, wenn für dieselbe Internetnachrichten-ID eine der in der folgenden Tabelle beschriebenen Eigenschaften abweicht. Wenn sich eine dieser Eigenschaften in einem doppelten Vorgang unterscheidet, wird ein neuer Überwachungsdatensatz generiert. Dieser Vorgang wird im nächsten Abschnitt ausführlicher beschrieben.

| Eigenschaft| Beschreibung|
|:--------|:---------|
|ClientIPAddress | IP-Adresse des Clientcomputers.|
|ClientInfoString| Clientprotokoll, für den Zugriff auf das Postfach verwendeter Client.| 
|ParentFolder    | Vollständiger Ordnerpfad des E-Mail-Elements, auf das zugegriffen wurde. |
|Logon_type      | Anmeldetyp des Benutzers, der die Aktion ausgeführt hat. Die Anmeldetypen (und deren zugehörige Enum-Werte) sind Besitzer (0), Administrator (1) oder Stellvertreter (2).|
|MailAccessType  | Gibt an, ob es sich bei dem Zugriff um einen Bindungs oder Synchronisierungsvorgang handelt.|
|MailboxUPN      | UPN des Postfachs, in dem sich die gelesene Nachricht befindet.|
|User            | UPN des Benutzers, der die Nachricht liest.|
|SessionId       | Die Sitzungs-ID hilft bei der Unterscheidung von Angreiferaktionen und alltäglichen Benutzeraktivitäten im selben Postfach (im Falle einer Kontokompromittierung). Weitere Informationen über Sitzungen finden Sie unter [Contextualizing attacker activity within sessions in Exchange Online](https://techcommunity.microsoft.com/t5/exchange-team-blog/contextualizing-attacker-activity-within-sessions-in-exchange/ba-p/608801) (Kontextualisierung von Angreiferaktivitäten innerhalb von Sitzungen in Exchange Online).|
||||

## <a name="identifying-the-access-contexts-of-different-audit-records"></a>Ermitteln des Zugriffskontexts verschiedener Überwachungsdatensätze

Es kommt häufig vor, dass ein Angreifer und der Besitzer eines Postfachs gleichzeitig auf das Postfach zugreifen. Um zwischen dem Zugriff durch den Angreifer und dem Zugriff durch den Postfachbesitzer zu unterscheiden, gibt es Überwachungsprotokolleigenschaften, die den Kontext des Zugriffs definieren. Wie bereits erläutert, werden bei unterschiedlichen Werten für diese Eigenschaften separate Überwachungsdatensätze generiert, selbst wenn die Aktivität innerhalb eines Aggregationsintervalls stattfindet. Im folgenden Beispiel gibt es drei verschiedene Überwachungsdatensätze. Sie unterscheiden sich in den Eigenschaften "Session Id" und "ClientIPAddress". Die Nachrichten, auf die zugegriffen wurde, werden ebenfalls identifiziert.

|Überwachungsdatensatz 1  |Überwachungsdatensatz 2  |Überwachungsdatensatz 3|
|---------|---------|---------|
|ClientIPAddress **1**<br/>SessionId **2**|ClientIPAddress **2**<br/>SessionId **2**|ClientIPAddress **1**<br/>SessionId **3**|
|InternetMessageId **A**<br/>InternetMessageId **D**<br/>InternetMessageId **E**<br/>InternetMessageId **F**<br/>|InternetMessageId **A**<br/>InternetMessageId **C**|InternetMessageId **B** |
||||

Wenn eine der in der Tabelle im [vorherigen Abschnitt](#filtering-of-duplicate-audit-records) aufgeführten Eigenschaften unterschiedlich ist, wird ein separater Überwachungsdatensatz generiert, um den neuen Kontext zu verfolgen. Die Zugriffe werden je nach dem Kontext, in dem die Aktivität stattgefunden hat, in separate Überwachungsdatensätze sortiert.

In den im folgenden Screenshot gezeigten Überwachungsdatensätzen wird die Zugriffsaktivität in verschiedenen Überwachungsdatensätzen zusammengestellt, je nachdem, in welchem Kontext der Zugriff stattgefunden hat, obwohl gleichzeitig von EWSEditor und OWA auf E-Mails zugegriffen wird. In diesem Fall wird der Kontext durch verschiedene Werte für die ClientInfoString-Eigenschaft definiert.

![Unterschiedliche Überwachungsdatensätze je nach Kontext](../media/MailItemsAccessed4.png)

Hier ist die Syntax für den im vorherigen Screenshot gezeigten Befehl:

```powershell
Search-MailboxAuditLog -Identity admin -ShowDetails -Operations MailItemsAccessed -ResultSize 2000 | Select LastAccessed,Operation,AuditOperationsCountInAggregatedRecord,ClientInfoString
``` 
