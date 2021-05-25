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
description: Ändern Sie Ihre E-Mail-Adresse in eine tom@fourthcoffee.com E-Mail-Adresse, indem Sie einen Domänennamen kaufen und Microsoft 365.
ms.openlocfilehash: 1a248cb67bab5d0467cad35dc5be8023b8013a12
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635522"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Ändern der E-Mail-Adresse auf die eigene benutzerdefinierte Domäne

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 
  
::: moniker range="o365-worldwide"

Ihre anfängliche E-Mail-Adresse in Microsoft 365 schließt „.onmicrosoft.com“ ein, wie etwa in „tom@fourthcoffee.onmicrosoft.com“. Sie können dies in eine benutzerfreundlichere Adresse ändern, z. B. „tom@fourthcoffee.com“. Zunächst benötigen Sie Ihren eigenen Domänennamen, wie z. B. „fourthcoffee.com“. Wenn Sie bereits darüber verfügen, ist eine Voraussetzung schon erfüllt. Wenn nicht, informieren Sie sich, wie Sie [einen Domänennamen von einer Domänenregistrierungsstelle erwerben](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

Ihre anfängliche E-Mail-Adresse in Office 365 Deutschland schließt „.onmicrosoft.de“ ein, wie etwa in „tom@fourthcoffee.onmicrosoft.de“. Sie können dies in eine benutzerfreundlichere Adresse ändern, z. B. „tom@fourthcoffee.de“. Zunächst benötigen Sie Ihren eigenen Domänennamen, wie z. B. „fourthcoffee.de“. Wenn Sie bereits darüber verfügen, ist eine Voraussetzung schon erfüllt. Wenn nicht, informieren Sie sich, wie Sie [einen Domänennamen von einer Domänenregistrierungsstelle erwerben](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

Ihre anfängliche E-Mail-Adresse in Office 365, betrieben von 21Vianet, schließt „.partner.onmschina.cn“ ein, wie etwa in „tom@fourthcoffee.partner.onmschina.cn“. Sie können dies in eine benutzerfreundlichere Adresse ändern, z. B. „tom@fourthcoffee.cn“. Zunächst benötigen Sie Ihren eigenen Domänennamen, wie z. B. „fourthcoffee.cn“. Wenn Sie bereits darüber verfügen, ist eine Voraussetzung schon erfüllt. Wenn nicht, informieren Sie sich, wie Sie [einen Domänennamen von einer Domänenregistrierungsstelle erwerben](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

Wenn Sie Ihr E-Mail-System auf Microsoft 365 ändern, indem Sie im nächsten Schritt den MX-Eintrag der Domäne ändern, werden von nun an alle an diese Domäne gesendeten E-Mails an Microsoft 365 gesendet. Sorgen Sie dafür, dass Sie in Microsoft 365 Postfächer für alle Personen erstellt haben, die in Ihrer Domäne über E-Mail verfügen, BEVOR Sie den MX-Eintrag ändern. Sie möchten nicht für jeden in Ihrer Domäne E-Mails nach Microsoft 365 verschieben? Sie können stattdessen [ein Pilotprojekt mit Microsoft 365 und nur wenigen E-Mail-Adressen in die Wege leiten](../misc/pilot-microsoft-365-from-my-custom-domain.md). 
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Ändern der E-Mail-Adresse auf die eigene benutzerdefinierte Domäne über das Microsoft 365 Admin Center

Sie müssen über ein globales Administratorkonto verfügen, um diese Schritte ausführen zu können. 

::: moniker range="o365-worldwide"

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>. 

::: moniker-end 

2. Wechseln Sie zur Seite **Setup** > **Domänen**. 

3. Klicken Sie auf der Seite **Domänen** auf **Domäne hinzufügen**.
    
4. Befolgen Sie die angezeigten Schritte, um zu bestätigen, dass Sie die Domäne besitzen, und Ihre E-Mail-Adresse zu ändern.
    
Sie werden durch das Verfahren zum ordnungsgemäßen Einrichten Ihrer Domäne in Microsoft 365 geführt.

> [!NOTE]
> Wenn Sie keine Exchange-Lizenz verwenden, können Sie die Domäne nicht zum Senden oder Empfangen von E-Mails vom Microsoft 365-Mandanten verwenden.
  
## <a name="related-content"></a>Verwandte Inhalte

[Erwerben einer benutzerdefinierten Domäne mithilfe Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (Artikel)\
[Verwalten von Domänen](../get-help-with-domains/index.yml) (Linkseite)\
[Häufig gestellte Fragen zu Domänen](../setup/domains-faq.yml) (Artikel)