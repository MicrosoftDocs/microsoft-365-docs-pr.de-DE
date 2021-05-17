---
title: Entfernen oder Deaktivieren der modernen Hybridauthentifizierung aus Skype for Business und Exchange
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel wird erläutert, wie Sie die hybride moderne Authentifizierung aus Skype for Business und Exchange.
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927288"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a><span data-ttu-id="b2152-103">Entfernen oder Deaktivieren der modernen Hybridauthentifizierung aus Skype for Business und Exchange</span><span class="sxs-lookup"><span data-stu-id="b2152-103">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>

<span data-ttu-id="b2152-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b2152-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b2152-105">Wenn Sie die hybride moderne Authentifizierung (Hybrid Modern Authentication, HMA) nur aktiviert haben, um zu finden, dass sie für Ihre aktuelle Umgebung ungeeignet ist, können Sie HMA deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b2152-105">If you've enabled Hybrid Modern Authentication (HMA) only to find it's unsuitable for your current environment, you can disable HMA.</span></span> <span data-ttu-id="b2152-106">In diesem Artikel wird dies erläutert.</span><span class="sxs-lookup"><span data-stu-id="b2152-106">This article explains how.</span></span>
  
## <a name="who-is-this-article-for"></a><span data-ttu-id="b2152-107">Wer ist dieser Artikel für?</span><span class="sxs-lookup"><span data-stu-id="b2152-107">Who is this article for?</span></span>

<span data-ttu-id="b2152-108">Wenn Sie die moderne Authentifizierung in Skype for Business Online oder lokal und/oder Exchange Online oder lokal aktiviert haben und festgestellt haben, dass Sie HMA deaktivieren müssen, sind diese Schritte für Sie da.</span><span class="sxs-lookup"><span data-stu-id="b2152-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2152-109">Lesen Sie den Artikel Skype for Business[topologies supported with Modern Authentication](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), wenn Sie in Skype for Business Online oder Lokal sind, über eine HMA für gemischte Topologien verfügen und unterstützte Topologien sehen müssen, bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="b2152-109">See the '[Skype for Business topologies supported with Modern Authentication](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)' article if you're in Skype for Business Online or On-premises, have a mixed-topology HMA, and need to look at supported topologies before you begin.</span></span>
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a><span data-ttu-id="b2152-110">Deaktivieren der modernen Hybridauthentifizierung (Exchange)</span><span class="sxs-lookup"><span data-stu-id="b2152-110">How to disable Hybrid Modern Authentication (Exchange)</span></span>

1. <span data-ttu-id="b2152-111">**Exchange Lokal**: Öffnen Sie die Exchange-Verwaltungsshell, und führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="b2152-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span></span> 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. <span data-ttu-id="b2152-112">**Exchange Online**: [Verbinden, Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) Remote PowerShell zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2152-112">**Exchange Online**: [Connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) with Remote PowerShell.</span></span> <span data-ttu-id="b2152-113">Führen Sie den folgenden Befehl aus, um das  *OAuth2ClientProfileEnabled-Flag*  in "false" zu verwandeln:</span><span class="sxs-lookup"><span data-stu-id="b2152-113">Run the following command to turn your  *OAuth2ClientProfileEnabled*  flag to 'false':</span></span>

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a><span data-ttu-id="b2152-114">Deaktivieren der modernen Hybridauthentifizierung (Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="b2152-114">How to disable Hybrid Modern Authentication (Skype for Business)</span></span>

1. <span data-ttu-id="b2152-115">**Skype for Business Lokal**: Führen Sie die folgenden Befehle in Skype for Business Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="b2152-115">**Skype for Business On-premises**: Run the following commands in Skype for Business Management Shell:</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. <span data-ttu-id="b2152-116">**Skype for Business Online**: [Verbinden, Skype for Business Mit Remote](manage-skype-for-business-online-with-microsoft-365-powershell.md) PowerShell online zu schalten.</span><span class="sxs-lookup"><span data-stu-id="b2152-116">**Skype for Business Online**: [Connect to Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) with Remote PowerShell.</span></span> <span data-ttu-id="b2152-117">Führen Sie den folgenden Befehl aus, um die moderne Authentifizierung zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="b2152-117">Run the following command to disable Modern Authentication:</span></span>

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

<span data-ttu-id="b2152-118">[Link zurück zur Übersicht über die moderne Authentifizierung](hybrid-modern-auth-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="b2152-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span></span> 
