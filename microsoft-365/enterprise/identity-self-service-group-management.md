---
title: 'Schritt 14: Zulassen der Erstellung und Verwaltung von eigenen Gruppen für Benutzer'
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
description: Informationen zum Verständnis und zur Konfiguration der Self-Service-Gruppenverwaltung in Azure AD.
ms.openlocfilehash: d46e82fd72b8eef896a223229a2cc3d25ae56c76
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867888"
---
# <a name="step-14-allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="34c6d-103">Schritt 14: Zulassen der Erstellung und Verwaltung von eigenen Gruppen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="34c6d-103">Step 14: Allow users to create and manage their own groups</span></span>

<span data-ttu-id="34c6d-104">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="34c6d-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="34c6d-p101">In diesem Schritt werden Sie Azure Active Directory (AD)-Gruppen identifizieren, die von Gruppenbesitzern, statt von IT-Administratoren, verwaltet werden können. Mit diesem als *Self-Service-Gruppenverwaltung* bezeichneten Feature können Gruppenbesitzer, denen keine Administratorrolle zugewiesen ist, Sicherheitsgruppen erstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="34c6d-p101">In Step 14, you'll identify Azure Active Directory (AD) groups that can be managed by group owners instead of IT administrators. Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="34c6d-p102">Benutzer können die Mitgliedschaft in einer Sicherheitsgruppe anfordern, und die Anforderung wird an den Gruppenbesitzer gesendet, statt an den IT-Administrator. So kann die tägliche Kontrolle über Gruppenmitgliedschaften an die Team-, Projekt- oder Unternehmensbesitzer delegiert werden, die die geschäftliche Verwendung für die Gruppe verstehen und die Mitgliedschaften verwalten können.</span><span class="sxs-lookup"><span data-stu-id="34c6d-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="34c6d-p103">Die Self-Service-Gruppenverwaltung steht nur für Azure AD-Sicherheits- und Office 365-Gruppen zur Verfügung. Sie steht nicht für E-Mail-aktivierte Gruppen, Verteilerlisten oder Gruppen zur Verfügung, die mit lokalem Windows Server Active Directory (AD) synchronisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="34c6d-p103">Self-service group management is available only for Azure AD security and Office 365 groups. It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Windows Server Active Directory (AD).</span></span>
>

<span data-ttu-id="34c6d-111">Weitere Informationen finden Sie in den [Anweisungen zum Konfigurieren einer Azure AD-Gruppe für Self-Service-Verwaltung](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="34c6d-111">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="34c6d-112">Als Zwischenprüfpunkt können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-self-service-groups) für diesen Schritt ansehen.</span><span class="sxs-lookup"><span data-stu-id="34c6d-112">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="34c6d-113">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="34c6d-113">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step15.png)| [<span data-ttu-id="34c6d-114">Einrichten der dynamischen Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="34c6d-114">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md) |
