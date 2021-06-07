---
title: Umleiten von Konten aus Office 365 Security and Compliance Center zum neuen Microsoft 365 Security Center
description: Umleiten von Defender für Office 365 zum Microsoft 365 Security Center
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 703d3c3c9086aa2bdfada560c009e8738dffbb18
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768969"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-security-center"></a>Umleiten von Konten aus Office 365 Security and Compliance Center an Microsoft 365 Security Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender
- Defender for Office 365

In diesem Artikel wird erläutert, wie Sie Konten an das Microsoft 365 Security Center weiterleiten, indem Sie die automatische Umleitung vom früheren Office 365 Security and Compliance Center (protection.office.com) zum Microsoft 365 Security Center (security.microsoft.com) aktivieren.

## <a name="what-to-expect"></a>Das erwartet Sie
Sobald die automatische Umleitung aktiviert und aktiv ist, werden Benutzer, die auf die sicherheitsrelevanten Funktionen in Office 365 Security and Compliance (protection.office.com) zugreifen, automatisch an das Microsoft 365 Security Center weitergeleitet ( https://security.microsoft.com) .  

Erfahren Sie mehr über die Änderungen: [Microsoft Defender für Office 365 im Microsoft 365 Security Center.](microsoft-365-security-center-mdo.md)

Wenn die automatische Umleitung aktiviert ist, werden Benutzer an Microsoft 365 Security Center weitergeleitet, wenn sie Sicherheitsfunktionen im Office 365 Security and Compliance Center verwenden.

Dazu gehören Funktionen im Abschnitt "Bedrohungsverwaltung" und im Dashboard und den Berichten zur Bedrohungsverwaltung. Elemente im Office 365 Security and Compliance Center, die sich nicht auf die Sicherheit beziehen, werden nicht an das Microsoft 365 Security Center umgeleitet.

Compliance-bezogene Elemente finden Sie im Microsoft 365 Compliance Center, und nachrichtenflussbezogene Elemente finden Sie im Exchange Admin Center.

Alle anderen Funktionen, sei es Compliance-bezogene Funktionen oder Funktionen, die beide dienste, sind von der Umleitung nicht betroffen. Office 365 Sicherheitswarnungen werden im Microsoft 365 Security Center und im Office 365 Security and Compliance Center ohne Umleitung angezeigt.  

### <a name="set-up-portal-redirection"></a>Einrichten der Portalumleitung
So starten Sie das Routing von Konten an das Microsoft 365 Security Center bei security.microsoft.com:

1. Stellen Sie sicher, dass Sie ein globaler Administrator sind oder über Sicherheitsadministratorberechtigungen in Azure Active Directory verfügen.
2. [Melden Sie sich](https://security.microsoft.com/) beim Microsoft 365 Security Center an.
3. Navigieren Sie zu **Einstellungen** Umleitung des  >  **E-Mail-&-Portals** für die  >  Zusammenarbeit.  
4. Umschalten der Einstellung für die automatische Umleitung auf **"Ein".**
5. Klicken Sie auf **"Aktivieren",** um die automatische Umleitung auf das Microsoft 365 Security Center-Portal anzuwenden.

> [!NOTE]
> Nachdem die Umleitung aktiviert ist, werden Konten in aktiven Sitzungen, während diese Einstellung angewendet wird, nicht aus ihrer Sitzung ausgeleitet und nur an das Microsoft 365 Security Center weitergeleitet, nachdem sie ihre aktuelle Sitzung beendet und sich erneut angemeldet haben.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kann ich zum früheren Portal zurückkehren?
Wenn etwas nicht für Sie funktioniert oder wenn Sie etwas nicht über das Microsoft 365 Security Center-Portal abschließen können, möchten wir uns über die Feedbackoption des Portals darüber informieren. Wenn Bei der Umleitung Probleme aufgetreten sind, teilen Sie uns dies bitte mit.

So kehren Sie zum früheren Portal zurück:

1. [Melden Sie sich](https://security.microsoft.com/) beim Microsoft 365 Security Center als globaler Administrator oder mithilfe von Und Konto mit Sicherheitsadministratorberechtigungen in Azure Active Directory an.

2. Navigieren Sie zu **Einstellungen** Umleitung des  >  **E-Mail-&-Portals** für die  >  Zusammenarbeit.   

3. Schalten Sie die Einstellung für die automatische Umleitung auf **"Aus" um.**

4. Klicken Sie auf **"Deaktivieren** & Feedback teilen", wenn Sie dazu aufgefordert werden.

Diese Einstellung kann jederzeit wieder aktiviert werden.

Nach der Deaktivierung werden Konten nicht mehr an security.microsoft.com weitergeleitet, und Sie haben wieder Zugriff auf das frühere Portal – securitycenter.windows.com oder securitycenter.microsoft.com.

## <a name="related-information"></a>Verwandte Informationen
- [Microsoft 365 Security Center – Übersicht](overview-security-center.md)
- [Microsoft Defender für Endpunkt im Microsoft 365 Security Center](microsoft-365-security-center-mde.md)
- [Microsoft bietet einheitliche SIEM- und XDR-Lösungen zur Modernisierung von Sicherheitsvorgängen](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR im Vergleich zu SIEM-Infografik](https://afrait.com/blog/xdr-versus-siem/) 
- [Der neue Defender](https://afrait.com/blog/the-new-defender/) 
- [Informationen zu Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft-Sicherheitsportale und Admin Center](portals.md)
