---
title: Hinzufügen oder Entfernen von Mitgliedern aus Microsoft 365 Gruppen
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: Erfahren Sie, wie Sie ein Mitglied zu einer Gruppe hinzufügen, Mitglieder aus der Gruppe entfernen und den Gruppenbesitzerstatus im Microsoft 365 verwalten.
ms.openlocfilehash: 3ab3ebe21caa2d9d3dfa381dd3b68c9d2512cb79
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593381"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>Hinzufügen oder Entfernen von Mitgliedern aus Microsoft 365 Gruppen mithilfe des Admin Centers

In Microsoft 365 Gruppenmitglieder in der Regel eigene Gruppen erstellen, sich Gruppen hinzufügen, die sie beitreten möchten, oder werden von Gruppenbesitzern eingeladen. Wenn sich der Gruppenbesitz ändert oder Sie feststellen, dass ein Mitglied hinzugefügt oder entfernt werden soll, können Sie diese Änderung auch als Administrator vornehmen. Nur ein globaler Administrator, Exchange, Gruppenadministrator oder Benutzeradministrator kann diese Änderungen vornehmen. [Was ist eine Microsoft 365 Gruppe?](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> Wenn Sie kein Administrator sind, können Sie Mitglieder mithilfe von [Outlook.](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de)
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>Hinzufügen eines Mitglieds zu einer Gruppe im Admin Center

1. Wechseln Sie im Admin Center zur Seite [**Aktive Gruppen.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Klicken Sie auf einen Gruppennamen.

3. Wählen Sie im Detailbereich auf der Registerkarte **Mitglieder** die Option Alle Anzeigen und Verwalten von Mitgliedern **aus,** und wählen Sie **dann Mitglieder hinzufügen aus.**

4. Suchen Sie nach dem Namen des Mitglieds, das hinzugefügt werden soll, oder wählen Sie ihn aus.

5. Klicken Sie auf **Speichern**.

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>Hinzufügen einer Gruppe zu einem Mitglied im Admin Center

1. Wechseln Sie im Admin Center zur Seite [**Aktive**](https://admin.microsoft.com/Adminportal/Home?#/users) Benutzer.  

2. Klicken Sie auf einen Benutzer.

3. Wählen Sie im Detailbereich auf der Registerkarte **Konto** die Option Gruppen **verwalten aus.**

4. Suchen oder wählen Sie den Namen der Gruppe aus, die Sie hinzufügen möchten.

5. Klicken Sie auf **Speichern**.

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>Entfernen eines Mitglieds aus einer Gruppe im Admin Center

> [!NOTE]
> Wenn Sie ein Mitglied aus einer privaten Gruppe entfernen, dauert es 5 Minuten, bis die Person aus der Gruppe blockiert wird.

1. Wechseln Sie im Admin Center zur Seite [**Aktive Gruppen.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Klicken Sie auf einen Gruppennamen.

3. Wählen Sie im Detailbereich auf der Registerkarte **Mitglieder** die Option **Alle anzeigen und Mitglieder verwalten aus.**

4. Wählen Sie neben dem Element, das Sie entfernen möchten, das X aus.

5. Wählen **Sie Speichern** aus, um das Element zu entfernen.

## <a name="manage-group-owner-status"></a>Verwalten des Gruppenbesitzerstatus

Die Person, die eine Gruppe erstellt hat, ist standardmäßig der Gruppenbesitzer. Häufig hat eine Gruppe als Sicherungsunterstützung oder aus anderen Gründen mehrere Besitzer. Mitglieder können in den Status eines Besitzers hochgestuft und Besitzer können in den Status eines Mitglieds heruntergestuft werden.
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>Bewerben eines Mitglieds zum Besitzerstatus im Admin Center

1. Wechseln Sie im Admin Center zur Seite [**Aktive Gruppen.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Klicken Sie auf einen Gruppennamen.

3. Wählen Sie im Detailbereich auf der Registerkarte **Mitglieder** die Option **Alle anzeigen und Besitzer verwalten aus.**

4. Wählen **Sie Besitzer hinzufügen aus.**

5. Aktivieren Sie das Kontrollkästchen neben dem Namen des Mitglieds, das Sie hinzufügen möchten.

6. Wählen **Sie Speichern** und dann Schließen **aus.**

### <a name="remove-owner-status-in-the-admin-center"></a>Entfernen des Besitzerstatus im Admin Center

1. Wechseln Sie im Admin Center zur Seite [**Aktive Gruppen.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Klicken Sie auf einen Gruppennamen.

3. Wählen Sie im Detailbereich auf der Registerkarte **Mitglieder** die Option **Alle anzeigen und Besitzer verwalten aus.**

4. Wählen Sie das X neben dem Namen des Besitzers aus.

5. Klicken Sie auf **Speichern**.

## <a name="more-on-managing-membership"></a>###Weitere Informationen zum Verwalten der Mitgliedschaft

- [Dynamisches Verwalten von Gruppen in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal): Lesen Sie den Abschnitt "Wie kann ich die Mitgliedschaft in einer Gruppe dynamisch verwalten?"

- Verwenden Sie [add-UnifiedGroupLinks,](/powershell/module/exchange/add-unifiedgrouplinks)um Gruppen Hunderte oder Tausende von Benutzern hinzuzufügen.

- [Zuweisen eines neuen Besitzers zu einer verwaisten Gruppe](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="related-content"></a>Verwandte Inhalte

[Aktualisieren von Verteilerlisten auf Microsoft 365 Gruppen in Outlook](../manage/upgrade-distribution-lists.md) (Artikel)

[Warum Sie Ihre Verteilerlisten zu Gruppen in Outlook aktualisieren sollten](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188) (Artikel)

[Verwalten des Gastzugriffs in Microsoft 365 Gruppen](manage-guest-access-in-groups.md) (Artikel)

[Verwalten Microsoft 365 Gruppen mit PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md): In diesem Artikel werden Die wichtigsten Cmdlets und Beispiele (Artikel) erläutert.

[Microsoft 365 gruppenbenennungsrichtlinie](../../solutions/groups-naming-policy.md) (Artikel)