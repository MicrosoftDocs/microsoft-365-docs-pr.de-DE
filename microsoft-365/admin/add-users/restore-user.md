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
description: Erfahren Sie, wie Sie gelöschte Benutzerkonten und alle zugeordneten Daten wiederherstellen.
ms.openlocfilehash: 4893f7468a8ab5919dd3be1cce233917323f2076
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023965"
---
# <a name="restore-a-user"></a>Wiederherstellen eines Benutzers
   
Wenn Sie ein Benutzerkonto innerhalb von 30 Tagen nach dem Löschen wiederherstellen, werden das Benutzerkonto und alle zugehörigen Daten wiederhergestellt. Der Benutzer kann sich mit demselben Firmen- oder Schulkonto anmelden. Das Postfach wird vollständig wiederhergestellt. Wenn Sie herausfinden müssen, wie viel Zeit noch bleibt, um ein bestimmtes Benutzerkonto wiederherzustellen, [wenden Sie sich an uns](../contact-support-for-business-products.md).
  
Nachfolgend ein paar Tipps:
  
- Stellen Sie sicher, dass Lizenzen verfügbar sind, die dem Konto zugewiesen werden können.
    
- Wenn Ihr Unternehmen Active Directory verwendet, lesen Sie die unter [Behandeln von Problemen mit gelöschten Benutzerkonten in Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts.md) aufgeführten Anweisungen zum Wiederherstellen eines Benutzerkontos. 
    
## <a name="restore-one-or-more-user-accounts"></a>Wiederherstellen eines oder mehrerer Benutzerkonten

Sie müssen ein globaler Microsoft 365-Administrator oder Benutzerverwaltungsadministrator sein, um diese Schritte ausführen zu können. 
  
 
::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur **Seite** Benutzer \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">gelöschte</a> Benutzer.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie zum [Admin Center,](https://go.microsoft.com/fwlink/p/?linkid=848041)und wählen Sie **dann Benutzer** \> **Gelöschte Benutzer aus.**

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie zum [Admin Center,](https://go.microsoft.com/fwlink/p/?linkid=850627)und wählen Sie **dann Benutzer** \> **Gelöschte Benutzer aus.**

::: moniker-end

2. Wählen Sie **auf der** Seite Gelöschte Benutzer die Namen der Benutzer aus, die Sie wiederherstellen möchten, und wählen Sie dann **Wiederherstellen aus.**
    
 
3. Folgen Sie den Aufforderungen zum Festlegen ihres Kennworts, und wählen Sie dann **Wiederherstellen aus.**
    
4. Wenn der Benutzer erfolgreich wiederhergestellt wurde, wählen Sie **E-Mail senden und schließen aus.** Wenn ein Namens- oder Proxyadressenkonflikt vorliegt, lesen Sie die nachstehenden Anweisungen, um zu erfahren, wie Sie diese Konten wiederherstellen können.
    
Nachdem Sie einen Benutzer wiederhergestellt haben, müssen Sie ihn darüber informieren, dass sich sein Kennwort geändert hat, und folgen Sie ihm.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>Wiederherstellen eines Benutzers mit einem Benutzernamenskonflikt
<a name="RestoreUserNameConflict"> </a>

Ein Benutzernamenskonflikt tritt auf, wenn Sie ein Benutzerkonto löschen, ein neues Benutzerkonto mit demselben Benutzernamen (für denselben Benutzer oder für einen anderen Benutzer mit einem ähnlichen Namen) erstellen und dann später versuchen, das gelöschte Konto wiederherzustellen.
  
Um diesen Konflikt zu lösen, können Sie entweder das aktive Benutzerkonto durch das wiederherzustellende Konto ersetzen oder dem Konto, das Sie wiederherstellen, einen anderen Benutzernamen zuweisen, damit nicht zwei Konten mit demselben Benutzernamen vorhanden sind. Gehen Sie dazu wie folgt vor:
  

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur **Seite** Benutzer \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">gelöschte</a> Benutzer.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie zum [Admin Center,](https://go.microsoft.com/fwlink/p/?linkid=848041)und wählen Sie **dann Benutzer** \> **Gelöschte Benutzer aus.**

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie zum [Admin Center,](https://go.microsoft.com/fwlink/p/?linkid=850627)und wählen Sie **dann Benutzer** \> **Gelöschte Benutzer aus.**

::: moniker-end

  
2. Wählen Sie **auf der Seite** Gelöschte Benutzer die Namen der Benutzer aus, die Sie wiederherstellen möchten, und wählen Sie dann **Wiederherstellen aus.**
    
    > [!NOTE]
    > Wenn mindestens zwei Benutzer nicht wiederhergestellt werden können, wird in einer Fehlermeldung angezeigt, dass der Wiederherstellungsvorgang für einige Benutzer nicht erfolgreich ausgeführt wurde. Öffnen Sie das Protokoll, um anzuzeigen, welche Benutzer nicht wiederhergestellt wurden, und stellen Sie dann die entsprechenden Konten jeweils einzeln wieder her. 
  
3. Folgen Sie den Aufforderungen zum Festlegen des Kennworts, und wählen Sie **Wiederherstellen aus.**
    
4. Sie werden in einer Meldung darüber informiert, dass beim Wiederherstellen des Kontos ein Problem aufgetreten ist. Führen Sie eine der folgenden Aktionen aus:
    
  - Brechen Sie den Wiederherstellungsvorgang ab, und benennen Sie den aktuellen aktiven Benutzer um. Versuchen Sie dann, den Wiederherstellungsvorgang erneut auszuführen.
    
  - OR, geben Sie eine neue primäre E-Mail-Adresse für den Benutzer ein, und wählen Sie **Wiederherstellen aus.**
    
5. Überprüfen Sie die Ergebnisse, und wählen Sie dann **Schließen** aus.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>Wiederherstellen eines Benutzers, der einen Proxyadressenkonflikt hat

Ein Proxyadressenkonflikt tritt auf, wenn Sie ein Benutzerkonto löschen, das eine Proxyadresse enthält, dieselbe Proxyadresse einem anderen Konto zuweisen und dann versuchen, das gelöschte Konto wiederherzustellen. Führen Sie die nachstehenden Schritte aus, um das Problem zu beheben.
  
Dazu müssen Sie [über Administratorberechtigungen](about-admin-roles.md) in Microsoft 365 verfügen. 
  

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur **Seite** Benutzer \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">gelöschte</a> Benutzer.

::: moniker-end

::: moniker range="o365-germany"

Wechseln Sie zum [Admin Center,](https://go.microsoft.com/fwlink/p/?linkid=848041)und wählen Sie **dann Benutzer** \> **Gelöschte Benutzer aus.**

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie zum [Admin Center,](https://go.microsoft.com/fwlink/p/?linkid=850627)und wählen Sie **dann Benutzer** \> **Gelöschte Benutzer aus.**

::: moniker-end

2. Wählen Sie auf der Seite **Gelöschte Benutzer** den Benutzer aus, den Sie wiederherstellen möchten, und wählen Sie dann **Wiederherstellen** aus. 
    
3. Folgen Sie **auf** der Seite Wiederherstellen den Anweisungen zum Festlegen des Kennworts, und wählen Sie **Wiederherstellen aus.** Für den Benutzer, den Sie wiederherstellen, werden alle Konflikt verursachenden Proxyadressen automatisch entfernt.
    
4. Überprüfen Sie die Ergebnisse, und wählen Sie dann **Schließen** aus.

## <a name="related-articles"></a>Verwandte Artikel

[Löschen eines Benutzers](delete-a-user.md)
