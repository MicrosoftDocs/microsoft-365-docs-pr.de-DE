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
ms.openlocfilehash: 786df75f3f8a514e9b3c2a7666d715c9abd082bd
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926390"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Die Einrichtung Ihrer Domäne für die Arbeit mit Microsoft 365 kann eine Herausforderung darstellen. Das DNS-System ist sehr sorgfältig für die Arbeit, und das DNS-Setup für Ihre Domäne wirkt sich auf wichtige Geschäftsaktivitäten wie E-Mail aus!

> [!NOTE]
> Sie können nach Problemen mit Ihrer Domäne suchen, indem Sie deren Status überprüfen. Wechseln Sie zu "Setupdomänen",  >   und zeigen Sie die Benachrichtigungen in der Spalte **"Status"** an. Wenn ein Problem angezeigt wird, wählen Sie „Weitere Aktionen“ aus (die drei Punkte), und wählen Sie dann **Integrität überprüfen** aus. In dem Bereich, der nun geöffnet wird, werden alle mit Ihrer Domäne auftretenden Probleme beschrieben.
  
## <a name="whats-going-on"></a>Was ist los?

- [Sie können Ihre Domäne nicht überprüfen?](#cant-verify-your-domain)
    
- [Outlook funktioniert nicht?](#outlook-isnt-working)
    
- [Die E-Mails aller Benutzer wurden zu Microsoft 365 umgestellt, und Sie wollten nur, dass Ihre E-Mail-Adresse wechselt?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?](#cant-confirm-non-profit-or-school-account-status)

- [Dienste funktionieren nicht mit Ihrer Domäne?](#services-not-working-with-your-domain)
    
- [Sie können nicht auf Ihre Website zugreifen?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Sie können Ihre Domäne nicht überprüfen?
<a name="BKMK_verify"> </a>

Es gibt einige häufige Gründe dafür, dass die Domänenüberprüfung nicht wie gewünscht funktioniert:
  
1. **Der Wert des Prüfeintrags ist nicht ganz korrekt.** Vergewissern Sie sich, dass Sie den exakten Wert kopiert und in den TXT-Prüfeintrag bei Ihrem DNS-Host eingefügt haben. Ein häufiges Problem ist, dass der Teil "MS=" des Eintrags fehlt. Diese Angabe ist ebenfalls erforderlich! 
    
2. **Der Datensatz wurde nicht gespeichert.** Bei einigen DNS-Hosts müssen Sie einen zusätzlichen Schritt zum Speichern der Zonendatei (in der der DNS-Eintrag gespeichert ist) unternehmen, damit sie über das Internet aktualisiert wird. Stellen Sie sicher, dass Sie Ihre Änderungen gespeichert haben, damit Microsoft 365 den Datensatz sehen und überprüfen kann. 
    
3. **Der Eintrag wurde noch nicht im Internet aktualisiert.** In der Regel dauert es nur ein paar Minuten, bis wir den neuen Eintrag sehen können, aber gelegentlich kann es auch ein paar Stunden dauern. 
    
## <a name="outlook-isnt-working"></a>Outlook funktioniert nicht?
<a name="BKMK_OutlookBroken"> </a>

Wenn Sie Ihren MX-Eintrag und andere DNS-Einträge für Ihre Domäne ordnungsgemäß eingerichtet haben, aber Ihr E-Mail-Programm nicht funktioniert, können wir Ihnen dabei helfen, [Ihre Probleme mit Outlook zu beheben](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>Die E-Mails aller Benutzer wurden zu Microsoft 365 umgestellt, und Sie wollten nur, dass Ihre E-Mails wechseln?
<a name="BKMK_EmailSwitched"> </a>

Wenn Sie Ihre Domäne zu Microsoft 365 hinzufügen, wird in der Regel der MX-Eintrag Ihrer Domäne (von Ihnen oder Microsoft 365) aktualisiert, um auf Microsoft 365 zu verweisen, und alle an diese Domäne gesendeten E-Mails werden an Microsoft 365 gesendet. Stellen Sie sicher, dass Sie Postfächer in Microsoft 365 für alle Benutzer erstellt haben, die über E-Mails in Ihrer Domäne verfügen, bevor Sie den MX-Eintrag ändern.
  
Was passiert, wenn Sie keine E-Mails für alle Benutzer in Ihrer Domäne nach Microsoft 365 verschieben möchten? Sie können stattdessen schritte zum [Piloten von Microsoft 365 mit nur wenigen E-Mail-Adressen ausführen.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?
<a name="BKMK_validateAcct"> </a>

Es gibt eine Reihe von Szenarios, in denen Sie lediglich die Domäne Ihrer Organisation bestätigen und keine Dienste einrichten müssen. Zum Beispiel, um Microsoft 365 nachzuweisen, dass Ihre Organisation für ein Schulabonnement qualifiziert ist.
  
Lesen Sie die Anweisungen unter "Überprüfen Ihrer [Microsoft 365-Domäne"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) zum Nachweis des Besitzes, der gemeinnützigen Organisation oder des Bildungsstatus oder zum Aktivieren von Yammer, um sicherzustellen, dass Sie alle erforderlichen Schritte abgeschlossen haben. Der Vorgang ist für jede Situation ein wenig anders. 
  
## <a name="services-not-working-with-your-domain"></a>Dienste funktionieren nicht mit Ihrer Domäne?
<a name="BKMK_Test"> </a>

Wir können Sie beim Diagnostizieren von Problemen mit der DNS-Einrichtung Ihrer Domäne unterstützen. In der Problembehandlung für Domänen in Microsoft 365 werden alle Einträge, die behoben werden müssen, und genau das, worauf die Einträge festgelegt werden müssen, gezeigt. 

> [!TIP]
> Haben Sie Ihr DNS ordnungsgemäß eingerichtet, aber E-Mail funktioniert nicht in Outlook auf Ihrem Desktop? Sehen Sie sich die verschiedenen E-Mail-Flussszenarien an, die Sie mit [Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) haben können, um sicherzustellen, dass Alles ordnungsgemäß für Ihr Unternehmen eingerichtet ist. Oder erhalten Sie weitere Hilfe zur Problembehandlung mit E-Mails hier: [Beheben von Outlook-Problemen.](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues) 
  
## <a name="accessing-your-website-isnt-working"></a>Sie können nicht auf Ihre Website zugreifen?
<a name="BKMK_Website"> </a>

Wenn Sie alle DNS-Probleme behoben haben, aber weiterhin Probleme auftreten, führen Sie eine der folgenden Aktionen aus.
  
- Benutzer können auf Ihre Website unter "www.mydomain.com" nicht zugreifen: [Diagnostizieren von Websiteproblemen](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
    
- Sie können Ihren A- oder #A0 nicht so aktualisieren, dass er auf Ihre Website verweisen kann: Aktualisieren benutzerdefinierter #A1 [in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)

## <a name="related-content"></a>Verwandte Inhalte

[Problembehandlung: Überwachen von Daten bei überprüften Domänenänderung](https://docs.microsoft.com/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

    
