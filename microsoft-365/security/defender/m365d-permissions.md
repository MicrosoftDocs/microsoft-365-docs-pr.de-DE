---
title: Verwalten des Zugriffs auf Microsoft 365 von Defender-Daten im Microsoft 365 Security Center
description: Informationen zum Verwalten von Berechtigungen für Daten in Microsoft 365 Defender
keywords: Access, permissions, Microsoft 365 Defender, M365, security, MCAS, Cloud App Security, Microsoft Defender for Endpoint, scope, scoping, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 52e4e9fc8c73d1adca0c24c5bebb50f9dcf7ac6f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935629"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a>Verwalten des Zugriffs auf Microsoft 365 Defender mit Azure Active Directory globalen Rollen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Es gibt zwei Möglichkeiten zum Verwalten des Zugriffs auf Microsoft 365 Defender
- **Globale Azure Active Directory (AD)-Rollen**
- **Benutzerdefinierter Rollenzugriff**

Konten, denen die folgenden globalen **Azure Active Directory (AD)-Rollen** zugewiesen sind, können auf Microsoft 365 Funktionen und Daten von Defender zugreifen:
- Globaler Administrator
- Sicherheitsadministrator
- Sicherheitsoperator
- Globaler Leser
- Sicherheitsleseberechtigter

Zum Überprüfen von Konten mit diesen Rollen, siehe[Berechtigungen im Microsoft 365 Security Center](https://security.microsoft.com/permissions).

**Benutzerdefinierter** Rollenzugriff ist eine neue Funktion in Microsoft 365 Defender und ermöglicht ihnen die Verwaltung des Zugriffs auf bestimmte Daten, Aufgaben und Funktionen in Microsoft Defender 365. Benutzerdefinierte Rollen bieten mehr Kontrolle als globale Azure AD-Rollen und bieten Benutzern nur den zugriff, den sie benötigen, mit den am wenigsten zulässigen Rollen.  Benutzerdefinierte Rollen können zusätzlich zu globalen Azure AD-Rollen erstellt werden. [Erfahren Sie mehr über benutzerdefinierte Rollen](custom-roles.md).

> ! [HINWEIS] Dieser Artikel gilt nur für die Verwaltung globaler Azure Active Directory Rollen. Weitere Informationen zum Verwenden der benutzerdefinierten rollenbasierten Zugriffssteuerung finden Sie unter [Benutzerdefinierte Rollen für die rollenbasierte Zugriffssteuerung.](custom-roles.md)

## <a name="access-to-functionality"></a>Zugriff auf Funktionen
Der Zugriff auf bestimmte Funktionen hängt von Ihrer [Azure AD-Rolle](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)ab. Wenden Sie sich an einen globalen Administrator, wenn Sie Zugriff auf bestimmte Funktionen benötigen, für die Ihnen oder Ihrer Benutzergruppe eine neue Rolle zugewiesen werden muss.

### <a name="approve-pending-automated-tasks"></a>Genehmigen ausstehender automatischer Vorgänge
[Automatisierte Untersuchungen und Reaktionen](m365d-autoir-actions.md) können Maßnahmen an E-Mails, Weiterleitungsregeln, Dateien, Persistenzmechanismen und anderen Artefakten durchführen, die bei Untersuchungen gefunden werden. Um ausstehende Aktionen, für die eine explizite Genehmigung erforderlich ist, genehmigen oder ablehnen zu können, müssen Ihnen in Microsoft 365 bestimmte Rollen zugewiesen sein. Weitere Informationen hierzu finden Sie unter [Info-Center-Berechtigungen](m365d-action-center.md#required-permissions-for-action-center-tasks).

## <a name="access-to-data"></a>Zugriff auf Daten
Der Zugriff auf Microsoft 365 Defender-Daten kann mithilfe des Bereichs gesteuert werden, der Benutzergruppen in Microsoft Defender for Endpoint role-based Access Control (RBAC) zugewiesen ist. Wenn Ihr Zugriff nicht auf eine bestimmte Gruppe von Geräten in Defender for Endpoint begrenzt wurde, haben Sie vollzugriff auf Daten in Microsoft 365 Defender. Sobald Ihrem Konto jedoch bereichsbezogener Zugriff gewährt wurde, werden nur die Daten zu den Geräten in dem betreffenden Bereich angezeigt.

Wenn Sie beispielsweise nur einer Benutzergruppe mit einer Microsoft Defender for Endpoint-Rolle angehören und diese Benutzergruppe nur Zugriff auf Verkaufsgeräte erhalten hat, werden nur Daten zu Verkaufsgeräten in Microsoft 365 Defender angezeigt. [Weitere Informationen zu RBAC-Einstellungen in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Microsoft Cloud App Security-Steuerelemente
Während der Vorschau erzwingt Microsoft 365 Defender keine Zugriffssteuerungen basierend auf Cloud App Security Einstellungen. Der Zugriff auf Microsoft 365 Defender-Daten wird von diesen Einstellungen nicht beeinflusst.

## <a name="related-topics"></a>Verwandte Themen
- [Benutzerdefinierte Rollen in der rollenbasierten Zugriffssteuerung für Microsoft 365 Defender](custom-roles.md)
- [Azure AD-Rollen](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender for Endpoint RBAC](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Rollen in Cloud App Security](/cloud-app-security/manage-admins)