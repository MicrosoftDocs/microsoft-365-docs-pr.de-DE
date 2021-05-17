---
title: Verwenden von Domänen Verbinden
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Erfahren Sie, wie Sie mit Verbinden registrierungsfähigen Registrierungsstellen arbeiten und Ihre Domäne zu Microsoft 365.
ms.openlocfilehash: 5dec69f70273e6a9430ce5926ed07888e197adcd
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860655"
---
# <a name="using-domain-connect"></a>Verwenden von Domänen Verbinden

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.
  
[Mit Verbinden](https://www.domainconnect.org/) aktivierten Registrierungsstellen können Sie Ihre Domäne Microsoft 365 in einem Drei-Schritt-Prozess hinzufügen, der Minuten dauert. 
  
Im Assistenten werden wir nur überprüfen, ob Sie der Besitzer der Domäne sind. Anschließend werden die Einträge der Domäne automatisch eingerichtet, damit E-Mails bei Microsoft 365 eingehen und andere Microsoft 365-Dienste wie Microsoft Teams mit Ihrer Domäne verwendet werden können.
  
> [!NOTE]
> Stellen Sie sicher, dass alle Popupblocker in Ihrem Browser deaktiviert sind, bevor Sie den Setup-Assistenten starten.
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Domain Connect-Registrierungsstellen, die eine Microsoft 365-Integration ermöglichen

- [1&amp;1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer oder WildWestDomains (GoDaddy-Wiederverkäufer, die SecureServer DNS-Hosting verwenden)
    - [MadDog-Webhosting](https://maddogwebhosting.com/domains/)
    - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>Was geschieht mit meinen E-Mails und meiner Website?

Nachdem Sie das Setup abgeschlossen haben, wird der MX-Eintrag für Ihre Domäne aktualisiert, damit er auf Microsoft 365 verweist. Daraufhin gehen sämtliche E-Mails für Ihre Domäne bei Microsoft 365 ein. Stellen Sie sicher, dass Sie in Microsoft 365 Benutzer und Postfächer für alle Personen hinzugefügt und erstellt haben, die in Ihrer Domäne E-Mails erhalten.
  
Wenn Sie über eine Website verfügen, die Sie für Ihr Unternehmen verwenden, funktioniert diese weiterhin wie zuvor. Die Einrichtungsschritte für Domain Connect wirken sich nicht auf Ihre Website aus.
