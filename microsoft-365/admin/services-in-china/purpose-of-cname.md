---
title: Was ist der Zweck des CNAME-Eintrags für MSOID in Office 365?
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Erfahren Sie mehr über den CNAME-Eintrag "MSOID" in Office 365, der Sie zum besten Server für Authentifizierungsprozesse leitet, sodass Sie eine schnellere Antwort erhalten.
monikerRange: o365-21vianet
ms.openlocfilehash: fdf728dcaebf65485b1eaed9b41e49f5327e9a41
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254126"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>Was ist der Zweck des CNAME-Eintrags für MSOID in Office 365?

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
> [!NOTE]
> Das folgende gilt nur für * * Office 365 betrieben von 21Vianet.
  
[] Möglicherweise wundern Sie sich, warum Sie den CNAME-Eintrag "MSOID" in Office 365 hinzufügen müssen. Dieser Eintrag muss für alle benutzerdefinierten Domänen hinzugefügt werden, ganz gleich, welches Abonnement Sie verwenden. Warum benötigen Sie diesen Eintrag? Zur Beantwortung dieser Frage müssen wir ein wenig in die Technik einsteigen, aber es geht im Wesentlichen darum, bei bestimmten Authentifizierungsprozessen die Umleitung auf den besten Server zu erreichen, damit Sie schnellere Antworten erhalten.
  
Zur Technik: Wenn Sie eine Clientanwendung ausführen, die mit Office 365 zusammenarbeitet, wie Skype for Business Online, Outlook, Windows PowerShell oder das Microsoft Azure Active Directory-Synchronisierungstool, müssen Ihre Anmeldeinformationen authentifiziert werden. Office 365 verwendet einen CNAME-Eintrag, um auf den korrekten Authentifizierungsendpunkt für Ihren Standort zu verweisen, wodurch bei der Authentifizierung eine schnelle Reaktionszeit sichergestellt wird.
  
Wenn dieser CNAME-Eintrag für Ihre Domäne fehlt, verwenden die Anwendungen einen standardmäßigen Authentifizierungsendpunkt in den USA, was bedeutet, dass die Authentifizierung ggf. langsamer erfolgt. Wenn dieser CNAME-Eintrag nicht ordnungsgemäß konfiguriert ist, wenn es beispielsweise einen Tippfehler im Feld **Verweist auf die Adresse** gibt, sind diese Anwendungen nicht in der Lage, eine Authentifizierung durchzuführen.
  
 **Wenn Office 365 die DNS-Einträge Ihrer Domäne verwaltet,** Office 365 richtet diesen CNAME-Eintrag für Sie ein. 
  
 **Wenn Sie DNS-Einträge für Ihre Domäne auf Ihrem DNS-Host verwalten,** erstellen Sie diesen Datensatz selbst, indem Sie [die Anweisungen für den DNS-Host befolgen](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx).
  
Wenn Sie eine Office 365-Bereitstellung planen und mehr über alle DNS-Einträge erfahren möchten, die Sie möglicherweise hinzufügen oder aktualisieren müssen, lesen Sie diese in [Bezug auf: externe Domänennamen-System Einträge für Office 365](https://go.microsoft.com/fwlink/?LinkId=579013).
  

