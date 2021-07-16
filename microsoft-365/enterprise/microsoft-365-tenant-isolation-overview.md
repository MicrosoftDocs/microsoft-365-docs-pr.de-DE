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
description: Dieser Artikel enthält eine Zusammenfassung, wie Microsoft die Mandantenisolation in Clouddiensten wie Microsoft 365 erzwingt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b52d936bb00ac0adef0baf428cbc5f9a8f8aba49
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464092"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Mandantenisolation in Microsoft 365

Einer der Hauptvorteile von Cloud Computing ist das Konzept einer gemeinsamen, gemeinsamen Infrastruktur für zahlreiche Kunden gleichzeitig, was zu Größenvorteilen führt. Dieses Konzept wird als *Mehrinstanzenfähigkeit* bezeichnet. Microsoft arbeitet kontinuierlich daran, sicherzustellen, dass die mehrmandantenfähigen Architekturen unserer Clouddienste Sicherheits-, Vertraulichkeits-, Datenschutz-, Integritäts- und Verfügbarkeitsstandards auf Unternehmensebene unterstützen.

Basierend auf den umfangreichen Investitionen und Erfahrungen, die von [Trustworthy Computing](https://www.microsoft.com/trust-center) und dem [Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/)gesammelt wurden, wurden Microsoft-Clouddienste mit der Annahme konzipiert, dass alle Mandanten potenziell gegen alle anderen Mandanten verfeinern, und wir haben Sicherheitsmaßnahmen implementiert, um zu verhindern, dass die Aktionen eines Mandanten die Sicherheit oder den Dienst eines anderen Mandanten beeinträchtigen oder auf den Inhalt eines anderen Mandanten zugreifen.

Die beiden Hauptziele der Aufrechterhaltung der Mandantenisolation in einer mehrinstanzenfähigen Umgebung sind:

1.    Verhindern von Lecks oder nicht autorisiertem Zugriff auf Kundeninhalte über Mandanten hinweg; Und
2.    Verhindern, dass sich aktionen eines Mandanten negativ auf den Dienst für einen anderen Mandanten auswirken

Es wurden mehrere Schutzformen in Microsoft 365 implementiert, um zu verhindern, dass Kunden Microsoft 365 Dienste oder Anwendungen gefährden oder nicht autorisierten Zugriff auf die Informationen anderer Mandanten oder des Microsoft 365 Systems selbst erhalten, einschließlich:

- Die logische Isolierung von Kundeninhalten innerhalb jedes Mandanten für Microsoft 365 Dienste wird durch Azure Active Directory Autorisierung und rollenbasierte Zugriffssteuerung erreicht.
- SharePoint Online bietet Datenisolationsmechanismen auf Speicherebene.
- Microsoft verwendet strenge physische Sicherheit, Hintergrundprüfung und eine mehrstufige Verschlüsselungsstrategie, um die Vertraulichkeit und Integrität von Kundeninhalten zu schützen. Alle Microsoft 365 Rechenzentren verfügen über biometrische Zugriffssteuerungen, wobei die meisten Handflächendrucke für den physischen Zugriff erforderlich sind. Darüber hinaus müssen alle IN den USA ansässigen Microsoft-Mitarbeiter im Rahmen des Einstellungsprozesses eine Standard-Hintergrundüberprüfung erfolgreich abschließen. Weitere Informationen zu den Steuerelementen, die für den administrativen Zugriff in Microsoft 365 verwendet werden, finden Sie unter [Microsoft 365 Administrative Access Controls](/compliance/assurance/assurance-administrative-access-controls-overview).
- Microsoft 365 verwendet dienstseitige Technologien, die Ruhe- und Transitinhalte von Kunden verschlüsseln, einschließlich BitLocker, Dateiverschlüsselung, TLS (Transport Layer Security) und Internet Protocol Security (IPsec). Spezifische Informationen zur Verschlüsselung in Microsoft 365 finden Sie unter [Datenverschlüsselungstechnologien in Microsoft 365](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md).

Zusammen bieten die oben aufgeführten Schutzmaßnahmen robuste logische Isolationskontrollen, die Bedrohungsschutz und Risikominderung bieten, die dem durch physische Isolation allein bereitgestellten entsprechen.

## <a name="related-links"></a>Links zu verwandten Themen

- [Isolierung und Zugriffssteuerung in Azure Active Directory](microsoft-365-isolation-in-azure-active-directory.md)
- [Mandantenisolation in Office Graph und Delve](microsoft-365-isolation-in-graph-and-delve.md)
- [Mandantenisolation in der Microsoft 365-Suche](microsoft-365-isolation-in-microsoft-365-search.md)
- [Ressourcenbeschränkungen](/compliance/assurance/assurance-resource-limits)
- [Überwachen und Testen von Mandantengrenzen](/compliance/assurance/assurance-monitoring-and-testing)
- [Isolierung und Zugriffskontrolle in Microsoft 365](microsoft-365-isolation-in-microsoft-365.md)