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
description: In diesem Artikel wird erläutert, wie Sie die moderne Hybridauthentifizierung aus Skype for Business und Exchange entfernen oder deaktivieren.
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927288"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Entfernen oder Deaktivieren der modernen Hybridauthentifizierung aus Skype for Business und Exchange

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Wenn Sie die hybride moderne Authentifizierung (Hybrid Modern Authentication, HMA) nur aktiviert haben, um zu finden, dass sie für Ihre aktuelle Umgebung ungeeignet ist, können Sie HMA deaktivieren. In diesem Artikel wird dies erläutert.
  
## <a name="who-is-this-article-for"></a>Für wen ist dieser Artikel da?

Wenn Sie die moderne Authentifizierung in Skype for Business Online oder lokal und/oder Exchange Online oder lokal aktiviert haben und festgestellt haben, dass Sie HMA deaktivieren müssen, sind diese Schritte für Sie da.

> [!IMPORTANT]
> Lesen Sie den Artikel "[Skype for Business topologies supported with Modern Authentication](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)", wenn Sie in Skype for Business Online oder lokal sind, über eine gemischte Topologie-HMA verfügen und unterstützte Topologien sehen müssen, bevor Sie beginnen.
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>Deaktivieren der hybriden modernen Authentifizierung (Exchange)

1. **Exchange Lokal**: Öffnen Sie die Exchange-Verwaltungsshell, und führen Sie die folgenden Befehle aus: 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange Online**: [Stellen Sie eine Verbindung mit Exchange Online mit](/powershell/exchange/connect-to-exchange-online-powershell) Remote PowerShell herzustellen. Führen Sie den folgenden Befehl aus, um das  *OAuth2ClientProfileEnabled-Flag*  in "false" zu verwandeln:

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>Deaktivieren der modernen Hybridauthentifizierung (Skype for Business)

1. **Skype for Business Lokal**: Führen Sie die folgenden Befehle in der Skype for Business Management Shell aus:

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype for Business Online**: [Verbinden sie sich mit Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) mit Remote PowerShell. Führen Sie den folgenden Befehl aus, um die moderne Authentifizierung zu deaktivieren:

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[Link zurück zur Übersicht über die moderne Authentifizierung](hybrid-modern-auth-overview.md) . 
