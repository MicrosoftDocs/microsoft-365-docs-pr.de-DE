---
title: Office 365 Verschlüsselung für Daten während der Übertragung
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 'Zusammenfassung: eine kurze Erläuterung der Art und Weise, wie Microsoft Daten bei der Übertragung verschlüsselt.'
ms.openlocfilehash: ba1317a0a2a685d0f3ac2216939d04e402503e49
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082269"
---
# <a name="office-365-encryption-for-data-in-transit"></a>Office 365 Verschlüsselung für Daten während der Übertragung

Neben dem Schutz von Kundendaten im Rest verwendet Microsoft Verschlüsselungstechnologien, um Office 365 Kundendaten während der Übertragung zu schützen. 

Die Daten werden in die Übertragung eingegangen:

- Wenn ein Clientcomputer mit einem Office 365 Server kommuniziert;
- Wenn ein Office 365 Server mit einem anderen Office 365-Server kommuniziert; und
- Wenn ein Office 365 Server mit einem nicht Office 365-Server kommuniziert (beispielsweise Exchange Online Zustellung von e-Mails an einen fremden e-Mail-Server).

Die Kommunikation zwischen Datencentern zwischen Office 365 Servern erfolgt über TLS oder IPSec, und alle kundenorientierten Server verhandeln mit TLS mit Clientcomputern eine sichere Sitzung (beispielsweise wird Exchange Online TLS 1,2 mit 256-Bit-Verschlüsselungsstärke verwendet (FIPS 140-2 Ebene 2 – überprüft). (Siehe [technische Referenzdetails zur Verschlüsselung in Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) für eine Liste der von Office 365 unterstützten TLS-Verschlüsselungs Pakete.) Dies gilt für die Protokolle, die von Clients wie Outlook, Skype for Business und Outlook im Internet (beispielsweise http, POP3 usw.) verwendet werden.

Die öffentlichen Zertifikate werden von Microsoft IT SSL mit SSLAdmin, einem internen Microsoft-Tool zum Schutz der Vertraulichkeit von übermittelten Informationen, ausgestellt. Alle von Microsoft ausgestellten Zertifikate weisen mindestens 2048 Bits auf, und die [WebTrust](http://www.webtrust.org/homepage-documents/item70372.pdf) -Compliance erfordert SSLAdmin, um sicherzustellen, dass Zertifikate nur für öffentliche IP-Adressen ausgestellt werden, die Microsoft gehören. Alle IP-Adressen, die dieses Kriterium nicht erfüllen, werden durch einen Ausnahme Prozess weitergeleitet.

Alle Implementierungsdetails wie die verwendete TLS-Version, ob das Forward-Geheimnis (FS) aktiviert ist, die Reihenfolge von Verschlüsselungs Paketen usw. sind öffentlich verfügbar. Eine Möglichkeit, diese Details anzuzeigen, ist die Verwendung einer Drittanbieterwebsite wie Qualys SSL Labs (www.ssllabs.com). Im folgenden finden Sie Links zu automatisierten Testseiten von Qualys, die Informationen für die folgenden Dienste anzeigen:

- [Office 365 Portal](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [Exchange Online](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [SharePoint Online](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [Skype for Business (SIP)](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [Skype for Business (im Internet)](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [Exchange Online Protection](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [Microsoft Teams](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

Für Exchange Online Schutz variieren URLs je nach Mandantennamen; Allerdings können alle Kunden Office 365 mit **Microsoft-com.Mail.Protection.Outlook.com**testen.
