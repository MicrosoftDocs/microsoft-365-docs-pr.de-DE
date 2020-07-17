---
title: Erstellen, bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
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
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Hier erfahren Sie, wie Sie eine Sicherheitsgruppe erstellen, bearbeiten oder löschen.
ms.openlocfilehash: c7c8d57037d972cd89dad45358dc5a7aa3fb86e8
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780241"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a>Erstellen, bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Auf der Seite Microsoft 365 **Gruppen** können Sie Gruppen von Benutzerkonten erstellen, die Sie verwenden können, um in SharePoint Online und CRM Online dieselben Berechtigungen zuzuweisen. Beispielsweise kann ein Administrator eine Sicherheitsgruppe erstellen, um einer bestimmten Gruppe von Personen Zugriff auf eine SharePoint-Website zu gewähren. Nur globale Administratoren und Benutzer Verwaltungsdienste verfügen über Berechtigungen zum Erstellen, bearbeiten oder Löschen von Sicherheitsgruppen. Weitere Informationen zu Administratorrollen finden Sie unter [zuweisen](../add-users/assign-admin-roles.md)von Administratorrollen. 
  
Darüber hinaus gibt es [Gruppen in Exchange Online und SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), mit denen Sie an eine Benutzergruppe E-Mails senden oder der Gruppe Berechtigungen zuweisen können, und [Gruppen in Exchange Online und SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), mit denen Benutzern Rechte zugewiesen sowie der Zugriff auf Websites und Websitesammlungen gewährt werden kann. 
  
> [!IMPORTANT]
>  Planen der Verwendung von Website Postfächern Alle Benutzer, die über eine Sicherheitsgruppe zu einer SharePoint-Website hinzugefügt werden, anstatt einzeln hinzugefügt zu werden, können nur das websitepostfach von SharePoint verwenden. Diese Benutzer können nicht über Outlook auf das websitepostfach zugreifen. Weitere Informationen finden Sie unter [Verwenden von Microsoft 365-Gruppen anstelle von Website Postfächern](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b). 
  
## <a name="manage-security-groups-in-the-admin-center"></a>Verwalten von Sicherheitsgruppen im Admin Center

### <a name="add-a-security-group"></a>Hinzufügen einer Sicherheitsgruppe

1. Wechseln Sie im Microsoft 365 Admin Center zur Seite **Gruppen**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a> .
  
2. Wählen Sie auf der Seite **Gruppen** die Option **Gruppe hinzufügen**aus.
    
3. Wählen Sie auf der Seite **Gruppentyp auswählen** die Option **Sicherheit**aus. 
    
4. Führen Sie die Schritte zum Abschließen der Erstellung der Gruppe aus. 
 
### <a name="add-members-to-a-security-group"></a>Hinzufügen von Mitgliedern zu einer Sicherheitsgruppe

::: moniker range="o365-worldwide"
    
1. Wählen Sie auf der Seite **Gruppen** den Namen der Sicherheitsgruppe aus, und wählen Sie auf der Registerkarte **Mitglieder** die Option **Alle anzeigen und Mitglieder verwalten**aus. 
    
2. Wählen Sie im Bereich Gruppe die Option **Mitglieder hinzufügen** aus, wählen Sie die Person aus der Liste aus, oder geben Sie den Namen der Person ein, die Sie im **Suchfeld** hinzufügen möchten, und wählen Sie dann **Speichern**aus.
    
    Um Mitglieder zu entfernen, wählen Sie das X neben Ihrem Namen aus. 
  
::: moniker-end

::: moniker range="o365-germany"

1. Wählen Sie auf der Seite **Gruppen** den Namen der Sicherheitsgruppe aus, und wählen Sie dann neben **Mitglieder** **Bearbeiten** aus. 
    
2. Wählen Sie im Bereich Gruppe die Option **Mitglieder hinzufügen** aus, wählen Sie die Person aus der Liste aus, oder geben Sie den Namen der Person ein, die Sie im **Suchfeld** hinzufügen möchten, und wählen Sie dann **Speichern**aus.
    
    Um Mitglieder zu entfernen, wählen Sie das X neben Ihrem Namen aus. 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. Wählen Sie auf der Seite **Gruppen** den Namen der Sicherheitsgruppe aus, und wählen Sie dann neben **Mitglieder** **Bearbeiten** aus. 
    
2. Wählen Sie im Bereich Gruppe die Option **Mitglieder hinzufügen** aus, wählen Sie die Person aus der Liste aus, oder geben Sie den Namen der Person ein, die Sie im **Suchfeld** hinzufügen möchten, und wählen Sie dann **Speichern**aus.
    
    Um Mitglieder zu entfernen, wählen Sie das X neben Ihrem Namen aus.

::: moniker-end

### <a name="edit-a-security-group"></a>Bearbeiten einer Sicherheitsgruppe

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.
  
2. Wählen Sie auf der Seite **Gruppen** den Namen der Gruppe aus. 
    
3. Wählen Sie im Bereich "Einstellungen" die Registerkarte " **Allgemein** " oder " **Mitglieder** " aus, um Gruppendetails oder Mitglieder zu bearbeiten.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** \> **Gruppen**.  
  
2. Wählen Sie auf der Seite **Gruppen** den Namen der Gruppe aus. 
    
3. Wählen Sie im Bereich Sicherheitsgruppe neben **Name** oder **Mitglieder** Registerkarte **Bearbeiten** aus, um Gruppendetails oder Mitglieder zu bearbeiten.
    
4. Nachdem Sie Änderungen vorgenommen haben, wählen Sie **Save** \> **Close**aus.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** \> **Gruppen**.
  
2. Wählen Sie auf der Seite **Gruppen** den Namen der Gruppe aus. 
    
3. Wählen Sie im Bereich Sicherheitsgruppe neben **Name** oder **Mitglieder** Registerkarte **Bearbeiten** aus, um Gruppendetails oder Mitglieder zu bearbeiten.
    
4. Nachdem Sie Änderungen vorgenommen haben, wählen Sie **Save** > **Close**aus.

::: moniker-end


### <a name="delete-a-security-group"></a>Löschen einer Sicherheitsgruppe

1. Wechseln Sie im Admin Center zur Seite **Gruppen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.
    
2. Wählen Sie auf der Seite **Gruppen** den Namen der Gruppe aus. 
    
3. Wählen Sie **Gruppe löschen** (wasetbin-Symbol) aus, und bestätigen Sie, indem Sie **Löschen**auswählen.
    
    Wählen Sie **Schließen** , nachdem die Gruppe gelöscht wurde. 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a>Gruppen in Exchange Online und SharePoint Online

Wenn Sie Benutzergruppen erstellen möchten, damit Sie e-Mails an alle gleichzeitig senden können, können Sie dies im Exchange Admin Center tun, indem Sie zu **Administrator** - \> **Exchange** - \> **Empfänger** \> **Gruppen**wechseln. Wählen Sie dann **neu** ![ hinzufügen aus ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) , und wählen Sie die Art der Gruppe aus, die Sie erstellen möchten: 
  
- **Verteilergruppe**: Wird verwendet, um Nachrichten an eine Benutzergruppe zu senden. Sie wird auch als *e-Mail-aktivierte Verteilergruppe*oder eine *Verteilerliste*bezeichnet. Weitere Informationen finden Sie unter [Verwalten von Verteilergruppen](https://technet.microsoft.com/library/bb124513.aspx).
    
- **Sicherheitsgruppe**: Kann verwendet werden, um Nachrichten an eine Benutzergruppe zu senden oder um Berechtigungen zum Zugriff auf Ressourcen zu gewähren. Diese Gruppe wird auch als *e-Mail-aktivierte Sicherheitsgruppe*bezeichnet. Weitere Informationen finden Sie unter [Verwalten von E-Mail-aktivierten Sicherheitsgruppen](https://technet.microsoft.com/library/bb123521.aspx).
    
- **Dynamische Verteilergruppe**: Eine Art von Verteilergruppe, bei der die Empfängerliste jedes Mal, wenn Sie eine Nachricht senden, basierend auf von Ihnen definierten Filtern und Bedingungen neu berechnet wird. Weitere Informationen finden Sie unter [Verwalten dynamischer Verteilergruppen](https://technet.microsoft.com/library/bb123722.aspx).
    
Nachdem Sie Verteilergruppen und e-Mail-aktivierte Sicherheitsgruppen im Exchange Admin Center erstellt haben, werden Ihre Namen und Benutzerlisten auf der Seite **Sicherheitsgruppen** angezeigt. Sie können diese Gruppen an beiden Positionen löschen, können sie jedoch nur im Exchange Admin Center bearbeiten. Dynamische Verteilergruppen werden auf der Seite **Sicherheitsgruppen** nicht angezeigt. 
  
 SharePoint-Gruppen werden automatisch beim Erstellen einer Websitesammlung erstellt. Den Standardgruppen werden mithilfe der SharePoint-Standardberechtigungsstufen (auch als SharePoint-Rollen bezeichnet) Rechte erteilt und wird Zugriff gewährt. Weitere Informationen finden Sie unter [SharePoint-Standardgruppen in SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a>Wie unterscheidet sich eine Sicherheitsgruppe von Sicherheitsgruppen, die ich in SharePoint erstelle?

Sicherheitsgruppen können mit SharePoint, Exchange, MDM, Windows und mehr verwendet werden. Eine Sicherheitsgruppe, die Sie in SharePoint erstellen, wird nur von der SharePoint-Websitesammlung erkannt.
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a>Muss ich Sicherheitsgruppen für meine Organisation verwenden, um sicher zu sein?

Nein. Dies ist nur eine weitere Möglichkeit zum Verwalten der Sicherheit für Ihre Organisation. Sie können immer individuell Benutzerberechtigungen erteilen und den Zugriff auf Websites zulassen. Mit Sicherheitsgruppen können Sie jedoch größere Benutzergruppen einfacher verwalten.
  
## <a name="can-i-send-email-to-a-security-group"></a>Kann ich eine e-Mail an eine Sicherheitsgruppe senden?

Ja. Wenn Sie jedoch Gruppen für e-Mail und Zusammenarbeit verwenden möchten, empfiehlt es sich, stattdessen [eine Microsoft 365-Gruppe zu erstellen](../create-groups/create-groups.md) . 
  
