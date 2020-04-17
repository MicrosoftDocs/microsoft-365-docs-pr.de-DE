---
title: Sammeln der zum Erstellen von Office 365-DNS-Einträgen erforderlichen Informationen
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Erfahren Sie, wie Sie die Werte/Informationen finden, die Sie zum Erstellen von DNS-Einträgen für Office 365 benötigen. '
ms.custom: okr_smb
ms.openlocfilehash: 2cb45b6a5c07bd50e15e7f2a941be344b5f69038
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43540879"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a>Sammeln der zum Erstellen von Office 365-DNS-Einträgen erforderlichen Informationen

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Schritt 1: Suchen des txt-Eintrags Werts und überprüfen

::: moniker range="o365-worldwide"

1. Wechseln Sie im Microsoft 365 Admin Center zur Seite **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a> .

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zur Seite **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a> .

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zur Seite **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a> .

::: moniker-end
    
2. Wählen Sie auf der Seite **Domänen** die Domäne aus, und wählen Sie dann **Setup starten**aus. Sie gelangen wieder zum Assistenten für die Domäneneinrichtung und sehen dort den spezifischen Wert, den Sie hinzufügen müssen.
    
3. Wählen Sie auf der Seite **Domäne überprüfen** die Option **TXT-Eintrag hinzufügen**aus, und wählen Sie dann **weiter**aus.
    
4. Kopieren Sie den angezeigten **txt-Wert** . Es sieht wie folgt aus: **MS = msXXXXXXXX**. 
    
5. Wechseln Sie zu [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter](create-dns-records-at-any-dns-hosting-provider.md), und wählen Sie Ihren DNS-Host aus der Liste der Registrierungsstellen aus, um die Schritt-für-Schritt-Anleitungen anzuzeigen.
    
6. Führen Sie die Schritte zum Erstellen des TXT-Eintrags (oder des MX-Eintrags) bei Ihrem DNS-Hostinganbieter aus, und überprüfen Sie die Domäne, wenn Sie sich wieder in Office 365 befinden.

7. Entfernen Sie den TXT-Eintrag (oder den MX-Eintrag) von Ihrem DNS-Host, nachdem die Domäne in Office 365 überprüft wurde.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Schritt 2: Suchen des MX-Eintrags Werts für e-Mail und mehr

::: moniker range="o365-worldwide"

1. Wechseln Sie im Microsoft 365 Admin Center zur Seite **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a> .

::: moniker-end
    
::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zur Seite **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a> .

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zur Seite **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a> .

::: moniker-end
    
2. Wählen Sie auf der Seite **Domänen** Ihre Domäne aus. 
    
3. Unter **Erforderliche DNS-Einstellungen** werden die hinzuzufügenden DNS-Einträge angezeigt.
    
    Sie sollten diese Informationen zur Verfügung haben, wenn Sie Änderungen bei Ihrem DNS-Hostinganbieter vornehmen, damit Sie die Werte kopieren und einfügen können.
    
    Die auf dieser Seite aufgelisteten Gruppen von DNS-Einträgen sind von den unter **Domänenzweck** aufgelisteten Optionen abhängig.
    
4. Wechseln Sie zu [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter](create-dns-records-at-any-dns-hosting-provider.md), und wählen Sie dann den DNS-Host aus der Liste der Registrierungsstellen aus, um Schritt-für-Schritt-Anweisungen zum Hinzufügen von Datensätzen auf der Website dieses DNS-Hosts anzuzeigen.
    
5. Führen Sie die Schritte zum Erstellen der DNS-Einträge bei Ihrem DNS-Hostinganbieter aus.
