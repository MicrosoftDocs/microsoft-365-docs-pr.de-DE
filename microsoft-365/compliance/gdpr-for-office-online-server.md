---
title: DSGVO für Office Online Server und Office Web Apps Server
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: Erfahren Sie, wie Sie mit DSGVO-Anforderungen in lokalen Exchange Server-Installationen umgehen.
ms.openlocfilehash: b1cf86beeeb195396e45e0bc262f1d1b81b21057
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "38749780"
---
# <a name="gdpr-for-office-web-apps-server-and-office-online-server"></a><span data-ttu-id="452bc-103">DSGVO für Office Web Apps Server und Office Online Server</span><span class="sxs-lookup"><span data-stu-id="452bc-103">GDPR for Office Web Apps Server and Office Online Server</span></span>

<span data-ttu-id="452bc-p101">Telemetriedaten von Office Online Server und Office Web Apps Server werden in Form von ULS-Protokollen gespeichert. Sie können ULS-Protokolle von Ihrem lokalen Mandanten mit [ULS Viewer](https://www.microsoft.com/download/details.aspx?id=44020) anzeigen.</span><span class="sxs-lookup"><span data-stu-id="452bc-p101">Office Online Server and Office Web Apps Server telemetry data is stored in the form of ULS logs. You can use [ULS Viewer](https://www.microsoft.com/download/details.aspx?id=44020) to view ULS logs from your on-premises tenant.</span></span>

<span data-ttu-id="452bc-p102">Jede Protokollzeile enthält eine CorrelationID. Verwandte Protokollzeilen teilen sich die gleiche CorrelationID. Jede CorrelationID ist mit einer einzelnen SessionID verknüpft, und eine SessionID kann mit vielen CorrelationIDs zusammenhängen. Jede SessionID kann mit einer einzelnen UserID verknüpft sein, wobei einige Sitzungen anonym sein können und daher keine zugehörige UserID besitzen. Um zu bestimmen, welche Daten einem bestimmten Benutzer zugeordnet sind, ist es daher möglich, Zuordnungen vorzunehmen von einer einzelnen UserID zu den diesem Benutzer zugeordneten SessionIDs, von diesen SessionIDs zu den zugehörigen CorrelationIDs und von diesen CorrelationIDs zu allen Protokollen in diesen Korrelationen. Im nachstehenden Diagramm sind die Beziehungen zwischen den unterschiedlichen IDs dargestellt.</span><span class="sxs-lookup"><span data-stu-id="452bc-p102">Every log line contains a CorrelationID. Related log lines share the same CorrelationID. Each CorrelationID is tied to a single SessionID, and one SessionID may be related to many CorrelationIDs. Each SessionID may be related to a single UserID, although some sessions can be anonymous and therefore not have an associated UserID. In order to determine what data is associated with a particular user, it is therefore possible to map from a single UserID to the SessionIDs associated with that user, from those SessionIDs to the associated CorrelationIDs, and from those CorrelationIDs to all the logs in those correlations. See the below diagram for the relationship between the different IDs.</span></span>

![](media/gdpr-for-office-online-server-image1.jpg)

## <a name="gathering-logs"></a><span data-ttu-id="452bc-112">Erfassen von Protokollen</span><span class="sxs-lookup"><span data-stu-id="452bc-112">Gathering Logs</span></span>

<span data-ttu-id="452bc-p103">Um alle Protokolle zu erfassen, die beispielsweise UserID 1 zugeordnet sind, müssen zunächst alle Sitzungen erfasst werden, die UserID 1 zugeordnet sind (d. h. SessionID 1 und SessionID 2). Der nächste Schritt wäre das Erfassen aller Korrelationen, die SessionID 1 (d. h. CorrelationIDs 1, 2 und 3) und SessionID 2 (d. h. CorrelationID 4) zugeordnet sind. Zum Schluss müssen alle Protokolle erfasst werden, die den einzelnen Korrelationen in der Liste zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="452bc-p103">In order to gather all logs associated with UserID 1, for example, the first step would be to gather all sessions associated with UserID 1 (i.e. SessionID 1 and SessionID2). The next step would be to gather all correlations associated with SessionID 1 (i.e. CorrelationIDs 1, 2, and 3) and with SessionID 2 (i.e. CorrelationID 4). Finally, gather all logs associated with each of the correlations in the list.</span></span>

1.  <span data-ttu-id="452bc-116">ULS Viewer starten</span><span class="sxs-lookup"><span data-stu-id="452bc-116">Launch UlsViewer</span></span>

2.  <span data-ttu-id="452bc-117">Öffnen Sie das ULS-Protokoll für den gewünschten Zeitrahmen; ULS-Protokolle werden gespeichert unter %PROGRAMDATA%\\Microsoft\\OfficeWebApps\\Data\\Logs\\ULS</span><span class="sxs-lookup"><span data-stu-id="452bc-117">Open up the uls log corresponding to the intended timeframe; ULS logs are stored in %PROGRAMDATA%\\Microsoft\\OfficeWebApps\\Data\\Logs\\ULS</span></span>

3.  <span data-ttu-id="452bc-118">Bearbeiten | Filter ändern</span><span class="sxs-lookup"><span data-stu-id="452bc-118">Edit | Modify Filter</span></span>

4.  <span data-ttu-id="452bc-119">Wenden Sie einen Filter folgender Art an:</span><span class="sxs-lookup"><span data-stu-id="452bc-119">Apply a filter that is:</span></span>

    -   <span data-ttu-id="452bc-120">EventID ist gleich apr3y oder</span><span class="sxs-lookup"><span data-stu-id="452bc-120">EventID equals apr3y Or</span></span>

    -   <span data-ttu-id="452bc-121">EventID ist gleich bp2d6</span><span class="sxs-lookup"><span data-stu-id="452bc-121">EventID equals bp2d6</span></span>

5.  <span data-ttu-id="452bc-122">Gehashte UserIDs werden sich in der Nachricht eines dieser beiden Ereignisse befinden.</span><span class="sxs-lookup"><span data-stu-id="452bc-122">Hashed UserIds will be in the Message of either one of these two events</span></span>

6.  <span data-ttu-id="452bc-123">Für apr3y wird die Nachricht einen Wert "UserID" und einen Wert "PUID" enthalten.</span><span class="sxs-lookup"><span data-stu-id="452bc-123">For apr3y, the Message will contain a UserID value and a PUID value</span></span>

7.  <span data-ttu-id="452bc-p104">Für bp2d6 wird die Nachricht ziemlich viele Informationen enthalten. Das Feld für den Wert "LoggableUserId" enthält die gehashte UserID.</span><span class="sxs-lookup"><span data-stu-id="452bc-p104">For bp2d6, the Message will contain quite a bit of information. The LoggableUserId Value field is the hashed UserID.</span></span>

8.  <span data-ttu-id="452bc-126">Nachdem die gehashte UserID aus einem der beiden Tags abgerufen wurde, enthält der Wert "WacSessionId" dieser Zeile in ULS Viewer die diesem Benutzer zugeordnete WacSessionId.</span><span class="sxs-lookup"><span data-stu-id="452bc-126">Once the hashed UserId is obtained from either of these two tags, the WacSessionId value of that row in ULSViewer will contain the WacSessionId associated with that user</span></span>

9.  <span data-ttu-id="452bc-127">Erfassen Sie alle Werte "WacSessionId" für den betreffenden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="452bc-127">Collect all of the WacSessionId values associated with the user in question</span></span>

10. <span data-ttu-id="452bc-128">Filtern Sie nach allen EventId gleich "xmnv", Nachrichten gleich "UserSessionId =\<WacSessionId\>" für die erste WacSessionId in der Liste (ersetzen Sie den \<WacSessionId\>-Teil des Filters durch Ihre WacSessionId).</span><span class="sxs-lookup"><span data-stu-id="452bc-128">Filter for all EventId equals "xmnv", Message equals "UserSessionId=\<WacSessionId\>" for the first WacSessionId in the list (replacing the \<WacSessionId\> part of the filter with your WacSessionId)</span></span>

11. <span data-ttu-id="452bc-129">Erfassen Sie alle Korrelationswerte, die mit dieser WacSessionId übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="452bc-129">Collect all values of Correlation that match that WacSessionId</span></span>

12. <span data-ttu-id="452bc-130">Wiederholen Sie die Schritte 10 bis 11 für alle Werte "WacSessionId" in der Liste für den betreffenden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="452bc-130">Repeat steps 10-11 for all values of WacSessionId in your list for the user in question</span></span>

13. <span data-ttu-id="452bc-131">Filtern Sie nach allen Korrelationen, die der ersten Korrelation in Ihrer Liste entsprechen.</span><span class="sxs-lookup"><span data-stu-id="452bc-131">Filter for all Correlation equals the first Correlation in your list</span></span>

14. <span data-ttu-id="452bc-132">Erfassen Sie alle Protokolle, die mit dieser Korrelation übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="452bc-132">Collect all logs matching that Correlation</span></span>

15. <span data-ttu-id="452bc-133">Wiederholen Sie die Schritte 13 bis 14 für alle Korrelationswerte in der Liste für den betreffenden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="452bc-133">Repeat steps 13-14 for all values of Correlation in your list for the user in question</span></span>

## <a name="types-of-data"></a><span data-ttu-id="452bc-134">Arten von Daten</span><span class="sxs-lookup"><span data-stu-id="452bc-134">Types of Data</span></span>

<span data-ttu-id="452bc-p105">Office-Protokolle enthalten eine Vielzahl von verschiedenen Arten von Daten. Nachfolgend finden Sie Beispiele für die Daten, die in ULS-Protokollen enthalten sein können:</span><span class="sxs-lookup"><span data-stu-id="452bc-p105">Office Online logs contain a variety of different types of data. The following are examples of the data that ULS logs may contain:</span></span>

-   <span data-ttu-id="452bc-137">Fehlercodes für Probleme, die während der Nutzung des Produkts auftreten</span><span class="sxs-lookup"><span data-stu-id="452bc-137">Error codes for issues encountered during use of the product</span></span>

-   <span data-ttu-id="452bc-138">Klicks auf Schaltflächen und andere Daten zur App-Verwendung</span><span class="sxs-lookup"><span data-stu-id="452bc-138">Button clicks and other pieces of data about app usage</span></span>

-   <span data-ttu-id="452bc-139">Leistungsdaten über die App und/oder bestimmte Features der App</span><span class="sxs-lookup"><span data-stu-id="452bc-139">Performance data about the app and/or particular features within the app</span></span>

-   <span data-ttu-id="452bc-140">Allgemeine Informationen zum Standort des Computers des Benutzers (z. B. Land/Region, Bundesland und Stadt, die aus der IP-Adresse abgeleitet werden), jedoch keine präzise Geolocation</span><span class="sxs-lookup"><span data-stu-id="452bc-140">General location information about where the user’s computer is (e.g. country / region, state, and city, derived from the IP address), but not precise geolocation</span></span>

-   <span data-ttu-id="452bc-141">Grundlegende Metadaten zum Browser, z. B. Browsername und Version, und zum Computer, z. B. Betriebssystemtyp und Version</span><span class="sxs-lookup"><span data-stu-id="452bc-141">Basic metadata about the browser, e.g. browser name and version, and the computer, e.g. OS type and version</span></span>

-   <span data-ttu-id="452bc-142">Fehlermeldungen aus dem Dokumenthost (z. B. OneDrive, SharePoint, Exchange)</span><span class="sxs-lookup"><span data-stu-id="452bc-142">Error messages from the document host (e.g. OneDrive, SharePoint, Exchange)</span></span>

-   <span data-ttu-id="452bc-143">Informationen zu App-internen Prozessen, die mit keiner Aktion des Benutzers zusammenhängen</span><span class="sxs-lookup"><span data-stu-id="452bc-143">Information about processes internal to the app, unrelated to any action the user has taken</span></span>
