---
title: Benutzeroberfläche in einer Multi-Geo-Umgebung
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Mehr zur Benutzeroberfläche von SharePoint, OneDrive und Exchange in einer Multi-Geo-Umgebung für Microsoft 365.
ms.openlocfilehash: c94fc5569a5444ca6361712f57460cf0c977b18e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690445"
---
# <a name="user-experience-in-a-multi-geo-environment"></a><span data-ttu-id="d814a-103">Benutzererfahrung in einer Multi-Geo-Umgebung</span><span class="sxs-lookup"><span data-stu-id="d814a-103">User experience in a multi-geo environment</span></span>

<span data-ttu-id="d814a-104">Im Folgenden wird erläutert, was Benutzern in einer Multi-Geo-Konfiguration in OneDrive angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="d814a-104">Here's what your users will see in a OneDrive Multi-Geo configuration:</span></span>

## <a name="exchange-mailbox"></a><span data-ttu-id="d814a-105">Exchange-Postfach</span><span class="sxs-lookup"><span data-stu-id="d814a-105">Exchange mailbox</span></span>

<span data-ttu-id="d814a-106">Das Exchange-Postfach eines Benutzers wird an dessen bevorzugten Datenspeicherort bereitgestellt und automatisch verschoben, wenn die PDL-Einstellungen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d814a-106">A user's Exchange mailbox is provisioned to their preferred data location, and is automatically relocated if their PDL changes.</span></span> <span data-ttu-id="d814a-107">Benutzer können Outlook und Outlook im Web in Multi-Geo-Umgebungen wie gewohnt und ohne Auswirkungen auf die Benutzererfahrung verwenden.</span><span class="sxs-lookup"><span data-stu-id="d814a-107">Users can use Outlook and Outlook on the web normally with no change in user experience in a multi-geo environment.</span></span>

## <a name="hub-sites"></a><span data-ttu-id="d814a-108">Hubwebsites</span><span class="sxs-lookup"><span data-stu-id="d814a-108">Hub sites</span></span>

<span data-ttu-id="d814a-109">SharePoint-Hubwebsites verbessern den Discovery- und Engagement-Prozess mit Inhalten für Mitarbeiter und gewährleisten eine vollständige und einheitliche Darstellung von Projekten, Abteilungen oder Regionen.</span><span class="sxs-lookup"><span data-stu-id="d814a-109">SharePoint Hub sites enhances the discovery and engagement with content for employees, while creating a complete and consistent representation of projects, departments or regions.</span></span> <span data-ttu-id="d814a-110">In einer Multi-Geo-Umgebung können Satellitenstandort-Websites ganz einfach mit einer Hubwebsite verknüpft werden, unabhängig vom geografischen Standort der Hubwebsite.</span><span class="sxs-lookup"><span data-stu-id="d814a-110">In a multi-geo environment, sites from satellite locations can easily be associated with a hub site regardless the hub site's geo location.</span></span> <span data-ttu-id="d814a-111">Über eine zentrale Suchoberfläche können Benutzer unabhängig vom geografischen Standort der Websites den gesamten Hub durchsuchen und entsprechende Ergebnisse erhalten.</span><span class="sxs-lookup"><span data-stu-id="d814a-111">Users can search and get results across the hub through a single search experience, regardless of the geo location of the sites.</span></span>

## <a name="microsoft-365-app-launcher"></a><span data-ttu-id="d814a-112">Microsoft 365-App-Startfeld</span><span class="sxs-lookup"><span data-stu-id="d814a-112">Microsoft 365 app launcher</span></span>

<span data-ttu-id="d814a-113">Mit jeder Kachel wird an den entsprechenden geografischen Standort des Workloads weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="d814a-113">The app launcher is multi-geo aware and will direct each tile to the appropriate geo location of the workload.</span></span> <span data-ttu-id="d814a-114">Die SharePoint- und OneDrive-Kacheln verweisen auf den Standort, der dem bereitgestellten geografischen Standort des Benutzers entspricht.</span><span class="sxs-lookup"><span data-stu-id="d814a-114">The SharePoint and OneDrive tiles will point the user to the location corresponding to the user's provisioned geo location.</span></span> <span data-ttu-id="d814a-115">Dies bedeutet, dass SharePoint-Kacheln im Falle von Benutzern mit einer OneDrive-Umgebung am zentralen Standort auf die SharePoint-Homepage verweisen, während die Gruppenwebsites solcher Benutzer an den als PDL festgelegten Standort bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d814a-115">This means that is the user has a OneDrive in the central location, their SharePoint tile will point them to SP Home in the central location but their group site will be provisioned in the location corresponding to their PDL.</span></span> 

## <a name="office-applications"></a><span data-ttu-id="d814a-116">Office-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="d814a-116">Office applications</span></span>

<span data-ttu-id="d814a-117">Office-Anwendungen wie Word, Excel und PowerPoint erkennen bei Anmeldung automatisch den richtigen geografischen OneDrive for Business-Standort für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d814a-117">Office applications such as Word, Excel, and PowerPoint will automatically detect the correct OneDrive for Business geo-location for each user when they log in.</span></span> <span data-ttu-id="d814a-118">Benutzer müssen nicht die für den geografischen OneDrive-oder SharePoint-Standort spezifische URL eingeben.</span><span class="sxs-lookup"><span data-stu-id="d814a-118">Users do not need to enter the geo-specific URL for their OneDrive or SharePoint sites.</span></span>

## <a name="onedrive-for-business-sync-client"></a><span data-ttu-id="d814a-119">OneDrive for Business-Synchronisierungsclient</span><span class="sxs-lookup"><span data-stu-id="d814a-119">OneDrive for Business Sync Client</span></span>

<span data-ttu-id="d814a-120">Der OneDrive for Business-Synchronisierungsclient (Version 17.3.6943.0625 und höher) erkennt automatisch den richtigen geografischen OneDrive for Business-Standort für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d814a-120">The OneDrive for Business Sync Client (version 17.3.6943.0625 and later) will automatically detect the correct OneDrive for Business geo location for the user.</span></span> <span data-ttu-id="d814a-121">Die Synchronisierungs-Clientunterstützung bietet die Möglichkeit, gruppenbasierte Websites unabhängig von ihrem geografischen Standort zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="d814a-121">Synch client support includes the ability to sync groups-based sites regardless of their geo location.</span></span> <span data-ttu-id="d814a-122">Beachten Sie, dass der Groove-Synchronisierungsclient nicht für Multi-Geo-Umgebungen unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="d814a-122">Note that the Groove sync client is not supported for multi-geo.</span></span> 

## <a name="onedrive-for-business-location"></a><span data-ttu-id="d814a-123">OneDrive for Business-Standort</span><span class="sxs-lookup"><span data-stu-id="d814a-123">OneDrive for Business location</span></span>

<span data-ttu-id="d814a-p106">OneDrive for Business wird Benutzern an dem jeweiligen bevorzugten Datenspeicherort bereitgestellt. Wenn ein Benutzer zu einer OneDrive-URL navigiert, die einen falschen geografischen Strandort enthält (zum Beispiel ein Lesezeichen von einem vorherigen geografischen Standort), werden sie automatisch zur OneDrive-Umgebung an dem entsprechenden geografischen Standort umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="d814a-p106">Users will have their OneDrive for Business provisioned in their preferred data location. If a user navigates to a OneDrive URL that contains an incorrect geo location (such as a bookmark from a previous geo location), they are automatically redirected to the OneDrive in the appropriate geo location.</span></span>

## <a name="onedrive-ios-and-android"></a><span data-ttu-id="d814a-126">OneDrive unter IOS und Android</span><span class="sxs-lookup"><span data-stu-id="d814a-126">OneDrive iOS and Android</span></span> 

<span data-ttu-id="d814a-p107">In den mobilen OneDrive-Apps für iOS und Android werden Ihre OneDrive-Dateien und für Sie freigegebene Dateien unabhängig vom geografischen Standort angezeigt. Die Suche in den mobilen OneDrive-Apps geben relevante Ergebnisse von allen geografischen Standorten zurück. Laden Sie die neueste Version dieser Apps herunter.</span><span class="sxs-lookup"><span data-stu-id="d814a-p107">The OneDrive iOS and Android mobile apps will show you your OneDrive files and files shared with you regardless of their geo location. Search from the OneDrive mobile apps will show relevant results from all geo locations. Please download the latest version of these apps.</span></span>

<span data-ttu-id="d814a-130">Weitere Informationen finden Sie unter Verwenden von [OneDrive unter iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) und [OneDrive unter Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36).</span><span class="sxs-lookup"><span data-stu-id="d814a-130">See Use [OneDrive on iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) and [Use OneDrive for Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) for more information.</span></span>

## <a name="onedrive-mobile-client"></a><span data-ttu-id="d814a-131">OneDrive Mobile-Client</span><span class="sxs-lookup"><span data-stu-id="d814a-131">OneDrive Mobile Client</span></span> 

<span data-ttu-id="d814a-132">Der OneDrive Mobile-Client ist Multi-Geo-fähig und zeigt relevante Inhalte und Ergebnisse von allen geografischen Standorten an.</span><span class="sxs-lookup"><span data-stu-id="d814a-132">The OneDrive Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="search"></a><span data-ttu-id="d814a-133">Suchen</span><span class="sxs-lookup"><span data-stu-id="d814a-133">Search</span></span>

<span data-ttu-id="d814a-p108">Jeder geografische Standort verfügt über einen eigenen Suchindex und ein Suchcenter. Wenn ein Benutzer eine Suche durchführt, wird die Abfrage an alle geografischen Standorte gesendet, und die zurückgegebenen Ergebnisse werden zusammengeführt und bewertet, sodass der Benutzer einheitliche Ergebnisse erhält. Benutzer erhalten unabhängig von ihrem geografischen Standort Ergebnisse von allen geografischen Standorten. Weitere Informationen dazu finden Sie unter [Konfigurieren der Suche für Multi-Geo in OneDrive for Business](configure-search-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="d814a-p108">Each geo location has its own search index and Search Center. When a user searches, the query is sent to all the geo locations, and the returned results are merged and then ranked so the user gets unified results. Users get results from all geo locations regardless of their own geo location. See [Configure Search for OneDrive for Business Multi-Geo](configure-search-for-multi-geo.md) for specifics.</span></span>

<span data-ttu-id="d814a-138">Die folgenden Suchclients werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="d814a-138">The following search clients are supported:</span></span>

-   <span data-ttu-id="d814a-139">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d814a-139">OneDrive for Business</span></span>

-   <span data-ttu-id="d814a-140">Delve</span><span class="sxs-lookup"><span data-stu-id="d814a-140">Delve</span></span>

-   <span data-ttu-id="d814a-141">SharePoint-Homepage</span><span class="sxs-lookup"><span data-stu-id="d814a-141">SharePoint Home</span></span>

-   <span data-ttu-id="d814a-142">Das Suchcenter</span><span class="sxs-lookup"><span data-stu-id="d814a-142">The Search Center</span></span>

-   <span data-ttu-id="d814a-143">Benutzerdefinierte Suchanwendungen, die die SharePoint-Suche-API verwenden</span><span class="sxs-lookup"><span data-stu-id="d814a-143">Custom search applications that use the SharePoint Search API</span></span>

## <a name="sharepoint-home"></a><span data-ttu-id="d814a-144">SharePoint-Homepage</span><span class="sxs-lookup"><span data-stu-id="d814a-144">SharePoint Home</span></span> 

<span data-ttu-id="d814a-145">In SharePoint Multi-Geo wird Ihre SharePoint-Homepage am Standort des Benutzers gehostet. Dieser wird anhand des entsprechenden OneDrive for Business-Standorts ermittelt.</span><span class="sxs-lookup"><span data-stu-id="d814a-145">In SharePoint Multi-Geo your SharePoint home is hosted in the location where the user resides as determined by their OneDrive for business location.</span></span> <span data-ttu-id="d814a-146">Wenn die OneDrive-Umgebung eines Benutzers zum Beispiel über einen europäischen Satellitenstandort gehostet wird, wird dessen SharePoint-Homepage in Europa gerendert.</span><span class="sxs-lookup"><span data-stu-id="d814a-146">For example: if the user has their OneDrive hosted in an European satellite location, their SharePoint Home will be rendered from Europe.</span></span> <span data-ttu-id="d814a-147">Die SharePoint-Homepage enthält unabhängig von ihrem geografischen Standort alle für den Benutzer relevanten Inhalte.</span><span class="sxs-lookup"><span data-stu-id="d814a-147">SharePoint home includes all content relevant to the user regardless of its geo location.</span></span> 

<span data-ttu-id="d814a-148">**Gefolgte Websites, Neuigkeiten von Websites, Zuletzt geöffnete Websites, Häufig verwendete Websites, und Empfohlene Websites**</span><span class="sxs-lookup"><span data-stu-id="d814a-148">**Followed Sites, News from Sites, Recent Sites, Frequent Sites, and Suggested sites**</span></span>

<span data-ttu-id="d814a-149">All diese Komponenten werden dem Benutzer unabhängig von dem geografischen Standort, an dem die Inhalte gehostet werden, unter der Bedingung angezeigt, dass der Benutzer über entsprechende Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="d814a-149">All of these components will show up for the user regardless of the geo location where the content is hosted, so long as the user has permissions to said content.</span></span> 

<span data-ttu-id="d814a-150">**Wichtige Links**</span><span class="sxs-lookup"><span data-stu-id="d814a-150">**Features Links**</span></span>

<span data-ttu-id="d814a-151">Administratoren können abhängig vom jeweiligen geografischen Standort wichtige Links auf der SharePoint-Homepage einrichten.</span><span class="sxs-lookup"><span data-stu-id="d814a-151">Admins may configure Featured links in SharePoint home as appropriate to each geo location.</span></span> <span data-ttu-id="d814a-152">So kann der Administrator für Benutzer in jeder Region jeweils wichtige Links auf der SharePoint-Homepage hervorheben.</span><span class="sxs-lookup"><span data-stu-id="d814a-152">This allows the admin to feature in the SP Home for each region the links that are appropriate for users in the region.</span></span> 

## <a name="sharepoint-mobile-client"></a><span data-ttu-id="d814a-153">SharePoint Mobile-Client</span><span class="sxs-lookup"><span data-stu-id="d814a-153">SharePoint Mobile Client</span></span> 

<span data-ttu-id="d814a-154">Der SharePoint Mobile-Client ist Multi-Geo-fähig und zeigt relevante Inhalte und Ergebnisse von allen geografischen Standorten an.</span><span class="sxs-lookup"><span data-stu-id="d814a-154">The SharePoint Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="sharing"></a><span data-ttu-id="d814a-155">Freigabe</span><span class="sxs-lookup"><span data-stu-id="d814a-155">Sharing</span></span>

<span data-ttu-id="d814a-156">Die Personenauswahl-Ansicht zeigt sämtliche Benutzer unabhängig von ihrem geografischen Standort an.</span><span class="sxs-lookup"><span data-stu-id="d814a-156">The People Picker experience shows all users regardless of their geo location.</span></span> <span data-ttu-id="d814a-157">Dadurch hat ein Benutzer die Möglichkeit, Inhalte mit anderen Benutzern am selben oder an einem anderen Ihrem Mandanten zugewiesenen geografischen Standort zu teilen.</span><span class="sxs-lookup"><span data-stu-id="d814a-157">This allows a user to share with another user in their same geo or in any other of your tenant's geo locations.</span></span> <span data-ttu-id="d814a-158">Inhalte von anderen geografischen Standorten werden unabhängig vom geografischen Standort, an dem sie gehostet werden, in der Ansicht **Für mich freigegeben** in der OneDrive for Business-Umgebung des Benutzers angezeigt und können über eine einmalige Anmeldung eingesehen werden.</span><span class="sxs-lookup"><span data-stu-id="d814a-158">Content from different geo locations will show up in the **Shared with Me** view in the user's OneDrive for Business and can be accessed with Single Sign-On experience regardless of which geo location it is hosted in.</span></span>

## <a name="teams-experience"></a><span data-ttu-id="d814a-159">Teams-Erfahrung</span><span class="sxs-lookup"><span data-stu-id="d814a-159">Teams Experience</span></span>

<span data-ttu-id="d814a-160">Teams ist Multi-Geo-fähig.</span><span class="sxs-lookup"><span data-stu-id="d814a-160">Teams is multi-geo aware.</span></span> <span data-ttu-id="d814a-161">OneDrive- und zuletzt angezeigte Dateien werden unabhängig vom geografischen Standort des Benutzers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d814a-161">OneDrive files and recently viewed files are shown regardless of the user's geo location.</span></span> <span data-ttu-id="d814a-162">@-Erwähnungen funktionieren mit Benutzern von allen geografischen Standorten.</span><span class="sxs-lookup"><span data-stu-id="d814a-162">@ mentions work with users from all geo-locations.</span></span>

## <a name="user-profiles"></a><span data-ttu-id="d814a-163">Benutzerprofile</span><span class="sxs-lookup"><span data-stu-id="d814a-163">User profiles</span></span>

<span data-ttu-id="d814a-p113">Benutzerprofilinformationen werden an dem geografischen Standort des Benutzers verwaltet. Beim Auswählen eines Benutzers werden Sie an den entsprechenden geografischen Standort des Benutzers weitergeleitet, wo vollständige Profilinformationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d814a-p113">User profile information is mastered in the user's geo location. When selecting a user, you will be directed to the appropriate geo location for the user, where you will see their full profile details.</span></span>

<span data-ttu-id="d814a-166">Wenn Delve deaktiviert ist, sehen Sie das klassische Profil in SharePoint, welches nicht Multi-Geo-fähig ist.</span><span class="sxs-lookup"><span data-stu-id="d814a-166">If Delve is turned off, you will see the classic profile experience in SharePoint, which is not multi-geo aware.</span></span>


