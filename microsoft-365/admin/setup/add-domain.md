---
title: Hinzufügen einer Domäne zu Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Fügen Sie Ihre Domäne zu Office 365 im Microsoft 365 Admin Center hinzu, indem Sie einen DNS-Eintrag auf Ihrem DNS-Host hinzufügen. Der Setup-Assistent führt Sie durch den Prozess.
ms.openlocfilehash: 4170fd74ae734a6fda9e535c17086997b1db6f6b
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42243982"
---
# <a name="add-a-domain-to-office-365"></a>Hinzufügen einer Domäne zu Office 365

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
 *Zum Hinzufügen, ändern oder Entfernen von Domänen **müssen** Sie ein **globaler Administrator** eines [Geschäfts-oder Unternehmensplans](https://products.office.com/business/office)sein. Diese Änderungen wirken sich auf den gesamten Mandanten aus, *benutzerdefinierte Administratoren* oder *reguläre Benutzer* können diese Änderungen nicht vornehmen.*  

 Führen Sie die folgenden Schritte aus, um eine Domäne hinzuzufügen, einzurichten oder weiter einzurichten. 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end
::: moniker range="o365-germany"

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end
    
2. Wechseln Sie zur Seite " **Einstellungs** > **Domänen** ". 

3. Wählen Sie **Domäne hinzufügen**aus.
    
4. Geben Sie den Namen der Domäne ein, die Sie hinzufügen möchten, und wählen Sie dann **weiter**aus.
    
5. Wählen Sie aus, wie Sie überprüfen möchten, ob Sie der Besitzer der Domäne sind.
    
    1. Wenn Ihre Domäne bei GoDaddy oder 1&amp;1 registriert ist, wählen Sie**weiter** **Anmelden** > aus, und Office 365 [wird Ihre Einträge automatisch einrichten](../get-help-with-domains/domain-connect.md).
    
    2. Sie können auch eine E-Mail mit einem Prüfcode an den registrierten Kontakt für die Domäne senden lassen. Wenn Sie die zu erfassenden e-Mails nicht erkennen oder Zugriff auf diese haben, können Sie die dritte Option verwenden.
    
    3. Sie können einen TXT-Eintrag zur Überprüfung Ihrer Domäne verwenden. Wählen Sie diese Option aus, und klicken Sie auf **weiter** , um Anweisungen zum Hinzufügen dieses DNS-Eintrags zur Website der Registrierungsstelle anzuzeigen. Dies kann bis zu 30 Minuten dauern, um zu überprüfen, nachdem Sie den Eintrag hinzugefügt haben. 
    
6. Wählen Sie aus, wie Sie die DNS-Änderungen vornehmen möchten, die für Office zur Verwendung Ihrer Domäne erforderlich sind.
    
    1. Wählen Sie **die Option DNS-Einträge hinzufügen aus** , wenn Office Ihre DNS automatisch konfigurieren soll. 
    
  
    2. Wählen Sie **Ich werde die DNS-Einträge selbst hinzufügen** , wenn Sie nur bestimmte Office 365 Dienste an Ihre Domäne anfügen möchten oder wenn Sie diese für jetzt überspringen möchten und dies später tun möchten. **Wählen Sie diese Option aus, wenn Sie genau wissen, was Sie gerade tun.**
    
7. Wenn Sie *selbst DNS-Einträge hinzugefügt* haben, wählen Sie **weiter** aus, und es wird eine Seite mit allen Datensätzen angezeigt, die Sie Ihrer Registrierungsstellen Website hinzufügen müssen, um Ihre Domäne einzurichten. 
    
  
  
    Wenn das Portal Ihre Registrierungsstelle nicht erkennt, können Sie [diesen allgemeinen Anleitungen folgen](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).
    
    Suchen Sie in der Liste der [hostspezifischen Anweisungen](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) Ihren Host, und führen Sie die Schritte zum Hinzufügen aller benötigten Datensätze aus. 
    
    Wenn Sie den DNS-Hostinganbieter oder die Domänenregistrierungsstelle für Ihre Domäne nicht kennen, lesen Sie [Finden Ihrer Domänenregistrierungsstelle oder Ihres DNS-Hostinganbieters](../get-help-with-domains/find-your-domain-registrar.md).
    
    Wenn Sie später warten möchten, führen Sie einen Bildlauf nach unten durch, und wählen Sie **diesen Schritt überspringen**aus.
    
8. Wählen Sie **Fertig stellen** aus – Sie sind fertig! 

## <a name="related-articles"></a>Verwandte Artikel

[Häufig gestellte Fragen zu Domänen](domains-faq.md)

[Was ist eine Domäne?](../get-help-with-domains/what-is-a-domain.md)

[Erwerben eines Domänennamens in Office 365](../get-help-with-domains/buy-a-domain-name.md)

[Einrichten Ihrer Domäne (hostspezifische Anweisungen)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[Abrufen von Hilfe zu Office 365 Domänen](../get-help-with-domains/get-help-with-domains.md)
