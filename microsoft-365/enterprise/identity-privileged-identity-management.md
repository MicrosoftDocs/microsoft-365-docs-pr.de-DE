---
title: 'Schritt 3: Einrichten von globalen Administratoren für den Bedarfsfall'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD Privileged Identity Management verstehen und konfigurieren
ms.openlocfilehash: d064fee82df74d8a6f1d282d80d22dd4b6c21a38
ms.sourcegitcommit: bd91ceded3921db8c56a84936889f974aa1f1528
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2018
ms.locfileid: "25994951"
---
# <a name="step-3-set-up-on-demand-global-administrators"></a><span data-ttu-id="4324f-103">Schritt 3: Einrichten von globalen Administratoren für den Bedarfsfall</span><span class="sxs-lookup"><span data-stu-id="4324f-103">Step 3: Set up on-demand global administrators</span></span>

<span data-ttu-id="4324f-104">*Dieser Schritt ist optional und gilt nur für die Versionen E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4324f-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="4324f-p101">In diesem Schritt richten Sie Azure AD Privileged Identitätsmanagement (PIM) ein, um die Zeitspanne zu verringern, in der Ihre globalen Administratorkonten anfällig für Angriffe von böswilligen Benutzern sind. PIM bietet bei Bedarf, just-in-Time Zuweisung der globalen Administratorrolle.</span><span class="sxs-lookup"><span data-stu-id="4324f-p101">In this step, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users. PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="4324f-p102">Ihre globalen Administratorkonten werden zu berechtigten Administratoren anstelle von dauerhaften Administratoren. Die globale Administratorrolle ist inaktiv, bis eine Person sie benötigt. Sie durchlaufen dann einen Aktivierungsprozess, bei dem die globale Administratorrolle für eine bestimmte Zeitspanne zum globalen Administratorkonto hinzugefügt wird. Wenn der Zeitraum abgelaufen ist, entfernt PIM die globale Administratorrolle vom globalen Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="4324f-p102">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="4324f-p103">PIM ist zusammen mit Azure Active Directory Premium P2 erhältlich, das in Microsoft 365 Enterprise E5 enthalten ist. Alternativ können Sie für Ihre globalen Administratorkonten einzelne Azure Active Directory Premium P2-Lizenzen erwerben.</span><span class="sxs-lookup"><span data-stu-id="4324f-p103">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="4324f-113">Weitere Informationen zum Aktivieren von Azure PIM für Ihren Azure AD-Mandanten und für globale Administratorkonten finden Sie unter der [Schritte zum Konfigurieren von PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="4324f-113">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="4324f-114">Weitere Informationen zum Entwickeln einer Roadmap, um den privilegierten Zugriff vor Cyberangriffen schützt, finden Sie unter [Schützen des privilegierten Zugriffs für hybride Cloudbereitstellungen in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="4324f-114">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="4324f-115">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-pim) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="4324f-115">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="4324f-116">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="4324f-116">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="4324f-117">Vereinfachen der Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="4324f-117">Simplify password resets</span></span>](identity-password-reset.md) |

