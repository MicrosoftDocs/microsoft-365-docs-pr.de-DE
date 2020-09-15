---
title: DSGVO für Office-Server
description: Erfahren Sie, wie Sie mit Anforderungen der Datenschutz-Grundverordnung (DSGVO) in lokalen Office-Servern umgehen.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5ee42a12f65ad5eff0a33ef2b61d328ebdc7af3e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547331"
---
# <a name="gdpr-for-office-on-premises-servers"></a>DSGVO für lokale Office-Server

Im Rahmen der Datenschutz-Grundverordnung (DSGVO) werden Anforderungen für Unternehmen zum Schutz personenbezogener Daten und zur angemessenen Reaktion auf Datensubjektanforderungen eingeführt. Diese Artikelreihe bietet empfohlene Ansätze für lokale Workloads:

- [SharePoint Server](gdpr-for-sharepoint-server.md)

- [Exchange Server](gdpr-for-exchange-server.md)

- [Skype for Business Server](gdpr-for-skype-for-business-server.md)

- [Project Server](gdpr-for-project-server.md)

- [Office Web Apps Server und Office Online Server](gdpr-for-office-online-server.md)

- [Lokale Dateifreigaben](gdpr-for-on-premises-file-shares.md)

Weitere Informationen zu der DSGVO und dazu, wie Microsoft Ihnen helfen kann, finden Sie im [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview
).

Vor der Arbeit mit lokalen Daten wenden Sie sich an die Teams Ihrer Rechts- und Compliance-Abteilung, um Hilfestellung und Informationen zu vorhandenen Klassifizierungsschemata und Ansätzen für die Arbeit mit personenbezogenen Daten zu erhalten. Microsoft bietet Empfehlungen für die Entwicklung und Erweiterung von Klassifizierungsschemata im DSGVO-bezogenen Data Discovery Toolkit von Microsoft unter [ https://aka.ms/gdprpartners ](<https://aka.ms/gdprpartners>). In diesem Toolkit werden auch Vorgehensweisen beschrieben, mit denen Sie lokale Daten in die Cloud verschieben können, wo Sie bei Bedarf komplexere Daten-Governance-Funktionen verwenden können. In den Artikeln in diesem Abschnitt werden Empfehlungen für Daten gegeben, die lokal gespeichert bleiben sollen.

In der folgenden Abbildung werden empfohlene Funktionen aufgeführt, die in jedem dieser Workloads zum Ermitteln, Klassifizieren, Schützen und Überwachen personenbezogener Daten verwendet werden können. Weitere Informationen finden Sie in den Artikeln in diesem Abschnitt.

![Diagramm, das beschreibt, wie personenbezogene Daten über Workloads hinweg ermittelt, klassifiziert, geschützt und überwacht werden können](../media/gdpr-for-office-servers-image1.png)

## <a name="illustration-description"></a>Beschreibung der Abbildung

Für Zwecke der Barrierefreiheit enthält die folgende Tabelle die gleichen Beispiele wie die Abbildung.

****

|Aktion|Windows Server-Dateifreigaben|SharePoint Server|Exchange Server|Skype for Business|Project Server|
|---|---|---|---|---|---|
|Ermitteln|Azure Information Protection-Scanner<sup>\*</sup>|Suchcenter oder eDiscovery (nach Klassifizierung der Daten) <br/><br/> Azure Information Protection-Scanner<sup>\*</sup>|Exchange-eDiscovery-Portal|Exchange-eDiscovery-Portal|SQL-Skripts für Ermittlung und Export|
|Klassifizieren|Azure Information Protection-Scanner<sup>\*</sup> <br/><br/> Typen vertraulicher Informationen in Office 365|Azure Information Protection-Scanner<sup>\*</sup> <br/><br/> Typen vertraulicher Informationen in Office 365|Aufbewahrungstags und Aufbewahrungsrichtlinien in Exchange|Aufbewahrungstags und Aufbewahrungsrichtlinien in Exchange||
|Schützen||Regeln zur Verhinderung von Datenverlust für Exchange Server <br/><br/> Berechtigungen, IRM – Schutz für Bibliotheken|Regeln zur Verhinderung von Datenverlust für Exchange Server <br/><br/> IRM-Integration in Exchange Server|||
|Überwachen|Protokolle in SIEM-Tools integrieren|Protokolle in SIEM-Tools integrieren|Protokolle in SIEM-Tools integrieren|Protokolle in SIEM-Tools integrieren|Protokolle in SIEM-Tools integrieren|
|

<sup>\*</sup> Durch Schutz wird die Datei verschlüsselt. Folglich kann der SharePoint Server die Typen vertraulicher Informationen in geschützten Dateien nicht finden.
