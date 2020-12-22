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
ms.openlocfilehash: af12cfe3acad9e12ca3983c9fa13f52b72f0a467
ms.sourcegitcommit: 16e018f8b6eef5dad48eabf179691ead3cebe533
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2020
ms.locfileid: "49725153"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a>Erteilen von Postfachberechtigungen für einen anderen Benutzer – Administratorhilfe

Als Administrator müssen Sie möglicherweise Unternehmensanforderungen erfüllen, die es einigen Benutzern gestatten, auf das Postfach eines anderen Benutzers zuzugreifen. Es kann z. B. wünschenswert sein, einen Mitarbeiter für das Senden oder Lesen von E-Mail aus dem Postfach seines Vorgesetzten zu aktivieren oder einem Ihrer Benutzer die Möglichkeit zum Senden von E-Mails im Auftrag eines anderen Benutzers zu geben. In diesem Thema wird gezeigt, wie dies erreicht werden kann.
  
Wenn Sie nach Informationen zum Erstellen und Verwalten von freigegebenen Postfächern suchen, lesen Sie [Erstellen eines freigegebenen Postfachs](../email/create-a-shared-mailbox.md).
    
## <a name="looking-to-set-up-mailbox-permissions"></a>Suchen Sie Informationen zum Einrichten von Postfachberechtigungen?

Postfachberechtigungen ermöglichen es Ihnen, einem anderen Benutzer Lese-/Schreibzugriff auf ein Postfach zu gewähren. Möglicherweise finden Sie in den nachstehenden Artikeln die benötigte Hilfe zum Einrichten und Verwenden dieser Funktion:
  
 **Einrichten der Berechtigungen:**
  
Der erste Schritt zum Einrichten von Berechtigungen ist die Entscheidung, welche Aktionen Sie dem anderen Benutzer im angegebenen Postfach erlauben möchten. Sie können einem Benutzer erlauben, E-Mails aus dem Postfach zu lesen, E-Mails im Auftrag eines anderen Benutzers zu senden und E-Mails so aussehen zu lassen, als ob sie über dieses Postfach gesendet wurden. In folgenden Artikeln finden Sie Informationen, wie die einzelnen Arten von Berechtigungen eingerichtet werden:
  
- [Lesen von E-Mails aus dem Postfach eines anderen Benutzers](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [Senden von E-Mails aus dem Postfach eines anderen Benutzers](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [Senden von E-Mails im Auftrag eines anderen Benutzers](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 **Ändern der Weitergabe:**
  
Sobald Sie die Berechtigungen eingerichtet haben, kann es bis zu 60 Minuten dauern, bis die Änderungen über das System weitergegeben wurden und wirksam sind.
  
 **Verwenden des Postfachs, nachdem die Berechtigungen eingerichtet wurden:**
  
Es gibt einige Möglichkeiten, wie Sie auf ein Postfach zugreifen können, nachdem Ihnen der Zugriff darauf gewährt wurde. Hilfe zu diesem Vorgang finden Sie in diesem Artikel: [Zugreifen auf das Postfach einer anderen Person](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).

> [!NOTE]
> Die Berechtigungen können nur innerhalb des Mandanten in der aktuellen Organisation festgelegt werden. Es ist nicht möglich, Postfachberechtigungen für Benutzer einzurichten, die nicht zum Mandanten gehören.
  
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


> [!NOTE]
> Die Berechtigungen **Lesen** und **Verwalten** werden als Berechtigung **Vollzugriff** bezeichnet, wenn sie im Exchange Admin Center erteilt werden. Die Berechtigung "Vollzugriff" gewährt nicht die Berechtigung **Senden als** oder **Senden im Auftrag**.

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


Möchten Sie wissen, wie Sie E-Mails aus dem Postfach eines anderen Benutzers senden können? Dann lesen Sie die folgenden Artikel:
  
- [Verwalten der E-Mail- und Kalenderelemente einer anderen Person](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [Senden von E-Mails im Namen einer anderen Person oder Gruppe](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
