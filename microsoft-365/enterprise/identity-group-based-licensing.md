---
title: 'Schritt 11: Einrichten der automatischen Lizenzierung'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und konfigurieren Sie die gruppenbasierte Lizenzierung für Azure AD-Gruppen.
ms.openlocfilehash: 6a5569bdc4692681425f8926d3647f81890e7b9f
ms.sourcegitcommit: f3bf836df0f915fa05422fbc7ea3882c1ea4bac7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2018
ms.locfileid: "20329047"
---
# <a name="step-11-set-up-automatic-licensing"></a><span data-ttu-id="8039c-103">Schritt 11: Einrichten der automatischen Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="8039c-103">Step 11: Set up automatic licensing</span></span>

<span data-ttu-id="8039c-104">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="8039c-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="8039c-p101">In Schritt 11 konfigurieren Sie Sicherheitsgruppen in Azure AD, um automatisch Lizenzen aus einem Satz von Abonnements zu allen Mitgliedern der Gruppe zuzuweisen. Dies wird als *gruppenbasierte Lizenzierung* bezeichnet. Wenn ein Benutzerkonto zur Gruppe hinzugefügt oder aus ihr entfernt wird, werden die Lizenzen für die Abonnements der Gruppe automatisch zugewiesen oder aus dem Benutzerkonto entfernt.</span><span class="sxs-lookup"><span data-stu-id="8039c-p101">In Step 11, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group. This is known as *group-based licensing*. If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="8039c-108">Für Microsoft 365 Enterprise konfigurieren Sie Azure AD-Sicherheitsgruppen, um beide Lizenzen zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="8039c-108">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign both of these licenses:</span></span>

- <span data-ttu-id="8039c-109">Office 365 Enterprise E3 oder E5</span><span class="sxs-lookup"><span data-stu-id="8039c-109">Office 365 Enterprise E3 or E5</span></span>
- <span data-ttu-id="8039c-110">Enterprise Mobility + Security (EMS) E3 oder E5</span><span class="sxs-lookup"><span data-stu-id="8039c-110">Enterprise Mobility + Security (EMS) E3 or E5</span></span>

<span data-ttu-id="8039c-p102">Suchen Sie unter Verwendung der Gruppen, die Sie in Schritt 2 identifiziert haben, nach Gruppen, die eine Liste der Konten enthalten, wobei alle Benutzer in dieser Gruppe Office 365- und EMS-Lizenzen haben müssen. Stellen Sie sicher, dass Sie genug Lizenzen für alle Gruppenmitglieder haben. Wenn keine Lizenzen mehr vorhanden sind, werden neuen Benutzern keine Lizenzen zugewiesen, bis Lizenzen verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="8039c-p102">Using the groups you identified in Step 2, look for groups that contain a list of accounts where all users in that group must have both Office 365 and EMS licenses. Make sure you have enough licenses for all the group members. If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="8039c-114">Sie sollten  nicht die *gruppenbasierte Lizenzierung* für Gruppen konfigurieren, die Azure Business to Business (B2B)-Konten enthalten.</span><span class="sxs-lookup"><span data-stu-id="8039c-114">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="8039c-115">Weitere Informationen finden Sie unter [Grundlagen der gruppenbasierten Lizenzierung in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="8039c-115">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="8039c-116">Lesen Sie die [Schritte zum Konfigurieren der gruppenbasierten Lizenzierung für eine Azure-Sicherheitsgruppe](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="8039c-116">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="8039c-117">Die Ergebnisse dieses Schritts sind:</span><span class="sxs-lookup"><span data-stu-id="8039c-117">The results of this step are:</span></span>

- <span data-ttu-id="8039c-118">Sie haben identifiziert, welche Sicherheitsgruppen für die gruppenbasierte Lizenzierung geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="8039c-118">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="8039c-119">Sie haben diese Gruppen für gruppenbasierte Lizenzierung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8039c-119">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="8039c-121">Testumgebungsanleitung: Automatisieren von Lizenzen und Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="8039c-121">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="8039c-122">Als Zwischenprüfpunkt können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-step11) für diesen Schritt ansehen.</span><span class="sxs-lookup"><span data-stu-id="8039c-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-step11) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="8039c-123">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="8039c-123">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step12.png)| [<span data-ttu-id="8039c-124">Einrichten der dynamischen Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="8039c-124">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md) |

