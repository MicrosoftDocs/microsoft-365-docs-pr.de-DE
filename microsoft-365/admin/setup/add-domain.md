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
description: Verwenden Sie den Setup-Assistenten, um Ihre Domäne Microsoft 365 im Microsoft 365 Admin Center hinzuzufügen, indem Sie einen DNS-Eintrag auf Ihrem DNS-Host hinzufügen.
ms.openlocfilehash: 96849e90a420dc31dbde8c55d5a1108f73f85978
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535830"
---
# <a name="add-a-domain-to-microsoft-365"></a>Hinzufügen einer Domäne zu Microsoft 365

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 
  
 *Um Domänen hinzuzufügen, zu ändern oder zu entfernen, **müssen** Sie ein **globaler Administrator** eines [Geschäfts- oder Unternehmensplans](https://products.office.com/business/office) sein. Diese Änderungen betreffen den gesamten Mandanten. *Benutzerdefinierte Administratoren* oder *reguläre Benutzer* können diese Änderungen nicht vornehmen.*  

 ## <a name="add-a-domain"></a>Domäne hinzufügen

Führen Sie die folgenden Schritte aus, um eine Domäne hinzuzufügen, einzurichten oder die Einrichtung einer Domäne fortzusetzen. 

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
    
    1. Wenn Ihre Domänenregistrierungsstelle [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365) verwendet, richtet Microsoft [Ihre Einträge automatisch ein](../get-help-with-domains/domain-connect.md). Hierfür müssen Sie sich bei Ihrer Registrierungsstelle anmelden und die Verbindung zu Microsoft 365 bestätigen. Sie werden zum Admin Center zurückgeführt, und Microsoft überprüft dann Ihre Domäne automatisch.
    2. Sie können einen TXT-Eintrag zur Überprüfung Ihrer Domäne verwenden. Wählen Sie dies und dann **Weiter** aus, um Anleitungen dazu anzuzeigen, wie Sie diesen DNS-Eintrag zur Website Ihrer Registrierungsstelle hinzufügen. Nachdem Sie den Eintrag hinzugefügt haben, kann die Überprüfung bis zu 30 Minuten dauern. 
    3. Sie können der Website Ihrer Domäne eine Textdatei hinzufügen. Wählen Sie die TXT-Datei aus dem Setup-Assistenten aus, laden Sie sie herunter, und laden Sie sie dann in den Ordner der obersten Ebene Ihrer Website hoch. Der Pfad zu der Datei sollte ähnlich wie dieser aussehen: `http://mydomain.com/ms39978200.txt`. Wir werden überprüfen, ob Sie die Domänen besitzen, indem wir die Datei auf Ihrer Website suchen.
    
6. Wählen Sie aus, wie Sie die erforderlichen DNS-Änderungen vornehmen möchten, damit Microsoft Ihre Domäne verwenden kann.
    
    1. Wählen Sie **DNS-Einträge für mich hinzufügen**, falls Ihre Domänenregistrierungsstelle [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365) unterstützt. Microsoft wird dann [Ihre Einträge automatisch einrichten](../get-help-with-domains/domain-connect.md). Hierfür müssen Sie sich bei Ihrer Registrierungsstelle anmelden und die Verbindung zu Microsoft 365 bestätigen.
    2. Wählen Sie **Ich füge die DNS-Einträge selbst hinzu** aus, wenn Sie nur bestimmte Microsoft 365-Dienste zu Ihrer Domäne hinzufügen oder diesen Schritt zunächst überspringen und erst zu einem späteren Zeitpunkt ausführen möchten. **Wählen Sie diese Option aus, wenn Sie genau wissen, was Sie tun.**

7. Wenn Sie ausgewählt haben, dass Sie *DNS-Einträge selbst hinzufügen* möchten, klicken Sie auf **Weiter**. Anschließend wird eine Seite mit allen Einträgen angezeigt, die Sie zur Website Ihrer Registrierungsstelle hinzufügen müssen, um Ihre Domäne einzurichten. 

    Wenn das Portal Ihre Registrierungsstelle nicht erkennt, können Sie [diesen allgemeinen Anleitungen folgen](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).
    
    Suchen Sie in der Liste der [hostspezifischen Anweisungen](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) Ihren Host, und führen Sie die Schritte zum Hinzufügen aller benötigten Datensätze aus. 
    
    Wenn Sie den DNS-Hostinganbieter oder die Domänenregistrierungsstelle für Ihre Domäne nicht kennen, lesen Sie [Finden Ihrer Domänenregistrierungsstelle oder Ihres DNS-Hostinganbieters](../get-help-with-domains/find-your-domain-registrar.md).
    
    Wenn Sie auf einen späteren Zeitpunkt warten möchten, deaktivieren Sie entweder die Auswahl aller Dienste, und klicken Sie auf **Weiter**, oder wählen Sie im vorherigen Schritt für die Domänenverbindung **Weitere Optionen** und dann **Dies vorerst überspringen** aus.
    
8. Klicken Sie auf **Fertigstellen**. Sie haben es geschafft!

## <a name="add-or-edit-custom-dns-records"></a>Hinzufügen oder Bearbeiten von benutzerdefinierten DNS-Einträgen

Führen Sie die folgenden Schritte aus, um einen benutzerdefinierten Eintrag für eine Website oder den Dienst eines Drittanbieters hinzuzufügen.

1. Melden Sie sich beim Microsoft Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> an.

2. Wechseln Sie zur Seite **Einstellungen**  > **Domänen**.

3. Wählen Sie auf der Seite **Domänen** eine Domäne aus. 
    
4. Wählen Sie unter **DNS-Einstellungen** die Option **Benutzerdefinierte Einträge** und dann **Neuer benutzerdefinierter Eintrag** aus.

5. Wählen Sie den Typ des DNS-Eintrags aus, den Sie hinzufügen möchten, und geben Sie die Informationen für den neuen Eintrag ein.
    
6. Klicken Sie auf **Speichern**.

## <a name="registrars-with-domain-connect"></a>Registrierungsstellen mit Domain Connect

Registrierungsstellen, die [Domain Connect](https://www.domainconnect.org/) unterstützen, ermöglichen es Ihnen, Ihre Domäne in einem dreistufigen Prozess zu Microsoft 365 hinzuzufügen, der nur wenige Minuten dauert. 
  
Im Assistenten werden wir nur überprüfen, ob Sie der Besitzer der Domäne sind. Anschließend werden die Einträge der Domäne automatisch eingerichtet, damit E-Mails bei Microsoft 365 eingehen und andere Microsoft 365-Dienste wie Microsoft Teams mit Ihrer Domäne verwendet werden können.
  
> [!NOTE]
> Stellen Sie sicher, dass alle Popupblocker in Ihrem Browser deaktiviert sind, bevor Sie den Setup-Assistenten starten.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Domain Connect-Registrierungsstellen, die eine Microsoft 365-Integration ermöglichen

- [1&amp;1 IONOS](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer oder WildWestDomains (GoDaddy-Wiederverkäufer, die SecureServer DNS-Hosting verwenden)
    - Beispiele:
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>Was geschieht mit meinen E-Mails und meiner Website?

Nachdem Sie das Setup abgeschlossen haben, wird der MX-Eintrag für Ihre Domäne aktualisiert, damit er auf Microsoft 365 verweist. Daraufhin gehen sämtliche E-Mails für Ihre Domäne bei Microsoft 365 ein. Stellen Sie sicher, dass Sie in Microsoft 365 Benutzer und Postfächer für alle Personen hinzugefügt und erstellt haben, die in Ihrer Domäne E-Mails erhalten.
  
Wenn Sie über eine Website verfügen, die Sie für Ihr Unternehmen verwenden, funktioniert diese weiterhin wie zuvor. Die Einrichtungsschritte für Domain Connect wirken sich nicht auf Ihre Website aus.

## <a name="related-content"></a>Verwandte Inhalte

[Häufig gestellte Fragen](domains-faq.yml) zu Domänen (Artikel)

[Was ist eine Domäne?](../get-help-with-domains/what-is-a-domain.md) (Artikel)

[Kaufen eines Domänennamens in Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (Artikel)

[Einrichten Ihrer Domäne](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) (Artikel)