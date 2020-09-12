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
description: In diesem Artikel wird erläutert, wie Sie die moderne Hybrid Authentifizierung aus Skype for Business und Exchange entfernen oder deaktivieren.
ms.openlocfilehash: 70f62b9b2165464837aa1dea0e12854df116efe0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547096"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a><span data-ttu-id="23331-103">Entfernen oder Deaktivieren der modernen Hybridauthentifizierung aus Skype for Business und Exchange</span><span class="sxs-lookup"><span data-stu-id="23331-103">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>

<span data-ttu-id="23331-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="23331-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="23331-105">Wenn Sie die hybride moderne Authentifizierung (HMA) aktiviert haben, um zu ermitteln, ob Sie für Ihre aktuelle Umgebung ungeeignet ist, können Sie HMA deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="23331-105">If you've enabled Hybrid Modern Authentication (HMA) only to find it's unsuitable for your current environment, you can disable HMA.</span></span> <span data-ttu-id="23331-106">In diesem Artikel wird erläutert, wie.</span><span class="sxs-lookup"><span data-stu-id="23331-106">This article explains how.</span></span>
  
## <a name="who-is-this-article-for"></a><span data-ttu-id="23331-107">An wen richtet sich dieser Artikel?</span><span class="sxs-lookup"><span data-stu-id="23331-107">Who is this article for?</span></span>

<span data-ttu-id="23331-108">Wenn Sie die moderne Authentifizierung in Skype for Business Online oder lokal und/oder Exchange Online oder lokal aktiviert haben und festgestellt haben, dass Sie HMA deaktivieren müssen, sind diese Schritte für Sie erforderlich.</span><span class="sxs-lookup"><span data-stu-id="23331-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23331-109">Lesen Sie den Artikel "[Skype for Business Topologien mit moderner Authentifizierung unterstützt](https://technet.microsoft.com/library/mt803262.aspx)", wenn Sie sich in Skype for Business Online oder lokal befinden, eine HMA mit gemischten Topologien haben und unterstützte Topologien suchen müssen, bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="23331-109">See the '[Skype for Business topologies supported with Modern Authentication](https://technet.microsoft.com/library/mt803262.aspx)' article if you're in Skype for Business Online or On-premises, have a mixed-topology HMA, and need to look at supported topologies before you begin.</span></span>
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a><span data-ttu-id="23331-110">Deaktivieren der modernen Hybrid Authentifizierung (Exchange)</span><span class="sxs-lookup"><span data-stu-id="23331-110">How to disable Hybrid Modern Authentication (Exchange)</span></span>

1. <span data-ttu-id="23331-111">**Exchange lokal**: Öffnen Sie das Exchange-Verwaltungsshell, und führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="23331-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span></span> 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. <span data-ttu-id="23331-112">**Exchange Online**: [Verbinden mit Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) mit Remote-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23331-112">**Exchange Online**: [Connect to Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) with Remote PowerShell.</span></span> <span data-ttu-id="23331-113">Führen Sie den folgenden Befehl aus, um die  *OAuth2ClientProfileEnabled*  -Kennzeichnung auf "false" zu verwandeln:</span><span class="sxs-lookup"><span data-stu-id="23331-113">Run the following command to turn your  *OAuth2ClientProfileEnabled*  flag to 'false':</span></span>

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a><span data-ttu-id="23331-114">Deaktivieren der modernen Hybrid Authentifizierung (Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="23331-114">How to disable Hybrid Modern Authentication (Skype for Business)</span></span>

1. <span data-ttu-id="23331-115">**Skype for Business lokal**: führen Sie die folgenden Befehle in Skype for Business-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="23331-115">**Skype for Business On-premises**: Run the following commands in Skype for Business Management Shell:</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. <span data-ttu-id="23331-116">**Skype for Business Online**: [Verbinden mit Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) mit Remote-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23331-116">**Skype for Business Online**: [Connect to Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) with Remote PowerShell.</span></span> <span data-ttu-id="23331-117">Führen Sie den folgenden Befehl aus, um die moderne Authentifizierung zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="23331-117">Run the following command to disable Modern Authentication:</span></span>

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

<span data-ttu-id="23331-118">[Link zurück zur modernen Authentifizierung (Übersicht](hybrid-modern-auth-overview.md) ).</span><span class="sxs-lookup"><span data-stu-id="23331-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span></span> 
  

