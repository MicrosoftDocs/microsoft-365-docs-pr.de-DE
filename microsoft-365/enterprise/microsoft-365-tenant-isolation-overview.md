---
title: Mandantenisolation in Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Dieser Artikel enthält eine Zusammenfassung darüber, wie Microsoft die Mandantenisolation in Clouddiensten wie Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7c5be65186b75f6056a64b776e4f0d25bcd55eb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923076"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Mandantenisolation in Microsoft 365

Einer der wichtigsten Vorteile von Cloud Computing ist das Konzept einer gemeinsamen, gemeinsamen Infrastruktur für zahlreiche Kunden gleichzeitig, was zu Größenvorteilen führt. Dieses Konzept wird als *multi-tenancy bezeichnet.* Microsoft arbeitet kontinuierlich daran, sicherzustellen, dass die mehrmandantenfähigen Architekturen unserer Clouddienste Sicherheits-, Vertraulichkeits-, Datenschutz-, Integritäts- und Verfügbarkeitsstandards auf Unternehmensebene unterstützen.

Basierend auf den erheblichen Investitionen und Erfahrungen aus [Trustworthy Computing](https://www.microsoft.com/trust-center) und dem [Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/)wurden Microsoft-Clouddienste mit der Annahme entworfen, dass alle Mandanten potenziell schädlich für alle anderen Mandanten sind, und wir haben Sicherheitsmaßnahmen implementiert, um zu verhindern, dass sich die Aktionen eines Mandanten auf die Sicherheit oder den Dienst eines anderen Mandanten oder auf den Inhalt eines anderen Mandanten ausdähen.

Die beiden Hauptziele für die Beibehaltung der Mandantenisolation in einer Mehr-Mandanten-Umgebung sind:

1.    Verhindern von Lecks oder unbefugtem Zugriff auf Kundeninhalte über Mandanten hinweg; und
2.    Verhindern, dass die Aktionen eines Mandanten den Dienst für einen anderen Mandanten beeinträchtigen

Mehrere Arten von Schutz wurden Microsoft 365 implementiert, um zu verhindern, dass Kunden Microsoft 365 Dienste oder Anwendungen kompromittieren oder nicht autorisierten Zugriff auf die Informationen anderer Mandanten oder des Microsoft 365-Systems selbst erhalten, einschließlich:

- Die logische Isolation von Kundeninhalten innerhalb jedes Mandanten für Microsoft 365 wird durch eine Azure Active Directory und rollenbasierte Zugriffssteuerung erreicht.
- SharePoint Online bietet Datenisolationsmechanismen auf Speicherebene.
- Microsoft verwendet strenge physische Sicherheit, Hintergrundprüfungen und eine mehrschichtige Verschlüsselungsstrategie, um die Vertraulichkeit und Integrität von Kundeninhalten zu schützen. Alle Microsoft 365 verfügen über biometrische Zugriffssteuerungen, bei denen die meisten Handflächendrucke erforderlich sind, um physischen Zugriff zu erhalten. Darüber hinaus müssen alle in den USA ansässigen Microsoft-Mitarbeiter eine Standardhintergrundprüfung im Rahmen des Einstellungsprozesses erfolgreich abschließen. Weitere Informationen zu den Steuerelementen, die für den Administratorzugriff in Microsoft 365 verwendet werden, finden Sie unter [Microsoft 365 Administrative Access Controls](/compliance/assurance/assurance-administrative-access-controls-overview).
- Microsoft 365 verwendet dienstseitige Technologien zum Verschlüsseln von Kundeninhalten im Ruhe- und Transitbereich, einschließlich BitLocker, Dateiverschlüsselung, Transport Layer Security (TLS) und Internet Protocol Security (IPsec). Spezifische Informationen zur Verschlüsselung in Microsoft 365 finden Sie unter [Data Encryption Technologies in Microsoft 365](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md).

Zusammen bieten die oben aufgeführten Schutzelemente robuste logische Isolationssteuerelemente, die bedrohungsschutz und -abschwächung äquivalent zu dem bieten, der allein durch physische Isolation bereitgestellt wird.

## <a name="related-links"></a>Links zu verwandten Themen

- [Isolierung und Zugriffssteuerung in Azure Active Directory](microsoft-365-isolation-in-azure-active-directory.md)
- [Mandantenisolation in Office Graph und Delve](microsoft-365-isolation-in-graph-and-delve.md)
- [Mandantenisolation in der Microsoft 365-Suche](microsoft-365-isolation-in-microsoft-365-search.md)
- [Mandantenisolation in Office 365 Video](microsoft-365-isolation-in-microsoft-365-video.md)
- [Ressourcenbeschränkungen](/compliance/assurance/assurance-resource-limits)
- [Überwachen und Testen von Mandantengrenzen](/compliance/assurance/assurance-monitoring-and-testing)
- [Isolierung und Zugriffskontrolle in Microsoft 365](microsoft-365-isolation-in-microsoft-365.md)