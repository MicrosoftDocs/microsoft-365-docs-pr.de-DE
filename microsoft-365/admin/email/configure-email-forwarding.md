---
title: Konfigurieren der E-Mail-Weiterleitung
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Einrichten der e-Mail-Weiterleitung an ein oder mehrere e-Mail-Konten mit Office365.
ms.openlocfilehash: f6c177ba37cf2b8ce3966732adbe8428d9b6179e
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780253"
---
# <a name="configure-email-forwarding"></a>Konfigurieren der E-Mail-Weiterleitung

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
Als Administrator einer Organisation haben Sie möglicherweise Unternehmens Anforderungen, um die e-Mail-Weiterleitung für das Postfach eines Benutzers einzurichten. Mit einer E-Mail-Weiterleitung können Sie E-Mails, die an das Postfach eines Benutzers gesendet wurden, an das Postfach eines anderen Benutzers innerhalb oder außerhalb Ihrer Organisation weiterleiten.

  
## <a name="configure-email-forwarding"></a>Konfigurieren der E-Mail-Weiterleitung

 Beachten Sie vor dem Einrichten der e-Mail-Weiterleitung Folgendes: 

- Nachdem Sie die e-Mail-Weiterleitung eingerichtet haben, sind nur **neue** e-Mails, die an das Postfach " *von* " gesendet werden, in. 
    
- Für die e-Mail-Weiterleitung muss das *von* -Konto über eine Lizenz verfügen. Wenn Sie die e-Mail-Weiterleitung einrichten, da der Benutzer Ihre Organisation verlassen hat, besteht eine andere Option darin, [Ihr Postfach in ein freigegebenes Postfach zu konvertieren](convert-user-mailbox-to-shared-mailbox.md). Auf diese Weise können mehrere Personen darauf zugreifen. Ein freigegebenes Postfach darf jedoch nicht mehr als 50 GB betragen. 
    
Sie müssen ein Exchange-Administrator oder globaler Administrator in Microsoft 365 sein, um diese Schritte ausführen zu können. Weitere Informationen finden Sie im Thema [zu Administratorrollen](../add-users/about-admin-roles.md).

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
    
2. Wählen Sie den Namen des Benutzers aus, dessen e-Mail weitergeleitet werden soll, um die Eigenschaftenseite zu öffnen. 
 
3. Wählen Sie auf der Registerkarte **e-Mail** die Option **e-Mail-Weiterleitung verwalten**aus. 
  
4. Wählen Sie auf der Seite e-Mail-Weiterleitung **alle an dieses Postfach gesendeten e-Mails weiterleiten**aus, geben Sie die Weiterleitungsadresse ein, und wählen Sie aus, ob eine Kopie der weitergeleiteten e-Mails aufbewahrt werden soll. Wenn diese Option nicht angezeigt wird, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist. Wählen Sie **Änderungen speichern** aus.
    
    Um **an mehrere e-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Regel in Outlook für die Weiterleitung an die Adressen einzurichten. Weitere Informationen finden Sie unter [Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746). 
    
     Oder erstellen Sie im Admin Center [eine Verteilergruppe](../setup/create-distribution-lists.md), [fügen Sie die Adressen hinzu](add-user-or-contact-to-distribution-list.md), und legen Sie dann die Weiterleitung so fest, dass Sie mithilfe der Anweisungen in diesem Artikel auf die Verteilerliste verweist.
    
5. Löschen Sie nicht das Konto der e-Mail-Adresse des Benutzers, die Sie weiterleiten, oder entfernen Sie die Lizenz!  Wenn Sie dies tun, wird die e-Mail-Weiterleitung angehalten. 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>. 
    
2. Wählen Sie den Namen des Benutzers aus, dessen e-Mail weitergeleitet werden soll, um die Eigenschaftenseite zu öffnen. 

3. Erweitern Sie **e-Mail-Einstellungen**, und wählen Sie dann im Abschnitt **e-Mail-Weiterleitung** die Option **Bearbeiten**aus.

4. Legen Sie auf der Seite e-Mail-Weiterleitung die Umschaltfläche **auf**ein, geben Sie die Weiterleitungsadresse ein, und wählen Sie aus, ob Sie eine Kopie der weitergeleiteten e-Mails behalten möchten. Wenn diese Option nicht angezeigt wird, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist. Wählen Sie **Speichern**.
    
    Um **an mehrere e-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Regel in Outlook für die Weiterleitung an die Adressen einzurichten. Weitere Informationen finden Sie unter [Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746). 
    
     Oder erstellen Sie im Admin Center [eine Verteilergruppe](../setup/create-distribution-lists.md), [fügen Sie die Adressen hinzu](add-user-or-contact-to-distribution-list.md), und legen Sie dann die Weiterleitung so fest, dass Sie mithilfe der Anweisungen in diesem Artikel auf die Verteilerliste verweist.
    
5. Löschen Sie nicht das Konto der e-Mail-Adresse des Benutzers, die Sie weiterleiten, oder entfernen Sie die Lizenz!  Wenn Sie dies tun, wird die e-Mail-Weiterleitung angehalten.    

::: moniker-end

::: moniker range="o365-21vianet"

 1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>. 
    
2. Wählen Sie den Namen des Benutzers aus, dessen e-Mail weitergeleitet werden soll, um die Eigenschaftenseite zu öffnen. 

3. Erweitern Sie **e-Mail-Einstellungen**, und wählen Sie dann im Abschnitt **e-Mail-Weiterleitung** die Option **Bearbeiten**aus.

4. Legen Sie auf der Seite e-Mail-Weiterleitung die Umschaltfläche **auf**ein, geben Sie die Weiterleitungsadresse ein, und wählen Sie aus, ob Sie eine Kopie der weitergeleiteten e-Mails behalten möchten. Wenn diese Option nicht angezeigt wird, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist. Wählen Sie **Speichern**.
    
    Um **an mehrere e-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Regel in Outlook für die Weiterleitung an die Adressen einzurichten. Weitere Informationen finden Sie unter [Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746). 
    
     Oder erstellen Sie im Admin Center [eine Verteilergruppe](../setup/create-distribution-lists.md), [fügen Sie die Adressen hinzu](add-user-or-contact-to-distribution-list.md), und legen Sie dann die Weiterleitung so fest, dass Sie mithilfe der Anweisungen in diesem Artikel auf die Verteilerliste verweist.
    
5. Löschen Sie nicht das Konto der e-Mail-Adresse des Benutzers, die Sie weiterleiten, oder entfernen Sie die Lizenz!  Wenn Sie dies tun, wird die e-Mail-Weiterleitung angehalten. 

::: moniker-end 
