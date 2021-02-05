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
description: 'Erfahren Sie, wie Sie ihrem Microsoft 365 Business-Konto mehr als eine E-Mail-Adresse, den so genannten E-Mail-Alias, zugeordnet haben können. '
ms.openlocfilehash: afb576a0499577b910fe3ed14eff75ae0a52b394
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114033"
---
# <a name="add-another-email-alias-for-a-user"></a>Hinzufügen eines weiteren E-Mail-Alias für einen Benutzer

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end
  
Dieser Artikel ist für Microsoft 365-Administratoren vorgesehen, die über Geschäftsabonnements verfügen. Er gilt nicht für private Benutzer.
  
Eine primäre E-Mail-Adresse in Microsoft 365 ist in der Regel die E-Mail-Adresse, die einem Benutzer zugewiesen wurde, als sein Konto erstellt wurde. Wenn der Benutzer eine E-Mail an eine andere Person sendet, wird seine primäre E-Mail-Adresse in E-Mail-Apps in der Regel im Feld  *Von*  angezeigt. Sie können ihrem Microsoft 365 Business-Konto auch mehrere E-Mail-Adressen zugeordnet haben. Diese zusätzlichen Adressen werden als "Aliase" bezeichnet. 
  
Nehmen wir beispielsweise an, dass Jenna die E-Mail-Adresse jenna@contosoco.com hat, aber sie möchte auch E-Mails bei jen@contosoco.com empfangen, da einige Personen mit diesem Namen auf sie verweisen. Sie können Aliase für sie erstellen, damit beide E-Mail-Adressen in Jennas Posteingang gehen.
<br><br>  
  
Sie können bis zu 400 Aliase für einen Benutzer erstellen. Es fallen keine zusätzlichen Gebühren oder Lizenzen an.
  
> [!Tip]
> Wenn Sie möchten, dass mehrere Personen E-Mails verwalten, die an eine einzelne E-Mail-Adresse wie info@NodPublishers.com oder sales@NodPublishers.com gesendet werden, erstellen Sie ein freigegebenes Postfach. Weitere Informationen finden Sie unter [Erstellen eines freigegebenen Postfachs.](create-a-shared-mailbox.md)
  
## <a name="add-email-aliases-to-a-user"></a>Hinzufügen von E-Mail-Aliasen zu einem Benutzer
<a name="AddEmailPreview"> </a>

Dazu müssen Sie [über Administratorberechtigungen](../add-users/about-admin-roles.md) verfügen. 

  
::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie **auf der Seite "Aktive** Benutzer" den Benutzer aus, > **E-Mail-Aliase verwalten.** Diese Option wird nicht angezeigt, wenn der Person keine Lizenz zugewiesen ist. 
    
3. Wählen **Sie +Hinzufügen eines Alias** aus, und geben Sie einen neuen Alias für den Benutzer ein.   
    
    > [!Important] 
    > Wenn die Fehlermeldung "Ein Parameter wurde nicht gefunden, der dem Parameternamen **'EmailAddresses'** entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, die Einrichtung Ihres Mandanten oder Ihre benutzerdefinierte Domäne fertig zu stellen, wenn Sie kürzlich einen hinzugefügt haben. Der Einrichtungsvorgang kann bis zu 4 Stunden dauern. Warten Sie eine Weile, bis der Einrichtungsprozess abgeschlossen ist, und versuchen Sie es dann erneut. Wenn das Problem weiterhin besteht, rufen Sie den Support an, und er wird eine vollständige Synchronisierung für Sie tun.
    
  
    > [!IMPORTANT]
    > Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln. 
  
    > [!TIP]
    > Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden. Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter ["Hinzufügen einer Domäne zu Microsoft 365".](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) 
  
     
5. Wenn Sie fertig sind, wählen Sie **"Änderungen speichern" aus.**
    
6. Warten Sie 24 Stunden, bis die neuen Aliase in Microsoft 365 auffüllen.
    
    Der Benutzer hat jetzt eine primäre Adresse und einen Alias. Beispielsweise gehen alle E-Mails, die an die primäre Adresse von Eliza Isaman, Eliza@NodPublishers.com, und ihr Alias Sales@NodPublishers.com an Elizas Posteingang gesendet werden.
    
  
7. **Wenn der Benutzer antwortet, ist die *"Von"-Adresse*  ihr primärer E-Mail-Alias.** Nehmen wir beispielsweise an, dass eine Nachricht an Sales@NodPublishers.com gesendet wird und im Posteingang von Eliza eintrifft. Wenn Eliza auf die Nachricht antwortet, wird ihre primäre E-Mail-Adresse als Absender und nicht als Sales@NodPublishers.com. 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>. 
    
    
2. Wählen Sie auf der Seite **Aktive Benutzer** den Namen der Person aus, die Sie bearbeiten möchten.

3. Wählen Sie neben **"Benutzername/E-Mail-Aliase"** die Option **"Bearbeiten" aus.**

    > [!Important] 
    > Wenn die Fehlermeldung "Ein Parameter wurde nicht gefunden, der dem Parameternamen **'EmailAddresses'** entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, die Einrichtung Ihres Mandanten oder Ihre benutzerdefinierte Domäne fertig zu stellen, wenn Sie kürzlich einen hinzugefügt haben. Der Einrichtungsvorgang kann bis zu 4 Stunden dauern. Warten Sie eine Weile, bis der Einrichtungsprozess abgeschlossen ist, und versuchen Sie es dann erneut. Wenn das Problem weiterhin besteht, rufen Sie den Support an, und er wird eine vollständige Synchronisierung für Sie tun.

4. Geben Sie im Textfeld unter **Alias** den ersten Teil des neuen E-Mail-Alias ein. Wenn Sie Ihre eigene Domäne zu Microsoft 365 hinzugefügt haben, können Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste auswählen. Wählen Sie dann **Hinzufügen** aus.

    > [!IMPORTANT]
    > Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln. 
  
    > [!TIP]
    > Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden. Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter ["Hinzufügen einer Domäne zu Microsoft 365".](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) 

5. Wenn Sie fertig sind, wählen Sie **Speichern**“ aus.

6. Warten Sie 24 Stunden, bis die neuen Aliase in Microsoft 365 auffüllen. 
    
    Der Benutzer hat jetzt eine primäre Adresse und einen Alias. Beispielsweise gehen alle E-Mails, die an die primäre Adresse von Eliza Isaman, Eliza@NodPublishers.com, und ihr Alias Sales@NodPublishers.com an Elizas Posteingang gesendet werden.
    
  
7. **Wenn der Benutzer antwortet, ist die *"Von"-Adresse*  ihr primärer E-Mail-Alias.** Nehmen wir beispielsweise an, dass eine Nachricht an Sales@NodPublishers.com gesendet wird und im Posteingang von Eliza eintrifft. Wenn Eliza auf die Nachricht antwortet, wird ihre primäre E-Mail-Adresse als Absender und nicht als Sales@NodPublishers.com. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>. 

    
2. Wählen Sie auf der Seite **Aktive Benutzer** den Namen der Person aus, die Sie bearbeiten möchten.

3. Wählen Sie neben **"Benutzername/E-Mail-Aliase"** die Option **"Bearbeiten" aus.**

    > [!Important] 
    > Wenn die Fehlermeldung "Ein Parameter wurde nicht gefunden, der dem Parameternamen **'EmailAddresses'** entspricht" angezeigt wird, bedeutet dies, dass es etwas länger dauert, die Einrichtung Ihres Mandanten oder Ihre benutzerdefinierte Domäne fertig zu stellen, wenn Sie kürzlich einen hinzugefügt haben. Der Einrichtungsvorgang kann bis zu 4 Stunden dauern. Warten Sie eine Weile, bis der Einrichtungsprozess abgeschlossen ist, und versuchen Sie es dann erneut. Wenn das Problem weiterhin besteht, rufen Sie den Support an, und er wird eine vollständige Synchronisierung für Sie tun.

4. Geben Sie im Textfeld unter **Alias** den ersten Teil des neuen E-Mail-Alias ein. Wenn Sie Ihre eigene Domäne zu Microsoft 365 hinzugefügt haben, können Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste auswählen. Wählen Sie dann **Hinzufügen** aus.

    > [!IMPORTANT]
    > Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln. 
  
    > [!TIP]
    > Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden. Informationen zum Hinzufügen eines weiteren Domänennamens zur Liste finden Sie unter ["Hinzufügen einer Domäne zu Microsoft 365".](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) 

5. Wenn Sie fertig sind, wählen Sie **Speichern**“ aus.

6. Warten Sie 24 Stunden, bis die neuen Aliase in Microsoft 365 auffüllen. 
    
    Der Benutzer hat jetzt eine primäre Adresse und einen Alias. Beispielsweise gehen alle E-Mails, die an die primäre Adresse von Eliza Isaman, Eliza@NodPublishers.com, und ihr Alias Sales@NodPublishers.com an Elizas Posteingang gesendet werden.
    
  
7. **Wenn der Benutzer antwortet, ist die *"Von"-Adresse*  ihr primärer E-Mail-Alias.** Nehmen wir beispielsweise an, dass eine Nachricht an Sales@NodPublishers.com gesendet wird und im Posteingang von Eliza eintrifft. Wenn Eliza auf die Nachricht antwortet, wird ihre primäre E-Mail-Adresse als Absender und nicht als Sales@NodPublishers.com. 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>Haben Sie "Ein Parameter, der dem Parameternamen "EmailAddresses" entspricht, nicht gefunden?


Wenn die Fehlermeldung "Ein Parameter, der dem Parameternamen **"EmailAddresses"** entspricht, nicht gefunden wird, bedeutet dies, dass es etwas länger dauert, die Einrichtung Ihres Mandanten oder Ihre benutzerdefinierte Domäne fertig zu stellen, wenn Sie kürzlich einen hinzugefügt haben. Der Einrichtungsvorgang kann bis zu 4 Stunden dauern. Warten Sie eine Weile, bis der Einrichtungsprozess abgeschlossen ist, und versuchen Sie es dann erneut. Wenn das Problem weiterhin besteht, rufen Sie den Support an, und er wird eine vollständige Synchronisierung für Sie tun.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>Haben Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft?


Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.
  
## <a name="related-articles"></a>Verwandte Artikel

[Senden von E-Mail über eine andere Adresse](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[Ändern eines Benutzernamens und einer E-Mail-Adresse](../add-users/change-a-user-name-and-email-address.md)
  

