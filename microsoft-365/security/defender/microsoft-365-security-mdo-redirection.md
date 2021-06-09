---
title: Umleiten von Konten aus Office 365 Security and Compliance Center zum neuen Microsoft 365 Defender
description: Umleiten von Defender für Office 365 zu Microsoft 365 Defender.
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
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842518"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a>Umleiten von Konten aus Office 365 Security and Compliance Center zu Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender
- Defender for Office 365

In diesem Artikel wird erläutert, wie Sie Konten an Microsoft 365 Defender weiterleiten, indem Sie die automatische Umleitung vom früheren Office 365 Security and Compliance Center (protection.office.com) zu Microsoft 365 Defender (security.microsoft.com) aktivieren.

## <a name="what-to-expect"></a>Das erwartet Sie
Sobald die automatische Umleitung aktiviert und aktiv ist, werden Benutzer, die auf die sicherheitsrelevanten Funktionen in Office 365 Security and Compliance (protection.office.com) zugreifen, automatisch an Microsoft 365 Defender ( https://security.microsoft.com) weitergeleitet.  

Erfahren Sie mehr über die Änderungen: [Microsoft Defender für Office 365 in Microsoft 365 Defender](microsoft-365-security-center-mdo.md).

Wenn die automatische Umleitung aktiviert ist, werden Benutzer zu Microsoft 365 Defender weitergeleitet, wenn sie Sicherheitsfunktionen im Office 365 Security and Compliance Center verwenden.

Dazu gehören Funktionen im Abschnitt "Bedrohungsverwaltung" und im Dashboard und den Berichten zur Bedrohungsverwaltung. Elemente im Office 365 Security and Compliance Center, die nicht mit der Sicherheit in Zusammenhang stehen, werden nicht an Microsoft 365 Defender umgeleitet.

Compliance-bezogene Elemente finden Sie im Microsoft 365 Compliance Center, und nachrichtenflussbezogene Elemente finden Sie im Exchange Admin Center.

Alle anderen Funktionen, sei es Compliance-bezogene Funktionen oder Funktionen, die beide dienste, sind von der Umleitung nicht betroffen. Office 365 Sicherheitswarnungen werden sowohl in Microsoft 365 Defender als auch im Office 365 Security and Compliance Center ohne Umleitung angezeigt.  

### <a name="set-up-portal-redirection"></a>Einrichten der Portalumleitung
So starten Sie das Routing von Konten an Microsoft 365 Defender bei security.microsoft.com:

1. Stellen Sie sicher, dass Sie ein globaler Administrator sind oder über Sicherheitsadministratorberechtigungen in Azure Active Directory verfügen.
2. [Melden Sie sich bei](https://security.microsoft.com/) Microsoft 365 Defender an.
3. Navigieren Sie zu **Einstellungen** Umleitung des  >  **E-Mail-&-Portals** für die  >  Zusammenarbeit.  
4. Umschalten der Einstellung für die automatische Umleitung auf **"Ein".**
5. Klicken Sie auf **"Aktivieren",** um die automatische Umleitung auf Microsoft 365 Defender anzuwenden.

> [!NOTE]
> Nachdem die Umleitung aktiviert wurde, werden Konten in aktiven Sitzungen, während diese Einstellung angewendet wird, nicht aus ihrer Sitzung ausgeleitet und nur an Microsoft 365 Defender weitergeleitet, nachdem sie ihre aktuelle Sitzung beendet und sich erneut angemeldet haben.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kann ich zum früheren Portal zurückkehren?
Wenn etwas nicht für Sie funktioniert oder wenn Sie etwas nicht über Microsoft 365 Defender abschließen können, möchten wir uns über die Feedbackoption des Portals darüber informieren. Wenn Bei der Umleitung Probleme aufgetreten sind, teilen Sie uns dies bitte mit.

So kehren Sie zum früheren Portal zurück:

1. [Melden Sie sich bei](https://security.microsoft.com/) Microsoft 365 Defender als globaler Administrator oder mithilfe von Sicherheitsadministratorberechtigungen in Azure Active Directory an.

2. Navigieren Sie zu **Einstellungen** Umleitung des  >  **E-Mail-&-Portals** für die  >  Zusammenarbeit.   

3. Schalten Sie die Einstellung für die automatische Umleitung auf **"Aus" um.**

4. Klicken Sie auf **"Deaktivieren** & Feedback teilen", wenn Sie dazu aufgefordert werden.

Diese Einstellung kann jederzeit wieder aktiviert werden.

Nach der Deaktivierung werden Konten nicht mehr an security.microsoft.com weitergeleitet, und Sie haben wieder Zugriff auf das frühere Portal – securitycenter.windows.com oder securitycenter.microsoft.com.

## <a name="related-information"></a>Verwandte Informationen
- [Microsoft 365 Übersicht über Defender](overview-security-center.md)
- [Microsoft Defender für Endpunkt in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft bietet einheitliche SIEM- und XDR-Lösungen zur Modernisierung von Sicherheitsvorgängen](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR im Vergleich zu SIEM-Infografik](https://afrait.com/blog/xdr-versus-siem/) 
- [Der neue Defender](https://afrait.com/blog/the-new-defender/) 
- [Informationen zu Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft-Sicherheitsportale und Admin Center](portals.md)
