---
title: Wiederherstellen eines Benutzers
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
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Innerhalb von 30 Tagen nach dem Löschen eines Benutzerkontos können Sie das Konto und alle Daten wiederherstellen, und der Benutzer kann sich mit demselben Konto anmelden.
ms.openlocfilehash: f849fe8e403aa9a72eccb4dd65665ec9f33618d1
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779650"
---
# <a name="restore-a-user"></a>Wiederherstellen eines Benutzers
   
Wenn Sie ein Benutzerkonto innerhalb von 30 Tagen nach dem Löschen wiederherstellen, werden das Benutzerkonto und alle zugehörigen Daten wiederhergestellt. Der Benutzer kann sich mit demselben Firmen- oder Schulkonto anmelden. Das Postfach wird vollständig wiederhergestellt. Wenn Sie herausfinden müssen, wie viel Zeit noch bleibt, um ein bestimmtes Benutzerkonto wiederherzustellen, [wenden Sie sich an uns](../../business-video/get-help-support.md).
  
Nachfolgend ein paar Tipps:
  
- Stellen Sie sicher, dass Dem Konto Lizenzen zugewiesen werden können.
    
- Wenn Ihr Unternehmen Active Directory verwendet, finden Sie Informationen zum Wiederherstellen eines Benutzerkontos unter [Problembehandlung gelöschter Benutzerkonten in Office 365.](/office365/troubleshoot/active-directory/restore-deleted-user-accounts) 
    
## <a name="restore-one-or-more-user-accounts"></a>Wiederherstellen eines oder mehrerer Benutzerkonten

Sie müssen ein Microsoft 365 globaler Administrator oder Benutzerverwaltungsadministrator sein, um diese Schritte ausführen zu können. 

1. Wechseln Sie im Admin Center zur Seite **"Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">gelöschte Benutzer".</a>

2. Wählen Sie auf der Seite **"Gelöschte Benutzer"** die Namen der Benutzer aus, die Sie wiederherstellen möchten, und wählen Sie dann **"Wiederherstellen"** aus.
    
3. Befolgen Sie die Aufforderungen, um ihr Kennwort festzulegen, und wählen Sie dann **Wiederherstellen** aus.
    
4. Wenn der Benutzer erfolgreich wiederhergestellt wurde, wählen Sie **"E-Mail senden" aus, und schließen Sie**. Wenn ein Namens- oder Proxyadressenkonflikt vorliegt, lesen Sie die nachstehenden Anweisungen, um zu erfahren, wie Sie diese Konten wiederherstellen können.
    
Nachdem Sie einen Benutzer wiederhergestellt haben, stellen Sie sicher, dass Sie diesen benachrichtigen, dass sein Kennwort geändert wurde, und folgen Sie diesen.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>Wiederherstellen eines Benutzers mit einem Benutzernamenskonflikt

Ein Benutzernamenskonflikt tritt auf, wenn Sie ein Benutzerkonto löschen, ein neues Benutzerkonto mit demselben Benutzernamen (für denselben Benutzer oder für einen anderen Benutzer mit einem ähnlichen Namen) erstellen und dann später versuchen, das gelöschte Konto wiederherzustellen.
  
Um diesen Konflikt zu lösen, können Sie entweder das aktive Benutzerkonto durch das wiederherzustellende Konto ersetzen oder dem Konto, das Sie wiederherstellen, einen anderen Benutzernamen zuweisen, damit nicht zwei Konten mit demselben Benutzernamen vorhanden sind. Gehen Sie dazu wie folgt vor:

1. Wechseln Sie im Admin Center zur Seite **"Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">gelöschte Benutzer".</a>
  
2. Wählen Sie auf der Seite **"Gelöschte Benutzer"** die Namen der Benutzer aus, die Sie wiederherstellen möchten, und wählen Sie dann **"Wiederherstellen"** aus.
    
    > [!NOTE]
    > Wenn mindestens zwei Benutzer nicht wiederhergestellt werden können, wird in einer Fehlermeldung angezeigt, dass der Wiederherstellungsvorgang für einige Benutzer nicht erfolgreich ausgeführt wurde. Öffnen Sie das Protokoll, um anzuzeigen, welche Benutzer nicht wiederhergestellt wurden, und stellen Sie dann die entsprechenden Konten jeweils einzeln wieder her. 
  
3. Folgen Sie den Aufforderungen, um das Kennwort festzulegen, und wählen Sie **"Wiederherstellen"** aus.
    
4. Sie werden in einer Meldung darüber informiert, dass beim Wiederherstellen des Kontos ein Problem aufgetreten ist. Führen Sie eine der folgenden Aktionen aus:
    
  - Brechen Sie den Wiederherstellungsvorgang ab, und benennen Sie den aktuellen aktiven Benutzer um. Versuchen Sie dann, den Wiederherstellungsvorgang erneut auszuführen.
    
  - OR, type a new primary email address for the user and select **Restore**.
    
5. Überprüfen Sie die Ergebnisse, und wählen Sie dann **Schließen** aus.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>Wiederherstellen eines Benutzers, der einen Proxyadressenkonflikt hat

Ein Proxyadressenkonflikt tritt auf, wenn Sie ein Benutzerkonto löschen, das eine Proxyadresse enthält, dieselbe Proxyadresse einem anderen Konto zuweisen und dann versuchen, das gelöschte Konto wiederherzustellen. Führen Sie die nachstehenden Schritte aus, um das Problem zu beheben.
  
Sie müssen über [Administratorberechtigungen](about-admin-roles.md) in Microsoft 365 verfügen, um dies zu tun. 

1. Wechseln Sie im Admin Center zur Seite **"Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">gelöschte Benutzer".</a>

2. Wählen Sie auf der Seite **Gelöschte Benutzer** den Benutzer aus, den Sie wiederherstellen möchten, und wählen Sie dann **Wiederherstellen** aus. 
    
3. Befolgen Sie auf der Seite **"Wiederherstellen"** die Anweisungen, um das Kennwort festzulegen, und wählen Sie **"Wiederherstellen"** aus. Für den Benutzer, den Sie wiederherstellen, werden alle Konflikt verursachenden Proxyadressen automatisch entfernt.
    
4. Überprüfen Sie die Ergebnisse, und wählen Sie dann **Schließen** aus.

## <a name="related-content"></a>Verwandte Inhalte

[Löschen eines Benutzers](delete-a-user.md) (Artikel)\
[Zuweisen von Administratorrollen](assign-admin-roles.md) (Video)\
[Zuweisen von Lizenzen zu Benutzern](../manage/assign-licenses-to-users.md) (Artikel)
