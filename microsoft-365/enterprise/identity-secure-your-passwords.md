---
title: 'Schritt 2: Schützen von Kennwörtern'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Sie müssen für Ihre gesamte Organisation sichere Kennwörter verwenden, und die Kennwortverwaltung einfach gestalten.
ms.openlocfilehash: c0ad9e2ad86cb803484e3d350fe112580610f509
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633093"
---
# <a name="step-2-secure-your-passwords"></a><span data-ttu-id="d45e4-103">Schritt 2: Schützen von Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="d45e4-103">Step 2: Secure your passwords</span></span>

![Phase 2: Identität](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a><span data-ttu-id="d45e4-105">Verhindern unsicherer Kennwörter</span><span class="sxs-lookup"><span data-stu-id="d45e4-105">Prevent bad passwords</span></span>

<span data-ttu-id="d45e4-106">*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="d45e4-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="d45e4-107">Alle Benutzer Ihrer Organisation sollten bei der Erstellung der Kennwörter für ihre Benutzerkonten die [Kennwortrichtlinien von Microsoft](https://www.microsoft.com/research/publication/password-guidance/) anwenden.</span><span class="sxs-lookup"><span data-stu-id="d45e4-107">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance/) to create their user account passwords.</span></span>

<span data-ttu-id="d45e4-108">Verwenden Sie den Azure AD-Kennwortschutz, der sowohl eine Liste global gesperrter Kennwörter als auch eine von Ihnen definierte optionale benutzerdefinierte Liste gesperrter Kennwörter verwendet, um Benutzer daran zu hindern, einfach zu erratende Kennwörter zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d45e4-108">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="d45e4-109">Hier können Sie beispielsweise Ausdrücke angeben, die für Ihre Organisation spezifisch sind, z. B.:</span><span class="sxs-lookup"><span data-stu-id="d45e4-109">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="d45e4-110">Markennamen</span><span class="sxs-lookup"><span data-stu-id="d45e4-110">Brand names</span></span>
- <span data-ttu-id="d45e4-111">Produktnamen</span><span class="sxs-lookup"><span data-stu-id="d45e4-111">Product names</span></span>
- <span data-ttu-id="d45e4-112">Standorte (z. B. Firmenhauptsitz)</span><span class="sxs-lookup"><span data-stu-id="d45e4-112">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="d45e4-113">Unternehmensspezifische interne Begriffe</span><span class="sxs-lookup"><span data-stu-id="d45e4-113">Company-specific internal terms</span></span>
- <span data-ttu-id="d45e4-114">Abkürzungen, die eine bestimmte Bedeutung im Unternehmen haben</span><span class="sxs-lookup"><span data-stu-id="d45e4-114">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="d45e4-115">Sie können unsichere Kennwörter [in der Cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) und für Ihre [lokalen Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) sperren.</span><span class="sxs-lookup"><span data-stu-id="d45e4-115">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

<span data-ttu-id="d45e4-116">Als Zwischenprüfung können Sie sich die [Abschlusskriterien](identity-exit-criteria.md#crit-password-prot) für diesen Abschnitt ansehen.</span><span class="sxs-lookup"><span data-stu-id="d45e4-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-password-prot) for this section.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="d45e4-117">Vereinfachen der Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="d45e4-117">Simplify password resets</span></span>

<span data-ttu-id="d45e4-118">*Dies ist optional und gilt für die Versionen E3 und E5 von Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="d45e4-118">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="d45e4-119">In diesem Abschnitt können Sie mit der Self-Service-Kennwortzurücksetzung (SSPR) Benutzern erlauben, ihre Kennwörter oder Konten zurückzusetzen oder zu entsperren.</span><span class="sxs-lookup"><span data-stu-id="d45e4-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="d45e4-120">Um über eine fehlerhafte oder missbräuchliche Nutzung informiert zu werden, können Sie die ausführliche Berichterstellung verwenden, bei der der Benutzerzugriff auf das System nachverfolgt wird.</span><span class="sxs-lookup"><span data-stu-id="d45e4-120">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="d45e4-121">Sie müssen das Rückschreiben des Kennworts aktivieren, bevor Sie das Zurücksetzen von Kennwörtern bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="d45e4-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="d45e4-122">Lesen Sie die [Anweisungen zum Rollout der Kennwortzurücksetzung](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="d45e4-122">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d45e4-124">Leitfaden für Testlabor: Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="d45e4-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="d45e4-125">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-pw-reset) für diesen Abschnitt betrachten.</span><span class="sxs-lookup"><span data-stu-id="d45e4-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this section.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="d45e4-126">Vereinfachen der Benutzeranmeldung</span><span class="sxs-lookup"><span data-stu-id="d45e4-126">Simplify user sign-in</span></span>

<span data-ttu-id="d45e4-127">*Dieser Schritt ist optional für Hybridumgebungen und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d45e4-127">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d45e4-128">In diesem Abschnitt werden Sie das nahtlose einmalige Anmelden von Azure Active Directory einrichten, das mit der Kennworthashsynchronisierung (PHS) und der Passthrough-Authentifizierung (PTA) verwendet werden kann, damit sich Benutzer bei Diensten anmelden können, die Azure AD-Benutzerkonten verwenden, ohne ihre Kennwörter und in vielen Fällen ohne ihre Benutzernamen angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="d45e4-128">In this section, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO), which works with Password Hash Synchronization (PHS) and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="d45e4-129">Damit können Benutzer einfacher auf cloudbasierte Anwendungen wie Office 365 zugreifen, ohne dass zusätzliche lokale Komponenten wie Identitätsverbundserver notwendig sind.</span><span class="sxs-lookup"><span data-stu-id="d45e4-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="d45e4-130">Sie konfigurieren Azure AD Seamless SSO mit Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="d45e4-130">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="d45e4-131">Lesen Sie die [Anweisungen zum Konfigurieren von Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="d45e4-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="d45e4-133">Testumgebungsanleitung: Nahtloses einmaliges Anmelden in Azure AD</span><span class="sxs-lookup"><span data-stu-id="d45e4-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="d45e4-134">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-sso) für diesen Abschnitt betrachten.</span><span class="sxs-lookup"><span data-stu-id="d45e4-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this section.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="d45e4-135">Anpassen der Office 365-Anmeldeseite</span><span class="sxs-lookup"><span data-stu-id="d45e4-135">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="d45e4-136">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d45e4-136">*This is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d45e4-137">In diesem Abschnitt werden Sie den Unternehmensnamen, das Logo und andere erkennbare Elemente zu der Anmeldeseite Ihrer Organisation hinzufügen, damit Benutzer diese als solche erkennen.</span><span class="sxs-lookup"><span data-stu-id="d45e4-137">In this section, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="d45e4-138">Mit Microsoft 365 Enterprise können Sie die Darstellung der Anmeldeseite und der Zugriffsbereichsseiten anpassen, damit sie Unternehmenslogo, Farbschemas und angepasste Benutzerinformationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d45e4-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="d45e4-139">Weitere Informationen finden Sie unter [Hinzufügen Ihres Unternehmensbrandings zur Anmeldeseite von Office 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span><span class="sxs-lookup"><span data-stu-id="d45e4-139">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="d45e4-140">Anweisungen zur Konfiguration finden Sie unter [Hinzufügen Ihres Unternehmensbrandings zur Anmeldeseite und zu Zugriffsbereichsseiten](https://aka.ms/aadpaddbranding).</span><span class="sxs-lookup"><span data-stu-id="d45e4-140">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](https://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="d45e4-141">Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-custom-sign-in) für diesen Abschnitt betrachten.</span><span class="sxs-lookup"><span data-stu-id="d45e4-141">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="d45e4-142">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d45e4-142">Next step</span></span>

|||
|:-------|:-----|
|![Schritt 3](../media/stepnumbers/Step3.png)| [<span data-ttu-id="d45e4-144">Absichern und Verwalten von Benutzeranmeldungen</span><span class="sxs-lookup"><span data-stu-id="d45e4-144">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
