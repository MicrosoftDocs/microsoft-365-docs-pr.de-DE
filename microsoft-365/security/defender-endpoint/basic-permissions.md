---
title: Verwenden grundlegender Berechtigungen für den Zugriff auf Microsoft Defender Security Center
description: Erfahren Sie, wie Sie grundlegende Berechtigungen für den Zugriff auf das Microsoft Defender for Endpoint-Portal verwenden.
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
ms.technology: mde
ms.openlocfilehash: cb5762d2a9e4b62432aba6dacd1033ddc3c7daf2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163671"
---
# <a name="use-basic-permissions-to-access-the-portal"></a>Verwenden grundlegender Berechtigungen für den Zugriff auf das Portal

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- Azure Active Directory
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

Lesen Sie die anweisungen unten, um die grundlegende Berechtigungsverwaltung zu verwenden.

Sie können eine der folgenden Lösungen verwenden:
- Azure PowerShell
- Azure-Portal

Wechseln Sie zur rollenbasierten Zugriffssteuerung, um die Berechtigungen präzise [zu steuern.](rbac.md)

## <a name="assign-user-access-using-azure-powershell"></a>Zuweisen des Benutzerzugriffs mithilfe von Azure PowerShell
Sie können Benutzern eine der folgenden Berechtigungsebenen zuweisen:
- Vollzugriff (Lese- und Schreibzugriff)
- Schreibgeschützter Zugriff

### <a name="before-you-begin"></a>Vorbereitung

- Installieren Sie Azure PowerShell. Weitere Informationen finden Sie unter Installieren und Konfigurieren [von Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).<br>

    > [!NOTE]
    > Sie müssen die PowerShell-Cmdlets in einer Befehlszeile mit erhöhten Rechten ausführen.

- Stellen Sie eine Verbindung mit Ihrem Azure Active Directory bereit. Weitere Informationen finden Sie unter [Connect-MsolService](https://docs.microsoft.com/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true).

**Vollzugriff** <br>
Benutzer mit Vollzugriff können sich anmelden, alle Systeminformationen anzeigen und Warnungen auflösen, Dateien für eine umfassende Analyse übermitteln und das Onboardingpaket herunterladen.
Das Zuweisen von Vollzugriffsrechten erfordert das Hinzufügen der Benutzer zu den integrierten AAD-Rollen "Sicherheitsadministrator" oder "Globaler Administrator".

**Schreibgeschützter Zugriff** <br>
Benutzer mit schreibgeschützten Zugriff können sich anmelden, alle Warnungen und zugehörige Informationen anzeigen.
Sie können keine Warnungszustände ändern, Dateien zur tiefen Analyse übermitteln oder Zustandsänderungsvorgänge ausführen.
Zum Zuweisen von schreibgeschützten Zugriffsrechten müssen die Benutzer der integrierten Azure AD-Rolle "Security Reader" hinzugefügt werden.

Verwenden Sie die folgenden Schritte, um Sicherheitsrollen zuzuordnen:

- Weisen **Sie benutzern für lese-** und schreibzugriff die Rolle des Sicherheitsadministrators mithilfe des folgenden Befehls zu:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- Weisen Sie benutzern für den **schreibgeschützten** Zugriff mithilfe des folgenden Befehls die Rolle "Sicherheitsleser" zu:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

Weitere Informationen finden Sie unter [Hinzufügen oder Entfernen von Gruppenmitgliedern mithilfe von Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).

## <a name="assign-user-access-using-the-azure-portal"></a>Zuweisen des Benutzerzugriffs mithilfe des Azure-Portals

Weitere Informationen finden Sie unter [Assign administrator and non-administrator roles to users with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="related-topic"></a>Verwandtes Thema

- [Verwalten des Portalzugriffs mithilfe von RBAC](rbac.md)
