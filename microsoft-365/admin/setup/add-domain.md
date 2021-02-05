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
description: Fügen Sie Ihre Domäne zu Microsoft 365 im Microsoft 365 Admin Center hinzu, indem Sie einen DNS-Eintrag bei Ihrem DNS-Host hinzufügen. Der Setup-Assistent führt Sie nun durch den Vorgang.
ms.openlocfilehash: 5a3c86fb2b2f93e9da844c15a55555c5d0d7b5c1
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114255"
---
# <a name="add-a-domain-to-microsoft-365"></a>Hinzufügen einer Domäne zu Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 
  
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
    
    1. Wenn Ihre Domänenregistrierungsstelle [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365)verwendet, richten [Microsoft](../get-help-with-domains/domain-connect.md) Ihre Einträge automatisch ein, indem Sie sich bei Ihrer Registrierungsstelle anmelden und die Verbindung zu Microsoft 365 bestätigen. Sie werden an das Admin Center zurückgegeben, und Microsoft überprüft Dann automatisch Ihre Domäne.
    2. Sie können einen TXT-Eintrag zur Überprüfung Ihrer Domäne verwenden. Wählen Sie dies und dann **Weiter** aus, um Anleitungen dazu anzuzeigen, wie Sie diesen DNS-Eintrag zur Website Ihrer Registrierungsstelle hinzufügen. Nachdem Sie den Eintrag hinzugefügt haben, kann die Überprüfung bis zu 30 Minuten dauern. 
    3. Sie können der Website Ihrer Domäne eine Textdatei hinzufügen. Wählen Sie die TXT-Datei aus dem Setup-Assistenten aus, und laden Sie sie in den Ordner auf oberster Ebene Ihrer Website hoch. Der Pfad zu der Datei sollte ähnlich aussehen wie: `http://mydomain.com/ms39978200.txt` . We'll confirm you own the domain by finding the file on your website.
    
6. Wählen Sie aus, wie Sie die dns-Änderungen vornehmen möchten, die microsoft für die Verwendung Ihrer Domäne benötigt.
    
    1. Choose **Add the DNS records for me** if your registrar supports Domain [Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft will set up your [records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.
    2. Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later. **Wählen Sie diese Option aus, wenn Sie genau wissen, was Sie tun.**

7. Wenn Sie sich dafür entschieden haben, selbst DNS-Einträge *hinzuzufügen,*  wählen Sie **"Weiter"** aus, und es wird eine Seite mit allen Einträgen angezeigt, die Sie ihrer Registrierungsstellenwebsite hinzufügen müssen, um Ihre Domäne einrichten zu können. 

    Wenn das Portal Ihre Registrierungsstelle nicht erkennt, können Sie [diesen allgemeinen Anleitungen folgen](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).
    
    Suchen Sie in der Liste der [hostspezifischen Anweisungen](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) Ihren Host, und führen Sie die Schritte zum Hinzufügen aller benötigten Datensätze aus. 
    
    Wenn Sie den DNS-Hostinganbieter oder die Domänenregistrierungsstelle für Ihre Domäne nicht kennen, lesen Sie [Finden Ihrer Domänenregistrierungsstelle oder Ihres DNS-Hostinganbieters](../get-help-with-domains/find-your-domain-registrar.md).
    
    Wenn Sie auf einen späteren Zeitpunkt warten möchten, deaktivieren Sie entweder die Auswahl  aller Dienste, und klicken Sie auf "Weiter", oder wählen Sie im vorherigen Schritt der Domänenverbindung "Weitere Optionen" aus, und wählen Sie "Diese Option **vorerst überspringen" aus.**
    
8. Wählen Sie **Fertig stellen** aus. Sie haben es geschafft!

## <a name="add-or-edit-custom-dns-records"></a>Hinzufügen oder Bearbeiten von benutzerdefinierten DNS-Einträgen

Führen Sie die folgenden Schritte aus, um einen benutzerdefinierten Eintrag für eine Website oder einen Drittanbieterdienst hinzuzufügen.

1. Melden Sie sich beim Microsoft Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> an.

2. Wechseln Sie zur Seite **Einstellungen**  > **Domänen**.

3. Wählen Sie auf der Seite **Domänen** eine Domäne aus. 
    
4. Wählen **Sie unter "DNS-Einstellungen"** **"Benutzerdefinierte Einträge" aus.** wählen Sie dann **"Neuer benutzerdefinierter Datensatz" aus.**

5. Wählen Sie den Typ des DNS-Eintrags aus, den Sie hinzufügen möchten, und geben Sie die Informationen für den neuen Eintrag ein.
    
6. Klicken Sie auf **Speichern**.

## <a name="registrars-with-domain-connect"></a>Registrierungen mit Domain Connect

[Mit domänenverbindeten](https://www.domainconnect.org/) Registrierungsstellen können Sie Ihre Domäne in einem Drei-Schritte-Prozess, der Minuten dauert, zu Microsoft 365 hinzufügen. 
  
Im Assistenten bestätigen wir lediglich, dass Sie der Domänenname ist, und richten dann automatisch die Einträge Ihrer Domäne ein, damit E-Mails an Microsoft 365 und andere Microsoft 365-Dienste, z. B. Teams, mit Ihrer Domäne funktionieren.
  
> [!NOTE]
> Stellen Sie sicher, dass Sie alle Popupblocker in Ihrem Browser deaktivieren, bevor Sie den Setup-Assistenten starten.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Integration von Domänen-Connect-Registrierungsstellen in Microsoft 365

- [1 &amp; 1OSAOS](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Zungesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer oder WildWestDomains (GoDaddy-Händler, die SecureServer-DNS-Hosting verwenden)
    - Beispiele:
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>Was geschieht mit meiner E-Mail und Website?

Nachdem Sie das Setup abgeschlossen haben, wird der MX-Eintrag für Ihre Domäne so aktualisiert, dass er auf Microsoft 365 verweisen kann, und alle E-Mails für Ihre Domäne werden an Microsoft 365 gesendet. Stellen Sie sicher, dass Sie Benutzer hinzugefügt und Postfächer in Microsoft 365 für alle Benutzer eingerichtet haben, die E-Mails in Ihrer Domäne erhalten!
  
Wenn Sie über eine Website verfügen, die Sie für Ihr Unternehmen verwenden, funktioniert sie weiterhin wie zuvor. Die Einrichtungsschritte für Domain Connect wirken sich nicht auf Ihre Website aus.

## <a name="related-articles"></a>Verwandte Artikel

[Häufig gestellte Fragen zu Domänen](domains-faq.yml)

[Was ist eine Domäne?](../get-help-with-domains/what-is-a-domain.md)

[Erwerben eines Domänennamens in Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)

[Einrichten Ihrer Domäne (hostspezifische Anweisungen)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
