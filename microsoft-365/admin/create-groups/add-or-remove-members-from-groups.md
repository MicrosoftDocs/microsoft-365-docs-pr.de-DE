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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: Erfahren Sie, wie Sie ein Mitglied zu einer Gruppe hinzufügen, ein Mitglied aus einer Gruppe entfernen und den Gruppenbesitzerstatus im Microsoft 365 Admin Center verwalten.
ms.openlocfilehash: 7eaa74a53ac5f27d801d1cf16c9af035c63c68b1
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393763"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>Hinzufügen oder Entfernen von Mitgliedern aus Microsoft 365 Gruppen mithilfe des Admin Centers

In Microsoft 365 erstellen Gruppenmitglieder in der Regel eigene Gruppen, fügen sich selbst Gruppen hinzu, denen sie beitreten möchten, oder werden von Gruppenbesitzern eingeladen. Wenn sich der Gruppenbesitz ändert oder Wenn Sie festlegen, dass ein Mitglied hinzugefügt oder entfernt werden soll, können Sie diese Änderung auch als Administrator vornehmen. Nur ein globaler Administrator, Exchange Administrator, Gruppenadministrator oder Benutzeradministrator kann diese Änderungen vornehmen. [Was ist eine Microsoft 365 Gruppe?](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> Wenn Sie kein Administrator sind, können Sie [Mitglieder mit Outlook hinzufügen oder entfernen.](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de)
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>Hinzufügen eines Mitglieds zu einer Gruppe im Admin Center

1. Wechseln Sie im Admin Center zur Seite [**"Aktive Gruppen".**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Klicken Sie auf einen Gruppennamen.

3. Wählen Sie im Detailbereich auf der Registerkarte **"Mitglieder"** die Option **"Alle anzeigen" und "Mitglieder verwalten"** aus, und wählen Sie dann **"Mitglieder hinzufügen"** aus.

4. Suchen Sie nach dem Namen des Mitglieds, das hinzugefügt werden soll, oder wählen Sie ihn aus.

5. Klicken Sie auf **Speichern**.

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>Hinzufügen einer Gruppe zu einem Mitglied im Admin Center

1. Wechseln Sie im Admin Center zur Seite [**"Aktive Benutzer".**](https://admin.microsoft.com/Adminportal/Home?#/users)  

2. Klicken Sie auf einen Benutzer.

3. Wählen Sie im Detailbereich auf der Registerkarte **"Konto"** die Option **"Gruppen verwalten"** aus.

4. Suchen Oder wählen Sie den Namen der Gruppe aus, die Sie hinzufügen möchten.

5. Klicken Sie auf **Speichern**.

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>Entfernen eines Mitglieds aus einer Gruppe im Admin Center

> [!NOTE]
> Wenn Sie ein Mitglied aus einer privaten Gruppe entfernen, dauert es 5 Minuten, bis die Person aus der Gruppe blockiert wird.

1. Wechseln Sie im Admin Center zur Seite [**"Aktive Gruppen".**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Klicken Sie auf einen Gruppennamen.

3. Wählen Sie im Detailbereich auf der Registerkarte **"Mitglieder"** die Option **"Alle anzeigen" und "Mitglieder verwalten"** aus.

4. Wählen Sie neben dem Element, das Sie entfernen möchten, das X aus.

5. Wählen Sie **"Speichern"** aus, um das Mitglied zu entfernen.

## <a name="manage-group-owner-status"></a>Verwalten des Gruppenbesitzerstatus

Die Person, die eine Gruppe erstellt hat, ist standardmäßig der Gruppenbesitzer. Häufig hat eine Gruppe als Sicherungsunterstützung oder aus anderen Gründen mehrere Besitzer. Mitglieder können in den Status eines Besitzers hochgestuft und Besitzer können in den Status eines Mitglieds heruntergestuft werden.
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>Höherstufen eines Mitglieds zum Besitzerstatus im Admin Center

1. Wechseln Sie im Admin Center zur Seite [**"Aktive Gruppen".**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Klicken Sie auf einen Gruppennamen.

3. Wählen Sie im Detailbereich auf der Registerkarte **"Mitglieder"** die Option **"Alle anzeigen" und "Besitzer verwalten"** aus.

4. Wählen Sie **Besitzer hinzufügen aus.**

5. Aktivieren Sie das Kontrollkästchen neben dem Namen des Mitglieds, das Sie hinzufügen möchten.

6. Wählen Sie **"Speichern"** und dann **"Schließen"** aus.

### <a name="remove-owner-status-in-the-admin-center"></a>Entfernen des Besitzerstatus im Admin Center

1. Wechseln Sie im Admin Center zur Seite [**"Aktive Gruppen".**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Klicken Sie auf einen Gruppennamen.

3. Wählen Sie im Detailbereich auf der Registerkarte **"Mitglieder"** die Option **"Alle anzeigen" und "Besitzer verwalten"** aus.

4. Wählen Sie das X neben dem Namen des Besitzers aus.

5. Wählen Sie **Speichern** aus.

## <a name="next-steps"></a>Nächste Schritte

- [Dynamisches Verwalten von Gruppen in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal): Lesen Sie den Abschnitt "Wie kann ich die Mitgliedschaft in einer Gruppe dynamisch verwalten?"

- Zum Hinzufügen von Hunderten oder Tausenden von Benutzern zu Gruppen verwenden Sie die [Add-UnifiedGroupLinks](/powershell/module/exchange/add-unifiedgrouplinks).

- [Zuweisen eines neuen Besitzers zu einer verwaisten Gruppe](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="related-content"></a>Verwandte Inhalte

[Aktualisieren von Verteilerlisten auf Microsoft 365 Gruppen in Outlook](../manage/upgrade-distribution-lists.md) (Artikel)\
[Warum Sie Ihre Verteilerlisten auf Gruppen in Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188) (Artikel)\ aktualisieren sollten
[Verwalten des Gastzugriffs in Microsoft 365 Gruppen](manage-guest-access-in-groups.md) (Artikel)\
[Verwalten Microsoft 365 Gruppen mit PowerShell:](../../enterprise/manage-microsoft-365-groups-with-powershell.md)In diesem Artikel werden wichtige Cmdlets vorgestellt und Beispiele (Artikel)\
[Microsoft 365 Benennungsrichtlinie](../../solutions/groups-naming-policy.md) für Gruppen (Artikel)