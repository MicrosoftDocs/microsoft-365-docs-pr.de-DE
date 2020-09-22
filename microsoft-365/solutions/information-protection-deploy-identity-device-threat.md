---
title: Verwenden von Identitäts-, Geräte-und Bedrohungsschutz für die Datenschutzverordnung
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
ms.custom: ''
description: Verhindern von Verletzungen personenbezogener Daten mit Identitäts-, Geräte-und Bedrohungsschutz Diensten von Microsoft 365.
ms.openlocfilehash: a0efdcfe8e9d27e19b6cf1355a6d0943b7cdaa59
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195663"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Verwenden von Identitäts-, Geräte-und Bedrohungsschutz für die Datenschutzverordnung

Microsoft 365 bietet eine Reihe von Funktionen für Identitäts-, Geräte-und Bedrohungsschutz, die von Organisationen eingesetzt werden können, um die Einhaltung von Datenschutzbestimmungen zu unterstützen. In diesem Artikel wird beschrieben, was die Datenschutzbestimmungen in diesen Bereichen erfordern und enthält eine Liste der zugehörigen Microsoft 365-Features und-Dienste mit Links zu weiteren Informationen, die Ihnen dabei helfen, die Implementierungsanforderungen zu erfüllen.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Wie Identitäts-, Geräte-und Bedrohungsschutz mit der Datenschutzverordnung in Zusammenhangstehen

Während die Datenschutzbestimmungen sich in ihrer Besonderheit unterscheiden, ist die Essenz dessen, was Sie bezeichnen, im dsgvo-Artikel 5 (1) (f) aufgeführt, in dem Folgendes heißt: 

- Personenbezogene Daten werden in einer Weise verarbeitet, die eine angemessene Sicherheit der personenbezogenen Daten einschließlich des Schutzes vor unbefugter oder unrechtmäßiger Verarbeitung sowie vor versehentlichem Verlust, Zerstörung oder Beschädigung durch geeignete technische oder organisatorische Maßnahmen ("Integrität und Vertraulichkeit") gewährleistet.

Da Verletzungen von personenbezogenen Daten häufig durch Administrator-oder Endbenutzerkonto Kompromisse und böswilligen Systemzugriff verursacht werden. Beispielsweise kann ein Administratorkonto-hacken dazu führen, dass Kundenkreditkartennummern oder andere persönliche Informationen ausgefiltert werden. Der in Microsoft 365 allgemein empfohlene Identitäts-, Geräte-und Bedrohungsschutz sollte möglicherweise implementiert werden, was sich in der Konformitätsbewertung im Compliance-Manager widerspiegelt.

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>Verwenden der Ergebnisse ihrer Assessment Work and Compliance Manager

Compliance-Manager umfasst Identitäts-, Geräte-und Bedrohungsschutz mithilfe dieser Kategorien:

- Identity entspricht der **Steuerelement Zugriffs** Kategorie
- Gerät entspricht der Kategorie " **Geräte verwalten** "
- Bedrohungsschutz entspricht der Kategorie " **Schutz vor Bedrohungen** "
 
Wenn diese in unserem Beispielsatz mit vier wichtigen Datenschutzbestimmungen ausgewählt wurden, gibt Compliance-Manager 90 Verbesserungs Aktionen an, von denen die meisten eine "27" erzielt haben. Da eine solche große Zahl vom Compliance-Manager für diese Kategorien aufgerufen wird, werden einige der häufigsten hier aufgeführten als Referenz aufgeführt.

Verwenden Sie [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) für Identity und die Kategorie **Steuerelement Zugriff** , mit der Sie folgende Möglichkeiten haben:

- Implementieren der Wiedergabe-resistenten Authentifizierung (um "Menschen in der Mitte"-Angriffe zu verhindern)
- Blockieren Sie die Legacyauthentifizierung.
- Konfigurieren von Risikorichtlinien für Benutzer Risiken und Benutzeranmeldungen
- Aktivieren Sie den bedingten Zugriff und die mehrstufige Authentifizierung (MFA) für Administratoren und nicht-Administratoren.
- Konfigurieren und Erzwingen von Kennwortrichtlinien
- Einschränken des Zugriffs auf privilegierte Konten mit Azure AD privilegierten Identitätsverwaltung.
- Zugriff beim Beenden deaktivieren.
- Überwachen von Benutzerkonten und Statusänderungen.
- Überprüfen Sie die Rollengruppe und die administrativen Änderungen.

Verwenden Sie [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) für Geräte und die Kategorie **Manage Devices** , mit der Sie folgende Möglichkeiten haben:

- Gesperrte beschädigte und verwurzelte Mobile Geräte blockieren.
- Konfigurieren von InTune für die Verwaltung mobiler Geräte.
- Erstellen Sie Konformitätsrichtlinien für Android-, Ios-, macOS-und Windows-Geräte.
- Erstellen Sie ein Geräte Konfigurationsprofil für Android-, Ios-, macOS-und Windows-Geräte.
- Erstellen von App-Schutzrichtlinien für IOS und Windows.
- Informationen mit Sperrbildschirm verbergen.
- Implementieren von Kennwortrichtlinien für mobile Geräte.
- Erfordern, dass Mobile Geräte nach Inaktivität sperren.
- Erfordern, dass Mobile Geräte bei mehreren Anmeldefehlern gelöscht werden.

Verwenden Sie [Exchange Online Schutz und Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) für die Kategorie **Protect Against Threats** , mit der Sie folgende Schritte durchführen können:

- Aktivieren Sie die Sender Authentifizierung (SPF, DMARC und DKIM).
- Richten Sie Office 365 Anti-Phishing-Richtlinien für Advanced Threat Protection (ATP) ein.
- Implementieren Sie ATP-sichere Anlagen.
- Implementieren Sie ATP-sichere Links.
- Implementieren von Malware Erkennungs-und-Antwort Richtlinien
- Implementieren Sie ausgehende und eingehende Spam Richtlinien.

### <a name="references"></a>Referenzen

- [Allgemeine Identitäts- und Gerätezugriffsrichtlinien](../enterprise/identity-access-policies.md)
- [Schutz vor Bedrohungen in Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [Sichere Anlagen in ATP](../security/office-365-security/atp-safe-attachments.md)
- [ATP-sichere Links](../security/office-365-security/atp-safe-links.md)
- [Sichere Dokumente in ATP](../security/office-365-security/safe-docs.md)
