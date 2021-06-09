---
title: Umleiten von Konten von Microsoft Defender für Endpunkt zu Microsoft 365 Defender
description: So leiten Sie Konten und Sitzungen vom Defender für Endpunkt an Microsoft 365 Defender um.
keywords: Microsoft 365 Defender, Erste Schritte mit Microsoft 365 Defender, Security Center-Umleitung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c678cb8d9eece9ff3a900a7d2b0c6bf95ad8eda9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842566"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-microsoft-365-defender"></a>Umleiten von Konten von Microsoft Defender für Endpunkt zu Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender
- Defender für Endpunkt

In Übereinstimmung mit dem domänenübergreifenden Ansatz von Microsoft für den Bedrohungsschutz mit SIEM und erweiterter Erkennung und Reaktion (Extended Detection and Response, XDR) haben wir Microsoft Defender Advanced Threat Protection als Microsoft Defender für Endpunkt umbenennen und in einem einzigen integrierten Portal – Microsoft 365 Defender – vereinheitlicht.

In diesem Leitfaden wird erläutert, wie Sie Konten an Microsoft 365 Defender weiterleiten, indem Sie die automatische Umleitung vom früheren Microsoft Defender für Endpunkt-Portal (securitycenter.windows.com oder securitycenter.microsoft.com) zu Microsoft 365 Defender-Portal (security.microsoft.com) aktivieren.

> [!NOTE]
> Microsoft Defender für Endpunkt in Microsoft 365 Defender unterstützt das Gewähren des [Zugriffs auf verwaltete Sicherheitsdienstanbieter (Managed Security Service Providers, MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) auf die gleiche Weise, wie der Zugriff [im Microsoft Defender Security Center gewährt](./mssp-access.md)wird.

## <a name="what-to-expect"></a>Das erwartet Sie
Sobald die automatische Umleitung aktiviert ist, werden Konten, die auf das frühere Microsoft Defender für Endpunkt-Portal unter securitycenter.windows.com oder securitycenter.microsoft.com zugreifen, automatisch an Microsoft 365 Defender-Portal bei security.microsoft.com weitergeleitet.
 
Erfahren Sie mehr über die Änderungen: [Microsoft Defender für Endpunkt in Microsoft 365 Defender](microsoft-365-security-center-mde.md).

Dazu gehört die Umleitung für den direkten Zugriff auf das frühere Portal über browser, einschließlich Links, die auf das frühere securitycenter.windows.com-Portal verweisen , z. B. Links in E-Mail-Benachrichtigungen und Links, die von SIEM-API-Aufrufen zurückgegeben werden.  

 Externe Links von E-Mail-Benachrichtigungen oder SIEM-APIs enthalten derzeit Links zu beiden Portalen. Sobald die Umleitung aktiviert ist, zeigen beide Links auf Microsoft 365 Defender, bis der alte Link schließlich entfernt wird. Wir empfehlen Ihnen, den neuen Link zu übernehmen, der auf Microsoft 365 Defender verweist.

Weitere Informationen zu Links und Routing finden Sie in der folgenden Tabelle.
## <a name="siem-api-routing"></a>SIEM-API-Routing

|**Eigenschaft**  |**Ziel, wenn die Umleitung ausgeschaltet ist**  |**Ziel bei aktivierter Umleitung** | 
|---------|---------|---------|
| LinkToWDATP | Warnungsseite in securitycenter.windows.com | Warnungsseite in security.microsoft.com  |
| IncidentLinkToWDATP | Vorfallseite in securitycenter.windows.com  | Vorfallseite in security.microsoft.com  |
| LinkToMTP | Warnungsseite in security.microsoft.com | Warnungsseite in security.microsoft.com  |
| IncidentLinkToMTP | Vorfallseite in security.microsoft.com  | Vorfallseite in security.microsoft.com  

## <a name="email-alert-notifications"></a>E-Mail-Benachrichtigungen

|**Eigenschaft**  |**Ziel, wenn die Umleitung ausgeschaltet ist**  |**Ziel bei aktivierter Umleitung** |
|---------|---------|---------|
| Warnungsseite  | Warnungsseite in securitycenter.windows.com  | Warnungsseite in security.microsoft.com  |
| Vorfallseite  |Vorfallseite in securitycenter.windows.com  | Vorfallseite in security.microsoft.com  
| Seite "Warnung" im Security Center-Portal | Warnungsseite in security.microsoft.com | Warnungsseite in security.microsoft.com | 
| Vorfallseite im Security Center-Portal | Vorfallseite in security.microsoft.com  | Vorfallseite in security.microsoft.com  |

## <a name="when-does-this-take-effect"></a>Wann wird dies wirksam? 
Nach der Aktivierung kann dieses Update für einige Konten fast sofort wirksam werden. Die Umleitung kann jedoch länger dauern, bis sie an jedes Konto in Ihrer Organisation verteilt wird. Konten in aktiven Sitzungen, während diese Einstellung angewendet wird, werden nicht aus ihrer Sitzung ejiziert und nur an Microsoft 365 Defender weitergeleitet, nachdem sie ihre aktuelle Sitzung beendet und sich erneut angemeldet haben.  

### <a name="set-up-portal-redirection"></a>Einrichten der Portalumleitung
So starten Sie das Routing von Konten an Microsoft 365 Defender:
1. Stellen Sie sicher, dass Sie ein globaler Administrator sind oder über Sicherheitsadministratorberechtigungen in Azure Active Directory verfügen. 

2. [Melden Sie sich bei](https://security.microsoft.com/) Microsoft 365 Defender an.

3. Navigieren Sie zu **Einstellungen**  >  **Allgemeinen**  >    >  **Endpunktportalumleitung,** oder [klicken Sie hier.](https://security.microsoft.com/preferences2/portal_redirection)  

4. Umschalten der Einstellung für die automatische Umleitung auf **"Ein".**

5. Klicken Sie auf **"Aktivieren",** um die automatische Umleitung auf Microsoft 365 Defender anzuwenden.

>[!IMPORTANT]
>Wenn Sie diese Einstellung aktivieren, werden aktive Benutzersitzungen nicht beendet. Konten, die sich während der Anwendung dieser Einstellung in einer aktiven Sitzung befinden, werden nur an Microsoft 365 Defender weitergeleitet, nachdem sie ihre aktuelle Sitzung beendet und sich erneut angemeldet haben.

>[!NOTE]
>Sie müssen ein globaler Administrator sein oder über Sicherheitsadministratorberechtigungen in Azure Active Directory verfügen, um diese Einstellung zu aktivieren oder zu deaktivieren.  

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kann ich zum früheren Portal zurückkehren?
Wenn etwas nicht für Sie funktioniert oder wenn Sie etwas nicht über Microsoft 365 Defender abschließen können, möchten wir uns darüber informieren. Wenn Bei der Umleitung Probleme aufgetreten sind, empfehlen wir Ihnen, uns dies über das Übermittlungsformular für Feedback mitzuteilen.

So kehren Sie zum früheren Microsoft Defender für Endpunkt-Portal zurück:

1. [Melden Sie sich bei](https://security.microsoft.com/) Microsoft 365 Defender als globaler Administrator oder mithilfe von Sicherheitsadministratorberechtigungen in Azure Active Directory an.

2. Navigieren Sie zu **Einstellungen**  >  **Allgemeinen**  >    >  **Endpunktportalumleitung,** oder öffnen Sie [die Seite hier.](https://security.microsoft.com/preferences2/portal_redirection)  

3. Schalten Sie die Einstellung für die automatische Umleitung auf **"Aus" um.**

4. Klicken Sie auf **"Deaktivieren** & Feedback teilen", wenn Sie dazu aufgefordert werden.

Diese Einstellung kann jederzeit wieder aktiviert werden. 

Nach der Deaktivierung werden Konten nicht mehr an security.microsoft.com weitergeleitet, und Sie haben erneut Zugriff auf das frühere Portal – securitycenter.windows.com oder securitycenter.microsoft.com. 

## <a name="related-information"></a>Verwandte Informationen
- [Microsoft 365 Übersicht über Defender](overview-security-center.md)
- [Microsoft Defender für Endpunkt in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft bietet einheitliche SIEM- und XDR-Lösungen zur Modernisierung von Sicherheitsvorgängen](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR im Vergleich zu SIEM-Infografik](https://afrait.com/blog/xdr-versus-siem/) 
- [Der neue Defender](https://afrait.com/blog/the-new-defender/) 
- [Informationen zu Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft-Sicherheitsportale und Admin Center](portals.md)