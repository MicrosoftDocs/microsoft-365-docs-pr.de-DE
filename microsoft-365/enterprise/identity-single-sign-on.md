---
title: 'Schritt 8: Vereinfachen der Benutzeranmeldung'
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
ms.openlocfilehash: 40158532638e3ebb7aab9aef73f9bae4a8375210
ms.sourcegitcommit: f0472e1b4bba523d7471add996ed70eb562c1b03
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2018
ms.locfileid: "22924399"
---
# <a name="step-8-simplify-user-sign-in"></a><span data-ttu-id="e742c-103">Schritt 8: Vereinfachen der Benutzeranmeldung</span><span class="sxs-lookup"><span data-stu-id="e742c-103">Step 8: Simplify user sign-in</span></span>

<span data-ttu-id="e742c-104">*Dieser Schritt ist optional für Hybridumgebungen und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e742c-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="e742c-p101">In Schritt 8 richten Sie Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) ein, damit Ihre Benutzer sich bei Diensten anmelden können, die Azure AD-Benutzerkonten verwenden, ohne ihre Kennwörter eingeben zu müssen, und in vielen Fällen ihre Benutzernamen. Damit erhalten die Benutzer einfacheren Zugriff auf cloudbasierte Anwendungen, z. B. Office 365, ohne dass zusätzliche lokale Komponenten wie Identitätsverbundserver erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e742c-p101">In Step 8, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames. This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="e742c-107">Sie konfigurieren Azure AD Seamless SSO mit Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="e742c-107">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="e742c-108">Lesen Sie die [Anweisungen zum Konfigurieren von Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="e742c-108">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

<span data-ttu-id="e742c-109">Unter [Kernkonzepte](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-365-policies-configurations#core-concepts) finden Sie weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="e742c-109">See [Core Concepts](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-365-policies-configurations#core-concepts) for additional information.</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="e742c-111">Testumgebungsanleitung: Nahtloses einmaliges Anmelden in Azure AD</span><span class="sxs-lookup"><span data-stu-id="e742c-111">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="e742c-112">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-step8) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="e742c-112">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-step8) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="e742c-113">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="e742c-113">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="e742c-114">Vereinfachen der Kennwortaktualisierungen</span><span class="sxs-lookup"><span data-stu-id="e742c-114">Simplify password updates</span></span>](identity-password-writeback.md) |

