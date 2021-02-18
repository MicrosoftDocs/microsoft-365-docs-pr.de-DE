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
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Erfahren Sie mehr über isolierte SharePoint Online-Teamwebsites, einschließlich der Anwendungen, Anforderungen und Funktionen, mit denen sie verwendet werden können.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 056c6f2a463d38dd27b26d484995280dddedf436
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286585"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="6d15f-103">Isolierte SharePoint Online-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="6d15f-103">Isolated SharePoint Online team sites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6d15f-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="6d15f-104">**Applies to**</span></span>
- [<span data-ttu-id="6d15f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6d15f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6d15f-106">Microsoft Defender für Office 365 – Plan 1</span><span class="sxs-lookup"><span data-stu-id="6d15f-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="6d15f-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6d15f-107">SharePoint Online</span></span> 

 <span data-ttu-id="6d15f-108">**Zusammenfassung:** Informationen zu Verwendungszwecken für isolierte SharePoint Online-Teamwebsites.</span><span class="sxs-lookup"><span data-stu-id="6d15f-108">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="6d15f-p101">SharePoint Online-Teamwebsites sind eine einfache Möglichkeit, um schnell einen Ort für die Zusammenarbeit an Notizen, Dokumenten, Artikeln, einem Kalender und anderen Ressourcen in Microsoft Office 365 zu erstellen. SharePoint Online-Teamwebsites basieren auf einer Microsoft 365-Gruppe und verfügen über ein vereinfachtes Verwaltungsmodell, um die offene Zusammenarbeit mit einer als „Privat“ definierten Menge von Gruppenmitgliedern oder der gesamten Organisation zu ermöglichen. Über eine standardmäßige SharePoint Online-Teamwebsite können Mitglieder der Microsoft 365-Gruppe andere Benutzer einladen und Berechtigungseinstellungen steuern.</span><span class="sxs-lookup"><span data-stu-id="6d15f-p101">SharePoint Online team sites are an easy way to quickly create a space for collaboration. Users can work together on notes, documents, articles, a calendar, and other resources in Microsoft Office 365. SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization. A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>

<span data-ttu-id="6d15f-113">Manchmal ist es jedoch erforderlich, den Websitezugriff über Gruppenmitgliedschaften und SharePoint Online-Berechtigungsstufen, die von SharePoint-Administratoren verwaltet werden, zu steuern.</span><span class="sxs-lookup"><span data-stu-id="6d15f-113">However, you'll sometimes need site access to be controlled by group memberships, and SharePoint Online permission levels managed by SharePoint administrators.</span></span> <span data-ttu-id="6d15f-114">Wir bezeichnen dies als eine isolierte Website, die auf die Gruppe der Benutzer beschränkt ist, die entweder auf der Website zusammenarbeiten, ihren Inhalt anzeigen oder diese verwalten.</span><span class="sxs-lookup"><span data-stu-id="6d15f-114">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span></span> <span data-ttu-id="6d15f-115">Eine isolierte Website kann z. B. in folgenden Fällen erforderlich sein:</span><span class="sxs-lookup"><span data-stu-id="6d15f-115">You might need an isolated site for the following:</span></span>

- <span data-ttu-id="6d15f-116">Für ein geheimes Projekt innerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="6d15f-116">A secret project within your organization.</span></span>

- <span data-ttu-id="6d15f-117">Als Speicherort für das besonders vertrauliche oder wertvolle geistige Eigentum Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="6d15f-117">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>

- <span data-ttu-id="6d15f-118">Für die Ressourcen im Zusammenhang mit einer Klage, die von Ihrer Organisation erhoben oder die gegen sie geführt wird.</span><span class="sxs-lookup"><span data-stu-id="6d15f-118">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>

- <span data-ttu-id="6d15f-119">Zum Freigeben eines Microsoft 365-Abonnements für mehrere Organisationen, zwischen denen es zwar einige Überschneidungen gibt, die jedoch größtenteils als eigenständige Geschäftseinheiten existieren.</span><span class="sxs-lookup"><span data-stu-id="6d15f-119">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>

<span data-ttu-id="6d15f-120">Dies sind die Anforderungen einer isolierten-Website:</span><span class="sxs-lookup"><span data-stu-id="6d15f-120">Here are the requirements of an isolated site:</span></span>

- <span data-ttu-id="6d15f-121">Nur SharePoint Online-Administratoren können Aufgaben der Websiteverwaltung ausführen; hierzu gehören die Gruppenmitgliedschaft für den Zugriff auf die Website und das Konfigurieren von benutzerdefinierten Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="6d15f-121">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>

- <span data-ttu-id="6d15f-122">Mitglieder der Website können keine anderen Mitglieder zur Teamwebsite einladen.</span><span class="sxs-lookup"><span data-stu-id="6d15f-122">Members of the site cannot invite other members to the team site.</span></span>

- <span data-ttu-id="6d15f-p103">Benutzer, die kein Mitglied der isolierten Website sind, können keinen Zugriff auf die Website anfordern. Wenn sie versuchen, auf eine der Website zugeordnete URL zuzugreifen, wird eine Webseite mit der Meldung angezeigt, dass der Zugriff verweigert wurde.</span><span class="sxs-lookup"><span data-stu-id="6d15f-p103">Users who are not members of the isolated site cannot request access to the site. They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>

<span data-ttu-id="6d15f-p104">Der Nachteil beim Anfordern einer zentralen Zugriffssteuerung und von benutzerdefinierten Berechtigungen von SharePoint Online-Administratoren besteht darin, dass die Website isoliert bleibt. Beispielsweise können aktuelle Mitglieder weder absichtlich noch versehentlich andere Benutzer innerhalb des Microsoft 365-Abonnements, die kein Mitglied der Website sein sollten, einladen oder benutzerdefinierte Berechtigungen für diese konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6d15f-p104">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time. For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>

<span data-ttu-id="6d15f-127">Eine isolierte Website kann mit anderen Features wie z. B. den folgenden verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="6d15f-127">An isolated site can be used with other features, such as:</span></span>

- <span data-ttu-id="6d15f-128">Information Rights Management, um sicherzustellen, dass die Ressourcen auf der Website verschlüsselt bleiben, auch wenn sie lokal heruntergeladen und auf eine andere Website hochgeladen werden, die der gesamten Organisation zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="6d15f-128">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>

- <span data-ttu-id="6d15f-129">Verhinderung von Datenverlust, um Benutzer daran zu hindern, die Ressourcen der Website (z. B. Dateien) per E-Mail zu senden.</span><span class="sxs-lookup"><span data-stu-id="6d15f-129">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6d15f-130">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6d15f-130">Next steps</span></span>

<span data-ttu-id="6d15f-131">Wenn Sie eine isolierte SharePoint Online-Teamwebsite in einem Testabonnement ausprobieren möchten, finden Sie eine schrittweise Anleitung unter [Isolierte SharePoint Online-Teamwebsite in Ihrer Office 365-Entwicklungs-/Testumgebung](isolated-sharepoint-online-team-site-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6d15f-131">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>

<span data-ttu-id="6d15f-132">Wenn Sie eine isolierte SharePoint Online-Teamwebsite in der Produktion bereitstellen möchten, lesen Sie die schrittweisen Überlegungen zum Entwurf unter [Entwerfen einer isolierten SharePoint Online-Teamwebsite](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="6d15f-132">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6d15f-133">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6d15f-133">Related topics</span></span>

[<span data-ttu-id="6d15f-134">Entwerfen einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="6d15f-134">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="6d15f-135">Verwalten einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="6d15f-135">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="6d15f-136">Bereitstellen einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="6d15f-136">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
