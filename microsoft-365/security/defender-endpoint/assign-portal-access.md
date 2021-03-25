---
title: Zuweisen von Benutzerzugriff zu Microsoft Defender Security Center
description: Weisen Sie dem Microsoft Defender for Endpoint-Portal Lese-, Schreib- oder schreibgeschützten Zugriff zu.
keywords: Zuweisen von Benutzerrollen, Zuweisen von Lese- und Schreibzugriff, Zuweisen von schreibgeschützten Zugriffen, Benutzern, Benutzerrollen, Rollen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164763"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a>Zuweisen von Benutzerzugriff zu Microsoft Defender Security Center

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- Azure Active Directory
- Office 365
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint unterstützt zwei Möglichkeiten zum Verwalten von Berechtigungen:

- **Grundlegende Berechtigungsverwaltung:** Legen Sie Berechtigungen auf Vollzugriff oder schreibgeschützt.
- **Rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC):** Legen Sie präzise Berechtigungen durch Definieren von Rollen, Zuweisen von Azure AD-Benutzergruppen zu den Rollen und Gewähren von Benutzergruppenzugriff auf Gerätegruppen. Weitere Informationen zur RBAC finden Sie unter [Verwalten des Portalzugriffs mithilfe der rollenbasierten Zugriffssteuerung](rbac.md).

> [!NOTE]
> Wenn Sie bereits grundlegende Berechtigungen zugewiesen haben, können Sie jederzeit zu RBAC wechseln. Berücksichtigen Sie Folgendes, bevor Sie die Option verwenden:
> 
> - Benutzern mit Vollzugriff (Benutzern, denen die Verzeichnisrolle globaler Administrator oder Sicherheitsadministrator in Azure AD zugewiesen ist) wird automatisch die standardmäßige Defender for Endpoint-Administratorrolle zugewiesen, die ebenfalls Vollzugriff hat. Zusätzliche Azure AD-Benutzergruppen können nach dem Wechsel zu RBAC der Administratorrolle Defender for Endpoint zugewiesen werden.  Nur Benutzer, die der Administratorrolle Defender for Endpoint zugewiesen sind, können Berechtigungen mithilfe von RBAC verwalten. 
> - Benutzer mit schreibgeschützten Zugriffen (Sicherheitsleser) verlieren den Zugriff auf das Portal, bis ihnen eine Rolle zugewiesen wurde. Beachten Sie, dass nur Azure AD-Benutzergruppen eine Rolle unter RBAC zugewiesen werden kann.
> - Nach dem Wechsel zu RBAC können Sie nicht mehr auf die Verwendung der grundlegenden Berechtigungsverwaltung umschalten.

## <a name="related-topics"></a>Verwandte Themen

- [Verwenden grundlegender Berechtigungen für den Zugriff auf das Portal](basic-permissions.md)
- [Verwalten des Portalzugriffs mithilfe von RBAC](rbac.md)
