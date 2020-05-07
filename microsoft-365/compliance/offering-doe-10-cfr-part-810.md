---
title: US DOE 10 CFR Part 810
description: Kunden, die den Export Kontrollanforderungen von US DOE 10 CFR Part 810 unterliegen, können Azure Government verwenden.
keywords: Microsoft 365, Compliance, Angebote
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: b34babe60781858b85a3c76280c2126094442851
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44066438"
---
# <a name="us-doe-10-cfr-part-810"></a>US DOE 10 CFR Part 810

## <a name="microsoft-and-doe-10-cfr-part-810"></a>Microsoft und DOE 10 CFR Part 810

Microsoft Azure Regierung kann Kunden, die den Export Kontrollanforderungen des US Department of Energy (DOE) 10 CFR Part 810 unterliegen, durch zwei Autorisierungen unterstützen:

- Die FedRAMP hohe provisorische Autorisierung für den Betrieb (P-ATO), ausgestellt vom Joint Authorization Board (Jab)
- Die provisorischen Berechtigungen Level 4 und 5 der Defense Information Systems-Agentur des Verteidigungsministeriums (Department of Defense, DoD)

FedRAMP bietet eine geeignete Basis, um sicherzustellen, dass Azure Government Kerninfrastruktur-und Virtualisierungstechnologie sowie Dienste wie COMPUTE, Storage und Netzwerke bereitstellt, die mit strengen NIST-Steuerelementen konzipiert sind. Diese helfen, die Anforderungen an die Trennung von Kundendaten zu erfüllen und sichere Verbindungen mit lokalen Kundenumgebungen zu ermöglichen.

Darüber hinaus ist Azure Government eine Community-Cloud der US-Regierung, die physisch von der Azure-Cloud getrennt ist. Es bietet zusätzliche Zusicherungen hinsichtlich spezifischer Anforderungen im Hinblick auf die Hintergrundprüfung durch die US-Regierung, einschließlich bestimmter Kontrollen, die den Zugriff auf Informationen und Systeme einschränken, um die US-Bürger unter Azure Operationspersonal zu überprüfen.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft Cloud Services im Leistungsumfang

- [Azure-Regierung](https://aka.ms/AzureCompliance)
- Intune

## <a name="how-to-implement"></a>Implementierung

- [NERC CIP-Standards & Cloud Computing](https://aka.ms/AzureNERC): Leitfaden für elektrische Hilfsprogramme und registrierte Entitäten, die Arbeitslasten für Azure oder Azure Government bereitstellen.

## <a name="about-doe-10-cfr-part-810"></a>Informationen zu Doe 10 CFR Part 810

Die Export Kontrollverordnung des US-Energieministeriums (DOE) [10 CFR Teil 810](https://www.govinfo.gov/content/pkg/FR-2015-02-23/pdf/2015-03479.pdf) regelt die Ausfuhr von nicht klassifizierter Nukleartechnologie und-Hilfe. Dadurch wird sichergestellt, dass nukleare Technologien, die aus den USA exportiert werden, nur für friedliche Zwecke verwendet werden. Der überarbeitete Abschnitt 810 (letzte Regel) wurde im März 2015 wirksam und wird von der [nationalen Nuclear Security Administration](https://www.energy.gov/nnsa/national-nuclear-security-administration)verwaltet. In Abschnitt 810,6 heißt es, dass eine spezifische Doe-Autorisierung sowohl für Unterstützungs-als auch für die Übertragung von sensiblen Nukleartechnologien, die "Allgemein autorisiert" sind, sowie für Personen erforderlich ist, die eine spezifische Autorisierung erfordern (beispielsweise für Unterstützung bei sensiblen Nukleartechnologien wie Anreicherung und Produktion von schwer Wasser).

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Gelten die Bestimmungen des 10 CFR-Teils 110 der US Nuclear Regulatory Commission für Azure Government?**

Nein. Die [US Nuclear Regulatory Commission](https://www.nrc.gov/) (NRC) regelt den [Export und Import](https://www.nrc.gov/about-nrc/ip/export-import.html) von Nuklearanlagen und dazugehörigen Geräten und Materialien unter [10 CFR Teil 110](https://www.nrc.gov/reading-rm/doc-collections/cfr/part110/). Der NRC reguliert nicht die Nukleartechnologie und Unterstützung im Zusammenhang mit diesen Elementen, die der Zuständigkeit der DOE unterliegen. Daher gelten die Bestimmungen des NRC 10 CFR Part 110 nicht für Azure Government.

**Wie kann ich nachweisen, dass ich doe 10 CFR Part 810 einhalte?**

Wenn Ihre Organisation Daten für Azure Government bereitstellt, können Sie sich auf die Azure Government FedRAMP High P-ATO als Beweis dafür verlassen, dass Sie Daten in einer entsprechend eingeschränkten Art und Weise verarbeiten. Sie sind jedoch für das erhalten von Doe-Autorisierungen ihrer eigenen Systeme verantwortlich, einschließlich der Verwendung von Cloud-Diensten.

**Was sind meine Aufgaben bei der Klassifizierung von Daten, die in Azure Government bereitgestellt werden?**

Kunden, die Daten für Azure Government bereitstellen, sind für den eigenen Sicherheits Klassifizierungsprozess verantwortlich. Für Kundendaten, die DOE-Exportkontrollen unterliegen, wird das Klassifizierungssystem durch die UCNI-Steuerelemente (nicht klassifizierte kontrollierte Nuklear Informationen) erweitert, die von Abschnitt 148 des [US-Atomgesetzes](https://www.epa.gov/laws-regulations/summary-atomic-energy-act)festgelegt wurden.

## <a name="resources"></a>Ressourcen

- [Azure Cloud Services und US-Export Steuerelemente](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=c24c11f2-2cd4-444a-9160-19762855ad3a&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)
- [Microsoft und FedRAMP](offering-fedramp.md)
- [Microsoft und DoD](offering-dod-disa-l2-l4-l5.md)
- [Microsoft Government Cloud](https://www.microsoft.com/enterprise/government)
- [Compliance im Microsoft Trust Center](https://www.microsoft.com/trust-center/compliance/compliance-overview)
