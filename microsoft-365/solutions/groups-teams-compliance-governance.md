---
title: Kompatibilitätsoptionen für Microsoft 365-Gruppen, Teams und SharePoint-Zusammenarbeit
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Hier finden Sie Informationen zu Kompatibilitätsoptionen für Microsoft 365-Gruppen, Teams und SharePoint-Zusammenarbeit.
ms.openlocfilehash: 0383b0728d9b8ea12ce75de8bf0e250932d14ae5
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377533"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Kompatibilitätsoptionen für Microsoft 365-Gruppen, Teams und SharePoint-Zusammenarbeit

Microsoft 365 bietet eine umfassende Sammlung von Tools, mit denen die Einhaltung der Anforderungen bei der Zusammenarbeit der Benutzer gewährleistet wird. Überprüfen Sie diese Optionen, und überprüfen Sie, wie Sie Ihre geschäftlichen Anforderungen, die Vertraulichkeit Ihrer Daten und den Umfang der Personen abbilden, mit denen Ihre Benutzer zusammenarbeiten müssen.

Die folgende Tabelle enthält eine Kurzübersicht über die in Microsoft 365 verfügbaren Konformitäts Steuerelemente. Weitere Informationen finden Sie in den folgenden Abschnitten.

|Kategorie|Beschreibung|Referenz|
|:-------|:----------|:--------|
|Informationsaufbewahrung|||
||Beibehalten von Gruppen-e-Mail-und SharePoint-Inhalten|[Informationen zu Aufbewahrungsrichtlinien für SharePoint und OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)|
||Chat und Nachrichten beibehalten|[Informationen zu Aufbewahrungsrichtlinien für Microsoft Teams.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)|
|Informationsklassifizierung|||
||Klassifizieren von Gruppen und Teams|[Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites verwenden](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Automatisches Klassifizieren von vertraulichen Inhalten|[Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)|
||Vertraulichen Inhalt verschlüsseln|[Einschränken des Zugriffs auf Inhalte mithilfe der Vertraulichkeitsbezeichnungen zur Verschlüsselung](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)|
|Information Protection|||
||Verhindern des Verlusts von vertraulichen Informationen|[Verhinderung von Datenverlust – Übersicht](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|
||Schützen Sie vertrauliche Informationen im Chat.|[Verhinderung von Datenverlust und Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)|
||Definieren der vertraulichen Informationen Ihrer Organisation|[Benutzerdefinierte vertrauliche Informationstypen](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)|
|Benutzersegmentierung|||
||Einschränken der Kommunikation zwischen Benutzersegmenten|[Informationsbarrieren](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)|

## <a name="information-retention"></a>Informationsaufbewahrung

Aufbewahrungsrichtlinien stehen zur Verfügung, um Elemente, die für die Zusammenarbeit in Gruppen und Teams verwendet werden, zu speichern oder zu löschen, einschließlich Dateien, Nachrichten und e-Mail. Richtlinien können so festgelegt werden, dass Sie beibehalten oder gelöscht, nur beibehalten oder nur gelöscht werden. Informationen, die von einer Aufbewahrungsrichtlinie abgedeckt werden, sind für den Fall geschützt, dass die Gruppe oder das Team abläuft oder anderweitig gelöscht wird.

Das Konfigurieren einer Aufbewahrungsrichtlinie für Microsoft 365-Gruppen umfasst das Gruppenpostfach und die zugehörige SharePoint-Website und die dazugehörigen Dateien.

- [Informationen zu Aufbewahrungsrichtlinien für SharePoint und OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)

Aufbewahrungsrichtlinien für Teams behalten Chat-und Kanal Nachrichten bei. Während Chat-und Kanal Nachrichten in Exchange-Postfächern gespeichert werden, sind Sie von Exchange-Aufbewahrungsrichtlinien nicht betroffen. Sie müssen ihre Aufbewahrungsrichtlinien so festlegen, dass Sie auf teamchats und Teams-Kanal Nachrichten angewendet werden:

- [Informationen zu Aufbewahrungsrichtlinien für Microsoft Teams.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

- [Aufbewahrungsrichtlinien in Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies)

Eine einzelne Aufbewahrungsrichtlinie kann so festgelegt werden, dass Sie auf Microsoft 365-Gruppen, teamchats und Teams-Kanal Nachrichten angewendet wird. 

Zusätzliche Ressourcen:

- [Informationen zu Aufbewahrungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

- [Aufbewahrungstags und Aufbewahrungsrichtlinien](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) in Exchange

## <a name="information-classification"></a>Informationsklassifizierung

Sie können Sensitivitäts Bezeichnungen verwenden, um Gastzugriff, Gruppen-und Team Datenschutz sowie Zugriff durch nicht verwaltete Geräte für Gruppen und Teams zu steuern. Durch Anwenden der Bezeichnung werden diese Einstellungen automatisch so konfiguriert, wie in den Bezeichnungs Einstellungen angegeben.

- [Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites verwenden](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Sie können Microsoft 365 so konfigurieren, dass die Vertraulichkeits Bezeichnungen auf Dateien und e-Mails basierend auf den von Ihnen angegebenen Kriterien automatisch angewendet werden, einschließlich der Erkennung vertraulicher Informationstypen oder der Musterübereinstimmung mit Schulungs Klassifizierern.

- [Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

Sie können Sensitivitäts Bezeichnungen zum Verschlüsseln von Dateien verwenden, sodass nur diejenigen mit Berechtigungen Sie entschlüsseln und lesen können.

- [Einschränken des Zugriffs auf Inhalte mithilfe der Vertraulichkeitsbezeichnungen zur Verschlüsselung](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

- [Konfigurieren eines Teams mit Sicherheitsisolierung](https://docs.microsoft.com/microsoft-365/solutions/secure-teams-security-isolation)

Zusätzliche Ressourcen:

- [Weitere Informationen zu Vertraulichkeitsbezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)


## <a name="information-protection"></a>Information Protection

Mit DLP-Richtlinien kann verhindert werden, dass vertrauliche Informationen in SharePoint, Exchange und Microsoft Teams versehentlich freigegeben werden. Sie können Richtlinien erstellen, mit denen auszuführende Aktionen (beispielsweise Sperrung des Zugriffs) basierend auf einem Regelsatz angegeben werden.

- [Verhinderung von Datenverlust – Übersicht](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

DLP in Teams kann zum Schutz vertraulicher Informationen in Microsoft Teams-Chat und Kanal Nachrichten beitragen, indem Sie Nachrichten löschen, die vertrauliche Informationen enthalten.

- [Verhinderung von Datenverlust und Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)

Wenn Sie über vertrauliche Informationen verfügen, die für Ihre Organisation eindeutig sind, beispielsweise Projektcodenamen, können Sie eigene vertrauliche Informationstypen erstellen und diese auf DLP-Richtlinien anwenden, um Inhalte in Gruppen, Teams und SharePoint zu schützen.

- [Benutzerdefinierte vertrauliche Informationstypen](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)

## <a name="user-segmentation"></a>Benutzersegmentierung

Mit Informationsbarrieren können Sie Ihre Daten und Benutzer segmentieren, um unerwünschte Kommunikation und Zusammenarbeit zwischen Gruppen einzuschränken und Interessenkonflikte in Ihrer Organisation zu vermeiden. Mit Informationsbarrieren können Sie Richtlinien erstellen, um die Zusammenarbeit in der Datei zu ermöglichen oder zu verhindern, chatten, Anrufe oder Einladungen zwischen Personengruppen in Ihrer Organisation zu treffen.

- [Informationsbarrieren](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

- [Informationsbarrieren in Microsoft Teams](https://docs.microsoft.com/microsoftteams/information-barriers-in-teams)

- [Verwenden von Informationsbarrieren mit SharePoint](https://docs.microsoft.com/sharepoint/information-barriers)

## <a name="related-topics"></a>Verwandte Themen

[Sicherheit und Compliance für Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance)

[Schützen von Informationen](https://docs.microsoft.com/microsoft-365/compliance/protect-information)


