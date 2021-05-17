---
title: Benutzerdefinierte Rollen für die rollenbasierte Zugriffssteuerung
description: Informationen zum Verwalten benutzerdefinierter Rollen in Microsoft 365 Security Center
keywords: Access, permissions, Microsoft 365 Defender, M365, security, MCAS, Cloud App Security, Microsoft Defender for Endpoint, scope, scoping, RBAC, roles-based access, custom roles-based access, roles-based auth, RBAC in MDO, roles, rolegroups, permissions inheritance, fine-grained permissions
search.product: eADQiWindows 10XVcnh
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 9dfa9f113c0a7d57360c2da6105cbfa07fcf6a99
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935689"
---
# <a name="custom-roles-in-role-based-access-control-for-microsoft-365-defender"></a>Benutzerdefinierte Rollen in der rollenbasierten Zugriffssteuerung für Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Gilt für:**

- Microsoft 365 Defender
 
Es gibt zwei Arten von Rollen, die für den Zugriff auf defender Microsoft 365 können:
- **Globale Azure Active Directory (AD)-Rollen**
- **Benutzerdefinierte Rollen**

Der Zugriff auf Microsoft 365 Defender kann gemeinsam mithilfe von globalen Rollen in Azure Active Directory [(AAD) verwaltet werden.](m365d-permissions.md)

Wenn Sie mehr Flexibilität und Kontrolle über den Zugriff auf bestimmte Produktdaten benötigen, kann Microsoft 365 Defender-Zugriff auch durch die Erstellung von benutzerdefinierten Rollen über jedes jeweilige Sicherheitsportal verwaltet werden.  

Eine benutzerdefinierte Rolle, die über Microsoft Defender for Endpoint erstellt wurde, ermöglicht beispielsweise den Zugriff auf die relevanten Produktdaten, einschließlich Endpunktdaten innerhalb des Microsoft 365 Security Centers. Auf ähnliche Weise würde eine benutzerdefinierte Rolle, die über Microsoft Defender für Office 365 erstellt wurde, den Zugriff auf die relevanten Produktdaten ermöglichen, einschließlich E-Mail & Zusammenarbeitsdaten innerhalb des Microsoft 365 Security Centers.

Benutzer mit vorhandenen benutzerdefinierten Rollen können auf Daten im Microsoft 365 Sicherheitscenter gemäß ihren vorhandenen Arbeitsauslastungsberechtigungen zugreifen, ohne dass eine zusätzliche Konfiguration erforderlich ist.

## <a name="create-and-manage-custom-roles"></a>Erstellen und Verwalten benutzerdefinierter Rollen
Benutzerdefinierte Rollen und Berechtigungen können über jedes der folgenden Sicherheitsportale erstellt und einzeln verwaltet werden: 

- Microsoft Defender for Endpoint – [Bearbeiten von Rollen in Microsoft Defender for Endpoint](../defender-endpoint/user-roles.md)
- Microsoft Defender for Office 365 – [Berechtigungen im Security & Compliance Center](../office-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide)
- Microsoft Cloud App Security – [Verwalten des Administratorzugriffs](/cloud-app-security/manage-admins)

Jede benutzerdefinierte Rolle, die über ein einzelnes Portal erstellt wird, ermöglicht den Zugriff auf die Daten des relevanten Produktportals. Beispielsweise ermöglicht eine benutzerdefinierte Rolle, die über Microsoft Defender for Endpoint erstellt wurde, nur den Zugriff auf Defender for Endpoint-Daten.

> [!TIP]
> Der Zugriff auf Berechtigungen und Rollen kann auch über das Microsoft 365 sicherheitscenter durch Auswählen von Berechtigungen & Rollen im Navigationsbereich möglich sein. Der Zugriff auf Microsoft Cloud App Security (MCAS) wird über das MCAS-Portal verwaltet und steuert auch den Zugriff auf Microsoft Defender for Identity.  Siehe [Microsoft Cloud App Security](/cloud-app-security/manage-admins)

> [!NOTE]
> Benutzerdefinierte Rollen, die in Microsoft Cloud App Security erstellt wurden, haben auch Zugriff auf Microsoft Defender for Identity-Daten. Benutzer mit Benutzergruppenadministrator oder App/Instanz-Administrator-Microsoft Cloud App Security können nicht über das Microsoft Cloud App Security Sicherheitscenter Microsoft 365 auf Microsoft Cloud App Security zugreifen.

## <a name="manage-permissions-and-roles-in-the-microsoft-365-security-center"></a>Verwalten von Berechtigungen und Rollen im Microsoft 365 Security Center
Berechtigungen und Rollen können auch im Microsoft 365 verwaltet werden:

1. Melden Sie sich beim Microsoft 365 Security Center unter security.microsoft.com.
2. Wählen Sie im Navigationsbereich Berechtigungen **& Rollen aus.**
3. Wählen Sie **unter der Kopfzeile** Berechtigungen die Option **Rollen aus.**

> [!NOTE]
> Dies gilt nur für Defender für Office 365 und Defender for Endpoint. Der Zugriff auf andere Arbeitsauslastungen muss in den entsprechenden Portalen ausgeführt werden.


## <a name="required-roles-and-permissions"></a>Erforderliche Rollen und Berechtigungen
In der folgenden Tabelle sind die Rollen und Berechtigungen aufgeführt, die für den Zugriff auf die einzelnen einheitlichen Funktionen in jeder Arbeitsauslastung erforderlich sind. Rollen, die in der folgenden Tabelle definiert sind, beziehen sich auf benutzerdefinierte Rollen in einzelnen Portalen und sind nicht mit globalen Rollen in Azure AD verbunden, auch wenn sie ähnlich benannt sind.

> [!NOTE]
> Die Vorfallverwaltung erfordert Verwaltungsberechtigungen für alle Produkte, die Teil des Vorfalls sind.
 
| **Eine der folgenden Rollen ist für defender Microsoft 365 erforderlich**  | **Eine der folgenden Rollen ist für Defender for Endpoint erforderlich**  | **Eine der folgenden Rollen ist für Defender für Office 365** | **Eine der folgenden Rollen ist für die Cloud App Security** | 
|---------|---------|---------|---------|
| Anzeigen von Untersuchungsdaten: <ul><li>Warnungsseite</li> <li>Benachrichtigungswarteschlange</li> <li>Vorfälle</li>  <li>Warteschlange für Vorfälle</li> <li>Info-Center</li></ul>| Anzeigen von Datensicherheitsvorgängen | <ul><li>Benachrichtigungen nur anzeigen </li> <li>Organisationskonfiguration</li><li>Überwachungsprotokolle</li> <li>Nur anzeigen von Überwachungsprotokollen</li> <li>Benutzer mit Leseberechtigung für Sicherheitsfunktionen</li> <li>Sicherheitsadministrator</li><li>Nur-Ansichtsempfänger</li></ul>  | <ul><li>Globaler Administrator</li> <li>Sicherheitsadministrator</li> <li>Compliance-Administrator</li> <li>Sicherheitsoperator</li> <li>Benutzer mit Leseberechtigung für Sicherheitsfunktionen</li> <li>Globale Leseberechtigung</li></ul> |
| Anzeigen von Jagddaten | Anzeigen von Datensicherheitsvorgängen | <ul><li>Benutzer mit Leseberechtigung für Sicherheitsfunktionen</li> <li>Sicherheitsadministrator</li> <li>Nur-Ansichtsempfänger</li> | <ul><li>Globaler Administrator</li> <li>Sicherheitsadministrator</li> <li>Compliance-Administrator</li> <li>Sicherheitsoperator</li> <li>Benutzer mit Leseberechtigung für Sicherheitsfunktionen</li> <li>Globale Leseberechtigung</li></ul> |
| Verwalten von Warnungen und Vorfällen | Warnungsuntersuchung | <ul><li>Verwalten von Warnungen</li> <li>Sicherheitsadministrator</li> | <ul><li>Globaler Administrator</li> <li>Sicherheitsadministrator</li> <li>Compliance-Administrator</li> <li>Sicherheitsoperator</li> <li>Benutzer mit Leseberechtigung für Sicherheitsfunktionen</li></ul> |
| Behebung des Aktionscenters | Aktive Korrekturaktionen – Sicherheitsvorgänge | Suchen und Löschen | |
| Festlegen von benutzerdefinierten Erkennungen | Verwalten von Sicherheitseinstellungen |<ul><li>Verwalten von Warnungen</li> <li>Sicherheitsadministrator</li></ul> | <ul><li>Globaler Administrator</li> <li>Sicherheitsadministrator</li> <li>Compliance-Administrator</li> <li>Sicherheitsoperator</li> <li>Benutzer mit Leseberechtigung für Sicherheitsfunktionen</li> <li>Globale Leseberechtigung</li></ul> |
| Bedrohungsanalyse | Daten zu Warnungen und Vorfällen: <ul><li>Anzeigen von Datensicherheitsvorgängen</li></ul>TVM-Gegenmaßnahmen:<ul><li>Anzeigen von Daten – Bedrohung und Sicherheitsrisikomanagement</li></ul> | Daten zu Warnungen und Vorfällen:<ul> <li>Benachrichtigungen nur anzeigen</li> <li>Verwalten von Warnungen</li> <li>Organisationskonfiguration</li><li>Überwachungsprotokolle</li> <li>Nur anzeigen von Überwachungsprotokollen</li><li>Benutzer mit Leseberechtigung für Sicherheitsfunktionen</li> <li>Sicherheitsadministrator</li><li>Nur-Ansichtsempfänger</li> </ul> Verhinderte E-Mail-Versuche: <ul><li>Benutzer mit Leseberechtigung für Sicherheitsfunktionen</li> <li>Sicherheitsadministrator</li><li>Nur-Ansichtsempfänger</li> | Nicht verfügbar für MCAS- oder MDI-Benutzer |

Zum Anzeigen von Nachsuchendaten aus Microsoft Defender for Endpoint sind beispielsweise Berechtigungen zum Anzeigen von Datensicherheitsvorgängen erforderlich.  

Ebenso benötigen Benutzer eine der folgenden Rollen, um Office 365 von Microsoft Defender für die Suche anzeigen zu können:  

- Anzeigen von Datensicherheitsvorgängen
- Benutzer mit Leseberechtigung für Sicherheitsfunktionen
- Sicherheitsadministrator
- Nur-Ansichtsempfänger

## <a name="related-topics"></a>Verwandte Themen
- [Verwalten des Zugriffs auf Microsoft 365 Defender](m365d-permissions.md)
- [Verwalten des Administratorzugriffs für MCAS](/cloud-app-security/manage-admins)
