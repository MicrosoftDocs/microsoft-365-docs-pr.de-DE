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
ms.openlocfilehash: 747de5f61dc9fce53f82f52b65f701572a56f8d4
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470881"
---
# <a name="add-a-domain-to-microsoft-365"></a>Hinzufügen einer Domäne zu Microsoft 365

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
    
    1. Wenn Ihre Domänenregistrierungsstelle [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365)verwendet, [wird](../get-help-with-domains/domain-connect.md) Microsoft Ihre Datensätze automatisch einrichten, indem Sie sich bei Ihrer Registrierungsstelle anmelden und die Verbindung zu Microsoft 365 bestätigen. Sie werden an das Admin Center zurückgegeben, und Microsoft überprüft dann automatisch Ihre Domäne.
    2. Sie können einen TXT-Eintrag zur Überprüfung Ihrer Domäne verwenden. Wählen Sie dies und dann **Weiter** aus, um Anleitungen dazu anzuzeigen, wie Sie diesen DNS-Eintrag zur Website Ihrer Registrierungsstelle hinzufügen. Nachdem Sie den Eintrag hinzugefügt haben, kann die Überprüfung bis zu 30 Minuten dauern. 
    3. Sie können der Website Ihrer Domäne eine Textdatei hinzufügen. Wählen Sie die TXT-Datei aus dem Setup-Assistenten aus, und laden Sie sie dann in den Ordner der obersten Ebene Ihrer Website hoch. Der Pfad zur Datei sollte ähnlich aussehen wie: `http://mydomain.com/ms39978200.txt` . Wir bestätigen, dass Sie DerEnt der Domäne sind, indem wir die Datei auf Ihrer Website suchen.
    
6. Wählen Sie aus, wie Sie die für die Verwendung Ihrer Domäne von Microsoft erforderlichen DNS-Änderungen vornehmen möchten.
    
    1. Wählen **Sie Hinzufügen der DNS-Einträge** für mich aus, wenn Ihre Registrierungsstelle Domain [Connect](#domain-connect-registrars-integrating-with-microsoft-365)unterstützt, und [Microsoft](../get-help-with-domains/domain-connect.md) wird Ihre Einträge automatisch einrichten, indem Sie sich bei Ihrer Registrierungsstelle anmelden und die Verbindung zu Microsoft 365 bestätigen.
    2. Wählen **Sie I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later. **Wählen Sie diese Option aus, wenn Sie genau wissen, was Sie tun.**

7. Wenn Sie selbst *DNS-Einträge*  hinzufügen möchten, wählen Sie **Weiter** aus, und Es wird eine Seite mit allen Datensätzen angezeigt, die Sie zur Registrierungsstellenwebsite hinzufügen müssen, um Ihre Domäne einrichten zu können. 

    Wenn das Portal Ihre Registrierungsstelle nicht erkennt, können Sie [diesen allgemeinen Anleitungen folgen](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).
    
    Suchen Sie in der Liste der [hostspezifischen Anweisungen](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) Ihren Host, und führen Sie die Schritte zum Hinzufügen aller benötigten Datensätze aus. 
    
    Wenn Sie den DNS-Hostinganbieter oder die Domänenregistrierungsstelle für Ihre Domäne nicht kennen, lesen Sie [Finden Ihrer Domänenregistrierungsstelle oder Ihres DNS-Hostinganbieters](../get-help-with-domains/find-your-domain-registrar.md).
    
    Wenn Sie später warten möchten, deaktivieren Sie entweder die Auswahl aller Dienste, und klicken Sie auf **Weiter**, oder wählen Sie im vorherigen Schritt domänenverbindung die Option **Weitere Optionen** aus, und wählen Sie diese option für den Moment **überspringen aus.**
    
8. Wählen Sie **Fertig stellen** aus. Sie haben es geschafft!

## <a name="add-or-edit-custom-dns-records"></a>Hinzufügen oder Bearbeiten von benutzerdefinierten DNS-Einträgen

Führen Sie die folgenden Schritte aus, um einen benutzerdefinierten Datensatz für eine Website oder einen Drittanbieterdienst hinzuzufügen.

1. Melden Sie sich beim Microsoft Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> an.

2. Wechseln Sie zur Seite **Einstellungen**  > **Domänen**.

3. Wählen Sie auf der Seite **Domänen** eine Domäne aus. 
    
4. Wählen **Sie unter #A0** **benutzerdefinierte Datensätze aus.** wählen Sie dann **Neuer benutzerdefinierter Datensatz aus.**

5. Wählen Sie den Typ des DNS-Eintrags aus, den Sie hinzufügen möchten, und geben Sie die Informationen für den neuen Eintrag ein.
    
6. Wählen Sie **Speichern** aus.

## <a name="registrars-with-domain-connect"></a>Registrierungsstellen mit Domänen verbinden

[Domain](https://www.domainconnect.org/) Connect-aktivierte Registrierungsstellen ermöglicht es Ihnen, Ihre Domäne in einem Drei-Schritt-Prozess, der Minuten dauert, zu Microsoft 365 hinzuzufügen. 
  
Im Assistenten bestätigen wir nur, dass Sie der Domänenname sind, und richten dann automatisch die Datensätze Ihrer Domäne ein, damit E-Mails an Microsoft 365 und andere Microsoft 365-Dienste wie Teams mit Ihrer Domäne funktionieren.
  
> [!NOTE]
> Stellen Sie sicher, dass Sie alle Popupblocker in Ihrem Browser deaktivieren, bevor Sie den Setup-Assistenten starten.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Integration von Domänen-Connect-Registrierungsstellen in Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer oder WildWestDomains (GoDaddy-Vertriebspartner, die SecureServer-DNS-Hosting verwenden)
    - Beispiele:
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>Was geschieht mit meiner E-Mail und Website?

Nachdem Sie das Setup abgeschlossen haben, wird der MX-Eintrag für Ihre Domäne auf Microsoft 365 aktualisiert, und alle E-Mails für Ihre Domäne werden an Microsoft 365 gesendet. Stellen Sie sicher, dass Sie Benutzer hinzugefügt und Postfächer in Microsoft 365 für alle Benutzer eingerichtet haben, die E-Mails in Ihrer Domäne erhalten!
  
Wenn Sie über eine Website verfügen, die Sie für Ihr Unternehmen verwenden, funktioniert sie weiterhin wie zuvor. Die Schritte zum Einrichten von Domänen verbinden wirken sich nicht auf Ihre Website aus.

## <a name="related-articles"></a>Verwandte Artikel

[Häufig gestellte Fragen zu Domänen](domains-faq.yml)

[Was ist eine Domäne?](../get-help-with-domains/what-is-a-domain.md)

[Erwerben eines Domänennamens in Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)

[Einrichten Ihrer Domäne (hostspezifische Anweisungen)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)