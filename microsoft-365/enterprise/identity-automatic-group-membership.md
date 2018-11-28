---
title: 'Schritt 12: Einrichten der dynamischen Gruppenmitgliedschaft'
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
description: Verstehen Sie die automatische Gruppenmitgliedschaft auf Grundlage von Konto-Attributen, und konfigurieren Sie sie.
ms.openlocfilehash: 9397ecaa56a35d39b4639fcef227f8285397807b
ms.sourcegitcommit: f3bf836df0f915fa05422fbc7ea3882c1ea4bac7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2018
ms.locfileid: "20329037"
---
# <a name="step-12-set-up-dynamic-group-membership"></a><span data-ttu-id="f0ead-103">Schritt 12: Einrichten der dynamischen Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="f0ead-103">Step 12: Set up dynamic group membership</span></span>

<span data-ttu-id="f0ead-104">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f0ead-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="f0ead-p101">In Schritt 12 erstellen Sie eine Reihe von Regeln, die automatisch Benutzerkonten als Mitglieder einer Azure AD-Gruppe hinzufügen oder entfernen. Dies wird als *dynamische Gruppenmitgliedschaft* bezeichnet. Die Regeln basieren auf Benutzerkontoattributen, wie Abteilung oder Land.</span><span class="sxs-lookup"><span data-stu-id="f0ead-p101">In Step 12, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group. This is known as *dynamic group membership*. The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="f0ead-108">Die Regeln werden wie folgt angewendet:</span><span class="sxs-lookup"><span data-stu-id="f0ead-108">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="f0ead-109">Wenn ein neues Benutzerkonto allen Regeln für die Gruppe entspricht, wird es ein Mitglied.</span><span class="sxs-lookup"><span data-stu-id="f0ead-109">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="f0ead-110">Wenn ein Benutzerkonto kein Mitglied der Gruppe ist, aber sich seine Attribute ändern, sodass es allen Regeln für die Gruppe entspricht, wird es ein Mitglied dieser Gruppe.</span><span class="sxs-lookup"><span data-stu-id="f0ead-110">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="f0ead-111">Wenn ein Benutzerkonto nicht allen Regeln für die Gruppe entspricht, wird es nicht zur Gruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f0ead-111">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="f0ead-112">Wenn ein Benutzerkonto Mitglied der Gruppe ist, aber sich seine Attribute ändern, sodass es nicht mehr allen Regeln für die Gruppe entspricht, wird es als Mitglied der Gruppe entfernt.</span><span class="sxs-lookup"><span data-stu-id="f0ead-112">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="f0ead-p102">Um die dynamische Mitgliedschaft zu verwenden, müssen Sie zuerst die Sätze von Gruppen mit einem gemeinsamen Satz von Benutzerkonto-Attributen bestimmen. Beispielsweise sollten alle Mitglieder der Vertriebsabteilung Teil der Azure AD-Gruppe „Vertrieb“ sein, basierend auf dem Benutzerkonto-Attribut „Abteilung“ = „Vertrieb“.</span><span class="sxs-lookup"><span data-stu-id="f0ead-p102">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="f0ead-115">Lesen Sie die [Anweisungen, um die Regeln für eine dynamische Azure AD-Gruppe zu erstellen und zu konfigurieren](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="f0ead-115">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="f0ead-116">Die Ergebnisse dieses Schritts sind:</span><span class="sxs-lookup"><span data-stu-id="f0ead-116">The results of this step are:</span></span>

- <span data-ttu-id="f0ead-117">Ein Satz von Azure AD-Gruppen, die für die dynamische Mitgliedschaft konfiguriert werden können</span><span class="sxs-lookup"><span data-stu-id="f0ead-117">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="f0ead-118">Ein Satz von Regeln für jede dynamische Gruppe</span><span class="sxs-lookup"><span data-stu-id="f0ead-118">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="f0ead-120">Testumgebungsanleitung: Automatisieren von Lizenzen und Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="f0ead-120">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="f0ead-121">Als Zwischenprüfpunkt können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-step12) für diesen Schritt ansehen.</span><span class="sxs-lookup"><span data-stu-id="f0ead-121">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-step12) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="f0ead-122">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="f0ead-122">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="f0ead-123">Überwachen der Mandanten- und Anmeldeaktivität</span><span class="sxs-lookup"><span data-stu-id="f0ead-123">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |
