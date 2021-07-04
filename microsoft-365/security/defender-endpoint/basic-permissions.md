---
title: Verwenden grundlegender Berechtigungen für den Zugriff auf Microsoft Defender Security Center
description: Erfahren Sie, wie Sie grundlegende Berechtigungen für den Zugriff auf das Microsoft Defender für Endpunkt-Portal verwenden.
keywords: Benutzerrollen zuweisen, Lese- und Schreibzugriff zuweisen, schreibgeschützten Zugriff zuweisen, Benutzer, Benutzerrollen, Rollen
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
ms.openlocfilehash: e7c208998e436245c53b90905858b7cf7ebe91d6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290195"
---
# <a name="use-basic-permissions-to-access-the-portal"></a>Verwenden von grundlegenden Berechtigungen für den Zugriff auf das Portal

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- Azure Active Directory
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

Informationen zur Verwendung der grundlegenden Berechtigungsverwaltung finden Sie in den nachstehenden Anweisungen.

Sie können eine der folgenden Lösungen verwenden:
- Azure PowerShell
- Azure-Portal

Um eine präzise Kontrolle über Berechtigungen zu erhalten, [wechseln Sie zur rollenbasierten Zugriffssteuerung.](rbac.md)

## <a name="assign-user-access-using-azure-powershell"></a>Zuweisen des Benutzerzugriffs mithilfe von Azure PowerShell
Sie können Benutzern eine der folgenden Berechtigungsstufen zuweisen:
- Vollzugriff (Lese- und Schreibzugriff)
- Schreibgeschützter Zugriff

### <a name="before-you-begin"></a>Bevor Sie beginnen

- Installieren Sie Azure PowerShell. Weitere Informationen finden Sie unter ["So installieren und konfigurieren Sie Azure PowerShell.](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)<br>

    > [!NOTE]
    > Sie müssen die PowerShell-Cmdlets in einer Befehlszeile mit erhöhten Rechten ausführen.

- Verbinden zu Ihrem Azure Active Directory. Weitere Informationen finden Sie unter [Verbinden-MsolService](/powershell/module/msonline/connect-msolservice).

**Vollzugriff** <br>
Benutzer mit Vollzugriff können sich anmelden, alle Systeminformationen anzeigen und Warnungen auflösen, Dateien für eine umfassende Analyse übermitteln und das Onboardingpaket herunterladen.
Das Zuweisen von Vollzugriffsrechten erfordert das Hinzufügen der Benutzer zu den integrierten AAD-Rollen "Sicherheitsadministrator" oder "Globaler Administrator".

**Schreibgeschützter Zugriff** <br>
Benutzer mit schreibgeschütztem Zugriff können sich anmelden, alle Warnungen und zugehörige Informationen anzeigen.
Sie können keine Warnungszustände ändern, Keine Dateien für eine umfassende Analyse übermitteln oder Vorgänge zur Zustandsänderung ausführen.
Um schreibgeschützte Zugriffsrechte zuzuweisen, müssen Sie die Benutzer der integrierten Azure AD-Rolle "Security Reader" hinzufügen.

Führen Sie die folgenden Schritte aus, um Sicherheitsrollen zuzuweisen:

- Weisen Sie der Sicherheitsadministratorrolle mithilfe des folgenden Befehls Benutzer für Lese- **und Schreibzugriff** zu:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- Weisen Sie für **den schreibgeschützten** Zugriff benutzer mithilfe des folgenden Befehls der Rolle "Sicherheitsleseberechtigter" zu:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

Weitere Informationen finden Sie unter [Hinzufügen oder Entfernen von Gruppenmitgliedern mit Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).

## <a name="assign-user-access-using-the-azure-portal"></a>Zuweisen des Benutzerzugriffs über das Azure-Portal

Weitere Informationen finden Sie unter [Zuweisen von Administrator- und Nicht-Administratorrollen zu Benutzern mit Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="related-topic"></a>Verwandtes Thema

- [Verwalten des Portalzugriffs mithilfe des RBAC](rbac.md)
