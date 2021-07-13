---
title: Zuweisen von Administratorrollen zum Microsoft 365 Admin Center
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: Erfahren Sie, wie Sie einem Benutzer oder mehreren Benutzern in Ihrem Unternehmen Administratorrollen zuweisen, damit diese bestimmte Aufgaben im Admin Center ausführen können.
ms.openlocfilehash: 575d1d8c6b0ffce40877fb41d28df82c24e84d04
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393775"
---
# <a name="assign-admin-roles"></a>Administratorrollen zuweisen

Wenn Sie die Person sind, die Ihr Microsoft Business-Abonnement erworben hat, sind Sie der globale Administrator. Dies bedeutet, dass Sie unbegrenzte Kontrolle über die Produkte in Ihren Abonnements haben und auf die meisten Daten zugreifen können.

Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](about-admin-roles.md).

Wenn Sie neue Benutzer hinzufügen, wenn Sie ihnen keine Administratorrolle zuweisen, befinden sie sich in der *Benutzerrolle* und verfügen über keine Administratorrechte für eines der Microsoft Admin Center. Wenn Sie jedoch Hilfe benötigen, um Dies zu erledigen, können Sie einem Benutzer eine Administratorrolle zuweisen. Wenn Sie beispielsweise jemanden benötigen, der beim Zurücksetzen von Kennwörtern helfen soll, sollten Sie ihm nicht die globale Administratorrolle zuweisen, sie sollten ihm die Kennwortadministratorrolle zuweisen. Zu viele globale Administratoren mit unbegrenztem Zugriff auf Ihre Daten und Ihr Onlinegeschäft zu ernennen, stellt ein Sicherheitsrisiko dar.

## <a name="watch-add-an-adminbrbr"></a>Überwachung: Hinzufügen eines Administrators<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](../../business-video/index.yml) an.

## <a name="assign-admin-roles"></a>Administratorrollen zuweisen 

Sie können einer Rolle auf zwei verschiedene Arten Benutzer zuweisen:

- Sie können zu den Details des Benutzers wechseln und **Rollen verwalten,** um dem Benutzer eine Rolle zuzuweisen.
- Sie können auch zu **"Rollen"** wechseln und die Rolle auswählen und dann mehrere Benutzer hinzufügen.

### <a name="assign-admin-roles-to-users-using-roles"></a>Zuweisen von Administratorrollen zu Benutzern mithilfe von Rollen

1. Wechseln Sie im Admin Center zu **"Rollen".** Wählen Sie die **Registerkarten Azure AD** oder **Intune** aus, um die für Ihre Organisation verfügbaren Administratorrollen anzuzeigen.
2. Wählen Sie die Administratorrolle aus, der Sie den Benutzer zuweisen möchten.
3. Wählen Sie **"Zugewiesene Administratoren**  >  **hinzufügen"** aus.
4. Geben Sie den **Anzeigenamen** oder **Benutzernamen** des Benutzers ein, und wählen Sie dann den Benutzer aus der Liste der Vorschläge aus.
5. Fügen Sie mehrere Benutzer hinzu, bis Sie fertig sind.
6. Wählen Sie **"Speichern"** aus, und dann wird der Benutzer der Liste der zugewiesenen Administratoren hinzugefügt.

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>Zuweisen eines Benutzers zu einer Administratorrolle über "Aktive Benutzer"

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin  Center zur Seite > ["Aktive Benutzer von](https://go.microsoft.com/fwlink/p/?linkid=834822) Benutzern".

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

::: moniker-end

2. Wählen Sie auf der Seite **"Aktive Benutzer"** den Benutzer aus, dessen Administratorrolle Sie ändern möchten. Wählen Sie im Flyoutbereich unter **"Rollen"** die Option **"Rollen verwalten"** aus.

3. Wählen Sie die Administratorrolle aus, die Sie dem Benutzer zuweisen möchten. Wenn die gesuchte Rolle nicht angezeigt wird, wählen Sie **"Alle anzeigen"** am Ende der Liste aus.

## <a name="assign-admin-roles-to-multiple-users"></a>Zuweisen von Administratorrollen zu mehreren Benutzern

Wenn Sie PowerShell kennen, lesen [Sie "Zuweisen von Rollen zu Benutzerkonten mit PowerShell".](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) PowerShell ist ideal für die Zuweisung von Rollen zu mehreren hundert Benutzern geeignet.
  
Verwenden Sie die folgenden Anweisungen, um dutzenden Benutzern Rollen zuzuweisen.

## <a name="check-admin-roles-in-your-organization"></a>Überprüfen von Administratorrollen in Ihrer Organisation

Möglicherweise verfügen Sie nicht über die richtigen Berechtigungen, um anderen Benutzern Administratorrollen zuzuweisen. Stellen Sie sicher, dass Sie über die richtigen Berechtigungen verfügen, oder bitten Sie einen anderen Administrator, Rollen für Sie zuzuweisen.

Sie können Administratorrollenberechtigungen auf zwei verschiedene Arten überprüfen:

- Sie können zu den Details des Benutzers wechseln und auf der **Seite "Konto"** unter **"Rollen"** suchen.
- Sie können auch zu **"Rollen"** wechseln und die Administratorrolle auswählen und die zugewiesenen Administratoren auswählen, um zu sehen, welche Benutzer zugewiesen sind.

## <a name="related-content"></a>Verwandte Inhalte

[Informationen zu Microsoft 365 Administratorrollen](about-admin-roles.md) (Artikel)\
[Administratorrollenberechtigungen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) (Artikel)\
[Zuweisen von Rollen zu Benutzerkonten mit PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (Artikel)\
[Autorisieren oder Entfernen von Partnerbeziehungen](../misc/add-partner.md) (Artikel)