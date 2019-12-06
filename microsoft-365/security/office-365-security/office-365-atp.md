---
title: Office 365 Advanced Threat Protection
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/03/2019
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
ms.openlocfilehash: 65f123e77d5b38163dfe4e8971426d8a1135b571
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866707"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) verfügen. Wenn Sie Outlook.com, Office 365 Home oder Office 365 Personal verwenden und Informationen zu sicheren Links in Outlook benötigen, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="overview"></a>Übersicht

Office 365 Advanced Threat Protection (ATP) schützt Ihre Organisation vor bösartigen Bedrohungen durch E-Mail-Nachrichten, Links (URLs) und Zusammenarbeitstools. ATP enthält folgende Elemente:

- [Threat protection-Richtlinien](#configure-atp-policies): Definieren von Richtlinien für den Bedrohungsschutz, um den geeigneten Schutzgrad für Ihre Organisation festzulegen. 

- [Berichte](#view-office-365-atp-reports): Anzeigen von Echtzeitberichten, um die ATP-Leistung in Ihrer Organisation zu überwachen. 

- [Bedrohungsuntersuchung- und Antwortfunktionen](#use-threat-investigation-and-response-capabilities) Verwenden Sie brandneue Tools, um Bedrohungen zu untersuchen, zu verstehen, zu simulieren und zu verhindern. 

- [Automatisierte Reaktion auf Sicherheitsvorfälle](#save-time-with-automated-incident-response): Sparen Sie Zeit und Mühe beim Untersuchen und Beheben von Bedrohungen.

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP Plan 1 und Plan 2

ATP ist Bestandteil von Office 365 E5. Office 365 ATP Plan 1 und Office 365 ATP Plan 2 sind jedoch jeweils als Add-On für bestimmte Abonnements verfügbar. Weitere Informationen hierzu finden Sie unter [Funktionsverfügbarkeit bei ATP-Plänen](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

> [!TIP]
> Wenn Sie noch nicht über Office 365 ATP verfügen, können [Sie sich für eine kostenlose Testversion registrieren](https://go.microsoft.com/fwlink/p/?LinkID=698279).


## <a name="configure-atp-policies"></a>Konfigurieren von ATP-Richtlinien

Mit Office 365 ATP kann das Sicherheitsteam Ihrer Organisation den Schutz durch Definition von Richtlinien im Office 365 Security & Compliance Center konfigurieren. Navigieren Sie zu [https://protection.office.com](https://protection.office.com) > **Bedrohungsverwaltung** > **Richtlinie**. 

> [!TIP]
> Eine schnelle Liste der zu definierenden Richtlinien finden Sie unter [Schutz vor Bedrohungen](protect-against-threats.md).

Die Richtlinien, die für Ihre Organisation definiert sind, bestimmen das Verhalten und den Schutzgrad für vordefinierte Bedrohungen. Richtlinienoptionen sind äußerst flexibel. Beispielsweise kann das Sicherheitsteam Ihrer Organisation einen fein abgestuften Bedrohungsschutz auf Benutzer-, Organisations-, Empfänger- und Domänenebene festlegen. Es ist wichtig, dass Sie Ihre Richtlinien regelmäßig überprüfen, da täglich neue Bedrohungen und Herausforderungen entstehen.  

- **[ATP-sichere Anlagen](atp-safe-attachments.md)**: Bietet Zero-Day-Schutz, um Ihr Messagingsystem zu schützen, indem E-Mail-Anlagen auf schädliche Inhalte überprüft werden. Es leitet alle Nachrichten und Anlagen, die keine Viren- und Malware-Signaturen aufweisen, an eine spezielle Umgebung weiter, und verwendet dann Machine Learning- und Analysetechniken, um bösartige Absichten zu erkennen. Wenn keine verdächtigen Aktivitäten gefunden werden, wird die Nachricht an das Postfach weitergeleitet. Weitere Informationen hierzu finden Sie unter [Einrichten einer Richtlinie für Office 365 ATP-sichere Anlagen](set-up-atp-safe-attachments-policies.md).

- **[ATP-sichere Links](atp-safe-links.md)**: Bietet eine Zeit-auf-Klick-Überprüfung von URLs, beispielsweise in E-Mails und Office-Dateien. Der Schutz ist laufend aktiv und gilt für Ihre Messaging- und Office-Umgebung. Links werden bei jedem Klick gescannt: sichere Links bleiben verfügbar, bösartige Links werden dynamisch blockiert. Weitere Informationen hierzu finden Sie unter [Einrichten einer Richtlinie für Office 365 ATP-sichere Links](https://docs.microsoft.com/office365/securitycompliance/set-up-atp-safe-links-policies). 

- **[ATP für SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md)**: Schützt Ihre Organisation, wenn Benutzer zusammenarbeiten und Dateien freigeben, indem es schädliche Dateien in Team-Websites und Dokumentbibliotheken identifiziert und blockiert. Weitere Informationen finden Sie unter [Office 365 ATP für SharePoint, OneDrive, und Microsoft Teams aktivieren](turn-on-atp-for-spo-odb-and-teams.md). 

- **[ATP-Antiphishingschutz](atp-anti-phishing.md)**: Erkennt Versuche, Ihre Benutzer und benutzerdefinierten Domänen zu imitieren. Es wendet Machine Learning-Modelle und erweiterte Algorithmen zum Erkennen von Identitätswechsel an, um Phishing-Angriffe zu abzuwenden. Weitere Informationen finden Sie unter[Einrichten von Office 365 ATP-Antiphishing und Antiphishingrichtlinien](set-up-anti-phishing-policies.md).

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

- Mit dem **[Angriffssimulator](attack-simulator.md)** können Sie realistische Angriffsszenarien in Ihrer Organisation ausführen, um Sicherheitsrisiken zu erkennen. Zur Verfügung stehen Simulationen aktueller Angriffstypen, einschließlich eines [Anzeigename – Spear-Phishing-Angriffs](attack-simulator.md#display-name-spear-phishing-attack), eines [Kennwort-Spray-Angriffs](attack-simulator.md#password-spray-attack), eines [Brute-Force-Kennwortangriffs](attack-simulator.md#brute-force-password-attack) und vieles mehr.
    
## <a name="save-time-with-automated-incident-response"></a>Einsparen von Zeit mit der automatisierten Reaktion auf Sicherheitsvorfälle (AIR)

(**NEU!**) Bei der Untersuchung eines potenziellen Cyberangriffs ist Zeit von äußerster Wichtigkeit. Je früher Sie Bedrohungen erkennen und eindämmen können, desto besser für Ihre Organisation. AIR-Funktionen ([automatisierte Reaktion auf Sicherheitsvorfälle](automated-investigation-response-office.md)) umfassen eine Reihe von Sicherheitsplaybooks, die automatisch, z. B. wenn eine Warnung ausgelöst wird, oder manuell, z. B. aus einer Explorer-Ansicht, gestartet werden können. AIR spart Ihrem Team für Sicherheitsvorgänge Zeit und Mühe beim effektiven und effizienten Eindämmen von Bedrohungen. Weitere Informationen hierzu finden Sie unter [AIR in Office 365](automated-investigation-response-office.md).

## <a name="permissions-required-to-use-atp-features"></a>Erforderliche Berechtigungen für die Verwendung von ATP-Funktionen

Für den Zugriff auf ATP-Features im Security & Compliance Center müssen Sie über eine entsprechende Rolle verfügen. Die folgende Tabelle enthält einige Beispiele:

|Rolle oder Rollengruppe  |Ressourcen mit mehr Informationen  |
|---------|---------|
|Globaler Office 365-Administrator (kann in Azure Active Directory oder im Office 365 Security & Compliance Center zugewiesen werden.) |[Informationen zu Office 365-Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|Sicherheitsadministrator (kann in Azure Active Directory oder im Office 365 Security & Compliance Center zugewiesen werden.) |[Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br><br/>[Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)|
|Exchange Online-Organisationsverwaltung (wird in Exchange Online zugewiesen)|[Berechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)<br><br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|
|Suchen und Löschen (wird nur im Office 365 Security & Compliance Center zugewiesen) |[Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) |

Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="get-office-365-atp"></a>Office 365 ATP abrufen

Office 365 ATP ist in bestimmten Abonnements wie Microsoft 365 E5, Office 365 E5, Office 365 A5 und Microsoft 365 Business enthalten. Wenn Ihr Abonnement Office 365 ATP nicht enthält, können Sie ATP Plan 1 oder ATP Plan 2 als Add-On für bestimmte Abonnements erwerben. Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:

- Unter [Verfügbarkeit von Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) finden Sie eine Liste der Abonnements, die ATP-Pläne enthalten.

- Unter [Verfügbarkeit von Features in Advanced Threat Protection (ATP)-Plänen](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) finden Sie eine Liste der in Plan 1 und Plan 2 enthaltenen Features.

- Auf der Seite [Office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) können Sie Pläne vergleichen und Office 365 ATP erwerben.

- [Erste Schritte mit einer kostenlosen Testversion](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-office-365-atp"></a>Ausprobieren neuer Features in Office 365 ATP

Neue Features werden Office 365 ATP kontinuierlich hinzugefügt. Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:

- Die [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) liefert eine Liste neuer Features in Entwicklung und Rollout begriffen.

- Die [Dienstbeschreibung von Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) beschreibt Verfügbarkeit und Funktionen in ATP-Plänen.
