---
title: Erteilen von Postfachberechtigungen für einen anderen Benutzer – Administratorhilfe
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 'Erfahren Sie, wie Sie einem Benutzer die Berechtigung erteilen, auf das Postfach eines anderen Benutzers zuzugreifen. Damit erhält der Benutzer das Recht, E-Mails zu lesen und E-Mails aus dem Postfach des anderen Benutzers zu senden. '
ms.openlocfilehash: dafe0f8c8f7d65b2721b70f6c132d179c461a89b
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780601"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a>Erteilen von Postfachberechtigungen für einen anderen Benutzer – Administratorhilfe

Als Administrator müssen Sie möglicherweise Unternehmensanforderungen erfüllen, die es einigen Benutzern gestatten, auf das Postfach eines anderen Benutzers zuzugreifen. Es kann z. B. wünschenswert sein, einen Mitarbeiter für das Senden oder Lesen von E-Mail aus dem Postfach seines Vorgesetzten zu aktivieren oder einem Ihrer Benutzer die Möglichkeit zum Senden von E-Mails im Auftrag eines anderen Benutzers zu geben. In diesem Thema wird gezeigt, wie dies erreicht werden kann.
  
Wenn Sie nach Informationen zum Erstellen und Verwalten von freigegebenen Postfächern suchen, lesen Sie [Erstellen eines freigegebenen Postfachs](../email/create-a-shared-mailbox.md).
    
## <a name="looking-to-set-up-mailbox-permissions"></a>Suchen Sie Informationen zum Einrichten von Postfachberechtigungen?

Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:
  
 **Einrichten der Berechtigungen:**
  
The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:
  
- [Lesen von E-Mails aus dem Postfach eines anderen Benutzers](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [Senden von E-Mails aus dem Postfach eines anderen Benutzers](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [Senden von E-Mails im Auftrag eines anderen Benutzers](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 **Ändern der Weitergabe:**
  
Sobald Sie die Berechtigungen eingerichtet haben, kann es bis zu 60 Minuten dauern, bis die Änderungen über das System weitergegeben wurden und wirksam sind.
  
 **Verwenden des Postfachs, nachdem die Berechtigungen eingerichtet wurden:**
  
There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)
  
## <a name="send-email-from-another-users-mailbox"></a>Senden von E-Mails aus dem Postfach eines anderen Benutzers

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.  
    
2. Wählen Sie den Namen des Benutzers (dem Sie eine Sendeberechtigung erteilen möchten) aus, um dessen Eigenschaftenbereich zu öffnen.
    
3. Wählen Sie auf der Registerkarte **E-Mail** die Option **Postfachberechtigungen verwalten** aus.

4. Wählen Sie neben **Senden als** die Option **Bearbeiten** aus. 

5. Wählen Sie **Berechtigungen hinzufügen** und dann den Namen der Person aus, in dessen Namen dieser Benutzer senden kann. 
    
6. Klicken Sie auf **Speichern**.
 
::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.  

2. Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.

3. Wählen Sie neben **Senden als** die Option **Bearbeiten** aus. 

4. Wählen Sie **Berechtigungen hinzufügen** und dann den Namen der Person aus, in dessen Namen dieser Benutzer senden kann. 
    
5. Klicken Sie auf **Speichern**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>. 

2. Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.

3. Wählen Sie neben **Senden als** die Option **Bearbeiten** aus. 

4. Wählen Sie **Berechtigungen hinzufügen** und dann den Namen der Person aus, in dessen Namen dieser Benutzer senden kann. 
    
5. Klicken Sie auf **Speichern**.

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a>Lesen von E-Mails im Postfach eines anderen Benutzers

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.  
    
2. Wählen Sie den Namen des Benutzers (für dessen Postfach Sie eine Leseerlaubnis erteilen möchten) aus, um seinen Eigenschaftenbereich zu öffnen.
    
3. Wählen Sie auf der Registerkarte **E-Mail** die Option **Postfachberechtigungen verwalten** aus.
    
4. Wählen Sie neben **Lesen und verwalten** die Option **Bearbeiten** aus. 
    
5. Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails über das betreffende Postfach ermöglichen möchten.

6. Klicken Sie auf **Speichern**.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.  
  
2. Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.
    
3. Wählen Sie neben **Lesen und verwalten** die Option **Bearbeiten** aus. 
    
4. Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails über das betreffende Postfach ermöglichen möchten.

5. Klicken Sie auf **Speichern**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>. 
  
2. Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.
    
3. Wählen Sie neben **Lesen und verwalten** die Option **Bearbeiten** aus. 
    
4. Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails über das betreffende Postfach ermöglichen möchten.

5. Klicken Sie auf **Speichern**.

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a>Senden von E-Mails im Auftrag eines anderen Benutzers

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.  

2. Wählen Sie den Namen des Benutzers (dem Sie eine Berechtigung zum **Senden im Auftrag von** erteilen möchten) aus, um dessen Eigenschaftenbereich zu öffnen.
    
3. Wählen Sie auf der Registerkarte **E-Mail** die Option **Postfachberechtigungen verwalten** aus.
    
4. Wählen Sie neben **Senden im Auftrag von** die Option **Bearbeiten** aus.

5. Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails im Auftrag des Postfachs ermöglichen möchten.

6. Klicken Sie auf **Speichern**.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.  

2. Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.

3. Wählen Sie neben **Senden im Auftrag von** die Option **Bearbeiten** aus.
    
4. Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails im Auftrag des Postfachs ermöglichen möchten.

5. Klicken Sie auf **Speichern**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>. 

2. Wählen Sie den gewünschten Benutzer aus, erweitern Sie **E-Mail-Einstellungen**, und wählen Sie dann neben **Postfachberechtigungen** die Option **Bearbeiten** aus.

3. Wählen Sie neben **Senden im Auftrag von** die Option **Bearbeiten** aus.
    
4. Wählen Sie **Berechtigungen hinzufügen** und dann den Namen des Benutzers oder der Benutzer aus, dem bzw. denen Sie das Senden von E-Mails im Auftrag des Postfachs ermöglichen möchten.

5. Klicken Sie auf **Speichern**.

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a>Senden und Lesen von Outlook und Outlook im Web Business


Want to know how to send email from another user's mailbox? Check out the following topics:
  
- [Verwalten der E-Mail- und Kalenderelemente einer anderen Person](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [Senden von E-Mails im Namen einer anderen Person oder Gruppe](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
