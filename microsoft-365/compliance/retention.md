---
title: Informationen zu Aufbewahrungsrichtlinien und -bezeichnungen zum automatischen Beibehalten oder Löschen von Inhalten
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
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen, um zu behalten, was Sie benötigen, und zu löschen, was Sie nicht benötigen.
ms.openlocfilehash: 50bbe9d80b7b0a1b9fa346fd6e5abc8971dadcfb
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804758"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a>Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

In den meisten Organisationen nimmt die Menge und Komplexität der Daten täglich zu – E-Mails, Dokumente, Chatnachrichten usw. Eine effektive Verwaltung bzw. Governance dieser Informationen ist wichtig, da Sie:
  
- **branchenspezifische Vorschriften und interne Richtlinien einhalten müssen** , nach denen Inhalte für eine bestimmte Mindestdauer aufzubewahren sind – z. B. müssen Sie gemäß dem Sarbanes-Oxley Act möglicherweise bestimmte Arten von Inhalten sieben Jahre lang aufbewahren. 

- **das Risiko bei Rechtsstreitigkeiten oder einer Sicherheitsverletzung reduzieren müssen** , indem Sie alte Inhalte, die Sie nicht mehr aufbewahren müssen, endgültig löschen. 
    
- **Ihrer Organisation dabei helfen müssen, effektiven Wissensaustausch zu betreiben und agiler zu werden** , indem Sie sicherstellen, dass die Benutzer nur mit Inhalten arbeiten, die aktuell und für sie relevant sind. 
    
Die Aufbewahrungseinstellungen, die Sie konfigurieren, können Ihnen helfen, all diese Ziele zu erreichen. Zum Verwalten von Inhalten sind häufig zwei Aktionen erforderlich:
  
- **Aufbewahrung** von Inhalten, sodass sie nicht vor dem Ende des Aufbewahrungszeitraums dauerhaft gelöscht werden 
    
- **Endgültiges Löschen** von Inhalten am Ende des Aufbewahrungszeitraums. 
    

Mit diesen beiden Aufbewahrungsaktionen können Sie Aufbewahrungseinstellungen für die folgenden Ergebnisse konfigurieren:

- Nur Aufbewahren: Aufbewahren von Inhalten für immer oder für einen bestimmten Zeitraum.
- Nur Löschen: Löscht Inhalte nach einem bestimmten Zeitraum.
- Aufbewahren und Löschen: Inhalte für einen bestimmten Zeitraum aufbewahren und dann löschen.

Diese Aufbewahrungseinstellungen arbeiten mit bereits vorhandenen Inhalten und ersparen Ihnen den zusätzlichen Aufwand für die Erstellung und Konfiguration von zusätzlichem Speicherplatz, wenn Sie Inhalte aus Compliancegründen aufbewahren müssen. Außerdem müssen Sie keine benutzerdefinierten Prozesse implementieren, um diese Daten zu kopieren und zu synchronisieren.

## <a name="how-retention-settings-work-with-content-in-place"></a>Funktionsweise von Aufbewahrungseinstellungen bei vorhandenem Inhalt

Wenn einem Inhalt Aufbewahrungseinstellungen zugewiesen sind, bleibt dieser Inhalt an seinem ursprünglichen Speicherort. Die Benutzer können weiterhin mit ihren Dokumenten oder E-Mails arbeiten, als ob sich nichts geändert hätte. Wenn aber Inhalte bearbeitet oder gelöscht werden, die in die Aufbewahrungsrichtlinie einbezogen sind, wird eine Kopie des Inhalts automatisch so aufbewahrt, wie er zum Zeitpunkt der Anwendung der Aufbewahrungseinstellungen vorhanden war.
  
- Für SharePoint-und OneDrive-Websites: Die Kopie wird im **Permanenten Dokumentarchiv** aufbewahrt.

- Für Exchange-Postfächer: Die Kopie wird im Ordner **Wiederherstellbare Elemente** aufbewahrt. 

- Für Teams- und Chatnachrichten: Die Kopie wird in einem verborgenen Ordner namens **SubstrateHolds** als Unterordner im Exchange-Ordner **Wiederherstellbare Objekte** aufbewahrt.

> [!NOTE]
> Das permanente Dokumentarchiv verbraucht Speicherplatz, der nicht vom Speicherkontingent für die Website ausgenommen ist. Möglicherweise müssen Sie den Speicherplatz erhöhen, wenn Sie Aufbewahrungseinstellungen für SharePoint und Microsoft 365-Gruppen verwenden.
> 
Diese sicheren Speicherorte und die aufbewahrten Inhalte sind für die meisten Benutzer nicht sichtbar. In den meisten Fällen müssen die Benutzer gar nicht wissen, dass ihre Inhalte Aufbewahrungseinstellungen unterliegen.

Ausführlichere Informationen zur Funktionsweise von Aufbewahrungseinstellungen mit unterschiedlichen Workloads finden Sie in den folgenden Artikeln:

- [Informationen zur Aufbewahrung für SharePoint und OneDrive](retention-policies-sharepoint.md)
- [Informationen zur Aufbewahrung für Microsoft Teams](retention-policies-teams.md)
- [Informationen zur Aufbewahrung für Yammer](retention-policies-yammer.md)
- [Informationen zur Aufbewahrung für Exchange](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a>Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

Sie können sowohl Aufbewahrungsrichtlinien als auch Aufbewahrungsbezeichnungen verwenden, um Ihre Aufbewahrungseinstellungen den Inhalten zuzuweisen. 

Verwenden Sie eine Aufbewahrungsrichtlinie, um dieselben Aufbewahrungseinstellungen für Inhalte auf einer Website- oder Postfachebene zuzuweisen, und verwenden Sie eine Aufbewahrungsbezeichnung, um Aufbewahrungseinstellungen auf Elementebene (Ordner, Dokument, E-Mail) zuzuweisen.

Wenn beispielsweise alle Dokumente auf einer SharePoint-Website fünf Jahre lang aufbewahrt werden sollen, ist es effizienter, dies mit einer Aufbewahrungsrichtlinie zu tun, als alle Dokumente auf dieser Website mit derselben Aufbewahrungsbezeichnung anzuwenden. Wenn jedoch einige Dokumente auf dieser Website fünf Jahre lang aufbewahrt werden sollen und andere für zehn Jahre, kann dies in einer Aufbewahrungsrichtlinie nicht erfolgen. Wenn Sie Aufbewahrungseinstellungen auf Elementebene angeben müssen, verwenden Sie Aufbewahrungsbezeichnungen. 

Im Gegensatz zu Aufbewahrungsrichtlinien bleiben die Aufbewahrungseinstellungen von Aufbewahrungsbezeichnungen mit dem Inhalt erhalten, wenn dieser kopiert oder an einen anderen Microsoft 365-Speicherort verschoben wird. Darüber hinaus haben Aufbewahrungsbezeichnungen die folgenden Funktionen, die von den Aufbewahrungsrichtlinien nicht unterstützt werden: 
 
- Optionen zum Starten des Aufbewahrungszeitraums ab dem Zeitpunkt, ab dem die Inhalte bezeichnet wurden, statt anhand des Inhaltsalters oder dem Datum der letzten Änderung.

- Verwenden Sie [trainierbare Klassifizierer](classifier-learn-about.md), um die zu bezeichnenden Inhalte zu identifizieren.

- Wenden Sie eine Standardbezeichnung für SharePoint-Dokumente an.

- Unterstützen Sie die [Überprüfung der Disposition](disposition-reviews.md) , um den Inhalt zu überprüfen, bevor er endgültig gelöscht wird.

- Kennzeichnen Sie den Inhalt als [Datensatz](records-management.md#records) als Teil der Bezeichnungseinstellungen und haben Sie immer einen  [Nachweis über die Disposition](disposition.md#disposition-of-records) , wenn der Inhalt am Ende seines Aufbewahrungszeitraums gelöscht wird.

### <a name="retention-policies"></a>Aufbewahrungsrichtlinien

Aufbewahrungsrichtlinien können auf die folgenden Speicherorte angewendet werden:
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

Sie können eine einzelne Richtlinie sehr effizient auf mehrere Speicherorte oder auf bestimmte Speicherorte oder Benutzer anwenden.
    
Sie können eine Richtlinie auch auf alle Inhalte anwenden oder auf Inhalte, die bestimmte Bedingungen erfüllen, wie z. B. Inhalte, die Schlüsselwörter oder [vertrauliche Informationstypen](sensitive-information-type-entity-definitions.md) enthalten.

#### <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a>Verwenden der Erhaltungssperre zur Einhaltung gesetzlicher Vorschriften

Einige Organisationen müssen möglicherweise Regeln einhalten, die von Behörden definiert werden, wie zum Beispiel die Richtlinie 17a-4 der Securities And Exchange Commission (SEC), die vorgibt, dass eine Aufbewahrungsrichtlinie nach dem Aktivieren nicht deaktiviert oder weniger restriktiv eingestellt werden kann. 

Die Erhaltungssperre stellt sicher, dass Ihre Organisation solchen gesetzlichen Vorschriften gerecht werden kann, da hierdurch eine Aufbewahrungsrichtlinie gesperrt wird, sodass niemand – auch nicht der Administrator – die Richtlinie deaktivieren, löschen oder weniger restriktiv einstellen kann.
  
Das Sperren einer Aufbewahrungsrichtlinie bewirkt Folgendes:

- Keiner kann sie ausschalten
- Speicherorte können hinzugefügt, aber nicht entfernt werden
- Inhalte, die der Richtlinie unterliegen, können während des Aufbewahrungszeitraums weder geändert noch gelöscht werden.
- Sie können den Aufbewahrungszeitraum verlängern, ihn jedoch nicht verringern.

Zusammenfassend kann man sagen, dass eine gesperrte Richtlinie erweitert oder verlängert, jedoch nicht reduziert oder deaktiviert werden kann.
  
> [!IMPORTANT]
> Bevor Sie eine Aufbewahrungsrichtlinie sperren, ist es wichtig, dass Sie die Auswirkungen kennen und überlegen, ob dies zur Erfüllung der regulatorischen Anforderungen durch Ihre Organisation erforderlich ist. Administratoren können eine Aufbewahrungsrichtlinie nicht mehr deaktivieren oder löschen, nachdem die Erhaltungssperre angewendet wurde.

Sie wenden die Erhaltungssperre an, nachdem die Aufbewahrungsrichtlinie mithilfe von PowerShell erstellt wurde. Anweisungen dazu finden Sie unter [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](create-retention-policies.md).

#### <a name="releasing-a-retention-policy"></a>Aufheben einer Aufbewahrungsrichtlinie

Wenn eine Aufbewahrungsrichtlinie keiner Erhaltungssperre unterliegt, können Sie sie jederzeit deaktivieren oder löschen. 

In diesem Fall werden bis dahin im permanentes Dokumentarchiv aufbewahrte SharePoint- oder OneDrive-Inhalte nicht sofort und dauerhaft gelöscht. Um versehentlichem Datenverlust vorzubeugen, gibt es nun eine Nachfrist von 30 Tagen, während der der Inhaltsablauf für diese Richtlinie im permanenten Dokumentarchiv nicht eintritt, sodass Sie Inhalte ggf. wiederherstellen können. Darüber hinaus können Sie diese Inhalte während der Nachfrist nicht manuell löschen.

Sie können die Aufbewahrungsrichtlinie während der Nachfrist erneut aktivieren. In diesem Fall werden keine in Zusammenhang mit dieser Richtlinie stehenden Inhalte gelöscht.

Diese 30-tägige Nachfrist in SharePoint und OneDrive entspricht dem 30-tägigen Anhalten der Aufbewahrungszeit in Exchange. Weitere Informationen finden Sie unter [Verwalten von Postfächern mit angehaltener Aufbewahrungszeit](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

### <a name="retention-labels"></a>Aufbewahrungsbezeichnungen

Verwenden Sie Aufbewahrungsbezeichnungen für unterschiedliche Inhaltstypen, für die unterschiedliche Aufbewahrungseinstellungen erforderlich sind. Beispiel:
  
- Steuerformulare, die für einen bestimmten Zeitraum aufbewahrt werden müssen. 
    
- Pressematerialien, die nach dem Erreichen eines bestimmten Alters dauerhaft gelöscht werden müssen. 
    
- Im Wettbewerb stehende Forschungen, die für einen bestimmten Zeitraum aufbewahrt und dann endgültig gelöscht werden müssen. 
    
- Arbeitsvisa, die als Datensatz gekennzeichnet werden müssen, damit sie nicht bearbeitet oder gelöscht werden. 
    
In all diesen Fällen können Sie mit Hilfe von Aufbewahrungsbzeichnungen Aufbewahrungseinstellungen für die Governance-Kontrolle auf der Elementebene (Dokument oder E-Mail) anwenden.
  
Mit Aufbewahrungsbezeichnungen können Sie Folgendes:
  
- **Personen in Ihrer Organisation die Möglichkeit zum manuellen Anwenden einer Aufbewahrungsbezeichnung bieten** , und zwar auf Inhalte in Outlook und Outlook im Web, OneDrive, SharePoint und Microsoft 365-Gruppen. Benutzer wissen häufig am besten, mit welcher Art von Inhalten sie arbeiten, sodass sie diese klassifizieren und die entsprechenden Aufbewahrungseinstellungen anwenden lassen können. 
    
- **Sie können Aufbewahrungsbezeichnungen automatisch** auf Inhalt anwenden, wenn er bestimmten Bedingungen entspricht: 
    - Der Inhalt enthält bestimmte vertrauliche Informationen.
    - Der Inhalt enthält bestimmte Stichwörter, die einer von Ihnen erstellten Abfrage entsprechen.
    - Musterübereinstimmungen für eine trainierbare Klassifizierung.

- **Beginnen Sie den Aufbewahrungszeitraum ab dem Zeitpunkt der Bezeichnung des Inhalts** für Dokumente auf SharePoint-Websites und in OneDrive-Konten sowie für E-Mail-Elemente mit Ausnahme von Kalenderelementen. Wenn Sie eine Aufbewahrungsbezeichnung mit dieser Konfiguration auf ein Kalenderelement aufbringen, beginnt der Aufbewahrungszeitraum ab dem Zeitpunkt, an dem es gesendet wird.

- **Starten des Aufbewahrungszeitraums, wenn ein Ereignis auftritt** , z. B. Mitarbeiter, die das Unternehmen verlassen oder Verträge ablaufen.

- **Wenden Sie eine Standardaufbewahrungsbezeichnung auf eine Dokumentbibliothek, einen Ordner oder eine Dokumentenmappe** in SharePoint an, sodass alle an diesem Speicherort gespeicherten Dokumente mit der Standardaufbewahrungsbezeichnung versehen werden.

Aufbewahrungsbezeichnungen unterstützen darüber hinaus die [Datensatzverwaltung](records-management.md) für E-Mails und Dokumente in Microsoft 365-Apps und -Diensten. Sie können eine Aufbewahrungsbezeichnung verwenden, um Elemente als Datensätze zu kennzeichnen. Wenn dies geschieht und der Inhalt in Microsoft 365 bleibt, legt die Bezeichnung weitere Einschränkungen für die Inhalte fest, die aus rechtlichen Gründen möglicherweise erforderlich sind. Weitere Informationen finden Sie unter [Vergleichen Sie die Einschränkungen für die zulässigen oder blockierten Aktionen](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).

Aufbewahrungsbezeichnungen bleiben im Gegensatz zu [Vertraulichkeitsbezeichnungen](sensitivity-labels.md) nicht erhalten, wenn der Inhalt außerhalb von Microsoft 365 verschoben wird.

Für die Anzahl der Aufbewahrungsbezeichnungen, die für einen Mandanten unterstützt werden, gibt es keine Beschränkung. Es werden jedoch maximal 10.000 Richtlinien für einen Mandanten unterstützt. Dazu gehören die Richtlinien, mit denen die Bezeichnungen angewendet werden (Aufbewahrungsbezeichnungsrichtlinien und automatische Aufbewahrungsrichtlinien), sowie Aufbewahrungsrichtlinien.

#### <a name="classifying-content-without-applying-any-actions"></a>Klassifizieren von Inhalten ohne Anwendung von Aktionen

Obwohl der Hauptzweck von Aufbewahrungsbezeichnungen darin besteht, Inhalte beizubehalten oder zu löschen, können Sie auch Aufbewahrungsbezeichnungen verwenden, ohne die Aufbewahrung oder andere Aktionen einzuschalten. In diesem Fall können Sie eine Aufbewahrungsbezeichnung einfach als Beschriftung verwenden, ohne irgendwelche Aktionen zu erzwingen.
  
Sie können z. B. eine Aufbewahrungsbezeichnung mit dem Namen "Später überprüfen" ohne Aktionen erstellen und anwenden und dann diese Bezeichnung verwenden, um diesen Inhalt später wiederzufinden.
  
![Bezeichnungseinstellungen auf „Nur klassifizieren“ festlegen](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>Verwenden einer Aufbewahrungsbezeichnung als Bedingung in einer DLP-Richtlinie

Sie können eine Aufbewahrungsbezeichnung als Bedingung in einer DLP-Richtlinie für Dokumente in SharePoint angeben. Konfigurieren Sie beispielsweise eine DLP-Richtlinie, um zu verhindern, dass Dokumente außerhalb der Organisation freigegeben werden, wenn auf sie eine bestimmte Aufbewahrungsbezeichnung angewendet wurde.

Weitere Informationen finden Sie unter [Verwenden einer Aufbewahrungsbezeichnung als Bedingung in einer DLP-Richtlinie](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).

#### <a name="retention-labels-and-policies-that-apply-them"></a>Aufbewahrungsbezeichnungen und Richtlinien, die sie anwenden

Aufbewahrungsbezeichnungen sind unabhängige, wieder verwendbare Bausteine. Der Hauptzweck der Aufbewahrungsbezeichnungsrichtlinie besteht darin, eine Reihe von Aufbewahrungsbezeichnungen zu gruppieren und die Orte anzugeben, an denen die Bezeichnungen angezeigt werden sollen. Dann können Administratoren und Benutzer diese Bezeichnungen auf Inhalte an diesen Speicherorten anwenden.
  
![Diagramm der Bezeichnungen, Bezeichnungsrichtlinien und Speicherorte](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
Wenn Sie Aufbewahrungsbezeichnungen veröffentlichen, sind diese in einer Aufbewahrungsbezeichnungsrichtlinie enthalten, sodass Administratoren und Benutzer sie auswählen können:

- Eine einzelne Aufbewahrungsbezeichnung kann in mehrere Aufbewahrungsbezeichnungsrichtlinien einbezogen werden.

- Aufbewahrungsbezeichnungsrichtlinien geben die Speicherorte zum Veröffentlichen der Aufbewahrungsbezeichnungen an.

- Ein einzelner Ort kann auch in viele Aufbewahrungsbezeichnungsrichtlinien einbezogen werden.

Zusätzlich zu den Aufbewahrungsbezeichnungsrichtlinien können Sie auch eine oder mehrere Richtlinien für die automatische Anwendung erstellen, jede mit einer einzelnen Aufbewahrungsbezeichnung. Bei dieser Richtlinie wird automatisch eine Aufbewahrungsbezeichnung angebracht, wenn die Bedingungen, die Sie in der Richtlinie angeben, erfüllt sind. 

#### <a name="retention-label-policies-and-locations"></a>Aufbewahrungsbezeichnungsrichtlinien und Speicherorte

Verschiedene Arten von Aufbewahrungsbezeichnungen können an verschiedenen Speicherorten veröffentlicht werden, je nach Funktion der Aufbewahrungsbezeichnung.
  
| Wenn für die Aufbewahrungsbezeichnung Folgendes gilt: | Anwendungsmöglichkeit der Bezeichnungsrichtlinie |
|:-----|:-----|
|Veröffentlicht für Administratoren und Endbenutzer  <br/> |Exchange, SharePoint, OneDrive, Microsoft 365-Gruppen  <br/> |
|Basierend auf Typen vertraulicher Informationen oder trainierbaren Klassifizierer automatisch angewendet  <br/> |Exchange (nur alle Postfächer), SharePoint, OneDrive  <br/> |
|basieren auf einer Abfrage automatisch angewendet  <br/> |Exchange, SharePoint, OneDrive, Microsoft 365-Gruppen  <br/> |
   
In Exchange werden automatisch angewendete Bezeichnungen nur auf neu gesendete Nachrichten (in Übertragung begriffene Daten) angewendet, und nicht auf alle Elemente, die sich derzeit im Postfach befinden (ruhende Daten). Außerdem können automatisch angewendete Aufbewahrungsbezeichnungen für vertrauliche Informationstypen und trainierbare Klassifizierer auf alle Postfächer angewendet werden; Sie können keine bestimmten Postfächer auswählen.
  
Öffentliche Exchange-Ordner, Skype-, Teams- und Yammer-Nachrichten unterstützen keine Aufbewahrungsbezeichnungen. Zum Aufbewahren und Löschen von Containern an diesen Speicherorten verwenden Sie stattdessen Aufbewahrungsrichtlinien.

#### <a name="only-one-retention-label-at-a-time"></a>Jeweils nur eine Aufbewahrungsbezeichnung

Eine E-Mail-Nachricht oder ein Dokument kann jeweils nur über eine Aufbewahrungsbezeichnung verfügen:
  
- Aufbewahrungsbezeichnungen, die von den Administratoren oder den Endbenutzern manuell zugewiesen wurden, können entfernt oder geändert werden.
    
- Wenn dem Inhalt eine automatisch anwendbare Bezeichnung zugewiesen ist, kann diese Bezeichnung durch eine veröffentlichte Aufbewahrungsbezeichnung ersetzt werden.
    
- Wenn dem Inhalt eine Bezeichnung für die veröffentlichte Aufbewahrung zugewiesen wurde, kann diese nicht durch eine automatische anwendbare Bezeichnung ersetzt werden.
    
- Wenn es mehrere Regeln gibt, durch die eine Bezeichnung automatisch zugewiesen wird, und ein Inhalt die Bedingungen verschiedener Regeln erfüllt, wird die Aufbewahrungsbezeichnung für die älteste Regel (nach Erstellungsdatum) angewendet.
    
Um zu verstehen, wie und warum eine Aufbewahrungsbezeichnung und nicht eine andere angewendet wird, ist es hilfreich, den Unterschied zwischen der expliziten und der impliziten Zuweisung einer Bezeichnung nachzuvollziehen:

- Aufbewahrungsbezeichnungen, die von einer Bezeichnungsrichtlinie angewendet werden, werden explizit zugewiesen
- Aufbewahrungsbezeichnungen, die automatisch von einer automatisch anwendbaren Richtlinie angewendet werden, werden implizit zugewiesen

Eine explizit zugewiesene Aufbewahrungsbezeichnung hat Vorrang vor einer implizit zugewiesenen. Weitere Informationen finden Sie im Abschnitt [Die Grundsätze der Aufbewahrung, oder was hat Vorrang?](retention.md#the-principles-of-retention-or-what-takes-precedence) auf dieser Seite.

Für SharePoint können Aufbewahrungsbezeichnungen auch implizit zugewiesen werden, wenn Sie für alle Inhalte in einer SharePoint-Bibliothek, einem Ordner oder einem Dokumentensatz eine Standardbezeichnung konfigurieren. In diesem Szenario hat eine automatisch zugewiesene Bezeichnung Vorrang vor einer Standardbezeichnung, aber um alle Ergebnisse bei Verwendung einer Standardbezeichnung vollständig zu verstehen, lesen Sie die Informationen im Abschnitt [Anwenden einer Standardaufbewahrungsbezeichnung auf alle Inhalte in einer SharePoint-Bibliothek, einem Ordner oder einer Dokumentenmappe](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set). 

#### <a name="monitoring-retention-labels"></a>Überwachen von Aufbewahrungsbezeichnungen

Verwenden Sie im Microsoft 365 Compliance Center **Datenklassifizierung** > **Übersicht** , um zu überwachen, wie Ihre Aufbewahrungsbezeichnungen in Ihrem Mandanten verwendet werden und um festzustellen, wo sich Ihre bezeichneten Elemente befinden. Weitere Informationen, einschließlich wichtiger Voraussetzungen, finden Sie unter [Kennen Sie Ihre Daten – Überblick über die Datenklassifizierung](data-classification-overview.md).

Sie können dann mit dem [Inhalts-Explorer](data-classification-content-explorer.md) und dem [Aktivitäten-Explorer](data-classification-activity-explorer.md) in die Details gehen.

> [!TIP]
>Erwägen Sie die Verwendung einiger anderer Einblicke in die Datenklassifizierung, wie trainierbare Klassifikatoren und sensible Informationstypen, um Inhalte zu identifizieren, die Sie möglicherweise beibehalten oder löschen oder als Datensätze verwalten müssen.

Das Office 365 Security & Compliance Center verfügt über die entsprechenden Übersichtsinformationen für Aufbewahrungsbezeichnungen aus dem **Informationsgovernance** > **Dashboard** sowie ausführlichere Informationen aus dem **Informationsgovernance** > **Bezeichnungsaktivitäten-Explorer** . Weitere Informationen zum Überwachen von Aufbewahrungsbezeichnungen von diesem älteren Admin Center finden Sie in der folgenden Dokumentation:
- [Anzeigen der Datengovernanceberichte](view-the-data-governance-reports.md)
- [Anzeigen der Bezeichnungsnutzung mit der Analyse der Bezeichnungen](label-analytics.md)
- [Anzeigen der Bezeichnungsaktivität für Dokumente](view-label-activity-for-documents.md)

#### <a name="using-content-search-to-find-all-content-with-a-specific-retention-label"></a>Verwenden der Inhaltssuche zum Suchen des gesamten Inhalts mit einer bestimmten Aufbewahrungsbezeichnung

Nachdem die Aufbewahrungsbezeichnungen auf die Inhalte entweder von Benutzern oder automatisch angewendet wurden, können Sie mit der Inhaltssuche alle Elemente finden, auf die eine bestimmte Aufbewahrungsbezeichnung angewendet wurde.

Wenn Sie eine Inhaltssuche erstellen, wählen Sie die Bedingung **Aufbewahrungsbezeichnung** aus, und geben Sie den vollständigen Namen der Aufbewahrungsbezeichnung oder einen Teil des Bezeichnungsnamens ein und verwenden Sie einen Platzhalter. Weitere Informationen finden Sie unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).
  
![Zustand der Aufbewahrungsbezeichnung](../media/retention-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a>Vergleich der Funktionen für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

Mithilfe der folgenden Tabelle können Sie anhand der Funktionen feststellen, ob Sie eine Aufbewahrungsrichtlinie oder eine Aufbewahrungsbezeichnung verwenden sollten.

|Funktion|Aufbewahrungsrichtlinie |Aufbewahrungsbezeichnung|
|:-----|:-----|:-----|:-----|
|Aufbewahrungsbezeichnungen, die aufbewahrt und dann gelöscht, nur aufbewahrt oder nur gelöscht werden können |Ja |Ja |
|Unterstützte Workloads: <br />– Exchange <br />– SharePoint <br />– OneDrive <br />– Microsoft 365-Gruppen <br />– Skype for Business <br />– Teams<br />– Yammer|<br /> Ja <br /> Ja <br /> Ja <br /> Ja <br /> Ja <br /> Ja | <br /> Ja, ausgenommen öffentliche Ordner <br /> Ja <br /> Ja <br /> Ja <br /> Nein <br /> Nein <br /> Nein |
|Aufbewahrung automatisch angewendet | Ja | Ja |
|Aufbewahrung basierend auf Bedingungen angewendet <br /> – Typen vertraulicher Informationen, KQL-Abfragen, trainierbare Klassifizierungsmerkmale| Nein | Ja |
|Aufbewahrung manuell angewendet | Nein | Ja |
|Benutzeroberfläche-Anwesenheitsinformationen für Endbenutzer | Nein | Ja |
|Wird beibehalten, wenn der Inhalt verschoben wird | Nein | Ja, innerhalb Ihres Microsoft 365-Mandanten |
|Deklarieren eines Elements als Datensatz| Nein | Ja |
|Start des Aufbewahrungszeitraums: <br /> – Wenn Elemente erstellt oder zuletzt geändert wurden<br /> – Beim Anwenden einer Bezeichnung oder von einem Ereignis ausgehend | <br />Ja <br />Nein | <br />Ja <br /> Ja |
|Dispositionsüberprüfung | Nein| Ja |
|Dispositionsnachweise von bis zu 7 Jahren | Nein |Ja, wenn Element als ein Datensatz deklariert ist|
|Administratoraktivitäten überwachen| Ja | Ja|
|Identifizierung von Elementen, die der Aufbewahrung unterliegen: <br /> – Inhaltssuche <br /> – Datenklassifizierungsseite, Inhalts-Explorer, Aktivitäts-Explorer | <br /> Nein <br /> Nein | <br /> Ja <br /> Ja|

Beachten Sie, dass Sie sowohl Aufbewahrungsrichtlinien als auch Aufbewahrungsbezeichnungen als ergänzende Aufbewahrungsmethoden verwenden können. Beispiel:

1. Sie erstellen und konfigurieren eine Aufbewahrungsrichtlinie, die Inhalte fünf Jahre nach ihrer letzten Änderung automatisch löscht, und wenden die Richtlinie auf alle OneDrive-Konten an.

2. Sie erstellen und konfigurieren eine Aufbewahrungsbezeichnung, die Inhalte für immer behält, und fügen diese einer Bezeichnungsrichtlinie hinzu, die Sie für alle OneDrive-Konten veröffentlichen. Sie erklären den Benutzern, wie Sie diese Bezeichnung manuell auf bestimmte Dokumente anwenden, die von der automatischen Löschung ausgeschlossen werden sollen, wenn sie nach fünf Jahren nicht geändert werden.

Weitere Informationen darüber, wie Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen zusammenwirken und wie man ihr kombiniertes Ergebnis bestimmt, finden Sie im nächsten Abschnitt, in dem die Prinzipien der Aufbewahrung erläutert werden und was Vorrang hat.

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>Die Grundsätze der Aufbewahrung, oder was hat Vorrang?

Es ist möglich oder sogar wahrscheinlich, dass auf Inhalte mehrere Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen angewendet werden, die jeweils eine andere Aktion (Aufbewahren, Löschen oder beides, also zuerst Aufbewahren und dann Löschen) sowie einen anderen Aufbewahrungszeitraum vorgeben. Doch was hat Vorrang? 

Auf einer hohen Ebene können Sie sicher sein, dass die Aufbewahrung immer Vorrang vor der Löschung hat, und dann der längste Aufbewahrungszeitraum hat Vorrang. 

Es gibt jedoch noch ein paar weitere Faktoren, die man in die Mischung einfließen lassen sollte. Verwenden Sie also den folgenden Ablauf, um das Ergebnis zu verstehen, bei dem jede Ebene von oben nach unten als Entscheidungskriterium fungiert: Wenn das Ergebnis durch die erste Ebene bestimmt wird, besteht keine Notwendigkeit, zur nächsten Ebene überzugehen, und so weiter. Nur wenn das Ergebnis nicht durch die Regeln für die Ebene bestimmt werden kann, geht der Fluss auf die nächste Ebene hinunter, um das Ergebnis zu bestimmen, für das die Aufbewahrungseinstellungen Vorrang haben.

![Diagramm der Grundsätze der Aufbewahrung](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
Erläuterung der vier verschiedenen Ebenen:
  
1. **Aufbewahrung hat Vorrang vor Löschen.** Nehmen wir einmal an, eine Aufbewahrungsrichtlinie ist so konfiguriert, dass Exchange-E-Mails nach drei Jahren gelöscht werden sollen, während eine andere Aufbewahrungsrichtlinie vorgibt, dass Exchange-E-Mails fünf Jahre aufbewahrt und dann gelöscht werden sollen. Alle Inhalte werden, sobald sie drei Jahre alt sind, gelöscht und für den Benutzer ausgeblendet, aber immer noch im Ordner "Wiederherstellbare Elemente" aufbewahrt, bis der Inhalt fünf Jahre alt ist, und dann dauerhaft gelöscht. 
2. **Der längste Aufbewahrungszeitraum hat Vorrang.** Inhalte, die mehreren Aufbewahrungsrichtlinien mit unterschiedlichen Aufbewahrungszeiträumen unterliegen, werden bis zum Ende des längsten Aufbewahrungszeitraums aufbewahrt.
    
3. **Explizite Einbindung hat Vorrang vor impliziter Einbindung.** Das bedeutet Folgendes: 
    
    1. Wenn eine Aufbewahrungsbezeichnung mit Einstellungen für die Aufbewahrung von einem Benutzer manuell einem Element, z. B. einer Exchange-E-Mail oder einem OneDrive-Dokument, zugewiesen wird, hat diese Aufbewahrungsbezeichnung sowohl Vorrang vor einer Aufbewahrungsrichtlinie, die auf Website- oder Postfachebene zugewiesen wurde, als auch vor einer Standard-Aufbewahrungsbezeichnung, die der Dokumentbibliothek zugewiesen wurde. Wenn beispielsweise die explizite Aufbewahrungsbezeichnung eine Aufbewahrung von Inhalten über zehn Jahre vorgibt, die der Website zugewiesene Aufbewahrungsrichtlinie hingegen eine Aufbewahrung von Inhalten über nur fünf Jahre, hat die Aufbewahrungsbezeichnung Vorrang. Automatisch angewendete Bezeichnungen werden als implizit und nicht explizit angesehen, da sie von Microsoft 365 automatisch angewendet werden.
    
    2. Wenn eine Aufbewahrungsrichtlinie einen bestimmten Speicherort wie das Postfach oder OneDrive-Konto eines bestimmten Benutzers umfasst, hat diese Richtlinie Vorrang vor einer anderen Aufbewahrungsrichtlinie, die für alle Postfächer oder OneDrive-Konten von Benutzern gilt, aber nicht das Postfach dieses Benutzers speziell einschließt.
    
4. **Der kürzeste Zeitraum für Löschungen hat Vorrang.** Ebenso gilt, dass wenn Inhalte mehreren Aufbewahrungseinstellungen zur Löschung (ohne Aufbewahrung) unterliegen, sie am Ende des kürzesten Aufbewahrungszeitraums gelöscht werden. 

Inhalt, der für eDiscovery gesperrt ist, kann nicht dauerhaft aufgrund einer Aufbewahrungsrichtlinie oder -bezeichnung gelöscht werden. Wenn die Sperre aufgehoben wird, ist der Inhalt wieder für den Bereinigungsprozess an den gesicherten Speicherorten für den Workload geeignet.

## <a name="auditing-retention-configuration"></a>Prüfung der Aufbewahrungskonfiguration

Administratoraktionen für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen werden im Überwachungsprotokoll gespeichert, wenn [Überwachung aktiviert](turn-audit-log-search-on-or-off.md) ist. So wird beispielsweise ein Überwachungsereignis erstellt, wenn eine Aufbewahrungsrichtlinie oder -bezeichnung erstellt, konfiguriert oder gelöscht wird. Die vollständige Liste finden Sie unter [ Aufbewahrungsrichtlinie und Aufbewahrungsbezeichnungsaktivitäten](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a>PowerShell-Cmdlets für Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

Um die Cmdlets für die Aufbewahrun zu verwenden, müssen Sie zunächst [eine Verbindung zu Office 365 Security & Compliance Center PowerShell herstellen](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell). Verwenden Sie dann eines der folgenden Cmdlets:

- [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)

- [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)

- [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)

- [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)

- [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)

- [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)

- [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)

- [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)

- [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)

- [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)

- [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)

- [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)

- [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)

- [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)

## <a name="when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds"></a>Verwenden von Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen oder eDiscovery-Aufbewahrung

Aufbewahrungseinstellungen und [Haltebereiche, die Sie mit einem eDiscovery-Fall erstellen](create-ediscovery-holds.md), können zwar beide verhindern, dass Daten dauerhaft gelöscht werden, wurden aber für unterschiedliche Szenarien entwickelt.  Mithilfe des folgenden Leitfadens können Sie die Unterschiede nachvollziehen, und entscheiden, welches Sie benutzen möchten:

- Aufbewahrungseinstellungen, die Sie in Aufbewahrungsrichtlinien festlegen, und Aufbewahrungsbezeichnungen sollen eine langfristige Strategie zur Informationsgovernance sicherstellen, und Daten zur Einhaltung von Compliance-Anforderungen aufbewahren oder löschen. Der Anwendungsbereich ist üblicherweise breit, wobei der Hauptfokus jedoch auf dem Speicherort und dem Inhalt liegt als auf einzelnen Benutzern. Der Beginn und das Ende des Aufbewahrungszeitraums sind konfigurierbar. Sie haben auch die Möglichkeit, Inhalte automatisch zu löschen, ohne dass zusätzlich ein Administrator eingreifen muss.

- eDiscovery-Haltebereiche (entweder Core eDiscovery oder Advanced eDiscovery-Fälle) sind für eine begrenzte Dauer vorgesehen, um Daten für eine rechtliche Untersuchung aufzubewahren. Der Bereich ist spezifisch, der Fokus liegt auf Inhalten, deren Besitzer identifizierte Benutzer sind. Der Beginn und das Ende des Aufbewahrungszeitraums sind nicht konfigurierbar, sondern hängen von den Aktionen des einzelnen Administrators ab. Es gibt keine Option, Inhalte automatisch zu löschen, wenn der Haltebereich freigegeben wird.

Zusammenfassender Vergleich der Aufbewahrung mit Haltebereichen:

|Überlegungen|Aufbewahrung |eDiscovery-Haltebereiche|
|:-----|:-----|:-----|:-----|
|Geschäftliche Anforderung: |Compliance |Rechtliche Hinweise |
|Zeitbereich: |Langfristig |Kurzfristig |
|Fokus: |Breit, inhaltsbasiert |Spezifisch, benutzerbasiert |
|Konfigurierbares Start-und Enddatum: |Ja |Nein |
|Löschen von Inhalten: |Ja (optional) |Nein |
|Verwaltungskosten: |Niedrig |Hoch |

Wenn Inhalte sowohl Aufbewahrungseinstellungen als auch einem eDiscovery-Haltebereich unterliegen, hat die Aufbewahrung von Inhalten für den eDiscovery-Haltebereich immer Vorrang. Auf diese Art und Weise erstrecken sich die [Prinzipien der Aufbewahrung](#the-principles-of-retention-or-what-takes-precedence) auch auf eDiscovery-Haltebereiche, da Daten aufbewahrt werden, bis ein Administrator manuell die Sperre aufhebt. Trotz dieser Rangfolge sollten Sie eDiscovery-Haltebereiche nicht für die langfristige Informationsgovernance verwenden. Falls Ihnen das automatische Löschen von Daten Sorgen bereitet, können Sie Aufbewahrungseinstellungen so konfigurieren, dass Elemente dauerhaft beibehalten werden, oder die [Löschungsprüfung](disposition.md#disposition-reviews) mit Aufbewahrungsbezeichnungen verwenden.

Wenn Sie ältere eDiscovery-Tools für die Aufbewahrung Ihrer Daten verwenden, sollten Sie sich die folgenden Ressourcen anschauen:

- Exchange: 
    - [In-Situ-Speicher und Beweissicherungsverfahren](https://go.microsoft.com/fwlink/?linkid=846124)
    - [Identifizieren des Haltebereichs für ein Exchange Online-Postfach](https://docs.microsoft.com/microsoft-365/compliance/identify-a-hold-on-an-exchange-online-mailbox)

- SharePoint und OneDrive: 
    - [Hinzufügen von Inhalten zu einem Fall und temporäres Sperren von Quellen im eDiscovery Center](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center)

- [Einstellung älterer eDiscovery-Tools](legacy-ediscovery-retirement.md)

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a>Verwenden von Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen anstelle älterer Features

Wenn Sie Inhalte in Microsoft 365 für die Informationsverwaltung proaktiv aufbewahren oder löschen müssen, empfehlen wir Ihnen die Verwendung von Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen anstelle der folgenden älteren Features.

Wenn Sie derzeit diese älteren Features verwenden, werden sie weiterhin Seite an Seite mit den Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen arbeiten. Es wird jedoch empfohlen, in Zukunft stattdessen Aufbewahrungsrichtlinien und -bezeichnungen zu verwenden. Sie bieten einen einzigen Mechanismus, um die Aufbewahrung und Löschung von Inhalten in Microsoft 365 zentral zu verwalten.

**Ältere Features von Exchange Online:**

- [Aufbewahrungstags und Aufbewahrungsrichtlinien](https://go.microsoft.com/fwlink/?linkid=846125), auch bekannt als [Messaging-Datensatzverwaltung](https://go.microsoft.com/fwlink/?linkid=846126) (Nur Löschen)

**Ältere Features von SharePoint und OneDrive:**

- [Richtlinien zum Löschen von Dokumenten](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (nur Löschvorgang)
    
- [Konfigurieren der direkten Datensatzverwaltung](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (nur Aufbewahrung) 
    
- [Verwenden von Richtlinien für das Schließen und Löschen von Websites](https://support.microsoft.com/de-DE/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (Nur Löschen) 
    
- [Informationsverwaltungsrichtlinien](intro-to-info-mgmt-policies.md) (Nur Löschen)
     
Wenn Sie SharePoint-Websites für Inhaltstyprichtlinien oder Informationsverwaltungsrichtlinien so konfiguriert haben, dass Inhalte für eine Liste oder Bibliothek aufbewahrt werden, werden diese Richtlinien ignoriert, während eine Aufbewahrungsrichtlinie in Kraft ist. 

## <a name="related-information"></a>Verwandte Informationen

- [SharePoint Online-Beschränkungen](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Limits und Spezifikationen für Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [Einhaltung der SEC-Richtlinie 17a-4](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie bereit sind, Aufbewahrungsrichtlinien zu erstellen, lesen Sie [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](create-retention-policies.md).

Erstellen und Anwenden von Aufbewahrungsbezeichnungen:
- [Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)
- [Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte](apply-retention-labels-automatically.md)

