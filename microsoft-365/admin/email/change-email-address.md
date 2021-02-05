---
title: Ändern der E-Mail-Adresse auf die eigene benutzerdefinierte Domäne
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
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: 'Ändern Sie Ihre ursprüngliche E-Mail-Adresse in eine benutzerfreundliche E-Mail-Adresse wie tom@fourthcoffee.com. Dazu müssen Sie einen Domänennamen kaufen und zu Microsoft 365 hinzufügen. '
ms.openlocfilehash: 445b78f759cee79a794f9656afd5b26051534e26
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114021"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Ändern der E-Mail-Adresse auf die eigene benutzerdefinierte Domäne

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 
  
::: moniker range="o365-worldwide"

Ihre ursprüngliche E-Mail-Adresse in Microsoft 365 enthält .onmicrosoft.com, z. B. tom@fourthcoffee.onmicrosoft.com. Sie können die Adresse in eine freundlichere Adresse ändern, z. B. tom@fourthcoffee.com. Sie benötigen Ihren eigenen Domänennamen, z. B. fourthcoffee.com zuerst. Wenn Sie bereits über eine verfügen, ist dies sehr gut! Wenn nicht, können Sie erfahren, wie Sie [eine von einer Domänenregistrierungsstelle kaufen.](../get-help-with-domains/buy-a-domain-name.md)

::: moniker-end

::: moniker range="o365-germany"

Ihre ursprüngliche E-Mail-Adresse in Office 365 Deutschland enthält .onmicrosoft.de, z. B. tom@fourthcoffee.onmicrosoft.de. Sie können die Adresse in eine freundlichere Adresse ändern, z. B. tom@fourthcoffee.de. Sie benötigen Ihren eigenen Domänennamen, z. B. fourthcoffee.de. Wenn Sie bereits über eine verfügen, ist dies sehr gut! Wenn nicht, können Sie erfahren, wie Sie [eine von einer Domänenregistrierungsstelle kaufen.](../get-help-with-domains/buy-a-domain-name.md)

::: moniker-end

::: moniker range="o365-21vianet"

Ihre ursprüngliche E-Mail-Adresse in Office 365, betrieben von 21Vianet, umfasst partner.onmschina.cn, z. B. tom@fourthcoffee.partner.onmschina.cn. Sie können die Adresse in eine freundlichere Adresse ändern, z. B. tom@fourthcoffee.cn. Sie benötigen Ihren eigenen Domänennamen, z. B. fourthcoffee.cn. Wenn Sie bereits über eine verfügen, ist dies sehr gut! Wenn nicht, können Sie erfahren, wie Sie [eine von einer Domänenregistrierungsstelle kaufen.](../get-help-with-domains/buy-a-domain-name.md)

::: moniker-end

Wenn Sie die E-Mail-Adresse Ihrer Domäne so ändern, dass sie an Microsoft 365 gesendet wird, werden alle an diese Domäne gesendeten E-Mails bei Microsoft 365 übermittelt, indem Sie den MX-Eintrag Ihrer Domäne während des Setups aktualisieren. Stellen Sie sicher, dass Sie Benutzer hinzugefügt und Postfächer in Microsoft 365 für alle Benutzer erstellt haben, die über E-Mails in Ihrer Domäne verfügen, BEVOR Sie den MX-Eintrag ändern. Möchten Sie keine E-Mails für alle Benutzer in Ihrer Domäne nach Microsoft 365 verschieben? Sie können stattdessen schritte zum [Piloten von Microsoft 365 mit nur wenigen E-Mail-Adressen ausführen.](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide)
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Ändern Ihrer E-Mail-Adresse für die Verwendung Ihrer benutzerdefinierten Domäne mithilfe des Microsoft 365 Admin Centers

Sie müssen über ein globales Administratorkonto verfügen, um diese Schritte ausführen zu können. 

::: moniker range="o365-worldwide"

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>Admin Center unter . 

::: moniker-end 

2. Wechseln Sie zur **Seite "Setupdomänen".**  >   

3. Klicken Sie auf der Seite **Domänen** auf **Domäne hinzufügen**.
    
4. Befolgen Sie die angezeigten Schritte, um zu bestätigen, dass Sie die Domäne besitzen, und Ihre E-Mail-Adresse zu ändern.
    
Sie werden geführt, um alles ordnungsgemäß mit Ihrer Domäne in Microsoft 365 einrichten zu können.

> [!NOTE]
> Wenn Sie keine Exchange-Lizenz verwenden, können Sie die Domäne nicht zum Senden oder Empfangen von E-Mails vom Microsoft 365-Mandanten verwenden.
  
## <a name="related-articles"></a>Verwandte Artikel

[Erwerben einer benutzerdefinierten Domäne mit Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)
 
