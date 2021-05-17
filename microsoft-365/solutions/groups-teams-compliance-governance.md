---
title: Complianceoptionen für Microsoft 365, Teams und SharePoint Zusammenarbeit
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
description: Erfahren Sie mehr über Complianceoptionen Microsoft 365 Gruppen, Teams und SharePoint Zusammenarbeit.
ms.openlocfilehash: a9a94f0c1886ac5b60292f5f4d4b9b9d6d84380c
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241676"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Complianceoptionen für Microsoft 365, Teams und SharePoint Zusammenarbeit

Microsoft 365 bietet eine vollständige Suite von Tools zur Aufrechterhaltung der Compliance, während Ihre Benutzer zusammenarbeiten. Überprüfen Sie diese Optionen, und überlegen Sie, wie sie Ihren Geschäftlichen Anforderungen, der Vertraulichkeit Ihrer Daten und dem Umfang der Personen entsprechen, mit der Ihre Benutzer zusammenarbeiten müssen.

In der folgenden Tabelle finden Sie eine Kurzübersicht zu den compliance-Steuerelementen, die in Microsoft 365. Weitere Informationen finden Sie in den folgenden Abschnitten.

|Kategorie|Beschreibung|Referenz|
|:-------|:----------|:--------|
|Aufbewahrung von Informationen|||
||Beibehalten von E-Mail- und SharePoint Gruppeninhalten|[Informationen zu Aufbewahrungsrichtlinien für SharePoint und OneDrive](../compliance/retention-policies-sharepoint.md)|
||Beibehalten von Chats und Nachrichten|[Informationen zu Aufbewahrungsrichtlinien für Microsoft Teams.](../compliance/retention-policies-teams.md)|
|Informationsklassifizierung|||
||Klassifizieren von Gruppen und Teams|[Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites verwenden](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Automatisches Klassifizieren vertraulicher Inhalte|[Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](../compliance/apply-sensitivity-label-automatically.md)|
||Verschlüsseln vertraulicher Inhalte|[Einschränken des Zugriffs auf Inhalte mithilfe der Vertraulichkeitsbezeichnungen zur Verschlüsselung](../compliance/encryption-sensitivity-labels.md)|
|Information Protection|||
||Verhindern des Verlusts vertraulicher Informationen|[Informationen zur Verhinderung von Datenverlust](../compliance/dlp-learn-about-dlp.md)|
||Schützen sie vertrauliche Informationen im Chat.|[Verhinderung von Datenverlust (DLP) und Microsoft Teams](../compliance/dlp-microsoft-teams.md).|
||Definieren der vertraulichen Informationen Ihrer Organisation|[Benutzerdefinierte vertrauliche Informationstypen](../compliance/sensitive-information-type-learn-about.md)|
|Benutzersegmentierung|||
||Einschränken der Kommunikation zwischen Benutzersegmenten|[Informationsbarrieren](../compliance/information-barriers.md)|
|Datenaufbewahrung|||
||Store daten an bestimmten geografischen Standorten|[Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)|

## <a name="information-retention"></a>Aufbewahrung von Informationen

Aufbewahrungsrichtlinien stehen zum Beibehalten oder Löschen von Elementen zur Verfügung, die für die Zusammenarbeit in Gruppen und Teams verwendet werden, einschließlich Dateien, Nachrichten und E-Mails. Richtlinien können so festgelegt werden, dass sie beibehalten und gelöscht werden, nur beibehalten oder nur gelöscht werden. Informationen, die von einer Aufbewahrungsrichtlinie abgedeckt werden, werden für den Fall geschützt, dass die Gruppe oder das Team abläuft oder anderweitig gelöscht wird.

Das Konfigurieren einer Aufbewahrungsrichtlinie für Microsoft 365 umfasst das Gruppenpostfach und die zugehörigen SharePoint und Dateien.

- [Informationen zu Aufbewahrungsrichtlinien für SharePoint und OneDrive](../compliance/retention-policies-sharepoint.md)

Aufbewahrungsrichtlinien für Teams Chat- und Kanalnachrichten beibehalten. Chat- und Kanalnachrichten werden zwar in Exchange gespeichert, sie sind jedoch nicht von den aufbewahrungsrichtlinien Exchange betroffen. Sie müssen ihre Aufbewahrungsrichtlinien so festlegen, dass sie für Teams und Teams gelten. 

Benutzerchats werden auch dann unbegrenzt aufbewahrt, wenn ein Benutzerkonto gelöscht wird. Wenn Sie diese Daten nicht unbegrenzt speichern möchten, sollten Sie eine Aufbewahrungsrichtlinie verwenden, um Benutzerchats nach einer bestimmten Zeit zu löschen, oder fügen Sie diesen Löschvorgang in Ihren Benutzerlöschvorgang ein.

- [Informationen zu Aufbewahrungsrichtlinien für Microsoft Teams.](../compliance/retention-policies-teams.md)

- [Aufbewahrungsrichtlinien in Microsoft Teams](/microsoftteams/retention-policies)

Eine einzelne Aufbewahrungsrichtlinie kann so festgelegt werden, dass sie auf chat- und Teams und Teams angewendet wird. 

Zusätzliche Ressourcen:

- [Informationen zu Aufbewahrungsrichtlinien](../compliance/retention.md)

- [Aufbewahrungstags und Aufbewahrungsrichtlinien](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) in Exchange

## <a name="information-classification"></a>Informationsklassifizierung

Sie können Vertraulichkeitsbezeichnungen verwenden, um den Gastzugriff, den Gruppen- und Teamdatenschutz sowie den Zugriff durch nicht verwaltete Geräte für Gruppen und Teams zu steuern. Durch anwenden der Bezeichnung werden diese Einstellungen automatisch entsprechend den Bezeichnungseinstellungen konfiguriert.

- [Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites verwenden](../compliance/sensitivity-labels-teams-groups-sites.md)

Sie können Microsoft 365 so konfigurieren, dass Vertraulichkeitsbezeichnungen basierend auf den angegebenen Kriterien automatisch auf Dateien und E-Mails angewendet werden, einschließlich der Erkennung vertraulicher Informationstypen oder des Musterabgleichs mit trainierbaren Klassifizierungen.

- [Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](../compliance/apply-sensitivity-label-automatically.md)

Sie können Vertraulichkeitsbezeichnungen verwenden, um Dateien zu verschlüsseln, sodass sie nur von Benutzern mit Berechtigungen entschlüsselt und gelesen werden können.

- [Einschränken des Zugriffs auf Inhalte mithilfe der Vertraulichkeitsbezeichnungen zur Verschlüsselung](../compliance/encryption-sensitivity-labels.md)

- [Konfigurieren eines Teams mit Sicherheitsisolierung](./secure-teams-security-isolation.md)

Zusätzliche Ressourcen:

- [Weitere Informationen zu Vertraulichkeitsbezeichnungen](../compliance/sensitivity-labels.md)


## <a name="information-protection"></a>Information Protection

DLP-Richtlinien können verhindern, dass vertrauliche Informationen versehentlich SharePoint, Exchange und Teams. Sie können Richtlinien erstellen, die aktionen (z. B. Sperren des Zugriffs) basierend auf einer Reihe von Regeln angeben.

- [Informationen zur Verhinderung von Datenverlust](../compliance/dlp-learn-about-dlp.md)

DLP in Teams kann zum Schutz vertraulicher Informationen in chat- Teams Kanalnachrichten beitragen, indem Nachrichten gelöscht werden, die vertrauliche Informationen enthalten.

- [Verhinderung von Datenverlust (DLP) und Microsoft Teams](../compliance/dlp-microsoft-teams.md).

Wenn Sie über vertrauliche Informationen verfügen, die für Ihre Organisation eindeutig sind, z. B. Projektcodenamen, können Sie eigene Typen vertraulicher Informationen erstellen und diese auf DLP-Richtlinien anwenden, um Inhalte in Gruppen, Teams und Sharepoint zu schützen.

- [Benutzerdefinierte vertrauliche Informationstypen](../compliance/sensitive-information-type-learn-about.md)

## <a name="user-segmentation"></a>Benutzersegmentierung

Mit Informationsbarrieren können Sie Ihre Daten und Benutzer segmentieren, um unerwünschte Kommunikation und Zusammenarbeit zwischen Gruppen einzuschränken und Interessenkonflikte in Ihrer Organisation zu vermeiden. Mit Informationsbarrieren können Sie Richtlinien erstellen, um dateizusammenarbeit, Chats, Anrufe oder Besprechungseinladungen zwischen Personengruppen in Ihrer Organisation zu ermöglichen oder zu verhindern.

- [Informationsbarrieren](../compliance/information-barriers.md)

- [Informationsbarrieren in Microsoft Teams](/microsoftteams/information-barriers-in-teams)

- [Verwenden von Informationsbarrieren mit SharePoint](/sharepoint/information-barriers)

## <a name="data-residency"></a>Datenaufbewahrung

Mit Microsoft 365 Multi-Geo können Sie Ruhedaten an den geografischen Standorten bereitstellen und speichern, die Sie ausgewählt haben, um die Anforderungen an die Datenresidenz zu erfüllen. In einer Multi-Geo-Umgebung besteht Ihr Microsoft 365-Mandant aus einem zentralen Standort (an dem Ihr Microsoft 365-Abonnement ursprünglich bereitgestellt wurde) und einem oder mehreren Satellitenstandorten, an denen Sie Daten speichern können.

- [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)

- [Plan für Microsoft 365 Multi-Geo](/microsoft-365/enterprise/plan-for-multi-geo)

## <a name="related-topics"></a>Verwandte Themen

[Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Erstellen eines Plans für die Zusammenarbeitsgovernance](collaboration-governance-first.md)

[Sicherheit und Compliance für Exchange Online](/exchange/security-and-compliance/security-and-compliance)

[Schützen von Informationen](../compliance/information-protection.md)
