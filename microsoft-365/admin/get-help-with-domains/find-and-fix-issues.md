---
title: Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Erfahren Sie, wie Sie Probleme einkreisen können, die beim Einrichten einer benutzerdefinierten Domäne auftreten. Stellen Sie zunächst sicher, dass die DNS-Einträge ordnungsgemäß eingerichtet sind.
ms.openlocfilehash: 1dcc52be68fca11245e1a2437d9fe5a3f23ed694
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393895"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Es kann schwierig sein, Ihre Domäne für die Arbeit mit Microsoft 365 einzurichten. Das DNS-System eignet sich gut für die Arbeit, und das DNS-Setup für Ihre Domäne wirkt sich auf wichtige Geschäftsaktivitäten wie E-Mails aus.

> [!NOTE]
> Sie können nach Problemen mit Ihrer Domäne suchen, indem Sie deren Status überprüfen. Wechseln **Sie** zu  >  **"Setupdomänen",** und zeigen Sie die Benachrichtigungen in der Spalte **"Status"** an. Wenn ein Problem auftritt, wählen Sie die drei Punkte (weitere Aktionen) und dann **"Integrität überprüfen"** aus. In dem Bereich, der nun geöffnet wird, werden alle mit Ihrer Domäne auftretenden Probleme beschrieben.
  
## <a name="whats-going-on"></a>Was ist los?

- [Sie können Ihre Domäne nicht überprüfen?](#cant-verify-your-domain)
    
- [Outlook funktioniert nicht?](#outlook-isnt-working)
    
- [Die E-Mails aller Benutzer wurden auf Microsoft 365 umgestellt, und Sie wollten nur, dass IHRE E-Mail wechselt?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?](#cant-confirm-non-profit-or-school-account-status)

- [Dienste funktionieren nicht mit Ihrer Domäne?](#services-not-working-with-your-domain)
    
- [Sie können nicht auf Ihre Website zugreifen?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Sie können Ihre Domäne nicht überprüfen?
<a name="BKMK_verify"> </a>

Es gibt einige häufige Gründe dafür, dass die Domänenüberprüfung nicht wie gewünscht funktioniert:
  
1. **Der Wert des Prüfeintrags ist nicht ganz korrekt.** Vergewissern Sie sich, dass Sie den exakten Wert kopiert und in den TXT-Prüfeintrag bei Ihrem DNS-Host eingefügt haben. Ein häufiges Problem ist, dass der Teil "MS=" des Eintrags fehlt. Diese Angabe ist ebenfalls erforderlich! 
    
2. **Der Eintrag wurde nicht gespeichert.** Bei einigen DNS-Hosts müssen Sie einen zusätzlichen Schritt ausführen, um die Zonendatei zu speichern (in der der DNS-Eintrag gespeichert ist), damit der Eintrag im Internet aktualisiert wird. Stellen Sie sicher, dass Sie Ihre Änderungen gespeichert haben, damit Microsoft 365 den Datensatz anzeigen und überprüfen können. 
    
3. **Der Eintrag wurde noch nicht im Internet aktualisiert.** In der Regel dauert es nur ein paar Minuten, bis wir den neuen Eintrag sehen können, aber gelegentlich kann es auch ein paar Stunden dauern. 
    
## <a name="outlook-isnt-working"></a>Outlook funktioniert nicht?
<a name="BKMK_OutlookBroken"> </a>

Wenn Sie Ihren MX-Eintrag und andere DNS-Einträge für Ihre Domäne ordnungsgemäß eingerichtet haben, aber Ihr E-Mail-Programm nicht funktioniert, können wir Ihnen dabei helfen, [Ihre Probleme mit Outlook zu beheben](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>Die E-Mails aller Benutzer wurden auf Microsoft 365 umgestellt, und Sie wollten nur, dass IHRE E-Mail wechselt?
<a name="BKMK_EmailSwitched"> </a>

Wenn Sie Ihre Domäne zu Microsoft 365 hinzufügen, wird in der Regel der MX-Eintrag Ihrer Domäne (von Ihnen oder Microsoft 365) aktualisiert, um auf Microsoft 365 zu verweisen, und ALLE an diese Domäne gesendeten E-Mails werden an Microsoft 365 gesendet. Stellen Sie sicher, dass Sie Postfächer in Microsoft 365 für alle Benutzer erstellt haben, die über E-Mails in Ihrer Domäne verfügen, BEVOR Sie den MX-Eintrag ändern.
  
Was geschieht, wenn Sie keine E-Mails für alle Benutzer in Ihrer Domäne in Microsoft 365 verschieben möchten? Sie können stattdessen [ein Pilotprojekt mit Microsoft 365 und nur wenigen E-Mail-Adressen in die Wege leiten](../setup/domains-faq.yml). 
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?
<a name="BKMK_validateAcct"> </a>

Es gibt eine Reihe von Szenarios, in denen Sie lediglich die Domäne Ihrer Organisation bestätigen und keine Dienste einrichten müssen. Zum Beispiel, um Microsoft 365 nachzuweisen, dass Ihre Organisation für ein Schulabonnement qualifiziert ist.
  
Lesen Sie die Anleitung unter ["Überprüfen Ihrer Microsoft 365 Domäne, um den Besitz, den Status einer gemeinnützigen Organisation oder eines Bildungsbereichs nachzuweisen, oder um Yammer zu aktivieren,](../setup/domains-faq.yml) um sicherzustellen, dass Sie alle erforderlichen Schritte ausgeführt haben. Der Vorgang ist für jede Situation ein wenig anders. 
  
## <a name="services-not-working-with-your-domain"></a>Dienste funktionieren nicht mit Ihrer Domäne?
<a name="BKMK_Test"> </a>

Wir können Sie beim Diagnostizieren von Problemen mit der DNS-Einrichtung Ihrer Domäne unterstützen. Die Problembehandlung für Domänen in Microsoft 365 zeigt Alle Datensätze an, die korrigiert werden müssen, und genau, auf welche Datensätze festgelegt werden muss. 

> [!TIP]
> Sie haben Ihr DNS ordnungsgemäß eingerichtet, aber E-Mail-Nachrichten funktionieren in Outlook auf dem Desktop nicht? Sehen Sie sich die [verschiedenen E-Mail-Flussszenarien an,](/exchange/mail-flow-best-practices/mail-flow-best-practices) die Sie mit Microsoft 365 haben können, um sicherzustellen, dass Sie alles richtig für Ihr Unternehmen eingerichtet haben. Darüber hinaus finden Sie hier weitere Hilfe zur Problembehandlung im Zusammenhang mit E-Mails: [Beheben von Problemen mit Outlook](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>Sie können nicht auf Ihre Website zugreifen?
<a name="BKMK_Website"> </a>

Wenn Sie alle DNS-Probleme behoben haben, aber weiterhin Probleme auftreten, führen Sie eine der folgenden Aktionen aus.
  
- Benutzer können auf Ihre Website unter "www.mydomain.com" nicht zugreifen: [Diagnostizieren von Websiteproblemen](../setup/add-domain.md)
    
- Sie können Ihren A- oder CNAME-Eintrag nicht so aktualisieren, dass er auf Ihre Website verweist: [Aktualisieren von benutzerdefinierten DNS-Einträgen in Microsoft 365](../setup/add-domain.md)

## <a name="related-content"></a>Verwandte Inhalte

[Problembehandlung: Überwachen von Daten zu überprüften Domänenänderungen](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain) (Artikel)\
[Häufig gestellte Fragen zu Domänen](../setup/domains-faq.yml) (Artikel)

