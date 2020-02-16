---
title: Verwalten des Zugriffs auf Microsoft Threat Protection-Daten im Microsoft 365 Security Center
description: Erfahren Sie, wie Sie Berechtigungen für Daten in Microsoft Threat Protection verwalten
keywords: Zugriff, Berechtigungen, MTP, Microsoft Threat Protection, M365, Sicherheit, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, Bereich, bereichsbezogen, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 1b6411d04c2ecc8c646072e4da61dea1c470db5a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42086974"
---
# <a name="manage-access-to-microsoft-threat-protection"></a>Verwalten des Zugriffs auf Microsoft Threat Protection

**Gilt für:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Konten, denen die folgenden Azure Active Directory (AD)-Rollen zugewiesen sind, können auf Microsoft Threat Protection-Funktionen und -Daten zugreifen:
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
Der Zugriff auf Microsoft Threat Protection-Daten kann über den Bereich gesteuert werden, der Benutzergruppen in der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC) von Microsoft Defender ATP zugewiesen ist. Wenn Ihr Zugriff in Microsoft Defender ATP nicht auf eine bestimmte Gruppe von Geräten eingeschränkt wurde, haben Sie Vollzugriff auf die Daten in Microsoft Threat Protection. Sobald Ihrem Konto jedoch bereichsbezogener Zugriff gewährt wurde, werden nur die Daten zu den Geräten in dem betreffenden Bereich angezeigt.

Wenn Sie beispielsweise nur einer Benutzergruppe mit einer Microsoft Defender ATP-Rolle angehören und dieser Benutzergruppe nur der Zugriff auf Verkaufsgeräte gewährt wurde, werden Ihnen in Microsoft Threat Protection nur Daten zu Verkaufsgeräten angezeigt. Weitere Informationen hierzu finden Sie unter [RBAC-Einstellungen in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac).

### <a name="microsoft-cloud-app-security-access-controls"></a>Microsoft Cloud App Security-Steuerelemente
Während der Vorschau erzwingt Microsoft Threat Protection keine auf den Sicherheitseinstellungen in Cloud App Security basierende Zugriffssteuerung. Diese Einstellungen wirken sich nicht auf den Zugriff auf Microsoft Threat Protection-Daten aus.

## <a name="related-topics"></a>Verwandte Themen

- [Azure AD-Rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Rollenbasierte Zugriffssteuerung in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Rollen in Cloud App Security](https://docs.microsoft.com/cloud-app-security/manage-admins)
