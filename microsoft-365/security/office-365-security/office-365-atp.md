---
title: Office 365 Advanced Threat Protection
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 10/03/2019
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
ms.openlocfilehash: 9f2bedaa436aa5f38d8929e6bc8eda2e34896575
ms.sourcegitcommit: d4aa94716b33e6c270ae7adfbdc4c19cf4a0087d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "37386152"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) verfügen. Wenn Sie Outlook.com, Office 365 Home oder Office 365 Personal verwenden und Informationen zu sicheren Links in Outlook benötigen, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="overview"></a>Übersicht

Office 365 Advanced Threat Protection (ATP) schützt Ihre Organisation vor bösartigen Bedrohungen durch E-Mail-Nachrichten, Links (URLs) und Zusammenarbeitstools. ATP enthält folgende Elemente:

- [Threat protection-Richtlinien](#configure-atp-policies): Definieren von Richtlinien für den Bedrohungsschutz, um den geeigneten Schutzgrad für Ihre Organisation festzulegen. 

- [Berichte](#view-atp-reports): Anzeigen von Echtzeitberichten, um die ATP-Leistung in Ihrer Organisation zu überwachen. 

- [Bedrohungsuntersuchung- und Antwortfunktionen](#use-threat-investigation-and-response-capabilities) Verwenden Sie brandneue Tools, um Bedrohungen zu untersuchen, zu verstehen, zu simulieren und zu verhindern. 

- [Automatisierte Untersuchungs- und Antwortfunktionen](#save-time-with-automated-investigation-and-response) Sparen Sie Zeit und Mühe beim Untersuchen und Beheben von Bedrohungen.

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP Plan 1 und Plan 2

ATP ist Bestandteil von Office 365 E5. ATP Plan 1 und ATP Plan 2 jedoch sind jeweils als Add-On für bestimmte Abonnements verfügbar. Weitere Informationen hierzu finden Sie unter [Funktionsverfügbarkeit bei ATP-Plänen](https://docs.microsoft.com/de-DE/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="configure-atp-policies"></a>Konfigurieren von ATP-Richtlinien

Office 365 ATP bietet zahlreiche Tools zum Festlegen eines geeigneten Schutzgrades für Ihre Organisation. 

Das Sicherheitsteam Ihrer Organisation muss Richtlinien für jedes ATP-Tool im Office 365 Security & Compliance Center definieren. Wechseln Sie zu **Bedrohungsmanagement** > **Richtlinien**, um auf die Richtlinienoptionen zuzugreifen. Weitere Informationen finden Sie unter [Schützen vor Bedrohungen](protect-against-threats.md).

Die Richtlinien, die für Ihre Organisation definiert sind, bestimmen das Verhalten und den Schutzgrad für vordefinierte Bedrohungen. Richtlinienoptionen sind äußerst flexibel. Beispielsweise kann das Sicherheitsteam Ihrer Organisation einen fein abgestuften Bedrohungsschutz auf Benutzer-, Organisations-, Empfänger- und Domänenebene festlegen. Es ist wichtig, dass Sie Ihre Richtlinien regelmäßig überprüfen, da täglich neue Bedrohungen und Herausforderungen entstehen.  

- [ATP-sichere Anlagen](atp-safe-attachments.md): Bietet Zero-Day-Schutz, um Ihr Messagingsystem zu schützen, indem E-Mail-Anlagen auf schädliche Inhalte überprüft werden. Es leitet alle Nachrichten und Anlagen, die keine Viren- und Malware-Signaturen aufweisen, an eine spezielle Umgebung weiter, und verwendet dann Machine Learning- und Analysetechniken, um bösartige Absichten zu erkennen. Wenn keine verdächtigen Aktivitäten gefunden werden, wird die Nachricht an das Postfach weitergeleitet. Weitere Informationen hierzu finden Sie unter [Einrichten einer Richtlinie für Office 365 ATP-sichere Anlagen](set-up-atp-safe-attachments-policies.md).

- [ATP-sichere Links](atp-safe-links.md): Bietet eine Zeit-auf-Klick-Überprüfung von URLs, beispielsweise in E-Mails und Office-Dateien. Der Schutz ist laufend aktiv und gilt für Ihre Messaging- und Office-Umgebung. Links werden bei jedem Klick gescannt: sichere Links bleiben verfügbar, bösartige Links werden dynamisch blockiert. Weitere Informationen hierzu finden Sie unter [Einrichten einer Richtlinie für Office 365 ATP-sichere Links](https://docs.microsoft.com/de-DE/office365/securitycompliance/set-up-atp-safe-links-policies). 

- [ATP für SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md): Schützt Ihre Organisation, wenn Benutzer zusammenarbeiten und Dateien freigeben, indem es schädliche Dateien in Team-Websites und Dokumentbibliotheken identifiziert und blockiert. Weitere Informationen finden Sie unter [Office 365 ATP für SharePoint, OneDrive, und Microsoft Teams aktivieren](turn-on-atp-for-spo-odb-and-teams.md). 

- [ATP-Antiphishingschutz](atp-anti-phishing.md): Erkennt Versuche, Ihre Benutzer und benutzerdefinierten Domänen zu imitieren. Es wendet Machine Learning-Modelle und erweiterte Algorithmen zum Erkennen von Identitätswechsel an, um Phishing-Angriffe zu abzuwenden. Weitere Informationen finden Sie unter[Einrichten von Office 365 ATP-Antiphishing und Antiphishingrichtlinien](set-up-anti-phishing-policies.md).

## <a name="view-atp-reports"></a>ATP-Berichte anzeigen

Office 365 ATP enthält ein erweitertes [Reporting-Dashboard](view-reports-for-atp.md) zum Überwachen Ihrer ATP-Leistung. Sie können über **Berichte > Dashboard** im Security & Compliance Center darauf zugreifen. 

Berichte werden in Echtzeit aktualisiert, sodass Sie die neuesten Erkenntnisse erhalten. Diese Berichte bieten zudem Empfehlungen und warnen Sie vor bevorstehenden Bedrohungen. Vordefinierte Berichte umfassen folgende Informationen: 

- [Sicherheitsrisiken-Explorer (oder Echtzeit-Erkennung)](threat-explorer.md)

- [Threat Protection-Statusbericht](view-reports-for-atp.md#threat-protection-status-report)

- [ATP-Dateitypenbericht](view-reports-for-atp.md#atp-file-types-report)

- [ATP-Bericht zum Nachrichtenstatus](view-reports-for-atp.md#atp-message-disposition-report)

- ... und vieles mehr. 

## <a name="use-threat-investigation-and-response-capabilities"></a>Bedrohungsuntersuchung- und Antwortfunktionen verwenden

Office 365 ATP Plan 2 enthält erstklassige [Bedrohungsuntersuchung- und Antwort-Tools](office-365-ti.md), die das Sicherheitsteam Ihrer Organisation in die Lage versetzen, böswillige Angriffe vorwegzunehmen, zu verstehen und zu verhindern. 

- [Bedrohungs-Tracker](threat-trackers.md) liefern neueste Informationen zu vorherrschenden Internetsicherheitsproblemen. Beispielsweise können Sie Informationen zu der neuesten Malware anzeigen und Gegenmaßnahmen ergreifen, bevor diese zu einer tatsächlichen Bedrohung für Ihre Organisation werden. Verfügbare Tracker sind [beachtenswerte Tracker](threat-trackers.md#noteworthy-trackers), [Trend-Tracker](threat-trackers.md#trending-trackers), [nachverfolgte Abfragen](threat-trackers.md#tracked-queries) und [gespeicherte Abfragen](threat-trackers.md#saved-queries).

- [Bedrohungs-Explorer (oder Echtzeit-Entdeckungen)](threat-explorer.md) (auch als Explorer bezeichnet) ist ein Echtzeit-Bericht, der es Ihnen ermöglicht, aktuelle Bedrohungen zu erkennen und zu analysieren. Sie können Explorer so konfigurieren, dass Daten für benutzerdefinierte Zeiträume angezeigt werden.

- [Angriffssimulator](attack-simulator.md) ermöglicht Ihnen das Ausführen realistischer Angriffsszenarien in Ihrer Organisation, um Sicherheitsrisiken zu erkennen. Zur Verfügung stehen Simulationen aktueller Angriffstypen, einschließlich eines [Anzeigename – Spear-Phishing-Angriffs](attack-simulator.md#display-name-spear-phishing-attack), eines [Kennwort-Spray-Angriffs](attack-simulator.md#password-spray-attack), eines [Brute-Force-Kennwortangriffs](attack-simulator.md#brute-force-password-attack) und vieles mehr.
    
## <a name="save-time-with-automated-investigation-and-response"></a>Zeit sparen mit automatisierten Untersuchungen und Antworten

(**NEU!**) Bei der Untersuchung eines potenziellen Cyberangriffs ist Zeit von äußerster Wichtigkeit. Je früher Sie Bedrohungen erkennen und eindämmen können, desto besser für Ihre Organisation. Die unten aufgeführten Abonnements umfassen nun auch [Automatisierte Untersuchung und Antwort (Automated Investigation and Response, AIR)](automated-investigation-response-office.md)-Funktionen. (Wenn Sie noch nicht über diese Funktionen verfügen, werden Sie sie mit einem dieser Abonnements in Kürze erhalten.) 

Office 365 AIR ist in den folgenden Abonnements enthalten:

- Microsoft 365 E5
- Microsoft 365 E5 Security
- Office 365 E5
- Office 365 Advanced Threat Protection Plan 2

AIR umfasst eine Reihe von Sicherheits-Playbooks, die automatisch gestartet werden können, z.B. wenn eine Benachrichtigung ausgelöst wird, oder manuell, z.B. aus einer Explorer-Ansicht. AIR spart Ihrem Team für Sicherheitsvorgänge Zeit und Mühe beim effektiven und effizienten Eindämmen von Bedrohungen. Weitere Informationen finden Sie unter [Automatisierte Untersuchung und Reaktion (AIR) mit Office 365](automated-investigation-response-office.md).

## <a name="permissions-required-to-use-atp-features"></a>Erforderliche Berechtigungen für die Verwendung von ATP-Funktionen

Für den Zugriff auf ATP-Features im Security & Compliance Center müssen Sie über eine entsprechende Rolle verfügen. Die folgende Tabelle enthält einige Beispiele:

|Rolle oder Rollengruppe  |Ressourcen mit mehr Informationen  |
|---------|---------|
|Globaler Office 365-Administrator |[Informationen zu Office 365-Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|Sicherheitsadministrator |[Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/de-DE/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online-Organisationsverwaltung |[Berechtigungen in Exchange Online](https://docs.microsoft.com/de-DE/exchange/permissions-exo/permissions-exo) <br>und<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

Weitere Informationen finden Sie unter:

- [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) 

- [Freigeben des Benutzerzugriffs auf das Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md)

## <a name="get-office-365-atp"></a>Office 365 ATP abrufen

Office 365 ATP Plan 2 ist in Office 365 Enterprise E5, Office 365 Education A5 und Microsoft 365 Business enthalten. Wenn Ihr Abonnement Office 365 ATP nicht enthält, können Sie ATP Plan 1 oder ATP Plan 2 als Add-On für bestimmte Abonnements erwerben. Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:

- Eine Liste der Abonnements, die ATP-Pläne enthalten, finde Sie unter [Verfügbarkeit von Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability). 

- Eine Liste der in Plan 1 und Plan 2 enthaltenen Features finde Sie unter [Verfügbarkeit von Features in Advanced Threat Protection (ATP)-Plänen](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) 

- Unter [Die richtige Version von Office 365 Advanced Threat Protection erwerben](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) können Sie Pläne vergleichen und Office 365 ATP erwerben.

## <a name="new-features-in-office-365-atp"></a>Ausprobieren neuer Features in Office 365 ATP

Neue Features werden Office 365 ATP kontinuierlich hinzugefügt. Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:

- Die [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) liefert eine Liste neuer Features in Entwicklung und Rollout begriffen.

- Die [Dienstbeschreibung von Office 365 Advanced Threat Protection](https://docs.microsoft.com/de-DE/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) beschreibt Verfügbarkeit und Funktionen in ATP-Plänen. 
