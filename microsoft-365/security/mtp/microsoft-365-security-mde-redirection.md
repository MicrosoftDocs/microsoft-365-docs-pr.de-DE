---
title: Umleiten von Konten von Microsoft Defender for Endpoint zum Microsoft 365 Security Center
description: So leiten Sie Konten und Sitzungen vom Defender for Endpoint zum Microsoft 365 Security Center um.
keywords: Microsoft 365 Security Center, Erste Schritte mit dem Microsoft 365 Security Center, Sicherheitscenterumleitung
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 626bc9950512438bfa43e6500adf72940ddcbfec
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727565"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-the-microsoft-365-security-center"></a>Umleiten von Konten von Microsoft Defender for Endpoint zum Microsoft 365 Security Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Gilt für:**
- Microsoft 365 Defender
- Defender für Endpunkt

In Übereinstimmung mit dem domänenübergreifenden Ansatz von Microsoft für den Bedrohungsschutz mit SIEM und extended detection and response (XDR) haben wir Microsoft Defender Advanced Threat Protection als Microsoft Defender for Endpoint umbenannt und in einem einzigen integrierten Portal – dem Microsoft 365 Security Center – vereinheitlicht.

In diesem Handbuch wird erläutert, wie Konten an das Microsoft 365 Security Center geleitet werden, indem die automatische Umleitung vom ehemaligen Microsoft Defender for Endpoint-Portal (securitycenter.windows.com oder securitycenter.microsoft.com) zum Microsoft 365 Security Center-Portal (security.microsoft.com) aktiviert wird.

> [!NOTE]
> Microsoft Defender for Endpoint im Microsoft 365 Security Center unterstützt die Gewährung des Zugriffs auf anbieter für verwaltete Sicherheitsdienste [(Managed Security Service Provider, MSSPs)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) auf dieselbe Weise, wie der Zugriff im [Microsoft Defender Security Center gewährt wird.](https://docs.microsoft.com/microsoft-365/security/mtp/mssp-access)

## <a name="what-to-expect"></a>Was zu erwarten ist
Sobald die automatische Umleitung aktiviert ist, werden Konten, die auf das frühere Microsoft Defender for Endpoint-Portal unter securitycenter.windows.com oder securitycenter.microsoft.com zugreifen, automatisch an das Microsoft 365 Security Center-Portal unter security.microsoft.com.
 
Erfahren Sie mehr über die Geänderten: [Microsoft Defender for Endpoint im Microsoft 365 Security Center](microsoft-365-security-center-mde.md).

Dies umfasst die Umleitung für den direkten Zugriff auf das ehemalige Portal über den Browser, einschließlich Links, die auf das frühere securitycenter.windows.com-Portal zeigen – z. B. Links in E-Mail-Benachrichtigungen und Links, die von SIEM-API-Aufrufen zurückgegeben werden.  

 Externe Links von E-Mail-Benachrichtigungen oder SIEM-APIs enthalten derzeit Links zu beiden Portalen. Sobald die Umleitung aktiviert ist, verweisen beide Links auf das Microsoft 365 Security Center, bis der alte Link schließlich entfernt wird. Wir empfehlen Ihnen, den neuen Link zu übernehmen, der auf das Microsoft 365 Security Center verweisen soll.

Weitere Informationen zu Links und Routing finden Sie in der folgenden Tabelle.
## <a name="siem-api-routing"></a>SIEM-API-Routing

|**Eigenschaft**  |**Ziel, wenn die Umleitung DEAKTIVIERT ist**  |**Ziel, wenn die Umleitung EIN ist** | 
|---------|---------|---------|
| LinkToWDATP | Warnungsseite in securitycenter.windows.com | Warnungsseite in security.microsoft.com  |
| IncidentLinkToWDATP | Seite "Vorfall" in securitycenter.windows.com  | Seite "Vorfall" in security.microsoft.com  |
| LinkToMTP | Warnungsseite in security.microsoft.com | Warnungsseite in security.microsoft.com  |
| IncidentLinkToMTP | Seite "Vorfall" in security.microsoft.com  | Seite "Vorfall" in security.microsoft.com  

## <a name="email-alert-notifications"></a>E-Mail-Benachrichtigungen

|**Eigenschaft**  |**Ziel, wenn die Umleitung DEAKTIVIERT ist**  |**Ziel, wenn die Umleitung EIN ist** |
|---------|---------|---------|
| Warnungsseite  | Warnungsseite in securitycenter.windows.com  | Warnungsseite in security.microsoft.com  |
| Seite "Vorfälle"  |Seite "Vorfall" in securitycenter.windows.com  | Seite "Vorfall" in security.microsoft.com  
| Warnungsseite im Security Center-Portal | Warnungsseite in security.microsoft.com | Warnungsseite in security.microsoft.com | 
| Seite "Vorfall" im Security Center-Portal | Seite "Vorfall" in security.microsoft.com  | Seite "Vorfall" in security.microsoft.com  |

## <a name="when-does-this-take-effect"></a>Wann wird dies wirksam? 
Sobald diese Option aktiviert ist, kann dieses Update für einige Konten fast sofort wirksam werden. Die Umleitung kann jedoch länger dauern, bis sie auf jedes Konto in Ihrer Organisation übergeleitet wird. Konten in aktiven Sitzungen, während diese Einstellung angewendet wird, werden nicht aus ihrer Sitzung entfernt und nur an das Microsoft 365 Security Center geroutet, nachdem ihre aktuelle Sitzung beendet und sich erneut anmelden.  

### <a name="set-up-portal-redirection"></a>Einrichten der Portalumleitung
So starten Sie das Routing von Konten an das Microsoft 365 Security Center:
1. Stellen Sie sicher, dass Sie ein globaler Administrator sind oder über Sicherheitsadministratorberechtigungen in Azure Active Directory verfügen. 

2. [Melden Sie sich](https://security.microsoft.com/) beim Microsoft 365 Security Center an.

3. Navigieren Sie zu **Einstellungen**  >    >  **Endpunkte Allgemeine**  >  **Portalumleitung,** oder [klicken Sie hier](https://security.microsoft.com/preferences2/portal_redirection).  

4. Umschalten der Einstellung Automatische Umleitung auf **Ein**.

5. Klicken **Sie auf Aktivieren,** um die automatische Umleitung auf das Microsoft 365 Security Center-Portal anzuwenden.

>[!IMPORTANT]
>Wenn Sie diese Einstellung aktivieren, werden aktive Benutzersitzungen nicht beendet. Konten, die sich in einer aktiven Sitzung befinden, während diese Einstellung angewendet wird, werden nur an das Microsoft 365 Security Center geleitet, nachdem sie ihre aktuelle Sitzung beendet und sich erneut anmelden.

>[!NOTE]
>Sie müssen ein globaler Administrator sein oder über Sicherheitsadministratorberechtigungen in Azure Active Directory verfügen, um diese Einstellung zu aktivieren oder zu deaktivieren.  

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kann ich wieder auf das frühere Portal zugreifen?
Wenn etwas nicht für Sie funktioniert oder wenn sie nicht über das Microsoft 365 Security Center-Portal abgeschlossen werden können, möchten wir darüber erfahren. Wenn Probleme mit der Umleitung aufgetreten sind, empfehlen wir Ihnen, uns dies mithilfe des Feedback-Übermittlungsformulars zu sagen.

So kehren Sie zum früheren Microsoft Defender for Endpoint-Portal zurück:

1. [Melden Sie](https://security.microsoft.com/) sich beim Microsoft 365 Security Center als globaler Administrator an oder verwenden Und Konto mit Sicherheitsadministratorberechtigungen in Azure Active Directory.

2. Navigieren Sie zu **Einstellungen**  >    >  **Endpunkte Allgemeine**  >  **Portalumleitung,** [oder öffnen Sie die Seite hier](https://security.microsoft.com/preferences2/portal_redirection).  

3. Umschalten der Einstellung Automatische Umleitung auf **Aus**.

4. Klicken **Sie auf &** feedback deaktivieren, wenn Sie dazu aufgefordert werden.

Diese Einstellung kann jederzeit wieder aktiviert werden. 

Nach dem Deaktivieren werden Konten nicht mehr an security.microsoft.com, und Sie haben erneut Zugriff auf das frühere Portal - securitycenter.windows.com oder securitycenter.microsoft.com. 

## <a name="related-information"></a>Verwandte Informationen
- [Microsoft 365 Security Center – Übersicht](overview-security-center.md)
- [Microsoft Defender for Endpoint im Microsoft 365 Security Center](microsoft-365-security-center-mde.md)
- [Microsoft bietet einheitliches SIEM und XDR zur Modernisierung von Sicherheitsvorgängen](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR- und SIEM-Infografik](https://afrait.com/blog/xdr-versus-siem/) 
- [Der neue Defender](https://afrait.com/blog/the-new-defender/) 
- [Informationen zu Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft-Sicherheitsportale und Admin Center](portals.md)
