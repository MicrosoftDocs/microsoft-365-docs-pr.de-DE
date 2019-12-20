---
title: Bereitstellen von Microsoft Teams für Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: Hier finden Sie Informationen zu Microsoft Teams und dessen Einführung in Ihrem Unternehmen.
ms.openlocfilehash: 8220d06fe90bc4bc793ab33d6121e93bb855f973
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801240"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a><span data-ttu-id="be1b6-103">Bereitstellen von Microsoft Teams für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="be1b6-103">Deploy Microsoft Teams for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="be1b6-104">*Diese Workload ist in den Versionen E3 und E5 von Microsoft 365 Enterprise enthalten.*</span><span class="sxs-lookup"><span data-stu-id="be1b6-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="be1b6-p101">In Microsoft Teams werden Chats, Konferenzen, Dokumentfreigabe und Diskussionsthreads derart kombiniert, dass das Erstellen und Freigeben von Inhalten über Gruppen hinweg erleichtert wird. Teams ermöglicht Teamarbeit und Zusammenarbeit für Microsoft 365 Enterprise und ist ein Schlüsselelement für den Ansatz "Built for Teamwork" von Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="be1b6-p101">Microsoft Teams brings together chat, conferencing, document sharing, and threaded conversations in a way that makes it easy to create and share content across groups. Teams is the way you do teamwork and collaboration for Microsoft 365 Enterprise and is a key element of the Built for Teamwork value of Microsoft 365.</span></span> 

<span data-ttu-id="be1b6-107">Wenn Sie noch nicht mit Teams vertraut sind, lesen Sie die Informationen unter [Willkommen bei Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).</span><span class="sxs-lookup"><span data-stu-id="be1b6-107">If you're brand new to Teams, see [Welcome to Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).</span></span> 


## <a name="roll-out-teams-to-your-organization"></a><span data-ttu-id="be1b6-108">Bereitstellen von Teams für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="be1b6-108">Roll out Teams to your organization</span></span>

<span data-ttu-id="be1b6-109">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="be1b6-109">Before you begin:</span></span>

- <span data-ttu-id="be1b6-110">Stellen Sie sicher, dass Sie die richtigen [Foundation-Infrastruktur](deploy-foundation-infrastructure.md)-Phasen konfiguriert haben, sodass Ihren Teams die erforderlichen Benutzerkonten und Sicherheitsfunktionen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="be1b6-110">Make sure you've configured the right [foundation infrastructure](deploy-foundation-infrastructure.md) phases so that your teams have the user accounts and security capabilities you need.</span></span> <span data-ttu-id="be1b6-111">"Identität" und "Informationsschutz" sind die wichtigsten Phasen für Anmeldung, Verwendung und Absicherung von E-Mails und Dateien mit Aufbewahrungs- und Vertraulichkeitsbezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="be1b6-111">The Identity and Information Protection phases are the most important for signing on and using securing email and files with retention and sensitivity labels.</span></span>
- <span data-ttu-id="be1b6-112">In [diesem Artikel](https://docs.microsoft.com/microsoftteams/security-compliance-overview) erfahren Sie mehr über Sicherheit und Compliance in Teams.</span><span class="sxs-lookup"><span data-stu-id="be1b6-112">Learn about security and compliance in Teams with [this article](https://docs.microsoft.com/microsoftteams/security-compliance-overview).</span></span>
- <span data-ttu-id="be1b6-113">In [diesem Artikel](https://docs.microsoft.com/microsoftteams/office-365-licensing) erfahren Sie mehr über die Office 365-Lizenzierung für Teams.</span><span class="sxs-lookup"><span data-stu-id="be1b6-113">Learn about Office 365 licensing for Teams with [this article](https://docs.microsoft.com/microsoftteams/office-365-licensing).</span></span>

<span data-ttu-id="be1b6-114">Wenn Sie Teams in Ihrer Organisation bereitstellen möchten, lesen Sie [Bereitstellen von Microsoft Teams](https://docs.microsoft.com/microsoftteams/how-to-roll-out-teams).</span><span class="sxs-lookup"><span data-stu-id="be1b6-114">To roll out Teams in your organization, read [How to roll out Teams](https://docs.microsoft.com/microsoftteams/how-to-roll-out-teams).</span></span>

<span data-ttu-id="be1b6-115">Informationen zu den ersten Teams-Funktionen finden Sie unter [Chat, Teams, Kanäle und Apps in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/deploy-chat-teams-channels-microsoft-teams-landing-page).</span><span class="sxs-lookup"><span data-stu-id="be1b6-115">For your first set of Teams capabilities, see [Chat, teams, channels, and apps in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/deploy-chat-teams-channels-microsoft-teams-landing-page).</span></span>

<span data-ttu-id="be1b6-116">Erweiterte Teams-Funktionen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="be1b6-116">For more advanced Teams capabilities, see:</span></span>

- [<span data-ttu-id="be1b6-117">Besprechungen und Konferenzen</span><span class="sxs-lookup"><span data-stu-id="be1b6-117">Meetings and Conferencing</span></span>](https://docs.microsoft.com/microsoftteams/deploy-meetings-microsoft-teams-landing-page)
- <span data-ttu-id="be1b6-118">[Cloud Voice](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page) (erfordert Microsoft 365 E5)</span><span class="sxs-lookup"><span data-stu-id="be1b6-118">[Cloud voice](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page) (requires Microsoft 365 Enterprise E5)</span></span>

<span data-ttu-id="be1b6-119">Informationen zum Überwachen der Verwendung von Teams in Ihrer Organisation finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="be1b6-119">To monitor your organization's usage of Teams, see:</span></span>

- [<span data-ttu-id="be1b6-120">Teamübergreifende und teambezogene Analysen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be1b6-120">Cross-team and per-team analytics in Teams</span></span>](https://docs.microsoft.com/microsoftteams/teams-analytics-and-reports/cross-team-per-team-analytics)
- [<span data-ttu-id="be1b6-121">Analyse und Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="be1b6-121">Analytics and reporting</span></span>](https://docs.microsoft.com/microsoftteams/teams-analytics-and-reports/teams-reporting-reference)


## <a name="upgrade-to-teams"></a><span data-ttu-id="be1b6-122">Upgrade zu Teams</span><span class="sxs-lookup"><span data-stu-id="be1b6-122">Upgrade to Teams</span></span>

<span data-ttu-id="be1b6-123">Wenn noch nicht geschehen, werden Sie bald ein Upgrade von Skype for Business auf Microsoft Teams durchführen.</span><span class="sxs-lookup"><span data-stu-id="be1b6-123">If it hasn’t happened already, you will soon upgrade from Skype for Business to Microsoft Teams.</span></span> <span data-ttu-id="be1b6-124">Ganz gleich, ob Sie neu bei Microsoft Teams sind, Microsoft Teams bereits zusammen mit Skype for Business verwenden oder bereit für das Upgrade sind – wir möchten sicherstellen, dass Sie alles haben, was Sie für eine erfolgreiche Umstellung auf Microsoft Teams benötigen.</span><span class="sxs-lookup"><span data-stu-id="be1b6-124">Whether you’re just getting started with Teams, already using Teams alongside Skype for Business, or ready to upgrade, we want to ensure you have everything you need to navigate a successful journey to Teams.</span></span>

<span data-ttu-id="be1b6-125">Ganz gleich, ob Sie ein Upgrade von Skype for Business Online auf Microsoft Teams oder von einer lokalen Skype for Business-Umgebung zu Microsoft Teams durchführen – das Upgrade Framework führt Sie basierend auf Ihrem Geschäftsszenario durch den Prozess.</span><span class="sxs-lookup"><span data-stu-id="be1b6-125">Whether you are upgrading from Skype for Business Online to Teams or from a Skype for Business on-premises environment to Teams, the upgrade framework will guide you through the process based on your business scenario.</span></span>
 
<span data-ttu-id="be1b6-126">Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade von Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="be1b6-126">See the [Getting started with your Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here) for more information.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="be1b6-127">Funktionsweise von Microsoft 365 Enterprise bei Microsoft</span><span class="sxs-lookup"><span data-stu-id="be1b6-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="be1b6-128">Im folgenden Artikel erhalten Sie einen Einblick in die Arbeit von Microsoft, und erfahren Sie, wie wir Teams für die Zusammenarbeit bereitgestellt haben und verwenden:</span><span class="sxs-lookup"><span data-stu-id="be1b6-128">To peek inside Microsoft and learn how we deployed and are using Teams for collaboration, see:</span></span>

- [<span data-ttu-id="be1b6-129">Die Strategie für die Einführung von Microsoft Teams bereitet Mitarbeiter auf eine neue Unternehmenskultur vor</span><span class="sxs-lookup"><span data-stu-id="be1b6-129">Microsoft Teams adoption strategy prepares employees for a new culture of work</span></span>](https://www.microsoft.com/itshowcase/microsoft-teams-adoption-strategy-prepares-employees-for-a-new-culture-of-work)
- [<span data-ttu-id="be1b6-130">Microsoft Teams-Räume schafft eine global skalierbare moderne Besprechungsumgebung</span><span class="sxs-lookup"><span data-stu-id="be1b6-130">With Microsoft Teams Rooms, comes a globally scalable modern meeting experience</span></span>](https://www.microsoft.com/itshowcase/with-microsoft-teams-rooms-comes-a-globally-scalable-modern-meeting-experience)

## <a name="next-steps"></a><span data-ttu-id="be1b6-131">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="be1b6-131">Next steps</span></span>

- [<span data-ttu-id="be1b6-132">Verwalten von Microsoft Teams-Features in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="be1b6-132">Manage Microsoft Teams features for your organization</span></span>](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [<span data-ttu-id="be1b6-133">Administratorschulung für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be1b6-133">Admin training for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/itadmin-readiness)

