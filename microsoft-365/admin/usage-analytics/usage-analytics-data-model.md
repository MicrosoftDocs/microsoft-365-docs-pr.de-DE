---
title: Microsoft 365 Datenmodell von Nutzungsanalysen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 08c5307c-4a6b-4761-8410-a6c96725760f
description: 'Erfahren Sie, wie die Verwendungsanalyse eine Verbindung mit einer API herstellt und eine monatliche Nutzungs Tendenz verschiedener Microsoft 365-Dienste bereitstellt.  '
ms.openlocfilehash: 1fa1cb842b603a920665ec1b59ca18f586b5d181
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560859"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Microsoft 365 Datenmodell von Nutzungsanalysen

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>Daten für die Microsoft 365 Nutzungsanalysetabellen

Die Nutzungsanalyse von Microsoft 365 verbindet sich mit einer API, die ein mehrdimensionales Datenmodell bereitstellt. Die APIs befinden sich in der Vorschau und können unter verwendet werden `https://reports.office.com/pbi/v1.0/\<tenantid\>` (ersetzen \<tenant id\> Sie die durch ihre Mandanten-GUID). 
  
> [!NOTE]
> Weitere Informationen finden Sie unter [Arbeiten mit Microsoft 365-Nutzungsberichten in Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=864336). 
  
Diese API enthält Informationen zur monatlichen Nutzungs Tendenz der verschiedenen Microsoft 365-Dienste. Die genauen Daten, die von der API zurückgegeben werden, finden Sie in der Tabelle im folgenden Abschnitt.
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>Von der Microsoft 365-Berichts-API zurückgegebene Datentabellen

|**Tabellenname**|**Informationen in der Tabelle**|**Datumsbereich**|
|:-----|:-----|:-----|
|Tenant Product Usage  <br/> |Enthält monatliche Gesamtsummen für aktivierte, aktive Benutzer, Monat für Monat behaltene Benutzer, erstmalige Benutzer und die kumulativen aktiven Benutzer.  <br/> |Enthält monatliche kumulierte Daten für einen fortlaufenden 12-monatigen Zeitraum einschließlich des aktuellen Teilmonats.  <br/> |
|Tenant Product Activity  <br/> |Enthält monatliche Gesamtsummen der Anzahl von Aktivitäten und aktiven Benutzern für verschiedene Aktivitäten innerhalb der Produkte.  <br/> Informationen zu den Aktivitäten innerhalb eines Produkts, die in dieser Datentabelle zurückgegeben werden, finden Sie unter [Definition aktiver Benutzer](active-user-in-usage-reports.md).  <br/> |Enthält monatliche kumulierte Daten für einen fortlaufenden 12-monatigen Zeitraum einschließlich des aktuellen Teilmonats.  <br/> |
|Tenant Office Licenses  <br/> |Enthält Daten zur Anzahl von Microsoft Office-Abonnements, die Benutzern zugewiesen sind.  <br/> |Enthält Monats Zustandsdaten für einen laufenden 12-monatigen Zeitraum einschließlich des aktuellen Teil Monats.  <br/> |
|Tenant Mailbox Usage  <br/> |Enthält Daten zum Postfach des Benutzers, die sich auf die Gesamtpostfachanzahl und die Verwendung des Speichers beziehen.  <br/> |Enthält Monats Zustandsdaten für einen laufenden 12-monatigen Zeitraum einschließlich des aktuellen Teil Monats.  <br/> |
|Tenant Client Usage  <br/> |Enthält Daten zur Anzahl der Benutzer, die bestimmte Clients/Geräte aktiv verwenden, um eine Verbindung mit Exchange Online, Skype for Business und Yammer herzustellen.  <br/> |Enthält monatliche kumulierte Daten für einen fortlaufenden 12-monatigen Zeitraum einschließlich des aktuellen Teilmonats.  <br/> |
|Tenant SharePoint Online Usage  <br/> |Enthält Daten zu den SharePoint-Websites, die Team- oder Gruppenwebsites umfassen, z. B. die Gesamtanzahl von Websites, die Anzahl von Dokumenten auf der Website, die Anzahl der Dateien nach Aktivitätstyp und verwendetem Speicherplatz.  <br/> |Enthält Monats Zustandsdaten für einen laufenden 12-monatigen Zeitraum einschließlich des aktuellen Teil Monats.  <br/> |
|Tenant OneDrive for Business Usage  <br/> |Enthält Daten zu den OneDrive-Konten, z. B. die Anzahl der Konten, die Anzahl der auf OneDrive verteilten Dokumente, der verwendete Speicherplatz oder die Dateianzahl nach Aktivitätstyp.  <br/> |Enthält Monats Zustandsdaten für einen laufenden 12-monatigen Zeitraum einschließlich des aktuellen Teil Monats.  <br/> |
|Mandanten Microsoft 365 Gruppen Nutzung  <br/> |Enthält Daten zur Verwendung von Microsoft 365-Gruppen, einschließlich Mailbox, SharePoint und jammern.  <br/> |Enthält Monats Zustandsdaten für einen laufenden 12-monatigen Zeitraum einschließlich des aktuellen Teil Monats.  <br/> |
|Tenant Office Activation  <br/> |Enthält Daten zur Anzahl der Office-Abonnement Aktivierungen, zur Anzahl der Aktivierungen pro Gerät (Android/IOS/Mac/PC), Aktivierungen nach Dienstplänen, beispielsweise Microsoft 365-Apps für Unternehmen, Visio, Project.  <br/> |Enthält Monats Zustandsdaten für einen laufenden 12-monatigen Zeitraum einschließlich des aktuellen Teil Monats.  <br/> |
|Benutzerstatus  <br/> |Enthält Metadaten zu Benutzern, einschließlich Anzeigename des Benutzers, zugewiesene Produkte, Standort, Abteilung, Titel, Unternehmen. Bei diesen Daten handelt es sich um Benutzer, denen im letzten abgeschlossenen Monat eine Lizenz zugewiesen wurde. Jeder Benutzer wird durch eine Benutzer-ID eindeutig dargestellt.  <br/> |Diese Daten beziehen sich auf Benutzer, denen im letzten abgelaufenen Monat eine Lizenz zugewiesen war.  <br/> |
|User Activity  <br/> |Enthält Informationen pro Benutzer zu den von lizenzierten Benutzern ausgeführten Aktivitäten.  <br/> Informationen zu den Aktivitäten innerhalb eines Produkts, die in dieser Datentabelle zurückgegeben werden, finden Sie unter [Definition aktiver Benutzer](active-user-in-usage-reports.md).  <br/> |Diese Daten beziehen sich auf Benutzer, die im letzten abgelaufenen Monat eine Aktivität in einem der Dienste ausgeführt haben.  <br/> |
   
Erweitern Sie die folgenden Abschnitte, um ausführliche Informationen zu jeder Datentabelle anzuzeigen.
  
### <a name="data-table---user-state"></a>Datentabelle – User State

Diese Tabelle enthält Details auf Benutzerebene für alle Benutzer, denen im letzten abgelaufenen Monat eine Lizenz zugewiesen war. Sie bezieht Daten aus Azure Active Directory ein.
  
|**Spaltenname**|**Spaltenbeschreibung**|
|:-----|:-----|
|UserId  <br/> |Eindeutige Benutzer-ID, die einen Benutzer darstellt und eine Verknüpfung mit anderen Datentabellen innerhalb des Datasets ermöglicht.  <br/> |
|Timeframe  <br/> |Monatswert, für den diese Tabelle Daten enthält.  <br/> |
|UPN  <br/> |Benutzerprinzipalname. Eindeutige Kennzeichnung des Benutzers, der eine Verknüpfung mit anderen externen Datenquellen herstellen kann.  <br/> |
|DisplayName  <br/> |Der Anzeigename des Benutzers.  <br/> |
|IDType  <br/> |Der ID-Typ ist auf 1 festgelegt, wenn es sich bei dem Benutzer um einen Benutzer mit Jammer-ID oder 0 handelt, der eine Verbindung mit jammern herstellt, indem er seine Microsoft 365-ID verwendet.  <br/> Der Wert ist 1, um darzustellen, dass diese Benutzer eine Verbindung mit der Jammer-ID und nicht mit Ihrer Microsoft 365-ID herstellen.  <br/> |
|HasLicenseEXO  <br/> |Auf "True" festgelegt, wenn dem Benutzer eine Lizenz zugewiesen ist und er für die Verwendung von Exchange aktiviert ist.  <br/> |
|HasLicenseODB  <br/> |Auf "True" festgelegt, wenn dem Benutzer eine Lizenz zugewiesen ist und er für die Verwendung von OneDrive for Business aktiviert ist.  <br/> |
|HasLicenseSPO  <br/> |Auf "True" festgelegt, wenn dem Benutzer eine Lizenz zugewiesen ist und er für die Verwendung von SharePoint Online aktiviert ist.  <br/> |
|HasLicenseYAM  <br/> |Auf "True" festgelegt, wenn dem Benutzer eine Lizenz zugewiesen ist und er für die Verwendung von Yammer aktiviert ist.  <br/> |
|HasLicenseSFB  <br/> |Auf "True" festgelegt, wenn dem Benutzer eine Lizenz zugewiesen ist und er für die Verwendung von Skype for Business aktiviert ist.  <br/> |
|HasLicenseTeams  <br/> |Auf "True" festgelegt, wenn dem Benutzer eine Lizenz zugewiesen ist und er für die Verwendung von Microsoft Teams aktiviert ist.  <br/> |
|Unternehmen  <br/> |Daten zum Unternehmen, die in Azure Active Directory für diesen Benutzer angegeben sind.  <br/> |
|Department  <br/> |Daten zur Abteilung, die in Azure Active Directory für diesen Benutzer angegeben sind.  <br/> |
|LocationCity  <br/> |Daten zum Ort, die in Azure Active Directory für diesen Benutzer angegeben sind.  <br/> |
|LocationCountry  <br/> |Daten zum Land, die in Azure Active Directory für diesen Benutzer angegeben sind.  <br/> |
|LocationState  <br/> |Daten zum Bundesland, die in Azure Active Directory für diesen Benutzer angegeben sind.  <br/> |
|LocationOffice  <br/> |Das Büro des Benutzers.  <br/> |
|Title  <br/> |Daten zum Titel, die in Azure Active Directory für diesen Benutzer angegeben sind.  <br/> |
|Gelöscht  <br/> |True, wenn der Benutzer in diesem letzten abgeschlossenen Monat aus Microsoft 365 gelöscht wurde.  <br/> |
|DeletedDate  <br/> |Datum, an dem der Benutzer aus Microsoft 365 gelöscht wurde.  <br/> |
|YAM_State  <br/> |Die möglichen Statusangaben für den Benutzer im Yammer-System sind "aktiv", "gelöscht" oder "gesperrt".  <br/> |
|YAM_ActivationDate  <br/> |Das Datum, an dem für den Benutzer in Yammer der Status "aktiv" angegeben wurde.  <br/> |
|YAM_DeletionDate  <br/> |Das Datum, an dem für den Benutzer in Yammer der Status "gelöscht" angegeben wurde.  <br/> |
|YAM_SuspensionDate  <br/> |Das Datum, an dem für den Benutzer in Yammer der Status "gesperrt" angegeben wurde.  <br/> |
   
### <a name="data-table---user-activity"></a>Datentabelle – User Activity

Diese Tabelle enthält Daten zu jedem Benutzer, der im vorherigen Monat in einem der Dienste eine Aktivität ausgeführt hat.
  
|**Spaltenname**|**Spaltenbeschreibung**|
|:-----|:-----|
|UserID  <br/> |Eindeutige Benutzer-ID, die einen Benutzer darstellt und eine Verknüpfung mit anderen Datentabellen innerhalb des Datasets ermöglicht.  <br/> |
|IDType  <br/> |Der ID-Typ ist auf 1 festgelegt, wenn es sich bei dem Benutzer um einen Benutzer mit Jammer-ID oder 0 handelt, der eine Verbindung mit jammern herstellt, indem er seine Microsoft 365-ID verwendet.  <br/> Der Wert ist 1, um darzustellen, dass diese Benutzer eine Verbindung mit der Jammer-ID und nicht mit Ihrer Microsoft 365-ID herstellen.  <br/> |
|Timeframe  <br/> |Monatswert, für den diese Tabelle Daten enthält.  <br/> |
|EXO_EmailSent  <br/> |Die Anzahl von gesendeten E-Mails.  <br/> |
|EXO_EmailReceived  <br/> |Die Anzahl von empfangenen E-Mails.  <br/> |
|EXO_EmailRead  <br/> |Die Anzahl von Aktivitäten vom Typ "E-Mail lesen", die der Benutzer ausgeführt hat. Dabei kann eine bereits gelesene E-Mail mehrere Male gelesen werden, oder es kann eine zuvor empfangene E-Mail gelesen werden.
 









  <br/> |
|EXO_AppointmentCreated  <br/> |Die Anzahl der erstellten Besprechungen.  <br/> |
|EXO_MeetingAccepted  <br/> |Die Anzahl der akzeptierten Besprechungen.  <br/> |
|EXO_MeetingCancelled  <br/> |Die Anzahl der abgesagten Besprechungen.  <br/> |
|EXO_MeetingDeclined  <br/> |Die Anzahl der abgelehnten Besprechungen.  <br/> |
|EXO_MeetingSent  <br/> |Die Anzahl der gesendeten Besprechungen.  <br/> |
|ODB_FileViewedModified  <br/> |Die Anzahl von Dateien, mit denen dieser Benutzer auf OneDrive for Business interagiert hat (z. B. erstellt, aktualisiert, gelöscht, angezeigt oder heruntergeladen).  <br/> |
|ODB_FileSynched  <br/> |Die Anzahl von Dateien, die dieser Benutzer auf OneDrive for Business synchronisiert hat.  <br/> |
|ODB_FileSharedInternally  <br/> |Die Anzahl der Dateien, die dieser Benutzer intern von einem beliebigen OneDrive for Business oder mit Benutzern innerhalb von Gruppen (zu denen auch externe Benutzer gehören können) freigegeben hat.  <br/> |
|ODB_FileSharedExternally  <br/> |Die Anzahl von Dateien, die dieser Benutzer auf OneDrive for Business extern freigegeben hat.  <br/> |
|ODB_AccessByOwner  <br/> |Die Anzahl von Dateien, mit denen dieser Benutzer interagiert hat und die sich im eigenen OneDrive for Business-Speicher befinden.  <br/> |
|ODB_AccessOthers  <br/> |Die Anzahl von Dateien, mit denen dieser Benutzer interagiert hat und die sich im OneDrive for Business-Speicher eines anderen Benutzers befinden.  <br/> |
|SPO_GroupFileViewedModified  <br/> |Die Anzahl von Dateien, mit denen dieser Benutzer auf einer beliebigen Gruppenwebsite interagiert hat.  <br/> |
|SPO_GroupFileSynched  <br/> |Die Anzahl von Dateien, die dieser Benutzer auf einer beliebigen Gruppenwebsite synchronisiert hat.  <br/> |
|SPO_GroupFileSharedInternally  <br/> |Die Anzahl der Dateien, die für Benutzer innerhalb der Organisation oder für Benutzer innerhalb von Gruppen (die auch externe Benutzer enthalten können) freigegeben wurden.  <br/> |
|SPO_GroupFileSharedExternally  <br/> |Die Anzahl von Dateien, die dieser Benutzer von einer beliebigen Gruppenwebsite extern freigegeben hat.  <br/> |
|SPO_GroupAccessByOwner  <br/> |Die Anzahl von Dateien, mit denen der Benutzer interagiert hat und die sich auf einer Gruppenwebsite befinden, die er besitzt.  <br/> |
|SPO_GroupAccessByOthers  <br/> |Die Anzahl von Dateien, mit denen der Benutzer interagiert hat und die sich auf einer Gruppenwebsite befinden, die ein anderer Benutzer besitzt.  <br/> |
|SPO_OtherFileViewedModified  <br/> |Die Anzahl von Dateien, mit denen dieser Benutzer auf einer beliebigen Website interagiert hat.  <br/> |
|SPO_OtherFileSynched  <br/> |Die Anzahl von Dateien, die dieser Benutzer von einer beliebigen Website synchronisiert hat.  <br/> |
|SPO_OtherFileSharedInternally  <br/> |Die Anzahl der Dateien, die dieser Benutzer intern von einer beliebigen Website oder mit Benutzern innerhalb von Gruppen (zu denen auch externe Benutzer gehören können) freigegeben hat. <br/> |
|SPO_OtherFileSharedExternally  <br/> |Die Anzahl von Dateien, die dieser Benutzer von einer beliebigen Website extern freigegeben hat.  <br/> |
|SPO_OtherAccessedByOwner  <br/> |Die Anzahl von Dateien, mit denen der Benutzer interagiert hat und die sich auf einer Website befinden, die er besitzt.  <br/> |
|SPO_OtherAccessedByOthers  <br/> |Die Anzahl von Dateien, mit denen der Benutzer interagiert hat und die sich auf einer Website befinden, die ein anderer Benutzer besitzt.  <br/> |
|SPO_TeamFileViewedModified  <br/> |Die Anzahl von Dateien, mit denen dieser Benutzer auf einer beliebigen Teamwebsite interagiert hat.  <br/> |
|SPO_TeamFileSynched  <br/> |Die Anzahl von Dateien, die dieser Benutzer von einer beliebigen Teamwebsite synchronisiert hat.  <br/> |
|SPO_TeamFileSharedInternally  <br/> |Die Anzahl der Dateien, die dieser Benutzer intern von einer beliebigen Teamwebsite oder mit Benutzern innerhalb von Gruppen (zu denen auch externe Benutzer gehören können) freigegeben hat.  <br/> |
|SPO_TeamFileSharedExternally  <br/> |Die Anzahl von Dateien, die dieser Benutzer von einer beliebigen Teamwebsite extern freigegeben hat.  <br/> |
|SPO_TeamAccessByOwner  <br/> |Die Anzahl von Dateien, mit denen der Benutzer interagiert hat und die sich auf einer Teamwebsite befinden, die er besitzt.  <br/> |
|SPO_TeamAccessByOthers  <br/> |Die Anzahl von Dateien, mit denen der Benutzer interagiert hat und die sich auf einer Teamwebsite befinden, die ein anderer Benutzer besitzt.  <br/> |
|Teams_ChatMessages  <br/> |Die Anzahl der gesendeten Chat-Nachrichten.  <br/> |
|Teams_ChannelMessage  <br/> |Die Anzahl der Nachrichten, die in den Kanälen gepostet wurden.  <br/> |
|Teams_CallParticipate  <br/> |Die Anzahl der Anrufe, an denen der Benutzer teilgenommen hat.  <br/> |
|Teams_MeetingParticipate  <br/> |Die Anzahl der Besprechungen, an denen der Benutzer teilgenommen hat.  <br/> |
|Teams_HasOtherAction  <br/> |Boolescher Wert, wenn der Benutzer andere Aktionen in Microsoft Teams durchgeführt hat.  <br/> |
|YAM_MessagePost  <br/> |Die Anzahl von Yammer-Nachrichten, die dieser Benutzer gepostet hat.  <br/> |
|YAM_MessageLiked  <br/> |Die Anzahl von Yammer-Nachrichten, die dieser Benutzer mit "Gefällt mir" gekennzeichnet hat.  <br/> |
|YAM_MessageRead  <br/> |Die Anzahl von Yammer-Nachrichten, die dieser Benutzer gelesen hat.  <br/> |
|SFB_P2PSummary  <br/> |Die Anzahl von Peer-zu-Peer-Sitzungen, an denen dieser Benutzer teilgenommen hat.  <br/> |
|SFB_ConfOrgSummary  <br/> |Die Anzahl von Konferenzsitzungen, die dieser Benutzer organisiert hat.  <br/> |
|SFB_ConfPartSummary  <br/> |Die Anzahl von Konferenzsitzungen, an denen dieser Benutzer teilgenommen hat.  <br/> |

> [!NOTE]
> Teams_HasOtherAction bedeutet, dass der Benutzer als aktiv eingestuft wird, aber einen Nullwert für die Chat Nachrichten, 1:1 Anrufe, Kanal Nachrichten, Gesamt Besprechungen und Besprechungen organisiert hat.
   
### <a name="data-table---tenant-product-usage"></a>Datentabelle – Tenant Product Usage

Diese Tabelle enthält Daten zur Monats übergreifenden Einführung in Bezug auf Enable, Active, Returning und First-Time Users für jedes Produkt in Microsoft 365. Der Microsoft 365-Wert stellt die aktive Verwendung in einem der Produkte dar.
  
|**Spaltenname**|**Spaltenbeschreibung**|
|:-----|:-----|
|Produkt  <br/> |Name der Produkte, für die die Informationen zur Nutzung zusammengefasst werden. Microsoft 365-Wert in der Spalte Product stellt Aktivitäten für alle Produkte dar.  <br/> |
|Timeframe  <br/> |Monatswert. Es gibt eine Zeile pro Produkt pro Monat für die letzten 12 Monate einschließlich des aktuellen Teilmonats.  <br/> |
|EnabledUsers  <br/> |Die Anzahl der Benutzer, die zur Verwendung des Produkts für den Zeitrahmenwert aktiviert sind. Wenn ein Benutzer für einen Teil des Monats aktiviert wurde, wird er dennoch gezählt.  <br/> |
|ActiveUsers  <br/> |Die Anzahl der Benutzer, die eine beabsichtigte Aktivität im Produkt für den Zeitrahmenwert ausgeführt haben.  <br/> Ein Benutzer wird für ein Produkt für einen bestimmten Monat als aktiviert gezählt, wenn er eine der Hauptaktivitäten im Produkt ausgeführt hat. Die Hauptaktivitäten sind in der Tabelle **Tenant Product Activity** verfügbar.  <br/> |
|CumulativeActiveUsers  <br/> |Die Anzahl der Benutzer, die zur Verwendung eines Produkts aktiviert sind und das Produkt bis zum Zeitrahmenmonat mindestens einmal seit Beginn der Datensammlung im neuen Verwendungssystem genutzt haben.  <br/> |
|MoMReturningUsers  <br/> |Die Anzahl der Benutzer, die im Zeitrahmenmonat aktiv sind und auch im vorherigen Monat aktiv waren.  <br/> |
|FirstTimeUsers  <br/> |Die Anzahl der Benutzer, die im Zeitrahmen zum ersten Mal seit Beginn der Datensammlung im neuen Verwendungssystem aktiv wurden.  <br/> Ein Benutzer wird in einem bestimmten Monat als erstmaliger Benutzer gezählt, wenn seine Aktivität seit Beginn der Datensammlung in diesem neuen Berichtssystem zum ersten Mal erkannt wurde. Einmal als Erstbenutzer gezählt, selbst wenn dieser Benutzer eine große Lücke in Ihrer Aktivität hat, werden Sie nie wieder als Erstbenutzer gezählt.  <br/> |
|Content Date  <br/> |Wenn der Zeitrahmen den aktuellen Monat angibt, stellt dieser Wert das neueste Datum des aktuellen Monats dar, für das Daten verfügbar sind.  <br/> Wenn der Zeitrahmen den vorherigen Monat angibt, stellt dieser Wert das letzte Datum des Zeitrahmenmonats dar.  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>Datentabelle – Tenant Product Activity 

Diese Tabelle enthält monatliche Gesamtsummen der Anzahl von Aktivitäten und aktiven Benutzern für verschiedene Aktivitäten innerhalb der Produkte.
  
|**Spaltenname**|**Spaltenbeschreibung**|
|:-----|:-----|
|Timeframe  <br/> |Monatswert. Es gibt eine Zeile pro Produkt pro Monat für die letzten 12 Monate einschließlich des aktuellen Teilmonats.  <br/> |
|Product  <br/> |Name des Produkts in Microsoft 365, für das Verwendungsdaten verfügbar sind.  <br/> |
|Activity  <br/> |Name der Aktivität in einem Produkt, die zur Veranschaulichung der aktiven Nutzung des Produkts verwendet wird.  <br/> |
|ActivityCount  <br/> |Dies ist die Gesamtanzahl von Aktionen, die für jede Aktivität gezählt werden, die von allen aktiven Benutzern innerhalb des Produkts ausgeführt wird.  <br/> **Hinweis:** Bei SharePoint Online- und OneDrive for Business-Aktivitäten stellt dieser Wert die Anzahl der verschiedenen Dokumente dar, mit denen Benutzer interagierten.  <br/> |
|ActiveUserCount  <br/> |Die Anzahl der Benutzer, die die Aktivität innerhalb des Produkts ausgeführt haben.  <br/> |
|TotalDurationInMinute  <br/> |Die Dauer in Minuten für alle aktiven Benutzer, die eine Audio- oder Videositzung in einer entsprechenden Skype for Business-Aktivität verwendet haben.  <br/> |
|Content Date  <br/> |Wenn der Zeitrahmen den aktuellen Monat angibt, stellt dieser Wert das neueste Datum des aktuellen Monats dar, für das Daten verfügbar sind.  <br/> Wenn der Zeitrahmen den vorherigen Monat angibt, stellt dieser Wert das letzte Datum des Zeitrahmenmonats dar.  <br/> |
   
### <a name="data-table---tenant-mailbox-usage"></a>Datentabelle – Tenant Mailbox Usage

Diese Tabelle besteht aus Zusammenfassungsdaten für alle lizenzierten Exchange Online-Benutzer, die über ein Benutzerpostfach verfügen. Sie enthält den Monatsendzustand für alle Benutzerpostfächer. Die Daten in dieser Tabelle werden nicht für mehrere Monate zusammengefasst. Die Daten des letzten Monats in dieser Tabelle stellen den aktuellsten Zustand dar.
  
|**Spaltenname**|**Spaltenbeschreibung**|
|:-----|:-----|
|TotalMailboxes  <br/> |Die Anzahl der Benutzerpostfächer für das Microsoft 365-Abonnement.  <br/> |
|IssueWarningQuota  <br/> |Das Gesamtkontingent für die Ausgabe von Warnungen für alle Benutzerpostfächer.  <br/> |
|ProhibitSendQuota  <br/> |Das Gesamtkontingent für untersagte Sendevorgänge für alle Benutzerpostfächer.  <br/> |
|ProhibitSendReceiveQuota  <br/> |Das Gesamtkontingent für untersagte Sende-/Empfangsvorgänge für alle Benutzerpostfächer.  <br/> |
|TotalItemBytes  <br/> |Die Menge an Speicherplatz in Byte, der für alle Benutzerpostfächer verwendet wird.  <br/> |
|MailboxesNoWarning  <br/> |Die Anzahl der Benutzerpostfächer, die unter dem Limit für Speicherwarnungen geblieben sind.  <br/> |
|MailboxesIssueWarning  <br/> |Die Anzahl der Benutzerpostfächer, für die eine Speicherkontingentwarnung ausgegeben wurde.  <br/> |
|MailboxesExceedSendQuota  <br/> |Die Anzahl der Benutzerpostfächer, die das Kontingent für Sendevorgänge überschritten haben.  <br/> |
|MailboxesExceedSendReceiveQuota  <br/> |Die Anzahl der Benutzerpostfächer, die das Kontingent für Sende-/Empfangsvorgänge überschritten haben.  <br/> |
|DeletedMailboxes  <br/> |Die Anzahl der Benutzerpostfächer, die im Zeitrahmen gelöscht wurden.  <br/> |
|Timeframe  <br/> |Monatswert.  <br/> |
|Content Date  <br/> |Wenn der Zeitrahmen den aktuellen Monat angibt, stellt dieser Wert das neueste Datum des aktuellen Monats dar, für das Daten verfügbar sind.  <br/> Wenn der Zeitrahmen den vorherigen Monat angibt, stellt dieser Wert das letzte Datum des Zeitrahmenmonats dar.  <br/> |
   
### <a name="data-table---tenant-client-usage"></a>Datentabelle – Tenant Client Usage 

Diese Tabelle enthält zusammenfassende Zusammenfassungsdaten von Monaten über die Clients, die die Benutzer zum Herstellen einer Verbindung mit Exchange Online, Skype for Business und jammern verwenden. In dieser Tabelle sind noch keine Daten zur Clientnutzung für SharePoint Online und OneDrive for Business enthalten.
  
|**Spaltenname**|**Spaltenbeschreibung**|
|:-----|:-----|
|Produkt  <br/> |Name des Produkts in Microsoft 365, für das Client Nutzungsdaten verfügbar sind.  <br/> |
|ClientId  <br/> |Name des jeweiligen Geräts, mit dem die Verbindung mit dem Produkt hergestellt wurde.  <br/> |
|UserCount  <br/> |Die Anzahl der Benutzer, die den jeweiligen Client für jedes Produkt verwendet haben.  <br/> |
|Timeframe  <br/> |Monatswert.  <br/> |
|Content Date  <br/> |Wenn der Zeitrahmen den aktuellen Monat angibt, stellt dieser Wert das neueste Datum des aktuellen Monats dar, für das Daten verfügbar sind.  <br/> Wenn der Zeitrahmen den vorherigen Monat angibt, stellt dieser Wert das letzte Datum des Zeitrahmenmonats dar.  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>Datentabelle – Tenant SharePoint Online Usage

Diese Tabelle enthält monatliche Zusammenfassungsdaten zur Nutzung oder Aktivität von SharePoint Online-Websites. Dies umfasst nur Teamwebsites und Gruppenwebsites. Der Monatsendzustand von SharePoint Online-Websites wird in dieser Spalte dargestellt. Wenn z. B. ein Benutzer fünf Dokumente erstellt und 10 MB Gesamtspeicherplatz verwendet, und dann einige Dateien gelöscht sowie weitere Dateien hinzugefügt hat, sodass der Monatsendzustand eine Gesamtzahl von sieben Dateien ergibt, die 5 MB Speicherplatz verwenden. Der in dieser Tabelle dargestellte Wert ist dann der Monatsendzustand. Diese Tabelle wird ausgeblendet, um zu vermeiden, dass Aggregationen doppelt gezählt werden. Die Tabelle wird als Quelle zum Erstellen von zwei Referenztabellen verwendet.
  
|**Name der Spalte**|**Spaltenbeschreibung**|
|:-----|:-----|
|SiteType  <br/> |Websitetypwert (any/team/group) ("any" stellt einen dieser beiden Websitetypen dar).  <br/> |
|TotalSites  <br/> |Die Anzahl der Websites, die am Ende des Zeitrahmens vorhanden waren.  <br/> |
|DocumentCount  <br/> |Die Gesamtzahl der Dokumente, die am Ende des Zeitrahmens auf der Website vorhanden waren.  <br/> |
|Diplansed  <br/> |Verwendeter Gesamtspeicherplatz für alle Websites am Ende des Zeitrahmens.  <br/> |
|ActivityType  <br/> |Die Anzahl der Websites, die die verschiedenen Arten von Dateiaktivitäten aufgezeichnet haben (any/active files/files shared EXT/INT/files synched).  <br/> "Any" gibt an, dass eine beliebige Dateiaktivität ausgeführt wurde.  <br/> |
|SitesWithOwnerActivities  <br/> |Die Anzahl aktiver Websites, bei denen der Websitebesitzer eine bestimmte Dateiaktivität auf seinen eigenen Websites ausgeführt hat.  <br/> |
|SitesWithNonOwnerActivities  <br/> |Die Anzahl der für den Monat zusammengefassten aktiven Websites, bei denen andere Benutzer als der Websitebesitzer eine bestimmte Dateiaktivität auf Websites ausgeführt haben.  <br/> |
|ActivityTotalSites  <br/> |Die Anzahl der Websites, die im Zeitrahmen eine Aktivität aufgezeichnet haben. Eine Website, bei der zu Anfang des Zeitrahmens eine Aktivität aufgetreten ist und die gegen Ende des Zeitrahmens gelöscht wurde, wird dennoch für den Gesamtwert der aktiven Websites für diesen Zeitrahmen gezählt.  <br/> |
|Timeframe  <br/> |Diese Spalte enthält den Datumswert. Als n:1-Beziehung für die Tabelle "Kalender" verwendet.  <br/> |
|Content Date  <br/> |Wenn der Zeitrahmen den aktuellen Monat angibt, stellt dieser Wert das neueste Datum des aktuellen Monats dar, für das Daten verfügbar sind.  <br/> Wenn der Zeitrahmen den vorherigen Monat angibt, stellt dieser Wert das letzte Datum des Zeitrahmenmonats dar.  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>Datentabelle – Tenant OnveDrive Usage

Diese Tabelle enthält Daten zu OneDrive-Konten, z. B. die Anzahl der Konten, die Anzahl der auf OneDrive-Konten verteilten Dokumente, der verwendete Speicherplatz oder die Anzahl der Dateien nach Aktivitätstyp. Der Monatsendzustand von OneDrive for Business-Konten wird in dieser Tabelle dargestellt. Wenn z. B. ein Benutzer fünf Dokumente erstellt und 10 MB Speicherplatz verwendet und dann einige Dateien löscht sowie weitere Dateien hinzufügt, sodass der Monatsendzustand eine Gesamtzahl von sieben Dateien ergibt, die 5 MB Speicherplatz verwenden, dann wird der Monatsendwert in dieser Tabelle am Ende des Monats dargestellt.
  
|**Spaltenname**|**Spaltenbeschreibung**|
|:-----|:-----|
|SiteType  <br/> |Der Wert ist "OneDrive"  <br/> |
|TotalSites  <br/> |Die Anzahl der OneDrive for Business-Konten, die am Ende des Zeitrahmens vorhanden waren.  <br/> |
|DocumentCount  <br/> |Die Gesamtanzahl der Dokumente, die am Ende des Zeitrahmens auf allen OneDrive for Business-Konten vorhanden waren  <br/> |
|Diplansed  <br/> |Verwendeter Gesamtspeicherplatz für alle OneDrive for Business-Konten am Ende des Zeitrahmens.  <br/> |
|ActivityType  <br/> |Die Anzahl der Konten, die die verschiedenen Arten von Dateiaktivitäten aufgezeichnet haben (beliebig/aktive Dateien/EXT bzw. INT freigegebene Dateien/synchronisierte Dateien).  <br/> "Any" gibt an, dass eine beliebige Dateiaktivität ausgeführt wurde.  <br/> |
|SitesWithOwnerActivities  <br/> |Die Anzahl aktiver OneDrive for Business-Konten, bei denen der Kontobesitzer eine bestimmte Dateiaktivität im eigenen Konto durchgeführt hat.  <br/> |
|SitesWithNonOwnerActivities  <br/> |Die Anzahl von OneDrive for Business-Konten, bei denen die Dateiaktivität von einem anderen Benutzer als dem Kontobesitzer durchgeführt wurde.  <br/> |
|ActivityTotalSites  <br/> |Die Anzahl der OneDrive for Business-Konten, die im Zeitrahmen eine Aktivität aufgezeichnet haben. Ein OneDrive for Business-Konto, bei dem zu Anfang des Zeitrahmens eine Aktivität aufgetreten ist und das gegen Ende des Zeitrahmens gelöscht wurde, wird dennoch als aktives OneDrive for Business-Konto für diesen Zeitrahmen gezählt.  <br/> |
|Timeframe  <br/> |Diese Spalte enthält den Datumswert. Als n:1-Beziehung für die Tabelle "Kalender" verwendet.  <br/> |
|Content Date  <br/> |Wenn der Zeitrahmen den aktuellen Monat angibt, stellt dieser Wert das neueste Datum des aktuellen Monats dar, für das Daten verfügbar sind.  <br/> Wenn der Zeitrahmen den vorherigen Monat angibt, stellt dieser Wert das letzte Datum des Zeitrahmenmonats dar.  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>Datentabelle-Mandanten Verwendung von Microsoft 365-Gruppen

Diese Tabelle enthält Daten darüber, wie Microsoft 365-Gruppen in der gesamten Organisation verwendet werden.
  
****

|**Spaltenname**|**Spaltenbeschreibung**|
|:-----|:-----|
|Timeframe  <br/> |Monatswert. Es gibt eine Zeile pro Produkt pro Monat für die letzten 12 Monate einschließlich des aktuellen Teilmonats.  <br/> |
|GroupType  <br/> |Die Gruppenart (privat/öffentlich/beliebig).  <br/> |
|TotalGroups  <br/> |Die Anzahl der Gruppen in jeder Gruppenart.  <br/> |
|ActiveGroups  <br/> |Die Anzahl aktiver Gruppen.  <br/> |
|MBX_TotalGroups  <br/> |Die Anzahl von Postfach-Gruppen.  <br/> |
|MBX_ActiveGroups  <br/> |Die Anzahl der aktiven Postfach-Gruppen.  <br/> |
|MBX_TotalActivities  <br/> |Die Anzahl der Postfach-Aktivitäten.  <br/> |
|MBX_TotalItems  <br/> |Die Anzahl von Postfach-Elementen.  <br/> |
|MBX_StorageUsed  <br/> |Verwendeter Postfachspeicherplatz.  <br/> |
|SPO_TotalGroups  <br/> |Die Anzahl der SharePoint-Gruppen.  <br/> |
|SPO_ActiveGroups  <br/> |Die Anzahl aktiver SharePoint-Gruppen.  <br/> |
|SPO_FileAccessedActiveGroups  <br/> |Die Anzahl der SharePoint-Gruppen, die Aktivitäten mit Dateizugriff aufweisen.  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |Die Anzahl von SharePoint-Gruppen, die Aktivitäten zur Dateisynchronisierung anzeigen.  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |Die Anzahl von SharePoint-Gruppen, die Aktivitäten intern oder mit Gruppen (zu denen auch externe Benutzer gehören können) freigegeben haben.  <br/> |
|SPO_FileSharedExternallyActiveGroups  <br/> |Die Anzahl von SharePoint-Gruppen, die Aktivitäten extern freigegeben haben.  <br/> |
|SPO_TotalActivities  <br/> |Die Anzahl der SharePoint-Aktivitäten.  <br/> |
|SPO_FileAccessedActivities  <br/> |Die Anzahl der Aktivitäten, bei denen auf eine SharePoint-Datei zugegriffen wurde.  <br/> |
|SPO_FileSyncedActivities  <br/> |Die Anzahl der mit SharePoint-Aktivitäten, bei denen Dateien synchronisiert wurden.  <br/> |
|SPO_FileSharedInternallyActivities  <br/> |Die Anzahl der SharePoint-Aktivitäten, bei denen Dateien intern oder mit Gruppen (zu denen auch externe Mitglieder gehören können) freigegeben wurden.  <br/> |
|SPO_FileSharedExternallyActivities  <br/> |Die Anzahl der SharePoint-Aktivitäten, bei denen Dateien extern freigegeben wurden.  <br/> |
|SPO_TotalFiles  <br/> |Die Anzahl der SharePoint-Dateien.  <br/> |
|SPO_ActiveFiles  <br/> |Die Anzahl aktiver SharePoint-Dateien.  <br/> |
|SPO_StorageUsed  <br/> |Verwendeter Speicher in SharePoint.  <br/> |
|YAM_TotalGroups  <br/> |Die Anzahl von Yammer-Gruppen.  <br/> |
|YAM_ActiveGroups  <br/> |Die Anzahl aktiver Yammer-Gruppen.  <br/> |
|YAM_LikedActiveGroups  <br/> |Die Anzahl der Yammer-Gruppen, die "Like" Aktivitäten enthalten.  <br/> |
|YAM_PostedActiveGroups  <br/> |Die Anzahl der Yammer-Gruppen, die „Posten“ Aktivitäten enthalten.  <br/> |
|YAM_ReadActiveGroups  <br/> |Die Anzahl der Yammer-Gruppen, die „Gelesene" Aktivitäten enthalten.  <br/> |
|YAM_TotalActivities  <br/> |Die Anzahl der Yammer-Aktivitäten.  <br/> |
|YAM_LikedActivities  <br/> |Die Anzahl der Yammer „Like“ Aktivitäten.  <br/> |
|YAM_PostedActivties  <br/> |Die Anzahl der Yammer „Posten“ Aktivitäten.  <br/> |
|YAM_ReadActivites  <br/> |Die Anzahl der Yammer „Gelesene“ Aktivitäten.  <br/> |
   
### <a name="data-table---tenant-office-activation"></a>Datentabelle – Tenant Office Activation

Die Tabelle enthält Daten zur Anzahl der Office-Abonnement Aktivierungen in den Dienstplänen, beispielsweise Microsoft 365-Apps für Unternehmen, Visio, Project. Außerdem werden Daten zur Anzahl der Aktivierungen pro Gerät (Android/IOS/Mac/PC) bereitgestellt.
  
|**Spaltenname**|**Spaltenbeschreibung**|
|:-----|:-----|
|ServicePlanName  <br/> |Liste der Werte für den Serviceplannamen und Anzahl der Aktivierungen nach Geräten, wie es in den folgenden Spalten dargestellt ist.  <br/> |
|TotalEnabled  <br/> |Die Anzahl der aktivierten Benutzer pro Serviceplanname am Ende des Zeitrahmens.  <br/> |
|TotalActivatedUsers  <br/> |Die Anzahl der Benutzer, die die einzelnen Servicepläne am Ende des Zeitrahmens aktiviert haben.  <br/> |
|AndroidCount  <br/> |Die Anzahl von Aktivierungen pro Serviceplan für Android-Geräte am Ende des Zeitrahmens.  <br/> |
|iOSCount  <br/> |Die Anzahl von Aktivierungen pro Serviceplan für iOS-Geräte am Ende des Zeitrahmens.  <br/> |
|MacCount  <br/> |Die Anzahl von Aktivierungen pro Serviceplan für MAC-Geräte am Ende des Zeitrahmens.  <br/> |
|PcCount  <br/> |Die Anzahl von Aktivierungen pro Serviceplan für PC-Geräte am Ende des Zeitrahmens.  <br/> |
|WinRtCount  <br/> |Die Anzahl von Aktivierungen pro Serviceplan für Windows Mobile-Geräte am Ende des Zeitrahmens.  <br/> |
|Timeframe  <br/> |Diese Spalte enthält den Datumswert. Als n:1-Beziehung für die Tabelle "Kalender" verwendet.  <br/> |
|Content Date  <br/> |Wenn der Zeitrahmen den aktuellen Monat angibt, stellt dieser Wert das neueste Datum des aktuellen Monats dar, für das Daten verfügbar sind.  <br/> Wenn der Zeitrahmen den vorherigen Monat angibt, stellt dieser Wert das letzte Datum des Zeitrahmenmonats dar.  <br/> |
   

