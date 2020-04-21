---
title: Wiederherstellen eines Benutzers
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Hier erfahren Sie, wie gelöschte Benutzerkonten und alle zugehörigen Daten wiederhergestellt werden.
ms.openlocfilehash: 78766f1f6708665271361d542372aa945b0a7e29
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43624058"
---
# <a name="restore-a-user"></a>Wiederherstellen eines Benutzers
   
Wenn Sie ein Benutzerkonto innerhalb von 30 Tagen nach dem Löschen wiederherstellen, werden das Benutzerkonto und alle zugehörigen Daten wiederhergestellt. Der Benutzer kann sich mit demselben Firmen- oder Schulkonto anmelden. Das Postfach wird vollständig wiederhergestellt. Wenn Sie herausfinden müssen, wie viel Zeit noch bleibt, um ein bestimmtes Benutzerkonto wiederherzustellen, [wenden Sie sich an uns](../contact-support-for-business-products.md).
  
Nachfolgend ein paar Tipps:
  
- Stellen Sie sicher, dass Lizenzen zur Verfügung stehen, um das Konto zuzuweisen.
    
- Wenn Ihr Unternehmen Active Directory verwendet, lesen Sie die unter [Behandeln von Problemen mit gelöschten Benutzerkonten in Office 365](https://support.microsoft.com/kb/2619308) aufgeführten Anweisungen zum Wiederherstellen eines Benutzerkontos. 
    
## <a name="restore-one-or-more-user-accounts"></a>Wiederherstellen eines oder mehrerer Benutzerkonten

Sie müssen ein Microsoft 365 globaler Administrator oder Administrator der Benutzerverwaltung sein, um diese Schritte ausführen zu können. 
  
 
::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur \> Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Gelöschte</a> Benutzer Benutzer. **Users**

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie zum [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=848041), **und wählen Sie** \> dann **Gelöschte**Benutzer aus.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie zum [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=850627), **und wählen Sie** \> dann **Gelöschte**Benutzer aus.

::: moniker-end

2. Wählen Sie auf der Seite **Gelöschte Benutzer** die Namen der Benutzer aus, die Sie wiederherstellen möchten, und wählen Sie dann **Wiederherstellen**aus.
    
 
3. Führen Sie die Anweisungen aus, um Ihr Kennwort festzulegen, und wählen Sie dann **Wiederherstellen**aus.
    
4. Wenn der Benutzer erfolgreich wiederhergestellt wurde, wählen Sie **e-Mail senden und schließen**aus. Wenn ein Namens- oder Proxyadressenkonflikt vorliegt, lesen Sie die nachstehenden Anweisungen, um zu erfahren, wie Sie diese Konten wiederherstellen können.
    
Nachdem Sie einen Benutzer wiederhergestellt haben, müssen Sie darauf achten, dass das Kennwort geändert wurde, und Sie nachverfolgen.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>Wiederherstellen eines Benutzers mit einem Benutzernamenskonflikt
<a name="RestoreUserNameConflict"> </a>

Ein Benutzernamenskonflikt tritt auf, wenn Sie ein Benutzerkonto löschen, ein neues Benutzerkonto mit demselben Benutzernamen (für denselben Benutzer oder für einen anderen Benutzer mit einem ähnlichen Namen) erstellen und dann später versuchen, das gelöschte Konto wiederherzustellen.
  
Um diesen Konflikt zu lösen, können Sie entweder das aktive Benutzerkonto durch das wiederherzustellende Konto ersetzen oder dem Konto, das Sie wiederherstellen, einen anderen Benutzernamen zuweisen, damit nicht zwei Konten mit demselben Benutzernamen vorhanden sind. Gehen Sie dazu wie folgt vor:
  

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur \> Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Gelöschte</a> Benutzer Benutzer. **Users**

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie zum [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=848041), **und wählen Sie** \> dann **Gelöschte**Benutzer aus.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie zum [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=850627), **und wählen Sie** \> dann **Gelöschte**Benutzer aus.

::: moniker-end

  
2. Wählen Sie auf der Seite **Gelöschte Benutzer** die Namen der Benutzer aus, die Sie wiederherstellen möchten, und wählen Sie dann **Wiederherstellen**aus.
    
    > [!NOTE]
    > Wenn mindestens zwei Benutzer nicht wiederhergestellt werden können, wird in einer Fehlermeldung angezeigt, dass der Wiederherstellungsvorgang für einige Benutzer nicht erfolgreich ausgeführt wurde. Öffnen Sie das Protokoll, um anzuzeigen, welche Benutzer nicht wiederhergestellt wurden, und stellen Sie dann die entsprechenden Konten jeweils einzeln wieder her. 
  
3. Führen Sie die Anweisungen aus, um das Kennwort festzulegen, und wählen Sie **Wiederherstellen**aus.
    
4. Sie werden in einer Meldung darüber informiert, dass beim Wiederherstellen des Kontos ein Problem aufgetreten ist. Führen Sie eine der folgenden Aktionen aus:
    
  - Brechen Sie den Wiederherstellungsvorgang ab, und benennen Sie den aktuellen aktiven Benutzer um. Versuchen Sie dann, den Wiederherstellungsvorgang erneut auszuführen.
    
  - Oder geben Sie eine neue primäre e-Mail-Adresse für den Benutzer ein, und wählen Sie **Wiederherstellen**aus.
    
5. Überprüfen Sie die Ergebnisse, und wählen Sie dann **Schließen** aus.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>Wiederherstellen eines Benutzers, der einen Proxyadressenkonflikt hat

Ein Proxyadressenkonflikt tritt auf, wenn Sie ein Benutzerkonto löschen, das eine Proxyadresse enthält, dieselbe Proxyadresse einem anderen Konto zuweisen und dann versuchen, das gelöschte Konto wiederherzustellen. Führen Sie die nachstehenden Schritte aus, um das Problem zu beheben.
  
Sie benötigen [Administratorberechtigungen](about-admin-roles.md) in Microsoft 365, um dies zu tun. 
  

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur \> Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Gelöschte</a> Benutzer Benutzer. **Users**

::: moniker-end

::: moniker range="o365-germany"

Wechseln Sie zum [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=848041), **und wählen Sie** \> dann **Gelöschte**Benutzer aus.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie zum [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=850627), **und wählen Sie** \> dann **Gelöschte**Benutzer aus.

::: moniker-end

2. Wählen Sie auf der Seite **Gelöschte Benutzer** den Benutzer aus, den Sie wiederherstellen möchten, und wählen Sie dann **Wiederherstellen** aus. 
    
3. Befolgen Sie auf der Seite **Wiederherstellen** die Anweisungen zum Festlegen des Kennworts, und wählen Sie **Wiederherstellen**aus. Für den Benutzer, den Sie wiederherstellen, werden alle Konflikt verursachenden Proxyadressen automatisch entfernt.
    
4. Überprüfen Sie die Ergebnisse, und wählen Sie dann **Schließen** aus.

## <a name="related-articles"></a>Verwandte Artikel

[Löschen eines Benutzers](delete-a-user.md)
  
