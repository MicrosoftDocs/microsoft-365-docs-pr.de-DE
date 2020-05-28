---
title: Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Erfahren Sie, wie Sie Probleme einkreisen können, die beim Einrichten einer benutzerdefinierten Domäne auftreten. Stellen Sie zunächst sicher, dass die DNS-Einträge ordnungsgemäß eingerichtet sind.
ms.openlocfilehash: e3c66e10a673d840cfddad81a057739b6dfac721
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399944"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Das Einrichten Ihrer Domäne für die Zusammenarbeit mit Microsoft 365 kann eine Herausforderung darstellen. Das DNS-System ist Nitpicky, mit dem Sie arbeiten können, und das DNS-Setup für Ihre Domäne betrifft wichtige geschäftliche Aktivitäten wie e-Mail!

> [!NOTE]
> Sie können nach Problemen mit Ihrer Domäne suchen, indem Sie deren Status überprüfen. Wechseln Sie zu **Setup**  >  **Domänen** , und zeigen Sie die Benachrichtigungen in der Spalte **Status** an. Wenn ein Problem angezeigt wird, wählen Sie „Weitere Aktionen“ aus (die drei Punkte), und wählen Sie dann **Integrität überprüfen**aus. In dem Bereich, der nun geöffnet wird, werden alle mit Ihrer Domäne auftretenden Probleme beschrieben.
  
## <a name="whats-going-on"></a>Was ist los?

- [Sie können Ihre Domäne nicht überprüfen?](#cant-verify-your-domain)
    
- [Outlook funktioniert nicht?](#outlook-isnt-working)
    
- [Alle e-Mails wurden zu Microsoft 365 gewechselt, und Sie wollten nur, dass Ihre e-Mail gewechselt wird?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?](#cant-confirm-non-profit-or-school-account-status)

- [Dienste funktionieren nicht mit Ihrer Domäne?](#services-not-working-with-your-domain)
    
- [Sie können nicht auf Ihre Website zugreifen?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Sie können Ihre Domäne nicht überprüfen?
<a name="BKMK_verify"> </a>

Es gibt einige häufige Gründe dafür, dass die Domänenüberprüfung nicht wie gewünscht funktioniert:
  
1. **Der Wert des Prüfeintrags ist nicht ganz korrekt.** Vergewissern Sie sich, dass Sie den exakten Wert kopiert und in den TXT-Prüfeintrag bei Ihrem DNS-Host eingefügt haben. Ein häufiges Problem ist, dass der Teil "MS=" des Eintrags fehlt. Diese Angabe ist ebenfalls erforderlich! 
    
2. **Der Datensatz wurde nicht gespeichert.** Bei einigen DNS-Hosts müssen Sie einen zusätzlichen Schritt ausführen, um die Zonendatei (in der der DNS-Eintrag gespeichert ist) zu speichern, damit Sie über das Internet aktualisiert wird. Stellen Sie sicher, dass Sie Ihre Änderungen gespeichert haben, damit Microsoft 365 den Datensatz sehen und überprüfen kann. 
    
3. **Der Eintrag wurde noch nicht im Internet aktualisiert.** In der Regel dauert es nur ein paar Minuten, bis wir den neuen Eintrag sehen können, aber gelegentlich kann es auch ein paar Stunden dauern. 
    
## <a name="outlook-isnt-working"></a>Outlook funktioniert nicht?
<a name="BKMK_OutlookBroken"> </a>

Wenn Sie Ihren MX-Eintrag und andere DNS-Einträge für Ihre Domäne ordnungsgemäß eingerichtet haben, aber Ihr E-Mail-Programm nicht funktioniert, können wir Ihnen dabei helfen, [Ihre Probleme mit Outlook zu beheben](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>Alle e-Mails wurden zu Microsoft 365 gewechselt, und Sie wollten nur, dass Ihre e-Mail gewechselt wird?
<a name="BKMK_EmailSwitched"> </a>

Wenn Sie Ihre Domäne zu Microsoft 365 hinzufügen, wird der MX-Eintrag Ihrer Domäne in der Regel aktualisiert (von Ihnen oder von Microsoft 365), um auf Microsoft 365 zu deuten, und alle e-Mails, die an diese Domäne gesendet werden, beginnen mit Microsoft 365. Stellen Sie sicher, dass Sie in Microsoft 365 Postfächer für alle Benutzer erstellt haben, die e-Mails in Ihrer Domäne haben, bevor Sie den MX-Eintrag ändern.
  
Was geschieht, wenn Sie e-Mails nicht für alle Benutzer Ihrer Domäne nach Microsoft 365 bewegen möchten? Sie können [stattdessen ein Pilotprojekt von Microsoft 365 mit nur wenigen e-Mail-Adressen](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)ausführen.
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?
<a name="BKMK_validateAcct"> </a>

Es gibt eine Reihe von Szenarios, in denen Sie lediglich die Domäne Ihrer Organisation bestätigen und keine Dienste einrichten müssen. Um beispielsweise Microsoft 365 zu beweisen, dass Ihre Organisation für ein Schul Abonnement qualifiziert ist.
  
Lesen Sie den Leitfaden unter [verify your Microsoft 365 Domain to prove Ownership, Non-Profit oder Education Status, oder aktivieren Sie jammern](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) , um sicherzustellen, dass Sie alle erforderlichen Schritte abgeschlossen haben. Der Vorgang ist für jede Situation ein wenig anders. 
  
## <a name="services-not-working-with-your-domain"></a>Dienste funktionieren nicht mit Ihrer Domäne?
<a name="BKMK_Test"> </a>

Wir können Sie beim Diagnostizieren von Problemen mit der DNS-Einrichtung Ihrer Domäne unterstützen. In der Domänen-Problembehandlung in Microsoft 365 werden alle Datensätze angezeigt, die repariert werden müssen, und genau das, worauf die Datensätze festgelegt werden müssen. 

> [!TIP]
> Haben Sie Ihren DNS richtig eingerichtet, aber e-Mails funktionieren nicht in Outlook auf Ihrem Desktop? Sehen Sie sich die [unterschiedlichen Nachrichtenfluss Szenarien an, die Sie mit Microsoft 365 haben können](https://www.microsoft.com/?ref=go) , um sicherzustellen, dass Sie die Dinge ordnungsgemäß für Ihr Unternehmen eingerichtet haben. Weitere Informationen zur Problembehandlung mit e-Mails finden Sie hier: [Beheben von Outlook-Problemen](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>Sie können nicht auf Ihre Website zugreifen?
<a name="BKMK_Website"> </a>

Wenn Sie alle DNS-Probleme behoben haben, aber weiterhin Probleme auftreten, führen Sie eine der folgenden Aktionen aus.
  
- Benutzer können auf Ihre Website unter "www.mydomain.com" nicht zugreifen: [Diagnostizieren von Websiteproblemen](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
    
- Sie können einen Eintrag oder CNAME-Eintrag nicht so aktualisieren, dass er auf Ihre Website verweist: [Aktualisieren von benutzerdefinierten DNS-Einträgen in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)
    
