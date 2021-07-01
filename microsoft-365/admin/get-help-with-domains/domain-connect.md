---
title: Verwenden von Domänen-Verbinden
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
description: Erfahren Sie, wie Sie mit Domänen-Verbinden aktivierten Registrierungsstellen arbeiten und Ihre Domäne Microsoft 365 hinzufügen.
ms.openlocfilehash: 12e1f227c0a157414b56fd04f99e5460a1eb05d4
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228013"
---
# <a name="using-domain-connect"></a>Verwenden von Domänen-Verbinden

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.

Registrierungsstellen, die [Domain Connect](https://www.domainconnect.org/) unterstützen, ermöglichen es Ihnen, Ihre Domäne in einem dreistufigen Prozess zu Microsoft 365 hinzuzufügen, der nur wenige Minuten dauert.

Im Assistenten werden wir nur überprüfen, ob Sie der Besitzer der Domäne sind. Anschließend werden die Einträge der Domäne automatisch eingerichtet, damit E-Mails bei Microsoft 365 eingehen und andere Microsoft 365-Dienste wie Microsoft Teams mit Ihrer Domäne verwendet werden können.

> [!NOTE]
> Stellen Sie sicher, dass alle Popupblocker in Ihrem Browser deaktiviert sind, bevor Sie den Setup-Assistenten starten.

## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Domain Connect-Registrierungsstellen, die eine Microsoft 365-Integration ermöglichen

- [1&amp;1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [Wordpress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer oder WildWestDomains (GoDaddy-Wiederverkäufer, die SecureServer DNS-Hosting verwenden)
  - [Mad Dog Web Hosting](https://maddogwebhosting.com/domains/)
  - ["Untername"](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>Was geschieht mit meinen E-Mails und meiner Website?

Nachdem Sie das Setup abgeschlossen haben, wird der MX-Eintrag für Ihre Domäne aktualisiert, damit er auf Microsoft 365 verweist. Daraufhin gehen sämtliche E-Mails für Ihre Domäne bei Microsoft 365 ein. Stellen Sie sicher, dass Sie in Microsoft 365 Benutzer und Postfächer für alle Personen hinzugefügt und erstellt haben, die in Ihrer Domäne E-Mails erhalten.

Wenn Sie über eine Website verfügen, die Sie für Ihr Unternehmen verwenden, funktioniert diese weiterhin wie zuvor. Die Einrichtungsschritte für Domain Connect wirken sich nicht auf Ihre Website aus.
