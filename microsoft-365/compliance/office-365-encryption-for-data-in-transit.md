---
title: Verschlüsselung von Daten während der Übertragung
f1.keywords:
- NOCSH
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
description: Eine kurze Erläuterung der Art und Weise, wie Microsoft Daten während der Übertragung in ihren Rechenzentren verschlüsselt.
ms.openlocfilehash: 645294522185a631012c1654fbad96ba0a21b33e
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943304"
---
# <a name="encryption-for-data-in-transit"></a>Verschlüsselung von Daten während der Übertragung

Neben dem Schutz von Kundendaten im Rest verwendet Microsoft Verschlüsselungstechnologien zum Schutz von Kundendaten während der Übertragung. 

Die Daten werden in die Übertragung eingegangen:

- Wenn ein Clientcomputer mit einem Microsoft-Server kommuniziert;
- Wenn ein Microsoft-Server mit einem anderen Microsoft-Server kommuniziert; und
- Wenn ein Microsoft-Server mit einem nicht-Microsoft-Server kommuniziert (beispielsweise Exchange Online Zustellung von e-Mails an einen e-Mail-Server eines Drittanbieters).

Die Kommunikation zwischen Datencentern zwischen Microsoft-Servern erfolgt über TLS oder IPSec, und alle kundenbezogenen Server verhandeln mit TLS mit Clientcomputern eine sichere Sitzung (beispielsweise wird Exchange Online TLS 1,2 mit 256-Bit-Verschlüsselungsstärke verwendet (FIPS 140-2 Level 2-validiert). (Weitere Informationen finden Sie unter [technische Referenzdetails zur Verschlüsselung](technical-reference-details-about-encryption.md) für eine Liste der TLS-Verschlüsselungs Pakete, die von Office 365 unterstützt werden.) Dies gilt für die Protokolle, die von Clients wie Outlook, Skype for Business, Microsoft Teams und Outlook im Internet (beispielsweise http, POP3 usw.) verwendet werden.

Die öffentlichen Zertifikate werden von Microsoft IT SSL mit SSLAdmin, einem internen Microsoft-Tool zum Schutz der Vertraulichkeit von übermittelten Informationen, ausgestellt. Alle von Microsoft ausgestellten Zertifikate weisen mindestens 2048 Bits auf, und die WebTrust-Compliance erfordert SSLAdmin, um sicherzustellen, dass Zertifikate nur für öffentliche IP-Adressen ausgestellt werden, die Microsoft gehören. Alle IP-Adressen, die dieses Kriterium nicht erfüllen, werden durch einen Ausnahme Prozess weitergeleitet.

Alle Implementierungsdetails wie die verwendete TLS-Version, ob das Forward-Geheimnis (FS) aktiviert ist, die Reihenfolge von Verschlüsselungs Paketen usw. sind öffentlich verfügbar. Eine Möglichkeit, diese Details anzuzeigen, ist die Verwendung einer Drittanbieterwebsite wie [Qualys SSL Labs](https://www.ssllabs.com). Im folgenden finden Sie Links zu automatisierten Testseiten von Qualys, die Informationen für die folgenden Dienste anzeigen:

- [Office 365 Portal](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [Exchange Online](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [SharePoint Online](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [Skype for Business (SIP)](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [Skype for Business (im Internet)](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [Exchange Online Protection](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [Microsoft Teams](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

Für Exchange Online Schutz variieren URLs je nach Mandantennamen; Allerdings können alle Kunden Microsoft 365 mit **Microsoft-com.Mail.Protection.Outlook.com**testen.
