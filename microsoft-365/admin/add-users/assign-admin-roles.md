---
title: Zuweisen von Administratorrollen Microsoft 365 Admin Center
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: Erfahren Sie, wie Sie einem Benutzer oder mehreren Benutzern in Ihrem Unternehmen Administratorrollen zuweisen, damit sie bestimmte Aufgaben im Admin Center ausführen können.
ms.openlocfilehash: e53d1a414d081ddb74a1c4784adcd982b6194691
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683211"
---
# <a name="assign-admin-roles"></a>Zuweisen von Administratorrollen

Wenn Sie die Person sind, die Ihr Microsoft Business-Abonnement erworben hat, sind Sie der globale Administrator. Dies bedeutet, dass Sie unbegrenzte Kontrolle über die Produkte in Ihren Abonnements haben und auf die meisten Daten zugreifen können.

Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](about-admin-roles.md).

Wenn Sie neue Benutzer hinzufügen und ihnen keine Administratorrolle zuweisen,  befinden sie sich in der Benutzerrolle und verfügen nicht über Administratorrechte für die Microsoft Admin Center. Wenn Sie jedoch Hilfe beim Erledigen von Aufgaben benötigen, können Sie einem Benutzer eine Administratorrolle zuweisen. Wenn Sie z. B. eine Person benötigen, die beim Zurücksetzen von Kennwörtern helfen soll, sollten Sie ihnen nicht die globale Administratorrolle zuweisen, sondern ihnen die Administratorrolle kennwort zuweisen. Zu viele globale Administratoren mit unbegrenztem Zugriff auf Ihre Daten und Ihr Onlinegeschäft zu ernennen, stellt ein Sicherheitsrisiko dar.

## <a name="watch-add-an-adminbrbr"></a>Watch: Hinzufügen eines Admins<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](../../business-video/index.yml) an.

## <a name="assign-admin-roles"></a>Zuweisen von Administratorrollen 

Sie können einer Rolle auf 2 unterschiedliche Weise Benutzer zuweisen:

- Sie können zu den Details des Benutzers wechseln und **Rollen** verwalten, um dem Benutzer eine Rolle zuzuordnen.
- Sie können auch zu **Rollen** wechseln und die Rolle auswählen und dann mehrere Benutzer hinzufügen.

### <a name="assign-admin-roles-to-users-using-roles"></a>Zuweisen von Administratorrollen zu Benutzern mithilfe von Rollen

1. Wechseln Sie im Admin Center zu **Rollen**. Wählen Sie **die Registerkarten Azure AD** oder **Intune** aus, um die für Ihre Organisation verfügbaren Administratorrollen anzeigen zu können.
2. Wählen Sie die Administratorrolle aus, der Sie den Benutzer zuweisen möchten.
3. Wählen **Sie Zugewiesene Administratoren** Hinzufügen  >  **aus.**
4. Geben Sie den **Anzeigenamen oder** Benutzernamen des Benutzers **ein,** und wählen Sie dann den Benutzer aus der Liste der Vorschläge aus.
5. Fügen Sie mehrere Benutzer hinzu, bis Sie fertig sind.
6. Wählen **Sie Speichern** aus, und dann wird der Benutzer der Liste der zugewiesenen Administratoren hinzugefügt.

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>Zuweisen eines Benutzers zu einer Administratorrolle über "Aktive Benutzer"

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu **Seite Aktive** > [Benutzer.](https://go.microsoft.com/fwlink/p/?linkid=834822)

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

::: moniker-end

2. Wählen Sie **auf der Seite** Aktive Benutzer den Benutzer aus, dessen Administratorrolle Sie ändern möchten. Wählen Sie im Flyoutbereich unter **Rollen** die Option Rollen **verwalten aus.**

3. Wählen Sie die Administratorrolle aus, die Sie dem Benutzer zuweisen möchten. Wenn die gesuchte Rolle nicht angezeigt wird, wählen Sie **am** Ende der Liste Alle anzeigen aus.

## <a name="assign-admin-roles-to-multiple-users"></a>Zuweisen von Administratorrollen zu mehreren Benutzern

Wenn Sie PowerShell kennen, lesen Sie Zuweisen von Rollen [zu Benutzerkonten mit PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md). PowerShell ist ideal für die Zuweisung von Rollen zu mehreren hundert Benutzern geeignet.
  
Verwenden Sie die folgenden Anweisungen, um dutzenden Benutzern Rollen zuzuweisen.

## <a name="check-admin-roles-in-your-organization"></a>Überprüfen von Administratorrollen in Ihrer Organisation

Möglicherweise verfügen Sie nicht über die richtigen Berechtigungen zum Zuweisen von Administratorrollen zu anderen Benutzern. Überprüfen Sie, ob Sie über die richtigen Berechtigungen verfügen, oder bitten Sie einen anderen Administrator, Ihnen Rollen zu zuweisen.

Sie können die Administratorrolleberechtigungen auf zwei verschiedene Arten überprüfen:

- Sie können zu den Details des Benutzers wechseln und auf der Seite Konto unter **Rollen** **suchen.**
- Sie können auch zu **Rollen** wechseln und die Administratorrolle auswählen und zugewiesene Administratoren auswählen, um zu sehen, welche Benutzer zugewiesen sind.

## <a name="related-content"></a>Verwandte Inhalte

[Informationen Microsoft 365 Administratorrollen](about-admin-roles.md) (Artikel)\
[Administratorrolleberechtigungen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) (Artikel)\
[Zuweisen von Rollen zu Benutzerkonten mit PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (Artikel)\
[Autorisieren oder Entfernen von Partnerbeziehungen](../misc/add-partner.md) (Artikel)