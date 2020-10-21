---
title: Kaufen eines Domänennamens
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
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1561140a-16a9-4a02-822d-a989250e479d
description: Erfahren Sie, wie Sie einen Domänennamen in Microsoft 365 kaufen.
ms.openlocfilehash: f636b9e6afc1e910a6b0c01a58a4e69127c80772
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645515"
---
# <a name="buy-a-domain-name"></a>Kaufen eines Domänennamens

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 *Um Domänen hinzuzufügen, zu ändern oder zu entfernen, **müssen** Sie ein **globaler Administrator** eines [Geschäfts- oder Unternehmensplans](https://products.office.com/business/office) sein. Diese Änderungen betreffen den gesamten Mandanten. *Benutzerdefinierte Administratoren* oder *reguläre Benutzer* können diese Änderungen nicht vornehmen.*  

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
### <a name="sign-in-and-go-to-settings--domains--buy-a-domain"></a>Melden Sie sich an und wechseln Sie zu Einstellungen \> Domänen \> kaufen einer Domäne

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.
    
3. Wählen Sie auf der Seite **Domänen** die Option **Domäne kaufen**aus.
    
Sie können aus den folgenden Domänen der obersten Ebene für Ihre Domäne auswählen.
  
- . biz
    
- . com
    
- . info
    
- . me
    
- . mobi
    
- .net
    
- . org
    
- . TV
    
- . co.uk
    
- org.uk
    

> [!NOTE]
> Wenn Sie die Option " **Domäne erwerben**" auswählen, werden Sie möglicherweise zur Website Ihres Microsoft-Partners umgeleitet, wenn der Mandant über einen Microsoft-Partner erworben/verwaltet wird.

### <a name="domain-privacy"></a>Datenschutz für Domänen
Wir bieten ein kostenloses Datenschutz Abonnement für Domänen mit dem Erwerb einer Domäne an. Dadurch bleiben Ihre Kontaktinformationen an die Registrierung Ihrer Domäne bei ICANN private angehängt. [Weitere Informationen.](https://whois.icann.org/en/privacy-and-proxy-services)
  
### <a name="buy-a-domain-from-another-domain-registrar"></a>Erwerben eines Domänennamens von einer anderen Domänenregistrierungsstelle
Wenn Sie eine Domäne von einer anderen Domänenregistrierungsstelle als [GoDaddy](https://www.godaddy.com)kaufen möchten, empfehlen wir die Verwendung eines unterstützten automatischen Setups (Domäne Connect). 
  
- [1 &amp; 1 Ionos](https://www.1and1.com/)
- [WordPress](https://www.wordpress.com) 

   
### <a name="transfer-your-domain-to-a-different-domain-registrar"></a>Übertragen Ihrer Domäne auf eine andere Domänenregistrierungsstelle

Wenn Ihre Domäne von einem Anbieter verwaltet wird, der nicht alle erforderlichen DNS-Einträge unterstützt, können Sie sie auf eine andere Registrierungsstelle übertragen. Wenn Sie die Domäne übertragen, ändern Sie die Angabe für das Unternehmen, das die Rechnungen ausstellt, um Ihren Domänennamen zu erneuern und beizubehalten.
  
Fordern Sie die Übertragung bei der Registrierungsstelle an, auf die Sie Ihre Domäne verschieben möchten. Suchen Sie auf deren Website nach einer entsprechenden Option wie **DNS übertragen**. Und denken Sie daran: Nachdem die Änderungen vorgenommen wurden, kann die Aktualisierung im Internet ein paar Tage dauern.
 



::: moniker range="o365-21vianet"
## <a name="how-to-buy-a-domain-for-office-365-operated-by-21vianet"></a>Erwerben einer Domäne für Office 365, betrieben von 21Vianet



Wenn Sie noch über keine eigene Domäne verfügen, können Sie bei einer Domänenregistrierungsstelle, einem Domänenwiederverkäufer oder sogar Ihrem aktuellen Internetanbieter problemlos online eine Domäne erwerben. Sie erhalten bei Ihrer Anmeldung bei Office 365, betrieben von 21Vianet einen Domänennamen wie contoso.partner.onmschina.cn. Vielleicht möchten Sie aber lieber einen benutzerdefinierten Domänennamen wie fourthcoffee.com verwenden.
  
Zum Einrichten einer Domäne in Microsoft 365 müssen Sie eine Domäne besitzen und einige der DNS-Einträge für Ihre Domäne ändern.
  
> [!CAUTION]
> Einige Domänenregistrierungsstellen oder DNS-Hostinganbieter erlauben nicht das Erstellen aller DNS-Einträge, die für Microsoft 365 erforderlich sind. Die in der folgenden Liste aufgeführten Hostinganbieter unterstützen alle erforderlichen Einträge. Falls Sie erwägen, einen anderen Hostinganbieter zu verwenden, [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). 
  
Nachdem Sie Ihre Domäne (bei einer Domänenregistrierungsstelle) registriert haben, melden Sie sich als Administrator bei Microsoft 365 an, und richten Sie Ihre Domäne so ein, dass Sie Sie mit Ihrer e-Mail-Adresse und anderen Diensten verwenden können..
  
> [!NOTE]
> Die SharePoint Online Informationen zur öffentlichen Website in diesem Artikel gelten nur, wenn Ihre Organisation Microsoft 365 vor dem 9. März 2015 erworben hat. 

## <a name="domain-registrars-that-support-all-dns-records-required-for-microsoft-365"></a>Domänenregistrierungsstellen, die alle für Microsoft 365 erforderlichen DNS-Einträge unterstützen

- [Oray](https://oray.com/)
    
- [HiChina](https://www.hichina.com/)
    
- [east.net](http://www.east.net/)
    
- [BIZCN](https://www.bizcn.com/)
    
::: moniker-end

## <a name="related-articles"></a>Verwandte Artikel

[Hinzufügen einer Domäne zu Microsoft 365](../setup/add-domain.md)

[Häufig gestellte Fragen zu Domänen](../setup/domains-faq.md)

[Aktualisieren von DNS-Einträgen, damit Ihre Website mit Ihrem aktuellen Hosting-Anbieter bleibt](https://docs.microsoft.com/microsoft-365/admin/dns/update-dns-records-to-retain-current-hosting-provider).
