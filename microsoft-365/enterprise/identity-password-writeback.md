---
title: 'Schritt 9: Vereinfachen der Kennwortaktualisierungen'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und konfigurieren Sie das Kennwortrückschreiben für Hybridumgebungen.
ms.openlocfilehash: 79f4b1077e5700903b1c52141ef6923e5c574d5b
ms.sourcegitcommit: 42645d5b15fd8698d116745f3b0d7943887e5a2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2018
ms.locfileid: "26644236"
---
# <a name="step-9-simplify-password-updates"></a><span data-ttu-id="a6b11-103">Schritt 9: Vereinfachen der Kennwortaktualisierungen</span><span class="sxs-lookup"><span data-stu-id="a6b11-103">Step 9: Simplify password updates</span></span>

<span data-ttu-id="a6b11-104">*Dieser Schritt ist optional für Hybridumgebungen und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a6b11-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="a6b11-p101">In diesem Schritt erlauben Sie Benutzern, ihre Kennwörter über Azure Active Directory (AD) zurückzusetzen, das dann zu Ihrem lokalen Windows Server Active Directory (AD) repliziert wird. Dieser Prozess ist als Kennwortrückschreiben bekannt. Dank dem Kennwortrückschreiben müssen Benutzer ihre Kennwörter nicht über das lokale Windows Server AD aktualisieren, wo Benutzerkonten und ihre Attribute gespeichert sind. Dies ist für Roaming- oder Remote-Benutzer nützlich, die keine Remote-Zugriffsverbindung zum lokalen Netzwerk haben.</span><span class="sxs-lookup"><span data-stu-id="a6b11-p101">In Step 9, you'll allow users to reset their passwords through Azure Active Directory (AD), which is then replicated to your local Windows Server Active Directory (AD). This process is known as password writeback. With password writeback, users don’t need to update their passwords through the on-premises Windows Server AD where user accounts and their attributes are stored. This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="a6b11-109">Das Kennwortrückschreiben ist erforderlich für die vollständige Nutzung von Identity Protection-Features, z. B. um zu verlangen, dass Benutzer ihre lokalen Kennwörter ändern, wenn ein hohes Risiko einer Kontogefährdung besteht.</span><span class="sxs-lookup"><span data-stu-id="a6b11-109">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="a6b11-110">Weitere Informationen und Hinweise zur Konfiguration finden Sie unter [Azure AD SSPR mit Kennwortrückschreiben](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="a6b11-110">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="a6b11-p102">Führen Sie ein Upgrade auf die neueste Version von Azure AD Connect durch, um das bestmögliche Benutzererlebnis und die Verfügbarkeit neuer Features sicherzustellen, sobald diese veröffentlicht werden. Weitere Informationen finden Sie unter [Benutzerdefinierte Installation von Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="a6b11-p102">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>


|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="a6b11-114">Testumgebungsanleitung: Rückschreiben des Kennworts</span><span class="sxs-lookup"><span data-stu-id="a6b11-114">Test Lab Guide: Password reset</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="a6b11-115">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-pw-writeback) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="a6b11-115">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="a6b11-116">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="a6b11-116">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="a6b11-117">Vereinfachen der Benutzeranmeldung</span><span class="sxs-lookup"><span data-stu-id="a6b11-117">Simplify user sign-in</span></span>](identity-single-sign-on.md) |

