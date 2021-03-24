---
title: Verwenden von Identitäts-, Geräte- und Bedrohungsschutz für Datenschutzbestimmungen
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Verhindern von Verletzungen personenbezogener Daten mit Identitäts-, Geräte- und Bedrohungsschutzdiensten von Microsoft 365.
ms.openlocfilehash: 145b8a59f7eafb95adf71dc24613ee15ef1c2cca
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052350"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Verwenden von Identitäts-, Geräte- und Bedrohungsschutz für Datenschutzbestimmungen

Microsoft 365 bietet eine Reihe von Identitäts-, Geräte- und Bedrohungsschutzfunktionen, die Organisationen zur Einhaltung datenschutzbezogener Compliancebestimmungen verwenden können. In diesem Artikel wird beschrieben, was die Datenschutzbestimmungen in diesen Bereichen erfordern, und enthält eine Liste der zugehörigen Microsoft 365-Features und -Dienste mit Links zu weiteren Informationen, mit denen Sie Implementierungsanforderungen erfüllen können.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Beziehung zwischen Identitäts-, Geräte- und Bedrohungsschutz in Bezug auf Datenschutzbestimmungen

Während die Datenschutzbestimmungen in ihrer Spezifizität variieren, ist das Wesentliche dessen, was sie fordern, in Artikel 5 Absatz 1 (f) der DSGVO enthalten, in dem es heißt, dass:

- Personenbezogene Daten werden auf eine Weise verarbeitet, die eine angemessene Sicherheit der personenbezogenen Daten gewährleistet, einschließlich des Schutzes vor nicht autorisierter oder unrechtmäßiger Verarbeitung und vor versehentlichem Verlust, Zerstörung oder Schaden, unter Verwendung geeigneter technischer oder organisatorischer Maßnahmen ("Integrität und Vertraulichkeit").

Da Verletzungen personenbezogener Daten häufig durch administrative oder Endbenutzerkontoverstöße und böswilligen Systemzugriff verursacht werden. Beispielsweise kann ein Administratorkonto-Hack zu einer Exfiltration von Kunden-Kreditkartennummern oder anderen persönlichen Informationen führen. Alle allgemein empfohlenen Identitäts-, Geräte- und Bedrohungsschutz, die mit Microsoft 365 verfügbar sind, sollten implementiert werden, was sich in Ihrer Compliance-Bewertung widerspiegelt, die im Compliance-Manager zu finden ist.

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>Verwenden der Ergebnisse Ihrer Bewertungsarbeit und des Compliance-Managers

Compliance Manager umfasst Identitäts-, Geräte- und Bedrohungsschutz unter Verwendung der folgenden Kategorien:

- Identität entspricht der **Kategorie "Zugriffssteuerung"**
- Gerät entspricht der **Kategorie Geräte** verwalten
- Bedrohungsschutz entspricht der **Kategorie Schutz vor Bedrohungen**
 
Wenn diese in unserem Beispielsatz mit vier wichtigen Datenschutzbestimmungen ausgewählt werden, gibt der Compliance-Manager 90 Verbesserungsmaßnahmen an, von denen die meisten als "27" bezeichnet werden. Da eine so große Anzahl vom Compliance-Manager für diese Kategorien aufgerufen wird, werden einige der gängigen Kategorien hier aufgeführt.

Verwenden [Sie Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) für die Identität und die Kategorie Control **Access,** mit der Sie:

- Implementieren der wiedergabesicheren Authentifizierung (um Angriffe von "Man in der Mitte" zu verhindern)
- Blockieren Sie die Legacyauthentifizierung.
- Konfigurieren von Risikorichtlinien für Benutzerrisiken und Benutzer-Anmelderisiken.
- Aktivieren Sie bedingten Zugriff und mehrstufige Authentifizierung (MFA) für Administratoren und Nicht-Administratoren.
- Konfigurieren und Erzwingen von Kennwortrichtlinien.
- Einschränken des Zugriffs auf privilegierte Konten mit Azure AD Privileged Identity Management.
- Deaktivieren sie den Zugriff bei Beendigung.
- Überwachen von Benutzerkonten und Statusänderungen.
- Überprüfen von Rollengruppen- und administrativen Änderungen.

Verwenden [Sie Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) für Geräte und die Kategorie **Geräte** verwalten, mit der Sie:

- Blockieren von beschädigten und verankerten mobilen Geräten im Jail.
- Konfigurieren von Intune für die Verwaltung mobiler Geräte.
- Erstellen von Compliancerichtlinien für Android-, iOS-, macOS- und Windows-Geräte.
- Erstellen Sie ein Gerätekonfigurationsprofil für Android-, iOS-, macOS- und Windows-Geräte.
- Erstellen von App-Schutzrichtlinien für iOS und Windows.
- Verbergen von Informationen mit Sperrbildschirm.
- Implementieren sie Kennwortrichtlinien für mobile Geräte.
- Mobile Geräte müssen bei Inaktivität gesperrt werden.
- Mobile Geräte müssen bei mehreren Anmeldefehlern wischen.

Verwenden [Sie Exchange Online Protection und Microsoft Defender für Office 365](../security/defender-365-security/defender-for-office-365.md) für die Kategorie **Schutz** vor Bedrohungen, mit der Sie:

- Aktivieren der Absenderauthentifizierung (SPF, DMARC und DKIM).
- Richten Sie Microsoft Defender für Office 365-Antiphishingrichtlinien ein.
- Implementieren sie sichere Anlagen.
- Implementieren sicherer Links.
- Implementieren von Richtlinien für die Erkennung und Reaktion auf Schadsoftware.
- Implementieren Sie ausgehende und eingehende Spamrichtlinien.

### <a name="references"></a>Verweise:

- [Allgemeine Identitäts- und Gerätezugriffsrichtlinien](../security/defender-365-security/identity-access-policies.md)
- [Schutz vor Bedrohungen in Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [Sichere Anlagen](../security/defender-365-security/safe-attachments.md)
- [Sichere Links](../security/defender-365-security/safe-links.md)
- [Sichere Dokumente](../security/defender-365-security/safe-docs.md)
