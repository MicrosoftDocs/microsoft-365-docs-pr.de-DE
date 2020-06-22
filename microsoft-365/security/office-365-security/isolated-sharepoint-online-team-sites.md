---
title: Isolierte SharePoint Online-Teamwebsites
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Erfahren Sie mehr über isolierte SharePoint Online-Teamwebsites, einschließlich der Anwendungen, Anforderungen und Funktionen, mit denen sie verwendet werden können.
ms.openlocfilehash: 0646ffc37256702844b550fd1beb841944b2d509
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819533"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="b72b8-103">Isolierte SharePoint Online-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="b72b8-103">Isolated SharePoint Online team sites</span></span>

 <span data-ttu-id="b72b8-104">**Zusammenfassung:** Informationen zu Verwendungszwecken für isolierte SharePoint Online-Teamwebsites.</span><span class="sxs-lookup"><span data-stu-id="b72b8-104">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="b72b8-105">SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="b72b8-105">SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365.</span></span> <span data-ttu-id="b72b8-106">SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization.</span><span class="sxs-lookup"><span data-stu-id="b72b8-106">SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization.</span></span> <span data-ttu-id="b72b8-107">A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span><span class="sxs-lookup"><span data-stu-id="b72b8-107">A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>
  
<span data-ttu-id="b72b8-108">However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators.</span><span class="sxs-lookup"><span data-stu-id="b72b8-108">However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators.</span></span> <span data-ttu-id="b72b8-109">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span><span class="sxs-lookup"><span data-stu-id="b72b8-109">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span></span> <span data-ttu-id="b72b8-110">You might need an isolated site for the following:</span><span class="sxs-lookup"><span data-stu-id="b72b8-110">You might need an isolated site for the following:</span></span>
  
- <span data-ttu-id="b72b8-111">Für ein geheimes Projekt innerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="b72b8-111">A secret project within your organization.</span></span>
    
- <span data-ttu-id="b72b8-112">Als Speicherort für das besonders vertrauliche oder wertvolle geistige Eigentum Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="b72b8-112">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>
    
- <span data-ttu-id="b72b8-113">Für die Ressourcen im Zusammenhang mit einer Klage, die von Ihrer Organisation erhoben oder die gegen sie geführt wird.</span><span class="sxs-lookup"><span data-stu-id="b72b8-113">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>
    
- <span data-ttu-id="b72b8-114">Zum Freigeben eines Microsoft 365-Abonnements für mehrere Organisationen, zwischen denen es zwar einige Überschneidungen gibt, die jedoch größtenteils als eigenständige Geschäftseinheiten existieren.</span><span class="sxs-lookup"><span data-stu-id="b72b8-114">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>
    
<span data-ttu-id="b72b8-115">Dies sind die Anforderungen einer isolierten-Website:</span><span class="sxs-lookup"><span data-stu-id="b72b8-115">Here are the requirements of an isolated site:</span></span>
  
- <span data-ttu-id="b72b8-116">Nur SharePoint Online-Administratoren können Aufgaben der Websiteverwaltung ausführen; hierzu gehören die Gruppenmitgliedschaft für den Zugriff auf die Website und das Konfigurieren von benutzerdefinierten Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="b72b8-116">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>
    
- <span data-ttu-id="b72b8-117">Mitglieder der Website können keine anderen Mitglieder zur Teamwebsite einladen.</span><span class="sxs-lookup"><span data-stu-id="b72b8-117">Members of the site cannot invite other members to the team site.</span></span>
    
- <span data-ttu-id="b72b8-118">Users who are not members of the isolated site cannot request access to the site.</span><span class="sxs-lookup"><span data-stu-id="b72b8-118">Users who are not members of the isolated site cannot request access to the site.</span></span> <span data-ttu-id="b72b8-119">They will receive an access denied web page when they attempt to access any URL associated with the site.</span><span class="sxs-lookup"><span data-stu-id="b72b8-119">They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>
    
<span data-ttu-id="b72b8-120">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time.</span><span class="sxs-lookup"><span data-stu-id="b72b8-120">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time.</span></span> <span data-ttu-id="b72b8-121">For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span><span class="sxs-lookup"><span data-stu-id="b72b8-121">For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>
  
<span data-ttu-id="b72b8-122">Eine isolierte Website kann mit anderen Features wie z. B. den folgenden verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="b72b8-122">An isolated site can be used with other features, such as:</span></span>
  
- <span data-ttu-id="b72b8-123">Information Rights Management, um sicherzustellen, dass die Ressourcen auf der Website verschlüsselt bleiben, auch wenn sie lokal heruntergeladen und auf eine andere Website hochgeladen werden, die der gesamten Organisation zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="b72b8-123">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>
    
- <span data-ttu-id="b72b8-124">Verhinderung von Datenverlust, um Benutzer daran zu hindern, die Ressourcen der Website (z. B. Dateien) per E-Mail zu senden.</span><span class="sxs-lookup"><span data-stu-id="b72b8-124">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="b72b8-125">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b72b8-125">Next steps</span></span>

<span data-ttu-id="b72b8-126">Wenn Sie eine isolierte SharePoint Online-Teamwebsite in einem Testabonnement ausprobieren möchten, finden Sie eine schrittweise Anleitung unter [Isolierte SharePoint Online-Teamwebsite in Ihrer Office 365-Entwicklungs-/Testumgebung](isolated-sharepoint-online-team-site-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b72b8-126">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>
  
<span data-ttu-id="b72b8-127">Wenn Sie eine isolierte SharePoint Online-Teamwebsite in der Produktion bereitstellen möchten, lesen Sie die schrittweisen Überlegungen zum Entwurf unter [Entwerfen einer isolierten SharePoint Online-Teamwebsite](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="b72b8-127">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b72b8-128">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b72b8-128">Related topics</span></span>

[<span data-ttu-id="b72b8-129">Entwerfen einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="b72b8-129">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="b72b8-130">Verwalten einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="b72b8-130">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="b72b8-131">Bereitstellen einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="b72b8-131">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)


