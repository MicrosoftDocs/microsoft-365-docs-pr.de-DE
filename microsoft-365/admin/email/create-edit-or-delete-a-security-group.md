---
title: Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe in der Microsoft 365 Admin Center
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
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Erfahren Sie, wie Sie eine Sicherheitsgruppe erstellen, bearbeiten oder löschen.
ms.openlocfilehash: 525acc45b293563f58bb9aa12c40bec1438cb055
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393955"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a>Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe in der Microsoft 365 Admin Center

Auf der Seite Microsoft 365 **Gruppen** können Sie Gruppen von Benutzerkonten erstellen, denen Sie in SharePoint Online und CRM Online die gleichen Berechtigungen zuweisen können. Beispielsweise kann ein Administrator eine Sicherheitsgruppe erstellen, um einer bestimmten Gruppe von Personen Zugriff auf eine SharePoint Website zu gewähren. Nur globale Und Benutzerverwaltungsadministratoren verfügen über Berechtigungen zum Erstellen, Bearbeiten oder Löschen von Sicherheitsgruppen. Weitere Informationen zu Administratorrollen finden Sie unter [Zuweisen von Administratorrollen.](../add-users/assign-admin-roles.md) 
  
Darüber hinaus gibt es [Gruppen in Exchange Online und SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), mit denen Sie an eine Benutzergruppe E-Mails senden oder der Gruppe Berechtigungen zuweisen können, und [Gruppen in Exchange Online und SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), mit denen Benutzern Rechte zugewiesen sowie der Zugriff auf Websites und Websitesammlungen gewährt werden kann. 
  
> [!IMPORTANT]
>  Planen der Verwendung von Websitepostfächern? Alle Benutzer, die einer SharePoint Website über eine Sicherheitsgruppe hinzugefügt werden, anstatt einzeln hinzugefügt zu werden, können nur das Websitepostfach aus SharePoint verwenden. Diese Benutzer können nicht über Outlook auf das Websitepostfach zugreifen. Weitere Informationen finden Sie unter [Verwenden Microsoft 365 Gruppen anstelle von Websitepostfächern.](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b) 
  
## <a name="manage-security-groups-in-the-admin-center"></a>Verwalten von Sicherheitsgruppen im Admin Center

### <a name="add-a-security-group"></a>Hinzufügen einer Sicherheitsgruppe

1. Wechseln Sie im Microsoft 365 Admin Center zur Seite **"Gruppengruppen".**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a>
  
2. Wählen Sie auf der Seite **"Gruppen"** die Option **"Gruppe hinzufügen"** aus.
    
3. Wählen Sie auf der Seite **"Gruppentyp auswählen"** die Option **"Sicherheit"** aus. 
    
4. Führen Sie die Schritte aus, um die Erstellung der Gruppe abzuschließen. 
 
### <a name="add-members-to-a-security-group"></a>Hinzufügen von Mitgliedern zu einer Sicherheitsgruppe
    
1. Wählen Sie den Namen der Sicherheitsgruppe auf der Seite **"Gruppen"** und auf der Registerkarte **"Mitglieder"** die Option **"Alle anzeigen" und "Mitglieder verwalten"** aus. 
    
2. Wählen Sie im Gruppenbereich **"Mitglieder hinzufügen"** aus, wählen Sie die Person aus der Liste aus, oder geben Sie den Namen der Person ein, die Sie im **Suchfeld** hinzufügen möchten, und wählen Sie dann **"Speichern"** aus.
    
    Um Mitglieder zu entfernen, wählen Sie das X neben ihrem Namen aus. 
  
### <a name="edit-a-security-group"></a>Bearbeiten einer Sicherheitsgruppe

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.
  
2. Wählen Sie auf der Seite **"Gruppen"** den Namen der Gruppe aus. 
    
3. Wählen Sie im Einstellungsbereich die Registerkarte **"Allgemein"** oder die Registerkarte **"Mitglieder"** aus, um Gruppendetails oder Mitglieder zu bearbeiten.

### <a name="delete-a-security-group"></a>Löschen einer Sicherheitsgruppe

1. Wechseln Sie im Admin Center zur Seite **Gruppen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.
    
2. Wählen Sie auf der Seite **"Gruppen"** den Namen der Gruppe aus. 
    
3. Wählen Sie **"Gruppe löschen"** (Wasetbin-Symbol) aus, und bestätigen Sie dann, indem Sie **"Löschen"** auswählen.
    
    Wählen Sie **"Schließen"** aus, nachdem die Gruppe gelöscht wurde. 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a>Gruppen in Exchange Online und SharePoint Online

Wenn Sie Benutzergruppen erstellen möchten, damit Sie ihnen alle gleichzeitig E-Mails senden können, können Sie dies im Exchange Admin Center tun, indem Sie zu **Admin** \> **Exchange** \> **Recipients** \> **Groups** wechseln. Wählen Sie als Nächstes **"Neu** ![ hinzufügen" ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) aus, und wählen Sie die Art der Gruppe aus, die Sie erstellen möchten: 
  
- **Verteilergruppe**: Wird verwendet, um Nachrichten an eine Benutzergruppe zu senden. Es wird auch als  *E-Mail-aktivierte Verteilergruppe* oder  *Verteilerliste* bezeichnet. Weitere Informationen finden Sie unter [Verwalten von Verteilergruppen](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).
    
- **Sicherheitsgruppe**: Kann verwendet werden, um Nachrichten an eine Benutzergruppe zu senden oder um Berechtigungen zum Zugriff auf Ressourcen zu gewähren. Diese Gruppe wird auch als *E-Mail-aktivierte Sicherheitsgruppe* bezeichnet. Weitere Informationen finden Sie unter [Verwalten von E-Mail-aktivierten Sicherheitsgruppen](/Exchange/recipients/mail-enabled-security-groups).
    
- **Dynamische Verteilergruppe**: Eine Art von Verteilergruppe, bei der die Empfängerliste jedes Mal, wenn Sie eine Nachricht senden, basierend auf von Ihnen definierten Filtern und Bedingungen neu berechnet wird. Weitere Informationen finden Sie unter [Verwalten dynamischer Verteilergruppen](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).
    
Nachdem Sie Verteilergruppen und E-Mail-aktivierte Sicherheitsgruppen im Exchange Admin Center erstellt haben, werden deren Namen und Benutzerlisten auf der Seite **"Sicherheitsgruppen"** angezeigt. Sie können diese Gruppen an beiden Positionen löschen, können sie jedoch nur im Exchange Admin Center bearbeiten. Dynamische Verteilergruppen werden nicht auf der Seite **"Sicherheitsgruppen"** angezeigt. 
  
 SharePoint-Gruppen werden automatisch beim Erstellen einer Websitesammlung erstellt. Den Standardgruppen werden mithilfe der SharePoint-Standardberechtigungsstufen (auch als SharePoint-Rollen bezeichnet) Rechte erteilt und wird Zugriff gewährt. Weitere Informationen finden Sie unter [Standard-SharePoint-Gruppen in SharePoint Online.](/sharepoint/default-sharepoint-groups)
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a>Wie unterscheidet sich eine Sicherheitsgruppe von Sicherheitsgruppen, die ich in SharePoint erstelle?

Sicherheitsgruppen können mit SharePoint, Exchange, MDM, Windows und mehr verwendet werden. Eine Sicherheitsgruppe, die Sie in SharePoint erstellen, wird nur von der SharePoint-Websitesammlung erkannt.
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a>Muss ich Sicherheitsgruppen verwenden, damit meine Organisation sicher ist?

Nein. Dies ist nur eine weitere Möglichkeit zum Verwalten der Sicherheit für Ihre Organisation. Sie können immer individuell Benutzerberechtigungen erteilen und den Zugriff auf Websites zulassen. Mit Sicherheitsgruppen können Sie jedoch größere Benutzergruppen einfacher verwalten.
  
## <a name="can-i-send-email-to-a-security-group"></a>Kann ich E-Mails an eine Sicherheitsgruppe senden?

Ja. Wenn Sie jedoch Gruppen für E-Mails und Zusammenarbeit verwenden möchten, empfehlen wir, stattdessen [eine Microsoft 365 Gruppe zu erstellen.](../create-groups/create-groups.md) 

## <a name="related-content"></a>Verwandte Inhalte

[Erstellen einer Gruppe im Microsoft 365 Admin Center](../create-groups/create-groups.md) (Artikel)\
[Erläutern Microsoft 365 Gruppen für Ihre Benutzer](../create-groups/explain-groups-knowledge-worker.md) (Artikel)\
[Verwalten einer Gruppe im Microsoft 365 Admin Center](../create-groups/manage-groups.md) (Artikel)