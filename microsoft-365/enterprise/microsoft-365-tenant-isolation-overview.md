---
title: Mandanten Isolierung in Microsoft 365
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
description: Dieser Artikel enthält eine Zusammenfassung darüber, wie Microsoft die Mandanten Isolierung in Cloud-Diensten wie Microsoft 365 erzwingt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7aca35fc61d03e94225375fcf67970e13dd691c9
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332688"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Mandanten Isolierung in Microsoft 365

Einer der Hauptvorteile von Cloud Computing ist das Konzept einer gemeinsam genutzten gemeinsamen Infrastruktur für zahlreiche Kunden gleichzeitig, die zu Größenvorteilen führt. Dieses Konzept wird als *mehr Mandanten*Fähigkeit bezeichnet. Microsoft arbeitet kontinuierlich daran, sicherzustellen, dass die mehrmandantenfähigen Architekturen unserer Clouddienste Sicherheits-, Vertraulichkeits-, Datenschutz-, Integritäts- und Verfügbarkeitsstandards auf Unternehmensebene unterstützen.

Basierend auf den bedeutenden Investitionen und Erfahrungen, die von [Trustworthy Computing](https://www.microsoft.com/trust-center) und dem [Sicherheits Entwicklungslebenszyklus](https://www.microsoft.com/securityengineering/sdl/)gesammelt wurden, wurden Microsoft Cloud-Dienste so konzipiert, dass alle Mandanten potenziell feindlich gegenüber allen anderen Mandanten sind, und wir haben Sicherheitsmaßnahmen implementiert, um zu verhindern, dass die Aktionen eines Mandanten die Sicherheit oder den Dienst eines anderen Mandanten beeinträchtigen oder auf den Inhalt eines anderen Mandanten zugreifen.

Die zwei Hauptziele der Verwaltung der mandantenisolation in einer Umgebung mit mehreren Mandanten sind:

1.    Verhindern von Auslaufen oder nicht autorisiertem Zugriff auf Kunden Inhalte über Mandanten hinweg; und
2.    Verhindern, dass die Aktionen eines Mandanten sich negativ auf den Dienst für einen anderen Mandanten auswirken

In Microsoft 365 wurden mehrere Schutzformen implementiert, um zu verhindern, dass Kunden Microsoft 365-Dienste oder-Anwendungen kompromittieren oder nicht autorisierten Zugriff auf die Informationen anderer Mandanten oder des Microsoft 365-Systems erhalten, einschließlich:

- Die logische Isolierung von Kundeninhalten innerhalb der einzelnen Mandanten für Microsoft 365-Dienste wird durch Azure Active Directory Autorisierung und rollenbasierte Zugriffssteuerung erreicht.
- SharePoint Online bietet Daten Isolationsmechanismen auf Speicherebene.
- Microsoft verwendet strenge physische Sicherheit, Hintergrundprüfung und eine mehrstufige Verschlüsselungsstrategie, um die Vertraulichkeit und Integrität von Kundeninhalten zu schützen. Alle Microsoft 365-Rechenzentren verfügen über biometrische Zugriffssteuerungen, wobei die meisten Palm Prints benötigen, um physischen Zugriff zu erhalten. Darüber hinaus müssen alle in den USA ansässigen Microsoft-Mitarbeiter eine standardmäßige Hintergrundüberprüfung im Rahmen des Einstellungsprozesses erfolgreich abschließen. Weitere Informationen zu den Steuerelementen, die für den administrativen Zugriff in Microsoft 365 verwendet werden, finden Sie unter [Microsoft 365 administrative Access Controls](microsoft-365-administrative-access-controls-overview.md).
- Microsoft 365 verwendet dienstseitige Technologien zum Verschlüsseln von Kundeninhalten im Rest und in der Übertragung, einschließlich BitLocker, Verschlüsselung per Datei, Transport Layer Security (TLS) und IPSec (Internet Protocol Security). Spezifische Details zur Verschlüsselung in Microsoft 365 finden Sie unter [Datenverschlüsselungstechnologien in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).

Zusammen bieten die oben aufgeführten Schutzmechanismen zuverlässige logische Isolierungs Steuerelemente, die den Schutz und die Minderung von Bedrohungen ermöglichen, gleichbedeutend mit der von der physischen Isolierung allein bereitgestellten.

## <a name="related-links"></a>Links zu verwandten Themen

- [Isolierung und Zugriffssteuerung in Azure Active Directory](microsoft-365-isolation-in-azure-active-directory.md)
- [Mandantenisolation in Office Graph und Delve](microsoft-365-isolation-in-graph-and-delve.md)
- [Mandantenisolation in der Microsoft 365-Suche](microsoft-365-isolation-in-microsoft-365-search.md)
- [Mandantenisolation in Office 365 Video](microsoft-365-isolation-in-microsoft-365-video.md)
- [Ressourcenbeschränkungen](microsoft-365-resource-limits.md)
- [Überwachen und Testen von Mandantengrenzen](microsoft-365-monitoring-and-testing.md)
- [Isolierung und Zugriffskontrolle in Microsoft 365](microsoft-365-isolation-in-microsoft-365.md)
