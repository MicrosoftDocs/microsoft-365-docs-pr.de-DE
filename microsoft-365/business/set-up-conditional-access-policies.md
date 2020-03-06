---
title: Einrichten von Richtlinien für bedingten Zugriff für Microsoft 365-Kampagnen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
description: In diesem Artikel erfahren Sie, wie Sie Richtlinien für bedingten Zugriff für Microsoft 365-Kampagnen einrichten, um erhebliche zusätzliche Sicherheit zu erhalten.
ms.openlocfilehash: be3ca0da3d27e3ec49f1227e4482cfd7fcaae8cb
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550075"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="c7129-103">Einrichten von Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="c7129-103">Set up conditional access policies</span></span>

<span data-ttu-id="c7129-104">[Bedingte Zugriffs](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) Richtlinien fügen erhebliche zusätzliche Sicherheit hinzu.</span><span class="sxs-lookup"><span data-stu-id="c7129-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="c7129-105">Microsoft stellt eine Reihe von Baseline-bedingten Zugriffsrichtlinien bereit, die für alle Kunden empfohlen werden.</span><span class="sxs-lookup"><span data-stu-id="c7129-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="c7129-106">Baseline-Richtlinien sind eine Reihe von vordefinierten Richtlinien, die Organisationen vor zahlreichen häufigen Angriffen schützen sollen.</span><span class="sxs-lookup"><span data-stu-id="c7129-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="c7129-107">Diese häufigen Angriffe können Kenn Wort Spray, Wiedergabe und Phishing umfassen.</span><span class="sxs-lookup"><span data-stu-id="c7129-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="c7129-108">Für diese Richtlinien müssen Administratoren und Benutzer eine zweite Authentifizierungsform (die als mehrstufige Authentifizierung bezeichnet wird, oder MFA) eingeben, wenn bestimmte Bedingungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="c7129-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="c7129-109">Wenn sich ein Benutzer beispielsweise von einem anderen Land aus anmeldet, wird die Anmeldung möglicherweise als riskant betrachtet, und der Benutzer muss eine zusätzliche Authentifizierungsform bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c7129-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="c7129-110">Derzeit umfassen Baseline-Richtlinien Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c7129-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="c7129-111">Für **Administratoren** &ndash; erfordert die mehrstufige Authentifizierung für die privilegierten Administratorrollen, einschließlich des globalen Administrators.</span><span class="sxs-lookup"><span data-stu-id="c7129-111">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="c7129-112">Der **Endbenutzer Schutz** &ndash; erfordert mehrstufige Authentifizierung für Benutzer nur, wenn eine Anmeldung riskant ist.</span><span class="sxs-lookup"><span data-stu-id="c7129-112">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="c7129-113">**Legacy Authentifizierung** &ndash; blockieren ältere Client-apps und einige neue Apps verwenden keine neueren, sichereren Authentifizierungsprotokolle.</span><span class="sxs-lookup"><span data-stu-id="c7129-113">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="c7129-114">Diese älteren Apps können Richtlinien für bedingten Zugriff umgehen und nicht autorisierten Zugriff auf Ihre Umgebung erlangen.</span><span class="sxs-lookup"><span data-stu-id="c7129-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="c7129-115">Diese Richtlinie blockiert den Zugriff von Clients, die keinen bedingten Zugriff unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c7129-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="c7129-116">Für die **Verwaltung von MFA for Service Management** &ndash; ist eine mehrstufige Authentifizierung für den Zugriff auf Verwaltungstools erforderlich, einschließlich des Azure-Portals (in dem Sie Basisrichtlinien konfigurieren).</span><span class="sxs-lookup"><span data-stu-id="c7129-116">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="c7129-117">Microsoft empfiehlt, alle diese Basisrichtlinien zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c7129-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="c7129-118">Nachdem diese Richtlinien aktiviert wurden, werden Administratoren und Benutzer aufgefordert, sich für die Azure multii-Factor Authentication zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="c7129-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="c7129-119">Weitere Informationen zu diesen Richtlinien finden Sie unter [Was sind Basisrichtlinien](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span><span class="sxs-lookup"><span data-stu-id="c7129-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="c7129-120">Einrichten von Baseline-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="c7129-120">Set up baseline policies</span></span>

1. <span data-ttu-id="c7129-121">Wechseln Sie [zu Azure-Portal](https://portal.azure.com), und navigieren Sie dann zu **Azure Active Directory** \> **bedingten Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="c7129-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="c7129-122">Die Basisrichtlinien werden auf der Seite aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c7129-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="c7129-123">![Seite, auf der Basisrichtlinien für bedingten Zugriff aufgelistet werden.](../media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="c7129-123">![Page that lists baseline policies for conditional access.](../media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="c7129-124">Lesen Sie die folgenden spezifischen Anweisungen für jede Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="c7129-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="c7129-125">MFA für Administratoren erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7129-125">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="c7129-126">MFA für Benutzer erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7129-126">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="c7129-127">Legacy Authentifizierung blockieren</span><span class="sxs-lookup"><span data-stu-id="c7129-127">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="c7129-128">MFA für Service Management erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7129-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="c7129-129">Sie können viele zusätzliche Richtlinien einrichten, beispielsweise das Anfordern von genehmigten Client-apps.</span><span class="sxs-lookup"><span data-stu-id="c7129-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="c7129-130">Weitere Informationen finden Sie in der [Dokumentation zum bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="c7129-130">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
