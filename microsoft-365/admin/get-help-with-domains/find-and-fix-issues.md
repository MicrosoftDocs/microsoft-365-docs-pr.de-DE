---
title: Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Erfahren Sie, wie Sie Probleme einkreisen können, die beim Einrichten einer benutzerdefinierten Domäne auftreten. Stellen Sie zunächst sicher, dass die DNS-Einträge ordnungsgemäß eingerichtet sind.
ms.openlocfilehash: a93318d54b950b908319fe50a0cfedefe8586036
ms.sourcegitcommit: 8edad75338cf74712ca1ab5d6631b9b52ff54410
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2020
ms.locfileid: "43115973"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records-in-office-365"></a>Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Das Einrichten Ihrer Domäne für die Zusammenarbeit mit Office 365 kann eine Herausforderung darstellen. Das DNS-System kann sich bei der Arbeit als recht anspruchsvoll erweisen, und außerdem wirkt sich die DNS-Einrichtung für Ihre Domäne auf wichtige geschäftliche Aktivitäten wie z. B. E-Mail aus!

> [!NOTE]
> Sie können nach Problemen mit Ihrer Domäne suchen, indem Sie deren Status überprüfen. Wechseln Sie zu **Setup** > **Domänen** , und zeigen Sie die Benachrichtigungen in der Spalte **Status** an. Wenn ein Problem angezeigt wird, wählen Sie „Weitere Aktionen“ aus (die drei Punkte), und wählen Sie dann **Integrität überprüfen**aus. In dem Bereich, der nun geöffnet wird, werden alle mit Ihrer Domäne auftretenden Probleme beschrieben.
  
## <a name="whats-going-on"></a>Was ist los?

- [Sie können Ihre Domäne nicht überprüfen?](#cant-verify-your-domain)
    
- [Outlook funktioniert nicht?](#outlook-isnt-working)
    
- [Die E-Mail-Adressen aller Benutzer wurden auf Office 365 umgestellt, Sie wollten jedoch, dass nur IHRE E-Mail-Adresse umgestellt wird?](#everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch)

- [Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?](#cant-confirm-non-profit-or-school-account-status)

- [Dienste funktionieren nicht mit Ihrer Domäne?](#services-not-working-with-your-domain)
    
- [Sie können nicht auf Ihre Website zugreifen?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Sie können Ihre Domäne nicht überprüfen?
<a name="BKMK_verify"> </a>

Es gibt einige häufige Gründe dafür, dass die Domänenüberprüfung nicht wie gewünscht funktioniert:
  
1. **Der Wert des Prüfeintrags ist nicht ganz korrekt.** Vergewissern Sie sich, dass Sie den exakten Wert kopiert und in den TXT-Prüfeintrag bei Ihrem DNS-Host eingefügt haben. Ein häufiges Problem ist, dass der Teil "MS=" des Eintrags fehlt. Diese Angabe ist ebenfalls erforderlich! 
    
2. **Der Eintrag wurde nicht gespeichert.** Bei einigen DNS-Hosts müssen Sie einen zusätzlichen Schritt ausführen, um die Zonendatei zu speichern (in der der DNS-Eintrag gespeichert ist), damit der Eintrag im Internet aktualisiert wird. Stellen Sie sicher, dass Sie die Änderungen gespeichert haben, damit der Eintrag von Office 365 angezeigt und überprüft werden kann. 
    
3. **Der Eintrag wurde noch nicht im Internet aktualisiert.** In der Regel dauert es nur ein paar Minuten, bis wir den neuen Eintrag sehen können, aber gelegentlich kann es auch ein paar Stunden dauern. 
    
## <a name="outlook-isnt-working"></a>Outlook funktioniert nicht?
<a name="BKMK_OutlookBroken"> </a>

Wenn Sie Ihren MX-Eintrag und andere DNS-Einträge für Ihre Domäne ordnungsgemäß eingerichtet haben, aber Ihr E-Mail-Programm nicht funktioniert, können wir Ihnen dabei helfen, [Ihre Probleme mit Outlook zu beheben](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).
  
## <a name="everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch"></a>Die E-Mail-Adressen aller Benutzer wurden auf Office 365 umgestellt, Sie wollten jedoch, dass nur IHRE E-Mail-Adresse umgestellt wird?
<a name="BKMK_EmailSwitched"> </a>

Wenn Sie Ihre Domäne zu Office 365 hinzufügen, wird in der Regel der MX-Eintrag der Domäne (durch Sie oder Office 365) so aktualisiert, dass er auf Office 365 verweist und dass ALLE an diese Domäne gesendeten E-Mails von Office 365 empfangen werden.  Sorgen Sie dafür, dass Sie in Office 365 Postfächer für alle Personen erstellt haben, die in Ihrer Domäne über E-Mail verfügen, BEVOR Sie den MX-Eintrag ändern. 
  
Sie möchten nicht für jeden in Ihrer Domäne E-Mails nach Office 365 verschieben? Sie können stattdessen [ein Pilotprojekt mit Office 365 und nur wenigen E-Mail-Adressen in die Wege leiten](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx). 
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?
<a name="BKMK_validateAcct"> </a>

Es gibt eine Reihe von Szenarios, in denen Sie lediglich die Domäne Ihrer Organisation bestätigen und keine Dienste einrichten müssen. Beispielsweise um Office 365 nachzuweisen, dass Ihre Organisation zu einem Schul-Abonnement berechtigt ist.
  
Lesen Sie den Leitfaden in [Überprüfen der Office 365-Domäne zum Bestätigen des Besitzrechts, des gemeinnützigen oder Ausbildungsstatus oder zum Aktivieren von Yammer](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590), um sicherzustellen, dass Sie alle erforderlichen Schritte ausgeführt haben. Der Vorgang ist für jede Situation ein wenig anders. 
  
## <a name="services-not-working-with-your-domain"></a>Dienste funktionieren nicht mit Ihrer Domäne?
<a name="BKMK_Test"> </a>

Wir können Sie beim Diagnostizieren von Problemen mit der DNS-Einrichtung Ihrer Domäne unterstützen. Die Problembehandlung bei Domänen in Office 365 zeigt alle Einträge an, die korrigiert werden müssen, und gibt genau an, wie die Einträge festgelegt werden müssen. 

> [!TIP]
> Sie haben Ihr DNS ordnungsgemäß eingerichtet, aber E-Mail-Nachrichten funktionieren in Outlook auf dem Desktop nicht? Lesen Sie [Unterschiedliche Szenarien für den E-Mail-Fluss in Office 365](https://go.microsoft.com/fwlink/?LinkId=787530), um sicherzustellen, dass alles für Ihr Unternehmen ordnungsgemäß eingerichtet ist. Darüber hinaus finden Sie hier weitere Hilfe zur Problembehandlung im Zusammenhang mit E-Mails: [Beheben von Problemen mit Outlook](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx). 
  
## <a name="accessing-your-website-isnt-working"></a>Sie können nicht auf Ihre Website zugreifen?
<a name="BKMK_Website"> </a>

Wenn Sie alle DNS-Probleme behoben haben, aber weiterhin Probleme auftreten, führen Sie eine der folgenden Aktionen aus.
  
- Benutzer können auf Ihre Website unter "www.mydomain.com" nicht zugreifen: [Diagnostizieren von Websiteproblemen](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)
    
- Sie können Ihren A-Eintrag oder CNAME-Eintrag nicht so aktualisieren, dass er auf Ihre Website verweist: [Aktualisieren von benutzerdefinierten DNS-Einträgen in Office 365](../dns/add-or-edit-custom-dns-records.md)
    
