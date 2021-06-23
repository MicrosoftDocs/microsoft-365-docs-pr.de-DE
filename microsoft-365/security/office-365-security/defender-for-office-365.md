---
title: Microsoft Defender für Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Microsoft Defender für Office 365 umfasst „Sichere Anlagen“, „Sichere Links“, erweiterte Antiphishing-Werkzeuge, Berichterstellungswerkzeuge und Threat Intelligence-Funktionen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 66afaa56efa93faef3fcc6ff8346df24681a0a50
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083020"
---
# <a name="microsoft-defender-for-office-365"></a>Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) verfügen. Wenn Sie Outlook.com, Microsoft 365 Family oder Microsoft 365 Single verwenden und Informationen zu sicheren Links oder sicheren Anlagen in Outlook benötigen, lesen Sie [Erweiterte Outlook.com-Sicherheit für Microsoft 365-Abonnenten](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Microsoft Defender für Office 365 schützt Ihre Organisation vor bösartigen Bedrohungen durch E-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit. Defender für Office 365 enthält:

- **[Richtlinien zum Schutz vor Bedrohungen](#configure-microsoft-defender-for-office-365-policies)**: Definieren Sie Richtlinien zum Schutz vor Bedrohungen, um den geeigneten Schutzgrad für Ihre Organisation festzulegen.

- **[Berichte](#view-microsoft-defender-for-office-365-reports)**: Anzeigen von Echtzeitberichten, um die Leistung von Defender für Office 365 in Ihrer Organisation zu überwachen.

- **[Untersuchung von und Antwort auf Bedrohungen](#use-threat-investigation-and-response-capabilities)**: Verwenden Sie brandneue Tools, um Bedrohungen zu untersuchen, zu verstehen, zu simulieren und zu verhindern.

- **[Funktionen für automatische Untersuchung und Reaktion](office-365-air.md)**: Sparen Sie Zeit und Mühe beim Untersuchen und Beheben von Bedrohungen.

## <a name="interactive-guide-to-microsoft-defender-for-office-365"></a>Interaktiver Leitfaden für Microsoft Defender für Office 365
In diesem interaktiven Leitfaden lernen Sie, wie Sie Ihre Organisation mit Microsoft Defender für Office 365 schützen können. Sie erfahren, wie Sie mithilfe von Defender für Office 365 Schutzrichtlinien definieren, Bedrohungen für Ihre Organisation analysieren und auf Angriffe reagieren können.

[Sehen Sie sich den interaktiven Leitfaden an](https://aka.ms/MSDO-IG)

## <a name="getting-started"></a>Erste Schritte

Wenn Sie noch nicht mit Microsoft Defender für Office 365 vertraut sind, oder nach der Methode „Learning by *doing*“ vorgehen möchten, könnte es hilfreich für Sie sein, mithilfe dieses Artikels die Erstkonfiguration von Defender für Office 365 in einzelne Schritte aufzuteilen, Untersuchungen durchzuführen und sich Berichte anzuschauen. Folgendermaßen können Sie die erste Konfiguration in kleine Abschnitte aufteilen:

- Konfigurieren Sie alles mit ‚*Anti-*‘ im Namen.
  - Antischadsoftware
  - Antiphishing
  - Antispam
- Richten Sie alles mit ‚*sicher*‘ im Namen ein.
  - Sichere Links
  - Sichere Anlagen
- Sichern Sie die Workloads (z. B. SharePoint Online, OneDrive, und Teams)
- Schutz durch automatische Bereinigung zur Nullstunde

Wenn Sie durch praktische Beispiele lernen möchten, [klicken Sie auf diesen Link](protect-against-threats.md).

> [!NOTE]
> Microsoft Defender für Office 365 ist in zwei verschiedenen Plantypen verfügbar. Sie erkennen, dass Sie **Plan 1** haben, wenn Sie über ‚Echtzeiterkennnungen‘ verfügen, und **Plan 2**, wenn Sie über den Sicherheitsrisiken-Explorer verfügen. Ihr Plan hat Auswirkungen darauf, welche Tools Sie sehen. Daher sollten Sie sich sicher sein, welchen Plan Sie haben, bevor Sie mit dem Lernen anfangen.

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender für Office 365 Plan 1 und Plan 2

In der folgenden Tabelle sind die Inhalte der einzelnen Pläne zusammengefasst.

****

|Microsoft Defender für Office 365 Plan 1|Microsoft Defender für Office 365 Plan 2|
|---|---|
|Konfigurations-, Schutz- und Erkennungsfunktionen: <ul><li>[Sichere Anlagen](safe-attachments.md)</li><li>[Sichere Links](safe-links.md)</li><li>[Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li><li>[Anti-Phishing in Defender für Office 365-Schutz](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Echtzeiterkennungen](threat-explorer.md)</li></ul>|Microsoft Defender für Office 365 Plan 1 – Funktionen <br>--- plus ---<br> Automatisierungs-, Untersuchungs-, Fehlerbehebungs- und Schulungsfunktionen:<ul><li>[Bedrohungs-Tracker](threat-trackers.md)</li><li>[Sicherheitsrisiken-Explorer](threat-explorer.md)</li><li>[Automatische Untersuchung und Reaktion](office-365-air.md)</li><li>[Angriffssimulationstraining](attack-simulation-training.md)</li><li>[Kampagnenansichten](campaigns.md)</li></ul>|
|

- Microsoft Defender für Office 365 Plan 2 ist in Office 365 E5, Office 365 A5, Microsoft 365 E5 Security, und Microsoft 365 E5 enthalten.

- Microsoft Defender für Office 365 Plan 1 ist in Microsoft 365 Business Premium enthalten.

- Microsoft Defender für Office 365 Plan 1 und Microsoft Defender für Office 365 Plan 2 sind jeweils als Add-On für bestimmte Abonnements verfügbar. Weitere Informationen hierzu finden Sie unter [Verfügbarkeit von Features in Microsoft Defender für Office 365-Plänen](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- Das Feature [Sichere Dokumente](safe-docs.md) ist nur für Benutzer mit den Lizenzen für Microsoft 365 E5 oder Microsoft 365 E5 Security verfügbar (nicht in Microsoft Defender für Office 365-Plänen enthalten).

- Wenn Ihr aktuelles Abonnement Microsoft Defender für Office 365 nicht enthält, [wenden Sie sich an den Vertrieb, um eine Testversion zu starten](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html) und zu testen, wie Defender für Office 365 für Ihre Organisation eingesetzt werden kann.

## <a name="configure-microsoft-defender-for-office-365-policies"></a>Konfigurieren von Microsoft Defender für Office 365-Richtlinien

Mit Microsoft Defender für Office 365 kann das Sicherheitsteam Ihrer Organisation den Schutz durch die Definition von Richtlinien im Microsoft 365 Defender Portal konfigurieren. (Wechseln Sie zu <https://security.microsoft.com> \> **E-Mail und Zusammenarbeit** \> **Richtlinien und Regeln** \> **Bedrohungsrichtlinien**).

Erfahren Sie mehr, in dem Sie [dieses Video](https://www.youtube.com/watch?v=vivvTmWJ_3c) ansehen.

> [!TIP]
> Eine schnelle Liste der zu definierenden Richtlinien finden Sie unter [Schutz vor Bedrohungen](protect-against-threats.md).

## <a name="defender-for-office-365-policies"></a>Microsoft Defender für Office 365-Richtlinien

Die Richtlinien, die für Ihre Organisation definiert sind, bestimmen das Verhalten und den Schutzgrad für vordefinierte Bedrohungen. Richtlinienoptionen sind äußerst flexibel. Beispielsweise kann das Sicherheitsteam Ihrer Organisation einen fein abgestuften Bedrohungsschutz auf Benutzer-, Organisations-, Empfänger- und Domänenebene festlegen. Es ist wichtig, dass Sie Ihre Richtlinien regelmäßig überprüfen, da täglich neue Bedrohungen und Herausforderungen entstehen.

- **[Sichere Anlagen](safe-attachments.md)**: Bietet Zero-Day-Schutz, um Ihr Messagingsystem zu schützen, indem E-Mail-Anlagen auf schädliche Inhalte überprüft werden. Es leitet alle Nachrichten und Anlagen, die keine Viren- und Malware-Signaturen aufweisen, an eine spezielle Umgebung weiter, und verwendet dann Machine Learning- und Analysetechniken, um bösartige Absichten zu erkennen. Wenn keine verdächtigen Aktivitäten gefunden werden, wird die Nachricht an das Postfach weitergeleitet. Weitere Informationen hierzu finden Sie unter [Einrichten einer Richtlinie für sichere Anlagen](set-up-safe-attachments-policies.md).

- **[Sichere Links](safe-links.md)**: Bietet eine Zeit-auf-Klick-Überprüfung von URLs, beispielsweise in E-Mails und Office-Dateien. Der Schutz ist laufend aktiv und gilt für Ihre Messaging- und Office-Umgebung. Links werden bei jedem Klick gescannt: sichere Links bleiben verfügbar, bösartige Links werden dynamisch blockiert. Weitere Informationen hierzu finden Sie unter [Einrichten einer Richtlinie für sichere Links](set-up-safe-links-policies.md).

- **[Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md)**: Schützt Ihre Organisation, wenn Benutzer zusammenarbeiten und Dateien freigeben, indem es schädliche Dateien in Team-Websites und Dokumentbibliotheken identifiziert und blockiert. Weitere Informationen finden Sie unter [Defender für Office 365 für SharePoint, OneDrive und Microsoft Teams aktivieren](turn-on-mdo-for-spo-odb-and-teams.md).

- **[Antiphishingschutz in Microsoft Defender für Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)**: Erkennt Versuche, die Identität von Benutzern und internen oder benutzerdefinierten Domänen anzunehmen. Es wendet Machine Learning-Modelle und erweiterte Algorithmen zum Erkennen von Identitätswechsel an, um Phishing-Angriffe zu abzuwenden. Weitere Informationen hierzu finden Sie unter [Konfigurieren von Antiphishing-Richtlinien in Microsoft Defender für Office 365](configure-mdo-anti-phishing-policies.md).

## <a name="view-microsoft-defender-for-office-365-reports"></a>Anzeigen von Microsoft Defender für Office 365-Berichten

Microsoft Defender für Office 365 enthält [Berichte](view-reports-for-mdo.md) zur Überwachung von Defender für Office 365. Sie können auf die Berichte im Microsoft 365 Defender-Portal unter **Berichte** \> **E-Mail & Zusammenarbeit** \> **E-Mail- & Zusammenarbeitsberichte** oder direkt unter <https://security.microsoft.com/securityreports>zugreifen.

Berichte werden in Echtzeit aktualisiert, sodass Sie die neuesten Erkenntnisse erhalten. Diese Berichte bieten zudem Empfehlungen und warnen Sie vor bevorstehenden Bedrohungen. Vordefinierte Berichte umfassen folgende Informationen:

- [Sicherheitsrisiken-Explorer (oder Echtzeit-Erkennung)](threat-explorer.md)
- [Threat Protection-Statusbericht](view-reports-for-mdo.md#threat-protection-status-report)
- ... und vieles mehr.

## <a name="use-threat-investigation-and-response-capabilities"></a>Bedrohungsuntersuchung- und Antwortfunktionen verwenden

Microsoft Defender für Office 365 Plan 2 enthält erstklassige [Tools für die Untersuchung von und Reaktion auf Bedrohungen](office-365-ti.md), die das Sicherheitsteam Ihrer Organisation in die Lage versetzen, böswillige Angriffe vorwegzunehmen, zu verstehen und zu verhindern.

- **[Bedrohungs-Tracker](threat-trackers.md)** liefern neueste Informationen zu vorherrschenden Internetsicherheitsproblemen. Beispielsweise können Sie Informationen zu der neuesten Malware anzeigen und Gegenmaßnahmen ergreifen, bevor diese zu einer tatsächlichen Bedrohung für Ihre Organisation werden. Verfügbare Tracker sind [beachtenswerte Tracker](threat-trackers.md#noteworthy-trackers), [Trend-Tracker](threat-trackers.md#trending-trackers), [nachverfolgte Abfragen](threat-trackers.md#tracked-queries) und [gespeicherte Abfragen](threat-trackers.md#saved-queries).

- Der **[Bedrohungs-Explorer (oder Echtzeit-Entdeckungen)](threat-explorer.md)** (auch als Explorer bezeichnet) ist ein Echtzeitbericht, der es Ihnen ermöglicht, aktuelle Bedrohungen zu erkennen und zu analysieren. Sie können Explorer so konfigurieren, dass Daten für benutzerdefinierte Zeiträume angezeigt werden.

- Das **[Angriffssimulationstraining](attack-simulation-training.md)** ermöglicht Ihnen, realistische Angriffsszenarien in Ihrer Organisation auszuführen, um Sicherheitsrisiken zu erkennen. Es stehen Simulationen der aktuellen Angriffstypen zur Verfügung, einschließlich der Nutzung von Spear-Phishing-Angriffen auf Anmeldeinformationen und mittels Anhängen verübten Angriffe sowie Kennwort-Spray- und Brute-Force-Angriffen.

## <a name="save-time-with-automated-investigation-and-response"></a>Zeit sparen mit automatisierten Untersuchungen und Antworten

(**NEU!**) Bei der Untersuchung eines potenziellen Cyberangriffs ist Zeit von äußerster Wichtigkeit. Je früher Sie Bedrohungen erkennen und eindämmen können, desto besser für Ihre Organisation. AIR-Funktionen ([Automatische Untersuchung und Reaktion](office-365-air.md)) umfassen eine Reihe von Sicherheitsplaybooks, die automatisch, z. B. wenn eine Warnung ausgelöst wird, oder manuell, z. B. aus einer Explorer-Ansicht, gestartet werden können. AIR spart Ihrem Team für Sicherheitsvorgänge Zeit und Mühe beim effektiven und effizienten Eindämmen von Bedrohungen. Weitere Informationen hierzu finden Sie unter [AIR in Office 365](office-365-air.md).

## <a name="permissions-required-to-use-microsoft-defender-for-office-365-features"></a>Berechtigungen, die für die Verwendung von Microsoft Defender für Office 365-Funktionen erforderlich sind

Um auf Microsoft Defender für Office 365-Features zugreifen zu können, muss Ihnen eine entsprechende Rolle zugewiesen sein. Die folgende Tabelle enthält einige Beispiele:

<br>

****

|Rolle oder Rollengruppe|Ressourcen mit mehr Informationen|
|---|---|
|Globaler Administrator (Organisationsverwaltung)|Sie können diese Rolle in Azure Active Directory oder im Microsoft 365 Defender-Portal zuweisen. Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md).|
|Sicherheitsadministrator|Sie können diese Rolle in Azure Active Directory oder im Microsoft 365 Defender-Portal zuweisen. Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md).|
|Organisationsverwaltung in Exchange Online|[Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo) <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|Suchen und Löschen|Diese Rolle ist nur im Microsoft 365 Defender-Portal oder im Microsoft 365 Compliance Center verfügbar. Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md) und unter [Berechtigungen im Microsoft 365 Compliance Center](../../compliance/microsoft-365-compliance-center-permissions.md).|
|||

## <a name="get-microsoft-defender-for-office-365"></a>So erhalten Sie Microsoft Defender für Office 365

Microsoft Defender für Office 365 ist in bestimmten Abonnements wie Microsoft 365 E5, Office 365 E5, Office 365 A5 und Microsoft 365 Business Premium enthalten. Wenn Ihr Abonnement Defender für Office 365 nicht enthält, können Sie Defender für Office 365 Plan 1 oder Defender für Office 365 Plan 2 als Add-On für bestimmte Abonnements erwerben. Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:

- [Verfügbarkeit von Microsoft Defender für Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) für eine Auflistung der Abonnements, die Defender für Office 365-Pläne umfassen.

- [Verfügbarkeit von Features in Microsoft Defender für Office 365-Plänen](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) für eine Liste der Features, die in Plan 1 und 2 enthalten sind.

- [Die richtige Version von Microsoft Defender für Office 365 auswählen](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content), um Pläne zu vergleichen und Defender für Office 365 zu erwerben.

- [Erste Schritte mit einer kostenlosen Testversion](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-microsoft-defender-for-office-365"></a>Neue Features in Microsoft Defender für Office 365

Es werden fortwährend neue Features zu Microsoft Defender für Office 365 hinzugefügt. Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:

- Die [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=Microsoft%2CDefender%2Cfor%2COffice%2C365) liefert eine Liste neuer Features in Entwicklung und Rollout begriffen.

- Unter [Microsoft Defender für Office 365 – Dienstbeschreibung](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) finden Sie eine Beschreibung von Funktionen und deren Verfügbarkeit in Defender für Office 365-Plänen.

## <a name="see-also"></a>Weitere Informationen

- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
- [Automatische Untersuchung und Reaktion (AIR, Automated Investigation and Response) in Microsoft 365 Defender](../defender/m365d-autoir.md)
