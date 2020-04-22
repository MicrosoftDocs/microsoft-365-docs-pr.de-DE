---
title: Office 365 Advanced Threat Protection
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 02/24/2020
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection umfasst sichere Anlagen, sichere Links, erweiterte Antiphishing-Tools, Berichterstellungstools und Threat Intelligence-Funktionen.
ms.openlocfilehash: 993939027962bd51ad4fdc3381c1e7d8ea4eddd4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634532"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) verfügen. Wenn Sie Outlook.com, Microsoft 365 Family oder Microsoft 365 Single verwenden und Informationen zu sicheren Links oder sicheren Anlagen in Outlook benötigen, lesen Sie [Erweiterte Outlook.com-Sicherheit für Microsoft 365-Abonnenten](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="overview"></a>Übersicht

Office 365 Advanced Threat Protection (ATP) schützt Ihre Organisation vor bösartigen Bedrohungen durch E-Mail-Nachrichten, Links (URLs) und Zusammenarbeitstools. ATP enthält folgende Elemente:

- **[Richtlinien zum Schutz vor Bedrohungen](#configure-atp-policies)**: Definieren Sie Richtlinien zum Schutz vor Bedrohungen, um den geeigneten Schutzgrad für Ihre Organisation festzulegen.

- **[Berichte](#view-office-365-atp-reports)**: Anzeigen von Echtzeitberichten, um die ATP-Leistung in Ihrer Organisation zu überwachen.

- **[Untersuchung von und Antwort auf Bedrohungen](#use-threat-investigation-and-response-capabilities)**: Verwenden Sie brandneue Tools, um Bedrohungen zu untersuchen, zu verstehen, zu simulieren und zu verhindern.

- **[Funktionen für automatische Untersuchung und Reaktion](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)**: Sparen Sie Zeit und Mühe beim Untersuchen und Beheben von Bedrohungen.

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP Plan 1 und Plan 2

In der folgenden Tabelle sind die Inhalte der einzelnen Pläne zusammengefasst.

|||
|---|---|
|**Office 365 ATP Plan 1**|**Office 365 ATP Plan 2**|
|Konfigurations-, Schutz- und Erkennungsfunktionen:<br/>• [Sichere Anlagen](atp-safe-attachments.md)<br/>• [Sichere Links](atp-safe-links.md)<br/>• [ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md)<br/>• [ATP Antiphishingschutz](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)<br/>• [Echtzeiterkennungen](threat-explorer.md)|Office 365 ATP Plan 1 – Funktionen<br/>--- plus ---<br/>Automatisierungs-, Untersuchungs-, Fehlerbehebungs- und Schulungsfunktionen:<br/>• [Sicherheitsrisiken-Nachverfolgung](threat-trackers.md)<br/>• [Sicherheitsrisiken-Explorer](threat-explorer.md)<br/>• [Automatische Untersuchung und Reaktion](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>• [Angriffssimulator](attack-simulator.md)|
|

- Office 365 ATP Plan 2 ist in Office 365 E5, Office 365 A5 und Microsoft 365 E5 enthalten.

- Office 365 ATP Plan 1 ist in Microsoft 365 Business Premium enthalten.

- Office 365 ATP Plan 1 und Office 365 ATP Plan 2 sind jeweils als Add-On für bestimmte Abonnements verfügbar. Weitere Informationen hierzu finden Sie unter [Funktionsverfügbarkeit bei ATP-Plänen](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- Wenn Ihr aktuelles Abonnement Office 365 ATP nicht enthält, [wenden Sie sich an den Vertrieb, um eine Testversion zu starten](https://go.microsoft.com/fwlink/p/?LinkId=518644) und zu testen, wie ATP für Ihre Organisation eingesetzt werden kann.

## <a name="configure-atp-policies"></a>Konfigurieren von ATP-Richtlinien

Mit Office 365 ATP kann das Sicherheitsteam Ihrer Organisation den Schutz durch Definition von Richtlinien im Security & Compliance Center konfigurieren. (Navigieren Sie zu [https://protection.office.com](https://protection.office.com) > **Bedrohungsverwaltung** > **Richtlinie**.)

> [!TIP]
> Eine schnelle Liste der zu definierenden Richtlinien finden Sie unter [Schutz vor Bedrohungen](protect-against-threats.md).

Die Richtlinien, die für Ihre Organisation definiert sind, bestimmen das Verhalten und den Schutzgrad für vordefinierte Bedrohungen. Richtlinienoptionen sind äußerst flexibel. Beispielsweise kann das Sicherheitsteam Ihrer Organisation einen fein abgestuften Bedrohungsschutz auf Benutzer-, Organisations-, Empfänger- und Domänenebene festlegen. Es ist wichtig, dass Sie Ihre Richtlinien regelmäßig überprüfen, da täglich neue Bedrohungen und Herausforderungen entstehen.

- **[ATP-sichere Anlagen](atp-safe-attachments.md)**: Bietet Zero-Day-Schutz, um Ihr Messagingsystem zu schützen, indem E-Mail-Anlagen auf schädliche Inhalte überprüft werden. Es leitet alle Nachrichten und Anlagen, die keine Viren- und Malware-Signaturen aufweisen, an eine spezielle Umgebung weiter, und verwendet dann Machine Learning- und Analysetechniken, um bösartige Absichten zu erkennen. Wenn keine verdächtigen Aktivitäten gefunden werden, wird die Nachricht an das Postfach weitergeleitet. Weitere Informationen hierzu finden Sie unter [Einrichten einer Richtlinie für Office 365 ATP-sichere Anlagen](set-up-atp-safe-attachments-policies.md).

- **[ATP-sichere Links](atp-safe-links.md)**: Bietet eine Zeit-auf-Klick-Überprüfung von URLs, beispielsweise in E-Mails und Office-Dateien. Der Schutz ist laufend aktiv und gilt für Ihre Messaging- und Office-Umgebung. Links werden bei jedem Klick gescannt: sichere Links bleiben verfügbar, bösartige Links werden dynamisch blockiert. Weitere Informationen hierzu finden Sie unter [Einrichten einer Richtlinie für Office 365 ATP-sichere Links](set-up-atp-safe-links-policies.md).

- **[ATP für SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md)**: Schützt Ihre Organisation, wenn Benutzer zusammenarbeiten und Dateien freigeben, indem es schädliche Dateien in Team-Websites und Dokumentbibliotheken identifiziert und blockiert. Weitere Informationen finden Sie unter [Office 365 ATP für SharePoint, OneDrive, und Microsoft Teams aktivieren](turn-on-atp-for-spo-odb-and-teams.md).

- **[ATP-Antiphishingschutz](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)**: Erkennt Versuche, Ihre Benutzer und internen oder benutzerdefinierten Domänen zu imitieren. Es wendet Machine Learning-Modelle und erweiterte Algorithmen zum Erkennen von Identitätswechsel an, um Phishing-Angriffe zu abzuwenden. Weitere Informationen hierzu finden Sie unter [Konfigurieren der ATP Antiphishing-Richtlinien in Office 365](configure-atp-anti-phishing-policies.md).

## <a name="view-office-365-atp-reports"></a>Anzeigen von Office 365 ATP-Berichten

Office 365 ATP enthält ein erweitertes [Reporting-Dashboard](view-reports-for-atp.md) zum Überwachen Ihrer ATP-Leistung. Sie können über **Berichte** > **Dashboard** im Security & Compliance Center darauf zugreifen.

Berichte werden in Echtzeit aktualisiert, sodass Sie die neuesten Erkenntnisse erhalten. Diese Berichte bieten zudem Empfehlungen und warnen Sie vor bevorstehenden Bedrohungen. Vordefinierte Berichte umfassen folgende Informationen:

- [Sicherheitsrisiken-Explorer (oder Echtzeit-Erkennung)](threat-explorer.md)

- [Threat Protection-Statusbericht](view-reports-for-atp.md#threat-protection-status-report)

- [ATP-Dateitypenbericht](view-reports-for-atp.md#atp-file-types-report)

- [ATP-Bericht zum Nachrichtenstatus](view-reports-for-atp.md#atp-message-disposition-report)

- ... und vieles mehr.

## <a name="use-threat-investigation-and-response-capabilities"></a>Bedrohungsuntersuchung- und Antwortfunktionen verwenden

Office 365 ATP Plan 2 enthält erstklassige [Bedrohungsuntersuchung- und Antwort-Tools](office-365-ti.md), die das Sicherheitsteam Ihrer Organisation in die Lage versetzen, böswillige Angriffe vorwegzunehmen, zu verstehen und zu verhindern.

- **[Bedrohungs-Tracker](threat-trackers.md)** liefern neueste Informationen zu vorherrschenden Internetsicherheitsproblemen. Beispielsweise können Sie Informationen zu der neuesten Malware anzeigen und Gegenmaßnahmen ergreifen, bevor diese zu einer tatsächlichen Bedrohung für Ihre Organisation werden. Verfügbare Tracker sind [beachtenswerte Tracker](threat-trackers.md#noteworthy-trackers), [Trend-Tracker](threat-trackers.md#trending-trackers), [nachverfolgte Abfragen](threat-trackers.md#tracked-queries) und [gespeicherte Abfragen](threat-trackers.md#saved-queries).

- Der **[Bedrohungs-Explorer (oder Echtzeit-Entdeckungen)](threat-explorer.md)** (auch als Explorer bezeichnet) ist ein Echtzeitbericht, der es Ihnen ermöglicht, aktuelle Bedrohungen zu erkennen und zu analysieren. Sie können Explorer so konfigurieren, dass Daten für benutzerdefinierte Zeiträume angezeigt werden.

- Der **[Angriffssimulator](attack-simulator.md)** ermöglicht Ihnen, realistische Angriffsszenarien in Ihrer Organisation auszuführen, um Sicherheitsrisiken zu erkennen. Es stehen Simulationen der aktuellen Angriffstypen zur Verfügung, einschließlich der Nutzung von Spear-Phishing-Angriffen auf Anmeldeinformationen und mittels Anhängen verübten Angriffe sowie Kennwort-Spray- und Brute-Force-Angriffen.

## <a name="save-time-with-automated-investigation-and-response"></a>Zeit sparen mit automatisierten Untersuchungen und Antworten

(**NEU!**) Bei der Untersuchung eines potenziellen Cyberangriffs ist Zeit von äußerster Wichtigkeit. Je früher Sie Bedrohungen erkennen und eindämmen können, desto besser für Ihre Organisation. AIR-Funktionen ([Automatische Untersuchung und Reaktion](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)) umfassen eine Reihe von Sicherheitsplaybooks, die automatisch, z. B. wenn eine Warnung ausgelöst wird, oder manuell, z. B. aus einer Explorer-Ansicht, gestartet werden können. AIR spart Ihrem Team für Sicherheitsvorgänge Zeit und Mühe beim effektiven und effizienten Eindämmen von Bedrohungen. Weitere Informationen hierzu finden Sie unter [AIR in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).

## <a name="permissions-required-to-use-atp-features"></a>Erforderliche Berechtigungen für die Verwendung von ATP-Funktionen

Für den Zugriff auf ATP-Features im Security & Compliance Center müssen Sie über eine entsprechende Rolle verfügen. Die folgende Tabelle enthält einige Beispiele:

|Rolle oder Rollengruppe|Ressourcen mit mehr Informationen|
|---------|---------|
|Globaler Administrator (kann in Azure Active Directory oder im Security & Compliance Center zugewiesen werden.) |[Informationen zu Microsoft 365-Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|Sicherheitsadministrator (kann in Azure Active Directory oder im Security & Compliance Center zugewiesen werden.) |[Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br><br/>[Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)|
|Exchange Online-Organisationsverwaltung (wird in Exchange Online zugewiesen)|[Berechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)<br><br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|
|Suchen und Löschen (wird nur im Security & Compliance Center zugewiesen) |[Berechtigungen im Security & Compliance Center] (permissions-in-the-security-and-compliance-center.md|

Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="get-office-365-atp"></a>Office 365 ATP abrufen

Office 365 ATP ist in bestimmten Abonnements wie Microsoft 365 E5, Office 365 E5, Office 365 A5 und Microsoft 365 Business Premium enthalten. Wenn Ihr Abonnement Office 365 ATP nicht enthält, können Sie ATP Plan 1 oder ATP Plan 2 als Add-On für bestimmte Abonnements erwerben. Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:

- Unter [Verfügbarkeit von Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) finden Sie eine Liste der Abonnements, die ATP-Pläne enthalten.

- Unter [Verfügbarkeit von Features in Advanced Threat Protection (ATP)-Plänen](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) finden Sie eine Liste der in Plan 1 und Plan 2 enthaltenen Features.

- Auf der Seite [Office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) können Sie Pläne vergleichen und Office 365 ATP erwerben.

- [Erste Schritte mit einer kostenlosen Testversion](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-office-365-atp"></a>Ausprobieren neuer Features in Office 365 ATP

Neue Features werden Office 365 ATP kontinuierlich hinzugefügt. Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:

- Die [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) liefert eine Liste neuer Features in Entwicklung und Rollout begriffen.

- Die [Dienstbeschreibung von Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) beschreibt Verfügbarkeit und Funktionen in ATP-Plänen.

## <a name="see-also"></a>Siehe auch

- [Microsoft Threat Protection](../mtp/microsoft-threat-protection.md)

- [Automatische Untersuchung und Reaktion (AIR) in Microsoft Threat Protection](../mtp/mtp-autoir.md)
