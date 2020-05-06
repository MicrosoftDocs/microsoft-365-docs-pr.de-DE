---
title: DSGVO für SharePoint Server
description: Erfahren Sie, wie Sie mit Anforderungen der Datenschutz-Grundverordnung (DSGVO) in lokalen SharePoint Server-Instanzen umgehen.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 58ddbe98ec5ca6b08e6d6be58c4258265c13e3de
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036228"
---
# <a name="gdpr-for-sharepoint-server"></a><span data-ttu-id="894a6-103">DSGVO für SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="894a6-103">GDPR for SharePoint Server</span></span>

<span data-ttu-id="894a6-104">Gilt für:</span><span class="sxs-lookup"><span data-stu-id="894a6-104">Applies to:</span></span>
- <span data-ttu-id="894a6-105">SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="894a6-105">SharePoint Server 2013</span></span>
- <span data-ttu-id="894a6-106">SharePoint Server 2016</span><span class="sxs-lookup"><span data-stu-id="894a6-106">SharePoint Server 2016</span></span>
- <span data-ttu-id="894a6-107">SharePoint Server 2019</span><span class="sxs-lookup"><span data-stu-id="894a6-107">SharePoint Server 2019</span></span>

<span data-ttu-id="894a6-108">Im Rahmen des Schutzes persönlicher Informationen empfehlen wir Folgendes:</span><span class="sxs-lookup"><span data-stu-id="894a6-108">As part of safeguarding personal information, we recommend the following:</span></span>

-   <span data-ttu-id="894a6-109">Klassifizieren Ihrer Daten mithilfe von Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="894a6-109">Classify your data, using Azure Information Protection.</span></span>

-   <span data-ttu-id="894a6-p101">SharePoint Server in einer Konfiguration mit der geringsten Konfiguration ausführen. Siehe [Planen der geringsten Berechtigungen in SharePoint Server](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/plan-for-least-privileged-administration) und [Security für SharePoint Server](https://docs.microsoft.com/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server) für weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="894a6-p101">Run SharePoint Server in a least-privileged configuration. See [Plan for least-privileged administration in SharePoint Server](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/plan-for-least-privileged-administration) and [Security for SharePoint Server](https://docs.microsoft.com/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server) for more information.</span></span>

-   <span data-ttu-id="894a6-112">[Aktivieren Sie die BitLocker-Verschlüsselung auf den Servern](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-how-to-deploy-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="894a6-112">[Enable BitLocker encryption on your servers](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-how-to-deploy-on-windows-server).</span></span>

## <a name="user-generated-content"></a><span data-ttu-id="894a6-113">Durch Benutzer erstellte Inhalte</span><span class="sxs-lookup"><span data-stu-id="894a6-113">User Generated content</span></span>

<span data-ttu-id="894a6-114">Der empfohlene grundlegende Ansatz für die von Benutzern erstellten Inhalte auf Websites und in Bibliotheken von SharePoint Server lautet:</span><span class="sxs-lookup"><span data-stu-id="894a6-114">The basic recommended approach for user generated content contained in SharePoint Server sites and libraries is:</span></span>

-   <span data-ttu-id="894a6-115">Verwenden Sie Azure Information Protection, um vertrauliche Daten zu beschriften.</span><span class="sxs-lookup"><span data-stu-id="894a6-115">Use Azure Information Protection to label sensitive data.</span></span>

-   <span data-ttu-id="894a6-116">Verwenden Sie die [SharePoint Server-Suche](https://docs.microsoft.com/SharePoint/search/search) und [eDiscovery](https://docs.microsoft.com/SharePoint/governance/ediscovery-and-in-place-holds-in-sharepoint-server), um vertrauliche Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="894a6-116">Use [SharePoint Server search](https://docs.microsoft.com/SharePoint/search/search) and [eDiscovery](https://docs.microsoft.com/SharePoint/governance/ediscovery-and-in-place-holds-in-sharepoint-server) to retrieve sensitive data.</span></span>

<span data-ttu-id="894a6-117">Die empfohlene Vorgehensweise für  Dateifreigaben, Websites und Bibliotheken von SharePoint und umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="894a6-117">The recommended approach for files shares and SharePoint sites and libraries includes these steps:</span></span>

1.  <span data-ttu-id="894a6-118">**[Installieren und konfigurieren Sie den Azure Information Protection-Scanner.](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide-install#options-to-install-the-azure-information-protection-client-for-users)**</span><span class="sxs-lookup"><span data-stu-id="894a6-118">**[Install and configure Azure Information Protection scanner.](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide-install#options-to-install-the-azure-information-protection-client-for-users)**</span></span>

    -   <span data-ttu-id="894a6-119">Entscheiden Sie, welche vertraulichen Datentypen Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="894a6-119">Decide which sensitive data types to use.</span></span>

    -   <span data-ttu-id="894a6-120">Geben Sie an, welche SharePoint-Websites verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="894a6-120">Specify which SharePoint sites to use.</span></span>

2.  <span data-ttu-id="894a6-121">**Führen Sie einen Suchzyklus durch.**</span><span class="sxs-lookup"><span data-stu-id="894a6-121">**Complete a discovery cycle.**</span></span>

    -   <span data-ttu-id="894a6-122">Führen Sie den Scanner im Suchmodus aus und überprüfen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="894a6-122">Run the scanner in discovery mode and validate the findings.</span></span>

    -   <span data-ttu-id="894a6-123">Falls erforderlich, optimieren Sie die Bedingungen und vertraulichen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="894a6-123">If needed, optimize the conditions and sensitive information types.</span></span>

    -   <span data-ttu-id="894a6-124">Bewerten Sie die erwarteten Auswirkungen einer automatischen Anwendung von Beschriftungen.</span><span class="sxs-lookup"><span data-stu-id="894a6-124">Assess the expected impact of automatically applying labels.</span></span>

3.  <span data-ttu-id="894a6-125">**Führen Sie den Azure Information Protection-Scanner aus, um Beschriftungen für berechtigende Dokumente anzuwenden**.</span><span class="sxs-lookup"><span data-stu-id="894a6-125">**Run the Azure Information Protection scanner to apply labels to qualifying documents**.</span></span>

4.  <span data-ttu-id="894a6-126">**Zum Schutz:**</span><span class="sxs-lookup"><span data-stu-id="894a6-126">**For protection:**</span></span>

    <span data-ttu-id="894a6-p102">a. Konfigurieren Sie Regeln zum Schutz vor Datenverlust in Exchange, um Dokumente mit der gewünschten Beschriftung zu schützen.</span><span class="sxs-lookup"><span data-stu-id="894a6-p102">a.  Configure Exchange data loss prevention rules to protect documents with the desired label.</span></span>

    <span data-ttu-id="894a6-p103">b. Beschränken Sie mithilfe von Berechtigungen, wer auf Dateien zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="894a6-p103">b.  Be sure permissions to limit who can access files.</span></span>

    <span data-ttu-id="894a6-p104">c. Verwenden Sie für SharePoint IRM-Schutz für Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="894a6-p104">c.  For SharePoint, use IRM-protection for libraries.</span></span>

5.  <span data-ttu-id="894a6-133">**Integrieren Sie zur Überwachung Windows Server-Protokolle mit einem SIEM-Tool.**</span><span class="sxs-lookup"><span data-stu-id="894a6-133">**For monitoring, integrate Windows Server logs with a SIEM tool.**</span></span>

    <span data-ttu-id="894a6-p105">a. Verwenden Sie Search Center oder eDiscovery, um personenbezogene Daten für Anfragen betroffener Personen zu finden.</span><span class="sxs-lookup"><span data-stu-id="894a6-p105">a.  To find personal data for data subject requests, use Search Center or eDiscovery.</span></span>

<span data-ttu-id="894a6-p106">Verwenden Sie zur Beschriftung vertraulicher Daten nur Beschriftungen ohne Schutz. Ein Schutz schließt eine Verschlüsselung ein, die verhindert, dass vertrauliche Daten von Diensten in den Dateien gefunden werden können.</span><span class="sxs-lookup"><span data-stu-id="894a6-p106">When applying labels to sensitive data, be sure to use a label that is not configured with protection. Protection includes encryption which prevents services from detecting sensitive data in the files.</span></span>

<span data-ttu-id="894a6-138">Weitere Informationen über die Verwendung des Azure Information Protection-Scanners zum Suchen und Beschriften von personenbezogenen Daten finden Sie im [Microsoft GDPR Data Discovery Toolkit](https://aka.ms/gdprpartners) (https://aka.ms/gdprpartners)).</span><span class="sxs-lookup"><span data-stu-id="894a6-138">For more information on using Azure Information Protection scanner to find and label personal data, see the [Microsoft GDPR Data Discovery Toolkit](https://aka.ms/gdprpartners) (https://aka.ms/gdprpartners).</span></span>

<span data-ttu-id="894a6-p107">Informationen über die Konfiguration des Scanners für Bedingungen und die Verwendung der vertraulichen Datentypen für die Verhinderung von Datenverlust in Office 365 finden Sie unter [So konfigurieren Sie Bedingungen für die automatische und empfohlene Klassifizierung von Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Beachten Sie, dass neue vertrauliche Datentypen in Office 365 nicht sofort für die Verwendung mit dem Scanner zur Verfügung stehen und dass benutzerdefinierte vertrauliche Datentypen nicht mit dem Scanner verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="894a6-p107">For information on configuring the scanner for conditions and using the Office 365 data loss prevention (DLP) sensitive information types, see [How to configure conditions for automatic and recommended classification for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Note that new Office 365 sensitive information types will not be immediately available to use with the scanner and custom sensitive information types cannot be used with the scanner.</span></span>

## <a name="removing-personal-information-from-office-files"></a><span data-ttu-id="894a6-141">Entfernen personenbezogener Daten aus Office-Dateien</span><span class="sxs-lookup"><span data-stu-id="894a6-141">Removing personal information from Office files</span></span>

<span data-ttu-id="894a6-p108">Das Entfernen von personenbezogenen Daten (z. B. Metadaten oder Kommentare in einem Word-Dokument) aus Office-Dateien, die sich in einer SharePoint-Dokumentbibliothek muss manuell erfolgen. Gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="894a6-p108">Removing personal information (such as metadata or comments in a Word document) from Office files that are stored in a SharePoint document library must be done manually. Follow these steps:</span></span>

1.  <span data-ttu-id="894a6-144">Laden Sie eine Kopie des Dokuments aus SharePoint Server auf Ihren lokalen Datenträger herunter.</span><span class="sxs-lookup"><span data-stu-id="894a6-144">Download a copy of the document from SharePoint Server to your local disk.</span></span>

2.  <span data-ttu-id="894a6-145">Löschen Sie das Dokument aus der SharePoint-Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="894a6-145">Delete the document from the SharePoint document library.</span></span>

3.  <span data-ttu-id="894a6-146">Führen Sie die unter [Entfernen von ausgeblendeten Daten und personenbezogenen Daten durch Prüfen von Dokumenten](https://support.office.com/article/356B7B5D-77AF-44FE-A07F-9AA4D085966F) beschriebenen Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="894a6-146">Follow the steps in [Remove hidden data and personal information by inspecting documents](https://support.office.com/article/356B7B5D-77AF-44FE-A07F-9AA4D085966F).</span></span>

4.  <span data-ttu-id="894a6-147">Laden Sie das Dokument erneut in die SharePoint-Dokumentbibliothek hoch.</span><span class="sxs-lookup"><span data-stu-id="894a6-147">Upload the document back to the SharePoint document library.</span></span>

## <a name="telemetry-and-log-files"></a><span data-ttu-id="894a6-148">Telemetrie und Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="894a6-148">Telemetry and log files</span></span>

### <a name="uls-logs"></a><span data-ttu-id="894a6-149">ULS-Protokolle</span><span class="sxs-lookup"><span data-stu-id="894a6-149">ULS Logs</span></span>

<span data-ttu-id="894a6-p109">Unified Logging Service (ULS) und die Verwendungsprotokollierung in SharePoint Server zeichnen verschiedene Systemfunktionen auf und sammeln somit möglicherweise auch Benutzerinformationen. ULS-Protokolle und Verwendungsprotokolle sind Textdateien und können mit einer Vielzahl von Suchwerkzeugen durchsucht werden. Mit dem [PowerShell-Cmdlet Merge-SPLogFile](https://docs.microsoft.com/powershell/module/sharepoint-server/merge-splogfile) können Datensätze aus den ULS-Protokollen auf mehreren Servern einer Farm ausfindig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="894a6-p109">Unified Logging Service (ULS) and Usage logging in SharePoint Server track a variety of system functions and can contain user information. ULS logs and usage logs are text files and can be searched using a variety of searching tools. The [Merge-SPLogFile PowerShell cmdlet](https://docs.microsoft.com/powershell/module/sharepoint-server/merge-splogfile) provides a way to return records from the ULS logs on multiple servers in a farm.</span></span>

<span data-ttu-id="894a6-p110">Ziehen Sie es in Erwägung, die Aufbewahrungsrichtlinien für Protokolle auf das für Ihr Unternehmen erforderliche Mindestmaß zu beschränken. Informationen zum Konfigurieren der Protokollierung in SharePoint Server finden Sie unter [Konfigurieren der Diagnoseprotokollierung in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span><span class="sxs-lookup"><span data-stu-id="894a6-p110">Consider setting log retention policies to the minimum value needed for your business purposes. For information about configuring logging in SharePoint Server, see [Configure diagnostic logging in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span></span>

<span data-ttu-id="894a6-155">Beachten Sie, dass einige Systemereignisse auch im Windows-Ereignisprotokoll festgehalten werden.</span><span class="sxs-lookup"><span data-stu-id="894a6-155">Note that some system events are also logged to the Windows Event Log.</span></span>

### <a name="usage-database"></a><span data-ttu-id="894a6-156">Verwendungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="894a6-156">Usage Database</span></span>

<span data-ttu-id="894a6-p111">Die Verwendungsdatenbank von SharePoint Server (Standardname WSS_Logging) enthält eine Teilmenge der Informationen aus den ULS-Protokollen. Die maximale Aufbewahrungszeit für Daten in dieser Datenbank beträgt 30 Tage. Es wird empfohlen, dass Sie diese Einstellung auf das für Ihr Unternehmen erforderliche Mindestmaß konfigurieren. Weitere Informationen finden Sie unter [Konfigurieren der Diagnoseprotokollierung in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span><span class="sxs-lookup"><span data-stu-id="894a6-p111">The SharePoint Server Usage database (default name WSS_Logging) contains a subset of the information found in the ULS logs. The maximum retention of data in this database is 30 days. We recommend that you configure it for the shortest duration allowable by your business needs. For more information, see [Configure diagnostic logging in SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).</span></span>

## <a name="personal-information-and-search"></a><span data-ttu-id="894a6-161">Personenbezogene Daten und Suche</span><span class="sxs-lookup"><span data-stu-id="894a6-161">Personal information and search</span></span>

<span data-ttu-id="894a6-162">Im Verlauf der Suchanfragen und in den Verwendungsprotokollen wird auf Benutzernamen Bezug genommen.</span><span class="sxs-lookup"><span data-stu-id="894a6-162">The search query history and usage records contain references to user names.</span></span>

### <a name="query-history-and-favorite-queries"></a><span data-ttu-id="894a6-163">Verlauf der Suchabfragen und häufigste Abfragen</span><span class="sxs-lookup"><span data-stu-id="894a6-163">Query history and favorite queries</span></span>

<span data-ttu-id="894a6-p112">In SharePoint Server werden die Verläufe der Suchabfragen und die am häufigsten genutzten Abfragen automatisch nach 365 Tagen gelöscht. Wenn ein Benutzer das Unternehmen verlässt, ist es möglich, Verweise auf den Benutzernamen aus dem Verlauf der Suchabfragen zu entfernen, indem die folgenden Schritte ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="894a6-p112">In SharePoint Server, query histories and 'favorite' queries automatically expire after 365 days. If a user leaves your organization, it is possible to remove references to a user's name from the query history using the steps below.</span></span>

<span data-ttu-id="894a6-166">Die folgenden SQL-Abfragen gelten für SharePoint Server und ermöglichen folgendes:</span><span class="sxs-lookup"><span data-stu-id="894a6-166">The following SQL queries apply to SharePoint Server and make it possible to:</span></span>

-   <span data-ttu-id="894a6-167">Exportieren des Verlaufs der Suchabfragen und der am häufigsten genutzten Abfragen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="894a6-167">Export a user's query history or favorite queries</span></span>

-   <span data-ttu-id="894a6-168">Entfernen von Verweisen auf Benutzernamen aus dem Verlauf der Suchabfragen</span><span class="sxs-lookup"><span data-stu-id="894a6-168">Remove references to user names in the query history</span></span>

#### <a name="export-a-users-queries-since-a-specific-date"></a><span data-ttu-id="894a6-169">Exportieren aller Abfragen eines Benutzers ab einem bestimmten Datum</span><span class="sxs-lookup"><span data-stu-id="894a6-169">Export a user's queries since a specific date</span></span> 

<span data-ttu-id="894a6-170">Mit dem folgenden Verfahren können Sie Abfragen aus den Protokolltabellen in Links Store exportieren, die von @Benutzername seit @Startzeitpunkt ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="894a6-170">Use the following procedure to export queries from the Link Store query log tables, performed by @UserName since @StartTime.</span></span>

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

#### <a name="export-a-users-queries-from-the-past-100-days"></a><span data-ttu-id="894a6-171">Exportieren der Abfragen eines Benutzers für die letzten 100 Tage</span><span class="sxs-lookup"><span data-stu-id="894a6-171">Export a user's queries from the past 100 days</span></span>

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetQueryTermsForUser '0#.w|domain\username', @FROMDATE 
```

#### <a name="export-a-users-favorite-queries"></a><span data-ttu-id="894a6-172">Exportieren der am häufigsten genutzten Abfragen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="894a6-172">Export a user's favorite queries</span></span>

<span data-ttu-id="894a6-173">Mit dem folgenden Verfahren können Sie die am häufigsten genutzten Abfragen eines Benutzers aus den Tabellen der persönlichen Suchergebnisse in der Search Admin-Datenbank exportieren, die von @Benutzername seit <DateTime> ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="894a6-173">Use the following procedure to export a user's favorite queries from the Search Admin DB personal result tables, performed by @UserName, since <DateTime>.</span></span>

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

#### <a name="export-a-users-favorite-queries-from-the-past-100-days"></a><span data-ttu-id="894a6-174">Exportieren der am häufigsten genutzten Abfragen eines Benutzers für die letzten 100 Tage</span><span class="sxs-lookup"><span data-stu-id="894a6-174">Export a user's favorite queries from the past 100 days</span></span> 

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetPersonalFavoriteQueries '0#.w|domain\username', @FROMDATE 
```

#### <a name="remove-references-to-user-names-that-are-more-than-x-days-old"></a><span data-ttu-id="894a6-175">Entfernen von Verweisen auf Benutzernamen, die älter als X Tage sind</span><span class="sxs-lookup"><span data-stu-id="894a6-175">Remove references to user names that are more than X days old</span></span>

<span data-ttu-id="894a6-p113">Mit dem folgenden Verfahren können Sie Verweise, die älter als @Tage sind, in Bezug auf *alle* Benutzernamen aus den Protokolltabellen in Links Store entfernen. Durch dieses Verfahren werden Verweise in umgekehrt chronologischer Reihenfolge entfernt, bis der @ZeitpunktDerLetztenBereinigung erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="894a6-p113">Use the following procedure to remove references to *all* user names that are more than @Days old, from the Links Store query log tables. The procedure only removes references backwards in time until it reaches the @LastCleanupTime.</span></span>

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

#### <a name="remove-references-to-a-specific-user-name-thats-more-than-x-days-old"></a><span data-ttu-id="894a6-178">Entfernen von Verweisen auf einen bestimmten Benutzernamen, die älter als X Tage sind</span><span class="sxs-lookup"><span data-stu-id="894a6-178">Remove references to a specific user name that's more than X days old</span></span>

<span data-ttu-id="894a6-p114">Mit dem folgenden Verfahren können Sie Verweise, die älter als @Tage sind, in Bezug auf einen *bestimmten* Benutzernamen aus den Protokolltabellen in Links Store entfernen. Durch dieses Verfahren werden Verweise in umgekehrt chronologischer Reihenfolge entfernt, bis der @ZeitpunktDerLetztenBereinigung erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="894a6-p114">Use the following procedure to remove references to a *specific* user name from the Links Store query log tables, where the references are more than @Days old. The procedure only removes references backwards in time until it reaches the @LastCleanupTime.</span></span>

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

#### <a name="remove-references-to-all-user-names-in-the-query-history-from-a-date-and-up-to-the-past-30-days"></a><span data-ttu-id="894a6-181">Entfernen von Verweisen auf alle Benutzernamen Verlauf der Suchabfragen ab einem bestimmten Datum und bis auf die letzten 30 Tage</span><span class="sxs-lookup"><span data-stu-id="894a6-181">Remove references to all user names in the query history from a date and up to the past 30 days</span></span>

```sql
EXECUTE proc_MSS_QLog_Cleanup_Users '1-1-2017', 30 
```

### <a name="delete-usage-records"></a><span data-ttu-id="894a6-182">Löschen von Verwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="894a6-182">Delete usage records</span></span>

<span data-ttu-id="894a6-p115">In SharePoint Server werden Verwendungsprotokolle nach 3 Jahren automatisch gelöscht. Sie können diese Datensätze mit dem folgenden Verfahren manuell löschen:</span><span class="sxs-lookup"><span data-stu-id="894a6-p115">SharePoint Server automatically deletes usage records after 3 years. You can manually delete such records using the procedure below:</span></span>

<span data-ttu-id="894a6-185">So löschen Sie alle die Verwendungsprotokolle, die gelöschten Dokumenten zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="894a6-185">To delete all usage records associated with deleted documents:</span></span> 

1.  <span data-ttu-id="894a6-186">Stellen Sie sicher, dass das neueste SharePoint-Update installiert ist.</span><span class="sxs-lookup"><span data-stu-id="894a6-186">Ensure that you have the latest SharePoint update installed.</span></span> 

2.  <span data-ttu-id="894a6-187">Starten Sie eine SharePoint-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="894a6-187">Start a SharePoint Management shell.</span></span>

3.  <span data-ttu-id="894a6-188">Beenden und löschen Sie die Verwendungsanalyse:</span><span class="sxs-lookup"><span data-stu-id="894a6-188">Stop and Clear the Usage Analytics analysis:</span></span> 

    ```powershell
    $tj = Get-SPTimerJob -Type Microsoft.Office.Server.Search.Analytics.UsageAnalyticsJobDefinition 
    $tj.DisableTimerjobSchedule()
    $tj.StopAnalysis() 
    $tj.ClearAnalysis() 
    $tj.EnableTimerjobSchedule()
    ```

4.  <span data-ttu-id="894a6-189">Warten Sie, bis die Analyse erneut gestartet wird (kann bis zu 24 Stunden dauern).</span><span class="sxs-lookup"><span data-stu-id="894a6-189">Wait for the analysis to start again (might take up to 24 hours).</span></span> 

5.  <span data-ttu-id="894a6-p116">Bei der nächsten Ausführung der Analyse werden Sicherungskopien aller Datensätze aus der Analytics Reporting-Datenbank erstellt. Bei einer großen Datenbank mit vielen Einträgen kann das Erstellen dieser Sicherungskopie eine Weile dauern.</span><span class="sxs-lookup"><span data-stu-id="894a6-p116">On the next run of the analysis, it will dump all records from the Analytics Reporting database. This full dump may take a while for a large database with many entries.</span></span>

6.  <span data-ttu-id="894a6-p117">Warten Sie zehn Tage. Die Analyse wird täglich ausgeführt und Datensätze, die gelöschten Dokumenten zugeordnet sind, werden nach der zehnten Ausführung entfernt. Diese Ausführung dauert länger als normal, wenn viele Datensätze gelöscht werden müssen.</span><span class="sxs-lookup"><span data-stu-id="894a6-p117">Wait for 10 days. The analysis runs daily, and records associated with deleted documents will be removed after the 10^th^ run. This run may take longer than normal if many records need to be deleted.</span></span> 

### <a name="personal-information-and-search-in-sharepoint-server-2010"></a><span data-ttu-id="894a6-195">Personenbezogene Daten und Suche in SharePoint Server 2010</span><span class="sxs-lookup"><span data-stu-id="894a6-195">Personal information and search in SharePoint Server 2010</span></span>

#### <a name="fast-search-server-2010-for-sharepoint"></a><span data-ttu-id="894a6-196">FAST Search Server 2010 for SharePoint</span><span class="sxs-lookup"><span data-stu-id="894a6-196">FAST Search Server 2010 for SharePoint</span></span> 

<span data-ttu-id="894a6-p118">Zusätzlich zur Speicherung von Dateien im Index, speichert das FAST Search Server 2010-Add-On die Dateien auch in einem temporären Format namens FixML. FiXML-Dateien werden standardmäßig jede Nacht zwischen 3 und 5 Uhr komprimiert. Durch die Komprimierung werden gelöschte Dateien automatisch aus den FiXML-Dateien gelöscht. Um sicherzustellen, dass Informationen zu gelöschten Benutzern oder Dokumenten zeitnah entfernt werden, sollte diese Komprimierung immer aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="894a6-p118">In addition to storing files in the index, the FAST Search Server 2010 Add-On also stores files in an intermediate format called FixML. FiXML files are compacted regularly, by default between 3 am and 5 am every night. Compaction removes deleted files from the FiXML files automatically. To ensure timely removal of information belonging to deleted users or documents, ensure that compaction is always enabled.</span></span>

### <a name="hybrid-search"></a><span data-ttu-id="894a6-201">Hybridsuche</span><span class="sxs-lookup"><span data-stu-id="894a6-201">Hybrid Search</span></span> 

<span data-ttu-id="894a6-p119">Die empfohlenen Aktionen für Lösungen für die Hybridsuche stimmen mit denen für die Suche in SharePoint Server oder SharePoint Online überein. Es gibt zwei Lösungen für die Hybridsuche:</span><span class="sxs-lookup"><span data-stu-id="894a6-p119">The recommended actions for hybrid search solutions are the same as for search in SharePoint Server or SharePoint Online. There are two hybrid search solutions:</span></span>

<span data-ttu-id="894a6-p120">**Die Cloudlösung für Hybridsuche –** Mit der Cloudlösung für die Hybridsuche für SharePoint indizieren Sie alle von Ihnen durchforsteten Inhalte, einschließlich der lokalen Inhalte im Suchindex in Office 365. Wenn Benutzer den Suchindex in Office 365 abfragen, erhalten sie Suchergebnisse aus sowohl lokalen als auch Office 365-Inhalten. Wenn Dokumente aus der SharePoint-Serverumgebung gelöscht werden, werden sie auch aus dem Suchindex in Office 365 gelöscht. [Lesen Sie weitere Informationen zur Cloudlösung für die Hybridsuche](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint) und zur [Interaktion zwischen Suchkomponenten und Datenbanken bei der Cloudhybridsuche](https://docs.microsoft.com/sharepoint/hybrid/plan-cloud-hybrid-search-for-sharepoint), um besser zu verstehen, wie sich die DSGVO auf die Hybridumgebung auswirkt.</span><span class="sxs-lookup"><span data-stu-id="894a6-p120">**The cloud hybrid search solution -** With the cloud hybrid search solution for SharePoint, you index all your crawled content, including on-premises content, in your search index in Office 365. When users query your search index in Office 365, they get search results from both on-premises and Office 365 content. When documents are deleted from the SharePoint Server environment, they are also deleted from the search index in Office 365. [Read more about the cloud hybrid search solution](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint) and [how search components and databases interact in cloud hybrid search](https://docs.microsoft.com/sharepoint/hybrid/plan-cloud-hybrid-search-for-sharepoint) to understand better how GDPR affects the hybrid environment.</span></span>

<span data-ttu-id="894a6-p121">**Die hybride Sammelsuche –** Mit der hybriden Sammelsuche verwenden Sie sowohl Ihren Index in SharePoint Server als auch Ihren Index in Office 365. Die beiden Suchdienste SharePoint Server und SharePoint Online können den Suchindex in der jeweils anderen Umgebung abfragen und Sammelergebnisse zurückgeben. Wenn Benutzer in einem Suchcenter suchen, stammen die Suchergebnisse aus dem Suchindex in SharePoint Server und dem Suchindex in Office 365. [Lesen Sie weitere Informationen zur hybriden Sammelsuche](https://docs.microsoft.com/sharepoint/hybrid/learn-about-hybrid-federated-search-for-sharepoint), um besser zu verstehen, wie sich die DSGVO auf die Hybridumgebung auswirkt.</span><span class="sxs-lookup"><span data-stu-id="894a6-p121">**The hybrid federated search solution -** With the hybrid federated search solution, you use both your index in SharePoint Server and your index in Office 365. Both SharePoint Server and SharePoint Online Search services can query the search index in the other environment and return federated results. When users search from a Search Center, the search results come from both your search index in SharePoint Server and your search index in Office 365. [Read more about the hybrid federated search solution](https://docs.microsoft.com/sharepoint/hybrid/learn-about-hybrid-federated-search-for-sharepoint) to understand better how GDPR affects the hybrid environment.</span></span>

## <a name="on-prem-to-cloud-migrations"></a><span data-ttu-id="894a6-212">Migrationen aus lokalen Installationen in die Cloud</span><span class="sxs-lookup"><span data-stu-id="894a6-212">On Prem to Cloud Migrations</span></span>

<span data-ttu-id="894a6-p122">Beim Migrieren von Daten aus SharePoint Server zu SharePoint Online sind manche Daten möglicherweise für einen bestimmten Zeitraum an beiden Speicherorten vorhanden. Wenn Sie Daten löschen müssen, die gerade migriert werden, empfehlen wir, dass Sie zuerst die Migration abschließen, und die Daten aus beiden Speicherorten löschen. Sie können Daten für den Export von beiden Speicherorten abfragen.</span><span class="sxs-lookup"><span data-stu-id="894a6-p122">While migrating data from SharePoint Server to SharePoint Online, duplicate data may exist in both locations for a time. If you have data that you need to delete that is in mid-migration, we recommend that you complete the migration first, and then delete the data from both locations. You can query data for export from either location.</span></span>

## <a name="user-profile-data"></a><span data-ttu-id="894a6-216">Benutzerprofildaten</span><span class="sxs-lookup"><span data-stu-id="894a6-216">User Profile data</span></span>

<span data-ttu-id="894a6-p123">Der Benutzerprofildienst ermöglicht das Importieren von Profildaten aus einer Vielzahl von externen Quellen. Abfragen und Aktualisierungen solcher Benutzerprofildaten sollten in den Systemen erfolgen, in denen die Daten verwaltet werden. Wenn Sie Updates des externen Systems vornehmen, sollten Sie unbedingt die Benutzerprofile in SharePoint Server erneut synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="894a6-p123">The User Profile Service allows for import of profile data from a variety of external sources. Queries for and update of such user profile data should be handled in the systems in which the data is mastered. If you make updates to the external system, be sure to synchronize the user profiles in SharePoint Server again.</span></span>

<span data-ttu-id="894a6-220">Führen Sie die folgenden grundlegenden Schritte aus, um die personenbezogenen Daten eines Benutzers aus dem entsprechenden Benutzerprofil in SharePoint Server zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="894a6-220">Follow these basic steps to remove a user's personal information from their SharePoint Server user profile:</span></span>

1.  <span data-ttu-id="894a6-p124">Entfernen Sie die Benutzerinformationen aus allen externen Systemen, die mit dem SharePoint Server-Benutzerprofil verknüpft sind. Wenn Sie die Verzeichnissynchronisierung verwenden, muss der Benutzer aus der lokalen Active Directory-Umgebung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="894a6-p124">Remove the user information from any external systems that feed into the SharePoint Server user profile. If you are using directory synchronization, the user must be removed from the on-premises Active Directory environment.</span></span>

2.  <span data-ttu-id="894a6-223">Führen Sie eine [Profilsynchronisierung](https://docs.microsoft.com/sharepoint/administration/start-profile-synchronization-manually) in SharePoint Server aus.</span><span class="sxs-lookup"><span data-stu-id="894a6-223">Run a [profile synchronization](https://docs.microsoft.com/sharepoint/administration/start-profile-synchronization-manually) on SharePoint Server.</span></span>

3.  <span data-ttu-id="894a6-p125">Löschen Sie das Profil aus SharePoint Server. Nachdem dies erfolgt ist, wird das Profil innerhalb von 30 Tagen vollständig aus der Benutzerprofildatenbank in SharePoint Server entfernt. Die Profilseite und die persönliche Website des Benutzers werden gelöscht.</span><span class="sxs-lookup"><span data-stu-id="894a6-p125">Delete the profile from SharePoint Server. Once this is done, SharePoint Server will fully remove the profile from the User Profile Database in 30 days. The user's profile page and personal site will be deleted.</span></span>

<span data-ttu-id="894a6-p126">Nach dem Löschen des Profils eines Benutzers, sind möglicherweise noch einige eingeschränkte Informationen (z. B. Benutzer-ID) weiterhin in Websitesammlungen vorhanden, die der Benutzer besucht hat. Wenn Sie diese Daten aus einer bestimmten Websitesammlung löschen möchten, können Sie dies mithilfe von CSOM tun. Nachfolgend finden Sie ein Beispielskript:</span><span class="sxs-lookup"><span data-stu-id="894a6-p126">After deleting a user's profile, some limited information (such as user ID) may still be recorded in site collections that the user has visited. If you choose to delete this data from a given site collection, this can be done using CSOM. A sample script is provided below:</span></span>

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
