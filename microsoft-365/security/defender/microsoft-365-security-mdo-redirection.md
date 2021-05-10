---
title: Umleiten von Konten von Microsoft Defender für Office 365 zum neuen Microsoft 365 Security Center
description: So umleiten Sie von defender for Office 365 zum Microsoft 365 Security Center.
keywords: Microsoft 365 Security Center, Erste Schritte mit Microsoft 365 Security Center, Sicherheitscenterumleitung
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
ms.openlocfilehash: 40d86f9f3a4896bbe788f0a9894a7e08efe3a690
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52301728"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>Umleiten von Konten von Microsoft Defender für Office 365 zum Microsoft 365 Security Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender
- Defender for Office 365

In diesem Artikel wird erläutert, wie Sie Konten an das Microsoft 365 Security Center weiterleiten, indem sie die automatische Umleitung vom ehemaligen Microsoft Security and Compliance Center (protection.office.com oder securitycenter.microsoft.com) zum Microsoft 365 Security Center (security.microsoft.com) aktivieren.

## <a name="what-to-expect"></a>Das erwartet Sie
Sobald die automatische Umleitung aktiviert und aktiv ist, werden Benutzer, die auf die sicherheitsbezogenen Funktionen in Office 365 Security and Compliance (protection.office.com) zugreifen, automatisch an das Microsoft 365 Security Center ( ) https://security.microsoft.com) geroutet.  

Erfahren Sie mehr über die Geänderten: [Microsoft Defender for Office 365 im Microsoft 365 Security Center](microsoft-365-security-center-mdo.md).

Wenn die automatische Umleitung aktiviert ist, werden Benutzer an Microsoft 365 Security Center geroutet, wenn sie Sicherheitsfunktionen im Office 365 Security and Compliance Center verwenden.

Dazu gehören Funktionen im Abschnitt Bedrohungsverwaltung und das Dashboard und Berichte zur Bedrohungsverwaltung. Elemente im Office 365 Security and Compliance Center, die nicht mit Sicherheit in Zusammenhang stehen, werden nicht an das Microsoft 365 umgeleitet.

Compliancebezogene Elemente finden Sie im Microsoft 365 Compliance Center, und nachrichtenflussbezogene Elemente finden Sie im Exchange Admin Center.

Alle anderen Funktionen, unabhängig davon, ob es sich um compliancebezogene oder funktionen handelt, die beide unterstützen, sind von der Umleitung nicht betroffen. Office 365 sicherheitswarnungen werden sowohl im Microsoft 365 Security Center als auch im Office 365 Security and Compliance Center ohne Umleitung angezeigt.  

### <a name="set-up-portal-redirection"></a>Einrichten der Portalumleitung
So starten Sie das Routing von Konten Microsoft 365 Sicherheitscenter unter security.microsoft.com:

1. Stellen Sie sicher, dass Sie ein globaler Administrator sind oder über Sicherheitsadministratorberechtigungen in Azure Active Directory verfügen.
2. [Melden Sie sich](https://security.microsoft.com/) beim Microsoft 365 an.
3. Navigieren Sie **zu Einstellungen**  >  **E-Mail &-Portal-Umleitung**  >  .  
4. Umschalten der Einstellung Automatische Umleitung auf **Ein**.
5. Klicken **Sie auf Aktivieren,** um die automatische Umleitung auf das Microsoft 365 anzuwenden.

> [!NOTE]
> Nachdem die Umleitung aktiviert wurde, werden Konten in aktiven Sitzungen, während diese Einstellung angewendet wird, nicht aus ihrer Sitzung entfernt und erst an das Microsoft 365 Security Center geroutet, nachdem ihre aktuelle Sitzung beendet und sich erneut anmelden.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kann ich wieder auf das frühere Portal zugreifen?
Wenn etwas nicht für Sie funktioniert oder wenn sie nicht über das Microsoft 365 Security Center-Portal abgeschlossen werden können, möchten wir über die Portalfeedbackoption darüber erfahren. Wenn Probleme mit der Umleitung aufgetreten sind, empfehlen wir Ihnen, sich direkt über die private Vorschau an Ihren PM-Kumpel zu wenden oder uns über das Feedback-Übermittlungsformular zu kontaktieren.

So kehren Sie zum vorherigen Portal zurück:

1. [Melden Sie](https://security.microsoft.com/) sich beim Microsoft 365 sicherheitscenter als globaler Administrator an oder verwenden und konto mit Sicherheitsadministratorberechtigungen in Azure Active Directory.

2. Navigieren Sie **zu Einstellungen**  >  **Endpoints**  >  **General**  >  **Portal redirection**.  

3. Umschalten der Einstellung Automatische Umleitung auf **Aus**.

4. Klicken **Sie auf &** feedback deaktivieren, wenn Sie dazu aufgefordert werden.

Diese Einstellung kann jederzeit wieder aktiviert werden.

Nach dem Deaktivieren werden Konten nicht mehr an security.microsoft.com, und Sie haben erneut Zugriff auf das frühere Portal - securitycenter.windows.com oder securitycenter.microsoft.com.

## <a name="related-information"></a>Verwandte Informationen
- [Microsoft 365 Security Center – Übersicht](overview-security-center.md)
- [Microsoft Defender für Endpunkt im Microsoft 365 Security Center](microsoft-365-security-center-mde.md)
- [Microsoft bietet einheitliches SIEM und XDR zur Modernisierung von Sicherheitsvorgängen](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR- und SIEM-Infografik](https://afrait.com/blog/xdr-versus-siem/) 
- [Der neue Defender](https://afrait.com/blog/the-new-defender/) 
- [Informationen Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft-Sicherheitsportale und Admin Center](portals.md)
