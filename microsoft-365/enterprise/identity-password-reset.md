---
title: 'Schritt 5: Vereinfachen des Zugriffs für Benutzer'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und konfigurieren Sie die Self-Service-Kennwortzurücksetzung (Self-Service Password Reset, SSPR) für Azure AD.
ms.openlocfilehash: ec81b2931fd4ad599ffcf983ea8a7d764c56404a
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981796"
---
# <a name="step-5-simplify-access-for-users"></a><span data-ttu-id="cf45b-103">Schritt 5: Vereinfachen des Zugriffs für Benutzer</span><span class="sxs-lookup"><span data-stu-id="cf45b-103">Step 5: Simplify access for users</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a><span data-ttu-id="cf45b-104">Vereinfachen der Kennwortaktualisierungen</span><span class="sxs-lookup"><span data-stu-id="cf45b-104">Simplify password updates</span></span>

<span data-ttu-id="cf45b-105">*Dieser Schritt ist optional für Hybridumgebungen und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="cf45b-105">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="cf45b-106">In diesem Abschnitt können Sie können Sie festlegen, dass Benutzer ihre Kennwörter über Azure Active Directory (Azure AD) zurücksetzen können, das dann in Ihre lokalen Active Directory Domain Services (AD DS) repliziert wird.</span><span class="sxs-lookup"><span data-stu-id="cf45b-106">In this section, you'll allow users to reset their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="cf45b-107">Dieser Vorgang wird als Rückschreiben des Kennworts bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="cf45b-107">This process is known as password writeback.</span></span> <span data-ttu-id="cf45b-108">Mit der Kennwortrückschreibung brauchen Benutzer ihre Kennwörter nicht mehr über den lokalen AD-DS zu aktualisieren, auf dem ihre Benutzerkonten und Attribute gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="cf45b-108">With password writeback, users don’t need to update their passwords through the on-premises Active Directory Domain Services (AD DS) where user accounts and their attributes are stored.</span></span> <span data-ttu-id="cf45b-109">Dies ist für Roaming- oder Remote-Benutzer nützlich, die keine Remote-Zugriffsverbindung zum lokalen Netzwerk haben.</span><span class="sxs-lookup"><span data-stu-id="cf45b-109">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="cf45b-110">Das Kennwortrückschreiben ist erforderlich für die vollständige Nutzung von Azure AD Identity Protection, z. B. um zu verlangen, dass Benutzer ihre lokalen Kennwörter ändern, wenn ein hohes Risiko einer Kontogefährdung besteht.</span><span class="sxs-lookup"><span data-stu-id="cf45b-110">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="cf45b-111">Weitere Informationen und Hinweise zur Konfiguration finden Sie unter [Azure AD SSPR mit Kennwortrückschreiben](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="cf45b-111">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="cf45b-p102">Führen Sie ein Upgrade auf die neueste Version von Azure AD Connect durch, um das bestmögliche Benutzererlebnis und die Verfügbarkeit neuer Features sicherzustellen, sobald diese veröffentlicht werden. Weitere Informationen finden Sie unter [Benutzerdefinierte Installation von Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="cf45b-p102">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="cf45b-115">Testumgebungsanleitung: Rückschreiben des Kennworts</span><span class="sxs-lookup"><span data-stu-id="cf45b-115">Test Lab Guide: Password writeback</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="cf45b-116">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-pw-writeback) für diesen Abschnitt betrachten.</span><span class="sxs-lookup"><span data-stu-id="cf45b-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this section.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="cf45b-117">Vereinfachen der Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="cf45b-117">Simplify password resets</span></span>

<span data-ttu-id="cf45b-118">*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="cf45b-118">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="cf45b-119">In diesem Abschnitt können Sie mit der Self-Service-Kennwortzurücksetzung (SSPR) Benutzern erlauben, ihre Kennwörter oder Konten zurückzusetzen oder zu entsperren.</span><span class="sxs-lookup"><span data-stu-id="cf45b-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="cf45b-120">Um über eine fehlerhafte oder missbräuchliche Nutzung informiert zu werden, können Sie die ausführliche Berichterstellung verwenden, bei der der Benutzerzugriff auf das System nachverfolgt wird.</span><span class="sxs-lookup"><span data-stu-id="cf45b-120">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="cf45b-121">Sie müssen das Rückschreiben des Kennworts aktivieren, bevor Sie das Zurücksetzen von Kennwörtern bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="cf45b-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="cf45b-122">Lesen Sie die [Anweisungen zum Rollout der Kennwortzurücksetzung](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="cf45b-122">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="cf45b-124">Leitfaden für Testlabor: Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="cf45b-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="cf45b-125">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-pw-reset) für diesen Abschnitt betrachten.</span><span class="sxs-lookup"><span data-stu-id="cf45b-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this section.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="cf45b-126">Vereinfachen der Benutzeranmeldung</span><span class="sxs-lookup"><span data-stu-id="cf45b-126">Simplify user sign-in</span></span>

<span data-ttu-id="cf45b-127">*Dieser Schritt ist optional für Hybridumgebungen und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="cf45b-127">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="cf45b-128">In diesem Abschnitt werden Sie das nahtlose einmalige Anmelden von Azure Active Directory einrichten, damit sich Benutzer bei Diensten anmelden können, die Azure AD-Benutzerkonten verwenden, ohne ihre Kennwörter und in vielen Fällen ohne ihre Benutzernamen angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="cf45b-128">In this section, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="cf45b-129">Damit können Benutzer einfacher auf cloudbasierte Anwendungen wie Office 365 zugreifen, ohne dass zusätzliche lokale Komponenten wie Identitätsverbundserver notwendig sind.</span><span class="sxs-lookup"><span data-stu-id="cf45b-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="cf45b-130">Sie konfigurieren Azure AD Seamless SSO mit Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="cf45b-130">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="cf45b-131">Lesen Sie die [Anweisungen zum Konfigurieren von Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="cf45b-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="cf45b-133">Testumgebungsanleitung: Nahtloses einmaliges Anmelden in Azure AD</span><span class="sxs-lookup"><span data-stu-id="cf45b-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="cf45b-134">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-sso) für diesen Abschnitt betrachten.</span><span class="sxs-lookup"><span data-stu-id="cf45b-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this section.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="cf45b-135">Anpassen der Office 365-Anmeldeseite</span><span class="sxs-lookup"><span data-stu-id="cf45b-135">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="cf45b-136">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="cf45b-136">*This is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="cf45b-137">In diesem Abschnitt werden Sie den Unternehmensnamen, das Logo und andere erkennbare Elemente zu der Anmeldeseite Ihrer Organisation hinzufügen, damit Benutzer diese als solche erkennen.</span><span class="sxs-lookup"><span data-stu-id="cf45b-137">In this section, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="cf45b-138">Mit Microsoft 365 Enterprise können Sie die Darstellung der Anmeldeseite und der Zugriffsbereichsseiten anpassen, damit sie Unternehmenslogo, Farbschemas und angepasste Benutzerinformationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="cf45b-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="cf45b-139">Weitere Informationen finden Sie unter [Hinzufügen Ihres Unternehmensbrandings zur Anmeldeseite von Office 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span><span class="sxs-lookup"><span data-stu-id="cf45b-139">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="cf45b-140">Anweisungen zur Konfiguration finden Sie unter [Hinzufügen Ihres Unternehmensbrandings zur Anmeldeseite und zu Zugriffsbereichsseiten](http://aka.ms/aadpaddbranding).</span><span class="sxs-lookup"><span data-stu-id="cf45b-140">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="cf45b-141">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-custom-sign-in) für diesen Abschnitt betrachten.</span><span class="sxs-lookup"><span data-stu-id="cf45b-141">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="cf45b-142">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="cf45b-142">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="cf45b-143">Verwenden von Gruppen zur einfacheren Verwaltung</span><span class="sxs-lookup"><span data-stu-id="cf45b-143">Use groups for easier management</span></span>](identity-self-service-group-management.md) |


