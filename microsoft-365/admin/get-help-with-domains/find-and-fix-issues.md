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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Erfahren Sie, wie Sie Probleme einkreisen können, die beim Einrichten einer benutzerdefinierten Domäne auftreten. Stellen Sie zunächst sicher, dass die DNS-Einträge ordnungsgemäß eingerichtet sind.
ms.openlocfilehash: 5959cae02b87cf481fc06edd941a6da284b71736
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537547"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Die Einrichtung Ihrer Domäne für die Arbeit mit Microsoft 365 kann eine Herausforderung darstellen. Das DNS-System ist zu verwenden, und das DNS-Setup für Ihre Domäne wirkt sich auf wichtige Geschäftsaktivitäten wie E-Mail aus.

> [!NOTE]
> Sie können nach Problemen mit Ihrer Domäne suchen, indem Sie deren Status überprüfen. Wechseln Sie **zu**  >  **Setupdomänen,** und zeigen Sie die Benachrichtigungen in der **Spalte Status** an. Wenn ein Problem angezeigt wird, wählen Sie die drei Punkte (weitere Aktionen) aus, und wählen Sie dann **Integrität überprüfen aus.** In dem Bereich, der nun geöffnet wird, werden alle mit Ihrer Domäne auftretenden Probleme beschrieben.
  
## <a name="whats-going-on"></a>Was ist los?

- [Sie können Ihre Domäne nicht überprüfen?](#cant-verify-your-domain)
    
- [Outlook funktioniert nicht?](#outlook-isnt-working)
    
- [Alle E-Mails wurden zu Microsoft 365 und Sie wollten nur, dass IHRE E-Mail gewechselt wird?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?](#cant-confirm-non-profit-or-school-account-status)

- [Dienste funktionieren nicht mit Ihrer Domäne?](#services-not-working-with-your-domain)
    
- [Sie können nicht auf Ihre Website zugreifen?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Sie können Ihre Domäne nicht überprüfen?
<a name="BKMK_verify"> </a>

Es gibt einige häufige Gründe dafür, dass die Domänenüberprüfung nicht wie gewünscht funktioniert:
  
1. **Der Wert des Prüfeintrags ist nicht ganz korrekt.** Vergewissern Sie sich, dass Sie den exakten Wert kopiert und in den TXT-Prüfeintrag bei Ihrem DNS-Host eingefügt haben. Ein häufiges Problem ist, dass der Teil "MS=" des Eintrags fehlt. Diese Angabe ist ebenfalls erforderlich! 
    
2. **Der Eintrag wurde nicht gespeichert.** Bei einigen DNS-Hosts müssen Sie einen zusätzlichen Schritt ausführen, um die Zonendatei zu speichern (in der der DNS-Eintrag gespeichert ist), damit der Eintrag im Internet aktualisiert wird. Stellen Sie sicher, dass Sie Ihre Änderungen gespeichert haben, damit Microsoft 365 den Datensatz sehen und überprüfen können. 
    
3. **Der Eintrag wurde noch nicht im Internet aktualisiert.** In der Regel dauert es nur ein paar Minuten, bis wir den neuen Eintrag sehen können, aber gelegentlich kann es auch ein paar Stunden dauern. 
    
## <a name="outlook-isnt-working"></a>Outlook funktioniert nicht?
<a name="BKMK_OutlookBroken"> </a>

Wenn Sie Ihren MX-Eintrag und andere DNS-Einträge für Ihre Domäne ordnungsgemäß eingerichtet haben, aber Ihr E-Mail-Programm nicht funktioniert, können wir Ihnen dabei helfen, [Ihre Probleme mit Outlook zu beheben](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>Alle E-Mails wurden zu Microsoft 365 und Sie wollten nur, dass IHRE E-Mail gewechselt wird?
<a name="BKMK_EmailSwitched"> </a>

Wenn Sie Ihre Domäne zu Microsoft 365 hinzufügen, wird in der Regel der MX-Eintrag Ihrer Domäne (von Ihnen oder Microsoft 365) aktualisiert, um auf Microsoft 365 zu verweisen, und alle an diese Domäne gesendeten E-Mails werden an Microsoft 365. Stellen Sie sicher, dass Sie Postfächer in Microsoft 365 für alle Personen erstellt haben, die E-Mails in Ihrer Domäne haben, BEVOR Sie den MX-Eintrag ändern.
  
Was passiert, wenn Sie E-Mails nicht für alle in Ihrer Domäne verschieben möchten, um Microsoft 365? Sie können stattdessen [ein Pilotprojekt mit Microsoft 365 und nur wenigen E-Mail-Adressen in die Wege leiten](../setup/domains-faq.yml). 
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?
<a name="BKMK_validateAcct"> </a>

Es gibt eine Reihe von Szenarios, in denen Sie lediglich die Domäne Ihrer Organisation bestätigen und keine Dienste einrichten müssen. Um z. B. zu Microsoft 365, dass Ihre Organisation für ein Schulabonnement qualifiziert ist.
  
Lesen Sie die Anleitungen unter [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status,](../setup/domains-faq.yml) or to activate Yammer to make sure you've completed all the required steps. Der Vorgang ist für jede Situation ein wenig anders. 
  
## <a name="services-not-working-with-your-domain"></a>Dienste funktionieren nicht mit Ihrer Domäne?
<a name="BKMK_Test"> </a>

Wir können Sie beim Diagnostizieren von Problemen mit der DNS-Einrichtung Ihrer Domäne unterstützen. Die Problembehandlung für Domänen in Microsoft 365 zeigt alle Datensätze an, die behoben werden müssen, und genau das, worauf die Datensätze festgelegt werden müssen. 

> [!TIP]
> Sie haben Ihr DNS ordnungsgemäß eingerichtet, aber E-Mail-Nachrichten funktionieren in Outlook auf dem Desktop nicht? Sehen Sie sich [die verschiedenen Nachrichtenflussszenarien](/exchange/mail-flow-best-practices/mail-flow-best-practices) an, die Sie mit Microsoft 365 können, um sicherzustellen, dass sie für Ihr Unternehmen richtig eingerichtet sind. Darüber hinaus finden Sie hier weitere Hilfe zur Problembehandlung im Zusammenhang mit E-Mails: [Beheben von Problemen mit Outlook](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>Sie können nicht auf Ihre Website zugreifen?
<a name="BKMK_Website"> </a>

Wenn Sie alle DNS-Probleme behoben haben, aber weiterhin Probleme auftreten, führen Sie eine der folgenden Aktionen aus.
  
- Benutzer können auf Ihre Website unter "www.mydomain.com" nicht zugreifen: [Diagnostizieren von Websiteproblemen](../setup/add-domain.md)
    
- Sie können Ihren A- oder #A0 nicht aktualisieren, um auf Ihre Website zu verweisen: Aktualisieren von benutzerdefinierten [#A1 in Microsoft 365](../setup/add-domain.md)

## <a name="related-content"></a>Verwandte Inhalte

[Problembehandlung: Überwachen von Daten bei überprüften Domänenänderung](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

