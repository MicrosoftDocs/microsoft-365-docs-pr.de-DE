---
title: Microsoft 365 Cloud-only Identity
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Beschreibt, wie Benutzer und Gruppen erstellt werden, wenn Ihr Microsoft 365-Abonnement nur eine Cloud-Identität verwendet.
ms.openlocfilehash: 111c42e644913a8f7f6e41d4e8bf65685263f757
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327927"
---
# <a name="microsoft-365-cloud-only-identity"></a><span data-ttu-id="fc463-103">Microsoft 365 Cloud-only Identity</span><span class="sxs-lookup"><span data-stu-id="fc463-103">Microsoft 365 cloud-only identity</span></span>

<span data-ttu-id="fc463-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="fc463-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fc463-105">Bei der reinen cloudbasierten Identität werden alle Ihre Benutzer, Gruppen und Kontakte im Azure Active Directory (Azure AD)-Mandanten Ihres Microsoft 365-Abonnements gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fc463-105">With cloud-only identity, all your users, groups, and contacts are stored in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="fc463-106">Hier sind die grundlegenden Komponenten der reinen Cloudidentität.</span><span class="sxs-lookup"><span data-stu-id="fc463-106">Here are the basic components of cloud-only identity.</span></span>
 
![Die grundlegenden Komponenten von Cloud-only Identity](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="fc463-108">Benutzer und ihre Benutzerkonten in Organisationen können auf verschiedene Arten kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="fc463-108">Users and their user accounts in organizations can be categorized in a number of ways.</span></span> <span data-ttu-id="fc463-109">Einige sind beispielsweise Mitarbeiter und haben einen permanenten Status.</span><span class="sxs-lookup"><span data-stu-id="fc463-109">For example, some are employees and have a permanent status.</span></span> <span data-ttu-id="fc463-110">Bei einigen handelt es sich um Kreditoren, Auftragnehmer oder Partner mit einem temporären Status.</span><span class="sxs-lookup"><span data-stu-id="fc463-110">Some are vendors, contractors, or partners that have a temporary status.</span></span> <span data-ttu-id="fc463-111">Einige sind externe Benutzer, die über keine Benutzerkonten verfügen, aber weiterhin Zugriff auf bestimmte Dienste und Ressourcen für die Unterstützung von Interaktion und Zusammenarbeit erhalten müssen.</span><span class="sxs-lookup"><span data-stu-id="fc463-111">Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration.</span></span> <span data-ttu-id="fc463-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fc463-112">For example:</span></span>

- <span data-ttu-id="fc463-113">Mandantenkonten stellen Benutzer in Ihrem Unternehmen dar, die Sie für Clouddienste lizenzieren.</span><span class="sxs-lookup"><span data-stu-id="fc463-113">Tenant accounts represent users within your organization that you license for cloud services</span></span>

- <span data-ttu-id="fc463-114">Business-to-Business(B2B)-Konten stellen Benutzer außerhalb Ihres Unternehmens dar, die Sie zur Zusammenarbeit einladen.</span><span class="sxs-lookup"><span data-stu-id="fc463-114">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="fc463-115">Übernehmen Sie eine Bestandsaufnahme der Benutzertypen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="fc463-115">Take stock of the types of users in your organization.</span></span> <span data-ttu-id="fc463-116">Was sind die Gruppierungen?</span><span class="sxs-lookup"><span data-stu-id="fc463-116">What are the groupings?</span></span> <span data-ttu-id="fc463-117">Beispielsweise können Sie Benutzer nach allgemeinen Funktionen oder Zweck in Ihrer Organisation gruppieren.</span><span class="sxs-lookup"><span data-stu-id="fc463-117">For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="fc463-p104">Darüber hinaus können einige Clouddienste für Benutzer außerhalb Ihres Unternehmens ohne Benutzerkonten freigegeben werden. Sie müssen diese Benutzergruppen ebenfalls identifizieren.</span><span class="sxs-lookup"><span data-stu-id="fc463-p104">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

<span data-ttu-id="fc463-120">Sie können Gruppen in Azure AD für verschiedene Zwecke verwenden, die die Verwaltung Ihrer Cloud-Umgebung vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="fc463-120">You can use groups in Azure AD for several purposes that simplify management of your cloud environment.</span></span> <span data-ttu-id="fc463-121">Beispielsweise können Sie mit Azure Ad Gruppen Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="fc463-121">For example, with Azure AD groups, you can:</span></span>

- <span data-ttu-id="fc463-122">Verwenden Sie Gruppenbasierte Lizenzierungen, um Ihren Benutzerkonten automatisch Lizenzen für Microsoft 365 zuzuweisen, sobald diese als Mitglieder hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fc463-122">Use group-based licensing to assign licenses for Microsoft 365 to your user accounts automatically as soon as they are added as members.</span></span>
- <span data-ttu-id="fc463-123">Hinzufügen von Benutzerkonten zu bestimmten Gruppen dynamisch basierend auf Benutzerkonto Attributen wie Abteilungsname.</span><span class="sxs-lookup"><span data-stu-id="fc463-123">Add user accounts to specific groups dynamically based on user account attributes, such as department name.</span></span>
- <span data-ttu-id="fc463-124">Automatische Bereitstellung von Benutzern für Software as a Service (SaaS)-Anwendungen und zum Schutz des Zugriffs auf diese Anwendungen mit mehrstufiger Authentifizierung (MFA) und anderen Richtlinien für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="fc463-124">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication (MFA) and other Conditional Access policies.</span></span>
- <span data-ttu-id="fc463-125">Bereitstellungsberechtigungen und Zugriffsebenen für SharePoint Online Teamwebsites.</span><span class="sxs-lookup"><span data-stu-id="fc463-125">Provision permissions and levels of access for SharePoint Online team sites.</span></span>

## <a name="next-steps-for-cloud-only-identity"></a><span data-ttu-id="fc463-126">Nächste Schritte für Cloud-only Identity</span><span class="sxs-lookup"><span data-stu-id="fc463-126">Next steps for cloud-only identity</span></span>

- [<span data-ttu-id="fc463-127">Verwalten von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="fc463-127">Manage user accounts</span></span>](manage-microsoft-365-accounts.md)
- [<span data-ttu-id="fc463-128">Zuweisen von Lizenzen zu Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="fc463-128">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)
- [<span data-ttu-id="fc463-129">Verwalten von Gruppen und Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="fc463-129">Manage groups and group membership</span></span>](manage-microsoft-365-groups.md)
- [<span data-ttu-id="fc463-130">Verwalten von Kennwörtern für Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="fc463-130">Manage user account passwords</span></span>](manage-microsoft-365-passwords.md)
