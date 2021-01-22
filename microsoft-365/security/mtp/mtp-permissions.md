---
title: Verwalten des Zugriffs auf Microsoft 365 Defender-Daten im Microsoft 365 Security Center
description: Informationen zum Verwalten von Berechtigungen für Daten in Microsoft 365 Defender
keywords: Zugriff, Berechtigungen, MTP, Microsoft Threat Protection, M365, Sicherheit, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, Bereich, bereichsbezogen, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f042b0c6314e8e5f80d40d76159712bc817a01c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930138"
---
# <a name="manage-access-to-microsoft-365-defender"></a>Verwalten des Zugriffs auf Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Konten, denen die folgenden Azure Active Directory (AD)-Rollen zugewiesen sind, können auf Microsoft 365 -Defender-Funktionen und -Daten zugreifen:
- Globaler Administrator
- Sicherheitsadministrator
- Sicherheitsoperator
- Globaler Leser
- Sicherheitsleseberechtigter

Zum Überprüfen von Konten mit diesen Rollen, siehe[Berechtigungen im Microsoft 365 Security Center](https://security.microsoft.com/permissions).

## <a name="access-to-functionality"></a>Zugriff auf Funktionen
Der Zugriff auf bestimmte Funktionen hängt von Ihrer [Azure AD-Rolle](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)ab. Wenden Sie sich an einen globalen Administrator, wenn Sie Zugriff auf bestimmte Funktionen benötigen, für die Ihnen oder Ihrer Benutzergruppe eine neue Rolle zugewiesen werden muss.

### <a name="approve-pending-automated-tasks"></a>Genehmigen ausstehender automatischer Vorgänge
[Automatisierte Untersuchungen und Reaktionen](mtp-autoir-actions.md) können Maßnahmen an E-Mails, Weiterleitungsregeln, Dateien, Persistenzmechanismen und anderen Artefakten durchführen, die bei Untersuchungen gefunden werden. Um ausstehende Aktionen, für die eine explizite Genehmigung erforderlich ist, genehmigen oder ablehnen zu können, müssen Ihnen in Microsoft 365 bestimmte Rollen zugewiesen sein. Weitere Informationen hierzu finden Sie unter [Info-Center-Berechtigungen](mtp-action-center.md#required-permissions-for-action-center-tasks).

## <a name="access-to-data"></a>Zugriff auf Daten
Der Zugriff auf Microsoft 365 -Defender-Daten kann mithilfe des Bereichs gesteuert werden, der Benutzergruppen in der rollenbasierten Zugriffssteuerung (RBAC) von Microsoft Defender for Endpoint zugewiesen ist. Wenn Ihr Zugriff nicht auf eine bestimmte Gruppe von Geräten im Defender for Endpoint begrenzt wurde, haben Sie Vollzugriff auf Daten in Microsoft 365 Defender. Sobald Ihrem Konto jedoch bereichsbezogener Zugriff gewährt wurde, werden nur die Daten zu den Geräten in dem betreffenden Bereich angezeigt.

Wenn Sie beispielsweise nur zu einer Benutzergruppe mit einer Microsoft Defender for Endpoint-Rolle gehören und dieser Benutzergruppe nur Zugriff auf Verkaufsgeräte gegeben wurde, werden nur Daten zu Verkaufsgeräten in Microsoft 365 Defender angezeigt. [Weitere Informationen zu rbAC-Einstellungen in Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Microsoft Cloud App Security-Steuerelemente
Während der Vorschau erzwingt Microsoft 365 Defender keine Zugriffssteuerungen basierend auf Cloud App Security-Einstellungen. Der Zugriff auf Microsoft 365 Defender-Daten ist von diesen Einstellungen nicht betroffen.

## <a name="related-topics"></a>Verwandte Themen

- [Azure AD-Rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender für Endpoint RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Rollen in Cloud App Security](https://docs.microsoft.com/cloud-app-security/manage-admins)
