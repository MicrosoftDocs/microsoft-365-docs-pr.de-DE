---
title: Wiederherstellen einer gelöschten Office 365-Gruppe
ms.reviewer: arvaradh
f1.keywords:
- CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 'Hier erfahren Sie, wie Sie eine Office 365-Gruppe über das Exchange Admin Center wiederherstellen. '
ms.openlocfilehash: c88f10df27e5f3a0af79c93c7d0e347c5646abc9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352436"
---
# <a name="restore-a-deleted-office-365-group"></a>Wiederherstellen einer gelöschten Office 365-Gruppe

Wenn Sie der Besitzer einer Office 365-Gruppe sind, können Sie die Gruppe selbst wiederherstellen, indem Sie die folgenden Schritte ausführen.

1. Wählen Sie auf der Seite [Gelöschte Gruppen](https://outlook.office.com/people/group/deleted)die Option **Gruppen verwalten** unter dem Knoten **Gruppen** und dann **Gelöscht** aus.
2. Klicken Sie auf die Schaltfläche **Wiederherstellen** neben der Gruppe, die Sie wiederherstellen möchten.

Wenn die gelöschte Gruppe hier nicht angezeigt wird, wenden Sie sich an einen Administrator.
  
Wenn Sie ein Benutzer sind, der eine Office 365-Gruppe wiederherstellen möchte, bitten Sie einen Administrator, diese Schritte für Sie auszuführen, oder wenden Sie sich an Ihren Helpdesk.  
   
Wenn Sie eine Gruppe gelöscht haben, wird Sie standardmäßig 30 Tage lang aufbewahrt. Dieser 30-Tage-Zeitraum wird als Aufbewahrungsfrist für das vorläufige Löschen betrachtet, weil ein Wiederherstellen der Gruppe während dieses Zeitraums noch möglich ist. Nach 30 Tagen werden die Gruppe und die zugehörigen Inhalte endgültig gelöscht und können nicht wiederhergestellt werden.
  
Wenn ein Benutzer während der Aufbewahrungsfrist für das vorläufige Löschen versucht, auf die Website zuzugreifen, wird eine "404 _Verboten_"-Meldung angezeigt. Wenn ein Benutzer nach Ablauf dieses Zeitraums versucht, auf die Website zuzugreifen, wird eine "404 _Nicht gefunden_"-Meldung angezeigt.
  
Beim Wiederherstellen einer Gruppe werden folgende Inhalte wiederhergestellt:
  
- Objekte, Eigenschaften und Mitglieder von Office 365-Gruppen in Azure Active Directory (AD).
    
- E-Mail-Adressen von Gruppen.
    
- Der freigegebene Posteingang und Kalender in Exchange Online.
    
- Die SharePoint Online-Teamwebsite und die entsprechenden Dateien.
    
- OneNote-Notizbuch
    
- Planner
    
- Microsoft Teams

- Yammer-Gruppe und Gruppeninhalt (wenn die Office 365-Gruppe aus Yammer erstellt wurde)
    
Sie können eine [Endgültiges Löschen einer Office 365-Gruppe](#permanently-delete-an-office-365-group), wenn Sie nicht warten möchten, bis der Aufbewahrungszeitraum von 30 Tagen abläuft und der Inhalt dann endgültig gelöscht wird. 

> [!NOTE]
> Auch der Besitzer der gelöschten Office 365-Gruppe kann die Gruppe wiederherstellen. Informationen zum Wiederherstellen einer Office 365-Gruppe mit Besitzer- und ohne Administratorberechtigung finden Sie unter [Wiederherstellen einer Office 365-Gruppe mithilfe von PowerShell](#restore-an-office-365-group-using-powershell).

## <a name="restore-an-office-365-group-using-the-exchange-admin-center"></a>Wiederherstellen einer Office 365-Gruppe über das Exchange Admin Center

Sie benötigen globale Administratorberechtigungen für Office 365.

1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.
    
2. Wählen Sie im Exchange Admin Center die Optionen **Empfänger** und dann **Gruppen** aus. Sie können anzeigen, ob die Gruppe aktiv ist oder vorläufig gelöscht wurde. Wenn die Gruppe endgültig gelöscht wurde, wird sie definitiv nicht mehr aufgeführt.
  
3. Um die genaue Zeit anzuzeigen, zu der die Gruppe vorläufig gelöscht wurde, wählen Sie die Gruppe aus, und zeigen Sie die Informationen im rechten Bereich an.
      
4. Wählen Sie die Gruppe, die Sie wiederherstellen möchten, und dann das Symbol "Wiederherstellen" aus.
    
    ![Wählen Sie die Gruppe, die Sie wiederherstellen möchten, und dann das Symbol "Wiederherstellen" aus.](../../media/restore-group.png)
  
5. Wählen Sie "Aktualisieren" aus. ![Aktualisieren (Symbol)](../../media/6464df90-2a91-4c1f-92a6-9a38c7696ac3.gif) aus, um die Informationen auf der Seite zu aktualisieren. Ihre Gruppe wird als "Aktiv" angezeigt. Alle Formulare und Formulardaten, die mit Ihrer Gruppe verbunden sind, werden ebenfalls wiederhergestellt.
    
## <a name="restore-an-office-365-group-using-powershell"></a>Wiederherstellen einer Office 365-Gruppe mithilfe von PowerShell

Sie müssen über globale Administratorberechtigungen für Office 365 verfügen oder ein ehemaliger Besitzer der gelöschten Office 365-Gruppe sein.

> [!IMPORTANT]
> Wenn Sie in PowerShell zum Löschen einer Gruppe "Remove-MsolGroup" verwenden, wird die Gruppe endgültig gelöscht. Wenn Sie PowerShell zum Löschen von Gruppen verwenden, empfiehlt sich die Verwendung von **Remove-AzureADMSGroup**, um die Office 365-Gruppe vorläufig zu löschen. Auf diese Weise können Sie die Gruppe bei Bedarf wiederherstellen. 
  
### <a name="install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a>Installieren der Vorschauversion von Azure Active Directory PowerShell für Graph

> [!IMPORTANT]
> Sie können nicht gleichzeitig Preview- und GA-Version auf demselben Computer installieren.
  
Als bewährte Methode empfehlen wir, *immer* die neueste Version zu verwenden: Deinstallieren Sie also die alte AzureADPreview- bzw. AzureAD-Version, und holen Sie sich die aktuellste Version. 
  
 
1. Geben Sie in der Suchleiste "Windows PowerShell" ein.
    
2. Klicken Sie mit der rechten Maustaste auf **Windows PowerShell**, und klicken Sie dann auf **Als Administrator ausführen**.
  
2. Überprüfen Sie die installierten Module:
    
  ```
  Get-InstalledModule -Name "AzureAD*"
  ```

3. Führen Sie zum Deinstallieren einer früheren Version von AzureADPreview oder AzureAD diesen Befehl aus:
  
```
   Uninstall-Module AzureADPreview
```

oder
  
```
   Uninstall-Module AzureAD
```

4. Führen Sie zum Installieren der aktuellsten Version von AzureADPreview diesen Befehl aus:
  
```
   Install-Module AzureADPreview
```



Geben Sie in der Nachricht über ein nicht vertrauenswürdiges Repository **J** ein. Die Installation des neuen Moduls dauert etwa eine Minute.
  
### <a name="restore-the-deleted-group"></a>Wiederherstellen der gelöschten Gruppe
  
1. Haben Sie das **AzureADPreview**-Modul installiert, wie im vorstehenden Abschnitt "Installieren der Preview-Version des Azure Active Directory-Moduls für Windows PowerShell" beschrieben?  Das Fehlen der aktuellsten **Preview**-Version ist der Hauptgrund, warum diese Schritte nicht funktionieren. 
    
2. Falls noch nicht geschehen, öffnen Sie ein Windows PowerShell-Fenster auf dem Computer (es spielt keine Rolle, ob es sich um ein normales Windows PowerShell-Fenster handelt oder eines, das Sie durch Auswählen von **Als Administrator ausführen** geöffnet haben).
    
3. Führen Sie die folgenden Befehle aus. Drücken Sie dazu nach jedem Befehl die EINGABETASTE: 
    
  ```
  Import-Module AzureADPreview
  ```

  ```
  Connect-AzureAD
  ```



  Geben Sie auf dem angezeigten Bildschirm **Bei Ihrem Konto anmelden** den Benutzernamen und das Kennwort Ihres Administratorkontos ein, um eine Verbindung mit Ihrem Azure AD-Dienst herzustellen, und wählen Sie **Anmelden** aus.
  
4. Führen Sie den folgenden Befehl aus, um alle vorläufig gelöschten Office 365-Gruppen in Ihrer Organisation anzuzeigen, die noch innerhalb des Aufbewahrungszeitraums von 30 Tagen für das vorläufige Löschen liegen:
    
  ```
  Get-AzureADMSDeletedGroup
  ```

5. Notieren Sie sich die Objekt-ID der Gruppe(n), die Sie wiederherstellen möchten. Wenn die Gruppe, nach der Sie suchen, nicht in dieser Liste enthalten ist, wurde sie wahrscheinlich bereits endgültig gelöscht.
    
    > [!CAUTION]
    > Wenn eine neue Gruppe mit demselben Alias oder derselben SMTP-Adresse wie Ihre gelöschte Gruppe erstellt wurde, müssen Sie diese neue Gruppe löschen, um Ihre gelöschte Gruppe wiederherstellen zu können. 
  
6. Führen Sie zum Wiederherstellen dieser Gruppe den folgenden Befehl aus:
    
  ```
  Restore-AzureADMSDeletedDirectoryObject -Id <objectId>
  ```

7. Dieser Vorgang dauert in der Regel nur ein paar Minuten, in einigen seltenen Fällen kann die vollständige Wiederherstellung jedoch bis zu 24 Stunden dauern. Führen Sie in PowerShell den folgenden Befehl aus, um zu überprüfen, ob die Gruppe erfolgreich wiederhergestellt wurde:
    
  ```
  Get-AzureADGroup -ObjectId <objectId>
  ```

Sobald die Wiederherstellung erfolgreich abgeschlossen wurde, sollte die Gruppe wieder in Outlook und Outlook im Web im Navigationsbereich angezeigt werden. Alle wiederhergestellten Inhalte (einschließlich SharePoint und Planner) sollten den Mitgliedern der Gruppe wieder zur Verfügung stehen.
  
## <a name="permanently-delete-an-office-365-group"></a>Endgültiges Löschen einer Office 365-Gruppe

Manchmal möchten Sie vielleicht eine Gruppe endgültig löschen, ohne den Ablauf der 30-Tage-Frist für das vorläufige Löschen abzuwarten. Starten Sie hierzu PowerShell, und führen Sie den folgenden Befehl aus, um die Objekt-ID der Gruppe abzurufen:
  
```
Get-AzureADMSDeletedGroup
```

Notieren Sie sich die Objekt-ID der Gruppe(n), die Sie endgültig löschen möchten.
  
> [!CAUTION]
> Durch das endgültige Löschen der Gruppe werden die Gruppe und alle zugehörigen Daten für immer entfernt. 
  
Führen Sie in PowerShell den folgenden Befehl aus, um die Gruppe endgültig zu löschen:
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

Führen Sie zur Bestätigung, dass die Gruppe erfolgreich endgültig gelöscht wurde, das Cmdlet  *Get-AzureADMSDeletedGroup*  erneut aus, um sicherzustellen, dass die Gruppe nicht mehr in der Liste vorläufig gelöschter Gruppen angezeigt wird. In einigen Fällen kann es bis zu 24 Stunden dauern, bis die Gruppe und alle zugehörigen Daten endgültig gelöscht wurden. 
  
## <a name="got-questions-about-office-365-groups"></a>Haben Sie Fragen zu Office 365-Gruppen?

Besuchen Sie die [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups), um Fragen zu posten und an Unterhaltungen zu Office 365-Gruppen teilzunehmen. 
  
## <a name="related-articles"></a>Verwandte Artikel

[Verwalten von Office 365-Gruppen mit PowerShell](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[Löschen von Gruppen mit dem Cmdlet "Remove-UnifiedGroup"](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Verwalten Ihrer gruppenabhängigen Teamwebsiteeinstellungen](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[Löschen einer Gruppe in Outlook 2016](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
