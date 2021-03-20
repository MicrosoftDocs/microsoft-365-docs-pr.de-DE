---
title: Verwalten von Microsoft 365-Benutzerkontenkennwörtern
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Erfahren Sie mehr über die Verwaltung von Microsoft 365-Benutzerkontenkennwörtern.
ms.openlocfilehash: 2062da49310121ec18f7ce21f523531f10d6df9b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905092"
---
# <a name="manage-microsoft-365-user-account-passwords"></a><span data-ttu-id="d9047-103">Verwalten von Microsoft 365-Benutzerkontenkennwörtern</span><span class="sxs-lookup"><span data-stu-id="d9047-103">Manage Microsoft 365 user account passwords</span></span>

<span data-ttu-id="d9047-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d9047-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d9047-105">Sie können Kennwörter für Microsoft 365-Benutzerkonten abhängig von Ihrer Identitätskonfiguration auf verschiedene Weise verwalten.</span><span class="sxs-lookup"><span data-stu-id="d9047-105">You can manage Microsoft 365 user account passwords in several different ways, depending on your identity configuration.</span></span> <span data-ttu-id="d9047-106">Sie können Benutzerkonten im [Microsoft 365 Admin Center,](../admin/add-users/index.yml)in Active Directory Domain Services (AD DS) oder im Azure Active Directory (Azure AD) Admin Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="d9047-106">You can manage user accounts in the [Microsoft 365 admin center](../admin/add-users/index.yml), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin center.</span></span>

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a><span data-ttu-id="d9047-107">Planen, wo und wie Sie Ihre Benutzerkontenkennwörter verwalten</span><span class="sxs-lookup"><span data-stu-id="d9047-107">Plan for where and how you will manage your user account passwords</span></span>

<span data-ttu-id="d9047-108">Wo und wie Sie Ihre Benutzerkonten verwalten können, hängt vom Identitätsmodell ab, das Sie für Microsoft 365 verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d9047-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="d9047-109">Die beiden Modelle sind nur cloud- und hybrid.</span><span class="sxs-lookup"><span data-stu-id="d9047-109">The two models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="d9047-110">Rein cloudbasiert</span><span class="sxs-lookup"><span data-stu-id="d9047-110">Cloud-only</span></span>

<span data-ttu-id="d9047-111">Sie verwalten Benutzerkontenkennwörter in:</span><span class="sxs-lookup"><span data-stu-id="d9047-111">You manage user account passwords in:</span></span>

- [<span data-ttu-id="d9047-112">Das Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="d9047-112">The Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)
- <span data-ttu-id="d9047-113">Azure AD Admin Center</span><span class="sxs-lookup"><span data-stu-id="d9047-113">The Azure AD admin center</span></span>
    
### <a name="hybrid"></a><span data-ttu-id="d9047-114">Hybrid</span><span class="sxs-lookup"><span data-stu-id="d9047-114">Hybrid</span></span>

<span data-ttu-id="d9047-115">Bei hybrider Identität werden Kennwörter in AD DS gespeichert, sodass Sie lokale AD DS-Tools zum Verwalten von Benutzerkontenkennwörtern verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="d9047-115">With hybrid identity, passwords are stored in AD DS so you must use on-premises AD DS tools to manage user account passwords.</span></span> <span data-ttu-id="d9047-116">Selbst bei Verwendung der Kennworthashsynchronisierung (Password Hash Synchronization, PHS), in der Azure AD eine Hashversion der bereits in AD DS hashierten Version speichert, müssen Sie und Benutzer ihre Kennwörter in AD DS verwalten.</span><span class="sxs-lookup"><span data-stu-id="d9047-116">Even when using Password Hash Synchronization (PHS), in which Azure AD stores a hashed version of the already hashed version in AD DS, you and users must manage their passwords in AD DS.</span></span>

<span data-ttu-id="d9047-117">Mit [dem Kennwortrückschreiben](#pw_writeback)können Ihre Benutzer ihre AD DS-Kennwörter über Azure AD ändern.</span><span class="sxs-lookup"><span data-stu-id="d9047-117">With [password writeback](#pw_writeback), your users can change their AD DS passwords through Azure AD.</span></span>

## <a name="prevent-bad-passwords"></a><span data-ttu-id="d9047-118">Verhindern unsicherer Kennwörter</span><span class="sxs-lookup"><span data-stu-id="d9047-118">Prevent bad passwords</span></span>

<span data-ttu-id="d9047-119">Alle Benutzer Ihrer Organisation sollten bei der Erstellung der Kennwörter für ihre Benutzerkonten die [Kennwortrichtlinien von Microsoft](https://www.microsoft.com/research/publication/password-guidance) anwenden.</span><span class="sxs-lookup"><span data-stu-id="d9047-119">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance) to create their user account passwords.</span></span>

<span data-ttu-id="d9047-120">Verwenden Sie den Azure AD-Kennwortschutz, der sowohl eine Liste global gesperrter Kennwörter als auch eine von Ihnen definierte optionale benutzerdefinierte Liste gesperrter Kennwörter verwendet, um Benutzer daran zu hindern, einfach zu erratende Kennwörter zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d9047-120">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="d9047-121">Hier können Sie beispielsweise Ausdrücke angeben, die für Ihre Organisation spezifisch sind, z. B.:</span><span class="sxs-lookup"><span data-stu-id="d9047-121">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="d9047-122">Markennamen</span><span class="sxs-lookup"><span data-stu-id="d9047-122">Brand names</span></span>
- <span data-ttu-id="d9047-123">Produktnamen</span><span class="sxs-lookup"><span data-stu-id="d9047-123">Product names</span></span>
- <span data-ttu-id="d9047-124">Standorte (z. B. Firmenhauptsitz)</span><span class="sxs-lookup"><span data-stu-id="d9047-124">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="d9047-125">Unternehmensspezifische interne Begriffe</span><span class="sxs-lookup"><span data-stu-id="d9047-125">Company-specific internal terms</span></span>
- <span data-ttu-id="d9047-126">Abkürzungen, die eine bestimmte Bedeutung im Unternehmen haben</span><span class="sxs-lookup"><span data-stu-id="d9047-126">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="d9047-127">Sie können ungültige Kennwörter [in der Cloud und](/azure/active-directory/authentication/concept-password-ban-bad) für Ihren lokalen AD [DS verbieten.](/azure/active-directory/authentication/concept-password-ban-bad-on-premises)</span><span class="sxs-lookup"><span data-stu-id="d9047-127">You can ban bad passwords [in the cloud](/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises AD DS](/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

## <a name="simplify-user-sign-in"></a><span data-ttu-id="d9047-128">Vereinfachen der Benutzeranmeldung</span><span class="sxs-lookup"><span data-stu-id="d9047-128">Simplify user sign-in</span></span>

<span data-ttu-id="d9047-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) funktioniert mit PHS und Pass-Through Authentication (PTA), um Ihren Benutzern die Anmeldung bei Diensten zu ermöglichen, die Azure AD-Benutzerkonten verwenden, ohne ihre Kennwörter und in vielen Fällen ihre Benutzernamen eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="d9047-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) works with PHS and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="d9047-130">Damit können Benutzer einfacher auf cloudbasierte Anwendungen wie Office 365 zugreifen, ohne dass zusätzliche lokale Komponenten wie Identitätsverbundserver notwendig sind.</span><span class="sxs-lookup"><span data-stu-id="d9047-130">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="d9047-131">Sie konfigurieren Azure AD Seamless SSO mit Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="d9047-131">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span> <span data-ttu-id="d9047-132">Lesen Sie die [Anweisungen zum Konfigurieren von Azure AD Seamless SSO](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="d9047-132">See the [instructions to configure Azure AD Seamless SSO](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a><span data-ttu-id="d9047-133">Vereinfachen von Kennwortupdates für AD DS</span><span class="sxs-lookup"><span data-stu-id="d9047-133">Simplify password updates to AD DS</span></span>

<span data-ttu-id="d9047-134">Mit dem Kennwortrückschreiben können Sie Benutzern das Zurücksetzen ihrer Kennwörter über Azure AD ermöglichen, das dann in AD DS repliziert wird.</span><span class="sxs-lookup"><span data-stu-id="d9047-134">With password writeback, you can allow users to reset their passwords through Azure AD, which is then replicated to AD DS.</span></span> <span data-ttu-id="d9047-135">Benutzer müssen nicht auf ihre lokale AD DS zugreifen, um ihre Kennwörter zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d9047-135">Users don’t need to access their on-premises AD DS to update their passwords.</span></span> <span data-ttu-id="d9047-136">Dies ist für Roaming- oder Remote-Benutzer nützlich, die keine Remote-Zugriffsverbindung zum lokalen Netzwerk haben.</span><span class="sxs-lookup"><span data-stu-id="d9047-136">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="d9047-137">Das Kennwortrückschreiben ist erforderlich für die vollständige Nutzung von Azure AD Identity Protection, z. B. um zu verlangen, dass Benutzer ihre lokalen Kennwörter ändern, wenn ein hohes Risiko einer Kontogefährdung besteht.</span><span class="sxs-lookup"><span data-stu-id="d9047-137">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="d9047-138">Weitere Informationen und Hinweise zur Konfiguration finden Sie unter [Azure AD SSPR mit Kennwortrückschreiben](/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="d9047-138">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="d9047-p108">Führen Sie ein Upgrade auf die neueste Version von Azure AD Connect durch, um das bestmögliche Benutzererlebnis und die Verfügbarkeit neuer Features sicherzustellen, sobald diese veröffentlicht werden. Weitere Informationen finden Sie unter [Benutzerdefinierte Installation von Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="d9047-p108">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

## <a name="simplify-password-resets"></a><span data-ttu-id="d9047-141">Vereinfachen der Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="d9047-141">Simplify password resets</span></span>

<span data-ttu-id="d9047-142">Mit der Self-Service Password Reset (SSPR) können Benutzer ihre Kennwörter oder Konten zurücksetzen oder entsperren.</span><span class="sxs-lookup"><span data-stu-id="d9047-142">Self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="d9047-143">Um über eine fehlerhafte oder missbräuchliche Nutzung informiert zu werden, können Sie die ausführliche Berichterstellung verwenden, bei der der Benutzerzugriff auf das System nachverfolgt wird.</span><span class="sxs-lookup"><span data-stu-id="d9047-143">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="d9047-144">Sie müssen das [Kennwortrückschreiben aktivieren,](#pw_writeback) bevor Sie Kennwortzurücksetzungen bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="d9047-144">You must enable [password writeback](#pw_writeback) before you can deploy password resets.</span></span>

<span data-ttu-id="d9047-145">Lesen Sie die [Anweisungen zum Rollout der Kennwortzurücksetzung](/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="d9047-145">See the [instructions to roll out password reset](/azure/active-directory/authentication/howto-sspr-deployment).</span></span>