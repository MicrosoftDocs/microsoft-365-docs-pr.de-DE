---
title: 'Schritt 10: Vereinfachen der Benutzeranmeldung'
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
description: Verstehen und konfigurieren Sie Azure AD Seamless Single Sign-On (Seamless SSO).
ms.openlocfilehash: 9d18cb559d3a4a9ee401e0f94fb53bc6360d88c8
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868102"
---
# <a name="step-10-simplify-user-sign-in"></a><span data-ttu-id="84680-103">Schritt 10: Vereinfachen der Benutzeranmeldung</span><span class="sxs-lookup"><span data-stu-id="84680-103">Step 10: Simplify user sign-in</span></span>

<span data-ttu-id="84680-104">*Dieser Schritt ist optional für Hybridumgebungen und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="84680-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="84680-p101">In diesem Schritt richten Sie Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) ein, damit Ihre Benutzer sich bei Diensten anmelden können, die Azure AD-Benutzerkonten verwenden, ohne ihre Kennwörter eingeben zu müssen, und in vielen Fällen ihre Benutzernamen. Damit erhalten die Benutzer einfacheren Zugriff auf cloudbasierte Anwendungen, z. B. Office 365, ohne dass zusätzliche lokale Komponenten wie Identitätsverbundserver erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="84680-p101">In Step 8, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames. This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="84680-107">Sie konfigurieren Azure AD Seamless SSO mit Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="84680-107">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="84680-108">Lesen Sie die [Anweisungen zum Konfigurieren von Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="84680-108">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="84680-110">Testumgebungsanleitung: Nahtloses einmaliges Anmelden in Azure AD</span><span class="sxs-lookup"><span data-stu-id="84680-110">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="84680-111">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-sso) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="84680-111">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="84680-112">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="84680-112">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="84680-113">Anpassen der Office 365-Anmeldeseite</span><span class="sxs-lookup"><span data-stu-id="84680-113">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |

