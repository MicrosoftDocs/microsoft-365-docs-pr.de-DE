---
title: Verwalten einer Gruppe im Admin Center
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 74a1ef8b-3844-4d08-9980-9f8f7a36000f
description: Informationen zum Verwalten Microsoft 365 Gruppen, einschließlich hinzufügen von Entfernen von Gruppenmitgliedern, Bearbeiten der E-Mail-Adresse, des Gruppennamens oder der Beschreibung und Anpassen der Funktionsweise der Gruppe.
ms.openlocfilehash: 3ba3dd36ed3929e956ce6359e678d6b684f64bb9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908710"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Verwalten einer Gruppe im Microsoft 365 Admin Center

Nachdem Sie [eine gruppe Microsoft 365 und](create-groups.md) hinzugefügte Gruppenmitglieder erstellt haben, können Sie Ihre Gruppe konfigurieren. Sie können den Gruppennamen oder die Beschreibung bearbeiten, Besitzer oder Mitglieder verwalten und angeben, ob externe Absender die Gruppe per E-Mail senden können und ob Kopien von Gruppenunterhaltungen an Mitglieder gesendet werden sollen.

Wechseln Sie zum Microsoft 365 Admin Center unter [https://admin.microsoft.com](https://admin.microsoft.com) .

## <a name="edit-the-group-name-or-description"></a>Bearbeiten des Gruppennamens oder der Beschreibung

1. Erweitern Sie im Admin Center **gruppen**, und klicken Sie dann auf **Gruppen**.

2. Wählen Sie die Gruppe aus, die Sie bearbeiten möchten, und klicken Sie dann **auf Name und Beschreibung bearbeiten.**

3. Aktualisieren Sie den Namen und die Beschreibung, und wählen Sie dann **Speichern aus.**

## <a name="manage-group-owners-and-members"></a>Verwalten von Gruppenbesitzern und -mitgliedern

1. Erweitern Sie im Admin Center **gruppen**, und klicken Sie dann auf **Gruppen**.

2. Klicken Sie auf den Namen der Gruppe, die Sie verwalten möchten, um den Einstellungsbereich zu öffnen.

3. Wählen Sie **auf** der Registerkarte Mitglieder aus, ob Sie Besitzer oder Mitglieder verwalten möchten.

4. Wählen **Sie Hinzufügen** aus, um eine Person hinzuzufügen, oder klicken Sie auf **X,** um eine Person zu entfernen.

5. Klicken Sie auf **Schließen**.

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>Senden von Kopien von Unterhaltungen an die Posteingange von Gruppenmitgliedern
  
Wenn Sie das Admin Center zum Erstellen einer Gruppe verwenden, erhalten Benutzer standardmäßig keine Kopien von Gruppen-E-Mails und Besprechungseinladungen, die an ihre Posteingange gesendet werden. Sie müssen zur Gruppe wechseln, um Unterhaltungen und Besprechungen zu sehen. Sie können diese Einstellung im Admin Center ändern.

Wenn Sie diese Einstellung aktivieren, erhalten Gruppenmitglieder eine Kopie von Gruppen-E-Mails und Besprechungseinladungen, die an ihren Posteingang Outlook werden. Jedes Gruppenmitglied kann seine Kopie der E-Mail lesen und löschen, ohne dass sich dies auf andere Gruppenmitglieder auswirkt. Im Posteingang der Gruppe bleibt eine Kopie der E-Mail weiterhin erhalten.

Gruppenmitglieder können den Empfang dieser E-Mails abmelden, indem sie die Gruppe in Outlook.

1. Erweitern Sie im Admin Center **gruppen**, und klicken Sie dann auf **Gruppen**.

2. Klicken Sie auf den Namen der Gruppe, die Sie verwalten möchten, um den Einstellungsbereich zu öffnen.

3. Wählen Sie **Einstellungen** Registerkarte Senden  von Kopien von Gruppenunterhaltungen und -ereignissen an Gruppenmitglieder aus, wenn Mitglieder Kopien von Gruppennachrichten und Kalenderelementen in ihrem eigenen Posteingang erhalten sollen.

4. Klicken Sie auf **Speichern**.

## <a name="let-people-outside-the-organization-email-the-group"></a>Personen außerhalb der Organisation eine E-Mail an die Gruppe senden lassen

Diese Option ist ideal, wenn Sie eine Unternehmens-E-Mail-Adresse wie info@contoso.com.
 
1. Erweitern Sie im Admin Center **gruppen**, und klicken Sie dann auf **Gruppen**.

2. Klicken Sie auf den Namen der Gruppe, die Sie verwalten möchten, um den Einstellungsbereich zu öffnen.

3. Wählen Sie in der Liste Admin Center-Gruppen den Namen der Gruppe aus, die Sie ändern möchten, und wählen Sie dann auf der Registerkarte Einstellungen die Option Externe Absender zum Senden einer E-Mail **an** diese Gruppe **zulassen aus.**
    
4. Klicken Sie auf **Speichern**.

## <a name="permanently-delete-a-microsoft-365-group"></a>Endgültiges Löschen einer Microsoft 365 Gruppe

Manchmal möchten Sie vielleicht eine Gruppe endgültig löschen, ohne den Ablauf der 30-Tage-Frist für das vorläufige Löschen abzuwarten. Starten Sie hierzu PowerShell, und führen Sie den folgenden Befehl aus, um die Objekt-ID der Gruppe abzurufen:
 
 ```powershell
`Get-AzureADMSDeletedGroup`
```

Notieren Sie sich die Objekt-ID der Gruppe(n), die Sie endgültig löschen möchten.
  
> [!CAUTION]
> Durch das endgültige Löschen der Gruppe werden die Gruppe und alle zugehörigen Daten für immer entfernt. 
  
Führen Sie in PowerShell den folgenden Befehl aus, um die Gruppe endgültig zu löschen:

```powershell
`Remove-AzureADMSDeletedDirectoryObject -Id <objectId>`
```

Führen Sie zur Bestätigung, dass die Gruppe erfolgreich endgültig gelöscht wurde, das Cmdlet  *Get-AzureADMSDeletedGroup*  erneut aus, um sicherzustellen, dass die Gruppe nicht mehr in der Liste vorläufig gelöschter Gruppen angezeigt wird. In einigen Fällen kann es bis zu 24 Stunden dauern, bis die Gruppe und alle zugehörigen Daten endgültig gelöscht wurden. 
  
## <a name="related-articles"></a>Verwandte Artikel

[Erstellen einer Microsoft 365 Gruppe](create-groups.md)

[Verwalten des Gastzugriffs auf Microsoft 365-Gruppen](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Wählen Sie die Domäne aus, die beim Erstellen Microsoft 365 werden soll](../../solutions/choose-domain-to-create-groups.md)

[Zulassen, dass Mitglieder im Namen einer Gruppe als oder Microsoft 365 senden](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[Aktualisieren von Verteilerlisten auf Microsoft 365 Gruppen](../manage/upgrade-distribution-lists.md)

[Verwalten Microsoft 365 Gruppen mit PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md)