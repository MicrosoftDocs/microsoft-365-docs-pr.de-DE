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
description: Erfahren Sie, wie Sie Microsoft 365 Gruppen verwalten, z. B. Gruppenmitglieder entfernen, die E-Mail-Adresse, den Gruppennamen oder die Beschreibung bearbeiten und die Funktionsweise der Gruppe anpassen.
ms.openlocfilehash: 2ec8198b7e28b47bcbbf40818fbe624b2744f0ee
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454577"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Verwalten einer Gruppe im Microsoft 365 Admin Center

Nachdem Sie [eine Microsoft 365 Gruppe erstellt](create-groups.md) und Gruppenmitglieder hinzugefügt haben, können Sie Ihre Gruppe konfigurieren. Sie können den Gruppennamen oder die Beschreibung bearbeiten, Besitzer oder Mitglieder verwalten und angeben, ob externe Absender eine E-Mail an die Gruppe senden können und ob Kopien von Gruppenunterhaltungen an Mitglieder gesendet werden sollen.

Wechseln Sie zu der Microsoft 365 Admin Center unter [https://admin.microsoft.com](https://admin.microsoft.com) .

## <a name="edit-the-group-name-or-description"></a>Bearbeiten des Gruppennamens oder der Beschreibung

1. Erweitern Sie im Admin Center **Gruppen,** und klicken Sie dann auf **"Gruppen".**

2. Wählen Sie die Gruppe aus, die Sie bearbeiten möchten, und klicken Sie dann auf **"Namen und Beschreibung bearbeiten".**

3. Aktualisieren Sie den Namen und die Beschreibung, und wählen Sie dann **"Speichern"** aus.

## <a name="manage-group-owners-and-members"></a>Verwalten von Gruppenbesitzern und -mitgliedern

1. Erweitern Sie im Admin Center **Gruppen,** und klicken Sie dann auf **"Gruppen".**

2. Klicken Sie auf den Namen der Gruppe, die Sie verwalten möchten, um den Einstellungsbereich zu öffnen.

3. Wählen Sie auf der Registerkarte **"Mitglieder"** aus, ob Sie Besitzer oder Mitglieder verwalten möchten.

4. Wählen Sie **"Hinzufügen"** aus, um eine Person hinzuzufügen, oder klicken Sie auf **"X",** um jemanden zu entfernen.

5. Klicken Sie auf **Schließen**.

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>Senden von Kopien von Unterhaltungen an die Postfächer von Gruppenmitgliedern
  
Wenn Sie das Admin Center zum Erstellen einer Gruppe verwenden, erhalten Benutzer standardmäßig keine Kopien von Gruppen-E-Mails, die an ihre Postfächer gesendet werden, obwohl Benutzer Kopien von Gruppenbesprechungseinladungen erhalten, die an ihre Postfächer gesendet werden. Sie müssen zu der Gruppe wechseln, um Unterhaltungen anzuzeigen. Sie können diese Einstellung im Admin Center ändern.

Wenn Sie diese Einstellung aktivieren, erhalten Gruppenmitglieder eine Kopie von Gruppen-E-Mails und Besprechungseinladungen, die an ihre Outlook Posteingang gesendet werden. Jedes Gruppenmitglied kann seine Kopie der E-Mail lesen und löschen, ohne dass sich dies auf andere Gruppenmitglieder auswirkt. Im Posteingang der Gruppe bleibt eine Kopie der E-Mail weiterhin erhalten.

Gruppenmitglieder können den Empfang dieser E-Mails deaktivieren, indem sie sich entscheiden, der Gruppe in Outlook nicht mehr zu folgen.

1. Erweitern Sie im Admin Center **Gruppen,** und klicken Sie dann auf **"Gruppen".**

2. Klicken Sie auf den Namen der Gruppe, die Sie verwalten möchten, um den Einstellungsbereich zu öffnen.

3. Wählen Sie auf der Registerkarte **Einstellungen** **Kopien von Gruppenunterhaltungen und -ereignissen an Gruppenmitglieder senden** aus, wenn Mitglieder Kopien von Gruppennachrichten und Kalenderelementen in ihrem eigenen Posteingang empfangen sollen.

4. Wählen Sie **Speichern** aus.

## <a name="let-people-outside-the-organization-email-the-group"></a>Personen außerhalb der Organisation eine E-Mail an die Gruppe senden lassen

Diese Option eignet sich hervorragend, wenn Sie eine Unternehmens-E-Mail-Adresse wie info@contoso.com haben möchten.
 
1. Erweitern Sie im Admin Center **Gruppen,** und klicken Sie dann auf **"Gruppen".**

2. Klicken Sie auf den Namen der Gruppe, die Sie verwalten möchten, um den Einstellungsbereich zu öffnen.

3. Wählen Sie in der Admin Center-Gruppenliste den Namen der Gruppe aus, die Sie ändern möchten, und wählen Sie dann auf der Registerkarte **Einstellungen** die Option **"Externe Absender dürfen diese Gruppe per E-Mail** senden" aus.
    
4. Wählen Sie **Speichern** aus.

## <a name="permanently-delete-a-microsoft-365-group"></a>Dauerhaftes Löschen einer Microsoft 365 Gruppe

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

[Auswählen der Domäne, die beim Erstellen Microsoft 365 Gruppen verwendet werden soll](../../solutions/choose-domain-to-create-groups.md)

[Mitgliedern das Senden als oder senden im Namen einer Microsoft 365 Gruppe gestatten](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[Aktualisieren von Verteilerlisten auf Microsoft 365 Gruppen](../manage/upgrade-distribution-lists.md)

[Verwalten Microsoft 365 Gruppen mit PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
