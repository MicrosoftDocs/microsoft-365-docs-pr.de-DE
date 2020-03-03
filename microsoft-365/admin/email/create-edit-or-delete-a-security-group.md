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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Hier erfahren Sie, wie Sie eine Sicherheitsgruppe erstellen, bearbeiten oder löschen.
ms.openlocfilehash: f51c21261a83e1a0034a67f9f1580dd297a3d583
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362280"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a>Erstellen, bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center

[] Auf der Office 365-Seite **Gruppen** können Sie Gruppen mit Benutzerkonten erstellen, denen Sie dann in SharePoint Online und CRM Online die gleichen Berechtigungen zuweisen. So kann ein Administrator beispielsweise eine Sicherheitsgruppe erstellen, um einer bestimmten Personengruppe den Zugriff auf eine SharePoint-Website zu gewähren. Nur globale und Benutzerverwaltungsadministratoren verfügen über die Berechtigungen zum Erstellen, Bearbeiten oder Löschen von Sicherheitsgruppen. Weitere Informationen zu Administratorrollen finden Sie unter [Zuweisen von Administratorrollen](../add-users/assign-admin-roles.md). 
  
Darüber hinaus gibt es [Gruppen in Exchange Online und SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), mit denen Sie an eine Benutzergruppe E-Mails senden oder der Gruppe Berechtigungen zuweisen können, und [Gruppen in Exchange Online und SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), mit denen Benutzern Rechte zugewiesen sowie der Zugriff auf Websites und Websitesammlungen gewährt werden kann. 
  
> [!IMPORTANT]
>  Planen der Verwendung von Website Postfächern Alle Benutzer, die über eine Sicherheitsgruppe zu einer SharePoint-Website hinzugefügt werden, anstatt einzeln hinzugefügt zu werden, können nur das websitepostfach von SharePoint verwenden. Diese Benutzer können nicht über Outlook auf das websitepostfach zugreifen. Weitere Informationen finden Sie unter [Use Office 365 Groups anstelle von Website Postfächern](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx). 
  
## <a name="manage-security-groups-in-the-admin-center"></a>Verwalten von Sicherheitsgruppen im Admin Center

### <a name="add-a-security-group"></a>Hinzufügen einer Sicherheitsgruppe

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.
  
2. Wählen Sie auf der Seite **Gruppen** die Option **Gruppe hinzufügen**aus.
    
3. Wählen Sie auf der Seite **Gruppentyp auswählen** die Option **Sicherheit**aus. 
    
4. Führen Sie die Schritte zum Abschließen der Erstellung der Gruppe aus. 
 
### <a name="add-members-to-a-security-group"></a>Hinzufügen von Mitgliedern zu einer Sicherheitsgruppe

::: moniker range="o365-worldwide"

> [!NOTE]
> Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.
    
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

> [!NOTE]
> Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.
  
2. Wählen Sie auf der Seite **Gruppen** den Namen der Gruppe aus. 
    
3. Wählen Sie im Bereich "Einstellungen" die Registerkarte " **Allgemein** " oder " **Mitglieder** " aus, um Gruppendetails oder Mitglieder zu bearbeiten.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.
  
2. Wählen Sie auf der Seite **Gruppen** den Namen der Gruppe aus. 
    
3. Wählen Sie im Bereich Sicherheitsgruppe neben **Name** oder **Mitglieder** Registerkarte **Bearbeiten** aus, um Gruppendetails oder Mitglieder zu bearbeiten.
    
4. Nachdem Sie Änderungen vorgenommen haben, wählen Sie **Save** \> **Close**aus.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.
  
2. Wählen Sie auf der Seite **Gruppen** den Namen der Gruppe aus. 
    
3. Wählen Sie im Bereich Sicherheitsgruppe neben **Name** oder **Mitglieder** Registerkarte **Bearbeiten** aus, um Gruppendetails oder Mitglieder zu bearbeiten.
    
4. Nachdem Sie Änderungen vorgenommen haben, wählen Sie **Save** \> **Close**aus.

::: moniker-end


### <a name="delete-a-security-group"></a>Löschen einer Sicherheitsgruppe

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.
    
2. Wählen Sie auf der Seite **Gruppen** den Namen der Gruppe aus. 
    
3. Wählen Sie **Gruppe löschen** (wasetbin-Symbol) aus, und bestätigen Sie, indem Sie **Löschen**auswählen.
    
    Wählen Sie **Schließen** , nachdem die Gruppe gelöscht wurde. 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a>Gruppen in Exchange Online und SharePoint Online

Wenn Sie Benutzergruppen erstellen möchten, damit Sie e-Mails an alle gleichzeitig senden können, können Sie dies im Exchange Admin Center tun, indem Sie zu **Administrator** \> **-Exchange** \> - **Empfänger** \> **Gruppen**wechseln. Wählen Sie dann **neu**![hinzu](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png)fügen aus, und wählen Sie die Art der Gruppe aus, die Sie erstellen möchten: 
  
- **Verteilergruppe**: Wird verwendet, um Nachrichten an eine Benutzergruppe zu senden. Sie wird auch als *e-Mail-aktivierte Verteilergruppe*oder in Office 365 eine *Verteilerliste*bezeichnet. Weitere Informationen finden Sie unter [Verwalten von Verteilergruppen](https://technet.microsoft.com/library/bb124513.aspx).
    
- **Sicherheitsgruppe**: Kann verwendet werden, um Nachrichten an eine Benutzergruppe zu senden oder um Berechtigungen zum Zugriff auf Ressourcen zu gewähren. Diese Gruppe wird auch als *e-Mail-aktivierte Sicherheitsgruppe*bezeichnet. Weitere Informationen finden Sie unter [Verwalten von E-Mail-aktivierten Sicherheitsgruppen](https://technet.microsoft.com/library/bb123521.aspx).
    
- **Dynamische Verteilergruppe**: Eine Art von Verteilergruppe, bei der die Empfängerliste jedes Mal, wenn Sie eine Nachricht senden, basierend auf von Ihnen definierten Filtern und Bedingungen neu berechnet wird. Weitere Informationen finden Sie unter [Verwalten dynamischer Verteilergruppen](https://technet.microsoft.com/library/bb123722.aspx).
    
Nachdem Sie im Exchange Admin Center Verteilergruppen und E-Mail-aktivierte Sicherheitsgruppen erstellt haben, werden die Namen und Benutzerlisten auf der Office 365-Seite **Sicherheitsgruppen** angezeigt. Sie können diese Gruppen an beiden Positionen löschen, können sie jedoch nur im Exchange Admin Center bearbeiten. Dynamische Verteilergruppen werden auf der Seite **Sicherheitsgruppen** von Office 365 nicht angezeigt. 
  
 SharePoint-Gruppen werden automatisch beim Erstellen einer Websitesammlung erstellt. Den Standardgruppen werden mithilfe der SharePoint-Standardberechtigungsstufen (auch als SharePoint-Rollen bezeichnet) Rechte erteilt und wird Zugriff gewährt. Weitere Informationen finden Sie unter [SharePoint-Standardgruppen in SharePoint Online](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx).
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a>Wie unterscheidet sich eine Sicherheitsgruppe von Sicherheitsgruppen, die ich in SharePoint erstelle?

Sicherheitsgruppen können mit SharePoint, Exchange, MDM, Windows und mehr verwendet werden. Eine Sicherheitsgruppe, die Sie in SharePoint erstellen, wird nur von der SharePoint-Websitesammlung erkannt.
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a>Muss ich Sicherheitsgruppen für meine Organisation verwenden, um sicher zu sein?

Nein. Dies ist nur eine weitere Möglichkeit zum Verwalten der Sicherheit für Ihre Organisation. Sie können immer individuell Benutzerberechtigungen erteilen und den Zugriff auf Websites zulassen. Mit Sicherheitsgruppen können Sie jedoch größere Benutzergruppen einfacher verwalten.
  
## <a name="can-i-send-email-to-a-security-group"></a>Kann ich eine e-Mail an eine Sicherheitsgruppe senden?

Ja. Wenn Sie jedoch Gruppen für e-Mail und Zusammenarbeit verwenden möchten, empfiehlt es sich, stattdessen [eine Office 365 Gruppe zu erstellen](../create-groups/create-groups.md) . 
  
