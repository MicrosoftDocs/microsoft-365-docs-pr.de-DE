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
description: Erfahren Sie mehr über das Verwalten von Microsoft 365-Gruppen, einschließlich Hinzufügen von Gruppenmitgliedern, Bearbeiten der e-Mail-Adresse, des Gruppennamens oder der Beschreibung und Anpassen der Funktionsweise der Gruppe.
ms.openlocfilehash: 8216b80ba6cd6bffe470f4fe4ace43307afba5f2
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753301"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Verwalten einer Gruppe im Microsoft 365 Admin Center

Nachdem Sie [eine Microsoft 365-Gruppe erstellt](create-groups.md) und Gruppenmitglieder hinzugefügt haben, können Sie Ihre Gruppe konfigurieren. Sie können den Gruppennamen oder die Beschreibung bearbeiten, Besitzer oder Mitglieder verwalten und angeben, ob externe Absender die Gruppe per e-Mail senden können und ob Kopien von Gruppenunterhaltungen an Mitglieder gesendet werden sollen.

Wechseln Sie zum Microsoft 365 Admin Center unter [https://admin.microsoft.com](https://admin.microsoft.com) .

## <a name="edit-the-group-name-or-description"></a>Bearbeiten des Gruppennamens oder der Beschreibung

1. Erweitern Sie im Admin Center den Knoten **Gruppen**, und klicken Sie dann auf **Gruppen**.

2. Wählen Sie die Gruppe aus, die Sie bearbeiten möchten, und klicken Sie dann auf **Name und Beschreibung bearbeiten**.

3. Aktualisieren Sie den Namen und die Beschreibung, und wählen Sie dann **Speichern**aus.

## <a name="manage-group-owners-and-members"></a>Verwalten von Gruppenbesitzern und-Mitgliedern

1. Erweitern Sie im Admin Center den Knoten **Gruppen**, und klicken Sie dann auf **Gruppen**.

2. Klicken Sie auf den Namen der Gruppe, die Sie verwalten möchten, um den Bereich Einstellungen zu öffnen.

3. Wählen Sie auf der Registerkarte **Mitglieder** aus, ob Sie Besitzer oder Mitglieder verwalten möchten.

4. Klicken Sie auf **Hinzufügen** , um jemanden hinzuzufügen oder auf **X** , um jemanden zu entfernen.

5. Klicken Sie auf **Schließen**.

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>Senden von Kopien von Unterhaltungen an die Posteingänge der Gruppenmitglieder
  
Wenn Sie das Admin Center zum Erstellen einer Gruppe verwenden, erhalten Benutzer standardmäßig keine Kopien von Gruppen-e-Mails und Besprechungseinladungen, die an ihre Posteingänge gesendet werden. Sie müssen zur Gruppe wechseln, um Unterhaltungen und Besprechungen anzuzeigen. Sie können diese Einstellung im Admin Center ändern.

Wenn Sie diese Einstellung aktivieren, erhalten Gruppenmitglieder eine Kopie der Gruppen-e-Mails und Besprechungseinladungen, die an Ihren Outlook-Posteingang gesendet werden. Jedes Gruppenmitglied kann seine Kopie der E-Mail lesen und löschen, ohne dass sich dies auf andere Gruppenmitglieder auswirkt. Im Posteingang der Gruppe bleibt eine Kopie der E-Mail weiterhin erhalten.

Gruppenmitglieder können diesen e-Mail-Empfang nicht mehr erhalten, indem Sie das Folgen der Gruppe in Outlook beenden.

1. Erweitern Sie im Admin Center den Knoten **Gruppen**, und klicken Sie dann auf **Gruppen**.

2. Klicken Sie auf den Namen der Gruppe, die Sie verwalten möchten, um den Bereich Einstellungen zu öffnen.

3. Wählen Sie auf der Registerkarte **Einstellungen** die Option **Kopien von Gruppenunterhaltungen und Ereignissen an Gruppenmitglieder senden** aus, wenn Sie möchten, dass Mitglieder Kopien von Gruppen Nachrichten und Kalenderelementen in Ihrem eigenen Posteingang erhalten.

4. Klicken Sie auf **Speichern**.

## <a name="let-people-outside-the-organization-email-the-group"></a>Zulassen, dass Personen außerhalb der Organisation e-Mail an die Gruppe senden

Diese Option eignet sich hervorragend, wenn Sie eine Firmen-e-Mail-Adresse wie Info@contoso.com haben möchten.
 
1. Erweitern Sie im Admin Center den Knoten **Gruppen**, und klicken Sie dann auf **Gruppen**.

2. Klicken Sie auf den Namen der Gruppe, die Sie verwalten möchten, um den Bereich Einstellungen zu öffnen.

3. Wählen Sie in der Liste Admin Center-Gruppen den Namen der Gruppe aus, die Sie ändern möchten, und wählen Sie dann auf der Registerkarte **Einstellungen** die Option **externe Absender können diese Gruppe per e-Mail zulassen**aus.
    
4. Klicken Sie auf **Speichern**.

## <a name="permanently-delete-a-microsoft-365-group"></a>Dauerhaftes Löschen einer Microsoft 365-Gruppe

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

[Erstellen einer Microsoft 365-Gruppe](create-groups.md)

[Verwalten des Gastzugriffs auf Microsoft 365-Gruppen](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Wählen Sie die Domäne aus, die beim Erstellen von Microsoft 365-Gruppen verwendet werden soll.](../../solutions/choose-domain-to-create-groups.md)

[Zulassen, dass Mitglieder im Auftrag einer Microsoft 365-Gruppe senden als oder senden](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[Aktualisieren von Verteilerlisten auf Microsoft 365-Gruppen](../manage/upgrade-distribution-lists.md)

[Verwalten von Microsoft 365-Gruppen mit PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
