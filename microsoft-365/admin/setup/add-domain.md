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
description: Fügen Sie Ihre Domäne zu Office 365 im Microsoft 365-Verwaltungszentrum hinzu, indem Sie einen DNS-Eintrag bei Ihrem DNS-Host hinzufügen. Der Setup-Assistent führt Sie nun durch den Vorgang.
ms.openlocfilehash: a6ef611ec210bbfb2299b6d41edb7d6410d50073
ms.sourcegitcommit: 8edad75338cf74712ca1ab5d6631b9b52ff54410
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2020
ms.locfileid: "43116014"
---
# <a name="add-a-domain-to-office-365"></a>Hinzufügen einer Domäne zu Office 365

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
 *Um Domänen hinzuzufügen, zu ändern oder zu entfernen, **müssen** Sie ein **globaler Administrator** eines [Geschäfts- oder Unternehmensplans](https://products.office.com/business/office) sein. Diese Änderungen betreffen den gesamten Mandanten. *Benutzerdefinierte Administratoren* oder *reguläre Benutzer* können diese Änderungen nicht vornehmen.*  

 Führen Sie die folgenden Schritte aus, um eine Domäne hinzuzufügen, einzurichten oder die Einrichtung einer Domäne fortzusetzen. 

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
    
2. Wechseln Sie zur Seite **Setup** > **Domänen** . 

3. Wählen Sie **Domäne hinzufügen** aus.
    
4. Geben Sie den Namen der Domäne ein, die Sie hinzufügen möchten, und wählen Sie **Weiter** aus.
    
5. Wählen Sie aus, wie Sie überprüfen möchten, ob Sie die Domäne besitzen.
    
    1. Wenn Ihre Domäne bei GoDaddy oder 1&amp;1 registriert ist, wählen Sie **Anmelden** > **Weiter** aus. Office 365 [richtet Ihre Einträge dann automatisch ein](../get-help-with-domains/domain-connect.md).
    
    2. Sie können auch eine E-Mail mit einem Prüfcode an den registrierten Kontakt für die Domäne senden lassen. Wenn Sie diese E-Mail nicht erkennen oder keinen Zugriff darauf haben, können Sie die dritte Option verwenden.
    
    3. Sie können einen TXT-Eintrag zur Überprüfung Ihrer Domäne verwenden. Wählen Sie dies und dann **Weiter** aus, um Anleitungen dazu anzuzeigen, wie Sie diesen DNS-Eintrag zur Website Ihrer Registrierungsstelle hinzufügen. Nachdem Sie den Eintrag hinzugefügt haben, kann die Überprüfung bis zu 30 Minuten dauern. 
    
6. Wählen Sie aus, wie Sie die erforderlichen DNS-Änderungen vornehmen möchten, damit Office Ihre Domäne verwenden kann.
    
    1. Wählen Sie **DNS-Einträge für mich hinzufügen** aus, wenn Office Ihr DNS automatisch konfigurieren soll. 
    
  
    2. Wählen Sie **Ich füge die DNS-Einträge selbst hinzu** aus, wenn Sie nur bestimmte Office 365-Dienste an Ihre Domäne anfügen oder diesen Schritt zunächst überspringen und erst zu einem späteren Zeitpunkt ausführen möchten. **Wählen Sie diese Option aus, wenn Sie genau wissen, was Sie tun.**
    
7. Wenn Sie ausgewählt haben, dass Sie *DNS-Einträge selbst hinzufügen* möchten, wählen Sie **Weiter** aus. Anschließend wird eine Seite mit allen Einträgen angezeigt, die Sie zur Website Ihrer Registrierungsstelle hinzufügen müssen, um Ihre Domäne einzurichten. 
    
  
  
    Wenn das Portal Ihre Registrierungsstelle nicht erkennt, können Sie [diesen allgemeinen Anleitungen folgen](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).
    
    Suchen Sie in der Liste der [hostspezifischen Anweisungen](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) Ihren Host, und führen Sie die Schritte zum Hinzufügen aller benötigten Datensätze aus. 
    
    Wenn Sie den DNS-Hostinganbieter oder die Domänenregistrierungsstelle für Ihre Domäne nicht kennen, lesen Sie [Finden Ihrer Domänenregistrierungsstelle oder Ihres DNS-Hostinganbieters](../get-help-with-domains/find-your-domain-registrar.md).
    
    Wenn Sie auf einen späteren Zeitpunkt warten möchten, scrollen Sie bis ans Ende, und wählen Sie **Diesen Schritt überspringen** aus.
    
8. Wählen Sie **Fertig stellen** aus. Sie haben es geschafft! 

## <a name="related-articles"></a>Verwandte Artikel

[Häufig gestellte Fragen zu Domänen](domains-faq.md)

[Was ist eine Domäne?](../get-help-with-domains/what-is-a-domain.md)

[Erwerben eines Domänennamens in Office 365](../get-help-with-domains/buy-a-domain-name.md)

[Einrichten Ihrer Domäne (hostspezifische Anweisungen)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[Hilfe zu Office 365-Domänen erhalten](../get-help-with-domains/get-help-with-domains.md)
