---
title: Hinzufügen einer Domäne zu Microsoft 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Fügen Sie Ihre Domäne zu Microsoft 365 im Microsoft 365 Admin Center hinzu, indem Sie einen DNS-Eintrag auf Ihrem DNS-Host hinzufügen. Der Setup-Assistent führt Sie nun durch den Vorgang.
ms.openlocfilehash: 3a4cd31a37eb01570f58e9cdb83940640768a273
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644615"
---
# <a name="add-a-domain-to-microsoft-365"></a>Hinzufügen einer Domäne zu Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

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
    
2. Wechseln Sie zur Seite **Einstellungen** > **Domänen**. 

3. Wählen Sie **Domäne hinzufügen** aus.
    
4. Geben Sie den Namen der Domäne ein, die Sie hinzufügen möchten, und wählen Sie **Weiter** aus.
    
5. Wählen Sie aus, wie Sie überprüfen möchten, ob Sie die Domäne besitzen.
    
    1. Wenn Ihre Domänenregistrierungsstelle die [Domäne Connect](#domain-connect-registrars-integrating-with-microsoft-365)verwendet, [richtet Microsoft Ihre Datensätze automatisch](../get-help-with-domains/domain-connect.md) ein, indem Sie sich bei Ihrer Registrierungsstelle anmelden und die Verbindung mit Microsoft 365 bestätigen. Sie werden an das Admin Center zurückgegeben, und Microsoft prüft dann automatisch Ihre Domäne.
    2. Sie können einen TXT-Eintrag zur Überprüfung Ihrer Domäne verwenden. Wählen Sie dies und dann **Weiter** aus, um Anleitungen dazu anzuzeigen, wie Sie diesen DNS-Eintrag zur Website Ihrer Registrierungsstelle hinzufügen. Nachdem Sie den Eintrag hinzugefügt haben, kann die Überprüfung bis zu 30 Minuten dauern. 
    3. Sie können der Website Ihrer Domäne eine Textdatei hinzufügen. Wählen Sie aus, und laden Sie die Datei. txt aus dem Setup-Assistenten, und laden Sie die Datei dann in den Ordner auf oberster Ebene Ihrer Website hoch. Der Pfad zur Datei sollte wie folgt aussehen: `http://mydomain.com/ms39978200.txt` . Wir bestätigen, dass Sie die Domäne besitzen, indem Sie die Datei auf Ihrer Website suchen.
    
6. Wählen Sie aus, wie Sie die DNS-Änderungen vornehmen möchten, die Microsoft für die Verwendung Ihrer Domäne benötigt.
    
    1. Wählen Sie **Hinzufügen der DNS-Einträge für mich** aus, wenn Ihre Registrierungsstelle die [Domäne Connect](#domain-connect-registrars-integrating-with-microsoft-365)unterstützt, und Microsoft [wird Ihre Datensätze automatisch einrichten](../get-help-with-domains/domain-connect.md) , indem Sie sich bei Ihrer Registrierungsstelle anmelden und die Verbindung mit Microsoft 365 bestätigen.
    2. Wählen Sie **Ich werde die DNS-Einträge selbst hinzufügen** , wenn Sie nur bestimmte Microsoft 365-Dienste an Ihre Domäne anfügen möchten oder wenn Sie diese für jetzt überspringen möchten und dies später tun möchten. **Wählen Sie diese Option aus, wenn Sie genau wissen, was Sie tun.**

7. Wenn Sie *selbst DNS-Einträge hinzugefügt*  haben, wählen Sie **weiter** aus, und es wird eine Seite mit allen Datensätzen angezeigt, die Sie Ihrer Registrierungsstellen Website hinzufügen müssen, um Ihre Domäne einzurichten. 

    Wenn das Portal Ihre Registrierungsstelle nicht erkennt, können Sie [diesen allgemeinen Anleitungen folgen](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).
    
    Suchen Sie in der Liste der [hostspezifischen Anweisungen](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) Ihren Host, und führen Sie die Schritte zum Hinzufügen aller benötigten Datensätze aus. 
    
    Wenn Sie den DNS-Hostinganbieter oder die Domänenregistrierungsstelle für Ihre Domäne nicht kennen, lesen Sie [Finden Ihrer Domänenregistrierungsstelle oder Ihres DNS-Hostinganbieters](../get-help-with-domains/find-your-domain-registrar.md).
    
    Wenn Sie später warten möchten, deaktivieren Sie entweder alle Dienste, und klicken Sie auf **weiter**, oder wählen Sie im Abschnitt vorherige Domäne-Verbindung **Weitere Optionen** aus, und wählen Sie **diese Option jetzt überspringen**aus.
    
8. Wählen Sie **Fertig stellen** aus. Sie haben es geschafft!

## <a name="add-or-edit-custom-dns-records"></a>Hinzufügen oder Bearbeiten von benutzerdefinierten DNS-Einträgen

Führen Sie die folgenden Schritte aus, um einen benutzerdefinierten Datensatz für eine Website oder einen Drittanbieterdienst hinzuzufügen.

1. Melden Sie sich beim Microsoft Admin Center an <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Wechseln Sie zur Seite **Einstellungen**  > **Domänen**.

3. Wählen Sie auf der Seite **Domänen** eine Domäne aus. 
    
4. Wählen Sie unter **DNS-Einstellungen**die Option **Benutzerdefinierte Datensätze**aus. Wählen Sie dann **neuer benutzerdefinierter Datensatz**aus.

5. Wählen Sie den Typ des DNS-Eintrags aus, den Sie hinzufügen möchten, und geben Sie die Informationen für den neuen Datensatz ein.
    
6. Klicken Sie auf **Speichern**.

## <a name="registrars-with-domain-connect"></a>Registrierungsstellen mit Domäne Connect

Mit [Domänen Verbindungs](https://www.domainconnect.org/) fähigen Registrierungsstellen können Sie Ihre Domäne in einem dreistufigen Prozess, der Minuten dauert, zu Microsoft 365 hinzufügen. 
  
Im Assistenten bestätigen wir lediglich, dass Sie die Domäne besitzen und dann automatisch die Datensätze Ihrer Domäne einrichten, sodass e-Mails an Microsoft 365 und andere Microsoft 365-Dienste wie Teams mit Ihrer Domäne arbeiten.
  
> [!NOTE]
> Stellen Sie sicher, dass Sie alle Popupblocker in Ihrem Browser deaktivieren, bevor Sie den Setup-Assistenten starten.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Domänen Verbindungs Registrierungsstellen, die in Microsoft 365 integriert sind

- [1 &amp; 1 Ionos](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer oder WildWestDomains (GoDaddy Reseller mit SecureServer DNS-Hosting)
    - Beispiele:
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>Was geschieht mit meiner e-Mail und Website?

Nachdem Sie das Setup abgeschlossen haben, wird der MX-Eintrag für Ihre Domäne so aktualisiert, dass er auf Microsoft 365 verweist, und alle e-Mails für Ihre Domäne beginnen mit Microsoft 365. Stellen Sie sicher, dass Sie Benutzer hinzugefügt haben, und richten Sie in Microsoft 365 Postfächer für jeden ein, der e-Mails in Ihrer Domäne erhält!
  
Wenn Sie über eine Website verfügen, die Sie für Ihr Unternehmen verwenden, funktioniert sie weiterhin wie zuvor. Die Schritte zum Einrichten von Domänen Verbindungen wirken sich nicht auf Ihre Website aus.

## <a name="related-articles"></a>Verwandte Artikel

[Häufig gestellte Fragen zu Domänen](domains-faq.md)

[Was ist eine Domäne?](../get-help-with-domains/what-is-a-domain.md)

[Erwerben eines Domänennamens in Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)

[Einrichten Ihrer Domäne (hostspezifische Anweisungen)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
