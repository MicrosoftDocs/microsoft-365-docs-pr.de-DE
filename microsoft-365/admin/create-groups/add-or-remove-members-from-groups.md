---
title: Hinzufügen oder Entfernen von Mitgliedern aus Microsoft 365-Gruppen
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
description: Hier erfahren Sie, wie Sie einer Gruppe ein Mitglied hinzufügen, Mitglied aus der Gruppe entfernen und den Status von Gruppenbesitzern im Microsoft 365 Admin Center verwalten.
ms.openlocfilehash: 34c026bced5563e07a1ae0d13f4c691cfaf3f624
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663243"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>Hinzufügen oder Entfernen von Mitgliedern aus Microsoft 365-Gruppen mithilfe des Admin Centers

In Microsoft 365 erstellen Gruppenmitglieder in der Regel Ihre eigenen Gruppen, fügen sich selbst zu Gruppen hinzu, denen Sie beitreten möchten, oder werden von Gruppenbesitzern eingeladen. Wenn sich der Gruppenbesitz ändert oder Sie feststellen, dass ein Mitglied hinzugefügt oder entfernt werden soll, können Sie diese Änderung auch als Administrator vornehmen. Diese Änderungen können nur von einem globalen Administrator, einem Exchange-Administrator, einem Gruppenadministrator oder einem Benutzer Administrator vorgenommen werden. [Was ist eine Microsoft 365-Gruppe?](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> Wenn Sie kein Administrator sind, können Sie [Mitglieder mit Outlook hinzufügen oder entfernen](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de).
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>Hinzufügen eines Mitglieds zu einer Gruppe im Admin Center

1. Wechseln Sie im Admin Center zur Seite [**aktive Gruppen**](https://admin.microsoft.com/Adminportal/Home?#/groups) .  

2. Klicken Sie auf einen Gruppennamen.

3. Wählen Sie im Detailbereich auf der Registerkarte **Mitglieder** die Option **Alle anzeigen und Mitglieder verwalten** aus, und wählen Sie dann **Mitglieder hinzufügen** aus.

4. Suchen Sie nach dem Namen des Mitglieds, das hinzugefügt werden soll, oder wählen Sie ihn aus.

5. Wählen Sie **Speichern** aus.

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>Hinzufügen einer Gruppe zu einem Mitglied im Admin Center

1. Wechseln Sie im Admin Center zur Seite [**aktive Benutzer**](https://admin.microsoft.com/Adminportal/Home?#/users) .  

2. Klicken Sie auf einen Benutzer.

3. Wählen Sie im Detailbereich auf der Registerkarte **Konto** die Option **Gruppen verwalten** aus.

4. Suchen oder wählen Sie den Namen der Gruppe aus, die Sie hinzufügen möchten.

5. Wählen Sie **Speichern** aus.

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>Entfernen eines Mitglieds aus einer Gruppe im Admin Center

> [!NOTE]
> Wenn Sie ein Mitglied aus einer privaten Gruppe entfernen, dauert es 5 Minuten, bis die Person von der Gruppe blockiert wird.

1. Wechseln Sie im Admin Center zur Seite [**aktive Gruppen**](https://admin.microsoft.com/Adminportal/Home?#/groups) .  

2. Klicken Sie auf einen Gruppennamen.

3. Wählen Sie im Detailbereich auf der Registerkarte **Mitglieder** die Option **Alle anzeigen und Mitglieder verwalten** aus.

4. Wählen Sie neben dem Mitglied, das Sie entfernen möchten, das X aus.

5. Wählen Sie **Speichern** aus, um das Element zu entfernen.

## <a name="manage-group-owner-status"></a>Verwalten des Status von Gruppenbesitzern

Die Person, die eine Gruppe erstellt hat, ist standardmäßig der Gruppenbesitzer. Häufig hat eine Gruppe als Sicherungsunterstützung oder aus anderen Gründen mehrere Besitzer. Mitglieder können in den Status eines Besitzers hochgestuft und Besitzer können in den Status eines Mitglieds heruntergestuft werden.
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>Heraufstufen eines Mitglieds in den Besitzer Status im Admin Center

1. Wechseln Sie im Admin Center zur Seite [**aktive Gruppen**](https://admin.microsoft.com/Adminportal/Home?#/groups) .  

2. Klicken Sie auf einen Gruppennamen.

3. Wählen Sie im Detailbereich auf der Registerkarte **Mitglieder** die Option **Alle anzeigen und Besitzer verwalten** aus.

4. Wählen Sie **Besitzer hinzufügen** aus.

5. Aktivieren Sie das Kontrollkästchen neben dem Namen des Mitglieds, das Sie hinzufügen möchten.

6. Klicken Sie auf **Speichern** und dann auf **Schließen**.

### <a name="remove-owner-status-in-the-admin-center"></a>Entfernen des Besitzer Status im Admin Center

1. Wechseln Sie im Admin Center zur Seite [**aktive Gruppen**](https://admin.microsoft.com/Adminportal/Home?#/groups) .  

2. Klicken Sie auf einen Gruppennamen.

3. Wählen Sie im Detailbereich auf der Registerkarte **Mitglieder** die Option **Alle anzeigen und Besitzer verwalten** aus.

4. Wählen Sie neben dem Namen des Besitzers das X aus.

5. Wählen Sie **Speichern** aus.

## <a name="more-on-managing-membership"></a>###Weitere Informationen zum Verwalten der Mitgliedschaft

- [Dynamisches Verwalten von Gruppen in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=847632): Lesen Sie den Abschnitt "Wie kann ich die Mitgliedschaft in einer Gruppe dynamisch verwalten?"

- Um Hunderte oder Tausende von Benutzern zu Gruppen hinzuzufügen, verwenden [Sie das Add-UnifiedGroupLinks](https://docs.microsoft.com/powershell/module/exchange/add-unifiedgrouplinks).

- [Zuweisen eines neuen Besitzers zu einer verwaisten Gruppe](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="articles-about-managing-groups"></a>Artikel zum Verwalten von Gruppen

- [Aktualisieren von Verteilerlisten auf Microsoft 365-Gruppen in Outlook](../manage/upgrade-distribution-lists.md)

- [Warum Sie Ihre Verteilerlisten für Gruppen in Outlook aktualisieren sollten](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

- [Verwalten des Gastzugriffs in Microsoft 365-Gruppen](manage-guest-access-in-groups.md)

- [Verwalten von Microsoft 365-Gruppen mit PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell): in diesem Artikel werden wichtige Cmdlets vorgestellt und Beispiele bereitgestellt.

- [Microsoft 365 gruppenbenennungsrichtlinie](groups-naming-policy.md)
