---
title: Sammeln der Informationen, die Sie zum Erstellen von DNS-Einträgen benötigen
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Sammeln Sie die Werte/Informationen, die Sie zum Erstellen von DNS-Einträgen benötigen, um Ihre Domäne mit Ihrem Microsoft 365 Abonnement zu verbinden.
ms.openlocfilehash: c9869444da2ccb7f96ee01576d966767681c5b49
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393883"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>Sammeln der Informationen, die Sie zum Erstellen von DNS-Einträgen benötigen

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Schritt 1: Suchen des TXT-Eintragswerts und Überprüfen

::: moniker range="o365-worldwide"

1. Wechseln Sie im Microsoft 365 Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen.</a>

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a>.

::: moniker-end
    
2. Wählen Sie auf der Seite **"Domänen"** Ihre Domäne aus, und wählen Sie dann **"Setup starten"** aus. Sie gelangen wieder zum Assistenten für die Domäneneinrichtung und sehen dort den spezifischen Wert, den Sie hinzufügen müssen.
    
3. Wählen Sie auf der Seite **"Domänenüberprüfung"** **einen TXT-Eintrag zu den DNS-Einträgen der Domäne** hinzufügen aus, und wählen Sie dann **"Weiter"** aus.
    
4. Kopieren Sie den angezeigten **TXT-Wert.** Es sieht wie folgt aus: **MS=msXXXXXXXX**. 
    
5. Wechseln Sie zum [Hinzufügen von DNS-Einträgen, um Ihre Domäne zu verbinden,](create-dns-records-at-any-dns-hosting-provider.md)und führen Sie die Schritte aus, um Einträge auf der Website Ihres DNS-Hosts hinzuzufügen.
    
6. Führen Sie die Schritte zum Erstellen des TXT-Eintrags (oder MX-Eintrags) auf Ihrem DNS-Host aus, und überprüfen Sie dann die Domäne wieder in Microsoft 365.

7. Entfernen Sie den TXT-Eintrag (oder MX-Eintrag) von Ihrem DNS-Host, sobald die Domäne in Microsoft 365 überprüft wurde.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Schritt 2: Suchen des MX-Eintragswerts für E-Mails und mehr

::: moniker range="o365-worldwide"

1. Wechseln Sie im Microsoft 365 Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen.</a>

::: moniker-end
    
::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a>.

::: moniker-end
    
2. Wählen Sie auf der Seite **Domänen** Ihre Domäne aus.
    
3. Wählen Sie **"DNS verwalten"** aus, wählen Sie **"Weitere Optionen**  >  **hinzufügen"** aus, und wählen Sie **"Weiter"** aus, um die hinzuzufügenden DNS-Einträge anzuzeigen.
    
    Sie sollten diese Informationen zur Verfügung haben, wenn Sie Änderungen bei Ihrem DNS-Hostinganbieter vornehmen, damit Sie die Werte kopieren und einfügen können.
    
    Die auf dieser Seite aufgelisteten Gruppen von DNS-Einträgen sind von den unter **Domänenzweck** aufgelisteten Optionen abhängig.
    
4. Wechseln Sie zum [Hinzufügen von DNS-Einträgen, um Ihre Domäne zu verbinden,](create-dns-records-at-any-dns-hosting-provider.md)und führen Sie die Schritte aus, um Einträge auf der Website Ihres DNS-Hosts hinzuzufügen.

5. Führen Sie die Schritte zum Erstellen der DNS-Einträge bei Ihrem DNS-Hostinganbieter aus.

## <a name="related-content"></a>Verwandte Inhalte

[Häufig gestellte Fragen zu Domänen](../setup/domains-faq.yml) (Artikel)\
[Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](find-and-fix-issues.md) (Artikel)\
[Domänen verwalten](index.yml) (Linkseite)