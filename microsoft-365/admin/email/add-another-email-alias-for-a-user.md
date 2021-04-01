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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Erfahren Sie, wie Sie mehr als eine E-Mail-Adresse, genannt E-Mail-Alias, mit Ihrem Microsoft 365 Business-Konto verknüpfen können. '
ms.openlocfilehash: a44271cdbf52136e61702697a960cc3cbcd8119d
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471001"
---
# <a name="add-another-email-alias-for-a-user"></a>Hinzufügen eines weiteren E-Mail-Alias für einen Benutzer
  
Dieser Artikel ist Microsoft 365-Administratoren bestimmt, die über Business-Abonnements verfügen. Er gilt nicht für private Benutzer.
  
Eine primäre E-Mail-Adresse in Microsoft 365 ist normalerweise die E-Mail-Adresse, die einem Benutzer bei der Erstellung seines Kontos zugewiesen wurde. Wenn der Benutzer eine E-Mail an eine andere Person senden, wird in E-Mail-Apps in der Regel seine primäre E-Mail-Adresse im Feld *Von* angezeigt. Sie können auch mehrere E-Mail-Adressen haben, die ihrem Microsoft 365 Business-Konto zugeordnet sind. Diese zusätzlichen Adressen werden als „Aliase“ bezeichnet. 
  
Angenommen, Jenna hat die E-Mail-Adresse „jenna@contosoco.com“, möchte aber auch E-Mails unter „jen@contosoco.com“ empfangen, weil einige Leute sie mit diesem Namen ansprechen. Sie können Aliase für sie erstellen, sodass beide E-Mail-Adressen an Jennas Posteingang gehen.
<br><br>  
  
Sie können bis zu 400 Aliase für einen Benutzer erstellen. Es fallen keine zusätzlichen Gebühren oder Lizenzen an.
  
> [!Tip]
> Wenn Sie möchten, dass mehrere Personen E-Mails verwalten können, die an eine einzelne E-Mail-Adresse wie „info@NodPublishers.com“ oder „vertrieb@NodPublishers.com“ gesendet wurden, erstellen Sie ein freigegebenes Postfach. Weitere Informationen finden Sie unter [Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md).
  
## <a name="add-email-aliases-to-a-user"></a>Hinzufügen von E-Mail-Aliasen zu einem Benutzer
<a name="AddEmailPreview"> </a>

Sie benötigen [Administrator-Berechtigungen](../add-users/about-admin-roles.md) zum Ausführen der folgenden Schritte. 

  
::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie auf der Seite **Aktive Benutzer** den Benutzer und dann **E-Mail-Aliase bearbeiten** aus. Diese Option wird nicht angezeigt, wenn der Person keine Lizenz zugewiesen wurde. 
    
3. Wählen Sie **+ Alias hinzufügen** aus, und geben Sie einen neuen Alias für den Benutzer ein.   
    
    > [!Important] 
    > Wenn die Fehlermeldung „**Es wurde kein Parameter gefunden, der dem Parametername 'EmailAddresses' entspricht**“ angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis das Einrichten Ihres Mandanten oder Ihrer benutzerdefinierten Domäne (falls Sie kürzlich eine hinzugefügt haben) abgeschlossen ist. Der Setupvorgang kann bis zu 4 Stunden dauern. Warten Sie eine Zeitlang, damit dieser Vorgang abgeschlossen werden kann. Versuchen Sie es dann erneut. Wenn das Problem weiterhin besteht, rufen Sie den Support an, der eine vollständige Synchronisierung für Sie durchführt.
    
  
    > [!IMPORTANT]
    > Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln. 
  
    > [!TIP]
    > Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden. Informationen dazu, wie Sie der Liste einen weiteren Domänenname hinzufügen, finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365](../setup/add-domain.md). 
  
     
5. Wenn Sie fertig sind, wählen Sie **Änderungen speichern** aus.
    
6. Warten Sie 24 Stunden, bis sich die neuen Aliase durch Microsoft 365 verbreitet haben.
    
    Der Benutzer hat nun eine primäre Adresse und einen Alias. Alle E-Mails, die an Jana Hoffmanns primäre E-Mail-Adresse („Jana@NodPublishers.com“) und ihren Alias („Vertrieb@NodPublishers.com“) gesendet wurden, werden jetzt in Janas Posteingang zugestellt.
    
  
7. **Wenn der Benutzer antwortet, ist die *Von*-Adresse der primäre E-Mail-Alias.** Angenommen, eine Nachricht wurde an „Vertrieb@NodPublishers.com“ gesendet und ist dann in Janas Posteingang angekommen. Wenn Jana auf die Nachricht antwortet, wird ihre primäre E-Mail-Adresse als Absender angezeigt und nicht „Vertrieb@NodPublishers.com“. 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>. 
    
    
2. Wählen Sie auf der Seite **Aktive Benutzer** den Namen der Person aus, die Sie bearbeiten möchten.

3. Wählen Sie neben **Benutzername / E-Mail-Aliase** die Option **Bearbeiten** aus.

    > [!Important] 
    > Wenn die Fehlermeldung „**Es wurde kein Parameter gefunden, der dem Parametername 'EmailAddresses' entspricht**“ angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis das Einrichten Ihres Mandanten oder Ihrer benutzerdefinierten Domäne (falls Sie kürzlich eine hinzugefügt haben) abgeschlossen ist. Der Setupvorgang kann bis zu 4 Stunden dauern. Warten Sie eine Zeitlang, damit dieser Vorgang abgeschlossen werden kann. Versuchen Sie es dann erneut. Wenn das Problem weiterhin besteht, rufen Sie den Support an, der eine vollständige Synchronisierung für Sie durchführt.

4. Geben Sie im Textfeld unter **Alias** den ersten Teil der neuen E-Mail-Adresse ein. Wenn Sie Ihre eigene Domäne zu Microsoft 365 hinzugefügt haben, können Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste auswählen. Wählen Sie dann **Hinzufügen** aus.

    > [!IMPORTANT]
    > Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln. 
  
    > [!TIP]
    > Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden. Informationen dazu, wie Sie der Liste einen weiteren Domänenname hinzufügen, finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365](../setup/add-domain.md). 

5. Wenn Sie fertig sind, wählen Sie **Speichern** aus.

6. Warten Sie 24 Stunden, bis sich die neuen Aliase durch Microsoft 365 verbreitet haben. 
    
    Der Benutzer hat nun eine primäre Adresse und einen Alias. Alle E-Mails, die an Jana Hoffmanns primäre E-Mail-Adresse („Jana@NodPublishers.com“) und ihren Alias („Vertrieb@NodPublishers.com“) gesendet wurden, werden jetzt in Janas Posteingang zugestellt.
    
  
7. **Wenn der Benutzer antwortet, ist die *Von*-Adresse der primäre E-Mail-Alias.** Angenommen, eine Nachricht wurde an „Vertrieb@NodPublishers.com“ gesendet und ist dann in Janas Posteingang angekommen. Wenn Jana auf die Nachricht antwortet, wird ihre primäre E-Mail-Adresse als Absender angezeigt und nicht „Vertrieb@NodPublishers.com“. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>. 

    
2. Wählen Sie auf der Seite **Aktive Benutzer** den Namen der Person aus, die Sie bearbeiten möchten.

3. Wählen Sie neben **Benutzername / E-Mail-Aliase** die Option **Bearbeiten** aus.

    > [!Important] 
    > Wenn die Fehlermeldung „**Es wurde kein Parameter gefunden, der dem Parametername 'EmailAddresses' entspricht**“ angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis das Einrichten Ihres Mandanten oder Ihrer benutzerdefinierten Domäne (falls Sie kürzlich eine hinzugefügt haben) abgeschlossen ist. Der Setupvorgang kann bis zu 4 Stunden dauern. Warten Sie eine Zeitlang, damit dieser Vorgang abgeschlossen werden kann. Versuchen Sie es dann erneut. Wenn das Problem weiterhin besteht, rufen Sie den Support an, der eine vollständige Synchronisierung für Sie durchführt.

4. Geben Sie im Textfeld unter **Alias** den ersten Teil der neuen E-Mail-Adresse ein. Wenn Sie Ihre eigene Domäne zu Microsoft 365 hinzugefügt haben, können Sie die Domäne für den neuen E-Mail-Alias über die Dropdownliste auswählen. Wählen Sie dann **Hinzufügen** aus.

    > [!IMPORTANT]
    > Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln. 
  
    > [!TIP]
    > Der E-Mail-Alias muss mit einer Domäne aus der Dropdownliste enden. Informationen dazu, wie Sie der Liste einen weiteren Domänenname hinzufügen, finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365](../setup/add-domain.md). 

5. Wenn Sie fertig sind, wählen Sie **Speichern** aus.

6. Warten Sie 24 Stunden, bis sich die neuen Aliase durch Microsoft 365 verbreitet haben. 
    
    Der Benutzer hat nun eine primäre Adresse und einen Alias. Alle E-Mails, die an Jana Hoffmanns primäre E-Mail-Adresse („Jana@NodPublishers.com“) und ihren Alias („Vertrieb@NodPublishers.com“) gesendet wurden, werden jetzt in Janas Posteingang zugestellt.
    
  
7. **Wenn der Benutzer antwortet, ist die *Von*-Adresse der primäre E-Mail-Alias.** Angenommen, eine Nachricht wurde an „Vertrieb@NodPublishers.com“ gesendet und ist dann in Janas Posteingang angekommen. Wenn Jana auf die Nachricht antwortet, wird ihre primäre E-Mail-Adresse als Absender angezeigt und nicht „Vertrieb@NodPublishers.com“. 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>Wurde die Fehlermeldung „Es wurde kein Parameter gefunden, der dem Parameternamen 'EmailAddresses' entspricht“ angezeigt?


Wenn die Fehlermeldung "**Es wurde kein Parameter gefunden, der dem Parametername 'EmailAddresses' entspricht**" angezeigt wird, bedeutet dies, dass es etwas länger dauert, bis das Einrichten Ihres Mandanten oder Ihrer benutzerdefinierten Domäne (falls Sie kürzlich eine hinzugefügt haben) abgeschlossen ist. Der Setupvorgang kann bis zu 4 Stunden dauern. Warten Sie eine Zeitlang, damit dieser Vorgang abgeschlossen werden kann. Versuchen Sie es dann erneut. Wenn das Problem weiterhin besteht, rufen Sie den Support an, der eine vollständige Synchronisierung für Sie durchführt.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>Haben Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft?


Wenn Sie Ihr Abonnement bei GoDaddy oder einem anderen Partner gekauft haben und den neuen Alias als primäre E-Mail-Adresse festlegen möchten, müssen Sie zur Verwaltungskonsole "GoDaddy/partner" wechseln.
  
## <a name="related-articles"></a>Verwandte Artikel

[Senden von E-Mail über eine andere Adresse](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[Ändern eines Benutzernamens und einer E-Mail-Adresse](../add-users/change-a-user-name-and-email-address.md)
