---
title: Microsoft 365 Datenmodell von Nutzungsanalysen
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: 'Erfahren Sie, wie die Verwendungsanalyse eine Verbindung mit einer API herstellt und einen monatlichen Trend der Nutzung verschiedener Microsoft 365 bietet.  '
ms.openlocfilehash: 877ad005e3ff7f7537247963fafcab5fb1ff6c74
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580750"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Microsoft 365 Datenmodell von Nutzungsanalysen

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>Daten für die Microsoft 365 Nutzungsanalysetabellen

Microsoft 365 Verwendungsanalyse stellt eine Verbindung mit einer API bereit, die ein mehrdimensionales Datenmodell verfügbar macht. Die APIs, die Microsoft 365 verwendungsanalyse verwendet werden, um ihre Daten zu generieren, sind aus den verschiedenen, allgemein verfügbaren, Graph APIs. Die Funktion der Microsoft 365-Api für die Verwendungsanalyse ist nicht allgemein verfügbar.
  
> [!NOTE]
> Weitere Informationen finden Sie unter [Working with Microsoft 365 usage reports in Microsoft Graph](/graph/api/resources/report). 
  
Diese API enthält Informationen zum monatlichen Nutzungstrend der verschiedenen Microsoft 365 Dienste. Die genauen von der API zurückgegebenen Daten finden Sie in der Tabelle im folgenden Abschnitt.
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>Von der Berichterstellungs-API Microsoft 365 zurückgegebene Datentabellen

|**Tabellenname**|**Informationen in der Tabelle**|**Datumsbereich**|
|:-----|:-----|:-----|
|Tenant Product Usage  <br/> |Enthält monatliche Summen von aktivierten, aktiven Benutzern, von Monat zu Monat beibehaltenen Benutzern, Erstbenutzern und den kumulierten aktiven Benutzern.  <br/> |Enthält monatliche kumulierte Daten für einen fortlaufenden 12-monatigen Zeitraum einschließlich des aktuellen Teilmonats.  <br/> |
|Tenant Product Activity  <br/> |Enthält monatliche Summen von Aktivitäten und aktive Benutzeranzahl für verschiedene Aktivitäten innerhalb der Produkte.  <br/> Informationen zu den Aktivitäten innerhalb eines Produkts, die in dieser Datentabelle zurückgegeben werden, finden Sie unter [Definition aktiver Benutzer](active-user-in-usage-reports.md).  <br/> |Enthält monatliche kumulierte Daten für einen fortlaufenden 12-monatigen Zeitraum einschließlich des aktuellen Teilmonats.  <br/> |
|Tenant Office Licenses  <br/> |Enthält Daten zur Anzahl von Microsoft Office-Abonnements, die Benutzern zugewiesen sind.  <br/> |Enthält Statusdaten zum Monatsende für einen fortlaufenden Zeitraum von 12 Monaten, einschließlich des aktuellen Teilmonats.  <br/> |
|Tenant Mailbox Usage  <br/> |Enthält Daten zum Postfach des Benutzers, zur Gesamtanzahl der Postfächer und zur Verwendung des Speichers.  <br/> |Enthält Statusdaten zum Monatsende für einen fortlaufenden Zeitraum von 12 Monaten, einschließlich des aktuellen Teilmonats.  <br/> |
|Tenant Client Usage  <br/> |Enthält Daten zur Anzahl der Benutzer, die bestimmte Clients/Geräte aktiv verwenden, um eine Verbindung mit Exchange Online, Skype for Business und Yammer herzustellen.  <br/> |Enthält monatliche kumulierte Daten für einen fortlaufenden 12-monatigen Zeitraum einschließlich des aktuellen Teilmonats.  <br/> |
|Tenant SharePoint Online Usage  <br/> |Enthält Daten zu den SharePoint-Websites, die Team- oder Gruppenwebsites umfassen, z. B. die Gesamtanzahl von Websites, die Anzahl von Dokumenten auf der Website, die Anzahl der Dateien nach Aktivitätstyp und verwendetem Speicherplatz.  <br/> |Enthält Statusdaten zum Monatsende für einen fortlaufenden Zeitraum von 12 Monaten, einschließlich des aktuellen Teilmonats.  <br/> |
|Tenant OneDrive for Business Usage  <br/> |Enthält Daten zu den OneDrive-Konten, z. B. die Anzahl der Konten, die Anzahl der auf OneDrive verteilten Dokumente, der verwendete Speicherplatz oder die Dateianzahl nach Aktivitätstyp.  <br/> |Enthält Statusdaten zum Monatsende für einen fortlaufenden Zeitraum von 12 Monaten, einschließlich des aktuellen Teilmonats.  <br/> |
|Verwendung Microsoft 365 Mandantengruppen  <br/> |Enthält Daten zur Microsoft 365 Gruppennutzung, einschließlich Mailbox, SharePoint und Yammer.  <br/> |Enthält Statusdaten zum Monatsende für einen fortlaufenden Zeitraum von 12 Monaten, einschließlich des aktuellen Teilmonats.  <br/> |
|Tenant Office Activation  <br/> |Enthält Daten über die Anzahl Office Abonnementaktivierungen, die Anzahl der Aktivierungen pro Gerät (Android/iOS/Mac/PC), Aktivierungen nach Dienstplan, z. B. Microsoft 365 Apps for Enterprise, Visio, Project.  <br/> |Enthält Statusdaten zum Monatsende für einen fortlaufenden Zeitraum von 12 Monaten, einschließlich des aktuellen Teilmonats.  <br/> |
|Benutzerstatus  <br/> |Enthält Metadaten zu Benutzern, einschließlich Benutzeranzeigename, zugewiesene Produkte, Standort, Abteilung, Titel, Unternehmen. Bei diesen Daten handelt es sich um Benutzer, denen während des letzten vollständigen Monats eine Lizenz zugewiesen wurde. Jeder Benutzer wird durch eine Benutzer-ID eindeutig dargestellt.  <br/> |Diese Daten beziehen sich auf Benutzer, denen im letzten abgelaufenen Monat eine Lizenz zugewiesen war.  <br/> |
|User Activity  <br/> |Enthält Informationen pro Benutzer zu den von lizenzierten Benutzern ausgeführten Aktivitäten.  <br/> Informationen zu den Aktivitäten innerhalb eines Produkts, die in dieser Datentabelle zurückgegeben werden, finden Sie unter [Definition aktiver Benutzer](active-user-in-usage-reports.md).  <br/> |Diese Daten beziehen sich auf Benutzer, die im letzten abgelaufenen Monat eine Aktivität in einem der Dienste ausgeführt haben.  <br/> |
   
Erweitern Sie die folgenden Abschnitte, um ausführliche Informationen zu jeder Datentabelle anzuzeigen.
  
### <a name="data-table---user-state"></a>Datentabelle – User State

Diese Tabelle enthält Details auf Benutzerebene für alle Benutzer, denen während des letzten vollständigen Monats eine Lizenz zugewiesen wurde. Sie bezieht Daten aus Azure Active Directory ein.
  
|**Spaltenname**|**Spaltenbeschreibung**|
|:-----|:-----|
|UserId  <br/> |Eindeutige Benutzer-ID, die einen Benutzer darstellt und die Verbindung mit anderen Datentabellen innerhalb des Datensets ermöglicht.  <br/> |
|Timeframe  <br/> |Monatswert, für den diese Tabelle Daten enthält.  <br/> |
|UPN  <br/> |Benutzerprinzipalname. Eindeutige Kennzeichnung des Benutzers, der eine Verknüpfung mit anderen externen Datenquellen herstellen kann.  <br/> |
|DisplayName  <br/> |Der Anzeigename des Benutzers.  <br/> |
|IDType  <br/> |DER ID-Typ ist auf 1 festgelegt, wenn der Benutzer ein Yammer-Benutzer ist, der eine Verbindung mit seiner Yammer-ID herstellt, oder 0, wenn er eine Verbindung mit Yammer mithilfe seiner Microsoft 365 herstellt.  <br/> Der Wert ist 1, um zu repräsentieren, dass dieser Benutzer eine Verbindung mit Yammer mit seiner Yammer-ID und nicht mit der Microsoft 365 herstellt  <br/> |
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
|Gelöscht  <br/> |True, wenn der Benutzer in diesem letzten vollständigen Monat Microsoft 365 gelöscht wurde.  <br/> |
|DeletedDate  <br/> |Datum, an dem der Benutzer aus dem Microsoft 365.  <br/> |
|YAM_State  <br/> |Die Zustände des Benutzers im Yammer können aktiv, gelöscht oder angehalten werden.  <br/> |
|YAM_ActivationDate  <br/> |Das Datum, an dem für den Benutzer in Yammer der Status "aktiv" angegeben wurde.  <br/> |
|YAM_DeletionDate  <br/> |Das Datum, an dem für den Benutzer in Yammer der Status "gelöscht" angegeben wurde.  <br/> |
|YAM_SuspensionDate  <br/> |Das Datum, an dem für den Benutzer in Yammer der Status "gesperrt" angegeben wurde.  <br/> |
   
### <a name="data-table---user-activity"></a>Datentabelle – User Activity

Diese Tabelle enthält Daten zu jedem Benutzer, der im vorherigen Monat in einem der Dienste eine Aktivität ausgeführt hat.
  
|**Spaltenname**|**Spaltenbeschreibung**|
|:-----|:-----|
|UserID  <br/> |Eindeutige Benutzer-ID, die einen Benutzer darstellt und die Verbindung mit anderen Datentabellen innerhalb des Datensets ermöglicht.  <br/> |
|IDType  <br/> |DER ID-Typ ist auf 1 festgelegt, wenn der Benutzer ein Yammer-Benutzer ist, der eine Verbindung mit seiner Yammer-ID herstellt, oder 0, wenn er eine Verbindung mit Yammer mithilfe seiner Microsoft 365 herstellt.  <br/> Der Wert ist 1, um zu repräsentieren, dass dieser Benutzer eine Verbindung mit Yammer mit seiner Yammer-ID und nicht mit der Microsoft 365 herstellt  <br/> |
|Timeframe  <br/> |Monatswert, für den diese Tabelle Daten enthält.  <br/> |
|EXO_EmailSent  <br/> |Die Anzahl von gesendeten E-Mails.  <br/> |
|EXO_EmailReceived  <br/> |Die Anzahl von empfangenen E-Mails.  <br/> |
|EXO_EmailRead  <br/> |Die Anzahl der E-Mails, die der Benutzer gelesen hat, es kann mehrere Male sein, eine bereits gelesene E-Mail oder eine zuvor empfangene E-Mail zu lesen.  <br/> |
|EXO_AppointmentCreated  <br/> |Die Anzahl der erstellten Besprechungen.  <br/> |
|EXO_MeetingAccepted  <br/> |Die Anzahl der akzeptierten Besprechungen.  <br/> |
|EXO_MeetingCancelled  <br/> |Anzahl der abgebrochenen Besprechungen.  <br/> |
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
|YAM_MessagePost  <br/> |Anzahl der Yammer, die dieser Benutzer gepostet hat.  <br/> |
|YAM_MessageLiked  <br/> |Anzahl der Yammer, die diesem Benutzer gefallen haben.  <br/> |
|YAM_MessageRead  <br/> |Anzahl der Yammer Nachrichten, die dieser Benutzer gelesen hat.  <br/> |
|SFB_P2PSummary  <br/> |Die Anzahl von Peer-zu-Peer-Sitzungen, an denen dieser Benutzer teilgenommen hat.  <br/> |
|SFB_ConfOrgSummary  <br/> |Die Anzahl von Konferenzsitzungen, die dieser Benutzer organisiert hat.  <br/> |
|SFB_ConfPartSummary  <br/> |Die Anzahl von Konferenzsitzungen, an denen dieser Benutzer teilgenommen hat.  <br/> |

> [!NOTE]
> Teams_HasOtherAction bedeutet, dass der Benutzer als aktiv betrachtet wird, aber einen Nullwert für die Chatnachrichten, 1:1-Anrufe, Kanalnachrichten, Besprechungen insgesamt und Besprechungen hat.
   
### <a name="data-table---tenant-product-usage"></a>Datentabelle – Tenant Product Usage

Diese Tabelle enthält Monatlich-über-Monat-Einführungsdaten in Bezug auf aktivierende, aktive, wiederkehrende und erste Benutzer für jedes Produkt innerhalb Microsoft 365. Die Microsoft 365 stellen die aktive Verwendung in einem der Produkte dar.
  
|**Spaltenname**|**Spaltenbeschreibung**|
|:-----|:-----|
|Produkt  <br/> |Name der Produkte, für die die Informationen zur Nutzung zusammengefasst werden. Microsoft 365 wert in der Produktspalte stellt Die Aktivität in einem der Produkte dar  <br/> |
|Timeframe  <br/> |Monatswert. Es gibt eine Zeile pro Produkt pro Monat für die letzten 12 Monate einschließlich des aktuellen Teilmonats.  <br/> |
|EnabledUsers  <br/> |Die Anzahl der Benutzer, die für die Verwendung des Produkts für den Zeitrahmenwert aktiviert wurden, wenn ein Benutzer für einen Teil des Monats aktiviert wurde, werden weiterhin gezählt.  <br/> |
|ActiveUsers  <br/> |Anzahl der Benutzer, die eine beabsichtigte Aktivität im Produkt für den Zeitrahmenwert ausgeführt haben.  <br/> Ein Benutzer wird für ein Produkt für einen bestimmten Monat als aktiviert gezählt, wenn er eine der Hauptaktivitäten im Produkt ausgeführt hat. Die Hauptaktivitäten sind in der Tabelle **Tenant Product Activity** verfügbar.  <br/> |
|CumulativeActiveUsers  <br/> |Die Anzahl der Benutzer, die zur Verwendung eines Produkts aktiviert sind und das Produkt bis zum Zeitrahmenmonat mindestens einmal seit Beginn der Datensammlung im neuen Verwendungssystem genutzt haben.  <br/> |
|MoMReturningUsers  <br/> |Die Anzahl der Benutzer, die im Zeitrahmenmonat aktiv sind und auch im vorherigen Monat aktiv waren.  <br/> |
|FirstTimeUsers  <br/> |Die Anzahl der Benutzer, die im Zeitrahmen zum ersten Mal seit Beginn der Datensammlung im neuen Verwendungssystem aktiv wurden.  <br/> Ein Benutzer wird in einem bestimmten Monat als erstmaliger Benutzer gezählt, wenn seine Aktivität seit Beginn der Datensammlung in diesem neuen Berichtssystem zum ersten Mal erkannt wurde. Sobald er als Erstbenutzer gezählt wurde, wird er nie wieder als Erstbenutzer gezählt, auch wenn dieser Benutzer eine große Lücke in seinen Aktivitäten hat.  <br/> |
|Content Date  <br/> |Wenn der Zeitrahmen den aktuellen Monat angibt, stellt dieser Wert das neueste Datum des aktuellen Monats dar, für das Daten verfügbar sind.  <br/> Wenn der Zeitrahmen den vorherigen Monat angibt, stellt dieser Wert das letzte Datum des Zeitrahmenmonats dar.  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>Datentabelle – Tenant Product Activity 

Diese Tabelle enthält monatliche Summen der Aktivitäten und die Anzahl aktiver Benutzer für verschiedene Aktivitäten innerhalb der Produkte.
  
|**Spaltenname**|**Spaltenbeschreibung**|
|:-----|:-----|
|Timeframe  <br/> |Monatswert. Es gibt eine Zeile pro Produkt pro Monat für die letzten 12 Monate einschließlich des aktuellen Teilmonats.  <br/> |
|Product  <br/> |Name des Produkts innerhalb Microsoft 365, für das Nutzungsdaten verfügbar sind.  <br/> |
|Activity  <br/> |Name der Aktivität in einem Produkt, die zur Veranschaulichung der aktiven Nutzung des Produkts verwendet wird.  <br/> |
|ActivityCount  <br/> |Dies ist die Gesamtanzahl von Aktionen, die für jede Aktivität gezählt werden, die von allen aktiven Benutzern innerhalb des Produkts ausgeführt wird.  <br/> **Hinweis:** Bei SharePoint Online- und OneDrive for Business-Aktivitäten stellt dieser Wert die Anzahl der verschiedenen Dokumente dar, mit denen Benutzer interagierten.  <br/> |
|ActiveUserCount  <br/> |Die Anzahl der Benutzer, die die Aktivität innerhalb des Produkts ausgeführt haben.  <br/> |
|TotalDurationInMinute  <br/> |Die Dauer in Minuten für alle aktiven Benutzer, die eine Audio- oder Videositzung in einer entsprechenden Skype for Business-Aktivität verwendet haben.  <br/> |
|Content Date  <br/> |Wenn der Zeitrahmen den aktuellen Monat angibt, stellt dieser Wert das neueste Datum des aktuellen Monats dar, für das Daten verfügbar sind.  <br/> Wenn der Zeitrahmen den vorherigen Monat angibt, stellt dieser Wert das letzte Datum des Zeitrahmenmonats dar.  <br/> |
   
### <a name="data-table---tenant-mailbox-usage"></a>Datentabelle – Tenant Mailbox Usage

Diese Tabelle besteht aus Zusammenfassungsdaten für alle lizenzierten Exchange Online, die über ein Benutzerpostfach verfügen. Sie enthält den Monatsendzustand für alle Benutzerpostfächer. Die Daten in dieser Tabelle werden nicht für mehrere Monate zusammengefasst. Die Daten des letzten Monats in dieser Tabelle stellen den aktuellsten Zustand dar.
  
|**Spaltenname**|**Spaltenbeschreibung**|
|:-----|:-----|
|TotalMailboxes  <br/> |Anzahl der Benutzerpostfächer für Microsoft 365 Abonnement.  <br/> |
|IssueWarningQuota  <br/> |Gesamtkontingent für die Ausgabe von Warnmeldungen für alle Benutzerpostfächer.  <br/> |
|ProhibitSendQuota  <br/> |Das Gesamtkontingent für untersagte Sendevorgänge für alle Benutzerpostfächer.  <br/> |
|ProhibitSendReceiveQuota  <br/> |Das Gesamtkontingent für untersagte Sende-/Empfangsvorgänge für alle Benutzerpostfächer.  <br/> |
|TotalItemBytes  <br/> |Die Menge an Speicherplatz in Byte, der für alle Benutzerpostfächer verwendet wird.  <br/> |
|MailboxesNoWarning  <br/> |Die Anzahl der Benutzerpostfächer, die unter dem Limit für Speicherwarnungen geblieben sind.  <br/> |
|MailboxesIssueWarning  <br/> |Die Anzahl der Benutzerpostfächer, für die eine Speicherkontingentwarnung ausgegeben wurde.  <br/> |
|MailboxesExceedSendQuota  <br/> |Die Anzahl der Benutzerpostfächer, die das Kontingent für Sendevorgänge überschritten haben.  <br/> |
|MailboxesExceedSendReceiveQuota  <br/> |Die Anzahl der Benutzerpostfächer, die das Sende-/Empfangskontingent überschritten haben.  <br/> |
|DeletedMailboxes  <br/> |Die Anzahl der Benutzerpostfächer, die im Zeitrahmen gelöscht wurden.  <br/> |
|Timeframe  <br/> |Monatswert.  <br/> |
|Content Date  <br/> |Wenn der Zeitrahmen den aktuellen Monat angibt, stellt dieser Wert das neueste Datum des aktuellen Monats dar, für das Daten verfügbar sind.  <br/> Wenn der Zeitrahmen den vorherigen Monat angibt, stellt dieser Wert das letzte Datum des Zeitrahmenmonats dar.  <br/> |
   
### <a name="data-table---tenant-client-usage"></a>Datentabelle – Tenant Client Usage 

Diese Tabelle enthält monatlich zusammengefasste Daten zu den Clients, die die Benutzer zum Herstellen einer Verbindung mit Exchange Online, Skype for Business und Yammer. In dieser Tabelle sind noch keine Daten zur Clientnutzung für SharePoint Online und OneDrive for Business enthalten.
  
|**Spaltenname**|**Spaltenbeschreibung**|
|:-----|:-----|
|Produkt  <br/> |Name des Produkts innerhalb Microsoft 365, für das Clientverwendungsdaten verfügbar sind.  <br/> |
|ClientId  <br/> |Name des jeweiligen Geräts, mit dem die Verbindung mit dem Produkt hergestellt wurde.  <br/> |
|UserCount  <br/> |Die Anzahl der Benutzer, die den jeweiligen Client für jedes Produkt verwendet haben.  <br/> |
|Timeframe  <br/> |Monatswert.  <br/> |
|Content Date  <br/> |Wenn der Zeitrahmen den aktuellen Monat angibt, stellt dieser Wert das neueste Datum des aktuellen Monats dar, für das Daten verfügbar sind.  <br/> Wenn der Zeitrahmen den vorherigen Monat angibt, stellt dieser Wert das letzte Datum des Zeitrahmenmonats dar.  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>Datentabelle – Tenant SharePoint Online Usage

Diese Tabelle besteht aus Zusammenfassenden Daten von Monat zu Monat über die Verwendung oder Aktivität SharePoint Onlinewebsites. Dies gilt nur für Teamwebsites und Gruppenwebsites. Der End-of-Month-Status von SharePoint Onlinewebsites wird in dieser Spalte dargestellt, wenn ein Benutzer beispielsweise fünf Dokumente erstellt und 10 MB für den Gesamtspeicher verwendet hat, dann einige Dateien gelöscht und weitere Dateien hinzugefügt hat, sodass am Ende des Monats status für Dateien insgesamt sieben sind, die fünf MB Speicher verwenden, der Wert der in dieser Tabelle dargestellten ist Ende des Monatszustands. Diese Tabelle ist ausgeblendet, um eine doppelte Anzahl von Aggregationen zu vermeiden, und wird als Quelle zum Erstellen von zwei Referenztabellen verwendet.
  
|**Spaltenname**|**Spaltenbeschreibung**|
|:-----|:-----|
|SiteType  <br/> |Websitetypwert (any/team/group) ("any" stellt einen dieser beiden Websitetypen dar).  <br/> |
|TotalSites  <br/> |Die Anzahl der Websites, die am Ende des Zeitrahmens vorhanden waren.  <br/> |
|DocumentCount  <br/> |Die Gesamtzahl der Dokumente, die am Ende des Zeitrahmens auf der Website vorhanden waren.  <br/> |
|Diplansed  <br/> |Verwendeter Gesamtspeicherplatz für alle Websites am Ende des Zeitrahmens.  <br/> |
|ActivityType  <br/> |Die Anzahl der Websites, die die verschiedenen Arten von Dateiaktivitäten aufgezeichnet haben (any/active files/files shared EXT/INT/files synched).  <br/> Stellt eine der ausgeführten Dateiaktivitäten dar.  <br/> |
|SitesWithOwnerActivities  <br/> |Die Anzahl aktiver Websites, bei denen der Websitebesitzer eine bestimmte Dateiaktivität auf seinen eigenen Websites ausgeführt hat. Sie können den Websitebesitzer über den PowerShell-Befehl **get-sposite erhalten.** Dies ist die Person, die für die Website verantwortlich ist.   <br/> |
|SitesWithNonOwnerActivities  <br/> |Die Anzahl der für den Monat zusammengefassten aktiven Websites, bei denen andere Benutzer als der Websitebesitzer eine bestimmte Dateiaktivität auf Websites ausgeführt haben. Sie können den Websitebesitzer über den PowerShell-Befehl **get-sposite erhalten.** Dies ist die Person, die für die Website verantwortlich ist. <br/> |
|ActivityTotalSites  <br/> |Die Anzahl der Websites, die im Zeitrahmen eine Aktivität aufgezeichnet haben. Eine Website, bei der zu Anfang des Zeitrahmens eine Aktivität aufgetreten ist und die gegen Ende des Zeitrahmens gelöscht wurde, wird dennoch für den Gesamtwert der aktiven Websites für diesen Zeitrahmen gezählt.  <br/> |
|Timeframe  <br/> |Diese Spalte enthält den Datumswert. Als n:1-Beziehung für die Tabelle "Kalender" verwendet.  <br/> |
|Content Date  <br/> |Wenn der Zeitrahmen den aktuellen Monat angibt, stellt dieser Wert das neueste Datum des aktuellen Monats dar, für das Daten verfügbar sind.  <br/> Wenn der Zeitrahmen den vorherigen Monat angibt, stellt dieser Wert das letzte Datum des Zeitrahmenmonats dar.  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>Datentabelle – Tenant OnveDrive Usage

Diese Tabelle enthält Daten zu den OneDrive Konten, z. B. Anzahl der Konten, Anzahl der Dokumente OneDrive Konten, verwendeter Speicher, Dateianzahl nach Aktivitätstyp. Der Monatsendzustand OneDrive for Business konten wird in dieser Tabelle dargestellt. Wenn ein Benutzer beispielsweise fünf Dokumente erstellt hat, die 10 MB Speicher verwendet haben, dann einige gelöscht und weitere Dateien hinzugefügt hat, sodass er am Monatsende sieben Dateien mit fünf MB Speicher hat, wird der Monatsendwert in dieser Tabelle am Ende des Monats dargestellt.
  
|**Spaltenname**|**Spaltenbeschreibung**|
|:-----|:-----|
|SiteType  <br/> |Der Wert ist "OneDrive"  <br/> |
|TotalSites  <br/> |Die Anzahl der OneDrive for Business-Konten, die am Ende des Zeitrahmens vorhanden waren.  <br/> |
|DocumentCount  <br/> |Die Gesamtanzahl der Dokumente, die am Ende des Zeitrahmens auf allen OneDrive for Business-Konten vorhanden waren  <br/> |
|Diplansed  <br/> |Insgesamt verwendeter Speicher, der für alle OneDrive am Ende des Zeitrahmens zusammengefasst wurde.  <br/> |
|ActivityType  <br/> |Die Anzahl der Konten, die die verschiedenen Arten von Dateiaktivitäten aufgezeichnet haben (beliebig/aktive Dateien/EXT bzw. INT freigegebene Dateien/synchronisierte Dateien).  <br/> "Any" gibt an, dass eine beliebige Dateiaktivität ausgeführt wurde.  <br/> |
|SitesWithOwnerActivities  <br/> |Die Anzahl aktiver OneDrive for Business-Konten, bei denen der Kontobesitzer eine bestimmte Dateiaktivität im eigenen Konto durchgeführt hat.  <br/> |
|SitesWithNonOwnerActivities  <br/> |Die Anzahl von OneDrive for Business-Konten, bei denen die Dateiaktivität von einem anderen Benutzer als dem Kontobesitzer durchgeführt wurde.  <br/> |
|ActivityTotalSites  <br/> |Die Anzahl der OneDrive for Business-Konten, die im Zeitrahmen eine Aktivität aufgezeichnet haben. Ein OneDrive for Business-Konto, bei dem zu Anfang des Zeitrahmens eine Aktivität aufgetreten ist und das gegen Ende des Zeitrahmens gelöscht wurde, wird dennoch als aktives OneDrive for Business-Konto für diesen Zeitrahmen gezählt.  <br/> |
|Timeframe  <br/> |Diese Spalte enthält den Datumswert. Als n:1-Beziehung für die Tabelle "Kalender" verwendet.  <br/> |
|Content Date  <br/> |Wenn der Zeitrahmen den aktuellen Monat angibt, stellt dieser Wert das neueste Datum des aktuellen Monats dar, für das Daten verfügbar sind.  <br/> Wenn der Zeitrahmen den vorherigen Monat angibt, stellt dieser Wert das letzte Datum des Zeitrahmenmonats dar.  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>Datentabelle – Verwendung Microsoft 365 Mandantengruppen

Diese Tabelle enthält Daten darüber, Microsoft 365 Gruppen in der gesamten Organisation verwendet werden.
  
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
|SPO_FileAccessedActiveGroups  <br/> |Die Anzahl SharePoint Gruppen, auf die auf Dateien zugegriffen wird.  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |Die Anzahl SharePoint Gruppen, die über dateisynchrone Aktivitäten verfügen.  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |Anzahl der SharePoint gruppen, die intern oder mit Gruppen (die externe Benutzer enthalten können) freigegebene Aktivitäten haben.  <br/> |
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

Die Tabelle enthält Daten zur Anzahl Office Abonnementaktivierungen in den Dienstplänen, z. B. Microsoft 365 Apps für Unternehmen, Visio, Project. Außerdem werden Daten zur Anzahl der Aktivierungen pro Gerät (Android/iOS/Mac/PC) zur Verfügung stellen.
  
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
