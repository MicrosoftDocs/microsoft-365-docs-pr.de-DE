---
title: Umleiten von Konten von Microsoft Defender für Office 365 zum neuen Microsoft 365 Security Center
description: So leiten Sie von Defender for Office 365 zum Microsoft 365 Security Center um.
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
ms.openlocfilehash: ce8c178b4c46a00b83833f008080b776f4dc7e60
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064640"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>Umleiten von Konten von Microsoft Defender für Office 365 zum Microsoft 365 Security Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender
- Defender for Office 365

In diesem Artikel wird erläutert, wie Sie Konten an das Microsoft 365 Security Center weiterleiten, indem sie die automatische Umleitung vom ehemaligen Microsoft Security and Compliance Center (protection.office.com oder securitycenter.microsoft.com) zum Microsoft 365 Security Center (security.microsoft.com) aktivieren.

>[!NOTE]
> Portalumleitungsfunktion ist nur für Office 365 E5- und Microsoft Defender for Office P2-Kunden verfügbar

## <a name="what-to-expect"></a>Das erwartet Sie
Sobald die automatische Umleitung aktiviert und aktiv ist, werden Benutzer, die auf die sicherheitsbezogenen Funktionen in Office 365 Security and Compliance (protection.office.com) zugreifen, automatisch an das Microsoft 365 Security Center ( https://security.microsoft.com) geroutet.  

Erfahren Sie mehr über die Geänderten: [Microsoft Defender für Office 365 im Microsoft 365 Security Center](microsoft-365-security-center-mdo.md).

Wenn die automatische Umleitung aktiviert ist, werden Benutzer an das Microsoft 365 Security Center geroutet, wenn sie Sicherheitsfunktionen im Office 365 Security and Compliance Center verwenden.

Dazu gehören Funktionen im Abschnitt Bedrohungsverwaltung und das Dashboard und Berichte zur Bedrohungsverwaltung. Elemente im Office 365 Security and Compliance Center, die keinen Bezug zur Sicherheit haben, werden nicht an das Microsoft 365 Security Center umgeleitet.

Compliancebezogene Elemente finden Sie im Microsoft 365 Compliance Center, und nachrichtenflussbezogene Elemente finden Sie im Exchange Admin Center.

Alle anderen Funktionen, unabhängig davon, ob es sich um compliancebezogene oder funktionen handelt, die beide unterstützen, sind von der Umleitung nicht betroffen. Office 365-Sicherheitswarnungen werden sowohl im Microsoft 365 Security Center als auch im Office 365 Security and Compliance Center ohne Umleitung angezeigt.  

### <a name="set-up-portal-redirection"></a>Einrichten der Portalumleitung
So starten Sie das Routing von Konten an das Microsoft 365 Security Center unter security.microsoft.com:

1. Stellen Sie sicher, dass Sie ein globaler Administrator sind oder über Sicherheitsadministratorberechtigungen in Azure Active Directory verfügen.
2. [Melden Sie sich](https://security.microsoft.com/) beim Microsoft 365 Security Center an.
3. Navigieren Sie zu **Einstellungen**  >  **E-Mail & Umleitung des**  >  **Portals für die Zusammenarbeit**.  
4. Umschalten der Einstellung Automatische Umleitung auf **Ein**.
5. Klicken **Sie auf Aktivieren,** um die automatische Umleitung auf das Microsoft 365 Security Center-Portal anzuwenden.

> [!NOTE]
> Nachdem die Umleitung aktiviert wurde, werden Konten in aktiven Sitzungen, während diese Einstellung angewendet wird, nicht aus ihrer Sitzung entfernt und erst an das Microsoft 365 Security Center geroutet, nachdem die aktuelle Sitzung beendet und sich erneut anmelden.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kann ich wieder auf das frühere Portal zugreifen?
Wenn etwas nicht für Sie funktioniert oder wenn sie nicht über das Microsoft 365 Security Center-Portal abgeschlossen werden können, möchten wir über die Portalfeedbackoption darüber erfahren. Wenn Probleme mit der Umleitung aufgetreten sind, empfehlen wir Ihnen, sich direkt über die private Vorschau an Ihren PM-Kumpel zu wenden oder uns über das Feedback-Übermittlungsformular zu kontaktieren.

So kehren Sie zum vorherigen Portal zurück:

1. [Melden Sie](https://security.microsoft.com/) sich beim Microsoft 365 Security Center als globaler Administrator an oder verwenden Und Konto mit Sicherheitsadministratorberechtigungen in Azure Active Directory.

2. Navigieren Sie zu **Einstellungen**  >    >  **Endpunkte Allgemeine**  >  **Portalumleitung**.  

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
- [Informationen zu Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft-Sicherheitsportale und Admin Center](portals.md)