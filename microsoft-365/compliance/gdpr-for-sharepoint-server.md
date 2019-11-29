---
title: DSGVO für SharePoint Server
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: Erfahren Sie, wie Sie mit DSGVO-Anforderungen in lokalen SharePoint Servern umgehen.
ms.openlocfilehash: dba20f2f85bc9a474b39e427ed2628a2f9c9f437
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "39625386"
---
# <a name="gdpr-for-sharepoint-server"></a>DSGVO für SharePoint Server

Gilt für:
- SharePoint Server 2013
- SharePoint Server 2016
- SharePoint Server 2019

Im Rahmen des Schutzes persönlicher Informationen empfehlen wir Folgendes:

-   Klassifizieren Ihrer Daten mithilfe von Azure Information Protection.

-   SharePoint Server in einer Konfiguration mit der geringsten Konfiguration ausführen. Siehe [Planen der geringsten Berechtigungen in SharePoint Server](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/plan-for-least-privileged-administration) und [Security für SharePoint Server](https://docs.microsoft.com/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server) für weitere Informationen.

-   [Aktivieren Sie die BitLocker-Verschlüsselung auf den Servern](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-how-to-deploy-on-windows-server).

## <a name="user-generated-content"></a>Durch Benutzer erstellte Inhalte

Der empfohlene grundlegende Ansatz für die von Benutzern erstellten Inhalte auf Websites und in Bibliotheken von SharePoint Server lautet:

-   Verwenden Sie Azure Information Protection, um vertrauliche Daten zu beschriften.

-   Verwenden Sie die [SharePoint Server-Suche](https://docs.microsoft.com/SharePoint/search/search) und [eDiscovery](https://docs.microsoft.com/SharePoint/governance/ediscovery-and-in-place-holds-in-sharepoint-server), um vertrauliche Daten abzurufen.

Die empfohlene Vorgehensweise für  Dateifreigaben, Websites und Bibliotheken von SharePoint und umfasst die folgenden Schritte:

1.  **[Installieren und konfigurieren Sie den Azure Information Protection-Scanner.](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide-install#options-to-install-the-azure-information-protection-client-for-users)**

    -   Entscheiden Sie, welche vertraulichen Datentypen Sie verwenden möchten.

    -   Geben Sie an, welche SharePoint-Websites verwendet werden sollen.

2.  **Führen Sie einen Suchzyklus durch.**

    -   Führen Sie den Scanner im Suchmodus aus und überprüfen Sie die Ergebnisse.

    -   Falls erforderlich, optimieren Sie die Bedingungen und vertraulichen Datentypen.

    -   Bewerten Sie die erwarteten Auswirkungen einer automatischen Anwendung von Beschriftungen.

3.  **Führen Sie den Azure Information Protection-Scanner aus, um Beschriftungen für berechtigende Dokumente anzuwenden**.

4.  **Zum Schutz:**

    a. Konfigurieren Sie Regeln zum Schutz vor Datenverlust in Exchange, um Dokumente mit der gewünschten Beschriftung zu schützen.

    b. Beschränken Sie mithilfe von Berechtigungen, wer auf Dateien zugreifen kann.

    c. Verwenden Sie für SharePoint IRM-Schutz für Bibliotheken.

5.  **Integrieren Sie zur Überwachung Windows Server-Protokolle mit einem SIEM-Tool.**

    a. Verwenden Sie Search Center oder eDiscovery, um personenbezogene Daten für Anfragen betroffener Personen zu finden.

Verwenden Sie zur Beschriftung vertraulicher Daten nur Beschriftungen ohne Schutz. Ein Schutz schließt eine Verschlüsselung ein, die verhindert, dass vertrauliche Daten von Diensten in den Dateien gefunden werden können.

Weitere Informationen über die Verwendung des Azure Information Protection-Scanners zum Suchen und Beschriften von personenbezogenen Daten finden Sie im [Microsoft GDPR Data Discovery Toolkit](https://aka.ms/gdprpartners) (https://aka.ms/gdprpartners)).

Informationen über die Konfiguration des Scanners für Bedingungen und die Verwendung der vertraulichen Datentypen für die Verhinderung von Datenverlust in Office 365 finden Sie unter [So konfigurieren Sie Bedingungen für die automatische und empfohlene Klassifizierung von Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Beachten Sie, dass neue vertrauliche Datentypen in Office 365 nicht sofort für die Verwendung mit dem Scanner zur Verfügung stehen und dass benutzerdefinierte vertrauliche Datentypen nicht mit dem Scanner verwendet werden können.

## <a name="removing-personal-information-from-office-files"></a>Entfernen personenbezogener Daten aus Office-Dateien

Das Entfernen von personenbezogenen Daten (z. B. Metadaten oder Kommentare in einem Word-Dokument) aus Office-Dateien, die sich in einer SharePoint-Dokumentbibliothek muss manuell erfolgen. Gehen Sie folgendermaßen vor:

1.  Laden Sie eine Kopie des Dokuments aus SharePoint Server auf Ihren lokalen Datenträger herunter.

2.  Löschen Sie das Dokument aus der SharePoint-Dokumentbibliothek.

3.  Führen Sie die unter [Entfernen von ausgeblendeten Daten und personenbezogenen Daten durch Prüfen von Dokumenten](https://support.office.com/article/356B7B5D-77AF-44FE-A07F-9AA4D085966F) beschriebenen Schritte aus.

4.  Laden Sie das Dokument erneut in die SharePoint-Dokumentbibliothek hoch.

## <a name="telemetry-and-log-files"></a>Telemetrie und Protokolldateien

### <a name="uls-logs"></a>ULS-Protokolle

Unified Logging Service (ULS) und die Verwendungsprotokollierung in SharePoint Server zeichnen verschiedene Systemfunktionen auf und sammeln somit möglicherweise auch Benutzerinformationen. ULS-Protokolle und Verwendungsprotokolle sind Textdateien und können mit einer Vielzahl von Suchwerkzeugen durchsucht werden. Mit dem [PowerShell-Cmdlet Merge-SPLogFile](https://docs.microsoft.com/powershell/module/sharepoint-server/merge-splogfile) können Datensätze aus den ULS-Protokollen auf mehreren Servern einer Farm ausfindig gemacht werden.

Ziehen Sie es in Erwägung, die Aufbewahrungsrichtlinien für Protokolle auf das für Ihr Unternehmen erforderliche Mindestmaß zu beschränken. Informationen zum Konfigurieren der Protokollierung in SharePoint Server finden Sie unter [Konfigurieren der Diagnoseprotokollierung in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).

Beachten Sie, dass einige Systemereignisse auch im Windows-Ereignisprotokoll festgehalten werden.

### <a name="usage-database"></a>Verwendungsdatenbank

Die Verwendungsdatenbank von SharePoint Server (Standardname WSS_Logging) enthält eine Teilmenge der Informationen aus den ULS-Protokollen. Die maximale Aufbewahrungszeit für Daten in dieser Datenbank beträgt 30 Tage. Es wird empfohlen, dass Sie diese Einstellung auf das für Ihr Unternehmen erforderliche Mindestmaß konfigurieren. Weitere Informationen finden Sie unter [Konfigurieren der Diagnoseprotokollierung in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).

## <a name="personal-information-and-search"></a>Personenbezogene Daten und Suche

Im Verlauf der Suchanfragen und in den Verwendungsprotokollen wird auf Benutzernamen Bezug genommen.

### <a name="query-history-and-favorite-queries"></a>Verlauf der Suchabfragen und häufigste Abfragen

In SharePoint Server werden die Verläufe der Suchabfragen und die am häufigsten genutzten Abfragen automatisch nach 365 Tagen gelöscht. Wenn ein Benutzer das Unternehmen verlässt, ist es möglich, Verweise auf den Benutzernamen aus dem Verlauf der Suchabfragen zu entfernen, indem die folgenden Schritte ausgeführt werden.

Die folgenden SQL-Abfragen gelten für SharePoint Server und ermöglichen folgendes:

-   Exportieren des Verlaufs der Suchabfragen und der am häufigsten genutzten Abfragen eines Benutzers

-   Entfernen von Verweisen auf Benutzernamen aus dem Verlauf der Suchabfragen

#### <a name="export-a-users-queries-since-a-specific-date"></a>Exportieren aller Abfragen eines Benutzers ab einem bestimmten Datum 

Mit dem folgenden Verfahren können Sie Abfragen aus den Protokolltabellen in Links Store exportieren, die von @Benutzername seit @Startzeitpunkt ausgeführt wurden.

```sql
[In dbo].[LinkStore_<ID>]:
CREATE PROCEDURE proc_MSS_GetQueryTermsForUser 
( 
    @UserName nvarchar(256), 
    @StartTime datetime 
) 
AS 
BEGIN 
    SET NOCOUNT ON; 
    SELECT searchTime, queryString 
    FROM 
        dbo.MSSQLogPageImpressionQuery 
    WITH 
        (NOLOCK) 
    WHERE 
        userName = @UserName AND 
        searchTime > @StartTime 
END 
GO 
```

#### <a name="export-a-users-queries-from-the-past-100-days"></a>Exportieren der Abfragen eines Benutzers für die letzten 100 Tage

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetQueryTermsForUser '0#.w|domain\username', @FROMDATE 
```

#### <a name="export-a-users-favorite-queries"></a>Exportieren der am häufigsten genutzten Abfragen eines Benutzers

Mit dem folgenden Verfahren können Sie die am häufigsten genutzten Abfragen eines Benutzers aus den Tabellen der persönlichen Suchergebnisse in der Search Admin-Datenbank exportieren, die von @Benutzername seit <DateTime> ausgeführt wurden.

```sql
In [dbo].[Search_<ID>]:
CREATE PROCEDURE proc_MSS_GetPersonalFavoriteQueries 
( 
    @UserName nvarchar(256), 
    @SearchTime datetime 
) 
AS 
BEGIN 
    SET NOCOUNT ON; 
    SELECT max(queries.SearchTime) as SearchTime, 
           max(queries.querystring) as queryString, 
           max(url.url) as URL 
    FROM MSSQLogOwner owners WITH(NOLOCK) 
    JOIN MSSQLogPersonalResults results WITH(NOLOCK) on owners.OwnerId = results.OwnerId 
    JOIN MSSQLogUrl url WITH(NOLOCK) on results.ClickedUrlId = url.urlId 
    JOIN MSSQLogPersonalQueries queries WITH(NOLOCK) on results.OwnerId = queries.OwnerId 
    WHERE queries.SearchTime > @SearchTime 
        AND queries.UserName = @UserName 
        GROUP BY queries.QueryString,url.url 
END 
GO 
```

#### <a name="export-a-users-favorite-queries-from-the-past-100-days"></a>Exportieren der am häufigsten genutzten Abfragen eines Benutzers für die letzten 100 Tage 

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetPersonalFavoriteQueries '0#.w|domain\username', @FROMDATE 
```

#### <a name="remove-references-to-user-names-that-are-more-than-x-days-old"></a>Entfernen von Verweisen auf Benutzernamen, die älter als X Tage sind

Mit dem folgenden Verfahren können Sie Verweise, die älter als @Tage sind, in Bezug auf *alle* Benutzernamen aus den Protokolltabellen in Links Store entfernen. Durch dieses Verfahren werden Verweise in umgekehrt chronologischer Reihenfolge entfernt, bis der @ZeitpunktDerLetztenBereinigung erreicht ist.

```sql
In [dbo].[LinksStore_<ID>]:  
CREATE PROCEDURE proc_MSS_QLog_Cleanup_Users 
( 
    @LastCleanupTime datetime, 
    @Days int 
) 
AS 
BEGIN 
    DECLARE @TooOld datetime 
    SET @TooOld = DATEADD(day, -@Days, GETUTCDATE()) 
    DECLARE @FromLast datetime 
    SET @FromLast = DATEADD(day, -@Days, @LastCleanupTime) 
    BEGIN TRANSACTION 
         UPDATE MSSQLogPageImpressionQuery 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld 
    UPDATE MSSQLogO14PageClick 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld 
    COMMIT TRANSACTION 
END 
GO 
```

#### <a name="remove-references-to-a-specific-user-name-thats-more-than-x-days-old"></a>Entfernen von Verweisen auf einen bestimmten Benutzernamen, die älter als X Tage sind

Mit dem folgenden Verfahren können Sie Verweise, die älter als @Tage sind, in Bezug auf einen *bestimmten* Benutzernamen aus den Protokolltabellen in Links Store entfernen. Durch dieses Verfahren werden Verweise in umgekehrt chronologischer Reihenfolge entfernt, bis der @ZeitpunktDerLetztenBereinigung erreicht ist.

```sql
In [dbo].[LinksStore_<ID>]:
CREATE PROCEDURE proc_MSS_QLog_Cleanup_Users 
( 
    @UserName nvarchar(256),
    @LastCleanupTime datetime, 
    @Days int 
) 
AS 
BEGIN 
    DECLARE @TooOld datetime 
    SET @TooOld = DATEADD(day, -@Days, GETUTCDATE()) 
    DECLARE @FromLast datetime 
    SET @FromLast = DATEADD(day, -@Days, @LastCleanupTime) 
    BEGIN TRANSACTION 
         UPDATE MSSQLogPageImpressionQuery 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld AND userName = @UserName
    UPDATE MSSQLogO14PageClick 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld AND userName = @UserName
    COMMIT TRANSACTION 
END 
GO 
```

#### <a name="remove-references-to-all-user-names-in-the-query-history-from-a-date-and-up-to-the-past-30-days"></a>Entfernen von Verweisen auf alle Benutzernamen Verlauf der Suchabfragen ab einem bestimmten Datum und bis auf die letzten 30 Tage

```sql
EXECUTE proc_MSS_QLog_Cleanup_Users '1-1-2017', 30 
```

### <a name="delete-usage-records"></a>Löschen von Verwendungsprotokollen

In SharePoint Server werden Verwendungsprotokolle nach 3 Jahren automatisch gelöscht. Sie können diese Datensätze mit dem folgenden Verfahren manuell löschen:

So löschen Sie alle die Verwendungsprotokolle, die gelöschten Dokumenten zugeordnet sind 

1.  Stellen Sie sicher, dass das neueste SharePoint-Update installiert ist. 

2.  Starten Sie eine SharePoint-Verwaltungsshell.

3.  Beenden und löschen Sie die Verwendungsanalyse: 

    ```powershell
    $tj = Get-SPTimerJob -Type Microsoft.Office.Server.Search.Analytics.UsageAnalyticsJobDefinition 
    $tj.DisableTimerjobSchedule()
    $tj.StopAnalysis() 
    $tj.ClearAnalysis() 
    $tj.EnableTimerjobSchedule()
    ```

4.  Warten Sie, bis die Analyse erneut gestartet wird (kann bis zu 24 Stunden dauern). 

5.  Bei der nächsten Ausführung der Analyse werden Sicherungskopien aller Datensätze aus der Analytics Reporting-Datenbank erstellt. Bei einer großen Datenbank mit vielen Einträgen kann das Erstellen dieser Sicherungskopie eine Weile dauern.

6.  Warten Sie zehn Tage. Die Analyse wird täglich ausgeführt und Datensätze, die gelöschten Dokumenten zugeordnet sind, werden nach der zehnten Ausführung entfernt. Diese Ausführung dauert länger als normal, wenn viele Datensätze gelöscht werden müssen. 

### <a name="personal-information-and-search-in-sharepoint-server-2010"></a>Personenbezogene Daten und Suche in SharePoint Server 2010

#### <a name="fast-search-server-2010-for-sharepoint"></a>FAST Search Server 2010 for SharePoint 

Zusätzlich zur Speicherung von Dateien im Index, speichert das FAST Search Server 2010-Add-On die Dateien auch in einem temporären Format namens FixML. FiXML-Dateien werden standardmäßig jede Nacht zwischen 3 und 5 Uhr komprimiert. Durch die Komprimierung werden gelöschte Dateien automatisch aus den FiXML-Dateien gelöscht. Um sicherzustellen, dass Informationen zu gelöschten Benutzern oder Dokumenten zeitnah entfernt werden, sollte diese Komprimierung immer aktiviert sein.

### <a name="hybrid-search"></a>Hybridsuche 

Die empfohlenen Aktionen für Lösungen für die Hybridsuche stimmen mit denen für die Suche in SharePoint Server oder SharePoint Online überein. Es gibt zwei Lösungen für die Hybridsuche:

**Die Cloudlösung für Hybridsuche –** Mit der Cloudlösung für die Hybridsuche für SharePoint indizieren Sie alle von Ihnen durchforsteten Inhalte, einschließlich der lokalen Inhalte im Suchindex in Office 365. Wenn Benutzer den Suchindex in Office 365 abfragen, erhalten sie Suchergebnisse aus sowohl lokalen als auch Office 365-Inhalten. Wenn Dokumente aus der SharePoint-Serverumgebung gelöscht werden, werden sie auch aus dem Suchindex in Office 365 gelöscht. [Lesen Sie weitere Informationen zur Cloudlösung für die Hybridsuche](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint) und zur [Interaktion zwischen Suchkomponenten und Datenbanken bei der Cloudhybridsuche](https://docs.microsoft.com/sharepoint/hybrid/plan-cloud-hybrid-search-for-sharepoint), um besser zu verstehen, wie sich die DSGVO auf die Hybridumgebung auswirkt.

**Die hybride Sammelsuche –** Mit der hybriden Sammelsuche verwenden Sie sowohl Ihren Index in SharePoint Server als auch Ihren Index in Office 365. Die beiden Suchdienste SharePoint Server und SharePoint Online können den Suchindex in der jeweils anderen Umgebung abfragen und Sammelergebnisse zurückgeben. Wenn Benutzer in einem Suchcenter suchen, stammen die Suchergebnisse aus dem Suchindex in SharePoint Server und dem Suchindex in Office 365. [Lesen Sie weitere Informationen zur hybriden Sammelsuche](https://docs.microsoft.com/sharepoint/hybrid/learn-about-hybrid-federated-search-for-sharepoint), um besser zu verstehen, wie sich die DSGVO auf die Hybridumgebung auswirkt.

## <a name="on-prem-to-cloud-migrations"></a>Migrationen aus lokalen Installationen in die Cloud

Beim Migrieren von Daten aus SharePoint Server zu SharePoint Online sind manche Daten möglicherweise für einen bestimmten Zeitraum an beiden Speicherorten vorhanden. Wenn Sie Daten löschen müssen, die gerade migriert werden, empfehlen wir, dass Sie zuerst die Migration abschließen, und die Daten aus beiden Speicherorten löschen. Sie können Daten für den Export von beiden Speicherorten abfragen.

## <a name="user-profile-data"></a>Benutzerprofildaten

Der Benutzerprofildienst ermöglicht das Importieren von Profildaten aus einer Vielzahl von externen Quellen. Abfragen und Aktualisierungen solcher Benutzerprofildaten sollten in den Systemen erfolgen, in denen die Daten verwaltet werden. Wenn Sie Updates des externen Systems vornehmen, sollten Sie unbedingt die Benutzerprofile in SharePoint Server erneut synchronisieren.

Führen Sie die folgenden grundlegenden Schritte aus, um die personenbezogenen Daten eines Benutzers aus dem entsprechenden Benutzerprofil in SharePoint Server zu entfernen:

1.  Entfernen Sie die Benutzerinformationen aus allen externen Systemen, die mit dem SharePoint Server-Benutzerprofil verknüpft sind. Wenn Sie die Verzeichnissynchronisierung verwenden, muss der Benutzer aus der lokalen Active Directory-Umgebung entfernt werden.

2.  Führen Sie eine [Profilsynchronisierung](https://docs.microsoft.com/sharepoint/administration/start-profile-synchronization-manually) in SharePoint Server aus.

3.  Löschen Sie das Profil aus SharePoint Server. Nachdem dies erfolgt ist, wird das Profil innerhalb von 30 Tagen vollständig aus der Benutzerprofildatenbank in SharePoint Server entfernt. Die Profilseite und die persönliche Website des Benutzers werden gelöscht.

Nach dem Löschen des Profils eines Benutzers, sind möglicherweise noch einige eingeschränkte Informationen (z. B. Benutzer-ID) weiterhin in Websitesammlungen vorhanden, die der Benutzer besucht hat. Wenn Sie diese Daten aus einer bestimmten Websitesammlung löschen möchten, können Sie dies mithilfe von CSOM tun. Nachfolgend finden Sie ein Beispielskript:

```powershell
$username = "<admin@company.sharepoint.com>"
$password = "password"
$url = "<https://site.sharepoint.com>"
$securePassword = ConvertTo-SecureString $Password -AsPlainText -Force

# the path here may need to change if you used e.g. C:Lib.
Add-Type -Path "c:\Program Files\Common Files\microsoft shared\Web Server Extensions\16ISAPIMicrosoft.SharePoint.Client.dll"
Add-Type -Path "c:\Program Files\Common Files\microsoft shared\Web Server Extensions\16ISAPIMicrosoft.SharePoint.Client.Runtime.dll"

# connect/authenticate to SharePoint Online and get ClientContext object.
$clientContext = New-Object Microsoft.SharePoint.Client.ClientContext($url)
$credentials = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($username, $securePassword)
$clientContext.Credentials = $credentials
if (!$clientContext.ServerObjectIsNull.Value)
{
    Write-Host "Connected to SharePoint Online site: '$Url'" -ForegroundColor Green
}

# Get user
$user = $clientContext.Web.SiteUsers.GetByLoginName("i:0#.f|membership|user@company.sharepoint.com")

# Redact user
$user.Email = "Redacted"
$user.Title = "Redacted"
$user.Update()
$clientContext.Load($user)
$clientContext.ExecuteQuery()

# Get users
$users = $clientContext.Web.SiteUsers

# Remove user from site
$users.RemoveById($user.Id)
$clientContext.Load($users)
$clientContext.ExecuteQuery()
```
