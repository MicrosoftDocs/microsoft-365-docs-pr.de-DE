---
title: 'Microsoft 365 Client App Support: Mehrstufige Authentifizierung'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie, welche Plattformen, Clients und PowerShell-Module die mehrstufige Authentifizierung für Microsoft 365 unterstützen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 80ee370526d17d472cd048cd4d89b862e158b631
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927561"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a><span data-ttu-id="0b47e-103">Microsoft 365 Client App Support: Mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0b47e-103">Microsoft 365 Client App Support: Multi-factor authentication</span></span>

<span data-ttu-id="0b47e-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="0b47e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0b47e-105">Um ein zusätzliches Maß an Sicherheit für Anmeldungen zu bieten, können Clients für die Verwendung der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA) konfiguriert werden, die sowohl ein Benutzerkennwort als auch eine andere Benutzerüberprüfungsmethode verwendet, basierend auf:</span><span class="sxs-lookup"><span data-stu-id="0b47e-105">To provide an additional level of security for sign-ins, clients may be configured to use multi-factor authentication (MFA), which uses both a user password and another user verification method based on:</span></span>

- <span data-ttu-id="0b47e-106">Etwas, das sich in ihrem Besitz befindet, das nicht einfach dupliziert werden kann, z. B. ein Smartphone.</span><span class="sxs-lookup"><span data-stu-id="0b47e-106">Something  in their possession that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="0b47e-107">Etwas, das der Benutzer eindeutig und biometrisch besitzt, z. B. fingerabdrücke, Gesichtsdaten oder andere biometrische Attribute</span><span class="sxs-lookup"><span data-stu-id="0b47e-107">Something the user has uniquely and biologically, such as their fingerprints, face, or other biometric attribute</span></span>

<span data-ttu-id="0b47e-108">Erfahren Sie mehr [über die mehrstufige Authentifizierung](/azure/active-directory/authentication/multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="0b47e-108">Learn more about [multi-factor authentication](/azure/active-directory/authentication/multi-factor-authentication).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="0b47e-109">Unterstützte Clients & Plattformen</span><span class="sxs-lookup"><span data-stu-id="0b47e-109">Supported clients & platforms</span></span>

<span data-ttu-id="0b47e-110">Die neuesten Versionen der folgenden Clients und Plattformen unterstützen die mehrstufige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="0b47e-110">The latest versions of the following clients and platforms support multi-factor authentication.</span></span> <span data-ttu-id="0b47e-111">Weitere Informationen zur Plattformunterstützung in Microsoft 365 finden Sie unter [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span><span class="sxs-lookup"><span data-stu-id="0b47e-111">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="0b47e-112">Unterstützte PowerShell-Module</span><span class="sxs-lookup"><span data-stu-id="0b47e-112">Supported PowerShell modules</span></span>

- [<span data-ttu-id="0b47e-113">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b47e-113">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="0b47e-114">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b47e-114">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="0b47e-115">SharePoint Online-PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b47e-115">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)