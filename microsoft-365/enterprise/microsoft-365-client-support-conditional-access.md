---
title: 'Microsoft 365 Client-App-Unterstützung: Bedingter Zugriff'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie, welche Plattformen, Clients und PowerShell-Module bedingte Access für Microsoft 365 unterstützen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 763380429b8643c5dd01971117fccb040a9a0210
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286561"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a><span data-ttu-id="295b4-103">Microsoft 365 Client-App-Unterstützung: Bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="295b4-103">Microsoft 365 Client App Support: Conditional Access</span></span>

<span data-ttu-id="295b4-104">Am modernen Arbeitsplatz können Benutzer von überall aus mit verschiedenen Geräten und Apps auf die Ressourcen Ihrer Organisation zugreifen.</span><span class="sxs-lookup"><span data-stu-id="295b4-104">In the modern workplace, users can access your organization's resources using various devices and apps from anywhere.</span></span> <span data-ttu-id="295b4-105">Daher reicht es nicht mehr aus, sich nur darauf zu konzentrieren, wer auf eine Ressource zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="295b4-105">As a result, just focusing on who can access a resource is not sufficient anymore.</span></span> <span data-ttu-id="295b4-106">Ihre Organisation muss auch unterstützen, wie und wo in Ihrer Zugriffssteuerungsinfrastruktur auf eine Ressource zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="295b4-106">Your organization must also support how and where a resource is accessed in your access control infrastructure.</span></span>

<span data-ttu-id="295b4-107">Mit Azure Active Directory Gerät, Standort und multi-Factor Authentication-basiertem bedingten Zugriff können Sie diese neue Anforderung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="295b4-107">With Azure Active Directory device, location, and multi-factor authentication-based Conditional Access, you can meet this new requirement.</span></span> <span data-ttu-id="295b4-108">Der bedingte Zugriff ist eine Funktion von Azure Active Directory, mit der Sie Steuerelemente für den Zugriff auf Apps in Ihrer Umgebung erzwingen können, die alle auf bestimmten Bedingungen basieren und von einem zentralen Ort aus verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="295b4-108">Conditional Access is a capability of Azure Active Directory that enables you to enforce controls on the access to apps in your environment, all based on specific conditions and managed from a central location.</span></span>

<span data-ttu-id="295b4-109">Erfahren Sie mehr über [Azure Active Directory bedingten Zugriff.](/azure/active-directory/conditional-access/)</span><span class="sxs-lookup"><span data-stu-id="295b4-109">Learn more about [Azure Active Directory Conditional Access](/azure/active-directory/conditional-access/).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="295b4-110">Unterstützte Clients & Plattformen</span><span class="sxs-lookup"><span data-stu-id="295b4-110">Supported clients & platforms</span></span>

<span data-ttu-id="295b4-111">Die neuesten Versionen der folgenden Clients und Plattformen unterstützen den bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="295b4-111">The latest versions of the following clients and platforms support conditional access.</span></span> <span data-ttu-id="295b4-112">Weitere Informationen zur Plattformunterstützung in Microsoft 365 finden Sie unter [Systemanforderungen für Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)</span><span class="sxs-lookup"><span data-stu-id="295b4-112">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="295b4-113">Unterstützte PowerShell-Module</span><span class="sxs-lookup"><span data-stu-id="295b4-113">Supported PowerShell modules</span></span>

- [<span data-ttu-id="295b4-114">Azure Active Directory Powershell</span><span class="sxs-lookup"><span data-stu-id="295b4-114">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview)
- [<span data-ttu-id="295b4-115">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="295b4-115">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="295b4-116">SharePoint Online-PowerShell</span><span class="sxs-lookup"><span data-stu-id="295b4-116">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
