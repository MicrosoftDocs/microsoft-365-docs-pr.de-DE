---
title: Informationen zum Dashboard zur Verhinderung von Datenverlust
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie mehr über Warnungen zur Verhinderung von Datenverlust und das Benachrichtigungsdashboard.
ms.openlocfilehash: b6fd698e535e006149f6ce3a2a5bc57d0c92c7e2
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760732"
---
# <a name="learn-about-the-data-loss-prevention-alerts-dashboard"></a>Informationen zum Dashboard zur Verhinderung von Datenverlust

Wenn die Kriterien in einer Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) mit den Aktionen eines Benutzers für ein vertrauliches Element übereinstimmen, kann die Richtlinie eine Warnung generieren. Dies kann zu einer hohen Anzahl von Warnungen führen. DLP-Warnungen werden im Benachrichtigungsdashboard erfasst. Das Benachrichtigungsdashboard bietet Ihnen einen einzigen Ort, um eine tiefe Untersuchung aller Details zur Richtlinien übereinstimmung durchzuführen.  

<!-- [Microsoft 365 compliance center](https://compliance.microsoft.com/)-->

## <a name="workloads"></a>Arbeitslasten

Das [Dashboard für die DLP-Warnungsverwaltung](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)im Microsoft 365 Compliance [Center](https://compliance.microsoft.com/)zeigt Warnungen für DLP-Richtlinien für diese Workloads an:

- Exchange
- SharePoint
- OneDrive
- Teams
- Windows 10-Geräte 

> [!TIP]
> Kunden, die [Endpoint DLP](endpoint-dlp-learn-about.md) verwenden, die für Teams [DLP](dlp-microsoft-teams.md) berechtigt sind, sehen ihre DLP-Richtlinienwarnungen für Endpunkte und Teams im DLP-Warnungsverwaltungsdashboard.

## <a name="single-alert-and-aggregate-alert"></a>Einzelne Warnung und aggregierte Warnung

Es gibt zwei Arten von Warnungen, die in DLP-Richtlinien konfiguriert werden können.

Warnungen mit einem einzelnen Ereignis werden in der Regel in Richtlinien verwendet, die hochsensible Ereignisse überwachen, die bei geringem Volumen auftreten, z. B. eine einzelne **E-Mail** mit 10 oder mehr Kreditkartennummern von Kunden, die außerhalb Ihrer Organisation gesendet werden.

**Warnungen für aggregierte** Ereignisse werden in der Regel in Richtlinien verwendet, die ereignisse überwachen, die über einen bestimmten Zeitraum auf einem höheren Volume auftreten. Beispielsweise kann eine aggregierte Warnung ausgelöst werden, wenn 10 einzelne E-Mails mit jeweils einer Kunden-Kreditkartennummer über 48 Stunden außerhalb Ihrer Organisation gesendet werden.

## <a name="types-of-events"></a>Typen von Ereignissen

Hier sind einige der Ereignisse, die einer Warnung zugeordnet sind. Auf der Benutzeroberfläche können Sie ein bestimmtes Ereignis auswählen, um dessen Details anzuzeigen. 

### <a name="event-details"></a>Ereignisdetails

|Eigenschaftenname  |Beschreibung  |Ereignistypen  |
|---------|---------|---------|
|ID |Eindeutige ID, die dem Ereignis zugeordnet ist |alle Ereignisse |
|Speicherort |Arbeitsauslastung, bei der das Ereignis erkannt wurde|alle Ereignisse |
|Zeitpunkt der Aktivität     |Zeitpunkt der Benutzeraktivität, die den Kriterien der DLP-Richtlinie entspricht |

### <a name="impacted-entities"></a>Betroffene Entitäten

|Eigenschaftenname |Beschreibung| Ereignistypen|
|---------|---------|---------|
|Benutzer | Benutzer, der die Aktion, die die Richtlinien übereinstimmung verursacht hat, ausgelöst hat | alle Ereignisse|
|hostname | Hostname des Computers, auf dem die Übereinstimmung der DLP-Richtlinie aufgetreten ist | Geräteereignisse|
|IP-Adresse | IP-Adresse des Computers, auf dem die Übereinstimmung der DLP-Richtlinie aufgetreten ist | Geräteereignisse|
|sha1 |SHA-1-Hash der Datei | Geräteereignisse|
|sha256 | SHA-256-Hash der Datei | Geräteereignisse|
|MDATP Geräte-ID | Endpunktgerät MDATP ID|
|Dateigröße | Größe der Datei| SharePoint-, OneDrive- und Geräteereignisse|
|Dateipfad | Der absolute Pfad des Elements, das mit der Übereinstimmung der DLP-Richtlinie zuhaftet | SharePoint-, OneDrive- und Geräteereignisse|
|E-Mail-Empfänger |Wenn eine E-Mail das vertrauliche Element war, das mit der DLP-Richtlinie übereinstimmen sollte, enthält dieses Feld die Empfänger dieser E-Mail.| Exchange-Ereignisse|
|E-Mail-Betreff |Betreff der E-Mail, die mit der DLP-Richtlinie übereinstimmen |Exchange-Ereignisse|
|E-Mail-Anlagen | Namen der Anlagen in der E-Mail, die mit der DLP-Richtlinie übereinstimmen| Exchange-Ereignisse|
|Websitebesitzer |Name des Websitebesitzers| SharePoint und OneDrive Ereignisse|
|Website-URL |voll mit der URL der SharePoint oder OneDrive, an der die Übereinstimmung der DLP-Richtlinie aufgetreten ist |SharePoint und OneDrive Ereignisse|
|Datei erstellt |Zeitpunkt der Erstellung der Datei, die mit der DLP-Richtlinie übereinstimmen |SharePoint und OneDrive Ereignisse|
|Zuletzt geänderte Datei | Das letzte Mal, dass die Datei, die der DLP-Richtlinie entsprechen, geändert wurde | SharePoint und OneDrive Ereignisse|
|Dateigröße | Größe der Datei, die mit der DLP-Richtlinie übereinstimmen |SharePoint und OneDrive Ereignisse|
|Dateibesitzer |Besitzer der Datei, die mit der DLP-Richtlinie übereinstimmen |SharePoint und OneDrive Ereignisse|  

### <a name="policy-details"></a>Richtliniendetails

|Eigenschaftenname |Beschreibung |Ereignistypen |
|---------|---------|---------|
|Übereinstimmung der DLP-Richtlinie |Name der übereinstimmende DLP-Richtlinie |alle Ereignisse|
|Regel wurde übereinstimmend |Name der übereinstimmende DLP-Richtlinienregel |alle Ereignisse|
|Typen vertraulicher Informationen (SENSITIVE Information Types, SIT) erkannt|SITs, die im Rahmen der Übereinstimmung mit der DLP-Richtlinie erkannt wurden |alle Ereignisse|
|Durchgeführte Aktionen |Aktionen, die die Übereinstimmung der DLP-Richtlinie verursacht haben| alle Ereignisse|
|Verletzende Aktion | Aktion auf dem Endpunktgerät, das die DLP-Warnung ausgelöst hat| Geräteereignisse | 
|Benutzerüberrodungsrichtlinie |hat der Benutzer die Richtlinie über einen Richtlinientipp außer Kraft setzen | alle Ereignisse|
|Verwenden der Außerkraftsetzungsüberschreibungsüberschreibung |der Text des vom Benutzer für die Außerkraftsetzung angegebenen Grunds | alle Ereignisse|   

## <a name="see-also"></a>Siehe auch

- [Erste Schritte mit dem Dashboard zur Verhinderung von Datenverlust](dlp-alerts-dashboard-get-started.md)
- [Erste Schritte mit DLP (Verhinderung von Datenverlust)](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)