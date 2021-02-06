---
title: Sammeln der Zum Erstellen von DNS-Einträgen benötigten Informationen
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Erfahren Sie, wie Sie die Werte/Informationen finden, die Sie zum Erstellen von DNS-Einträgen für Microsoft 365 benötigen. '
ms.openlocfilehash: 45994139b11a2fd5a03b2e979dd6af334bc1f00b
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126371"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>Sammeln der Zum Erstellen von DNS-Einträgen benötigten Informationen

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Schritt 1: Suchen des Werts des TXT-Eintrags und Überprüfen

::: moniker range="o365-worldwide"

1. Wechseln Sie im Microsoft 365 Admin Center zur **Seite "Setupdomänen".** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a>

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zur Seite **"Setupdomänen".** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"></a>

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zur Seite **"Setupdomänen".** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"></a>

::: moniker-end
    
2. Wählen Sie **auf der Seite "Domänen"** Ihre Domäne aus, und wählen Sie dann **"Setup starten" aus.** Sie gelangen wieder zum Assistenten für die Domäneneinrichtung und sehen dort den spezifischen Wert, den Sie hinzufügen müssen.
    
3. On the **Verify domain** page, select Add a TXT **record instead,** then select **Next**.
    
4. Kopieren Sie den **angezeigten TXT-Wert.** It looks like this: **MS=msXXXXXXXX**. 
    
5. Wechseln Sie [zu Create DNS records at any DNS hosting provider,](create-dns-records-at-any-dns-hosting-provider.md)and select your DNS host from the list of registrars to see the step-by-step instructions.
    
6. Befolgen Sie die Schritte zum Erstellen des TXT-Eintrags (oder MX-Eintrags) bei Ihrem DNS-Host, und überprüfen Sie dann die Domäne wieder in Microsoft 365.

7. Entfernen Sie den TXT-Eintrag (oder MX-Eintrag) von Ihrem DNS-Host, nachdem die Domäne in Microsoft 365 überprüft wurde.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Schritt 2: Suchen des Werts des MX-Eintrags für E-Mails und vieles mehr

::: moniker range="o365-worldwide"

1. Wechseln Sie im Microsoft 365 Admin Center zur **Seite "Setupdomänen".** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a>

::: moniker-end
    
::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zur Seite **"Setupdomänen".** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"></a>

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zur Seite **"Setupdomänen".** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"></a>

::: moniker-end
    
2. Wählen Sie auf der Seite **Domänen** Ihre Domäne aus. 
    
3. Unter **Erforderliche DNS-Einstellungen** werden die hinzuzufügenden DNS-Einträge angezeigt.
    
    Sie sollten diese Informationen zur Verfügung haben, wenn Sie Änderungen bei Ihrem DNS-Hostinganbieter vornehmen, damit Sie die Werte kopieren und einfügen können.
    
    Die auf dieser Seite aufgelisteten Gruppen von DNS-Einträgen sind von den unter **Domänenzweck** aufgelisteten Optionen abhängig.
    
4. Wechseln Sie zu [Create DNS records at any DNS hosting provider,](create-dns-records-at-any-dns-hosting-provider.md)and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.
    
5. Führen Sie die Schritte zum Erstellen der DNS-Einträge bei Ihrem DNS-Hostinganbieter aus.
