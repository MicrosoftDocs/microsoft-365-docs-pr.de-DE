---
title: Hinzufügen eines weiteren E-Mail-Alias für einen Benutzer
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
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Erfahren Sie, wie Sie mit Ihrem Microsoft 365 for Business-Konto mehr als eine e-Mail-Adresse namens "e-Mail-Alias" erhalten. '
ms.openlocfilehash: 030d8022a8503f6b383d03b0dd97720f66d8f2f6
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080015"
---
# <a name="add-another-email-alias-for-a-user"></a>Hinzufügen eines weiteren E-Mail-Alias für einen Benutzer

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
Dieser Artikel richtet sich an Microsoft 365-Administratoren, die über Geschäfts Abonnements verfügen. Er gilt nicht für private Benutzer.
  
Eine primäre e-Mail-Adresse in Microsoft 365 ist normalerweise die e-Mail-Adresse, die einem Benutzer bei der Erstellung seines Kontos zugewiesen wurde. Wenn der Benutzer eine E-Mail an eine andere Person sendet, wird seine primäre E-Mail-Adresse in E-Mail-Apps in der Regel im Feld  *Von*  angezeigt. Sie können auch mehrere e-Mail-Adressen haben, die mit Ihrem Microsoft 365 for Business-Konto verknüpft sind. Diese zusätzlichen Adressen werden als "Aliase" bezeichnet. 
  
Angenommen, Jenna hat die e-Mail-Adresse Jenna@contosoco.com, aber Sie möchte auch eine e-Mail an Jen@contosoco.com empfangen, da einige Personen auf Sie mit diesem Namen Bezug nehmen. Sie können Aliase für Sie erstellen, sodass beide e-Mail-Adressen zu Jennas Posteingang wechseln.
<br><br>  
  
Sie können bis zu 400 Aliase für einen Benutzer erstellen. Es fallen keine zusätzlichen Gebühren oder Lizenzen an.
  
> [!Tip]
> Wenn Sie möchten, dass mehrere Personen e-Mails verwalten, die an eine einzelne e-Mail-Adresse wie Info@NodPublishers.com oder Sales@NodPublishers.com gesendet werden, erstellen Sie ein freigegebenes Postfach. Weitere Informationen finden Sie unter [Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md).
  
## <a name="add-email-aliases-to-a-user"></a>Hinzufügen von E-Mail-Aliasen zu einem Benutzer
<a name="AddEmailPreview"> </a>

Sie benötigen [Administratorberechtigungen](../add-users/about-admin-roles.md) , um dies zu tun. 

  
::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie auf der Seite **aktive Benutzer** den Benutzer > **e-Mail-Aliase verwalten**aus. Diese Option wird nicht angezeigt, wenn der Person keine Lizenz zugewiesen ist. 
    
3. Wählen Sie **+ Alias hinzufügen** aus, und geben Sie einen neuen Alias für den Benutzer ein.   
    
    > [!Important] 
    > Wenn die Fehlermeldung "**ein Parameter kann nicht gefunden werden, der dem Parameternamen**e-Mail-e-Mail-Nachrichten entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis Sie den Mandanten eingerichtet haben, oder Ihre benutzerdefinierte Domäne, wenn Sie kürzlich einen hinzugefügt haben. Der Installationsvorgang kann bis zu 4 Stunden in Anspruch nehmen. Warten Sie eine Weile, damit der Setup-Prozesszeit zum fertig stellen hat, und versuchen Sie es dann erneut. Wenn das Problem weiterhin besteht, wenden Sie sich an den Support, um eine vollständige Synchronisierung für Sie durchführen zu können.
    
  
    > [!IMPORTANT]
    > Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln. 
  
    > [!TIP]
    > Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden. Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain). 
  
     
5. Wenn Sie fertig sind, wählen Sie **Save Changes**aus.
    
6. Warten Sie 24 Stunden, bis die neuen Aliase in Microsoft 365 aufgefüllt wurden.
    
    Der Benutzer verfügt nun über eine primäre Adresse und einen Alias. Beispielsweise werden alle e-Mails, die an die primäre Adresse von Eliza Hoffman, Eliza@NodPublishers.com, und Ihr Alias Sales@NodPublishers.com gesendet werden, in den Posteingang von Eliza verschoben.
    
  
7. **Wenn der Benutzer antwortet, ist die *von* -Adresse Ihr primärer e-Mail-Alias.** Angenommen, eine Nachricht wird an Sales@NodPublishers.com gesendet, und Sie kommt in Elizas Posteingang an. Wenn Eliza auf die Nachricht antwortet, wird Ihre primäre e-Mail-Adresse als Absender und nicht Sales@NodPublishers.com angezeigt. 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>. 
    
    
2. Wählen Sie auf der Seite **Aktive Benutzer** den Namen der Person aus, die Sie bearbeiten möchten.

3. Wählen Sie neben **Benutzernamen/e-Mail-Aliase**die Option **Bearbeiten**aus.

    > [!Important] 
    > Wenn die Fehlermeldung "**ein Parameter kann nicht gefunden werden, der dem Parameternamen**e-Mail-e-Mail-Nachrichten entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis Sie den Mandanten eingerichtet haben, oder Ihre benutzerdefinierte Domäne, wenn Sie kürzlich einen hinzugefügt haben. Der Installationsvorgang kann bis zu 4 Stunden in Anspruch nehmen. Warten Sie eine Weile, damit der Setup-Prozesszeit zum fertig stellen hat, und versuchen Sie es dann erneut. Wenn das Problem weiterhin besteht, wenden Sie sich an den Support, um eine vollständige Synchronisierung für Sie durchführen zu können.

4. Geben Sie in das Textfeld unter **Alias**den ersten Teil des neuen e-Mail-Alias ein. Wenn Sie Ihre eigene Domäne zu Microsoft 365 hinzugefügt haben, können Sie die Domäne für den neuen e-Mail-Alias mithilfe der Dropdownliste auswählen. Wählen Sie dann **Hinzufügen** aus.

    > [!IMPORTANT]
    > Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln. 
  
    > [!TIP]
    > Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden. Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain). 

5. Wenn Sie fertig sind, wählen Sie **Speichern**“ aus.

6. Warten Sie 24 Stunden, bis die neuen Aliase in Microsoft 365 aufgefüllt wurden. 
    
    Der Benutzer verfügt nun über eine primäre Adresse und einen Alias. Beispielsweise werden alle e-Mails, die an die primäre Adresse von Eliza Hoffman, Eliza@NodPublishers.com, und Ihr Alias Sales@NodPublishers.com gesendet werden, in den Posteingang von Eliza verschoben.
    
  
7. **Wenn der Benutzer antwortet, ist die *von* -Adresse Ihr primärer e-Mail-Alias.** Angenommen, eine Nachricht wird an Sales@NodPublishers.com gesendet, und Sie kommt in Elizas Posteingang an. Wenn Eliza auf die Nachricht antwortet, wird Ihre primäre e-Mail-Adresse als Absender und nicht Sales@NodPublishers.com angezeigt. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>. 

    
2. Wählen Sie auf der Seite **Aktive Benutzer** den Namen der Person aus, die Sie bearbeiten möchten.

3. Wählen Sie neben **Benutzernamen/e-Mail-Aliase**die Option **Bearbeiten**aus.

    > [!Important] 
    > Wenn die Fehlermeldung "**ein Parameter kann nicht gefunden werden, der dem Parameternamen**e-Mail-e-Mail-Nachrichten entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis Sie den Mandanten eingerichtet haben, oder Ihre benutzerdefinierte Domäne, wenn Sie kürzlich einen hinzugefügt haben. Der Installationsvorgang kann bis zu 4 Stunden in Anspruch nehmen. Warten Sie eine Weile, damit der Setup-Prozesszeit zum fertig stellen hat, und versuchen Sie es dann erneut. Wenn das Problem weiterhin besteht, wenden Sie sich an den Support, um eine vollständige Synchronisierung für Sie durchführen zu können.

4. Geben Sie in das Textfeld unter **Alias**den ersten Teil des neuen e-Mail-Alias ein. Wenn Sie Ihre eigene Domäne zu Microsoft 365 hinzugefügt haben, können Sie die Domäne für den neuen e-Mail-Alias mithilfe der Dropdownliste auswählen. Wählen Sie dann **Hinzufügen** aus.

    > [!IMPORTANT]
    > Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln. 
  
    > [!TIP]
    > Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden. Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain). 

5. Wenn Sie fertig sind, wählen Sie **Speichern**“ aus.

6. Warten Sie 24 Stunden, bis die neuen Aliase in Microsoft 365 aufgefüllt wurden. 
    
    Der Benutzer verfügt nun über eine primäre Adresse und einen Alias. Beispielsweise werden alle e-Mails, die an die primäre Adresse von Eliza Hoffman, Eliza@NodPublishers.com, und Ihr Alias Sales@NodPublishers.com gesendet werden, in den Posteingang von Eliza verschoben.
    
  
7. **Wenn der Benutzer antwortet, ist die *von* -Adresse Ihr primärer e-Mail-Alias.** Angenommen, eine Nachricht wird an Sales@NodPublishers.com gesendet, und Sie kommt in Elizas Posteingang an. Wenn Eliza auf die Nachricht antwortet, wird Ihre primäre e-Mail-Adresse als Absender und nicht Sales@NodPublishers.com angezeigt. 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>Haben Sie "ein Parameter kann nicht gefunden werden, der mit dem Parameternamen" Emails "übereinstimmt, erhalten?


Wenn die Fehlermeldung "**ein Parameter kann nicht gefunden werden, der dem Parameternamen**e-Mail-Nachrichten entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis Sie den Mandanten eingerichtet haben, oder Ihre benutzerdefinierte Domäne, wenn Sie kürzlich einen hinzugefügt haben. Der Installationsvorgang kann bis zu 4 Stunden in Anspruch nehmen. Warten Sie eine Weile, damit der Setup-Prozesszeit zum fertig stellen hat, und versuchen Sie es dann erneut. Wenn das Problem weiterhin besteht, wenden Sie sich an den Support, um eine vollständige Synchronisierung für Sie durchführen zu können.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>Haben Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft?


Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.
  
## <a name="related-articles"></a>Verwandte Artikel

[Senden von E-Mail über eine andere Adresse](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[Ändern eines Benutzernamens und einer E-Mail-Adresse](../add-users/change-a-user-name-and-email-address.md)
  

